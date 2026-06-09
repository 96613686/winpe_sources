# UiaManagerCrossMachineStub::SetSurrogateWindow(HWND__ *,HWND__ *,uint)

- ea: `0x180040040`
- end: `0x1800400cd`
- name: `?SetSurrogateWindow@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@0I@Z`
- size: `141`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineStub *this, HWND, HWND, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18002a514`
- `0x180031540`
- `0x180040040`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180040098`
- `ext-ms-win-ntuser-window-l1-1-0!SetPropW` at `0x180040098`

## string_xrefs

- `0x18004005c`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x18004007d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800400a7`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerCrossMachineStub::SetSurrogateWindow(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        HWND a3,
        int a4)
{
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x524,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x525,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !SetPropW(a2, L"MS_UIA_SurrogateHwnd", a3) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x527,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        v5);
    UiaManagerCrossMachineStubFactory::s_surrogateProcessId = a4;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52C,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180040040  push    rbx; int
0x180040042  sub     rsp, 20h
0x180040046  mov     ebx, r9d
0x180040049  mov     rax, rdx
0x18004004c  mov     rcx, [rsp+28h]; this
0x180040051  test    rax, rax
0x180040054  jnz     short loc_18004006D
0x180040056  mov     r9d, 80070057h; char *
0x18004005c  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180040063  mov     edx, 524h; void *
0x180040068  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004006d  mov     rcx, [rsp+28h]; this
0x180040072  test    r8, r8
0x180040075  jnz     short loc_18004008E
0x180040077  mov     r9d, 80070057h; char *
0x18004007d  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180040084  mov     edx, 525h; void *
0x180040089  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004008e  lea     rdx, aMsUiaSurrogate; "MS_UIA_SurrogateHwnd"
0x180040095  mov     rcx, rax; hWnd
0x180040098  call    cs:__imp_SetPropW
0x18004009e  mov     rcx, [rsp+28h]; this
0x1800400a3  test    eax, eax
0x1800400a5  jnz     short loc_1800400B8
0x1800400a7  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800400ae  mov     edx, 527h; void *
0x1800400b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800400b8  mov     cs:?s_surrogateProcessId@UiaManagerCrossMachineStubFactory@@0U?$atomic@I@std@@A, ebx; std::atomic<uint> UiaManagerCrossMachineStubFactory::s_surrogateProcessId
0x1800400be  xor     eax, eax
0x1800400c0  jmp     short loc_1800400C6
0x1800400c2  mov     eax, [rsp+28h+arg_8]
0x1800400c6  add     rsp, 20h
0x1800400ca  pop     rbx
0x1800400cb  retn
```
