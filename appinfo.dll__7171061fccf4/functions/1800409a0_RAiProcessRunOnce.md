# RAiProcessRunOnce

- ea: `0x1800409a0`
- end: `0x180040c59`
- name: `RAiProcessRunOnce`
- size: `697`
- prototype: `__int64 __fastcall(void *, WCHAR *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180009d50`
- `0x180010dd4`
- `0x180021968`
- `0x180026630`
- `0x18002d8fc`
- `0x18003e9e8`
- `0x18003ef28`
- `0x1800409a0`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x180040a61`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x180040a61`
- `ntdll!NtClose` at `0x180040aaa`
- `ntdll!NtClose` at `0x180040abc`
- `ntdll!NtClose` at `0x180040acb`
- `ntdll!NtClose` at `0x180040aaa`
- `ntdll!NtClose` at `0x180040abc`
- `ntdll!NtClose` at `0x180040acb`
- `ntdll!NtQueryInformationToken` at `0x180040b75`
- `ntdll!NtQueryInformationToken` at `0x180040b75`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040b03`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040b03`

## pseudocode

```c
__int64 __fastcall RAiProcessRunOnce(void *a1, WCHAR *a2, void **a3)
{
  HANDLE v6; // rdi
  const wchar_t *v7; // r9
  unsigned int ElevationToken; // ebx
  unsigned int ClientInformation; // eax
  unsigned int v10; // esi
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  int v15; // ebx
  HANDLE v16; // rax
  void *v17; // rcx
  unsigned int v18; // ebx
  HANDLE v19; // rdx
  int v20; // [rsp+B0h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v22; // [rsp+C0h] [rbp-70h] BYREF
  int v23; // [rsp+C4h] [rbp-6Ch] BYREF
  HANDLE TokenHandle; // [rsp+C8h] [rbp-68h] BYREF
  ULONG ReturnLength; // [rsp+D0h] [rbp-60h] BYREF
  HANDLE v26; // [rsp+D8h] [rbp-58h] BYREF
  void *TokenInformation; // [rsp+E0h] [rbp-50h] BYREF
  __int128 v28; // [rsp+E8h] [rbp-48h] BYREF
  _BYTE v29[28]; // [rsp+F8h] [rbp-38h]
  __int16 v30; // [rsp+114h] [rbp-1Ch]

  v28 = *(_OWORD *)L"runonce.exe /Explorer";
  v22 = 0;
  v23 = 1;
  v6 = 0;
  *(_OWORD *)v29 = *(_OWORD *)L"exe /Explorer";
  v20 = 0;
  *(_OWORD *)&v29[12] = *(_OWORD *)L"xplorer";
  Handle = 0;
  v26 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = a2;
    if ( !a2 )
      v7 = L"NULL";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_42c22abf76e93d5f86809dc9c30a2332_Traceguids, v7);
  }
  ElevationToken = CheckElevationEnabled(&v23);
  if ( !ElevationToken )
  {
    ClientInformation = AiGetClientInformation(a1, &v26, &TokenHandle, &v22, 0);
    v6 = TokenHandle;
    ElevationToken = ClientInformation;
    if ( !ClientInformation )
    {
      v10 = v22;
      if ( !v22 )
      {
        ElevationToken = 1459;
        goto LABEL_10;
      }
      v12 = AiCheckForElevatedUser(TokenHandle, &v20);
      if ( v12 < 0 )
        goto LABEL_19;
      v15 = 0;
      if ( v20 )
      {
        v16 = Handle;
      }
      else
      {
        if ( !v23 )
          goto LABEL_23;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                v13) )
        {
          ElevationToken = AiGetElevationToken(0, v6, &Handle, 0);
          if ( ElevationToken )
            goto LABEL_10;
          v16 = Handle;
        }
        else
        {
          v12 = NtQueryInformationToken(v6, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
          if ( v12 < 0 )
          {
            if ( v12 == -1073741729 )
              goto LABEL_23;
            goto LABEL_19;
          }
          v16 = TokenInformation;
          Handle = TokenInformation;
        }
        v15 = 1;
      }
      v17 = v6;
      if ( v16 )
        v17 = v16;
      v12 = AiCheckForAdminUser(v17, 1, &v20);
      if ( v12 >= 0 )
      {
        if ( v20 )
        {
          v18 = v15 | 0x20000000;
          v19 = v6;
          if ( Handle )
            v19 = Handle;
          v14 = AiLaunchProcess(
                  v26,
                  v19,
                  0,
                  v18,
                  0,
                  (const WCHAR *)&v28,
                  0x400u,
                  0,
                  a2,
                  0,
                  0,
                  0,
                  v10,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  a3,
                  0);
          goto LABEL_20;
        }
LABEL_23:
        ElevationToken = 740;
        goto LABEL_10;
      }
LABEL_19:
      v14 = RtlNtStatusToDosErrorNoTeb(v12);
LABEL_20:
      ElevationToken = v14;
    }
  }
LABEL_10:
  if ( Handle && Handle != v6 )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v6 )
    NtClose(v6);
  if ( v26 )
    NtClose(v26);
  return ElevationToken;
}

```

## disassembly

```asm
0x1800409a0  push    rbp
0x1800409a2  push    rbx
0x1800409a3  push    rsi
0x1800409a4  push    rdi
0x1800409a5  push    r12
0x1800409a7  push    r14
0x1800409a9  push    r15
0x1800409ab  lea     rbp, [rsp+10h]
0x1800409b0  sub     rsp, 120h
0x1800409b7  mov     rax, cs:__security_cookie
0x1800409be  xor     rax, rsp
0x1800409c1  mov     [rbp+20h+var_38], rax
0x1800409c5  movups  xmm0, xmmword ptr cs:aRunonceExeExpl; "runonce.exe /Explorer"
0x1800409cc  xor     r12d, r12d
0x1800409cf  mov     r15, r8
0x1800409d2  movups  xmm1, xmmword ptr cs:aRunonceExeExpl+10h; "exe /Explorer"
0x1800409d9  xor     eax, eax
0x1800409db  mov     r14, rdx
0x1800409de  movups  [rbp+20h+var_68], xmm0
0x1800409e2  mov     rsi, rcx
0x1800409e5  mov     [rbp+20h+var_90], r12d
0x1800409e9  movups  xmm0, xmmword ptr cs:aRunonceExeExpl+1Ch; "xplorer"
0x1800409f0  mov     [rbp+20h+var_8C], 1
0x1800409f7  mov     edi, r12d
0x1800409fa  movups  xmmword ptr [rbp+20h+var_58], xmm1
0x1800409fe  mov     [rbp+20h+var_A0], r12d
0x180040a02  movups  xmmword ptr [rbp+20h+var_58+0Ch], xmm0
0x180040a06  mov     [rbp+20h+Handle], r12
0x180040a0a  mov     [rbp+20h+var_78], r12
0x180040a0e  mov     [rbp+20h+TokenHandle], r12
0x180040a12  mov     [rbp+20h+TokenInformation], r12
0x180040a16  mov     [rbp+20h+var_80], r12d
0x180040a1a  mov     [rbp+20h+var_3C], ax
0x180040a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a25  lea     rax, WPP_GLOBAL_Control
0x180040a2c  cmp     rcx, rax
0x180040a2f  jz      short loc_180040A5D
0x180040a31  test    byte ptr [rcx+1Ch], 1
0x180040a35  jz      short loc_180040A5D
0x180040a37  mov     rcx, [rcx+10h]
0x180040a3b  lea     rax, aNull_0; "NULL"
0x180040a42  test    rdx, rdx
0x180040a45  lea     r8, WPP_42c22abf76e93d5f86809dc9c30a2332_Traceguids
0x180040a4c  mov     r9, rdx
0x180040a4f  lea     edx, [r12+0Ah]
0x180040a54  cmovz   r9, rax
0x180040a58  call    WPP_SF_S
0x180040a5d  lea     rcx, [rbp+20h+var_8C]
0x180040a61  call    cs:__imp_CheckElevationEnabled
0x180040a67  mov     ebx, eax
0x180040a69  test    eax, eax
0x180040a6b  jnz     short loc_180040A9C
0x180040a6d  lea     r9, [rbp+20h+var_90]; unsigned int *
0x180040a71  mov     [rsp+150h+ReturnLength], r12; unsigned int *
0x180040a76  lea     r8, [rbp+20h+TokenHandle]; void **
0x180040a7a  mov     rcx, rsi; void *
0x180040a7d  lea     rdx, [rbp+20h+var_78]; void **
0x180040a81  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180040a86  mov     rdi, [rbp+20h+TokenHandle]
0x180040a8a  mov     ebx, eax
0x180040a8c  test    eax, eax
0x180040a8e  jnz     short loc_180040A9C
0x180040a90  mov     esi, [rbp+20h+var_90]
0x180040a93  test    esi, esi
0x180040a95  jnz     short loc_180040AF1
0x180040a97  mov     ebx, 5B3h
0x180040a9c  mov     rcx, [rbp+20h+Handle]; Handle
0x180040aa0  test    rcx, rcx
0x180040aa3  jz      short loc_180040AB4
0x180040aa5  cmp     rcx, rdi
0x180040aa8  jz      short loc_180040AB4
0x180040aaa  call    cs:__imp_NtClose
0x180040ab0  mov     [rbp+20h+Handle], r12
0x180040ab4  test    rdi, rdi
0x180040ab7  jz      short loc_180040AC2
0x180040ab9  mov     rcx, rdi; Handle
0x180040abc  call    cs:__imp_NtClose
0x180040ac2  mov     rcx, [rbp+20h+var_78]; Handle
0x180040ac6  test    rcx, rcx
0x180040ac9  jz      short loc_180040AD1
0x180040acb  call    cs:__imp_NtClose
0x180040ad1  mov     eax, ebx
0x180040ad3  mov     rcx, [rbp+20h+var_38]
0x180040ad7  xor     rcx, rsp; StackCookie
0x180040ada  call    __security_check_cookie
0x180040adf  add     rsp, 120h
0x180040ae6  pop     r15
0x180040ae8  pop     r14
0x180040aea  pop     r12
0x180040aec  pop     rdi
0x180040aed  pop     rsi
0x180040aee  pop     rbx
0x180040aef  pop     rbp
0x180040af0  retn
0x180040af1  lea     rdx, [rbp+20h+var_A0]; int *
0x180040af5  mov     rcx, rdi; void *
0x180040af8  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180040afd  test    eax, eax
0x180040aff  jns     short loc_180040B0D
0x180040b01  mov     ecx, eax; Status
0x180040b03  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040b09  mov     ebx, eax
0x180040b0b  jmp     short loc_180040A9C
0x180040b0d  mov     ebx, r12d
0x180040b10  cmp     [rbp+20h+var_A0], r12d
0x180040b14  jnz     loc_180040B9B
0x180040b1a  cmp     [rbp+20h+var_8C], r12d
0x180040b1e  jnz     short loc_180040B2A
0x180040b20  mov     ebx, 2E4h
0x180040b25  jmp     loc_180040A9C
0x180040b2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180040b31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180040b36  test    al, al
0x180040b38  jz      short loc_180040B5B
0x180040b3a  xor     r9d, r9d; int *
0x180040b3d  lea     r8, [rbp+20h+Handle]; phNewToken
0x180040b41  mov     rdx, rdi; HANDLE
0x180040b44  xor     ecx, ecx; TokenHandle
0x180040b46  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x180040b4b  mov     ebx, eax
0x180040b4d  test    eax, eax
0x180040b4f  jnz     loc_180040A9C
0x180040b55  mov     rax, [rbp+20h+Handle]
0x180040b59  jmp     short loc_180040B94
0x180040b5b  mov     r9d, 8; TokenInformationLength
0x180040b61  lea     rax, [rbp+20h+var_80]
0x180040b65  lea     r8, [rbp+20h+TokenInformation]; TokenInformation
0x180040b69  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180040b6e  mov     rcx, rdi; TokenHandle
0x180040b71  lea     edx, [r9+0Bh]; TokenInformationClass
0x180040b75  call    cs:__imp_NtQueryInformationToken
0x180040b7b  test    eax, eax
0x180040b7d  jns     short loc_180040B8C
0x180040b7f  cmp     eax, 0C000005Fh
0x180040b84  jnz     loc_180040B01
0x180040b8a  jmp     short loc_180040B20
0x180040b8c  mov     rax, [rbp+20h+TokenInformation]
0x180040b90  mov     [rbp+20h+Handle], rax
0x180040b94  mov     ebx, 1
0x180040b99  jmp     short loc_180040B9F
0x180040b9b  mov     rax, [rbp+20h+Handle]
0x180040b9f  test    rax, rax
0x180040ba2  lea     r8, [rbp+20h+var_A0]; int *
0x180040ba6  mov     rcx, rdi
0x180040ba9  mov     edx, 1; int
0x180040bae  cmovnz  rcx, rax; Handle
0x180040bb2  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x180040bb7  test    eax, eax
0x180040bb9  js      loc_180040B01
0x180040bbf  cmp     [rbp+20h+var_A0], r12d
0x180040bc3  jz      loc_180040B20
0x180040bc9  mov     rax, [rbp+20h+Handle]
0x180040bcd  bts     ebx, 1Dh
0x180040bd1  mov     rcx, [rbp+20h+var_78]
0x180040bd5  test    rax, rax
0x180040bd8  mov     [rsp+150h+var_B0], r12
0x180040be0  mov     rdx, rdi
0x180040be3  mov     [rsp+150h+var_B8], r15
0x180040beb  cmovnz  rdx, rax
0x180040bef  mov     [rsp+150h+var_C0], r12
0x180040bf7  lea     rax, [rbp+20h+var_68]
0x180040bfb  mov     [rsp+150h+var_C8], r12
0x180040c03  mov     r9d, ebx
0x180040c06  mov     [rsp+150h+var_D0], r12
0x180040c0e  xor     r8d, r8d
0x180040c11  mov     [rsp+150h+var_D8], r12d
0x180040c16  mov     [rsp+150h+var_E0], r12d
0x180040c1b  mov     [rsp+150h+var_E8], r12
0x180040c20  mov     [rsp+150h+var_F0], esi
0x180040c24  mov     [rsp+150h+var_F8], r12
0x180040c29  mov     [rsp+150h+var_100], r12
0x180040c2e  mov     [rsp+150h+var_108], r12
0x180040c33  mov     [rsp+150h+var_110], r14
0x180040c38  mov     [rsp+150h+var_118], r12
0x180040c3d  mov     [rsp+150h+var_120], 400h
0x180040c45  mov     [rsp+150h+var_128], rax
0x180040c4a  mov     [rsp+150h+ReturnLength], r12
0x180040c4f  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAU_SECURITY_CAPABILITIES@@K2KW4AicAgenticFlags@@0_K1PEAU_PROCESS_INFORMATION@@2@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,_SECURITY_CAPABILITIES *,ulong,ushort *,ulong,AicAgenticFlags,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *,ushort *)
0x180040c54  jmp     loc_180040B09
```
