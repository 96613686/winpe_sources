# winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor::ApplyCustomCursor(uint,winrt::Windows::UI::Color const &)

- ea: `0x18000e19c`
- end: `0x18000e293`
- name: `?ApplyCustomCursor@CustomCursor@implementation@Experience@Accessibility@Internal@Windows@winrt@@QEAAXIAEBUColor@UI@67@@Z`
- size: `247`
- prototype: `void __fastcall(winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor *__hidden this, unsigned int, const struct winrt::Windows::UI::Color *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e170`
- `0x18000e2c4`

## callees

- `0x18000cf94`
- `0x18000dcc0`
- `0x18000df78`
- `0x18000df9c`
- `0x18000e19c`
- `0x18000ea34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e1e5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e23c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e22d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e22d`

## string_xrefs

- `0x18000e207`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.accessibility.experience.customcursor.cpp`
- `0x18000e261`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.accessibility.experience.customcursor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor::ApplyCustomCursor(
        winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor *this,
        int a2,
        const struct winrt::Windows::UI::Color *a3)
{
  _DWORD *v5; // r9
  HANDLE Thread; // rax
  DWORD v7; // eax
  signed int LastError; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID lpParameter; // [rsp+40h] [rbp+8h] BYREF
  HANDLE v12; // [rsp+50h] [rbp+18h] BYREF

  lpParameter = this;
  std::make_unique__anonymous_namespace_::CustomCursorParameters_0_(&lpParameter);
  v5 = lpParameter;
  *(_DWORD *)lpParameter = a2;
  v5[1] = *(_DWORD *)a3;
  Thread = CreateThread(
             0,
             0,
             winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc,
             v5,
             0,
             0);
  v12 = Thread;
  if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.accessibility.exp"
                    "erience.customcursor.cpp",
      (const char *)retaddr);
  lpParameter = 0;
  v7 = WaitForSingleObject(Thread, 0x1388u);
  if ( v7 )
  {
    if ( v7 == -1 )
    {
      LastError = GetLastError();
      if ( LastError <= 0 )
        goto LABEL_9;
    }
    else
    {
      LOWORD(LastError) = 1460;
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
    if ( LastError < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.accessibility.e"
                      "xperience.customcursor.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationFlags);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  std::unique_ptr__anonymous_namespace_::CustomCursorParameters_std::default_delete__anonymous_namespace_::CustomCursorParameters___::_unique_ptr__anonymous_namespace_::CustomCursorParameters_std::default_delete__anonymous_namespace_::CustomCursorParameters___(&lpParameter);
}

```

## disassembly

```asm
0x18000e19c  mov     [rsp+arg_18], rbx
0x18000e1a1  mov     [rsp+lpParameter], rcx
0x18000e1a6  push    rdi
0x18000e1a7  sub     rsp, 30h
0x18000e1ab  mov     rdi, r8
0x18000e1ae  mov     ebx, edx
0x18000e1b0  lea     rcx, [rsp+38h+lpParameter]
0x18000e1b5  call    std__make_unique__anonymous_namespace___CustomCursorParameters_0_
0x18000e1ba  nop
0x18000e1bb  mov     r9, [rsp+38h+lpParameter]; lpParameter
0x18000e1c0  mov     [r9], ebx
0x18000e1c3  mov     eax, [rdi]
0x18000e1c5  mov     [r9+4], eax
0x18000e1c9  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000e1d2  mov     [rsp+38h+dwCreationFlags], 0; int
0x18000e1da  lea     r8, ?CustomCursorThreadProc@implementation@Experience@Accessibility@Internal@Windows@winrt@@YAKPEAX@Z; lpStartAddress
0x18000e1e1  xor     edx, edx; dwStackSize
0x18000e1e3  xor     ecx, ecx; lpThreadAttributes
0x18000e1e5  call    cs:__imp_CreateThread
0x18000e1eb  mov     [rsp+38h+arg_10], rax
0x18000e1f0  lea     rcx, [rax+1]
0x18000e1f4  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000e1fb  setz    cl
0x18000e1fe  mov     r9, [rsp+38h]; char *
0x18000e203  test    cl, cl
0x18000e205  jz      short loc_18000E21C
0x18000e207  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\accessibletech\\ex"...
0x18000e20e  mov     edx, 2Fh ; '/'; void *
0x18000e213  mov     rcx, r9; this
0x18000e216  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e21c  mov     [rsp+38h+lpParameter], 0
0x18000e225  mov     edx, 1388h; dwMilliseconds
0x18000e22a  mov     rcx, rax; hHandle
0x18000e22d  call    cs:__imp_WaitForSingleObject
0x18000e233  test    eax, eax
0x18000e235  jz      short loc_18000E273
0x18000e237  cmp     eax, 0FFFFFFFFh
0x18000e23a  jnz     short loc_18000E248
0x18000e23c  call    cs:__imp_GetLastError
0x18000e242  test    eax, eax
0x18000e244  jle     short loc_18000E255
0x18000e246  jmp     short loc_18000E24D
0x18000e248  mov     eax, 5B4h
0x18000e24d  movzx   eax, ax
0x18000e250  or      eax, 80070000h
0x18000e255  mov     rcx, [rsp+38h]; this
0x18000e25a  test    eax, eax
0x18000e25c  jns     short loc_18000E273
0x18000e25e  mov     r9d, eax; char *
0x18000e261  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\accessibletech\\ex"...
0x18000e268  mov     edx, 39h ; '9'; void *
0x18000e26d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e273  lea     rcx, [rsp+38h+arg_10]
0x18000e278  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e27d  nop
0x18000e27e  lea     rcx, [rsp+38h+lpParameter]
0x18000e283  call    std__unique_ptr__anonymous_namespace___CustomCursorParameters_std__default_delete__anonymous_namespace___CustomCursorParameters______unique_ptr__anonymous_namespace___CustomCursorParameters_std__default_delete__anonymous_namespace___CustomCursorParameters___
0x18000e288  mov     rbx, [rsp+38h+arg_18]
0x18000e28d  add     rsp, 30h
0x18000e291  pop     rdi
0x18000e292  retn
```
