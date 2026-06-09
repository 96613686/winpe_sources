# OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)

- ea: `0x18003647c`
- end: `0x1800367a5`
- name: `?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `809`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003596c`
- `0x180035ccc`
- `0x1800367ac`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x18003647c`
- `0x180036e58`
- `0x180036e7c`
- `0x18005667c`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800365cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800365cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800365eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800366f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800365eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800366f8`

## string_xrefs

- `0x18003652a`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800365aa`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
        __int64 a1,
        __int64 a2,
        __int64 **a3)
{
  HSTRING v5; // r12
  HSTRING v6; // rbx
  int v7; // eax
  HRESULT v8; // edi
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 *v14; // rcx
  __int64 *v15; // rcx
  __int64 v16; // rax
  HSTRING *v17; // r13
  HSTRING v18; // r14
  int v19; // eax
  int v20; // esi
  HSTRING v21; // rcx
  int v22; // eax
  int v23; // eax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  __int64 v25; // [rsp+28h] [rbp-30h] BYREF
  int v26; // [rsp+30h] [rbp-28h]
  HSTRING *v27; // [rsp+38h] [rbp-20h]
  __int64 (__fastcall ***v28)(_QWORD, GUID *, HSTRING *); // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  int v30; // [rsp+A0h] [rbp+48h] BYREF
  int v31; // [rsp+A4h] [rbp+4Ch]
  __int64 v32; // [rsp+A8h] [rbp+50h]
  __int64 **v33; // [rsp+B0h] [rbp+58h]
  HSTRING v34; // [rsp+B8h] [rbp+60h] BYREF

  v33 = a3;
  v32 = a2;
  v31 = HIDWORD(a1);
  v5 = 0;
  v30 = 0;
  v6 = 0;
  v34 = 0;
  v25 = 0;
  v26 = 0;
  if ( !*a3 )
  {
    v8 = -2147023728;
    goto LABEL_12;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 56))(*a3, &v30);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    goto LABEL_12;
  }
  if ( !v30 )
  {
    RoVariant::~RoVariant((RoVariant *)&v25);
    Windows::Internal::String::~String((Windows::Internal::String *)&v34);
    v8 = -2147023728;
    goto LABEL_12;
  }
  v9 = *(const WCHAR **)(a2 + 16);
  if ( !v9 )
  {
    v8 = -2147467261;
LABEL_10:
    v11 = (unsigned int)v8;
    v12 = 141;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)v11,
      (int)string);
    RoVariant::~RoVariant((RoVariant *)&v25);
    Windows::Internal::String::~String((Windows::Internal::String *)&v34);
LABEL_12:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(a3);
    return (unsigned int)v8;
  }
  string = 0;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  if ( v10 <= 0xFFFFFFFF )
  {
    v8 = WindowsCreateString(v9, v10, &string);
    if ( v8 >= 0 )
    {
      v6 = string;
      v34 = string;
      WindowsDeleteString(0);
    }
  }
  else
  {
    v8 = -2147024362;
  }
  if ( v8 < 0 )
    goto LABEL_10;
  v15 = *a3;
  v16 = **a3;
  v27 = (HSTRING *)&v25;
  v28 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v16 + 48))(v15, v6, &v28);
  v17 = v27;
  v18 = (HSTRING)v28;
  if ( v28 )
  {
    string = 0;
    v19 = (**v28)(v28, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &string);
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( v19 == -2147467262 )
      {
        v5 = v18;
        v20 = 3;
      }
      else
      {
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    else
    {
      v5 = string;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
      v20 = 7;
    }
  }
  else
  {
    v20 = 0;
  }
  v21 = *v17;
  *v17 = v5;
  v22 = *((_DWORD *)v17 + 2);
  *((_DWORD *)v17 + 2) = v20;
  if ( v21 && ((v22 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v8 < 0 )
  {
    if ( v25 && ((v26 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (**)(void))(*(_QWORD *)v25 + 16LL))();
    if ( v6 )
      WindowsDeleteString(v6);
    goto LABEL_12;
  }
  if ( v25 )
  {
    v23 = OSIntegration::Tools::DwordPropertyComparisonRule::Evaluate(v32, &v25);
    v8 = v23;
    if ( v23 >= 0 )
    {
      RoVariant::~RoVariant((RoVariant *)&v25);
      Windows::Internal::String::~String((Windows::Internal::String *)&v34);
      v8 = 0;
      goto LABEL_12;
    }
    v11 = (unsigned int)v23;
    v12 = 146;
    goto LABEL_11;
  }
  if ( v6 )
    WindowsDeleteString(v6);
  v14 = *a3;
  if ( *a3 )
  {
    *a3 = 0;
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x18003647c  mov     [rsp-40h+arg_10], r8
0x180036481  mov     [rsp-40h+arg_8], rdx
0x180036486  mov     [rsp-40h+arg_0], rcx
0x18003648b  push    rbp
0x18003648c  push    rbx
0x18003648d  push    rsi
0x18003648e  push    rdi
0x18003648f  push    r12
0x180036491  push    r13
0x180036493  push    r14
0x180036495  push    r15
0x180036497  mov     rbp, rsp
0x18003649a  sub     rsp, 58h
0x18003649e  mov     r15, r8
0x1800364a1  mov     rsi, rdx
0x1800364a4  xor     r12d, r12d
0x1800364a7  mov     dword ptr [rbp+arg_0], r12d
0x1800364ab  mov     ebx, r12d
0x1800364ae  mov     [rbp+arg_18], rbx
0x1800364b2  mov     [rbp+var_30], r12
0x1800364b6  mov     [rbp+var_28], r12d
0x1800364ba  mov     rcx, [r8]
0x1800364bd  test    rcx, rcx
0x1800364c0  jz      loc_1800366C0
0x1800364c6  mov     rax, [rcx]
0x1800364c9  lea     rdx, [rbp+arg_0]
0x1800364cd  mov     rax, [rax+38h]
0x1800364d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d6  mov     edi, eax
0x1800364d8  test    eax, eax
0x1800364da  js      loc_1800365A3
0x1800364e0  cmp     dword ptr [rbp+arg_0], r12d
0x1800364e4  jz      loc_180036745
0x1800364ea  mov     rcx, [rsi+10h]; sourceString
0x1800364ee  test    rcx, rcx
0x1800364f1  jz      short loc_18003651D
0x1800364f3  mov     [rbp+string], r12
0x1800364f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800364fb  inc     rdx; length
0x1800364fe  cmp     [rcx+rdx*2], r12w
0x180036503  jnz     short loc_1800364FB
0x180036505  mov     eax, 0FFFFFFFFh
0x18003650a  cmp     rdx, rax
0x18003650d  jbe     loc_1800365CB
0x180036513  mov     edi, 80070216h
0x180036518  jmp     loc_1800365F7
0x18003651d  mov     edi, 80004003h
0x180036522  mov     r9d, edi; char *
0x180036525  mov     edx, 8Dh; void *
0x18003652a  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180036531  mov     rcx, [rbp+40h]; this
0x180036535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003653a  nop
0x18003653b  lea     rcx, [rbp+var_30]; this
0x18003653f  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180036544  nop
0x180036545  lea     rcx, [rbp+arg_18]; this
0x180036549  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003654e  nop
0x18003654f  mov     rcx, r15
0x180036552  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180036557  mov     eax, edi
0x180036559  jmp     short loc_180036591
0x18003655b  test    rbx, rbx
0x18003655e  jz      short loc_180036570
0x180036560  mov     rcx, rbx; string
0x180036563  call    cs:__imp_WindowsDeleteString
0x18003656a  nop     dword ptr [rax+rax+00h]
0x18003656f  nop
0x180036570  mov     rcx, [r15]
0x180036573  test    rcx, rcx
0x180036576  jz      short loc_18003658C
0x180036578  mov     qword ptr [r15], 0
0x18003657f  mov     rax, [rcx]
0x180036582  mov     rax, [rax+10h]
0x180036586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003658b  nop
0x18003658c  mov     eax, 80070490h
0x180036591  add     rsp, 58h
0x180036595  pop     r15
0x180036597  pop     r14
0x180036599  pop     r13
0x18003659b  pop     r12
0x18003659d  pop     rdi
0x18003659e  pop     rsi
0x18003659f  pop     rbx
0x1800365a0  pop     rbp
0x1800365a1  retn
0x1800365a3  mov     rcx, [rbp+40h]; this
0x1800365a7  mov     r9d, eax; char *
0x1800365aa  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800365b1  mov     edx, 89h; void *
0x1800365b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800365bb  nop
0x1800365bc  mov     rcx, [rbp+var_30]
0x1800365c0  test    rcx, rcx
0x1800365c3  jnz     loc_180036709
0x1800365c9  jmp     short loc_18003654F
0x1800365cb  lea     r8, [rbp+string]; string
0x1800365cf  call    cs:__imp_WindowsCreateString
0x1800365d6  nop     dword ptr [rax+rax+00h]
0x1800365db  mov     edi, eax
0x1800365dd  test    eax, eax
0x1800365df  js      short loc_1800365F7
0x1800365e1  mov     rbx, [rbp+string]
0x1800365e5  mov     [rbp+arg_18], rbx
0x1800365e9  xor     ecx, ecx; string
0x1800365eb  call    cs:__imp_WindowsDeleteString
0x1800365f2  nop     dword ptr [rax+rax+00h]
0x1800365f7  test    edi, edi
0x1800365f9  js      loc_180036522
0x1800365ff  mov     rcx, [r15]
0x180036602  mov     rax, [rcx]
0x180036605  lea     rdx, [rbp+var_30]
0x180036609  mov     [rbp+var_20], rdx
0x18003660d  mov     [rbp+var_18], r12
0x180036611  lea     r8, [rbp+var_18]
0x180036615  mov     rdx, rbx
0x180036618  mov     rax, [rax+30h]
0x18003661c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036621  mov     edi, eax
0x180036623  mov     r13, [rbp+var_20]
0x180036627  mov     r14, [rbp+var_18]
0x18003662b  test    r14, r14
0x18003662e  jz      loc_1800366CA
0x180036634  mov     [rbp+string], r12
0x180036638  mov     rax, [r14]
0x18003663b  lea     r8, [rbp+string]
0x18003663f  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180036646  mov     rcx, r14
0x180036649  mov     rax, [rax]
0x18003664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036651  mov     esi, eax
0x180036653  test    eax, eax
0x180036655  js      loc_180036762
0x18003665b  mov     r12, [rbp+string]
0x18003665f  mov     rax, [r14]
0x180036662  mov     rcx, r14
0x180036665  mov     rax, [rax+10h]
0x180036669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003666e  mov     esi, 7
0x180036673  mov     rcx, [r13+0]
0x180036677  mov     [r13+0], r12
0x18003667b  mov     eax, [r13+8]
0x18003667f  mov     [r13+8], esi
0x180036683  mov     esi, 0FFFFFFFBh
0x180036688  test    rcx, rcx
0x18003668b  jnz     short loc_1800366CE
0x18003668d  test    edi, edi
0x18003668f  js      short loc_1800366E3
0x180036691  cmp     [rbp+var_30], 0
0x180036696  jz      loc_18003655B
0x18003669c  lea     rdx, [rbp+var_30]
0x1800366a0  mov     rcx, [rbp+arg_8]
0x1800366a4  call    ?Evaluate@DwordPropertyComparisonRule@Tools@OSIntegration@@SAJPEBV?$Property@K@Internal@23@AEAVRoVariant@@@Z; OSIntegration::Tools::DwordPropertyComparisonRule::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,RoVariant &)
0x1800366a9  mov     edi, eax
0x1800366ab  test    eax, eax
0x1800366ad  jns     loc_18003678A
0x1800366b3  mov     r9d, eax
0x1800366b6  mov     edx, 92h
0x1800366bb  jmp     loc_18003652A
0x1800366c0  mov     edi, 80070490h
0x1800366c5  jmp     loc_1800365C9
0x1800366ca  xor     esi, esi
0x1800366cc  jmp     short loc_180036673
0x1800366ce  add     eax, 0FFFFFFFDh
0x1800366d1  test    esi, eax
0x1800366d3  jnz     short loc_18003668D
0x1800366d5  mov     rax, [rcx]
0x1800366d8  mov     rax, [rax+10h]
0x1800366dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366e1  jmp     short loc_18003668D
0x1800366e3  mov     rcx, [rbp+var_30]
0x1800366e7  test    rcx, rcx
0x1800366ea  jnz     short loc_18003672D
0x1800366ec  test    rbx, rbx
0x1800366ef  jz      loc_18003654F
0x1800366f5  mov     rcx, rbx; string
0x1800366f8  call    cs:__imp_WindowsDeleteString
0x1800366ff  nop     dword ptr [rax+rax+00h]
0x180036704  jmp     loc_18003654F
0x180036709  mov     eax, [rbp+var_28]
0x18003670c  add     eax, 0FFFFFFFDh
0x18003670f  mov     esi, 0FFFFFFFBh
0x180036714  test    esi, eax
0x180036716  jnz     loc_1800365C9
0x18003671c  mov     rax, [rcx]
0x18003671f  mov     rax, [rax+10h]
0x180036723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036728  jmp     loc_1800365C9
0x18003672d  mov     eax, [rbp+var_28]
0x180036730  add     eax, 0FFFFFFFDh
0x180036733  test    esi, eax
0x180036735  jnz     short loc_1800366EC
0x180036737  mov     rax, [rcx]
0x18003673a  mov     rax, [rax+10h]
0x18003673e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036743  jmp     short loc_1800366EC
0x180036745  lea     rcx, [rbp+var_30]; this
0x180036749  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18003674e  nop
0x18003674f  lea     rcx, [rbp+arg_18]; this
0x180036753  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180036758  mov     edi, 80070490h
0x18003675d  jmp     loc_18003654F
0x180036762  cmp     eax, 80004002h
0x180036767  jnz     short loc_180036776
0x180036769  mov     r12, r14
0x18003676c  mov     esi, 3
0x180036771  jmp     loc_180036673
0x180036776  mov     rax, [r14]
0x180036779  mov     rcx, r14
0x18003677c  mov     rax, [rax+10h]
0x180036780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036785  jmp     loc_180036673
0x18003678a  lea     rcx, [rbp+var_30]; this
0x18003678e  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180036793  nop
0x180036794  lea     rcx, [rbp+arg_18]; this
0x180036798  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003679d  xor     edi, edi
0x18003679f  jmp     loc_18003654F
```
