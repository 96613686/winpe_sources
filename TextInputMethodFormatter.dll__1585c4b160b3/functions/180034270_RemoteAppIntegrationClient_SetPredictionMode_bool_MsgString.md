# RemoteAppIntegrationClient::SetPredictionMode(bool,MsgString *)

- ea: `0x180034270`
- end: `0x180034462`
- name: `?SetPredictionMode@RemoteAppIntegrationClient@@UEAAJ_NPEAUMsgString@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(RemoteAppIntegrationClient *__hidden this, bool, struct MsgString *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006a14`
- `0x180034270`
- `0x180034ba8`
- `0x180034d6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034303`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800343d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034303`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800343d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180034330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180034330`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteAppIntegrationClient::SetPredictionMode(
        __int64 **this,
        unsigned __int8 a2,
        struct MsgString *a3)
{
  int v4; // r14d
  unsigned int v7; // eax
  const WCHAR *v8; // rdi
  unsigned __int64 v9; // rbx
  UINT32 v10; // edx
  const WCHAR *v11; // rcx
  unsigned int v12; // ebx
  char IsEnabled; // al
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rax
  HSTRING v17; // r8
  unsigned int v18; // edi
  __int64 *v19; // rcx
  __int64 v20; // rax
  HSTRING v21; // r9
  int v22; // [rsp+20h] [rbp-48h]
  _QWORD v23[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  HSTRING string; // [rsp+B8h] [rbp+50h] BYREF

  v4 = a2;
  v23[0] = 0;
  if ( !(unsigned __int8)RemoteAppIntegrationClient::TryAcquireOwner(this, v23) )
  {
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return 0;
  }
  string = 0;
  if ( !a3 )
    goto LABEL_17;
  v7 = *(_DWORD *)a3 & 0xE0000000;
  if ( v7 == 0x40000000 )
  {
    v8 = (const WCHAR *)((char *)a3 + 8);
  }
  else
  {
    if ( v7 != 0x80000000 )
      __debugbreak();
    v8 = (const WCHAR *)*((_QWORD *)a3 + 1);
  }
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      v12 = -2147024362;
      goto LABEL_19;
    }
    WindowsDeleteString(0);
    v10 = v9;
    v11 = v8;
  }
  else
  {
LABEL_17:
    WindowsDeleteString(0);
    v10 = 0;
    v11 = &sourceString;
  }
  string = 0;
  v12 = WindowsCreateString(v11, v10, &string);
  if ( (v12 & 0x80000000) != 0 )
  {
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclient.cpp",
      (const char *)v12,
      v22);
    WindowsDeleteString(string);
    string = 0;
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return v12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl'::`2'::impl);
  v14 = *((unsigned int *)this + 15);
  if ( !IsEnabled )
  {
    v19 = this[5];
    v20 = *v19;
    v21 = string;
    string = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, int, int, _QWORD, HSTRING, _DWORD))(v20 + 56))(
            v19,
            v14,
            *((unsigned int *)this + 14),
            0,
            1,
            v4,
            0,
            v21,
            0);
    WindowsDeleteString(string);
    string = 0;
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return v12;
  }
  v15 = v23[0];
  v16 = *(_QWORD *)v23[0];
  v17 = string;
  string = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, int, _QWORD, HSTRING, _DWORD))(v16 + 56))(
          v23[0],
          v14,
          *((unsigned int *)this + 14),
          0,
          1,
          v4,
          0,
          v17,
          0);
  WindowsDeleteString(string);
  string = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return v18;
}

```

## disassembly

```asm
0x180034270  push    rbp
0x180034272  push    rbx
0x180034273  push    rsi
0x180034274  push    rdi
0x180034275  push    r14
0x180034277  push    r15
0x180034279  mov     rbp, rsp
0x18003427c  sub     rsp, 68h
0x180034280  mov     rbx, r8
0x180034283  movzx   r14d, dl
0x180034287  mov     rsi, rcx
0x18003428a  xor     r15d, r15d
0x18003428d  mov     [rbp+var_18], r15
0x180034291  lea     rdx, [rbp+var_18]
0x180034295  call    ?TryAcquireOwner@RemoteAppIntegrationClient@@AEAA_NAEAV?$ComPtr@UIRemoteAppIntegrationOwner@@@WRL@Microsoft@@@Z; RemoteAppIntegrationClient::TryAcquireOwner(Microsoft::WRL::ComPtr<IRemoteAppIntegrationOwner> &)
0x18003429a  test    al, al
0x18003429c  jnz     short loc_1800342BB
0x18003429e  mov     rcx, [rbp+var_18]
0x1800342a2  test    rcx, rcx
0x1800342a5  jz      short loc_1800342B4
0x1800342a7  mov     rax, [rcx]
0x1800342aa  mov     rax, [rax+10h]
0x1800342ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342b3  nop
0x1800342b4  xor     eax, eax
0x1800342b6  jmp     loc_180034455
0x1800342bb  mov     [rbp+string], r15
0x1800342bf  test    rbx, rbx
0x1800342c2  jz      short loc_180034317
0x1800342c4  mov     eax, [rbx]
0x1800342c6  and     eax, 0E0000000h
0x1800342cb  cmp     eax, 40000000h
0x1800342d0  jz      short loc_1800342E0
0x1800342d2  cmp     eax, 80000000h
0x1800342d7  jz      short loc_1800342DA
0x1800342d9  int     3; Trap to Debugger
0x1800342da  mov     rdi, [rbx+8]
0x1800342de  jmp     short loc_1800342E4
0x1800342e0  lea     rdi, [rbx+8]
0x1800342e4  test    rdi, rdi
0x1800342e7  jz      short loc_180034317
0x1800342e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800342ed  inc     rbx
0x1800342f0  cmp     [rdi+rbx*2], r15w
0x1800342f5  jnz     short loc_1800342ED
0x1800342f7  mov     eax, 0FFFFFFFFh
0x1800342fc  cmp     rbx, rax
0x1800342ff  ja      short loc_180034310
0x180034301  xor     ecx, ecx; string
0x180034303  call    cs:__imp_WindowsDeleteString
0x180034309  mov     edx, ebx
0x18003430b  mov     rcx, rdi
0x18003430e  jmp     short loc_180034328
0x180034310  mov     ebx, 80070216h
0x180034315  jmp     short loc_18003433C
0x180034317  xor     ecx, ecx; string
0x180034319  call    cs:__imp_WindowsDeleteString
0x18003431f  xor     edx, edx; length
0x180034321  lea     rcx, sourceString; sourceString
0x180034328  mov     [rbp+string], r15
0x18003432c  lea     r8, [rbp+string]; string
0x180034330  call    cs:__imp_WindowsCreateString
0x180034336  mov     ebx, eax
0x180034338  test    eax, eax
0x18003433a  jns     short loc_18003437D
0x18003433c  mov     rcx, [rbp+30h]; this
0x180034340  mov     r9d, ebx; char *
0x180034343  lea     r8, aMincoreTextinp_19; "mincore\\textinput\\dev\\virtualization"...
0x18003434a  mov     edx, 32Ch; void *
0x18003434f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034354  mov     rcx, [rbp+string]; string
0x180034358  call    cs:__imp_WindowsDeleteString
0x18003435e  mov     [rbp+string], r15
0x180034362  mov     rcx, [rbp+var_18]
0x180034366  test    rcx, rcx
0x180034369  jz      short loc_180034378
0x18003436b  mov     rax, [rcx]
0x18003436e  mov     rax, [rax+10h]
0x180034372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034377  nop
0x180034378  jmp     loc_180034453
0x18003437d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl(void)'::`2'::impl
0x180034384  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(void)
0x180034389  mov     [rsp+68h+var_28], r15d
0x18003438e  mov     edx, [rsi+3Ch]
0x180034391  test    al, al
0x180034393  jz      short loc_1800343F7
0x180034395  mov     rbx, [rbp+var_18]
0x180034399  mov     rax, [rbx]
0x18003439c  mov     r8, [rbp+string]
0x1800343a0  mov     [rbp+string], r15
0x1800343a4  mov     [rsp+68h+var_30], r8
0x1800343a9  mov     [rsp+68h+var_38], r15
0x1800343ae  mov     [rsp+68h+var_40], r14d
0x1800343b3  mov     [rsp+68h+var_48], 1
0x1800343bb  xor     r9d, r9d
0x1800343be  mov     r8d, [rsi+38h]
0x1800343c2  mov     rcx, rbx
0x1800343c5  mov     rax, [rax+38h]
0x1800343c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343ce  mov     edi, eax
0x1800343d0  mov     rcx, [rbp+string]; string
0x1800343d4  call    cs:__imp_WindowsDeleteString
0x1800343da  mov     [rbp+string], r15
0x1800343de  test    rbx, rbx
0x1800343e1  jz      short loc_1800343F3
0x1800343e3  mov     rdx, [rbx]
0x1800343e6  mov     rcx, rbx
0x1800343e9  mov     rax, [rdx+10h]
0x1800343ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343f2  nop
0x1800343f3  mov     eax, edi
0x1800343f5  jmp     short loc_180034455
0x1800343f7  mov     rcx, [rsi+28h]
0x1800343fb  mov     rax, [rcx]
0x1800343fe  mov     r9, [rbp+string]
0x180034402  mov     [rbp+string], r15
0x180034406  mov     [rsp+68h+var_30], r9
0x18003440b  mov     [rsp+68h+var_38], r15
0x180034410  mov     [rsp+68h+var_40], r14d
0x180034415  mov     [rsp+68h+var_48], 1
0x18003441d  xor     r9d, r9d
0x180034420  mov     r8d, [rsi+38h]
0x180034424  mov     rax, [rax+38h]
0x180034428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003442d  mov     ebx, eax
0x18003442f  mov     rcx, [rbp+string]; string
0x180034433  call    cs:__imp_WindowsDeleteString
0x180034439  mov     [rbp+string], r15
0x18003443d  mov     rcx, [rbp+var_18]
0x180034441  test    rcx, rcx
0x180034444  jz      short loc_180034453
0x180034446  mov     rdx, [rcx]
0x180034449  mov     rax, [rdx+10h]
0x18003444d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034452  nop
0x180034453  mov     eax, ebx
0x180034455  add     rsp, 68h
0x180034459  pop     r15
0x18003445b  pop     r14
0x18003445d  pop     rdi
0x18003445e  pop     rsi
0x18003445f  pop     rbx
0x180034460  pop     rbp
0x180034461  retn
```
