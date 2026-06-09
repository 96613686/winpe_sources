# RemoteAppIntegrationClient::ReplaceTextEx(tagMsgRoutingInfo,uint,uint,int,int,MsgString *,int,int)

- ea: `0x180033040`
- end: `0x180033260`
- name: `?ReplaceTextEx@RemoteAppIntegrationClient@@UEAAJUtagMsgRoutingInfo@@IIHHPEAUMsgString@@HH@Z`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006a14`
- `0x180033040`
- `0x180034ba8`
- `0x180034d6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800330db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800330f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800331bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003322f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800330db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800330f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800331bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003322f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180033108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180033108`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteAppIntegrationClient::ReplaceTextEx(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        int a9)
{
  unsigned int v13; // ecx
  const WCHAR *v14; // rdi
  unsigned __int64 v15; // rbx
  UINT32 v16; // edx
  const WCHAR *v17; // rcx
  unsigned int v18; // ebx
  char IsEnabled; // al
  __int64 v20; // r9
  __int64 *v21; // rbx
  __int64 v22; // rax
  HSTRING v23; // rdx
  unsigned int v24; // edi
  __int64 *v25; // rcx
  __int64 v26; // rax
  HSTRING v27; // r8
  int v28; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v30 = 0;
  if ( !(unsigned __int8)RemoteAppIntegrationClient::TryAcquireOwner(a1, &v30) )
  {
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    return 0;
  }
  string = 0;
  if ( !a7 )
    goto LABEL_17;
  v13 = *(_DWORD *)a7 & 0xE0000000;
  if ( v13 == 0x40000000 )
  {
    v14 = (const WCHAR *)(a7 + 8);
  }
  else
  {
    if ( v13 != 0x80000000 )
      __debugbreak();
    v14 = *(const WCHAR **)(a7 + 8);
  }
  if ( v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      v18 = -2147024362;
      goto LABEL_19;
    }
    WindowsDeleteString(0);
    v16 = v15;
    v17 = v14;
  }
  else
  {
LABEL_17:
    WindowsDeleteString(0);
    v16 = 0;
    v17 = &sourceString;
  }
  string = 0;
  v18 = WindowsCreateString(v17, v16, &string);
  if ( (v18 & 0x80000000) != 0 )
  {
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclient.cpp",
      (const char *)v18,
      v28);
    WindowsDeleteString(string);
    string = 0;
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    return v18;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl'::`2'::impl);
  v20 = *(unsigned int *)(a1 + 60);
  if ( !IsEnabled )
  {
    v25 = *(__int64 **)(a1 + 40);
    v26 = *v25;
    v27 = string;
    string = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, int, int, HSTRING, int, int))(v26 + 184))(
            v25,
            *(unsigned int *)(a1 + 56),
            a4,
            v20,
            a3,
            a5,
            a6,
            v27,
            a8,
            a9);
    WindowsDeleteString(string);
    string = 0;
    if ( v30 )
      (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
    return v18;
  }
  v21 = v30;
  v22 = *v30;
  v23 = string;
  string = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, int, int, HSTRING, int, int))(v22 + 184))(
          v30,
          *(unsigned int *)(a1 + 56),
          a4,
          v20,
          a3,
          a5,
          a6,
          v23,
          a8,
          a9);
  WindowsDeleteString(string);
  string = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  return v24;
}

```

## disassembly

```asm
0x180033040  push    rbp
0x180033042  push    rbx
0x180033043  push    rsi
0x180033044  push    rdi
0x180033045  push    r12
0x180033047  push    r14
0x180033049  push    r15
0x18003304b  mov     rbp, rsp
0x18003304e  sub     rsp, 70h
0x180033052  mov     r14d, r9d
0x180033055  mov     r15d, r8d
0x180033058  mov     rsi, rcx
0x18003305b  xor     r12d, r12d
0x18003305e  mov     [rbp+var_8], r12
0x180033062  lea     rdx, [rbp+var_8]
0x180033066  call    ?TryAcquireOwner@RemoteAppIntegrationClient@@AEAA_NAEAV?$ComPtr@UIRemoteAppIntegrationOwner@@@WRL@Microsoft@@@Z; RemoteAppIntegrationClient::TryAcquireOwner(Microsoft::WRL::ComPtr<IRemoteAppIntegrationOwner> &)
0x18003306b  test    al, al
0x18003306d  jnz     short loc_18003308C
0x18003306f  mov     rcx, [rbp+var_8]
0x180033073  test    rcx, rcx
0x180033076  jz      short loc_180033085
0x180033078  mov     rax, [rcx]
0x18003307b  mov     rax, [rax+10h]
0x18003307f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033084  nop
0x180033085  xor     eax, eax
0x180033087  jmp     loc_180033251
0x18003308c  mov     [rbp+string], r12
0x180033090  mov     rax, [rbp+arg_30]
0x180033094  test    rax, rax
0x180033097  jz      short loc_1800330EF
0x180033099  mov     ecx, [rax]
0x18003309b  and     ecx, 0E0000000h
0x1800330a1  cmp     ecx, 40000000h
0x1800330a7  jz      short loc_1800330B8
0x1800330a9  cmp     ecx, 80000000h
0x1800330af  jz      short loc_1800330B2
0x1800330b1  int     3; Trap to Debugger
0x1800330b2  mov     rdi, [rax+8]
0x1800330b6  jmp     short loc_1800330BC
0x1800330b8  lea     rdi, [rax+8]
0x1800330bc  test    rdi, rdi
0x1800330bf  jz      short loc_1800330EF
0x1800330c1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800330c5  inc     rbx
0x1800330c8  cmp     [rdi+rbx*2], r12w
0x1800330cd  jnz     short loc_1800330C5
0x1800330cf  mov     eax, 0FFFFFFFFh
0x1800330d4  cmp     rbx, rax
0x1800330d7  ja      short loc_1800330E8
0x1800330d9  xor     ecx, ecx; string
0x1800330db  call    cs:__imp_WindowsDeleteString
0x1800330e1  mov     edx, ebx
0x1800330e3  mov     rcx, rdi
0x1800330e6  jmp     short loc_180033100
0x1800330e8  mov     ebx, 80070216h
0x1800330ed  jmp     short loc_180033114
0x1800330ef  xor     ecx, ecx; string
0x1800330f1  call    cs:__imp_WindowsDeleteString
0x1800330f7  xor     edx, edx; length
0x1800330f9  lea     rcx, sourceString; sourceString
0x180033100  mov     [rbp+string], r12
0x180033104  lea     r8, [rbp+string]; string
0x180033108  call    cs:__imp_WindowsCreateString
0x18003310e  mov     ebx, eax
0x180033110  test    eax, eax
0x180033112  jns     short loc_180033155
0x180033114  mov     rcx, [rbp+38h]; this
0x180033118  mov     r9d, ebx; char *
0x18003311b  lea     r8, aMincoreTextinp_19; "mincore\\textinput\\dev\\virtualization"...
0x180033122  mov     edx, 14Eh; void *
0x180033127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003312c  mov     rcx, [rbp+string]; string
0x180033130  call    cs:__imp_WindowsDeleteString
0x180033136  mov     [rbp+string], r12
0x18003313a  mov     rcx, [rbp+var_8]
0x18003313e  test    rcx, rcx
0x180033141  jz      short loc_180033150
0x180033143  mov     rax, [rcx]
0x180033146  mov     rax, [rax+10h]
0x18003314a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003314f  nop
0x180033150  jmp     loc_18003324F
0x180033155  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl(void)'::`2'::impl
0x18003315c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(void)
0x180033161  mov     r9d, [rsi+3Ch]
0x180033165  test    al, al
0x180033167  jz      short loc_1800331DF
0x180033169  mov     rbx, [rbp+var_8]
0x18003316d  mov     rax, [rbx]
0x180033170  mov     rdx, [rbp+string]
0x180033174  mov     [rbp+string], r12
0x180033178  mov     ecx, [rbp+arg_40]
0x18003317e  mov     [rsp+70h+var_28], ecx
0x180033182  mov     ecx, [rbp+arg_38]
0x180033185  mov     [rsp+70h+var_30], ecx
0x180033189  mov     [rsp+70h+var_38], rdx
0x18003318e  mov     ecx, [rbp+arg_28]
0x180033191  mov     [rsp+70h+var_40], ecx
0x180033195  mov     ecx, [rbp+arg_20]
0x180033198  mov     [rsp+70h+var_48], ecx
0x18003319c  mov     [rsp+70h+var_50], r15d
0x1800331a1  mov     r8d, r14d
0x1800331a4  mov     edx, [rsi+38h]
0x1800331a7  mov     rcx, rbx
0x1800331aa  mov     rax, [rax+0B8h]
0x1800331b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331b6  mov     edi, eax
0x1800331b8  mov     rcx, [rbp+string]; string
0x1800331bc  call    cs:__imp_WindowsDeleteString
0x1800331c2  mov     [rbp+string], r12
0x1800331c6  test    rbx, rbx
0x1800331c9  jz      short loc_1800331DB
0x1800331cb  mov     rdx, [rbx]
0x1800331ce  mov     rcx, rbx
0x1800331d1  mov     rax, [rdx+10h]
0x1800331d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331da  nop
0x1800331db  mov     eax, edi
0x1800331dd  jmp     short loc_180033251
0x1800331df  mov     rcx, [rsi+28h]
0x1800331e3  mov     rax, [rcx]
0x1800331e6  mov     r8, [rbp+string]
0x1800331ea  mov     [rbp+string], r12
0x1800331ee  mov     edx, [rbp+arg_40]
0x1800331f4  mov     [rsp+70h+var_28], edx
0x1800331f8  mov     edx, [rbp+arg_38]
0x1800331fb  mov     [rsp+70h+var_30], edx
0x1800331ff  mov     [rsp+70h+var_38], r8
0x180033204  mov     edx, [rbp+arg_28]
0x180033207  mov     [rsp+70h+var_40], edx
0x18003320b  mov     edx, [rbp+arg_20]
0x18003320e  mov     [rsp+70h+var_48], edx
0x180033212  mov     [rsp+70h+var_50], r15d
0x180033217  mov     r8d, r14d
0x18003321a  mov     edx, [rsi+38h]
0x18003321d  mov     rax, [rax+0B8h]
0x180033224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033229  mov     ebx, eax
0x18003322b  mov     rcx, [rbp+string]; string
0x18003322f  call    cs:__imp_WindowsDeleteString
0x180033235  mov     [rbp+string], r12
0x180033239  mov     rcx, [rbp+var_8]
0x18003323d  test    rcx, rcx
0x180033240  jz      short loc_18003324F
0x180033242  mov     rdx, [rcx]
0x180033245  mov     rax, [rdx+10h]
0x180033249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003324e  nop
0x18003324f  mov     eax, ebx
0x180033251  add     rsp, 70h
0x180033255  pop     r15
0x180033257  pop     r14
0x180033259  pop     r12
0x18003325b  pop     rdi
0x18003325c  pop     rsi
0x18003325d  pop     rbx
0x18003325e  pop     rbp
0x18003325f  retn
```
