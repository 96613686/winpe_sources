# CLightDTEngine::RenderAllClipboardFormats(void)

- ea: `0x18006d420`
- end: `0x18006d4d4`
- name: `?RenderAllClipboardFormats@CLightDTEngine@@QEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002cfd0`

## callees

- `0x18003ffa8`
- `0x18006d420`
- `0x18006d4dc`

## import_xrefs

- `USER32!OpenClipboard` at `0x18006d469`
- `USER32!OpenClipboard` at `0x18006d469`
- `USER32!EmptyClipboard` at `0x18006d473`
- `USER32!EmptyClipboard` at `0x18006d473`
- `USER32!CloseClipboard` at `0x18006d4bd`
- `USER32!CloseClipboard` at `0x18006d4bd`
- `USER32!GetClipboardOwner` at `0x18006d437`
- `USER32!GetClipboardOwner` at `0x18006d437`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::RenderAllClipboardFormats(CLightDTEngine *this)
{
  HWND ClipboardOwner; // rax
  HWND v3; // rbx
  unsigned int v4; // ebx
  HWND hWndNewOwner; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 25) )
    return 0;
  ClipboardOwner = GetClipboardOwner();
  hWndNewOwner = 0;
  v3 = ClipboardOwner;
  if ( !ClipboardOwner
    || (unsigned int)CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner)
    || v3 != hWndNewOwner
    || !OpenClipboard(hWndNewOwner) )
  {
    return 0;
  }
  EmptyClipboard();
  v4 = CLightDTEngine::RenderClipboardFormat(this, (unsigned __int16)xmmword_1800A30F0);
  if ( !v4 )
  {
    v4 = CLightDTEngine::RenderClipboardFormat(this, 0xDu);
    if ( !v4 )
    {
      v4 = CLightDTEngine::RenderClipboardFormat(this, 8u);
      if ( !v4 )
        v4 = CLightDTEngine::RenderClipboardFormat(this, 1u);
    }
  }
  CloseClipboard();
  return v4;
}

```

## disassembly

```asm
0x18006d420  mov     [rsp+arg_8], rbx
0x18006d425  push    rdi
0x18006d426  sub     rsp, 20h
0x18006d42a  cmp     byte ptr [rcx+19h], 0
0x18006d42e  mov     rdi, rcx
0x18006d431  jz      loc_18006D4C7
0x18006d437  call    cs:__imp_GetClipboardOwner
0x18006d43d  mov     [rsp+28h+hWndNewOwner], 0
0x18006d446  mov     rbx, rax
0x18006d449  test    rax, rax
0x18006d44c  jz      short loc_18006D4C7
0x18006d44e  mov     rcx, [rdi]; this
0x18006d451  lea     rdx, [rsp+28h+hWndNewOwner]; HWND *
0x18006d456  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18006d45b  test    eax, eax
0x18006d45d  jnz     short loc_18006D4C7
0x18006d45f  mov     rcx, [rsp+28h+hWndNewOwner]; hWndNewOwner
0x18006d464  cmp     rbx, rcx
0x18006d467  jnz     short loc_18006D4C7
0x18006d469  call    cs:__imp_OpenClipboard
0x18006d46f  test    eax, eax
0x18006d471  jz      short loc_18006D4C7
0x18006d473  call    cs:__imp_EmptyClipboard
0x18006d479  movzx   edx, word ptr cs:xmmword_1800A30F0; unsigned __int64
0x18006d480  mov     rcx, rdi; this
0x18006d483  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006d488  mov     ebx, eax
0x18006d48a  test    eax, eax
0x18006d48c  jnz     short loc_18006D4BD
0x18006d48e  lea     edx, [rax+0Dh]; unsigned __int64
0x18006d491  mov     rcx, rdi; this
0x18006d494  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006d499  mov     ebx, eax
0x18006d49b  test    eax, eax
0x18006d49d  jnz     short loc_18006D4BD
0x18006d49f  lea     edx, [rax+8]; unsigned __int64
0x18006d4a2  mov     rcx, rdi; this
0x18006d4a5  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006d4aa  mov     ebx, eax
0x18006d4ac  test    eax, eax
0x18006d4ae  jnz     short loc_18006D4BD
0x18006d4b0  lea     edx, [rax+1]; unsigned __int64
0x18006d4b3  mov     rcx, rdi; this
0x18006d4b6  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x18006d4bb  mov     ebx, eax
0x18006d4bd  call    cs:__imp_CloseClipboard
0x18006d4c3  mov     eax, ebx
0x18006d4c5  jmp     short loc_18006D4C9
0x18006d4c7  xor     eax, eax
0x18006d4c9  mov     rbx, [rsp+28h+arg_8]
0x18006d4ce  add     rsp, 20h
0x18006d4d2  pop     rdi
0x18006d4d3  retn
```
