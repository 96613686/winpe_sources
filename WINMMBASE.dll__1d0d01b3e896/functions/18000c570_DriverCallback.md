# DriverCallback

- ea: `0x18000c570`
- end: `0x18000c698`
- name: `DriverCallback`
- size: `296`
- prototype: `BOOL __stdcall(DWORD_PTR dwCallback, DWORD dwFlags, HDRVR hDevice, DWORD dwMsg, DWORD_PTR dwUser, DWORD_PTR dwParam1, DWORD_PTR dwParam2)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180017990`
- `0x180017b20`
- `0x180017d30`
- `0x1800183c0`
- `0x18001a0b0`
- `0x18001f238`
- `0x18001f62c`

## callees

- `0x180007420`
- `0x18000c570`
- `0x180011690`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c5e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c5e8`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageA` at `0x18000c61f`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18000c635`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18000c635`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x18000c659`

## pseudocode

```c
BOOL __stdcall DriverCallback(
        DWORD_PTR dwCallback,
        DWORD dwFlags,
        HDRVR hDevice,
        DWORD dwMsg,
        DWORD_PTR dwUser,
        DWORD_PTR dwParam1,
        DWORD_PTR dwParam2)
{
  char v9; // bl
  int v11; // ebx
  int v13; // ebx
  int v14; // ebx
  HMIDIOUT v15; // rcx
  MMRESULT v16; // eax

  v9 = dwFlags;
  if ( dwMsg == 963 )
  {
    v15 = (HMIDIOUT)*((_QWORD *)hDevice + 4);
    if ( v15 )
    {
      v16 = midiOutShortMsg(v15, dwParam1);
      if ( v16 == 71 )
        return 0;
      if ( v16 == 5 )
        *((_QWORD *)hDevice + 4) = 0;
    }
  }
  if ( !dwCallback )
    return 0;
  v11 = v9 & 7;
  if ( v11 == 3 )
  {
    ((void (__fastcall *)(HDRVR, _QWORD, DWORD_PTR, DWORD_PTR, DWORD_PTR))dwCallback)(
      hDevice,
      dwMsg,
      dwUser,
      dwParam1,
      dwParam2);
    return 1;
  }
  v13 = v11 - 1;
  if ( !v13 )
    return PostMessageA((HWND)dwCallback, dwMsg, (WPARAM)hDevice, dwParam1);
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 == 3 )
    {
      SetEvent((HANDLE)dwCallback);
      return 1;
    }
    return 0;
  }
  PostThreadMessageA(dwCallback, dwMsg, (WPARAM)hDevice, dwParam1);
  if ( !(unsigned __int8)IsPostThreadMessageWPresent() )
    return 0;
  return PostThreadMessageA(dwCallback, 0x400u, 0, 0);
}

```

## disassembly

```asm
0x18000c570  push    rbx
0x18000c572  push    rbp
0x18000c573  push    rsi
0x18000c574  push    rdi
0x18000c575  sub     rsp, 38h
0x18000c579  mov     esi, r9d
0x18000c57c  mov     rbp, r8
0x18000c57f  mov     ebx, edx
0x18000c581  mov     rdi, rcx
0x18000c584  cmp     r9d, 3C3h
0x18000c58b  jz      loc_18000C660
0x18000c591  test    rdi, rdi
0x18000c594  jz      short loc_18000C5FC
0x18000c596  and     ebx, 7
0x18000c599  cmp     ebx, 3
0x18000c59c  jnz     short loc_18000C5D6
0x18000c59e  mov     rax, [rsp+58h+dwParam2]
0x18000c5a6  mov     edx, esi
0x18000c5a8  mov     r9, [rsp+58h+dwParam1]
0x18000c5b0  mov     rcx, rbp
0x18000c5b3  mov     r8, [rsp+58h+dwUser]
0x18000c5bb  mov     [rsp+58h+var_38], rax
0x18000c5c0  mov     rax, rdi
0x18000c5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5c8  mov     eax, 1
0x18000c5cd  add     rsp, 38h
0x18000c5d1  pop     rdi
0x18000c5d2  pop     rsi
0x18000c5d3  pop     rbp
0x18000c5d4  pop     rbx
0x18000c5d5  retn
0x18000c5d6  sub     ebx, 1
0x18000c5d9  jz      short loc_18000C607
0x18000c5db  sub     ebx, 1
0x18000c5de  jz      short loc_18000C626
0x18000c5e0  cmp     ebx, 3
0x18000c5e3  jnz     short loc_18000C5FC
0x18000c5e5  mov     rcx, rdi; hEvent
0x18000c5e8  call    cs:__imp_SetEvent
0x18000c5ee  mov     eax, 1
0x18000c5f3  add     rsp, 38h
0x18000c5f7  pop     rdi
0x18000c5f8  pop     rsi
0x18000c5f9  pop     rbp
0x18000c5fa  pop     rbx
0x18000c5fb  retn
0x18000c5fc  xor     eax, eax
0x18000c5fe  add     rsp, 38h
0x18000c602  pop     rdi
0x18000c603  pop     rsi
0x18000c604  pop     rbp
0x18000c605  pop     rbx
0x18000c606  retn
0x18000c607  mov     r9, [rsp+58h+dwParam1]
0x18000c60f  mov     r8, rbp
0x18000c612  mov     edx, esi
0x18000c614  mov     rcx, rdi
0x18000c617  add     rsp, 38h
0x18000c61b  pop     rdi
0x18000c61c  pop     rsi
0x18000c61d  pop     rbp
0x18000c61e  pop     rbx
0x18000c61f  jmp     cs:__imp_PostMessageA
0x18000c626  mov     r9, [rsp+58h+dwParam1]; lParam
0x18000c62e  mov     r8, rbp; wParam
0x18000c631  mov     edx, esi; Msg
0x18000c633  mov     ecx, edi; idThread
0x18000c635  call    cs:__imp_PostThreadMessageA
0x18000c63b  call    IsPostThreadMessageWPresent
0x18000c640  test    al, al
0x18000c642  jz      short loc_18000C5FC
0x18000c644  xor     r9d, r9d
0x18000c647  xor     r8d, r8d
0x18000c64a  mov     edx, 400h
0x18000c64f  mov     ecx, edi
0x18000c651  add     rsp, 38h
0x18000c655  pop     rdi
0x18000c656  pop     rsi
0x18000c657  pop     rbp
0x18000c658  pop     rbx
0x18000c659  jmp     cs:__imp_PostThreadMessageA
0x18000c660  mov     rcx, [r8+20h]; hmo
0x18000c664  test    rcx, rcx
0x18000c667  jz      loc_18000C591
0x18000c66d  mov     edx, dword ptr [rsp+58h+dwParam1]; dwMsg
0x18000c674  call    midiOutShortMsg
0x18000c679  cmp     eax, 47h ; 'G'
0x18000c67c  jz      loc_18000C5FC
0x18000c682  cmp     eax, 5
0x18000c685  jnz     loc_18000C591
0x18000c68b  mov     qword ptr [rbp+20h], 0
0x18000c693  jmp     loc_18000C591
```
