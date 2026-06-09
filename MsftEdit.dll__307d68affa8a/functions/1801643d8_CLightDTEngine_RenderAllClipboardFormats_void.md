# CLightDTEngine::RenderAllClipboardFormats(void)

- ea: `0x1801643d8`
- end: `0x18016448e`
- name: `?RenderAllClipboardFormats@CLightDTEngine@@QEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(CLightDTEngine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18011a5d0`

## callees

- `0x180100c98`
- `0x1801643d8`
- `0x180164494`

## import_xrefs

- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180164477`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180164477`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180164421`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180164421`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x18016442b`
- `ext-ms-win-ntuser-misc-l1-2-0!EmptyClipboard` at `0x18016442b`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801643ef`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801643ef`

## pseudocode

```c
_BOOL8 __fastcall CLightDTEngine::RenderAllClipboardFormats(CLightDTEngine *this)
{
  HWND ClipboardOwner; // rax
  HWND v3; // rdi
  BOOL v4; // edi
  HWND hWndNewOwner; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 26) )
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
  v4 = 1;
  if ( !CLightDTEngine::RenderClipboardFormat(this, stru_1802DC9E0.cfFormat)
    && !CLightDTEngine::RenderClipboardFormat(this, 0xDu)
    && !CLightDTEngine::RenderClipboardFormat(this, 8u) )
  {
    v4 = CLightDTEngine::RenderClipboardFormat(this, 1u) != 0;
  }
  CloseClipboard();
  return v4;
}

```

## disassembly

```asm
0x1801643d8  mov     [rsp+arg_8], rbx
0x1801643dd  push    rdi
0x1801643de  sub     rsp, 20h
0x1801643e2  cmp     byte ptr [rcx+1Ah], 0
0x1801643e6  mov     rbx, rcx
0x1801643e9  jz      loc_180164481
0x1801643ef  call    cs:__imp_GetClipboardOwner
0x1801643f5  mov     [rsp+28h+hWndNewOwner], 0
0x1801643fe  mov     rdi, rax
0x180164401  test    rax, rax
0x180164404  jz      short loc_180164481
0x180164406  mov     rcx, [rbx]; this
0x180164409  lea     rdx, [rsp+28h+hWndNewOwner]; HWND *
0x18016440e  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x180164413  test    eax, eax
0x180164415  jnz     short loc_180164481
0x180164417  mov     rcx, [rsp+28h+hWndNewOwner]; hWndNewOwner
0x18016441c  cmp     rdi, rcx
0x18016441f  jnz     short loc_180164481
0x180164421  call    cs:__imp_OpenClipboard
0x180164427  test    eax, eax
0x180164429  jz      short loc_180164481
0x18016442b  call    cs:__imp_EmptyClipboard
0x180164431  movzx   edx, cs:stru_1802DC9E0.cfFormat; unsigned __int64
0x180164438  mov     rcx, rbx; this
0x18016443b  mov     edi, 1
0x180164440  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x180164445  test    eax, eax
0x180164447  jnz     short loc_180164477
0x180164449  lea     edx, [rdi+0Ch]; unsigned __int64
0x18016444c  mov     rcx, rbx; this
0x18016444f  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x180164454  test    eax, eax
0x180164456  jnz     short loc_180164477
0x180164458  lea     edx, [rdi+7]; unsigned __int64
0x18016445b  mov     rcx, rbx; this
0x18016445e  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x180164463  test    eax, eax
0x180164465  jnz     short loc_180164477
0x180164467  mov     edx, edi; unsigned __int64
0x180164469  mov     rcx, rbx; this
0x18016446c  call    ?RenderClipboardFormat@CLightDTEngine@@QEAAJ_K@Z; CLightDTEngine::RenderClipboardFormat(unsigned __int64)
0x180164471  neg     eax
0x180164473  sbb     ecx, ecx
0x180164475  and     edi, ecx
0x180164477  call    cs:__imp_CloseClipboard
0x18016447d  mov     eax, edi
0x18016447f  jmp     short loc_180164483
0x180164481  xor     eax, eax
0x180164483  mov     rbx, [rsp+28h+arg_8]
0x180164488  add     rsp, 20h
0x18016448c  pop     rdi
0x18016448d  retn
```
