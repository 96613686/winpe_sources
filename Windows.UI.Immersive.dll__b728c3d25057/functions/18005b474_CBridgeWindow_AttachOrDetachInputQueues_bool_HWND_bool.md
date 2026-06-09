# CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)

- ea: `0x18005b474`
- end: `0x18005b515`
- name: `?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z`
- size: `161`
- prototype: `int(CBridgeWindow *__hidden this, bool, HWND, bool)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003ed70`
- `0x18005a400`
- `0x18005bf04`
- `0x18005c0b8`

## callees

- `0x18005b474`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4e5`
- `USER32!AttachThreadInput` at `0x18005b4d4`
- `USER32!AttachThreadInput` at `0x18005b4f2`
- `USER32!AttachThreadInput` at `0x18005b4d4`
- `USER32!AttachThreadInput` at `0x18005b4f2`
- `USER32!SetActiveWindow` at `0x18005b4dd`
- `USER32!SetActiveWindow` at `0x18005b4dd`
- `USER32!GetActiveWindow` at `0x18005b4af`
- `USER32!GetActiveWindow` at `0x18005b4af`
- `USER32!GetWindowThreadProcessId` at `0x18005b49e`
- `USER32!GetWindowThreadProcessId` at `0x18005b49e`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_AttachOrDetachInputQueues(CBridgeWindow *this, char a2, HWND a3, char a4)
{
  DWORD WindowThreadProcessId; // ebp
  HWND ActiveWindow; // rsi
  DWORD CurrentThreadId; // eax
  DWORD v10; // eax

  if ( *((_BYTE *)this + 248) )
  {
    *((_BYTE *)this + 249) = a2;
  }
  else
  {
    WindowThreadProcessId = GetWindowThreadProcessId(a3, 0);
    if ( WindowThreadProcessId )
    {
      if ( a2 )
      {
        ActiveWindow = GetActiveWindow();
        if ( !ActiveWindow )
          ActiveWindow = (HWND)*((_QWORD *)this + 21);
        CurrentThreadId = GetCurrentThreadId();
        AttachThreadInput(WindowThreadProcessId, CurrentThreadId, 1);
        SetActiveWindow(ActiveWindow);
      }
      else
      {
        do
          v10 = GetCurrentThreadId();
        while ( AttachThreadInput(WindowThreadProcessId, v10, 0) );
      }
    }
  }
  if ( !a4 )
    *((_BYTE *)this + 249) = a2;
  return 0;
}

```

## disassembly

```asm
0x18005b474  push    rbx
0x18005b476  push    rbp
0x18005b477  push    rsi
0x18005b478  push    rdi
0x18005b479  push    r14
0x18005b47b  sub     rsp, 20h
0x18005b47f  cmp     byte ptr [rcx+0F8h], 0
0x18005b486  mov     r14b, r9b
0x18005b489  mov     dil, dl
0x18005b48c  mov     rbx, rcx
0x18005b48f  jz      short loc_18005B499
0x18005b491  mov     [rcx+0F9h], dl
0x18005b497  jmp     short loc_18005B4FC
0x18005b499  xor     edx, edx; lpdwProcessId
0x18005b49b  mov     rcx, r8; hWnd
0x18005b49e  call    cs:__imp_GetWindowThreadProcessId
0x18005b4a4  mov     ebp, eax
0x18005b4a6  test    eax, eax
0x18005b4a8  jz      short loc_18005B4FC
0x18005b4aa  test    dil, dil
0x18005b4ad  jz      short loc_18005B4E5
0x18005b4af  call    cs:__imp_GetActiveWindow
0x18005b4b5  mov     rsi, rax
0x18005b4b8  test    rax, rax
0x18005b4bb  jnz     short loc_18005B4C4
0x18005b4bd  mov     rsi, [rbx+0A8h]
0x18005b4c4  call    cs:__imp_GetCurrentThreadId
0x18005b4ca  mov     r8d, 1; fAttach
0x18005b4d0  mov     ecx, ebp; idAttach
0x18005b4d2  mov     edx, eax; idAttachTo
0x18005b4d4  call    cs:__imp_AttachThreadInput
0x18005b4da  mov     rcx, rsi; hWnd
0x18005b4dd  call    cs:__imp_SetActiveWindow
0x18005b4e3  jmp     short loc_18005B4FC
0x18005b4e5  call    cs:__imp_GetCurrentThreadId
0x18005b4eb  xor     r8d, r8d; fAttach
0x18005b4ee  mov     ecx, ebp; idAttach
0x18005b4f0  mov     edx, eax; idAttachTo
0x18005b4f2  call    cs:__imp_AttachThreadInput
0x18005b4f8  test    eax, eax
0x18005b4fa  jnz     short loc_18005B4E5
0x18005b4fc  test    r14b, r14b
0x18005b4ff  jnz     short loc_18005B508
0x18005b501  mov     [rbx+0F9h], dil
0x18005b508  xor     eax, eax
0x18005b50a  add     rsp, 20h
0x18005b50e  pop     r14
0x18005b510  pop     rdi
0x18005b511  pop     rsi
0x18005b512  pop     rbp
0x18005b513  pop     rbx
0x18005b514  retn
```
