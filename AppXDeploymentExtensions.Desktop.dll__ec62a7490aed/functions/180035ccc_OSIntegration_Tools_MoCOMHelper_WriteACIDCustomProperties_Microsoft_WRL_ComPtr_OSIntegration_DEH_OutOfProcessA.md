# OSIntegration::Tools::MoCOMHelper::WriteACIDCustomProperties(Microsoft::WRL::ComPtr<OSIntegration::DEH::OutOfProcessActivatableClassRegistration> &)

- ea: `0x180035ccc`
- end: `0x1800361a1`
- name: `?WriteACIDCustomProperties@MoCOMHelper@Tools@OSIntegration@@AEBAJAEAV?$ComPtr@UOutOfProcessActivatableClassRegistration@DEH@OSIntegration@@@WRL@Microsoft@@@Z`
- size: `1237`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007a670`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x180035ccc`
- `0x1800361a8`
- `0x18003647c`
- `0x180036e58`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035f27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035e8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800360a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035e8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800360a0`

## string_xrefs

- `0x180035d7a`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180035ef1`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180035f98`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003614c`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::WriteACIDCustomProperties(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rsi
  __int64 v6; // rdi
  HSTRING v7; // rcx
  int v8; // eax
  HRESULT v9; // ebx
  const WCHAR *v10; // rcx
  HSTRING v11; // rcx
  unsigned int *v12; // rsi
  HSTRING v13; // rcx
  int v14; // eax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  HSTRING v17; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  HSTRING v22; // rcx
  const WCHAR *v23; // rcx
  unsigned __int64 v24; // rdx
  HSTRING v25; // rcx
  HSTRING v26; // rcx
  char *v27; // rax
  HSTRING v28; // rdx
  HSTRING v29; // rcx
  __int64 v30; // rcx
  HSTRING v31; // rcx
  char *v32; // rax
  HSTRING v33; // rdx
  HSTRING v34; // rcx
  __int64 v35; // rcx
  HSTRING v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-20h] BYREF
  char v38; // [rsp+28h] [rbp-18h] BYREF
  char v39; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HSTRING v41; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v42; // [rsp+88h] [rbp+48h] BYREF
  HSTRING string; // [rsp+90h] [rbp+50h] BYREF
  HSTRING v44; // [rsp+98h] [rbp+58h] BYREF

  v42 = 0;
  string = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 96LL))(*a2, &v41);
  for ( i = 0; i < a1[55]; ++i )
  {
    v12 = *(unsigned int **)(a1[53] + 8 * i);
    v13 = v41;
    v44 = v41;
    if ( v41 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v41 + 8LL))(v41);
    v14 = OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
            v13,
            v12,
            &v44);
    v9 = v14;
    if ( v14 == -2147023728 || v14 == -2147483637 )
    {
      v15 = (const WCHAR *)*((_QWORD *)v12 + 2);
      if ( !v15 )
      {
        v9 = -2147467261;
LABEL_39:
        v20 = 2645;
LABEL_40:
        v21 = (unsigned int)v9;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)v21,
          v37);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v41);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v42);
        return (unsigned int)v9;
      }
      v44 = 0;
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      if ( v16 <= 0xFFFFFFFF )
      {
        v9 = WindowsCreateString(v15, v16, &v44);
        if ( v9 >= 0 )
        {
          v26 = v42;
          v42 = v44;
          WindowsDeleteString(v26);
        }
      }
      else
      {
        v9 = -2147024362;
      }
      if ( v9 < 0 )
        goto LABEL_39;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, _QWORD))(*(_QWORD *)*a2 + 104LL))(*a2, &v42, *v12) )
      {
        v20 = 2646;
LABEL_85:
        v9 = -2147024882;
        goto LABEL_40;
      }
      v27 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 96LL))(*a2, &v37);
      v28 = 0;
      if ( &v38 != v27 )
      {
        v28 = *(HSTRING *)v27;
        *(_QWORD *)v27 = 0;
      }
      v29 = v41;
      v41 = v28;
      if ( v29 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v29 + 16LL))(v29);
      v30 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    else if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v14,
        v37);
      v36 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
      }
      goto LABEL_12;
    }
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= a1[67] )
    {
      v17 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v17 + 16LL))(v17);
      }
      if ( string )
        WindowsDeleteString(string);
      if ( v42 )
        WindowsDeleteString(v42);
      return 0;
    }
    v6 = *(_QWORD *)(a1[65] + 8 * j);
    v7 = v41;
    v44 = v41;
    if ( v41 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v41 + 8LL))(v41);
    v8 = OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(
           v7,
           v6,
           &v44);
    v9 = v8;
    if ( v8 != -2147023728 && v8 != -2147483637 )
    {
      if ( v8 < 0 )
      {
        v21 = (unsigned int)v8;
        v20 = 2678;
        goto LABEL_41;
      }
      continue;
    }
    v10 = *(const WCHAR **)(v6 + 32);
    if ( !v10 )
    {
      v9 = -2147467261;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v9,
        v37);
      v11 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_12;
    }
    v44 = 0;
    v19 = -1;
    do
      ++v19;
    while ( v10[v19] );
    if ( v19 <= 0xFFFFFFFF )
    {
      v9 = WindowsCreateString(v10, v19, &v44);
      if ( v9 >= 0 )
      {
        v22 = v42;
        v42 = v44;
        WindowsDeleteString(v22);
      }
    }
    else
    {
      v9 = -2147024362;
    }
    if ( v9 < 0 )
      goto LABEL_10;
    v23 = *(const WCHAR **)(v6 + 8);
    if ( !v23 )
      break;
    v44 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( v24 <= 0xFFFFFFFF )
    {
      v9 = WindowsCreateString(v23, v24, &v44);
      if ( v9 >= 0 )
      {
        v31 = string;
        string = v44;
        WindowsDeleteString(v31);
      }
    }
    else
    {
      v9 = -2147024362;
    }
    if ( v9 < 0 )
      goto LABEL_52;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, HSTRING *))(*(_QWORD *)*a2 + 112LL))(*a2, &v42, &string) )
    {
      v20 = 2670;
      goto LABEL_85;
    }
    v32 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 96LL))(*a2, &v37);
    v33 = 0;
    if ( &v39 != v32 )
    {
      v33 = *(HSTRING *)v32;
      *(_QWORD *)v32 = 0;
    }
    v34 = v41;
    v41 = v33;
    if ( v34 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v34 + 16LL))(v34);
    v35 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  v9 = -2147467261;
LABEL_52:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA6D,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v9,
    v37);
  v25 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_12:
  if ( string )
    WindowsDeleteString(string);
  if ( v42 )
    WindowsDeleteString(v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035ccc  push    rbp
0x180035cce  push    rbx
0x180035ccf  push    rsi
0x180035cd0  push    rdi
0x180035cd1  push    r12
0x180035cd3  push    r14
0x180035cd5  push    r15
0x180035cd7  mov     rbp, rsp
0x180035cda  sub     rsp, 40h
0x180035cde  mov     r15, rdx
0x180035ce1  mov     r14, rcx
0x180035ce4  xor     r12d, r12d
0x180035ce7  mov     [rbp+arg_8], r12
0x180035ceb  mov     [rbp+string], r12
0x180035cef  mov     rcx, [rdx]
0x180035cf2  mov     rax, [rcx]
0x180035cf5  lea     rdx, [rbp+arg_0]
0x180035cf9  mov     rax, [rax+60h]
0x180035cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d02  nop
0x180035d03  mov     edi, r12d
0x180035d06  cmp     rdi, [r14+1B8h]
0x180035d0d  jb      loc_180035DDA
0x180035d13  mov     rsi, r12
0x180035d16  cmp     rsi, [r14+218h]
0x180035d1d  jnb     loc_180035E6A
0x180035d23  mov     rax, [r14+208h]
0x180035d2a  mov     rdi, [rax+rsi*8]
0x180035d2e  mov     rcx, [rbp+arg_0]
0x180035d32  mov     [rbp+arg_18], rcx
0x180035d36  test    rcx, rcx
0x180035d39  jz      short loc_180035D48
0x180035d3b  mov     rax, [rcx]
0x180035d3e  mov     rax, [rax+8]
0x180035d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d47  nop
0x180035d48  lea     r8, [rbp+arg_18]
0x180035d4c  mov     rdx, rdi
0x180035d4f  call    ?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@VStringPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180035d54  mov     ebx, eax
0x180035d56  cmp     eax, 80070490h
0x180035d5b  jnz     loc_180035E4F
0x180035d61  mov     rcx, [rdi+20h]; sourceString
0x180035d65  test    rcx, rcx
0x180035d68  jnz     loc_180035EC1
0x180035d6e  mov     ebx, 80004003h
0x180035d73  mov     rcx, [rbp+38h]; this
0x180035d77  mov     r9d, ebx; char *
0x180035d7a  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180035d81  mov     edx, 0A6Ch; void *
0x180035d86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d8b  nop
0x180035d8c  mov     rcx, [rbp+arg_0]
0x180035d90  test    rcx, rcx
0x180035d93  jz      short loc_180035DA6
0x180035d95  mov     [rbp+arg_0], r12
0x180035d99  mov     rax, [rcx]
0x180035d9c  mov     rax, [rax+10h]
0x180035da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035da5  nop
0x180035da6  mov     rcx, [rbp+string]; string
0x180035daa  test    rcx, rcx
0x180035dad  jz      short loc_180035DBC
0x180035daf  call    cs:__imp_WindowsDeleteString
0x180035db6  nop     dword ptr [rax+rax+00h]
0x180035dbb  nop
0x180035dbc  mov     rcx, [rbp+arg_8]; string
0x180035dc0  test    rcx, rcx
0x180035dc3  jz      loc_180035F1F
0x180035dc9  call    cs:__imp_WindowsDeleteString
0x180035dd0  nop     dword ptr [rax+rax+00h]
0x180035dd5  jmp     loc_180035F1F
0x180035dda  mov     rax, [r14+1A8h]
0x180035de1  mov     rsi, [rax+rdi*8]
0x180035de5  mov     rcx, [rbp+arg_0]
0x180035de9  mov     [rbp+arg_18], rcx
0x180035ded  test    rcx, rcx
0x180035df0  jz      short loc_180035DFF
0x180035df2  mov     rax, [rcx]
0x180035df5  mov     rax, [rax+8]
0x180035df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dfe  nop
0x180035dff  lea     r8, [rbp+arg_18]
0x180035e03  mov     rdx, rsi
0x180035e06  call    ?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180035e0b  mov     ebx, eax
0x180035e0d  cmp     eax, 80070490h
0x180035e12  jnz     loc_180036131
0x180035e18  mov     rcx, [rsi+10h]; sourceString
0x180035e1c  test    rcx, rcx
0x180035e1f  jz      loc_180035EE4
0x180035e25  mov     [rbp+arg_18], r12
0x180035e29  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035e2d  inc     rdx; length
0x180035e30  cmp     [rcx+rdx*2], r12w
0x180035e35  jnz     short loc_180035E2D
0x180035e37  mov     eax, 0FFFFFFFFh
0x180035e3c  cmp     rdx, rax
0x180035e3f  jbe     loc_180035FC9
0x180035e45  mov     ebx, 80070216h
0x180035e4a  jmp     loc_180035FF7
0x180035e4f  cmp     eax, 8000000Bh
0x180035e54  jz      loc_180035D61
0x180035e5a  test    eax, eax
0x180035e5c  js      loc_180036184
0x180035e62  inc     rsi
0x180035e65  jmp     loc_180035D16
0x180035e6a  mov     rcx, [rbp+arg_0]
0x180035e6e  test    rcx, rcx
0x180035e71  jz      short loc_180035E84
0x180035e73  mov     [rbp+arg_0], r12
0x180035e77  mov     rax, [rcx]
0x180035e7a  mov     rax, [rax+10h]
0x180035e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e83  nop
0x180035e84  mov     rcx, [rbp+string]; string
0x180035e88  test    rcx, rcx
0x180035e8b  jz      short loc_180035E9A
0x180035e8d  call    cs:__imp_WindowsDeleteString
0x180035e94  nop     dword ptr [rax+rax+00h]
0x180035e99  nop
0x180035e9a  mov     rcx, [rbp+arg_8]; string
0x180035e9e  test    rcx, rcx
0x180035ea1  jz      short loc_180035EAF
0x180035ea3  call    cs:__imp_WindowsDeleteString
0x180035eaa  nop     dword ptr [rax+rax+00h]
0x180035eaf  xor     eax, eax
0x180035eb1  add     rsp, 40h
0x180035eb5  pop     r15
0x180035eb7  pop     r14
0x180035eb9  pop     r12
0x180035ebb  pop     rdi
0x180035ebc  pop     rsi
0x180035ebd  pop     rbx
0x180035ebe  pop     rbp
0x180035ebf  retn
0x180035ec1  mov     [rbp+arg_18], r12
0x180035ec5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035ec9  inc     rdx; length
0x180035ecc  cmp     [rcx+rdx*2], r12w
0x180035ed1  jnz     short loc_180035EC9
0x180035ed3  mov     eax, 0FFFFFFFFh
0x180035ed8  cmp     rdx, rax
0x180035edb  jbe     short loc_180035F23
0x180035edd  mov     ebx, 80070216h
0x180035ee2  jmp     short loc_180035F56
0x180035ee4  mov     ebx, 80004003h
0x180035ee9  mov     edx, 0A55h; void *
0x180035eee  mov     r9d, ebx; char *
0x180035ef1  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180035ef8  mov     rcx, [rbp+38h]; this
0x180035efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f01  nop
0x180035f02  lea     rcx, [rbp+arg_0]
0x180035f06  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180035f0b  nop
0x180035f0c  lea     rcx, [rbp+string]; this
0x180035f10  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180035f15  nop
0x180035f16  lea     rcx, [rbp+arg_8]; this
0x180035f1a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180035f1f  mov     eax, ebx
0x180035f21  jmp     short loc_180035EB1
0x180035f23  lea     r8, [rbp+arg_18]; string
0x180035f27  call    cs:__imp_WindowsCreateString
0x180035f2e  nop     dword ptr [rax+rax+00h]
0x180035f33  mov     ebx, eax
0x180035f35  test    eax, eax
0x180035f37  js      short loc_180035F51
0x180035f39  mov     rcx, [rbp+arg_8]; string
0x180035f3d  mov     rax, [rbp+arg_18]
0x180035f41  mov     [rbp+arg_8], rax
0x180035f45  call    cs:__imp_WindowsDeleteString
0x180035f4c  nop     dword ptr [rax+rax+00h]
0x180035f51  mov     eax, 0FFFFFFFFh
0x180035f56  test    ebx, ebx
0x180035f58  js      loc_180035D73
0x180035f5e  mov     rcx, [rdi+8]; sourceString
0x180035f62  test    rcx, rcx
0x180035f65  jz      short loc_180035F8C
0x180035f67  mov     [rbp+arg_18], r12
0x180035f6b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035f6f  inc     rdx; length
0x180035f72  cmp     [rcx+rdx*2], r12w
0x180035f77  jnz     short loc_180035F6F
0x180035f79  cmp     rdx, rax
0x180035f7c  jbe     loc_18003607E
0x180035f82  mov     ebx, 80070216h
0x180035f87  jmp     loc_1800360AC
0x180035f8c  mov     ebx, 80004003h
0x180035f91  mov     rcx, [rbp+38h]; this
0x180035f95  mov     r9d, ebx; char *
0x180035f98  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180035f9f  mov     edx, 0A6Dh; void *
0x180035fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035fa9  nop
0x180035faa  mov     rcx, [rbp+arg_0]
0x180035fae  test    rcx, rcx
0x180035fb1  jz      short loc_180035FC4
0x180035fb3  mov     [rbp+arg_0], r12
0x180035fb7  mov     rax, [rcx]
0x180035fba  mov     rax, [rax+10h]
0x180035fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fc3  nop
0x180035fc4  jmp     loc_180035DA6
0x180035fc9  lea     r8, [rbp+arg_18]; string
0x180035fcd  call    cs:__imp_WindowsCreateString
0x180035fd4  nop     dword ptr [rax+rax+00h]
0x180035fd9  mov     ebx, eax
0x180035fdb  test    eax, eax
0x180035fdd  js      short loc_180035FF7
0x180035fdf  mov     rcx, [rbp+arg_8]; string
0x180035fe3  mov     rax, [rbp+arg_18]
0x180035fe7  mov     [rbp+arg_8], rax
0x180035feb  call    cs:__imp_WindowsDeleteString
0x180035ff2  nop     dword ptr [rax+rax+00h]
0x180035ff7  test    ebx, ebx
0x180035ff9  js      loc_180035EE9
0x180035fff  mov     rcx, [r15]
0x180036002  mov     rax, [rcx]
0x180036005  mov     r8d, [rsi]
0x180036008  lea     rdx, [rbp+arg_8]
0x18003600c  mov     rax, [rax+68h]
0x180036010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036015  test    al, al
0x180036017  jz      loc_18003617D
0x18003601d  mov     rcx, [r15]
0x180036020  mov     rax, [rcx]
0x180036023  lea     rdx, [rbp+var_20]
0x180036027  mov     rax, [rax+60h]
0x18003602b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036030  mov     rdx, r12
0x180036033  lea     rcx, [rbp+var_18]
0x180036037  cmp     rcx, rax
0x18003603a  jz      short loc_180036042
0x18003603c  mov     rdx, [rax]
0x18003603f  mov     [rax], r12
0x180036042  mov     rcx, [rbp+arg_0]
0x180036046  mov     [rbp+arg_0], rdx
0x18003604a  test    rcx, rcx
0x18003604d  jz      short loc_18003605C
0x18003604f  mov     rax, [rcx]
0x180036052  mov     rax, [rax+10h]
0x180036056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003605b  nop
0x18003605c  mov     rcx, [rbp+var_20]
0x180036060  test    rcx, rcx
0x180036063  jz      short loc_180036076
0x180036065  mov     [rbp+var_20], r12
0x180036069  mov     rax, [rcx]
0x18003606c  mov     rax, [rax+10h]
0x180036070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036075  nop
0x180036076  inc     rdi
0x180036079  jmp     loc_180035D06
0x18003607e  lea     r8, [rbp+arg_18]; string
0x180036082  call    cs:__imp_WindowsCreateString
0x180036089  nop     dword ptr [rax+rax+00h]
0x18003608e  mov     ebx, eax
0x180036090  test    eax, eax
0x180036092  js      short loc_1800360AC
0x180036094  mov     rcx, [rbp+string]; string
0x180036098  mov     rax, [rbp+arg_18]
0x18003609c  mov     [rbp+string], rax
0x1800360a0  call    cs:__imp_WindowsDeleteString
0x1800360a7  nop     dword ptr [rax+rax+00h]
0x1800360ac  test    ebx, ebx
0x1800360ae  js      loc_180035F91
0x1800360b4  mov     rcx, [r15]
0x1800360b7  mov     rax, [rcx]
0x1800360ba  lea     r8, [rbp+string]
0x1800360be  lea     rdx, [rbp+arg_8]
0x1800360c2  mov     rax, [rax+70h]
0x1800360c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360cb  test    al, al
0x1800360cd  jz      loc_180036191
0x1800360d3  mov     rcx, [r15]
0x1800360d6  mov     rax, [rcx]
0x1800360d9  lea     rdx, [rbp+var_20]
0x1800360dd  mov     rax, [rax+60h]
0x1800360e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360e6  mov     rdx, r12
0x1800360e9  lea     rcx, [rbp+var_10]
0x1800360ed  cmp     rcx, rax
0x1800360f0  jz      short loc_1800360F8
0x1800360f2  mov     rdx, [rax]
0x1800360f5  mov     [rax], r12
0x1800360f8  mov     rcx, [rbp+arg_0]
0x1800360fc  mov     [rbp+arg_0], rdx
0x180036100  test    rcx, rcx
0x180036103  jz      short loc_180036112
0x180036105  mov     rax, [rcx]
0x180036108  mov     rax, [rax+10h]
0x18003610c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036111  nop
0x180036112  mov     rcx, [rbp+var_20]
0x180036116  test    rcx, rcx
0x180036119  jz      short loc_18003612C
0x18003611b  mov     [rbp+var_20], r12
0x18003611f  mov     rax, [rcx]
  ... truncated ...
```
