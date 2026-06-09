# RAiProcessRunOnce

- ea: `0x18003e0d0`
- end: `0x18003e3bd`
- name: `RAiProcessRunOnce`
- size: `749`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18000a230`
- `0x180011ff8`
- `0x180014da0`
- `0x180016a40`
- `0x18001e804`
- `0x180022bb0`
- `0x180025880`
- `0x18003c74c`
- `0x18003e0d0`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e1a3`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003e1a3`
- `ntdll!NtClose` at `0x18003e1f2`
- `ntdll!NtClose` at `0x18003e20a`
- `ntdll!NtClose` at `0x18003e21f`
- `ntdll!NtClose` at `0x18003e1f2`
- `ntdll!NtClose` at `0x18003e20a`
- `ntdll!NtClose` at `0x18003e21f`
- `ntdll!NtQueryInformationToken` at `0x18003e2df`
- `ntdll!NtQueryInformationToken` at `0x18003e2df`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e267`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e267`

## pseudocode

```c
__int64 __fastcall RAiProcessRunOnce(void *a1, unsigned __int16 *a2, struct _PROCESS_INFORMATION *a3)
{
  int v6; // r14d
  HANDLE v7; // rdi
  const unsigned __int16 *v8; // r9
  unsigned int ElevationToken; // ebx
  unsigned int ClientInformation; // eax
  unsigned int v11; // esi
  int v13; // eax
  unsigned int v14; // eax
  HANDLE v15; // rax
  void *v16; // rcx
  char IsEnabled; // al
  int v18; // r9d
  HANDLE v19; // rdx
  int v20; // [rsp+90h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-41h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp-39h] BYREF
  int v23; // [rsp+A4h] [rbp-35h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp-31h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp-29h] BYREF
  HANDLE v26; // [rsp+B8h] [rbp-21h] BYREF
  void *TokenInformation; // [rsp+C0h] [rbp-19h] BYREF
  unsigned __int16 v28[8]; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v29; // [rsp+D8h] [rbp-1h]
  __int64 v30; // [rsp+E8h] [rbp+Fh]
  int v31; // [rsp+F0h] [rbp+17h]
  __int16 v32; // [rsp+F4h] [rbp+1Bh]

  v31 = *(_DWORD *)L"r";
  *(_OWORD *)v28 = *(_OWORD *)L"runonce.exe /Explorer";
  v30 = *(_QWORD *)L"lorer";
  v6 = 0;
  v22 = 0;
  v7 = 0;
  v23 = 1;
  v20 = 0;
  Handle = 0;
  v26 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v29 = *(_OWORD *)L"exe /Explorer";
  v32 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = a2;
    if ( !a2 )
      v8 = L"NULL";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_42c22abf76e93d5f86809dc9c30a2332_Traceguids, v8);
  }
  ElevationToken = CheckElevationEnabled(&v23);
  if ( !ElevationToken )
  {
    ClientInformation = AiGetClientInformation(a1, &v26, &TokenHandle, &v22, 0);
    v7 = TokenHandle;
    ElevationToken = ClientInformation;
    if ( !ClientInformation )
    {
      v11 = v22;
      if ( !v22 )
      {
        ElevationToken = 1459;
        goto LABEL_10;
      }
      v13 = AiCheckForElevatedUser(TokenHandle, &v20);
      if ( v13 < 0 )
        goto LABEL_19;
      if ( v20 )
      {
        v15 = Handle;
      }
      else
      {
        if ( !v23 )
          goto LABEL_23;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          ElevationToken = AiGetElevationToken(0, v7, &Handle, 0);
          if ( ElevationToken )
            goto LABEL_10;
          v15 = Handle;
        }
        else
        {
          v13 = NtQueryInformationToken(v7, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength);
          if ( v13 < 0 )
          {
            if ( v13 == -1073741729 )
              goto LABEL_23;
            goto LABEL_19;
          }
          v15 = TokenInformation;
          Handle = TokenInformation;
        }
        v6 = 1;
      }
      v16 = v7;
      if ( v15 )
        v16 = v15;
      v13 = AiCheckForAdminUser(v16, 1, &v20);
      if ( v13 >= 0 )
      {
        if ( v20 )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl'::`2'::impl);
          v18 = v6 | 0x20000000;
          v19 = v7;
          if ( !IsEnabled )
            v18 = v6;
          if ( Handle )
            v19 = Handle;
          v14 = AiLaunchProcess(v26, v19, 0, v18, 0, v28, 0x400u, 0, a2, 0, v11, 0, 0, 0, 0, 0, a3);
          goto LABEL_20;
        }
LABEL_23:
        ElevationToken = 740;
        goto LABEL_10;
      }
LABEL_19:
      v14 = RtlNtStatusToDosErrorNoTeb(v13);
LABEL_20:
      ElevationToken = v14;
    }
  }
LABEL_10:
  if ( Handle && Handle != v7 )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v7 )
    NtClose(v7);
  if ( v26 )
    NtClose(v26);
  return ElevationToken;
}

```

## disassembly

```asm
0x18003e0d0  mov     [rsp-8+arg_18], rbx
0x18003e0d5  push    rbp
0x18003e0d6  push    rsi
0x18003e0d7  push    rdi
0x18003e0d8  push    r12
0x18003e0da  push    r13
0x18003e0dc  push    r14
0x18003e0de  push    r15
0x18003e0e0  lea     rbp, [rsp-27h]
0x18003e0e5  sub     rsp, 100h
0x18003e0ec  mov     rax, cs:__security_cookie
0x18003e0f3  xor     rax, rsp
0x18003e0f6  mov     [rbp+57h+var_38], rax
0x18003e0fa  movups  xmm0, xmmword ptr cs:aRunonceExeExpl; "runonce.exe /Explorer"
0x18003e101  mov     eax, dword ptr cs:aRunonceExeExpl+28h; "r"
0x18003e107  xor     r13d, r13d
0x18003e10a  movups  xmm1, xmmword ptr cs:aRunonceExeExpl+10h; "exe /Explorer"
0x18003e111  mov     [rbp+57h+var_40], eax
0x18003e114  xor     eax, eax
0x18003e116  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18003e11a  mov     r12, r8
0x18003e11d  mov     r15, rdx
0x18003e120  movsd   xmm0, qword ptr cs:aRunonceExeExpl+20h; "lorer"
0x18003e128  mov     rsi, rcx
0x18003e12b  movsd   [rbp+57h+var_48], xmm0
0x18003e130  mov     r14d, r13d
0x18003e133  mov     [rbp+57h+var_90], r13d
0x18003e137  mov     edi, r13d
0x18003e13a  mov     [rbp+57h+var_8C], 1
0x18003e141  mov     [rbp+57h+var_A0], r13d
0x18003e145  mov     [rbp+57h+Handle], r13
0x18003e149  mov     [rbp+57h+var_78], r13
0x18003e14d  mov     [rbp+57h+TokenHandle], r13
0x18003e151  mov     [rbp+57h+TokenInformation], r13
0x18003e155  mov     [rbp+57h+var_80], r13d
0x18003e159  movups  [rbp+57h+var_58], xmm1
0x18003e15d  mov     [rbp+57h+var_3C], ax
0x18003e161  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e168  lea     rax, WPP_GLOBAL_Control
0x18003e16f  cmp     rcx, rax
0x18003e172  jz      short loc_18003E19F
0x18003e174  test    byte ptr [rcx+1Ch], 1
0x18003e178  jz      short loc_18003E19F
0x18003e17a  mov     rcx, [rcx+10h]
0x18003e17e  lea     rax, aNull_0; "NULL"
0x18003e185  test    rdx, rdx
0x18003e188  lea     r8, WPP_42c22abf76e93d5f86809dc9c30a2332_Traceguids
0x18003e18f  mov     r9, rdx
0x18003e192  lea     edx, [r13+0Ah]
0x18003e196  cmovz   r9, rax
0x18003e19a  call    WPP_SF_S
0x18003e19f  lea     rcx, [rbp+57h+var_8C]
0x18003e1a3  call    cs:__imp_CheckElevationEnabled
0x18003e1aa  nop     dword ptr [rax+rax+00h]
0x18003e1af  mov     ebx, eax
0x18003e1b1  test    eax, eax
0x18003e1b3  jnz     short loc_18003E1E4
0x18003e1b5  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18003e1b9  mov     [rsp+130h+ReturnLength], r13; unsigned int *
0x18003e1be  lea     r8, [rbp+57h+TokenHandle]; void **
0x18003e1c2  mov     rcx, rsi; void *
0x18003e1c5  lea     rdx, [rbp+57h+var_78]; void **
0x18003e1c9  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003e1ce  mov     rdi, [rbp+57h+TokenHandle]
0x18003e1d2  mov     ebx, eax
0x18003e1d4  test    eax, eax
0x18003e1d6  jnz     short loc_18003E1E4
0x18003e1d8  mov     esi, [rbp+57h+var_90]
0x18003e1db  test    esi, esi
0x18003e1dd  jnz     short loc_18003E255
0x18003e1df  mov     ebx, 5B3h
0x18003e1e4  mov     rcx, [rbp+57h+Handle]; Handle
0x18003e1e8  test    rcx, rcx
0x18003e1eb  jz      short loc_18003E202
0x18003e1ed  cmp     rcx, rdi
0x18003e1f0  jz      short loc_18003E202
0x18003e1f2  call    cs:__imp_NtClose
0x18003e1f9  nop     dword ptr [rax+rax+00h]
0x18003e1fe  mov     [rbp+57h+Handle], r13
0x18003e202  test    rdi, rdi
0x18003e205  jz      short loc_18003E216
0x18003e207  mov     rcx, rdi; Handle
0x18003e20a  call    cs:__imp_NtClose
0x18003e211  nop     dword ptr [rax+rax+00h]
0x18003e216  mov     rcx, [rbp+57h+var_78]; Handle
0x18003e21a  test    rcx, rcx
0x18003e21d  jz      short loc_18003E22B
0x18003e21f  call    cs:__imp_NtClose
0x18003e226  nop     dword ptr [rax+rax+00h]
0x18003e22b  mov     eax, ebx
0x18003e22d  mov     rcx, [rbp+57h+var_38]
0x18003e231  xor     rcx, rsp; StackCookie
0x18003e234  call    __security_check_cookie
0x18003e239  mov     rbx, [rsp+130h+arg_18]
0x18003e241  add     rsp, 100h
0x18003e248  pop     r15
0x18003e24a  pop     r14
0x18003e24c  pop     r13
0x18003e24e  pop     r12
0x18003e250  pop     rdi
0x18003e251  pop     rsi
0x18003e252  pop     rbp
0x18003e253  retn
0x18003e255  lea     rdx, [rbp+57h+var_A0]; int *
0x18003e259  mov     rcx, rdi; void *
0x18003e25c  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003e261  test    eax, eax
0x18003e263  jns     short loc_18003E27A
0x18003e265  mov     ecx, eax; Status
0x18003e267  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e26e  nop     dword ptr [rax+rax+00h]
0x18003e273  mov     ebx, eax
0x18003e275  jmp     loc_18003E1E4
0x18003e27a  cmp     [rbp+57h+var_A0], r13d
0x18003e27e  jnz     loc_18003E30C
0x18003e284  cmp     [rbp+57h+var_8C], r13d
0x18003e288  jnz     short loc_18003E294
0x18003e28a  mov     ebx, 2E4h
0x18003e28f  jmp     loc_18003E1E4
0x18003e294  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003e29b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003e2a0  test    al, al
0x18003e2a2  jz      short loc_18003E2C5
0x18003e2a4  xor     r9d, r9d; int *
0x18003e2a7  lea     r8, [rbp+57h+Handle]; DuplicateTokenHandle
0x18003e2ab  mov     rdx, rdi; HANDLE
0x18003e2ae  xor     ecx, ecx; TokenHandle
0x18003e2b0  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x18003e2b5  mov     ebx, eax
0x18003e2b7  test    eax, eax
0x18003e2b9  jnz     loc_18003E1E4
0x18003e2bf  mov     rax, [rbp+57h+Handle]
0x18003e2c3  jmp     short loc_18003E304
0x18003e2c5  mov     r9d, 8; TokenInformationLength
0x18003e2cb  lea     rax, [rbp+57h+var_80]
0x18003e2cf  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003e2d3  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18003e2d8  mov     rcx, rdi; TokenHandle
0x18003e2db  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003e2df  call    cs:__imp_NtQueryInformationToken
0x18003e2e6  nop     dword ptr [rax+rax+00h]
0x18003e2eb  test    eax, eax
0x18003e2ed  jns     short loc_18003E2FC
0x18003e2ef  cmp     eax, 0C000005Fh
0x18003e2f4  jnz     loc_18003E265
0x18003e2fa  jmp     short loc_18003E28A
0x18003e2fc  mov     rax, [rbp+57h+TokenInformation]
0x18003e300  mov     [rbp+57h+Handle], rax
0x18003e304  mov     r14d, 1
0x18003e30a  jmp     short loc_18003E310
0x18003e30c  mov     rax, [rbp+57h+Handle]
0x18003e310  test    rax, rax
0x18003e313  lea     r8, [rbp+57h+var_A0]; int *
0x18003e317  mov     rcx, rdi
0x18003e31a  mov     edx, 1; int
0x18003e31f  cmovnz  rcx, rax; Handle
0x18003e323  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003e328  test    eax, eax
0x18003e32a  js      loc_18003E265
0x18003e330  cmp     [rbp+57h+var_A0], r13d
0x18003e334  jz      loc_18003E28A
0x18003e33a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1200131385@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385> `wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl(void)'::`2'::impl
0x18003e341  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(void)
0x18003e346  mov     rcx, [rbp+57h+var_78]; void *
0x18003e34a  mov     r9d, r14d
0x18003e34d  mov     [rsp+130h+var_B0], r12; struct _PROCESS_INFORMATION *
0x18003e355  bts     r9d, 1Dh
0x18003e35a  mov     [rsp+130h+Src], r13; Src
0x18003e35f  test    al, al
0x18003e361  mov     rax, [rbp+57h+Handle]
0x18003e365  mov     rdx, rdi
0x18003e368  mov     [rsp+130h+var_C0], r13; unsigned __int64
0x18003e36d  cmovz   r9d, r14d; unsigned int
0x18003e371  mov     [rsp+130h+var_C8], r13; void *
0x18003e376  test    rax, rax
0x18003e379  mov     [rsp+130h+var_D0], r13d; unsigned int
0x18003e37e  mov     [rsp+130h+lpValue], r13; lpValue
0x18003e383  cmovnz  rdx, rax; void *
0x18003e387  mov     [rsp+130h+var_E0], esi; unsigned int
0x18003e38b  lea     rax, [rbp+57h+var_68]
0x18003e38f  mov     [rsp+130h+var_E8], r13; struct _APPINFO_STARTUPINFO *
0x18003e394  xor     r8d, r8d; void *
0x18003e397  mov     [rsp+130h+var_F0], r15; unsigned __int16 *
0x18003e39c  mov     [rsp+130h+var_F8], r13; unsigned __int16 *
0x18003e3a1  mov     [rsp+130h+var_100], 400h; unsigned int
0x18003e3a9  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18003e3ae  mov     [rsp+130h+ReturnLength], r13; unsigned __int16 *
0x18003e3b3  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)
0x18003e3b8  jmp     loc_18003E273
```
