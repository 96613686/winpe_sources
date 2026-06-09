# RemoteAppIntegrationClient::ReplaceText(tagMsgRoutingInfo,uint,uint,int,int,MsgString *)

- ea: `0x180032e40`
- end: `0x180033035`
- name: `?ReplaceText@RemoteAppIntegrationClient@@UEAAJUtagMsgRoutingInfo@@IIHHPEAUMsgString@@@Z`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006a14`
- `0x180032e40`
- `0x180034ba8`
- `0x180034d6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032f08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteAppIntegrationClient::ReplaceText(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6,
        __int64 a7)
{
  unsigned int v11; // ecx
  const WCHAR *v12; // rdi
  unsigned __int64 v13; // rbx
  UINT32 v14; // edx
  const WCHAR *v15; // rcx
  unsigned int v16; // ebx
  char IsEnabled; // al
  __int64 v18; // r9
  __int64 *v19; // rbx
  __int64 v20; // rax
  HSTRING v21; // rcx
  unsigned int v22; // edi
  __int64 *v23; // rcx
  __int64 v24; // rax
  HSTRING v25; // rdx
  int v26; // [rsp+20h] [rbp-40h]
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v28 = 0;
  if ( !(unsigned __int8)RemoteAppIntegrationClient::TryAcquireOwner(a1, &v28) )
  {
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    return 0;
  }
  string = 0;
  if ( !a7 )
    goto LABEL_17;
  v11 = *(_DWORD *)a7 & 0xE0000000;
  if ( v11 == 0x40000000 )
  {
    v12 = (const WCHAR *)(a7 + 8);
  }
  else
  {
    if ( v11 != 0x80000000 )
      __debugbreak();
    v12 = *(const WCHAR **)(a7 + 8);
  }
  if ( v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 > 0xFFFFFFFF )
    {
      v16 = -2147024362;
      goto LABEL_19;
    }
    WindowsDeleteString(0);
    v14 = v13;
    v15 = v12;
  }
  else
  {
LABEL_17:
    WindowsDeleteString(0);
    v14 = 0;
    v15 = &sourceString;
  }
  string = 0;
  v16 = WindowsCreateString(v15, v14, &string);
  if ( (v16 & 0x80000000) != 0 )
  {
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclient.cpp",
      (const char *)v16,
      v26);
    WindowsDeleteString(string);
    string = 0;
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    return v16;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl'::`2'::impl);
  v18 = *(unsigned int *)(a1 + 60);
  if ( !IsEnabled )
  {
    v23 = *(__int64 **)(a1 + 40);
    v24 = *v23;
    v25 = string;
    string = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, int, int, HSTRING))(v24 + 32))(
            v23,
            *(unsigned int *)(a1 + 56),
            a4,
            v18,
            a3,
            a5,
            a6,
            v25);
    WindowsDeleteString(string);
    string = 0;
    if ( v28 )
      (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
    return v16;
  }
  v19 = v28;
  v20 = *v28;
  v21 = string;
  string = 0;
  v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, int, int, HSTRING))(v20 + 32))(
          v28,
          *(unsigned int *)(a1 + 56),
          a4,
          v18,
          a3,
          a5,
          a6,
          v21);
  WindowsDeleteString(string);
  string = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  return v22;
}

```

## disassembly

```asm
0x180032e40  push    rbp
0x180032e42  push    rbx
0x180032e43  push    rsi
0x180032e44  push    rdi
0x180032e45  push    r12
0x180032e47  push    r14
0x180032e49  push    r15
0x180032e4b  mov     rbp, rsp
0x180032e4e  sub     rsp, 60h
0x180032e52  mov     r14d, r9d
0x180032e55  mov     r15d, r8d
0x180032e58  mov     rsi, rcx
0x180032e5b  xor     r12d, r12d
0x180032e5e  mov     [rbp+var_8], r12
0x180032e62  lea     rdx, [rbp+var_8]
0x180032e66  call    ?TryAcquireOwner@RemoteAppIntegrationClient@@AEAA_NAEAV?$ComPtr@UIRemoteAppIntegrationOwner@@@WRL@Microsoft@@@Z; RemoteAppIntegrationClient::TryAcquireOwner(Microsoft::WRL::ComPtr<IRemoteAppIntegrationOwner> &)
0x180032e6b  test    al, al
0x180032e6d  jnz     short loc_180032E8C
0x180032e6f  mov     rcx, [rbp+var_8]
0x180032e73  test    rcx, rcx
0x180032e76  jz      short loc_180032E85
0x180032e78  mov     rax, [rcx]
0x180032e7b  mov     rax, [rax+10h]
0x180032e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e84  nop
0x180032e85  xor     eax, eax
0x180032e87  jmp     loc_180033026
0x180032e8c  mov     [rbp+string], r12
0x180032e90  mov     rax, [rbp+arg_30]
0x180032e94  test    rax, rax
0x180032e97  jz      short loc_180032EEF
0x180032e99  mov     ecx, [rax]
0x180032e9b  and     ecx, 0E0000000h
0x180032ea1  cmp     ecx, 40000000h
0x180032ea7  jz      short loc_180032EB8
0x180032ea9  cmp     ecx, 80000000h
0x180032eaf  jz      short loc_180032EB2
0x180032eb1  int     3; Trap to Debugger
0x180032eb2  mov     rdi, [rax+8]
0x180032eb6  jmp     short loc_180032EBC
0x180032eb8  lea     rdi, [rax+8]
0x180032ebc  test    rdi, rdi
0x180032ebf  jz      short loc_180032EEF
0x180032ec1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180032ec5  inc     rbx
0x180032ec8  cmp     [rdi+rbx*2], r12w
0x180032ecd  jnz     short loc_180032EC5
0x180032ecf  mov     eax, 0FFFFFFFFh
0x180032ed4  cmp     rbx, rax
0x180032ed7  ja      short loc_180032EE8
0x180032ed9  xor     ecx, ecx; string
0x180032edb  call    cs:__imp_WindowsDeleteString
0x180032ee1  mov     edx, ebx
0x180032ee3  mov     rcx, rdi
0x180032ee6  jmp     short loc_180032F00
0x180032ee8  mov     ebx, 80070216h
0x180032eed  jmp     short loc_180032F14
0x180032eef  xor     ecx, ecx; string
0x180032ef1  call    cs:__imp_WindowsDeleteString
0x180032ef7  xor     edx, edx; length
0x180032ef9  lea     rcx, sourceString; sourceString
0x180032f00  mov     [rbp+string], r12
0x180032f04  lea     r8, [rbp+string]; string
0x180032f08  call    cs:__imp_WindowsCreateString
0x180032f0e  mov     ebx, eax
0x180032f10  test    eax, eax
0x180032f12  jns     short loc_180032F55
0x180032f14  mov     rcx, [rbp+38h]; this
0x180032f18  mov     r9d, ebx; char *
0x180032f1b  lea     r8, aMincoreTextinp_19; "mincore\\textinput\\dev\\virtualization"...
0x180032f22  mov     edx, 133h; void *
0x180032f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f2c  mov     rcx, [rbp+string]; string
0x180032f30  call    cs:__imp_WindowsDeleteString
0x180032f36  mov     [rbp+string], r12
0x180032f3a  mov     rcx, [rbp+var_8]
0x180032f3e  test    rcx, rcx
0x180032f41  jz      short loc_180032F50
0x180032f43  mov     rax, [rcx]
0x180032f46  mov     rax, [rax+10h]
0x180032f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f4f  nop
0x180032f50  jmp     loc_180033024
0x180032f55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl(void)'::`2'::impl
0x180032f5c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(void)
0x180032f61  mov     r9d, [rsi+3Ch]
0x180032f65  mov     r8d, r14d
0x180032f68  test    al, al
0x180032f6a  jz      short loc_180032FCB
0x180032f6c  mov     rbx, [rbp+var_8]
0x180032f70  mov     rax, [rbx]
0x180032f73  mov     rcx, [rbp+string]
0x180032f77  mov     [rbp+string], r12
0x180032f7b  mov     [rsp+60h+var_28], rcx
0x180032f80  mov     ecx, [rbp+arg_28]
0x180032f83  mov     [rsp+60h+var_30], ecx
0x180032f87  mov     ecx, [rbp+arg_20]
0x180032f8a  mov     [rsp+60h+var_38], ecx
0x180032f8e  mov     [rsp+60h+var_40], r15d
0x180032f93  mov     edx, [rsi+38h]
0x180032f96  mov     rcx, rbx
0x180032f99  mov     rax, [rax+20h]
0x180032f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fa2  mov     edi, eax
0x180032fa4  mov     rcx, [rbp+string]; string
0x180032fa8  call    cs:__imp_WindowsDeleteString
0x180032fae  mov     [rbp+string], r12
0x180032fb2  test    rbx, rbx
0x180032fb5  jz      short loc_180032FC7
0x180032fb7  mov     rdx, [rbx]
0x180032fba  mov     rcx, rbx
0x180032fbd  mov     rax, [rdx+10h]
0x180032fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fc6  nop
0x180032fc7  mov     eax, edi
0x180032fc9  jmp     short loc_180033026
0x180032fcb  mov     rcx, [rsi+28h]
0x180032fcf  mov     rax, [rcx]
0x180032fd2  mov     rdx, [rbp+string]
0x180032fd6  mov     [rbp+string], r12
0x180032fda  mov     [rsp+60h+var_28], rdx
0x180032fdf  mov     edx, [rbp+arg_28]
0x180032fe2  mov     [rsp+60h+var_30], edx
0x180032fe6  mov     edx, [rbp+arg_20]
0x180032fe9  mov     [rsp+60h+var_38], edx
0x180032fed  mov     [rsp+60h+var_40], r15d
0x180032ff2  mov     edx, [rsi+38h]
0x180032ff5  mov     rax, [rax+20h]
0x180032ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ffe  mov     ebx, eax
0x180033000  mov     rcx, [rbp+string]; string
0x180033004  call    cs:__imp_WindowsDeleteString
0x18003300a  mov     [rbp+string], r12
0x18003300e  mov     rcx, [rbp+var_8]
0x180033012  test    rcx, rcx
0x180033015  jz      short loc_180033024
0x180033017  mov     rdx, [rcx]
0x18003301a  mov     rax, [rdx+10h]
0x18003301e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033023  nop
0x180033024  mov     eax, ebx
0x180033026  add     rsp, 60h
0x18003302a  pop     r15
0x18003302c  pop     r14
0x18003302e  pop     r12
0x180033030  pop     rdi
0x180033031  pop     rsi
0x180033032  pop     rbx
0x180033033  pop     rbp
0x180033034  retn
```
