# CSyncBasePropertyPage::_CreateBoldFont(void)

- ea: `0x18004c214`
- end: `0x18004c2c1`
- name: `?_CreateBoldFont@CSyncBasePropertyPage@@AEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(HWND *this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18003c780`
- `0x18003d5d0`
- `0x18003e270`
- `0x18004bfd0`

## callees

- `0x180012e54`
- `0x18004c214`
- `0x18005292a`
- `0x180052950`

## import_xrefs

- `USER32!SendMessageW` at `0x18004c244`
- `USER32!SendMessageW` at `0x18004c244`
- `GDI32!CreateFontIndirectW` at `0x18004c288`
- `GDI32!CreateFontIndirectW` at `0x18004c288`
- `GDI32!GetObjectW` at `0x18004c26f`
- `GDI32!GetObjectW` at `0x18004c26f`

## pseudocode

```c
__int64 __fastcall CSyncBasePropertyPage::_CreateBoldFont(HWND *this)
{
  void *v2; // rbx
  unsigned int v3; // ebx
  HFONT v4; // rax
  LOGFONTW pv; // [rsp+20h] [rbp-78h] BYREF

  v2 = (void *)SendMessageW(this[1], 0x31u, 0, 0);
  if ( !v2 )
    return (unsigned int)ResultFromKnownLastError();
  memset_0(&pv, 0, sizeof(pv));
  if ( !GetObjectW(v2, 92, &pv) )
    return (unsigned int)ResultFromKnownLastError();
  pv.lfWeight = 700;
  v3 = 0;
  v4 = CreateFontIndirectW(&pv);
  this[2] = (HWND)v4;
  if ( !v4 )
    return (unsigned int)ResultFromKnownLastError();
  return v3;
}

```

## disassembly

```asm
0x18004c214  mov     [rsp+arg_8], rbx
0x18004c219  push    rdi
0x18004c21a  sub     rsp, 90h
0x18004c221  mov     rax, cs:__security_cookie
0x18004c228  xor     rax, rsp
0x18004c22b  mov     [rsp+98h+var_18], rax
0x18004c233  xor     r9d, r9d; lParam
0x18004c236  mov     rdi, rcx
0x18004c239  mov     rcx, [rcx+8]; hWnd
0x18004c23d  xor     r8d, r8d; wParam
0x18004c240  lea     edx, [r9+31h]; Msg
0x18004c244  call    cs:__imp_SendMessageW
0x18004c24a  mov     rbx, rax
0x18004c24d  test    rax, rax
0x18004c250  jz      short loc_18004C297
0x18004c252  xor     edx, edx; Val
0x18004c254  lea     rcx, [rsp+98h+pv]; void *
0x18004c259  lea     r8d, [rdx+5Ch]; Size
0x18004c25d  call    memset_0
0x18004c262  lea     r8, [rsp+98h+pv]; pv
0x18004c267  mov     edx, 5Ch ; '\'; c
0x18004c26c  mov     rcx, rbx; h
0x18004c26f  call    cs:__imp_GetObjectW
0x18004c275  test    eax, eax
0x18004c277  jz      short loc_18004C297
0x18004c279  lea     rcx, [rsp+98h+pv]; lplf
0x18004c27e  mov     [rsp+98h+var_68], 2BCh
0x18004c286  xor     ebx, ebx
0x18004c288  call    cs:__imp_CreateFontIndirectW
0x18004c28e  mov     [rdi+10h], rax
0x18004c292  test    rax, rax
0x18004c295  jnz     short loc_18004C29E
0x18004c297  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004c29c  mov     ebx, eax
0x18004c29e  mov     eax, ebx
0x18004c2a0  mov     rcx, [rsp+98h+var_18]
0x18004c2a8  xor     rcx, rsp; StackCookie
0x18004c2ab  call    __security_check_cookie
0x18004c2b0  mov     rbx, [rsp+98h+arg_8]
0x18004c2b8  add     rsp, 90h
0x18004c2bf  pop     rdi
0x18004c2c0  retn
```
