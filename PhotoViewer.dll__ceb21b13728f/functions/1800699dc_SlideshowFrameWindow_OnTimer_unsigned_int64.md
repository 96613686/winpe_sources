# SlideshowFrameWindow::OnTimer(unsigned __int64)

- ea: `0x1800699dc`
- end: `0x180069a8d`
- name: `?OnTimer@SlideshowFrameWindow@@AEAAX_K@Z`
- size: `177`
- prototype: `void __fastcall(SlideshowFrameWindow *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028c6c`

## callees

- `0x1800699dc`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180069a16`
- `KERNEL32!GetTickCount` at `0x180069a16`
- `USER32!SystemParametersInfoW` at `0x180069a69`
- `USER32!SystemParametersInfoW` at `0x180069a7c`
- `USER32!SystemParametersInfoW` at `0x180069a69`
- `USER32!SystemParametersInfoW` at `0x180069a7c`
- `USER32!IsWindow` at `0x1800699f0`
- `USER32!IsWindow` at `0x1800699f0`

## pseudocode

```c
void __fastcall SlideshowFrameWindow::OnTimer(SlideshowFrameWindow *this, __int64 a2)
{
  void (*v4)(void); // rax
  UINT pvParam; // [rsp+30h] [rbp+8h] BYREF

  if ( IsWindow(*((HWND *)this + 1)) )
  {
    switch ( a2 )
    {
      case 2LL:
        if ( *((_BYTE *)this + 380) && !*((_BYTE *)this + 400) && GetTickCount() - *((_DWORD *)this + 98) > 0x9C4 )
        {
          v4 = *(void (**)(void))(*((_QWORD *)this + 13) + 72LL);
LABEL_9:
          v4();
        }
        break;
      case 1LL:
        v4 = *(void (**)(void))(*((_QWORD *)this + 15) + 56LL);
        goto LABEL_9;
      case 3LL:
        pvParam = 600;
        SystemParametersInfoW(0xEu, 0, &pvParam, 0);
        SystemParametersInfoW(0xFu, pvParam, 0, 0);
        break;
    }
  }
}

```

## disassembly

```asm
0x1800699dc  mov     [rsp+arg_8], rbx
0x1800699e1  push    rdi
0x1800699e2  sub     rsp, 20h
0x1800699e6  mov     rbx, rcx
0x1800699e9  mov     rdi, rdx
0x1800699ec  mov     rcx, [rcx+8]; hWnd
0x1800699f0  call    cs:__imp_IsWindow
0x1800699f6  test    eax, eax
0x1800699f8  jz      loc_180069A82
0x1800699fe  cmp     rdi, 2
0x180069a02  jnz     short loc_180069A36
0x180069a04  cmp     byte ptr [rbx+17Ch], 0
0x180069a0b  jz      short loc_180069A82
0x180069a0d  cmp     byte ptr [rbx+190h], 0
0x180069a14  jnz     short loc_180069A82
0x180069a16  call    cs:__imp_GetTickCount
0x180069a1c  sub     eax, [rbx+188h]
0x180069a22  cmp     eax, 9C4h
0x180069a27  jbe     short loc_180069A82
0x180069a29  lea     rcx, [rbx+68h]
0x180069a2d  mov     rax, [rcx]
0x180069a30  mov     rax, [rax+48h]
0x180069a34  jmp     short loc_180069A47
0x180069a36  cmp     rdi, 1
0x180069a3a  jnz     short loc_180069A4E
0x180069a3c  lea     rcx, [rbx+78h]
0x180069a40  mov     rax, [rcx]
0x180069a43  mov     rax, [rax+38h]
0x180069a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a4c  jmp     short loc_180069A82
0x180069a4e  cmp     rdi, 3
0x180069a52  jnz     short loc_180069A82
0x180069a54  xor     r9d, r9d; fWinIni
0x180069a57  mov     [rsp+28h+pvParam], 258h
0x180069a5f  lea     r8, [rsp+28h+pvParam]; pvParam
0x180069a64  xor     edx, edx; uiParam
0x180069a66  lea     ecx, [rdi+0Bh]; uiAction
0x180069a69  call    cs:__imp_SystemParametersInfoW
0x180069a6f  mov     edx, [rsp+28h+pvParam]; uiParam
0x180069a73  lea     ecx, [rdi+0Ch]; uiAction
0x180069a76  xor     r9d, r9d; fWinIni
0x180069a79  xor     r8d, r8d; pvParam
0x180069a7c  call    cs:__imp_SystemParametersInfoW
0x180069a82  mov     rbx, [rsp+28h+arg_8]
0x180069a87  add     rsp, 20h
0x180069a8b  pop     rdi
0x180069a8c  retn
```
