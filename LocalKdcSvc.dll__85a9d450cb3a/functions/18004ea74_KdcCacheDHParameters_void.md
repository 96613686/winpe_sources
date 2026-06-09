# KdcCacheDHParameters(void)

- ea: `0x18004ea74`
- end: `0x18004ecad`
- name: `?KdcCacheDHParameters@@YAJXZ`
- size: `569`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050e78`
- `0x180053ec0`

## callees

- `0x1800101ec`
- `0x18001022c`
- `0x180010718`
- `0x1800107dc`
- `0x18004d9bc`
- `0x18004ea74`
- `0x180079228`
- `0x18008441c`
- `0x180084fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb44`
- `ntdll!NtQuerySystemTime` at `0x18004eb77`
- `ntdll!NtQuerySystemTime` at `0x18004eb77`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004eaa4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004eaa4`
- `bcrypt!BCryptDestroyKey` at `0x18004ec08`
- `bcrypt!BCryptDestroyKey` at `0x18004ec08`

## pseudocode

```c
__int64 KdcCacheDHParameters(void)
{
  __int64 v0; // rax
  int v1; // edx
  unsigned int ECDHKey; // ebx
  int v3; // edx
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 i; // rdi
  CSecurityData *v7; // rcx
  __int64 v8; // rdx
  BCRYPT_KEY_HANDLE *v9; // rbx
  _BYTE v11[16]; // [rsp+30h] [rbp-10h] BYREF
  char v12; // [rsp+70h] [rbp+30h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+78h] [rbp+38h] BYREF
  char v14; // [rsp+80h] [rbp+40h] BYREF

  SystemTime.QuadPart = 0;
  v12 = 0;
  if ( !KdcGlobalDHParametersInitialized )
  {
    RtlAcquireResourceExclusive(&KdcGlobalDHParametersLock, 1u);
    v0 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v14, &v12);
    wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v11, v0);
    if ( KdcGlobalDHParametersInitialized )
    {
      ECDHKey = 0;
LABEL_31:
      wil::details::lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___::_lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___(v11);
      return ECDHKey;
    }
    v12 = 1;
    if ( KerbGenerateDHParameters(0x400u, v1, &KdcGlobalDHParameters) )
    {
      if ( KerbGenerateDHParameters(0x800u, v3, &stru_1800B44C8) )
      {
        NtQuerySystemTime(&SystemTime);
        for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
        {
          (&KdcGlobalDHKeyExpirationTime)[i] = (union _LARGE_INTEGER near *)(SystemTime.QuadPart
                                                                           + KdcGlobalAllowedDHKeyLifeTime.QuadPart);
          ECDHKey = KerbDHCreateBCryptKey(&KdcGlobalDHParameters + i, (void **)&(&KdcGlobalCachedDHKeys)[i]);
          if ( ECDHKey )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 123;
LABEL_30:
              WPP_SF_Dd(
                *((_QWORD *)v7 + 2),
                v8,
                WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
                (unsigned int)i,
                ECDHKey);
            }
            goto LABEL_31;
          }
        }
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= 3 )
          {
            KdcGlobalDHParametersInitialized = 1;
            v12 = 0;
            wil::details::lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___::_lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___(v11);
            return 0;
          }
          v9 = (BCRYPT_KEY_HANDLE *)&(&KdcGlobalCachedECDHKeys)[i];
          if ( *v9 )
          {
            BCryptDestroyKey(*v9);
            *v9 = 0;
          }
          ECDHKey = KerbGenerateECDHKey(
                      *((_DWORD *)&KerbGlobalECCNamedCurves + 18 * i),
                      (BCRYPT_KEY_HANDLE *)&(&KdcGlobalCachedECDHKeys)[i]);
          if ( ECDHKey )
            break;
          (&KdcGlobalECDHKeyExpirationTime)[i] = (union _LARGE_INTEGER near *)(SystemTime.QuadPart
                                                                             + KdcGlobalAllowedDHKeyLifeTime.QuadPart);
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 124;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v5 = 122;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      LastError = GetLastError();
      v5 = 121;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, LastError);
LABEL_13:
    ECDHKey = 60;
    goto LABEL_31;
  }
  return 0;
}

```

## disassembly

```asm
0x18004ea74  push    rbp
0x18004ea76  push    rbx
0x18004ea77  push    rsi
0x18004ea78  push    rdi
0x18004ea79  push    r12
0x18004ea7b  mov     rbp, rsp
0x18004ea7e  sub     rsp, 40h
0x18004ea82  mov     qword ptr [rbp+SystemTime], 0
0x18004ea8a  mov     [rbp+arg_0], 0
0x18004ea8e  cmp     cs:?KdcGlobalDHParametersInitialized@@3JA, 0; long KdcGlobalDHParametersInitialized
0x18004ea95  jnz     loc_18004ECA0
0x18004ea9b  mov     dl, 1; Wait
0x18004ea9d  lea     rcx, ?KdcGlobalDHParametersLock@@3U_RTL_RESOURCE@@A; Resource
0x18004eaa4  call    cs:__imp_RtlAcquireResourceExclusive
0x18004eaaa  lea     rdx, [rbp+arg_0]
0x18004eaae  lea     rcx, [rbp+arg_10]
0x18004eab2  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x18004eab7  mov     rdx, rax
0x18004eaba  lea     rcx, [rbp+var_10]
0x18004eabe  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x18004eac3  nop
0x18004eac4  cmp     cs:?KdcGlobalDHParametersInitialized@@3JA, 0; long KdcGlobalDHParametersInitialized
0x18004eacb  jz      short loc_18004EAD4
0x18004eacd  xor     ebx, ebx
0x18004eacf  jmp     loc_18004EC7C
0x18004ead4  mov     [rbp+arg_0], 1
0x18004ead8  lea     rsi, ?KdcGlobalDHParameters@@3PAU_CERT_X942_DH_PARAMETERS@@A; _CERT_X942_DH_PARAMETERS near * KdcGlobalDHParameters
0x18004eadf  mov     r8, rsi; struct _CERT_X942_DH_PARAMETERS *
0x18004eae2  mov     ecx, 400h; unsigned int
0x18004eae7  call    ?KerbGenerateDHParameters@@YAHKHPEAU_CERT_X942_DH_PARAMETERS@@@Z; KerbGenerateDHParameters(ulong,int,_CERT_X942_DH_PARAMETERS *)
0x18004eaec  test    eax, eax
0x18004eaee  jnz     short loc_18004EB16
0x18004eaf0  lea     rax, WPP_GLOBAL_Control
0x18004eaf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eafe  cmp     rcx, rax
0x18004eb01  jz      short loc_18004EB69
0x18004eb03  test    byte ptr [rcx+1Ch], 1
0x18004eb07  jz      short loc_18004EB69
0x18004eb09  call    cs:__imp_GetLastError
0x18004eb0f  mov     edx, 79h ; 'y'
0x18004eb14  jmp     short loc_18004EB4F
0x18004eb16  lea     r8, stru_1800B44C8; struct _CERT_X942_DH_PARAMETERS *
0x18004eb1d  mov     ecx, 800h; unsigned int
0x18004eb22  call    ?KerbGenerateDHParameters@@YAHKHPEAU_CERT_X942_DH_PARAMETERS@@@Z; KerbGenerateDHParameters(ulong,int,_CERT_X942_DH_PARAMETERS *)
0x18004eb27  test    eax, eax
0x18004eb29  jnz     short loc_18004EB73
0x18004eb2b  lea     rax, WPP_GLOBAL_Control
0x18004eb32  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb39  cmp     rcx, rax
0x18004eb3c  jz      short loc_18004EB69
0x18004eb3e  test    byte ptr [rcx+1Ch], 1
0x18004eb42  jz      short loc_18004EB69
0x18004eb44  call    cs:__imp_GetLastError
0x18004eb4a  mov     edx, 7Ah ; 'z'
0x18004eb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb56  mov     r9d, eax
0x18004eb59  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18004eb60  mov     rcx, [rcx+10h]
0x18004eb64  call    WPP_SF_d
0x18004eb69  mov     ebx, 3Ch ; '<'
0x18004eb6e  jmp     loc_18004EC7C
0x18004eb73  lea     rcx, [rbp+SystemTime]; SystemTime
0x18004eb77  call    cs:__imp_NtQuerySystemTime
0x18004eb7d  xor     edi, edi
0x18004eb7f  lea     r12, __ImageBase
0x18004eb86  cmp     edi, 2
0x18004eb89  jnb     short loc_18004EBE9
0x18004eb8b  mov     rdx, cs:?KdcGlobalAllowedDHKeyLifeTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KdcGlobalAllowedDHKeyLifeTime
0x18004eb92  add     rdx, qword ptr [rbp+SystemTime]
0x18004eb96  mov     rva ?KdcGlobalDHKeyExpirationTime@@3PAT_LARGE_INTEGER@@A[r12+rdi*8], rdx; _LARGE_INTEGER near * KdcGlobalDHKeyExpirationTime ...
0x18004eb9e  lea     rdx, rva ?KdcGlobalCachedDHKeys@@3PAPEAXA[r12]; void * near * KdcGlobalCachedDHKeys ...
0x18004eba6  lea     rdx, [rdx+rdi*8]; void **
0x18004ebaa  lea     rax, [rdi+rdi*8]
0x18004ebae  lea     rcx, [rsi+rax*8]; struct _CERT_X942_DH_PARAMETERS *
0x18004ebb2  call    ?KerbDHCreateBCryptKey@@YAJAEBU_CERT_X942_DH_PARAMETERS@@PEAPEAX@Z; KerbDHCreateBCryptKey(_CERT_X942_DH_PARAMETERS const &,void * *)
0x18004ebb7  mov     ebx, eax
0x18004ebb9  test    eax, eax
0x18004ebbb  jnz     short loc_18004EBC1
0x18004ebbd  inc     edi
0x18004ebbf  jmp     short loc_18004EB86
0x18004ebc1  lea     rax, WPP_GLOBAL_Control
0x18004ebc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebcf  cmp     rcx, rax
0x18004ebd2  jz      loc_18004EC7C
0x18004ebd8  test    byte ptr [rcx+1Ch], 1
0x18004ebdc  jz      loc_18004EC7C
0x18004ebe2  mov     edx, 7Bh ; '{'
0x18004ebe7  jmp     short loc_18004EC64
0x18004ebe9  xor     edi, edi
0x18004ebeb  cmp     edi, 3
0x18004ebee  jnb     loc_18004EC89
0x18004ebf4  lea     rbx, rva ?KdcGlobalCachedECDHKeys@@3PAPEAXA[r12]; void * near * KdcGlobalCachedECDHKeys ...
0x18004ebfc  lea     rbx, [rbx+rdi*8]
0x18004ec00  mov     rcx, [rbx]; hKey
0x18004ec03  test    rcx, rcx
0x18004ec06  jz      short loc_18004EC15
0x18004ec08  call    cs:__imp_BCryptDestroyKey
0x18004ec0e  mov     qword ptr [rbx], 0
0x18004ec15  lea     rcx, [rdi+rdi*8]
0x18004ec19  mov     rdx, rbx; phKey
0x18004ec1c  mov     ecx, rva ?KerbGlobalECCNamedCurves@@3PAU_KERB_ECC_CURVE_INFO@@A[r12+rcx*8]; dwLength
0x18004ec24  call    ?KerbGenerateECDHKey@@YAJKPEAPEAX@Z; KerbGenerateECDHKey(ulong,void * *)
0x18004ec29  mov     ebx, eax
0x18004ec2b  test    eax, eax
0x18004ec2d  jnz     short loc_18004EC46
0x18004ec2f  mov     rdx, cs:?KdcGlobalAllowedDHKeyLifeTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KdcGlobalAllowedDHKeyLifeTime
0x18004ec36  add     rdx, qword ptr [rbp+SystemTime]
0x18004ec3a  mov     rva ?KdcGlobalECDHKeyExpirationTime@@3PAT_LARGE_INTEGER@@A[r12+rdi*8], rdx; _LARGE_INTEGER near * KdcGlobalECDHKeyExpirationTime ...
0x18004ec42  inc     edi
0x18004ec44  jmp     short loc_18004EBEB
0x18004ec46  lea     rax, WPP_GLOBAL_Control
0x18004ec4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec54  cmp     rcx, rax
0x18004ec57  jz      short loc_18004EC7C
0x18004ec59  test    byte ptr [rcx+1Ch], 1
0x18004ec5d  jz      short loc_18004EC7C
0x18004ec5f  mov     edx, 7Ch ; '|'
0x18004ec64  mov     [rsp+40h+var_20], ebx
0x18004ec68  mov     r9d, edi
0x18004ec6b  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18004ec72  mov     rcx, [rcx+10h]
0x18004ec76  call    WPP_SF_Dd
0x18004ec7b  nop
0x18004ec7c  lea     rcx, [rbp+var_10]
0x18004ec80  call    wil__details__lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253______lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___
0x18004ec85  mov     eax, ebx
0x18004ec87  jmp     short loc_18004ECA2
0x18004ec89  mov     cs:?KdcGlobalDHParametersInitialized@@3JA, 1; long KdcGlobalDHParametersInitialized
0x18004ec93  mov     [rbp+arg_0], 0
0x18004ec97  lea     rcx, [rbp+var_10]
0x18004ec9b  call    wil__details__lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253______lambda_call__lambda_7db228113d7dc8c3bd6a433c5c777253___
0x18004eca0  xor     eax, eax
0x18004eca2  add     rsp, 40h
0x18004eca6  pop     r12
0x18004eca8  pop     rdi
0x18004eca9  pop     rsi
0x18004ecaa  pop     rbx
0x18004ecab  pop     rbp
0x18004ecac  retn
```
