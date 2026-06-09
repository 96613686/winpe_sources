# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x140008e88`
- end: `0x140008f9f`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009080`

## callees

- `0x140001f5c`
- `0x140008e88`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v5; // ebx
  __int64 *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r11
  unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  bool v14; // cf

  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v5 = -2147024809;
LABEL_7:
    *a1 = 0;
    return v5;
  }
  if ( a4 < 0x7FFFFFFF )
  {
    v6 = &qword_14000DB08;
    if ( a3 )
      v6 = (__int64 *)a3;
    v7 = a4 & -(__int64)(a3 != 0);
    if ( a2 )
    {
      v8 = a2;
      v9 = a1;
      v10 = 0;
      do
      {
        if ( !v7 )
          break;
        if ( !*(_WORD *)v6 )
          break;
        *v9 = *(_WORD *)v6;
        v6 = (__int64 *)((char *)v6 + 2);
        ++v9;
        --v7;
        ++v10;
        --v8;
      }
      while ( v8 );
      v11 = v10 - 1;
      v12 = v9 - 1;
      if ( v8 )
      {
        v11 = v10;
        v12 = v9;
      }
      *v12 = 0;
      v5 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
      {
        v14 = a2 == v11;
        v13 = a2 - v11;
        if ( !v14 && v13 != 1 && (unsigned __int64)(2 * v13) > 2 )
          memset_0(&a1[v11 + 1], 0, 2 * v13 - 2);
      }
    }
    else
    {
      v5 = 0;
      if ( v7 && *(_WORD *)v6 )
        return a1 != 0 ? -2147024774 : -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( a2 )
      goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x140008e88  mov     [rsp+arg_10], rbx
0x140008e8d  push    rdi
0x140008e8e  sub     rsp, 20h
0x140008e92  xor     edi, edi
0x140008e94  mov     r10, rcx
0x140008e97  test    rcx, rcx
0x140008e9a  jnz     short loc_140008EA1
0x140008e9c  test    rdx, rdx
0x140008e9f  jnz     short loc_140008EAB
0x140008ea1  mov     eax, 7FFFFFFFh
0x140008ea6  cmp     rdx, rax
0x140008ea9  jbe     short loc_140008EB2
0x140008eab  mov     ebx, 80070057h
0x140008eb0  jmp     short loc_140008EC5
0x140008eb2  cmp     r9, rax
0x140008eb5  jb      short loc_140008ECD
0x140008eb7  mov     ebx, 80070057h
0x140008ebc  test    rdx, rdx
0x140008ebf  jz      loc_140008F92
0x140008ec5  mov     [rcx], di
0x140008ec8  jmp     loc_140008F92
0x140008ecd  test    r8, r8
0x140008ed0  lea     rcx, qword_14000DB08
0x140008ed7  cmovnz  rcx, r8
0x140008edb  neg     r8
0x140008ede  sbb     rax, rax
0x140008ee1  and     rax, r9
0x140008ee4  test    rdx, rdx
0x140008ee7  jnz     short loc_140008F11
0x140008ee9  mov     ebx, edi
0x140008eeb  test    rax, rax
0x140008eee  jz      loc_140008F92
0x140008ef4  cmp     [rcx], di
0x140008ef7  jz      loc_140008F92
0x140008efd  neg     r10
0x140008f00  mov     ebx, 80070057h
0x140008f05  sbb     eax, eax
0x140008f07  and     eax, 23h
0x140008f0a  add     ebx, eax
0x140008f0c  jmp     loc_140008F92
0x140008f11  mov     r8, rdx
0x140008f14  mov     r9, r10
0x140008f17  mov     rbx, rdi
0x140008f1a  test    rax, rax
0x140008f1d  jz      short loc_140008F41
0x140008f1f  movzx   r11d, word ptr [rcx]
0x140008f23  test    r11w, r11w
0x140008f27  jz      short loc_140008F41
0x140008f29  mov     [r9], r11w
0x140008f2d  add     rcx, 2
0x140008f31  add     r9, 2
0x140008f35  dec     rax
0x140008f38  inc     rbx
0x140008f3b  sub     r8, 1
0x140008f3f  jnz     short loc_140008F1A
0x140008f41  test    r8, r8
0x140008f44  lea     r11, [rbx-1]
0x140008f48  lea     rcx, [r9-2]
0x140008f4c  mov     rax, r8
0x140008f4f  cmovnz  r11, rbx
0x140008f53  cmovnz  rcx, r9
0x140008f57  neg     rax
0x140008f5a  sbb     ebx, ebx
0x140008f5c  not     ebx
0x140008f5e  mov     [rcx], di
0x140008f61  and     ebx, 8007007Ah
0x140008f67  test    r8, r8
0x140008f6a  jz      short loc_140008F92
0x140008f6c  sub     rdx, r11
0x140008f6f  cmp     rdx, 1
0x140008f73  jbe     short loc_140008F92
0x140008f75  lea     r8, [rdx+rdx]
0x140008f79  cmp     r8, 2
0x140008f7d  jbe     short loc_140008F92
0x140008f7f  add     r10, 2
0x140008f83  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x140008f87  xor     edx, edx; Val
0x140008f89  lea     rcx, [r10+r11*2]; void *
0x140008f8d  call    memset_0
0x140008f92  mov     eax, ebx
0x140008f94  mov     rbx, [rsp+28h+arg_10]
0x140008f99  add     rsp, 20h
0x140008f9d  pop     rdi
0x140008f9e  retn
```
