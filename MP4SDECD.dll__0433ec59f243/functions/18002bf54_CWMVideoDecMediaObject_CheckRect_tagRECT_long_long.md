# CWMVideoDecMediaObject::CheckRect(tagRECT *,long,long)

- ea: `0x18002bf54`
- end: `0x18002bfa5`
- name: `?CheckRect@CWMVideoDecMediaObject@@AEAAJPEAUtagRECT@@JJ@Z`
- size: `81`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, struct tagRECT *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bc14`

## callees

- `0x18002bf54`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002bf6f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x18002bf6f`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::CheckRect(CWMVideoDecMediaObject *this, struct tagRECT *a2, int a3, int a4)
{
  if ( IsRectEmpty(a2) || a3 == a2->right && !a2->left && a4 == a2->bottom && !a2->top )
    return 0;
  else
    return 2147746309LL;
}

```

## disassembly

```asm
0x18002bf54  mov     [rsp+arg_0], rbx
0x18002bf59  mov     [rsp+arg_8], rsi
0x18002bf5e  push    rdi
0x18002bf5f  sub     rsp, 20h
0x18002bf63  mov     rcx, rdx; lprc
0x18002bf66  mov     edi, r9d
0x18002bf69  mov     esi, r8d
0x18002bf6c  mov     rbx, rdx
0x18002bf6f  call    cs:__imp_IsRectEmpty
0x18002bf75  test    eax, eax
0x18002bf77  jnz     short loc_18002BF93
0x18002bf79  cmp     esi, [rbx+8]
0x18002bf7c  jnz     short loc_18002BF8C
0x18002bf7e  cmp     [rbx], eax
0x18002bf80  jnz     short loc_18002BF8C
0x18002bf82  cmp     edi, [rbx+0Ch]
0x18002bf85  jnz     short loc_18002BF8C
0x18002bf87  cmp     [rbx+4], eax
0x18002bf8a  jz      short loc_18002BF93
0x18002bf8c  mov     eax, 80040205h
0x18002bf91  jmp     short loc_18002BF95
0x18002bf93  xor     eax, eax
0x18002bf95  mov     rbx, [rsp+28h+arg_0]
0x18002bf9a  mov     rsi, [rsp+28h+arg_8]
0x18002bf9f  add     rsp, 20h
0x18002bfa3  pop     rdi
0x18002bfa4  retn
```
