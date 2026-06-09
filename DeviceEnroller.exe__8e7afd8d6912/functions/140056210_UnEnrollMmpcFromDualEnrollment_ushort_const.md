# UnEnrollMmpcFromDualEnrollment(ushort const *)

- ea: `0x140056210`
- end: `0x1400563ef`
- name: `?UnEnrollMmpcFromDualEnrollment@@YAJPEBG@Z`
- size: `479`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140019a6c`
- `0x140052fc0`

## callees

- `0x1400042f0`
- `0x140006b8c`
- `0x1400095b4`
- `0x14000ad3c`
- `0x14001d7ec`
- `0x140056210`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400562d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400562d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400563ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400563ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140056250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140056250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400562be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400562be`

## string_xrefs

- `0x140056371`: `UnenrollAsync WaitForCompletionNoThrow failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UnEnrollMmpcFromDualEnrollment(const unsigned __int16 *a1)
{
  __int64 v1; // rdx
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  HSTRING v6; // rbx
  __int64 v7; // rcx
  int v8; // edi
  const wchar_t *v9; // r8
  DWORD v10; // edx
  int v11; // r8d
  __int64 v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v17; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v14 = 0;
  string = 0;
  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  v2 = WindowsCreateString(a1, v1, &string);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)v2,
      (int)v14);
    if ( string )
      WindowsDeleteString(string);
    v4 = v14;
    if ( v14 )
    {
      v14 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v4)[2])(v4);
    }
    return v3;
  }
  v6 = string;
  if ( WindowsCreateStringReference(L"Windows.Internal.Management.Enrollment.Enroller", 0x2Fu, &hstringHeader, &v17) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v15 = 0;
  v8 = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(v17, &v15);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v15 + 48LL))(v15, v6, &v14);
    if ( v8 >= 0 )
    {
      v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v14, v10, v11);
      if ( v8 >= 0 || (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
        goto LABEL_21;
      v9 = L"UnenrollAsync WaitForCompletionNoThrow failed";
      goto LABEL_20;
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
    {
      v9 = L"UnenrollAsync failed";
      goto LABEL_20;
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
  {
    v9 = L"UnEnrollMmpcFromDualEnrollment: Failed to activate MDM enrollment instance";
LABEL_20:
    McTemplateU0zd_EventWriteTransfer(v7, "]", v9);
  }
LABEL_21:
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( string )
    WindowsDeleteString(string);
  v13 = v14;
  if ( v14 )
  {
    v14 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v13)[2])(v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140056210  mov     [rsp-18h+arg_8], rbx
0x140056215  mov     [rsp-18h+arg_10], rsi
0x14005621a  push    rbp
0x14005621b  push    rdi
0x14005621c  push    r14
0x14005621e  mov     rbp, rsp
0x140056221  sub     rsp, 60h
0x140056225  mov     rax, cs:__security_cookie
0x14005622c  xor     rax, rsp
0x14005622f  mov     [rbp+var_8], rax
0x140056233  xor     r14d, r14d
0x140056236  mov     [rbp+var_40], r14
0x14005623a  mov     [rbp+string], r14
0x14005623e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140056242  inc     rdx; length
0x140056245  cmp     [rcx+rdx*2], r14w
0x14005624a  jnz     short loc_140056242
0x14005624c  lea     r8, [rbp+string]; string
0x140056250  call    cs:__imp_WindowsCreateString
0x140056256  mov     ebx, eax
0x140056258  test    eax, eax
0x14005625a  jns     short loc_1400562A6
0x14005625c  mov     rcx, [rbp+18h]; this
0x140056260  mov     r9d, eax; char *
0x140056263  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14005626a  mov     edx, 497h; void *
0x14005626f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056274  nop
0x140056275  mov     rcx, [rbp+string]; string
0x140056279  test    rcx, rcx
0x14005627c  jz      short loc_140056285
0x14005627e  call    cs:__imp_WindowsDeleteString
0x140056284  nop
0x140056285  mov     rcx, [rbp+var_40]
0x140056289  test    rcx, rcx
0x14005628c  jz      short loc_14005629F
0x14005628e  mov     [rbp+var_40], r14
0x140056292  mov     rax, [rcx]
0x140056295  mov     rax, [rax+10h]
0x140056299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005629e  nop
0x14005629f  mov     eax, ebx
0x1400562a1  jmp     loc_1400563CE
0x1400562a6  mov     rbx, [rbp+string]
0x1400562aa  lea     r9, [rbp+var_28]; string
0x1400562ae  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400562b2  mov     edx, 2Fh ; '/'; length
0x1400562b7  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x1400562be  call    cs:__imp_WindowsCreateStringReference
0x1400562c4  test    eax, eax
0x1400562c6  jns     short loc_1400562DD
0x1400562c8  xor     r9d, r9d; lpArguments
0x1400562cb  xor     r8d, r8d; nNumberOfArguments
0x1400562ce  lea     edx, [r9+1]; dwExceptionFlags
0x1400562d2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1400562d7  call    cs:__imp_RaiseException
0x1400562dd  mov     [rbp+var_38], r14
0x1400562e1  lea     rdx, [rbp+var_38]
0x1400562e5  mov     rcx, [rbp+var_28]
0x1400562e9  call    ??$ActivateInstance@UIEnrollment@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEnrollment@Enrollment@Management@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(HSTRING__ *,Windows::Internal::Management::Enrollment::IEnrollment * *)
0x1400562ee  mov     edi, eax
0x1400562f0  test    eax, eax
0x1400562f2  jns     short loc_14005630A
0x1400562f4  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 2
0x1400562fb  jz      loc_140056388
0x140056301  lea     r8, aUnenrollmmpcfr; "UnEnrollMmpcFromDualEnrollment: Failed "...
0x140056308  jmp     short loc_140056378
0x14005630a  mov     rdi, [rbp+var_38]
0x14005630e  mov     rax, [rdi]
0x140056311  mov     rsi, [rax+30h]
0x140056315  mov     rcx, [rbp+var_40]
0x140056319  test    rcx, rcx
0x14005631c  jz      short loc_14005632F
0x14005631e  mov     [rbp+var_40], r14
0x140056322  mov     rdx, [rcx]
0x140056325  mov     rax, [rdx+10h]
0x140056329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005632e  nop
0x14005632f  lea     r8, [rbp+var_40]
0x140056333  mov     rdx, rbx
0x140056336  mov     rcx, rdi
0x140056339  mov     rax, rsi
0x14005633c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056341  mov     edi, eax
0x140056343  test    eax, eax
0x140056345  jns     short loc_140056359
0x140056347  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 2
0x14005634e  jz      short loc_140056388
0x140056350  lea     r8, aUnenrollasyncF; "UnenrollAsync failed"
0x140056357  jmp     short loc_140056378
0x140056359  mov     rcx, [rbp+var_40]
0x14005635d  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x140056362  mov     edi, eax
0x140056364  test    eax, eax
0x140056366  jns     short loc_140056388
0x140056368  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 2
0x14005636f  jz      short loc_140056388
0x140056371  lea     r8, aUnenrollasyncW; "UnenrollAsync WaitForCompletionNoThrow "...
0x140056378  mov     r9d, eax
0x14005637b  lea     rdx, EnterpriseDiagnosticsDualModeFailure; "]"
0x140056382  call    McTemplateU0zd_EventWriteTransfer
0x140056387  nop
0x140056388  mov     rcx, [rbp+var_38]
0x14005638c  test    rcx, rcx
0x14005638f  jz      short loc_1400563A2
0x140056391  mov     [rbp+var_38], r14
0x140056395  mov     rax, [rcx]
0x140056398  mov     rax, [rax+10h]
0x14005639c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400563a1  nop
0x1400563a2  mov     rcx, [rbp+string]; string
0x1400563a6  test    rcx, rcx
0x1400563a9  jz      short loc_1400563B2
0x1400563ab  call    cs:__imp_WindowsDeleteString
0x1400563b1  nop
0x1400563b2  mov     rcx, [rbp+var_40]
0x1400563b6  test    rcx, rcx
0x1400563b9  jz      short loc_1400563CC
0x1400563bb  mov     [rbp+var_40], r14
0x1400563bf  mov     rax, [rcx]
0x1400563c2  mov     rax, [rax+10h]
0x1400563c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400563cb  nop
0x1400563cc  mov     eax, edi
0x1400563ce  mov     rcx, [rbp+var_8]
0x1400563d2  xor     rcx, rsp; StackCookie
0x1400563d5  call    __security_check_cookie
0x1400563da  lea     r11, [rsp+60h+var_s0]
0x1400563df  mov     rbx, [r11+28h]
0x1400563e3  mov     rsi, [r11+30h]
0x1400563e7  mov     rsp, r11
0x1400563ea  pop     r14
0x1400563ec  pop     rdi
0x1400563ed  pop     rbp
0x1400563ee  retn
```
