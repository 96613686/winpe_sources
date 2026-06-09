# RAiProcessRunOnce

- ea: `0x18003db90`
- end: `0x18003de7d`
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
- `0x18003c20c`
- `0x18003db90`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003dc63`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003dc63`
- `ntdll!NtClose` at `0x18003dcb2`
- `ntdll!NtClose` at `0x18003dcca`
- `ntdll!NtClose` at `0x18003dcdf`
- `ntdll!NtClose` at `0x18003dcb2`
- `ntdll!NtClose` at `0x18003dcca`
- `ntdll!NtClose` at `0x18003dcdf`
- `ntdll!NtQueryInformationToken` at `0x18003dd9f`
- `ntdll!NtQueryInformationToken` at `0x18003dd9f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003dd27`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003dd27`

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
0x18003db90  mov     [rsp-8+arg_18], rbx
0x18003db95  push    rbp
0x18003db96  push    rsi
0x18003db97  push    rdi
0x18003db98  push    r12
0x18003db9a  push    r13
0x18003db9c  push    r14
0x18003db9e  push    r15
0x18003dba0  lea     rbp, [rsp-27h]
0x18003dba5  sub     rsp, 100h
0x18003dbac  mov     rax, cs:__security_cookie
0x18003dbb3  xor     rax, rsp
0x18003dbb6  mov     [rbp+57h+var_38], rax
0x18003dbba  movups  xmm0, xmmword ptr cs:aRunonceExeExpl; "runonce.exe /Explorer"
0x18003dbc1  mov     eax, dword ptr cs:aRunonceExeExpl+28h; "r"
0x18003dbc7  xor     r13d, r13d
0x18003dbca  movups  xmm1, xmmword ptr cs:aRunonceExeExpl+10h; "exe /Explorer"
0x18003dbd1  mov     [rbp+57h+var_40], eax
0x18003dbd4  xor     eax, eax
0x18003dbd6  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18003dbda  mov     r12, r8
0x18003dbdd  mov     r15, rdx
0x18003dbe0  movsd   xmm0, qword ptr cs:aRunonceExeExpl+20h; "lorer"
0x18003dbe8  mov     rsi, rcx
0x18003dbeb  movsd   [rbp+57h+var_48], xmm0
0x18003dbf0  mov     r14d, r13d
0x18003dbf3  mov     [rbp+57h+var_90], r13d
0x18003dbf7  mov     edi, r13d
0x18003dbfa  mov     [rbp+57h+var_8C], 1
0x18003dc01  mov     [rbp+57h+var_A0], r13d
0x18003dc05  mov     [rbp+57h+Handle], r13
0x18003dc09  mov     [rbp+57h+var_78], r13
0x18003dc0d  mov     [rbp+57h+TokenHandle], r13
0x18003dc11  mov     [rbp+57h+TokenInformation], r13
0x18003dc15  mov     [rbp+57h+var_80], r13d
0x18003dc19  movups  [rbp+57h+var_58], xmm1
0x18003dc1d  mov     [rbp+57h+var_3C], ax
0x18003dc21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc28  lea     rax, WPP_GLOBAL_Control
0x18003dc2f  cmp     rcx, rax
0x18003dc32  jz      short loc_18003DC5F
0x18003dc34  test    byte ptr [rcx+1Ch], 1
0x18003dc38  jz      short loc_18003DC5F
0x18003dc3a  mov     rcx, [rcx+10h]
0x18003dc3e  lea     rax, aNull_0; "NULL"
0x18003dc45  test    rdx, rdx
0x18003dc48  lea     r8, WPP_42c22abf76e93d5f86809dc9c30a2332_Traceguids
0x18003dc4f  mov     r9, rdx
0x18003dc52  lea     edx, [r13+0Ah]
0x18003dc56  cmovz   r9, rax
0x18003dc5a  call    WPP_SF_S
0x18003dc5f  lea     rcx, [rbp+57h+var_8C]
0x18003dc63  call    cs:__imp_CheckElevationEnabled
0x18003dc6a  nop     dword ptr [rax+rax+00h]
0x18003dc6f  mov     ebx, eax
0x18003dc71  test    eax, eax
0x18003dc73  jnz     short loc_18003DCA4
0x18003dc75  lea     r9, [rbp+57h+var_90]; unsigned int *
0x18003dc79  mov     [rsp+130h+ReturnLength], r13; unsigned int *
0x18003dc7e  lea     r8, [rbp+57h+TokenHandle]; void **
0x18003dc82  mov     rcx, rsi; void *
0x18003dc85  lea     rdx, [rbp+57h+var_78]; void **
0x18003dc89  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003dc8e  mov     rdi, [rbp+57h+TokenHandle]
0x18003dc92  mov     ebx, eax
0x18003dc94  test    eax, eax
0x18003dc96  jnz     short loc_18003DCA4
0x18003dc98  mov     esi, [rbp+57h+var_90]
0x18003dc9b  test    esi, esi
0x18003dc9d  jnz     short loc_18003DD15
0x18003dc9f  mov     ebx, 5B3h
0x18003dca4  mov     rcx, [rbp+57h+Handle]; Handle
0x18003dca8  test    rcx, rcx
0x18003dcab  jz      short loc_18003DCC2
0x18003dcad  cmp     rcx, rdi
0x18003dcb0  jz      short loc_18003DCC2
0x18003dcb2  call    cs:__imp_NtClose
0x18003dcb9  nop     dword ptr [rax+rax+00h]
0x18003dcbe  mov     [rbp+57h+Handle], r13
0x18003dcc2  test    rdi, rdi
0x18003dcc5  jz      short loc_18003DCD6
0x18003dcc7  mov     rcx, rdi; Handle
0x18003dcca  call    cs:__imp_NtClose
0x18003dcd1  nop     dword ptr [rax+rax+00h]
0x18003dcd6  mov     rcx, [rbp+57h+var_78]; Handle
0x18003dcda  test    rcx, rcx
0x18003dcdd  jz      short loc_18003DCEB
0x18003dcdf  call    cs:__imp_NtClose
0x18003dce6  nop     dword ptr [rax+rax+00h]
0x18003dceb  mov     eax, ebx
0x18003dced  mov     rcx, [rbp+57h+var_38]
0x18003dcf1  xor     rcx, rsp; StackCookie
0x18003dcf4  call    __security_check_cookie
0x18003dcf9  mov     rbx, [rsp+130h+arg_18]
0x18003dd01  add     rsp, 100h
0x18003dd08  pop     r15
0x18003dd0a  pop     r14
0x18003dd0c  pop     r13
0x18003dd0e  pop     r12
0x18003dd10  pop     rdi
0x18003dd11  pop     rsi
0x18003dd12  pop     rbp
0x18003dd13  retn
0x18003dd15  lea     rdx, [rbp+57h+var_A0]; int *
0x18003dd19  mov     rcx, rdi; void *
0x18003dd1c  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003dd21  test    eax, eax
0x18003dd23  jns     short loc_18003DD3A
0x18003dd25  mov     ecx, eax; Status
0x18003dd27  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003dd2e  nop     dword ptr [rax+rax+00h]
0x18003dd33  mov     ebx, eax
0x18003dd35  jmp     loc_18003DCA4
0x18003dd3a  cmp     [rbp+57h+var_A0], r13d
0x18003dd3e  jnz     loc_18003DDCC
0x18003dd44  cmp     [rbp+57h+var_8C], r13d
0x18003dd48  jnz     short loc_18003DD54
0x18003dd4a  mov     ebx, 2E4h
0x18003dd4f  jmp     loc_18003DCA4
0x18003dd54  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003dd5b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003dd60  test    al, al
0x18003dd62  jz      short loc_18003DD85
0x18003dd64  xor     r9d, r9d; int *
0x18003dd67  lea     r8, [rbp+57h+Handle]; DuplicateTokenHandle
0x18003dd6b  mov     rdx, rdi; HANDLE
0x18003dd6e  xor     ecx, ecx; TokenHandle
0x18003dd70  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x18003dd75  mov     ebx, eax
0x18003dd77  test    eax, eax
0x18003dd79  jnz     loc_18003DCA4
0x18003dd7f  mov     rax, [rbp+57h+Handle]
0x18003dd83  jmp     short loc_18003DDC4
0x18003dd85  mov     r9d, 8; TokenInformationLength
0x18003dd8b  lea     rax, [rbp+57h+var_80]
0x18003dd8f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003dd93  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18003dd98  mov     rcx, rdi; TokenHandle
0x18003dd9b  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003dd9f  call    cs:__imp_NtQueryInformationToken
0x18003dda6  nop     dword ptr [rax+rax+00h]
0x18003ddab  test    eax, eax
0x18003ddad  jns     short loc_18003DDBC
0x18003ddaf  cmp     eax, 0C000005Fh
0x18003ddb4  jnz     loc_18003DD25
0x18003ddba  jmp     short loc_18003DD4A
0x18003ddbc  mov     rax, [rbp+57h+TokenInformation]
0x18003ddc0  mov     [rbp+57h+Handle], rax
0x18003ddc4  mov     r14d, 1
0x18003ddca  jmp     short loc_18003DDD0
0x18003ddcc  mov     rax, [rbp+57h+Handle]
0x18003ddd0  test    rax, rax
0x18003ddd3  lea     r8, [rbp+57h+var_A0]; int *
0x18003ddd7  mov     rcx, rdi
0x18003ddda  mov     edx, 1; int
0x18003dddf  cmovnz  rcx, rax; Handle
0x18003dde3  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003dde8  test    eax, eax
0x18003ddea  js      loc_18003DD25
0x18003ddf0  cmp     [rbp+57h+var_A0], r13d
0x18003ddf4  jz      loc_18003DD4A
0x18003ddfa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1200131385@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385> `wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl(void)'::`2'::impl
0x18003de01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(void)
0x18003de06  mov     rcx, [rbp+57h+var_78]; void *
0x18003de0a  mov     r9d, r14d
0x18003de0d  mov     [rsp+130h+var_B0], r12; struct _PROCESS_INFORMATION *
0x18003de15  bts     r9d, 1Dh
0x18003de1a  mov     [rsp+130h+Src], r13; Src
0x18003de1f  test    al, al
0x18003de21  mov     rax, [rbp+57h+Handle]
0x18003de25  mov     rdx, rdi
0x18003de28  mov     [rsp+130h+var_C0], r13; unsigned __int64
0x18003de2d  cmovz   r9d, r14d; unsigned int
0x18003de31  mov     [rsp+130h+var_C8], r13; void *
0x18003de36  test    rax, rax
0x18003de39  mov     [rsp+130h+var_D0], r13d; unsigned int
0x18003de3e  mov     [rsp+130h+lpValue], r13; lpValue
0x18003de43  cmovnz  rdx, rax; void *
0x18003de47  mov     [rsp+130h+var_E0], esi; unsigned int
0x18003de4b  lea     rax, [rbp+57h+var_68]
0x18003de4f  mov     [rsp+130h+var_E8], r13; struct _APPINFO_STARTUPINFO *
0x18003de54  xor     r8d, r8d; void *
0x18003de57  mov     [rsp+130h+var_F0], r15; unsigned __int16 *
0x18003de5c  mov     [rsp+130h+var_F8], r13; unsigned __int16 *
0x18003de61  mov     [rsp+130h+var_100], 400h; unsigned int
0x18003de69  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18003de6e  mov     [rsp+130h+ReturnLength], r13; unsigned __int16 *
0x18003de73  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)
0x18003de78  jmp     loc_18003DD33
```
