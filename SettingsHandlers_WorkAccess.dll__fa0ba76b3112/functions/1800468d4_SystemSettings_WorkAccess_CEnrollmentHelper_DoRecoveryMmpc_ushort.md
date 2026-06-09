# SystemSettings::WorkAccess::CEnrollmentHelper::DoRecoveryMmpc(ushort *)

- ea: `0x1800468d4`
- end: `0x180046a3a`
- name: `?DoRecoveryMmpc@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAG@Z`
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
- `0x1800468d4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004697b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004697b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004694e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004694e`

## string_xrefs

- `0x180046923`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x1800469ce`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::DoRecoveryMmpc(
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
           *(_QWORD *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 24),
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
      v10 = 1896;
    }
    else
    {
      v9 = (unsigned int)v8;
      v10 = 1895;
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
    (void *)0x764,
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
0x1800468d4  push    rbp
0x1800468d6  push    rbx
0x1800468d7  push    rsi
0x1800468d8  push    rdi
0x1800468d9  lea     rbp, [rsp-3Fh]
0x1800468de  sub     rsp, 88h
0x1800468e5  mov     rax, cs:__security_cookie
0x1800468ec  xor     rax, rsp
0x1800468ef  mov     [rbp+57h+var_30], rax
0x1800468f3  mov     rdi, rcx
0x1800468f6  xor     esi, esi
0x1800468f8  mov     [rbp+57h+string], rsi
0x1800468fc  lea     rcx, [rbp+57h+var_50]; string
0x180046900  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180046905  mov     [rbp+57h+var_60], rsi
0x180046909  lea     rdx, [rbp+57h+var_60]
0x18004690d  mov     rcx, [rbp+57h+var_50]
0x180046911  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x180046916  mov     ebx, eax
0x180046918  test    eax, eax
0x18004691a  jns     short loc_180046939
0x18004691c  mov     rcx, [rbp+5Fh]; this
0x180046920  mov     r9d, eax; char *
0x180046923  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004692a  mov     edx, 764h; void *
0x18004692f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046934  jmp     loc_180046A0C
0x180046939  mov     rbx, [rbp+57h+string]
0x18004693d  test    rbx, rbx
0x180046940  jz      short loc_180046963
0x180046942  lea     rcx, [rbp+57h+var_58]; this
0x180046946  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004694b  mov     rcx, rbx; string
0x18004694e  call    cs:__imp_WindowsDeleteString
0x180046955  nop     dword ptr [rax+rax+00h]
0x18004695a  lea     rcx, [rbp+57h+var_58]; this
0x18004695e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180046963  mov     [rbp+57h+string], rsi
0x180046967  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004696b  inc     rdx; length
0x18004696e  cmp     [rdi+rdx*2], si
0x180046972  jnz     short loc_18004696B
0x180046974  lea     r8, [rbp+57h+string]; string
0x180046978  mov     rcx, rdi; sourceString
0x18004697b  call    cs:__imp_WindowsCreateString
0x180046982  nop     dword ptr [rax+rax+00h]
0x180046987  mov     [rbp+57h+var_70], rsi
0x18004698b  mov     rdi, [rbp+57h+var_60]
0x18004698f  mov     rax, [rdi]
0x180046992  mov     rbx, [rax+0C8h]
0x180046999  lea     rcx, [rbp+57h+var_70]
0x18004699d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800469a2  lea     r9, [rbp+57h+var_70]
0x1800469a6  mov     r8, [rbp+57h+string]
0x1800469aa  mov     rdx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1800469b1  mov     rdx, [rdx+18h]
0x1800469b5  mov     rcx, rdi
0x1800469b8  mov     rax, rbx
0x1800469bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c0  mov     ebx, eax
0x1800469c2  test    eax, eax
0x1800469c4  jns     short loc_1800469E0
0x1800469c6  mov     r9d, eax; char *
0x1800469c9  mov     edx, 767h; void *
0x1800469ce  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x1800469d5  mov     rcx, [rbp+5Fh]; this
0x1800469d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800469de  jmp     short loc_180046A02
0x1800469e0  mov     rcx, [rbp+57h+var_70]
0x1800469e4  test    rcx, rcx
0x1800469e7  jnz     short loc_1800469F8
0x1800469e9  mov     ebx, 8007000Eh
0x1800469ee  mov     r9d, ebx
0x1800469f1  mov     edx, 768h
0x1800469f6  jmp     short loc_1800469CE
0x1800469f8  or      edx, 0FFFFFFFFh
0x1800469fb  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180046a00  mov     ebx, eax
0x180046a02  lea     rcx, [rbp+57h+var_70]
0x180046a06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046a0b  nop
0x180046a0c  lea     rcx, [rbp+57h+var_60]
0x180046a10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046a15  nop
0x180046a16  lea     rcx, [rbp+57h+string]; this
0x180046a1a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180046a1f  mov     eax, ebx
0x180046a21  mov     rcx, [rbp+57h+var_30]
0x180046a25  xor     rcx, rsp; StackCookie
0x180046a28  call    __security_check_cookie
0x180046a2d  add     rsp, 88h
0x180046a34  pop     rdi
0x180046a35  pop     rsi
0x180046a36  pop     rbx
0x180046a37  pop     rbp
0x180046a38  retn
```
