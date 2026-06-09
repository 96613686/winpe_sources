# UiaManagerCrossMachineStub::GetProcessId(HWND__ *,uint *)

- ea: `0x180066650`
- end: `0x1800666af`
- name: `?GetProcessId@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@PEAI@Z`
- size: `95`
- prototype: `int(UiaManagerCrossMachineStub *__hidden this, HWND, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180031540`
- `0x180066650`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180066694`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180066694`

## string_xrefs

- `0x180066673`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerCrossMachineStub::GetProcessId(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        unsigned int *a3)
{
  const char *v4; // r9
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  try
  {
    *a3 = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80070057LL,
        v6);
    dwProcessId = 0;
    GetWindowThreadProcessId(a2, &dwProcessId);
    *a3 = dwProcessId;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x13E,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180066650  push    rbx; int
0x180066652  sub     rsp, 20h
0x180066656  mov     rbx, r8
0x180066659  mov     rax, rdx
0x18006665c  mov     dword ptr [r8], 0
0x180066663  mov     rcx, [rsp+28h]; this
0x180066668  test    rax, rax
0x18006666b  jnz     short loc_180066684
0x18006666d  mov     r9d, 80070057h; char *
0x180066673  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18006667a  mov     edx, 135h; void *
0x18006667f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066684  mov     [rsp+28h+dwProcessId], 0
0x18006668c  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180066691  mov     rcx, rax; hWnd
0x180066694  call    cs:__imp_GetWindowThreadProcessId
0x18006669a  mov     eax, [rsp+28h+dwProcessId]
0x18006669e  mov     [rbx], eax
0x1800666a0  xor     eax, eax
0x1800666a2  jmp     short loc_1800666A8
0x1800666a4  mov     eax, [rsp+28h+dwProcessId]
0x1800666a8  add     rsp, 20h
0x1800666ac  pop     rbx
0x1800666ad  retn
```
