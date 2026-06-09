# __acrt_WideCharToMultiByte

- ea: `0x140007bc4`
- end: `0x140007ca2`
- name: `__acrt_WideCharToMultiByte`
- size: `222`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ade8`
- `0x14000b67c`
- `0x14000bd34`

## callees

- `0x140007bc4`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140007c9b`

## pseudocode

```c
int __fastcall _acrt_WideCharToMultiByte(
        UINT a1,
        int a2,
        const WCHAR *a3,
        int a4,
        CHAR *a5,
        int a6,
        const CHAR *a7,
        BOOL *a8)
{
  bool v10; // zf
  bool v11; // zf
  UINT v12; // eax
  DWORD v13; // edx
  BOOL *v15; // r8

  if ( a1 > 0xDEAC )
  {
    if ( a1 == 57005 || a1 == 57006 || a1 == 57007 || a1 == 57008 || a1 == 57009 || a1 == 57010 || a1 == 57011 )
      goto LABEL_25;
    v12 = a1 - 65000;
    v11 = a1 == 65000;
    goto LABEL_21;
  }
  if ( a1 == 57004 )
    goto LABEL_25;
  if ( a1 > 0xC433 )
  {
    if ( a1 == 50229 || a1 == 54936 )
      goto LABEL_25;
    v12 = a1 - 57002;
    v11 = a1 == 57002;
LABEL_21:
    if ( !v11 )
    {
      v10 = v12 == 1;
      goto LABEL_23;
    }
LABEL_25:
    v13 = 0;
    goto LABEL_26;
  }
  if ( a1 == 50227 || a1 == 42 || a1 == 50220 || a1 == 50221 || a1 == 50222 )
    goto LABEL_25;
  v10 = a1 == 50225;
LABEL_23:
  if ( v10 )
    goto LABEL_25;
  v13 = a2 & 0xFFFFFF7F;
LABEL_26:
  v15 = a8;
  if ( a1 - 65000 <= 1 )
  {
    v15 = 0;
    a7 = 0;
    if ( a8 )
      *a8 = 0;
  }
  return WideCharToMultiByte(a1, v13, a3, a4, a5, a6, a7, v15);
}

```

## disassembly

```asm
0x140007bc4  mov     [rsp+arg_0], rbx
0x140007bc9  push    rdi
0x140007bca  lea     eax, [rcx-0FDE8h]
0x140007bd0  mov     r11d, r9d
0x140007bd3  cmp     eax, 1
0x140007bd6  mov     rbx, r8
0x140007bd9  mov     eax, 0DEACh
0x140007bde  setbe   r10b
0x140007be2  xor     edi, edi
0x140007be4  cmp     ecx, eax
0x140007be6  ja      short loc_140007C29
0x140007be8  jz      short loc_140007C62
0x140007bea  mov     eax, 0C433h
0x140007bef  cmp     ecx, eax
0x140007bf1  ja      short loc_140007C12
0x140007bf3  jz      short loc_140007C62
0x140007bf5  mov     eax, ecx
0x140007bf7  sub     eax, 2Ah ; '*'
0x140007bfa  jz      short loc_140007C62
0x140007bfc  sub     eax, 0C402h
0x140007c01  jz      short loc_140007C62
0x140007c03  sub     eax, 1
0x140007c06  jz      short loc_140007C62
0x140007c08  sub     eax, 1
0x140007c0b  jz      short loc_140007C62
0x140007c0d  cmp     eax, 3
0x140007c10  jmp     short loc_140007C5A
0x140007c12  mov     eax, ecx
0x140007c14  sub     eax, 0C435h
0x140007c19  jz      short loc_140007C62
0x140007c1b  sub     eax, 1263h
0x140007c20  jz      short loc_140007C62
0x140007c22  sub     eax, 812h
0x140007c27  jmp     short loc_140007C55
0x140007c29  mov     eax, ecx
0x140007c2b  sub     eax, 0DEADh
0x140007c30  jz      short loc_140007C62
0x140007c32  sub     eax, 1
0x140007c35  jz      short loc_140007C62
0x140007c37  sub     eax, 1
0x140007c3a  jz      short loc_140007C62
0x140007c3c  sub     eax, 1
0x140007c3f  jz      short loc_140007C62
0x140007c41  sub     eax, 1
0x140007c44  jz      short loc_140007C62
0x140007c46  sub     eax, 1
0x140007c49  jz      short loc_140007C62
0x140007c4b  sub     eax, 1
0x140007c4e  jz      short loc_140007C62
0x140007c50  sub     eax, 1F35h
0x140007c55  jz      short loc_140007C62
0x140007c57  cmp     eax, 1
0x140007c5a  jz      short loc_140007C62
0x140007c5c  btr     edx, 7
0x140007c60  jmp     short loc_140007C64
0x140007c62  mov     edx, edi
0x140007c64  mov     rax, [rsp+8+arg_38]
0x140007c69  test    r10b, r10b
0x140007c6c  mov     r9, [rsp+8+arg_30]
0x140007c71  mov     r8, rax
0x140007c74  cmovnz  r8, rdi
0x140007c78  cmovnz  r9, rdi
0x140007c7c  jz      short loc_140007C85
0x140007c7e  test    rax, rax
0x140007c81  jz      short loc_140007C85
0x140007c83  mov     [rax], edi
0x140007c85  mov     [rsp+8+arg_38], r8
0x140007c8a  mov     r8, rbx
0x140007c8d  mov     [rsp+8+arg_30], r9
0x140007c92  mov     r9d, r11d
0x140007c95  mov     rbx, [rsp+8+arg_0]
0x140007c9a  pop     rdi
0x140007c9b  jmp     cs:WideCharToMultiByte
```
