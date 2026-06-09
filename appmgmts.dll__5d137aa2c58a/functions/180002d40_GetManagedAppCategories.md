# GetManagedAppCategories

- ea: `0x180002d40`
- end: `0x1800030ac`
- name: `GetManagedAppCategories`
- size: `876`
- prototype: `RPC_STATUS __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002aa0`
- `0x180002d40`
- `0x18000c0b0`
- `0x18000c3bc`
- `0x18000df00`
- `0x18000e4f0`
- `0x18000e69c`
- `0x18000e744`
- `0x18001bb70`
- `0x18001bec0`
- `0x1800295b4`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180002d7a`
- `RPCRT4!RpcImpersonateClient` at `0x180002d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002d88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002d88`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002da1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000308d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000308d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002dc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002dc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000307d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000307d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002de1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000306b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002de1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000306b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e41`
- `USERENV!LeaveCriticalPolicySection` at `0x180002fe9`
- `USERENV!LeaveCriticalPolicySection` at `0x180002fe9`

## pseudocode

```c
RPC_STATUS __fastcall GetManagedAppCategories(__int64 a1, __int64 a2)
{
  RPC_STATUS result; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  int AppCategories; // edi
  unsigned int v7; // edx
  unsigned int i; // ecx
  __int64 v9; // r9
  __int64 v10; // rax
  char *v11; // rax
  char *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r11
  unsigned __int16 *v16; // r11
  __int64 v17; // r8
  const unsigned __int16 *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rax
  signed int v21; // ebx
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v24[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  int v28; // [rsp+B0h] [rbp-50h]
  _BYTE *v29; // [rsp+B8h] [rbp-48h]
  __int128 *v30; // [rsp+C0h] [rbp-40h]
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v32; // [rsp+F0h] [rbp-10h]
  signed int *v33; // [rsp+F8h] [rbp-8h]
  _BYTE v34[360]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v35[64]; // [rsp+2C8h] [rbp+1C8h] BYREF
  HANDLE hSection; // [rsp+308h] [rbp+208h]
  unsigned int v37; // [rsp+390h] [rbp+290h] BYREF
  void *TokenHandle; // [rsp+398h] [rbp+298h] BYREF

  TokenHandle = 0;
  phkResult = 0;
  *(_OWORD *)a2 = 0;
  v22 = 0;
  result = RpcImpersonateClient(0);
  if ( result )
    return result;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) && (LastError = GetLastError()) != 0
    || (LastError = RegOpenCurrentUser(0x10000000u, &phkResult)) != 0 )
  {
    RevertToSelf();
    goto LABEL_45;
  }
  AppCategories = CsGetAppCategories(&v22);
  RevertToSelf();
  if ( AppCategories >= 0 )
  {
    v7 = 0;
    for ( i = 32 * v22; v7 < (unsigned int)v22; i += 2 * v10 + 2 )
    {
      v9 = *(_QWORD *)(32LL * v7 + *((_QWORD *)&v22 + 1) + 8);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v9 + 2 * v10) );
      }
      else
      {
        LODWORD(v10) = 0;
      }
      ++v7;
    }
    v11 = (char *)LocalAlloc(0x40u, i);
    *(_QWORD *)(a2 + 8) = v11;
    v12 = v11;
    if ( v11 )
    {
      v13 = v22;
      v14 = 0;
      v15 = (unsigned int)v22;
      *(_DWORD *)a2 = v22;
      v16 = (unsigned __int16 *)&v12[32 * v15];
      if ( v13 )
      {
        while ( 1 )
        {
          v17 = 32LL * v14;
          *(_DWORD *)(v17 + *(_QWORD *)(a2 + 8)) = *(_DWORD *)(v17 + *((_QWORD *)&v22 + 1));
          *(_OWORD *)(v17 + *(_QWORD *)(a2 + 8) + 16) = *(_OWORD *)(v17 + *((_QWORD *)&v22 + 1) + 16);
          *(_QWORD *)(v17 + *(_QWORD *)(a2 + 8) + 8) = v16;
          v18 = *(const unsigned __int16 **)(v17 + *((_QWORD *)&v22 + 1) + 8);
          if ( v18 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v18[v19] );
            AppCategories = StringCchCopyW(v16, v19 + 1, v18);
            if ( AppCategories < 0 )
              break;
          }
          if ( v16 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v16[v20] );
            v16 += v20 + 1;
          }
          if ( ++v14 >= (unsigned int)v22 )
            goto LABEL_24;
        }
      }
      else
      {
LABEL_24:
        v37 = 0;
        CRsopAppContext::CRsopAppContext((CRsopAppContext *)v31, 2u, 0, 0);
        CManagedAppProcessor::CManagedAppProcessor(
          (CManagedAppProcessor *)v34,
          0,
          TokenHandle,
          phkResult,
          0,
          1,
          0,
          (struct CRsopAppContext *)v31,
          &v37);
        v21 = v37;
        if ( v37 )
        {
          if ( (int)v37 > 0 )
            v21 = (unsigned __int16)v37 | 0x80070000;
        }
        else
        {
          v24[0] = &CCategoryInfoLog::`vftable';
          v24[1] = 0;
          v25 = 0;
          v29 = v35;
          v28 = 0;
          v30 = &v22;
          v26 = 0;
          v21 = 0;
          v27 = 0;
          if ( !CRsopContext::GetExclusiveLoggingAccess((CRsopContext *)v35, TokenHandle == 0) )
            v21 = CCategoryInfoLog::WriteLog((CCategoryInfoLog *)v24);
          if ( hSection )
          {
            LeaveCriticalPolicySection(hSection);
            hSection = 0;
          }
          CCategoryInfoLog::~CCategoryInfoLog((CCategoryInfoLog *)v24);
        }
        if ( v21 < 0 )
        {
          if ( v32 && v33 )
            *v33 = v21;
          v32 = 0;
        }
        CManagedAppProcessor::~CManagedAppProcessor((CManagedAppProcessor *)v34);
        CRsopAppContext::~CRsopAppContext((CRsopAppContext *)v31);
      }
      LastError = 0;
      if ( !AppCategories )
        goto LABEL_43;
      if ( (AppCategories & 0x1FFF0000) != 0x70000 )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = AppCategories;
        goto LABEL_43;
      }
    }
    else
    {
      LOWORD(AppCategories) = 14;
    }
    LastError = (unsigned __int16)AppCategories;
LABEL_43:
    ReleaseAppCategoryInfoList(&v22);
  }
LABEL_45:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastError;
}

```

## disassembly

```asm
0x180002d40  mov     [rsp-8+arg_0], rbx
0x180002d45  push    rbp
0x180002d46  push    rsi
0x180002d47  push    rdi
0x180002d48  push    r12
0x180002d4a  push    r14
0x180002d4c  lea     rbp, [rsp-250h]
0x180002d54  sub     rsp, 350h
0x180002d5b  xorps   xmm0, xmm0
0x180002d5e  xor     r14d, r14d
0x180002d61  xor     ecx, ecx; BindingHandle
0x180002d63  mov     [rbp+270h+TokenHandle], r14
0x180002d6a  mov     [rsp+370h+phkResult], r14
0x180002d6f  mov     rsi, rdx
0x180002d72  movups  xmmword ptr [rdx], xmm0
0x180002d75  movups  [rsp+370h+var_320], xmm0
0x180002d7a  call    cs:__imp_RpcImpersonateClient
0x180002d80  test    eax, eax
0x180002d82  jnz     loc_180003095
0x180002d88  call    cs:__imp_GetCurrentThread
0x180002d8e  lea     r9, [rbp+270h+TokenHandle]; TokenHandle
0x180002d95  mov     edx, 2000Eh; DesiredAccess
0x180002d9a  mov     rcx, rax; ThreadHandle
0x180002d9d  lea     r8d, [r14+1]; OpenAsSelf
0x180002da1  call    cs:__imp_OpenThreadToken
0x180002da7  test    eax, eax
0x180002da9  jnz     short loc_180002DBB
0x180002dab  call    cs:__imp_GetLastError
0x180002db1  mov     ebx, eax
0x180002db3  test    eax, eax
0x180002db5  jnz     loc_18000306B
0x180002dbb  lea     rdx, [rsp+370h+phkResult]; phkResult
0x180002dc0  mov     ecx, 10000000h; samDesired
0x180002dc5  call    cs:__imp_RegOpenCurrentUser
0x180002dcb  mov     ebx, eax
0x180002dcd  test    eax, eax
0x180002dcf  jnz     loc_18000306B
0x180002dd5  lea     rcx, [rsp+370h+var_320]
0x180002dda  call    CsGetAppCategories
0x180002ddf  mov     edi, eax
0x180002de1  call    cs:__imp_RevertToSelf
0x180002de7  test    edi, edi
0x180002de9  js      loc_180003071
0x180002def  mov     r8d, dword ptr [rsp+370h+var_320]
0x180002df4  or      r12, 0FFFFFFFFFFFFFFFFh
0x180002df8  mov     ecx, r8d
0x180002dfb  mov     edx, r14d
0x180002dfe  shl     ecx, 5
0x180002e01  test    r8d, r8d
0x180002e04  jz      short loc_180002E3A
0x180002e06  mov     r10, qword ptr [rsp+370h+var_320+8]
0x180002e0b  mov     eax, edx
0x180002e0d  shl     rax, 5
0x180002e11  mov     r9, [rax+r10+8]
0x180002e16  test    r9, r9
0x180002e19  jnz     short loc_180002E20
0x180002e1b  mov     rax, r14
0x180002e1e  jmp     short loc_180002E2D
0x180002e20  mov     rax, r12
0x180002e23  inc     rax
0x180002e26  cmp     [r9+rax*2], r14w
0x180002e2b  jnz     short loc_180002E23
0x180002e2d  lea     ecx, [rcx+rax*2]
0x180002e30  inc     edx
0x180002e32  add     ecx, 2
0x180002e35  cmp     edx, r8d
0x180002e38  jb      short loc_180002E0B
0x180002e3a  mov     edx, ecx; uBytes
0x180002e3c  mov     ecx, 40h ; '@'; uFlags
0x180002e41  call    cs:__imp_LocalAlloc
0x180002e47  mov     [rsi+8], rax
0x180002e4b  mov     rcx, rax
0x180002e4e  test    rax, rax
0x180002e51  jnz     short loc_180002E5D
0x180002e53  mov     edi, 8007000Eh
0x180002e58  jmp     loc_18000304D
0x180002e5d  mov     eax, dword ptr [rsp+370h+var_320]
0x180002e61  mov     ebx, r14d
0x180002e64  mov     r11d, eax
0x180002e67  mov     [rsi], eax
0x180002e69  shl     r11, 5
0x180002e6d  add     r11, rcx
0x180002e70  test    eax, eax
0x180002e72  jz      loc_180002F06
0x180002e78  mov     rax, qword ptr [rsp+370h+var_320+8]
0x180002e7d  mov     rdx, [rsi+8]
0x180002e81  mov     r8d, ebx
0x180002e84  shl     r8, 5
0x180002e88  mov     ecx, [r8+rax]
0x180002e8c  mov     [r8+rdx], ecx
0x180002e90  mov     rax, qword ptr [rsp+370h+var_320+8]
0x180002e95  mov     rcx, [rsi+8]
0x180002e99  movups  xmm0, xmmword ptr [r8+rax+10h]
0x180002e9f  movdqu  xmmword ptr [r8+rcx+10h], xmm0
0x180002ea6  mov     rax, [rsi+8]
0x180002eaa  mov     [r8+rax+8], r11
0x180002eaf  mov     rax, qword ptr [rsp+370h+var_320+8]
0x180002eb4  mov     r8, [r8+rax+8]; unsigned __int16 *
0x180002eb9  test    r8, r8
0x180002ebc  jz      short loc_180002EE0
0x180002ebe  mov     rdx, r12
0x180002ec1  inc     rdx
0x180002ec4  cmp     [r8+rdx*2], r14w
0x180002ec9  jnz     short loc_180002EC1
0x180002ecb  inc     rdx; unsigned __int64
0x180002ece  mov     rcx, r11; unsigned __int16 *
0x180002ed1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002ed6  mov     edi, eax
0x180002ed8  test    eax, eax
0x180002eda  js      loc_180003038
0x180002ee0  test    r11, r11
0x180002ee3  jz      short loc_180002EFA
0x180002ee5  mov     rax, r12
0x180002ee8  inc     rax
0x180002eeb  cmp     [r11+rax*2], r14w
0x180002ef0  jnz     short loc_180002EE8
0x180002ef2  lea     r11, [r11+rax*2]
0x180002ef6  add     r11, 2
0x180002efa  inc     ebx
0x180002efc  cmp     ebx, dword ptr [rsp+370h+var_320]
0x180002f00  jb      loc_180002E78
0x180002f06  test    edi, edi
0x180002f08  js      loc_180003038
0x180002f0e  xor     r9d, r9d; struct _APPKEY *
0x180002f11  mov     [rbp+270h+arg_10], r14d
0x180002f18  xor     r8d, r8d; void *
0x180002f1b  lea     rcx, [rbp+270h+var_2A0]; this
0x180002f1f  lea     edx, [r9+2]; unsigned int
0x180002f23  call    ??0CRsopAppContext@@QEAA@KPEAXPEAU_APPKEY@@@Z; CRsopAppContext::CRsopAppContext(ulong,void *,_APPKEY *)
0x180002f28  mov     r9, [rsp+370h+phkResult]; HKEY
0x180002f2d  lea     rax, [rbp+270h+arg_10]
0x180002f34  mov     r8, [rbp+270h+TokenHandle]; void *
0x180002f3b  lea     rcx, [rbp+270h+var_210]; this
0x180002f3f  mov     [rsp+370h+var_330], rax; unsigned int *
0x180002f44  xor     edx, edx; unsigned int
0x180002f46  lea     rax, [rbp+270h+var_2A0]
0x180002f4a  mov     [rsp+370h+var_338], rax; struct CRsopAppContext *
0x180002f4f  mov     [rsp+370h+var_340], r14d; int
0x180002f54  mov     [rsp+370h+var_348], 1; int
0x180002f5c  mov     qword ptr [rsp+370h+cbData], r14; cbData
0x180002f61  call    ??0CManagedAppProcessor@@QEAA@KPEAXPEAUHKEY__@@P6AKHPEAG@ZHHPEAVCRsopAppContext@@AEAK@Z; CManagedAppProcessor::CManagedAppProcessor(ulong,void *,HKEY__ *,ulong (*)(int,ushort *),int,int,CRsopAppContext *,ulong &)
0x180002f66  mov     ebx, [rbp+270h+arg_10]
0x180002f6c  test    ebx, ebx
0x180002f6e  jnz     loc_180003002
0x180002f74  cmp     [rbp+270h+TokenHandle], r14
0x180002f7b  lea     rax, ??_7CCategoryInfoLog@@6B@; const CCategoryInfoLog::`vftable'
0x180002f82  mov     [rsp+370h+var_300], rax
0x180002f87  lea     rcx, [rbp+270h+var_A8]; this
0x180002f8e  xorps   xmm0, xmm0
0x180002f91  mov     [rsp+370h+var_2F8], r14
0x180002f96  lea     rax, [rbp+270h+var_A8]
0x180002f9d  movdqa  [rbp+270h+var_2F0], xmm0
0x180002fa2  mov     [rbp+270h+var_2B8], rax
0x180002fa6  mov     edx, r14d
0x180002fa9  lea     rax, [rsp+370h+var_320]
0x180002fae  mov     [rbp+270h+var_2C0], r14d
0x180002fb2  xorps   xmm1, xmm1
0x180002fb5  mov     [rbp+270h+var_2B0], rax
0x180002fb9  setz    dl; int
0x180002fbc  movdqa  [rbp+270h+var_2E0], xmm1
0x180002fc1  mov     ebx, r14d
0x180002fc4  movups  [rbp+270h+var_2D0], xmm0
0x180002fc8  call    ?GetExclusiveLoggingAccess@CRsopContext@@QEAAJH@Z; CRsopContext::GetExclusiveLoggingAccess(int)
0x180002fcd  test    eax, eax
0x180002fcf  jnz     short loc_180002FDD
0x180002fd1  lea     rcx, [rsp+370h+var_300]; this
0x180002fd6  call    ?WriteLog@CCategoryInfoLog@@QEAAJXZ; CCategoryInfoLog::WriteLog(void)
0x180002fdb  mov     ebx, eax
0x180002fdd  mov     rcx, [rbp+270h+hSection]; hSection
0x180002fe4  test    rcx, rcx
0x180002fe7  jz      short loc_180002FF6
0x180002fe9  call    cs:__imp_LeaveCriticalPolicySection
0x180002fef  mov     [rbp+270h+hSection], r14
0x180002ff6  lea     rcx, [rsp+370h+var_300]; this
0x180002ffb  call    ??1CCategoryInfoLog@@UEAA@XZ; CCategoryInfoLog::~CCategoryInfoLog(void)
0x180003000  jmp     short loc_18000300D
0x180003002  jle     short loc_18000300D
0x180003004  movzx   ebx, bx
0x180003007  or      ebx, 80070000h
0x18000300d  test    ebx, ebx
0x18000300f  jns     short loc_180003026
0x180003011  cmp     [rbp+270h+var_280], r14d
0x180003015  jz      short loc_180003022
0x180003017  mov     rax, [rbp+270h+var_278]
0x18000301b  test    rax, rax
0x18000301e  jz      short loc_180003022
0x180003020  mov     [rax], ebx
0x180003022  mov     [rbp+270h+var_280], r14d
0x180003026  lea     rcx, [rbp+270h+var_210]; this
0x18000302a  call    ??1CManagedAppProcessor@@QEAA@XZ; CManagedAppProcessor::~CManagedAppProcessor(void)
0x18000302f  lea     rcx, [rbp+270h+var_2A0]; this
0x180003033  call    ??1CRsopAppContext@@QEAA@XZ; CRsopAppContext::~CRsopAppContext(void)
0x180003038  mov     ebx, r14d
0x18000303b  test    edi, edi
0x18000303d  jz      short loc_18000305F
0x18000303f  mov     eax, edi
0x180003041  and     eax, 1FFF0000h
0x180003046  cmp     eax, 70000h
0x18000304b  jnz     short loc_180003052
0x18000304d  movzx   ebx, di
0x180003050  jmp     short loc_18000305F
0x180003052  call    cs:__imp_GetLastError
0x180003058  test    eax, eax
0x18000305a  mov     ebx, eax
0x18000305c  cmovz   ebx, edi
0x18000305f  lea     rcx, [rsp+370h+var_320]
0x180003064  call    ReleaseAppCategoryInfoList
0x180003069  jmp     short loc_180003071
0x18000306b  call    cs:__imp_RevertToSelf
0x180003071  mov     rcx, [rbp+270h+TokenHandle]; hObject
0x180003078  test    rcx, rcx
0x18000307b  jz      short loc_180003083
0x18000307d  call    cs:__imp_CloseHandle
0x180003083  mov     rcx, [rsp+370h+phkResult]; hKey
0x180003088  test    rcx, rcx
0x18000308b  jz      short loc_180003093
0x18000308d  call    cs:__imp_RegCloseKey
0x180003093  mov     eax, ebx
0x180003095  mov     rbx, [rsp+370h+arg_0]
0x18000309d  add     rsp, 350h
0x1800030a4  pop     r14
0x1800030a6  pop     r12
0x1800030a8  pop     rdi
0x1800030a9  pop     rsi
0x1800030aa  pop     rbp
0x1800030ab  retn
```
