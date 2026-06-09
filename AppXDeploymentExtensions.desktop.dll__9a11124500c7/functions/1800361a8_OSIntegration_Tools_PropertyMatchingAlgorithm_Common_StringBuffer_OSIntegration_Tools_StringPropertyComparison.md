# OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)

- ea: `0x1800361a8`
- end: `0x180036475`
- name: `?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@VStringPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003596c`
- `0x180035ccc`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x1800361a8`
- `0x180036e58`
- `0x180036e7c`
- `0x1800ddb88`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003636e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003636e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036433`

## string_xrefs

- `0x1800363a5`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800363f4`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(
        __int64 a1,
        __int64 a2,
        __int64 **a3)
{
  HSTRING v5; // r14
  HSTRING v6; // rbx
  int v7; // eax
  HRESULT v8; // edi
  __int64 v9; // rdx
  const WCHAR *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // r13d
  HSTRING *v15; // r15
  HSTRING v16; // rsi
  int v17; // edi
  int v18; // eax
  HSTRING v19; // rcx
  int v20; // eax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  __int64 v23; // [rsp+28h] [rbp-30h] BYREF
  int v24; // [rsp+30h] [rbp-28h]
  HSTRING *v25; // [rsp+38h] [rbp-20h]
  __int64 (__fastcall ***v26)(_QWORD, GUID *, HSTRING *); // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  int v28; // [rsp+A0h] [rbp+48h] BYREF
  int v29; // [rsp+A4h] [rbp+4Ch]
  __int64 v30; // [rsp+A8h] [rbp+50h]
  __int64 **v31; // [rsp+B0h] [rbp+58h]
  HSTRING v32; // [rsp+B8h] [rbp+60h] BYREF

  v31 = a3;
  v30 = a2;
  v29 = HIDWORD(a1);
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v32 = 0;
  v23 = 0;
  v24 = 0;
  if ( !*a3 )
    goto LABEL_41;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 56))(*a3, &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 137;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    RoVariant::~RoVariant((RoVariant *)&v23);
    Windows::Internal::String::~String((Windows::Internal::String *)&v32);
    goto LABEL_42;
  }
  if ( !v28 )
    goto LABEL_41;
  v10 = *(const WCHAR **)(a2 + 32);
  if ( v10 )
  {
    string = 0;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    if ( v11 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
    }
    else
    {
      v8 = WindowsCreateString(v10, v11, &string);
      if ( v8 >= 0 )
      {
        v6 = string;
        v32 = string;
        WindowsDeleteString(0);
      }
    }
    if ( v8 >= 0 )
    {
      v12 = *a3;
      v13 = **a3;
      v25 = (HSTRING *)&v23;
      v26 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v13 + 48))(v12, v6, &v26);
      v15 = v25;
      v16 = (HSTRING)v26;
      if ( v26 )
      {
        string = 0;
        v18 = (**v26)(v26, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &string);
        v17 = v18;
        if ( v18 < 0 )
        {
          if ( v18 == -2147467262 )
          {
            v5 = v16;
            v17 = 3;
          }
          else
          {
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
        else
        {
          v5 = string;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
          v17 = 7;
        }
      }
      else
      {
        v17 = 0;
      }
      v19 = *v15;
      *v15 = v5;
      v20 = *((_DWORD *)v15 + 2);
      *((_DWORD *)v15 + 2) = v17;
      if ( v19 && ((v20 - 3) & 0xFFFFFFFB) == 0 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v14 < 0 )
      {
        if ( v23 && ((v24 - 3) & 0xFFFFFFFB) == 0 )
          (*(void (**)(void))(*(_QWORD *)v23 + 16LL))();
        if ( v6 )
          WindowsDeleteString(v6);
        v8 = v14;
        goto LABEL_42;
      }
      if ( v23 )
      {
        v7 = OSIntegration::Tools::StringPropertyComparisonRule::Evaluate(v30, &v23);
        v8 = v7;
        if ( v7 >= 0 )
        {
          RoVariant::~RoVariant((RoVariant *)&v23);
          Windows::Internal::String::~String((Windows::Internal::String *)&v32);
          v8 = 0;
          goto LABEL_42;
        }
        v9 = 146;
        goto LABEL_33;
      }
LABEL_41:
      RoVariant::~RoVariant((RoVariant *)&v23);
      Windows::Internal::String::~String((Windows::Internal::String *)&v32);
      v8 = -2147023728;
      goto LABEL_42;
    }
  }
  else
  {
    v8 = -2147467261;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8D,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v8,
    (int)string);
  if ( v23 && ((v24 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v23 + 16LL))();
  if ( v6 )
    WindowsDeleteString(v6);
LABEL_42:
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(a3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800361a8  mov     [rsp-40h+arg_10], r8
0x1800361ad  mov     [rsp-40h+arg_8], rdx
0x1800361b2  mov     [rsp-40h+arg_0], rcx
0x1800361b7  push    rbp
0x1800361b8  push    rbx
0x1800361b9  push    rsi
0x1800361ba  push    rdi
0x1800361bb  push    r12
0x1800361bd  push    r13
0x1800361bf  push    r14
0x1800361c1  push    r15
0x1800361c3  mov     rbp, rsp
0x1800361c6  sub     rsp, 58h
0x1800361ca  mov     r12, r8
0x1800361cd  mov     rsi, rdx
0x1800361d0  xor     r14d, r14d
0x1800361d3  mov     dword ptr [rbp+arg_0], r14d
0x1800361d7  mov     ebx, r14d
0x1800361da  mov     [rbp+arg_18], rbx
0x1800361de  mov     [rbp+var_30], r14
0x1800361e2  mov     [rbp+var_28], r14d
0x1800361e6  mov     rcx, [r8]
0x1800361e9  test    rcx, rcx
0x1800361ec  jz      loc_180036441
0x1800361f2  mov     rax, [rcx]
0x1800361f5  lea     rdx, [rbp+arg_0]
0x1800361f9  mov     rax, [rax+38h]
0x1800361fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036202  mov     edi, eax
0x180036204  test    eax, eax
0x180036206  jns     short loc_180036212
0x180036208  mov     edx, 89h
0x18003620d  jmp     loc_1800363A5
0x180036212  cmp     dword ptr [rbp+arg_0], r14d
0x180036216  jz      loc_180036441
0x18003621c  mov     rcx, [rsi+20h]; sourceString
0x180036220  test    rcx, rcx
0x180036223  jz      loc_1800363E8
0x180036229  mov     [rbp+string], r14
0x18003622d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180036231  inc     rdx; length
0x180036234  cmp     [rcx+rdx*2], r14w
0x180036239  jnz     short loc_180036231
0x18003623b  mov     eax, 0FFFFFFFFh
0x180036240  cmp     rdx, rax
0x180036243  ja      short loc_180036273
0x180036245  lea     r8, [rbp+string]; string
0x180036249  call    cs:__imp_WindowsCreateString
0x180036250  nop     dword ptr [rax+rax+00h]
0x180036255  mov     edi, eax
0x180036257  test    eax, eax
0x180036259  js      short loc_180036278
0x18003625b  mov     rbx, [rbp+string]
0x18003625f  mov     [rbp+arg_18], rbx
0x180036263  xor     ecx, ecx; string
0x180036265  call    cs:__imp_WindowsDeleteString
0x18003626c  nop     dword ptr [rax+rax+00h]
0x180036271  jmp     short loc_180036278
0x180036273  mov     edi, 80070216h
0x180036278  test    edi, edi
0x18003627a  js      loc_1800363ED
0x180036280  mov     rcx, [r12]
0x180036284  mov     rax, [rcx]
0x180036287  lea     rdx, [rbp+var_30]
0x18003628b  mov     [rbp+var_20], rdx
0x18003628f  mov     [rbp+var_18], r14
0x180036293  lea     r8, [rbp+var_18]
0x180036297  mov     rdx, rbx
0x18003629a  mov     rax, [rax+30h]
0x18003629e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362a3  mov     r13d, eax
0x1800362a6  mov     r15, [rbp+var_20]
0x1800362aa  mov     rsi, [rbp+var_18]
0x1800362ae  test    rsi, rsi
0x1800362b1  jnz     short loc_1800362B7
0x1800362b3  xor     edi, edi
0x1800362b5  jmp     short loc_180036315
0x1800362b7  mov     [rbp+string], r14
0x1800362bb  mov     rax, [rsi]
0x1800362be  lea     r8, [rbp+string]
0x1800362c2  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800362c9  mov     rcx, rsi
0x1800362cc  mov     rax, [rax]
0x1800362cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362d4  mov     edi, eax
0x1800362d6  test    eax, eax
0x1800362d8  js      short loc_1800362F4
0x1800362da  mov     r14, [rbp+string]
0x1800362de  mov     rax, [rsi]
0x1800362e1  mov     rcx, rsi
0x1800362e4  mov     rax, [rax+10h]
0x1800362e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362ed  mov     edi, 7
0x1800362f2  jmp     short loc_180036315
0x1800362f4  cmp     eax, 80004002h
0x1800362f9  jnz     short loc_180036305
0x1800362fb  mov     r14, rsi
0x1800362fe  mov     edi, 3
0x180036303  jmp     short loc_180036315
0x180036305  mov     rax, [rsi]
0x180036308  mov     rcx, rsi
0x18003630b  mov     rax, [rax+10h]
0x18003630f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036314  nop
0x180036315  mov     rcx, [r15]
0x180036318  mov     [r15], r14
0x18003631b  mov     eax, [r15+8]
0x18003631f  mov     [r15+8], edi
0x180036323  mov     esi, 0FFFFFFFBh
0x180036328  test    rcx, rcx
0x18003632b  jz      short loc_180036341
0x18003632d  add     eax, 0FFFFFFFDh
0x180036330  test    esi, eax
0x180036332  jnz     short loc_180036341
0x180036334  mov     rax, [rcx]
0x180036337  mov     rax, [rax+10h]
0x18003633b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036340  nop
0x180036341  test    r13d, r13d
0x180036344  jns     short loc_180036382
0x180036346  mov     rcx, [rbp+var_30]
0x18003634a  test    rcx, rcx
0x18003634d  jz      short loc_180036366
0x18003634f  mov     eax, [rbp+var_28]
0x180036352  add     eax, 0FFFFFFFDh
0x180036355  test    esi, eax
0x180036357  jnz     short loc_180036366
0x180036359  mov     rax, [rcx]
0x18003635c  mov     rax, [rax+10h]
0x180036360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036365  nop
0x180036366  test    rbx, rbx
0x180036369  jz      short loc_18003637A
0x18003636b  mov     rcx, rbx; string
0x18003636e  call    cs:__imp_WindowsDeleteString
0x180036375  nop     dword ptr [rax+rax+00h]
0x18003637a  mov     edi, r13d
0x18003637d  jmp     loc_180036459
0x180036382  cmp     [rbp+var_30], 0
0x180036387  jz      loc_180036441
0x18003638d  lea     rdx, [rbp+var_30]
0x180036391  mov     rcx, [rbp+arg_8]
0x180036395  call    ?Evaluate@StringPropertyComparisonRule@Tools@OSIntegration@@SAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@AEAVRoVariant@@@Z; OSIntegration::Tools::StringPropertyComparisonRule::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,RoVariant &)
0x18003639a  mov     edi, eax
0x18003639c  test    eax, eax
0x18003639e  jns     short loc_1800363D1
0x1800363a0  mov     edx, 92h; void *
0x1800363a5  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800363ac  mov     r9d, eax; char *
0x1800363af  mov     rcx, [rbp+40h]; this
0x1800363b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363b8  nop
0x1800363b9  lea     rcx, [rbp+var_30]; this
0x1800363bd  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800363c2  nop
0x1800363c3  lea     rcx, [rbp+arg_18]; this
0x1800363c7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800363cc  jmp     loc_180036459
0x1800363d1  lea     rcx, [rbp+var_30]; this
0x1800363d5  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800363da  nop
0x1800363db  lea     rcx, [rbp+arg_18]; this
0x1800363df  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800363e4  xor     edi, edi
0x1800363e6  jmp     short loc_180036459
0x1800363e8  mov     edi, 80004003h
0x1800363ed  mov     rcx, [rbp+40h]; this
0x1800363f1  mov     r9d, edi; char *
0x1800363f4  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800363fb  mov     edx, 8Dh; void *
0x180036400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036405  nop
0x180036406  mov     rcx, [rbp+var_30]
0x18003640a  test    rcx, rcx
0x18003640d  jz      short loc_18003642B
0x18003640f  mov     eax, [rbp+var_28]
0x180036412  add     eax, 0FFFFFFFDh
0x180036415  mov     esi, 0FFFFFFFBh
0x18003641a  test    esi, eax
0x18003641c  jnz     short loc_18003642B
0x18003641e  mov     rax, [rcx]
0x180036421  mov     rax, [rax+10h]
0x180036425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003642a  nop
0x18003642b  test    rbx, rbx
0x18003642e  jz      short loc_180036459
0x180036430  mov     rcx, rbx; string
0x180036433  call    cs:__imp_WindowsDeleteString
0x18003643a  nop     dword ptr [rax+rax+00h]
0x18003643f  jmp     short loc_180036459
0x180036441  lea     rcx, [rbp+var_30]; this
0x180036445  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18003644a  nop
0x18003644b  lea     rcx, [rbp+arg_18]; this
0x18003644f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180036454  mov     edi, 80070490h
0x180036459  mov     rcx, r12
0x18003645c  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180036461  mov     eax, edi
0x180036463  add     rsp, 58h
0x180036467  pop     r15
0x180036469  pop     r14
0x18003646b  pop     r13
0x18003646d  pop     r12
0x18003646f  pop     rdi
0x180036470  pop     rsi
0x180036471  pop     rbx
0x180036472  pop     rbp
0x180036473  retn
```
