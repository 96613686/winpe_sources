# UiaManagerCrossMachineStub::GetHwndWindowRect(HWND__ *,tagRECT *)

- ea: `0x180066260`
- end: `0x1800662ca`
- name: `?GetHwndWindowRect@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `106`
- prototype: `int(UiaManagerCrossMachineStub *__hidden this, HWND, struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18002a514`
- `0x180031540`
- `0x180066260`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18006629d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18006629d`

## string_xrefs

- `0x180066281`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800662a7`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerCrossMachineStub::GetHwndWindowRect(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        struct tagRECT *a3)
{
  const char *v3; // r9
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    *a3 = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x603,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80070057LL,
        v5);
    if ( !GetWindowRect(a2, a3) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x605,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x609,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180066260  push    rbx; int
0x180066262  sub     rsp, 20h
0x180066266  mov     rax, rdx
0x180066269  xorps   xmm0, xmm0
0x18006626c  movdqu  xmmword ptr [r8], xmm0
0x180066271  mov     rcx, [rsp+28h]; this
0x180066276  test    rax, rax
0x180066279  jnz     short loc_180066292
0x18006627b  mov     r9d, 80070057h; char *
0x180066281  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180066288  mov     edx, 603h; void *
0x18006628d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066292  mov     rbx, [rsp+28h]
0x180066297  mov     rdx, r8; lpRect
0x18006629a  mov     rcx, rax; hWnd
0x18006629d  call    cs:__imp_GetWindowRect
0x1800662a3  test    eax, eax
0x1800662a5  jnz     short loc_1800662BB
0x1800662a7  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800662ae  mov     edx, 605h; void *
0x1800662b3  mov     rcx, rbx; this
0x1800662b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800662bb  xor     eax, eax
0x1800662bd  jmp     short loc_1800662C3
0x1800662bf  mov     eax, [rsp+28h+arg_8]
0x1800662c3  add     rsp, 20h
0x1800662c7  pop     rbx
0x1800662c8  retn
```
