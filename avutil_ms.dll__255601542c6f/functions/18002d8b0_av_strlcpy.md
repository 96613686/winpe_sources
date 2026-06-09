# av_strlcpy

- ea: `0x18002d8b0`
- end: `0x18002d8f6`
- name: `av_strlcpy`
- size: `70`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cf40`
- `0x18002d7c0`
- `0x180032620`
- `0x180032bc0`
- `0x1800332ec`
- `0x180037180`
- `0x18004b170`
- `0x18004c800`

## callees

- `0x18002d8b0`
- `0x180078c1a`

## pseudocode

```c
size_t __fastcall av_strlcpy(_BYTE *a1, const char *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx

  v3 = 1;
  if ( a3 > 1 )
  {
    while ( *a2 )
    {
      *a1++ = *a2++;
      if ( ++v3 >= a3 )
        goto LABEL_4;
    }
    goto LABEL_5;
  }
LABEL_4:
  if ( v3 <= a3 )
LABEL_5:
    *a1 = 0;
  return v3 - 1 + strlen(a2);
}

```

## disassembly

```asm
0x18002d8b0  push    rbx
0x18002d8b2  sub     rsp, 20h
0x18002d8b6  mov     r9d, 1
0x18002d8bc  mov     ebx, r9d
0x18002d8bf  cmp     r9, r8
0x18002d8c2  jnb     short loc_18002D8DA
0x18002d8c4  mov     al, [rdx]
0x18002d8c6  test    al, al
0x18002d8c8  jz      short loc_18002D8DF
0x18002d8ca  mov     [rcx], al
0x18002d8cc  add     rdx, r9
0x18002d8cf  add     rcx, r9
0x18002d8d2  add     rbx, r9
0x18002d8d5  cmp     rbx, r8
0x18002d8d8  jb      short loc_18002D8C4
0x18002d8da  cmp     rbx, r8
0x18002d8dd  ja      short loc_18002D8E2
0x18002d8df  mov     byte ptr [rcx], 0
0x18002d8e2  mov     rcx, rdx; Str
0x18002d8e5  call    strlen
0x18002d8ea  dec     rbx
0x18002d8ed  add     rax, rbx
0x18002d8f0  add     rsp, 20h
0x18002d8f4  pop     rbx
0x18002d8f5  retn
```
