# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800136c4`
- end: `0x18001373a`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091c0`
- `0x180025a5c`
- `0x180026410`

## callees

- `0x1800136c4`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(char *a1, __int64 a2, char *a3)
{
  int v3; // r9d
  __int64 v4; // r10
  signed __int64 v5; // r8
  unsigned __int16 v6; // ax

  v3 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    v3 = -2147024809;
  if ( v3 >= 0 )
  {
    v3 = 0;
    if ( !a2 )
      goto LABEL_10;
    v4 = 2147483646 - a2;
    v5 = a3 - a1;
    do
    {
      if ( !(v4 + a2) )
        break;
      v6 = *(_WORD *)&a1[v5];
      if ( !v6 )
        break;
      *(_WORD *)a1 = v6;
      a1 += 2;
      --a2;
    }
    while ( a2 );
    if ( !a2 )
    {
LABEL_10:
      a1 -= 2;
      v3 = -2147024774;
    }
    goto LABEL_12;
  }
  if ( a2 )
LABEL_12:
    *(_WORD *)a1 = 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800136c4  mov     [rsp+arg_0], rbx
0x1800136c9  xor     ebx, ebx
0x1800136cb  lea     rax, [rdx-1]
0x1800136cf  mov     r10d, 7FFFFFFEh
0x1800136d5  mov     r9d, ebx
0x1800136d8  cmp     rax, r10
0x1800136db  mov     r11d, 80070057h
0x1800136e1  cmova   r9d, r11d
0x1800136e5  test    r9d, r9d
0x1800136e8  js      short loc_180013729
0x1800136ea  mov     r9d, ebx
0x1800136ed  test    rdx, rdx
0x1800136f0  jz      short loc_18001371D
0x1800136f2  sub     r10, rdx
0x1800136f5  sub     r8, rcx
0x1800136f8  lea     rax, [r10+rdx]
0x1800136fc  test    rax, rax
0x1800136ff  jz      short loc_180013718
0x180013701  movzx   eax, word ptr [r8+rcx]
0x180013706  test    ax, ax
0x180013709  jz      short loc_180013718
0x18001370b  mov     [rcx], ax
0x18001370e  add     rcx, 2
0x180013712  sub     rdx, 1
0x180013716  jnz     short loc_1800136F8
0x180013718  test    rdx, rdx
0x18001371b  jnz     short loc_18001372E
0x18001371d  sub     rcx, 2
0x180013721  mov     r9d, 8007007Ah
0x180013727  jmp     short loc_18001372E
0x180013729  test    rdx, rdx
0x18001372c  jz      short loc_180013731
0x18001372e  mov     [rcx], bx
0x180013731  mov     rbx, [rsp+arg_0]
0x180013736  mov     eax, r9d
0x180013739  retn
```
