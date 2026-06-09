# SystemSettings::WorkAccess::CEnrollmentHelper::DoRecovery(ushort *)

- ea: `0x180046768`
- end: `0x1800468ce`
- name: `?DoRecovery@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAG@Z`
- size: `358`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002454c`

## callees

- `0x180002a60`
- `0x18000526c`
- `0x1800058fc`
- `0x1800076ac`
- `0x1800096ec`
- `0x18001ac98`
- `0x1800222b0`
- `0x18003ac00`
- `0x180044668`
- `0x180046768`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004680f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004680f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800467e2`

## string_xrefs

- `0x1800467b7`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180046862`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::DoRecovery(
        PCNZWCH sourceString,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-29h]
  __int64 v13; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  __int64 v15; // [rsp+40h] [rbp-9h] BYREF
  HSTRING v16; // [rsp+50h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  string = 0;
  Windows::Internal::StringReference::StringReference(&v16, (const unsigned __int16 (*)[48])a2);
  v15 = 0;
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
         v16,
         &v15);
  v4 = v3;
  if ( v3 >= 0 )
  {
    string = 0;
    v5 = -1;
    do
      ++v5;
    while ( sourceString[v5] );
    WindowsCreateString(sourceString, v5, &string);
    v13 = 0;
    v6 = v15;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v15 + 200LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    v8 = v7(
           v6,
           *(_QWORD *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 8),
           string,
           &v13);
    v4 = v8;
    if ( v8 >= 0 )
    {
      if ( v13 )
      {
        v4 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
               v13,
               0xFFFFFFFFLL);
        goto LABEL_11;
      }
      v4 = -2147024882;
      v9 = 2147942414LL;
      v10 = 1882;
    }
    else
    {
      v9 = (unsigned int)v8;
      v10 = 1881;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)v9,
      v12);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x756,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v3,
    v12);
LABEL_12:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v4;
}

```

## disassembly

```asm
0x180046768  push    rbp
0x18004676a  push    rbx
0x18004676b  push    rsi
0x18004676c  push    rdi
0x18004676d  lea     rbp, [rsp-3Fh]
0x180046772  sub     rsp, 88h
0x180046779  mov     rax, cs:__security_cookie
0x180046780  xor     rax, rsp
0x180046783  mov     [rbp+57h+var_30], rax
0x180046787  mov     rdi, rcx
0x18004678a  xor     esi, esi
0x18004678c  mov     [rbp+57h+string], rsi
0x180046790  lea     rcx, [rbp+57h+var_50]; string
0x180046794  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180046799  mov     [rbp+57h+var_60], rsi
0x18004679d  lea     rdx, [rbp+57h+var_60]
0x1800467a1  mov     rcx, [rbp+57h+var_50]
0x1800467a5  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x1800467aa  mov     ebx, eax
0x1800467ac  test    eax, eax
0x1800467ae  jns     short loc_1800467CD
0x1800467b0  mov     rcx, [rbp+5Fh]; this
0x1800467b4  mov     r9d, eax; char *
0x1800467b7  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x1800467be  mov     edx, 756h; void *
0x1800467c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800467c8  jmp     loc_1800468A0
0x1800467cd  mov     rbx, [rbp+57h+string]
0x1800467d1  test    rbx, rbx
0x1800467d4  jz      short loc_1800467F7
0x1800467d6  lea     rcx, [rbp+57h+var_58]; this
0x1800467da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800467df  mov     rcx, rbx; string
0x1800467e2  call    cs:__imp_WindowsDeleteString
0x1800467e9  nop     dword ptr [rax+rax+00h]
0x1800467ee  lea     rcx, [rbp+57h+var_58]; this
0x1800467f2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800467f7  mov     [rbp+57h+string], rsi
0x1800467fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800467ff  inc     rdx; length
0x180046802  cmp     [rdi+rdx*2], si
0x180046806  jnz     short loc_1800467FF
0x180046808  lea     r8, [rbp+57h+string]; string
0x18004680c  mov     rcx, rdi; sourceString
0x18004680f  call    cs:__imp_WindowsCreateString
0x180046816  nop     dword ptr [rax+rax+00h]
0x18004681b  mov     [rbp+57h+var_70], rsi
0x18004681f  mov     rdi, [rbp+57h+var_60]
0x180046823  mov     rax, [rdi]
0x180046826  mov     rbx, [rax+0C8h]
0x18004682d  lea     rcx, [rbp+57h+var_70]
0x180046831  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046836  lea     r9, [rbp+57h+var_70]
0x18004683a  mov     r8, [rbp+57h+string]
0x18004683e  mov     rdx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180046845  mov     rdx, [rdx+8]
0x180046849  mov     rcx, rdi
0x18004684c  mov     rax, rbx
0x18004684f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046854  mov     ebx, eax
0x180046856  test    eax, eax
0x180046858  jns     short loc_180046874
0x18004685a  mov     r9d, eax; char *
0x18004685d  mov     edx, 759h; void *
0x180046862  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180046869  mov     rcx, [rbp+5Fh]; this
0x18004686d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046872  jmp     short loc_180046896
0x180046874  mov     rcx, [rbp+57h+var_70]
0x180046878  test    rcx, rcx
0x18004687b  jnz     short loc_18004688C
0x18004687d  mov     ebx, 8007000Eh
0x180046882  mov     r9d, ebx
0x180046885  mov     edx, 75Ah
0x18004688a  jmp     short loc_180046862
0x18004688c  or      edx, 0FFFFFFFFh
0x18004688f  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180046894  mov     ebx, eax
0x180046896  lea     rcx, [rbp+57h+var_70]
0x18004689a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004689f  nop
0x1800468a0  lea     rcx, [rbp+57h+var_60]
0x1800468a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800468a9  nop
0x1800468aa  lea     rcx, [rbp+57h+string]; this
0x1800468ae  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800468b3  mov     eax, ebx
0x1800468b5  mov     rcx, [rbp+57h+var_30]
0x1800468b9  xor     rcx, rsp; StackCookie
0x1800468bc  call    __security_check_cookie
0x1800468c1  add     rsp, 88h
0x1800468c8  pop     rdi
0x1800468c9  pop     rsi
0x1800468ca  pop     rbx
0x1800468cb  pop     rbp
0x1800468cc  retn
```
