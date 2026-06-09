# winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc(void *)

- ea: `0x18000e340`
- end: `0x18000e3ae`
- name: `?CustomCursorThreadProc@implementation@Experience@Accessibility@Internal@Windows@winrt@@YAKPEAX@Z`
- size: `110`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000cf94`
- `0x18000df78`
- `0x18000e2ec`
- `0x18000e340`
- `0x18002b1e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e38e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e38e`

## string_xrefs

- `0x18000e36f`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.accessibility.experience.customcursor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc(
        unsigned int *Parameter)
{
  int v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v7; // [rsp+30h] [rbp+8h]
  unsigned int *v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = Parameter;
  try
  {
    wil::CoInitializeEx();
    v2 = CursorUtils::CreateAndApplyCustomCursor(*Parameter, Parameter[1]);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.accessibility.e"
                      "xperience.customcursor.cpp",
        (const char *)(unsigned int)v2,
        v5);
    if ( v7 )
      CoUninitialize();
    std::unique_ptr__anonymous_namespace_::CustomCursorParameters_std::default_delete__anonymous_namespace_::CustomCursorParameters___::_unique_ptr__anonymous_namespace_::CustomCursorParameters_std::default_delete__anonymous_namespace_::CustomCursorParameters___(&v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x20,
                           (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.inter"
                                         "nal.accessibility.experience.customcursor.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000e340  push    rbx; int
0x18000e342  sub     rsp, 20h
0x18000e346  mov     rbx, rcx
0x18000e349  mov     [rsp+28h+arg_8], rcx
0x18000e34e  lea     rcx, [rsp+28h+arg_0]
0x18000e353  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x18000e358  nop
0x18000e359  mov     edx, [rbx+4]
0x18000e35c  mov     ecx, [rbx]
0x18000e35e  call    ?CreateAndApplyCustomCursor@CursorUtils@@SAJHUColor@UI@Windows@winrt@@@Z; CursorUtils::CreateAndApplyCustomCursor(int,winrt::Windows::UI::Color)
0x18000e363  mov     rcx, [rsp+28h]; this
0x18000e368  test    eax, eax
0x18000e36a  jns     short loc_18000E381
0x18000e36c  mov     r9d, eax; char *
0x18000e36f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\accessibletech\\ex"...
0x18000e376  mov     edx, 1Ch; void *
0x18000e37b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e381  mov     al, byte ptr [rsp+28h+arg_0]
0x18000e385  mov     byte ptr [rsp+28h+arg_0], 0
0x18000e38a  test    al, al
0x18000e38c  jz      short loc_18000E395
0x18000e38e  call    cs:__imp_CoUninitialize
0x18000e394  nop
0x18000e395  lea     rcx, [rsp+28h+arg_8]
0x18000e39a  call    std__unique_ptr__anonymous_namespace___CustomCursorParameters_std__default_delete__anonymous_namespace___CustomCursorParameters______unique_ptr__anonymous_namespace___CustomCursorParameters_std__default_delete__anonymous_namespace___CustomCursorParameters___
0x18000e39f  xor     eax, eax
0x18000e3a1  jmp     short loc_18000E3A7
0x18000e3a3  mov     eax, [rsp+28h+arg_0]
0x18000e3a7  add     rsp, 20h
0x18000e3ab  pop     rbx
0x18000e3ac  retn
```
