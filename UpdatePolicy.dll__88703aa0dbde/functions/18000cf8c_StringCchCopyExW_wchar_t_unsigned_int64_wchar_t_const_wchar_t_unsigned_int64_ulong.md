# StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)

- ea: `0x18000cf8c`
- end: `0x18000d067`
- name: `?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z`
- size: `219`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, wchar_t **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cdd4`

## callees

- `0x18000cf8c`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, wchar_t **a4)
{
  unsigned __int64 v5; // r10
  wchar_t *v6; // r11
  unsigned int v7; // edx
  const WCHAR *v8; // rcx
  wchar_t *v9; // r8
  unsigned __int64 v10; // rdx
  __int64 v11; // r9
  signed __int64 v12; // rcx
  wchar_t v13; // ax
  wchar_t *v14; // rax
  __int64 v15; // rax

  v5 = a2;
  v6 = a1;
  if ( (a1 || !a2) && a2 <= 0x7FFFFFFF )
  {
    v8 = &OutputString;
    v7 = 0;
    if ( a3 )
      v8 = a3;
    if ( v5 )
    {
      v9 = v6;
      v10 = 2147483646 - v5;
      v11 = 0;
      v12 = (char *)v8 - (char *)v6;
      do
      {
        if ( !(v10 + v5) )
          break;
        v13 = *(wchar_t *)((char *)v9 + v12);
        if ( !v13 )
          break;
        *v9 = v13;
        ++v11;
        ++v9;
        --v5;
      }
      while ( v5 );
      v14 = v9 - 1;
      v7 = v5 == 0 ? 0x8007007A : 0;
      if ( v5 )
        v14 = v9;
      *v14 = 0;
      v15 = v11 - 1;
      if ( v5 )
        v15 = v11;
      v6 += v15;
    }
    else if ( *v8 )
    {
      if ( !v6 )
        return (unsigned int)-2147024809;
      v7 = -2147024774;
    }
    if ( a4 )
      *a4 = v6;
  }
  else
  {
    v7 = -2147024809;
    if ( v5 )
      *a1 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000cf8c  mov     [rsp+arg_10], rbx
0x18000cf91  push    rdi
0x18000cf92  xor     edi, edi
0x18000cf94  mov     rbx, r9
0x18000cf97  mov     r10, rdx
0x18000cf9a  mov     r11, rcx
0x18000cf9d  test    rcx, rcx
0x18000cfa0  jnz     short loc_18000CFA7
0x18000cfa2  test    rdx, rdx
0x18000cfa5  jnz     short loc_18000CFB0
0x18000cfa7  cmp     r10, 7FFFFFFFh
0x18000cfae  jbe     short loc_18000CFC6
0x18000cfb0  mov     edx, 80070057h
0x18000cfb5  test    r10, r10
0x18000cfb8  jz      loc_18000D05E
0x18000cfbe  mov     [rcx], di
0x18000cfc1  jmp     loc_18000D05E
0x18000cfc6  test    r8, r8
0x18000cfc9  lea     rcx, OutputString
0x18000cfd0  mov     edx, edi
0x18000cfd2  cmovnz  rcx, r8
0x18000cfd6  test    r10, r10
0x18000cfd9  jnz     short loc_18000CFF3
0x18000cfdb  cmp     [rcx], di
0x18000cfde  jz      short loc_18000D056
0x18000cfe0  test    r11, r11
0x18000cfe3  jnz     short loc_18000CFEC
0x18000cfe5  mov     edx, 80070057h
0x18000cfea  jmp     short loc_18000D05E
0x18000cfec  mov     edx, 8007007Ah
0x18000cff1  jmp     short loc_18000D056
0x18000cff3  mov     edx, 7FFFFFFEh
0x18000cff8  mov     r8, r11
0x18000cffb  sub     rdx, r10
0x18000cffe  mov     r9, rdi
0x18000d001  sub     rcx, r11
0x18000d004  lea     rax, [rdx+r10]
0x18000d008  test    rax, rax
0x18000d00b  jz      short loc_18000D028
0x18000d00d  movzx   eax, word ptr [rcx+r8]
0x18000d012  test    ax, ax
0x18000d015  jz      short loc_18000D028
0x18000d017  mov     [r8], ax
0x18000d01b  inc     r9
0x18000d01e  add     r8, 2
0x18000d022  sub     r10, 1
0x18000d026  jnz     short loc_18000D004
0x18000d028  mov     rax, r10
0x18000d02b  mov     edx, 8007007Ah
0x18000d030  neg     rax
0x18000d033  lea     rax, [r8-2]
0x18000d037  sbb     ecx, ecx
0x18000d039  not     ecx
0x18000d03b  and     edx, ecx
0x18000d03d  test    r10, r10
0x18000d040  cmovnz  rax, r8
0x18000d044  mov     [rax], di
0x18000d047  lea     rax, [r9-1]
0x18000d04b  cmovnz  rax, r9
0x18000d04f  lea     rcx, [r11+rax*2]
0x18000d053  mov     r11, rcx
0x18000d056  test    rbx, rbx
0x18000d059  jz      short loc_18000D05E
0x18000d05b  mov     [rbx], r11
0x18000d05e  mov     rbx, [rsp+8+arg_10]
0x18000d063  mov     eax, edx
0x18000d065  pop     rdi
0x18000d066  retn
```
