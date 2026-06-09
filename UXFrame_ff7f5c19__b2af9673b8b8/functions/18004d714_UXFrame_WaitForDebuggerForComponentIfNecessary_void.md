# UXFrame::WaitForDebuggerForComponentIfNecessary(void)

- ea: `0x18004d714`
- end: `0x18004d78d`
- name: `?WaitForDebuggerForComponentIfNecessary@UXFrame@@AEAAXXZ`
- size: `121`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046cb0`
- `0x18004a43c`

## callees

- `0x1800043f4`
- `0x18000d810`
- `0x18001049c`
- `0x18001f48c`
- `0x18004d714`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004d76b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004d76b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004d765`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004d765`

## string_xrefs

- `0x18004d77b`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004d728`: `WaitForDebuggerBeforeLoadingComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UXFrame::WaitForDebuggerForComponentIfNecessary(UXFrame *this, __int64 a2, __int64 a3, const char *a4)
{
  char v5; // bl
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 56) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x531,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      a4);
  winrt::hstring::hstring((winrt::hstring *)&v7, L"WaitForDebuggerBeforeLoadingComponent");
  v5 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
         &v7,
         (_QWORD *)this + 22,
         0);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v7);
  if ( v5 )
  {
    while ( !IsDebuggerPresent() )
      Sleep(0x3E8u);
  }
}

```

## disassembly

```asm
0x18004d714  push    rbx
0x18004d716  sub     rsp, 20h
0x18004d71a  mov     rbx, rcx
0x18004d71d  mov     rcx, [rsp+28h]; this
0x18004d722  cmp     byte ptr [rbx+38h], 0
0x18004d726  jz      short loc_18004D77B
0x18004d728  lea     rdx, aWaitfordebugge; "WaitForDebuggerBeforeLoadingComponent"
0x18004d72f  lea     rcx, [rsp+28h+arg_0]; this
0x18004d734  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18004d739  nop
0x18004d73a  lea     rdx, [rbx+0B0h]
0x18004d741  xor     r8d, r8d
0x18004d744  lea     rcx, [rsp+28h+arg_0]
0x18004d749  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x18004d74e  mov     bl, al
0x18004d750  lea     rcx, [rsp+28h+arg_0]
0x18004d755  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004d75a  test    bl, bl
0x18004d75c  jz      short loc_18004D775
0x18004d75e  jmp     short loc_18004D76B
0x18004d760  mov     ecx, 3E8h; dwMilliseconds
0x18004d765  call    cs:__imp_Sleep
0x18004d76b  call    cs:__imp_IsDebuggerPresent
0x18004d771  test    eax, eax
0x18004d773  jz      short loc_18004D760
0x18004d775  add     rsp, 20h
0x18004d779  pop     rbx
0x18004d77a  retn
0x18004d77b  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004d782  mov     edx, 531h; void *
0x18004d787  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
