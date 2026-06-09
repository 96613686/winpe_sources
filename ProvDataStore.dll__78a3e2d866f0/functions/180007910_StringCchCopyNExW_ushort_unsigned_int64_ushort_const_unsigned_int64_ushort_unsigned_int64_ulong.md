# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180007910`
- end: `0x180007a27`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d94`

## callees

- `0x180007910`
- `0x180010f4e`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v5; // ebx
  int *v6; // rcx
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
    v6 = &dword_18001490C;
    if ( a3 )
      v6 = (int *)a3;
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
        v6 = (int *)((char *)v6 + 2);
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
0x180007910  mov     [rsp+arg_0], rbx
0x180007915  push    rdi
0x180007916  sub     rsp, 20h
0x18000791a  xor     edi, edi
0x18000791c  mov     r10, rcx
0x18000791f  test    rcx, rcx
0x180007922  jnz     short loc_180007929
0x180007924  test    rdx, rdx
0x180007927  jnz     short loc_180007933
0x180007929  mov     eax, 7FFFFFFFh
0x18000792e  cmp     rdx, rax
0x180007931  jbe     short loc_18000793A
0x180007933  mov     ebx, 80070057h
0x180007938  jmp     short loc_18000794D
0x18000793a  cmp     r9, rax
0x18000793d  jb      short loc_180007955
0x18000793f  mov     ebx, 80070057h
0x180007944  test    rdx, rdx
0x180007947  jz      loc_180007A1A
0x18000794d  mov     [rcx], di
0x180007950  jmp     loc_180007A1A
0x180007955  test    r8, r8
0x180007958  lea     rcx, dword_18001490C
0x18000795f  cmovnz  rcx, r8
0x180007963  neg     r8
0x180007966  sbb     rax, rax
0x180007969  and     rax, r9
0x18000796c  test    rdx, rdx
0x18000796f  jnz     short loc_180007999
0x180007971  mov     ebx, edi
0x180007973  test    rax, rax
0x180007976  jz      loc_180007A1A
0x18000797c  cmp     [rcx], di
0x18000797f  jz      loc_180007A1A
0x180007985  neg     r10
0x180007988  mov     ebx, 80070057h
0x18000798d  sbb     eax, eax
0x18000798f  and     eax, 23h
0x180007992  add     ebx, eax
0x180007994  jmp     loc_180007A1A
0x180007999  mov     r8, rdx
0x18000799c  mov     r9, r10
0x18000799f  mov     rbx, rdi
0x1800079a2  test    rax, rax
0x1800079a5  jz      short loc_1800079C9
0x1800079a7  movzx   r11d, word ptr [rcx]
0x1800079ab  test    r11w, r11w
0x1800079af  jz      short loc_1800079C9
0x1800079b1  mov     [r9], r11w
0x1800079b5  add     rcx, 2
0x1800079b9  add     r9, 2
0x1800079bd  dec     rax
0x1800079c0  inc     rbx
0x1800079c3  sub     r8, 1
0x1800079c7  jnz     short loc_1800079A2
0x1800079c9  test    r8, r8
0x1800079cc  lea     r11, [rbx-1]
0x1800079d0  lea     rcx, [r9-2]
0x1800079d4  mov     rax, r8
0x1800079d7  cmovnz  r11, rbx
0x1800079db  cmovnz  rcx, r9
0x1800079df  neg     rax
0x1800079e2  sbb     ebx, ebx
0x1800079e4  not     ebx
0x1800079e6  mov     [rcx], di
0x1800079e9  and     ebx, 8007007Ah
0x1800079ef  test    r8, r8
0x1800079f2  jz      short loc_180007A1A
0x1800079f4  sub     rdx, r11
0x1800079f7  cmp     rdx, 1
0x1800079fb  jbe     short loc_180007A1A
0x1800079fd  lea     r8, [rdx+rdx]
0x180007a01  cmp     r8, 2
0x180007a05  jbe     short loc_180007A1A
0x180007a07  add     r10, 2
0x180007a0b  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180007a0f  xor     edx, edx; Val
0x180007a11  lea     rcx, [r10+r11*2]; void *
0x180007a15  call    memset_0
0x180007a1a  mov     eax, ebx
0x180007a1c  mov     rbx, [rsp+28h+arg_0]
0x180007a21  add     rsp, 20h
0x180007a25  pop     rdi
0x180007a26  retn
```
