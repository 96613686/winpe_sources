# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)

- ea: `0x180007398`
- end: `0x1800074d0`
- name: `??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z`
- size: `312`
- prototype: `char **__fastcall(char **, unsigned __int64, __int64, const void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000786c`
- `0x180007918`

## callees

- `0x180001c24`
- `0x180002014`
- `0x180007398`
- `0x1800078d8`
- `0x180007900`
- `0x180013ab4`

## pseudocode

```c
char **__fastcall std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4)
{
  __int64 v4; // rbx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  size_t v11; // rcx
  void *v12; // rax
  _QWORD *v13; // rsi
  char *v14; // rax
  unsigned __int64 v15; // rdx
  char *v16; // rcx
  char **result; // rax

  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v8 = (unsigned __int64)a1[3];
  v9 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v10 = v8 >> 1, v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1)) )
  {
    v4 = v10 + v8;
    if ( v9 >= v10 + v8 )
      v4 = v9;
    if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_24;
    v11 = 2 * (v4 + 1);
    if ( !v11 )
    {
      v13 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v11 = -2;
  }
  if ( v11 < 0x1000 )
  {
    v13 = operator new(v11);
    goto LABEL_15;
  }
  if ( v11 + 39 < v11 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_19;
  v13 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v12;
LABEL_15:
  a1[3] = (char *)v4;
  a1[2] = (char *)a2;
  memcpy_0(v13, a4, 2 * a2);
  *((_WORD *)v13 + a2) = 0;
  if ( v8 > 7 )
  {
    v14 = *a1;
    v15 = 2 * v8 + 2;
    if ( v15 < 0x1000 )
    {
      v16 = *a1;
      goto LABEL_21;
    }
    v16 = (char *)*((_QWORD *)v14 - 1);
    if ( (unsigned __int64)(v14 - v16 - 8) <= 0x1F )
    {
      v15 = 2 * v8 + 41;
LABEL_21:
      operator delete(v16, v15);
      goto LABEL_22;
    }
LABEL_19:
    __fastfail(5u);
  }
LABEL_22:
  result = a1;
  *a1 = (char *)v13;
  return result;
}

```

## disassembly

```asm
0x180007398  push    rbx
0x18000739a  push    rbp
0x18000739b  push    rsi
0x18000739c  push    rdi
0x18000739d  push    r14
0x18000739f  push    r15
0x1800073a1  sub     rsp, 28h
0x1800073a5  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1800073af  mov     r15, r9
0x1800073b2  mov     r14, rdx
0x1800073b5  mov     rdi, rcx
0x1800073b8  cmp     rdx, rbx
0x1800073bb  ja      loc_1800074C4
0x1800073c1  mov     rbp, [rcx+18h]
0x1800073c5  mov     rcx, rdx
0x1800073c8  or      rcx, 7
0x1800073cc  cmp     rcx, rbx
0x1800073cf  ja      short loc_1800073E2
0x1800073d1  mov     rdx, rbp
0x1800073d4  mov     rax, rbx
0x1800073d7  shr     rdx, 1
0x1800073da  sub     rax, rdx
0x1800073dd  cmp     rbp, rax
0x1800073e0  jbe     short loc_18000741E
0x1800073e2  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x1800073e9  cmp     rcx, 1000h
0x1800073f0  jb      short loc_180007449
0x1800073f2  lea     rax, [rcx+27h]
0x1800073f6  cmp     rax, rcx
0x1800073f9  jbe     loc_1800074CA
0x1800073ff  mov     rcx, rax; Size
0x180007402  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007407  test    rax, rax
0x18000740a  jz      loc_1800074A2
0x180007410  lea     rsi, [rax+27h]
0x180007414  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180007418  mov     [rsi-8], rax
0x18000741c  jmp     short loc_180007451
0x18000741e  lea     rbx, [rdx+rbp]
0x180007422  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000742c  cmp     rcx, rbx
0x18000742f  cmovnb  rbx, rcx
0x180007433  lea     rcx, [rbx+1]
0x180007437  cmp     rcx, rax
0x18000743a  ja      loc_1800074CA
0x180007440  add     rcx, rcx
0x180007443  jnz     short loc_1800073E9
0x180007445  xor     esi, esi
0x180007447  jmp     short loc_180007451
0x180007449  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000744e  mov     rsi, rax
0x180007451  mov     [rdi+18h], rbx
0x180007455  mov     rdx, r15; Src
0x180007458  lea     rbx, [r14+r14]
0x18000745c  mov     [rdi+10h], r14
0x180007460  mov     r8, rbx; Size
0x180007463  mov     rcx, rsi; void *
0x180007466  call    memcpy_0
0x18000746b  xor     ecx, ecx
0x18000746d  mov     [rbx+rsi], cx
0x180007471  cmp     rbp, 7
0x180007475  jbe     short loc_1800074B1
0x180007477  mov     rax, [rdi]
0x18000747a  lea     rdx, ds:2[rbp*2]; unsigned __int64
0x180007482  cmp     rdx, 1000h
0x180007489  jb      short loc_1800074A9
0x18000748b  mov     rcx, [rax-8]
0x18000748f  sub     rax, rcx
0x180007492  sub     rax, 8
0x180007496  cmp     rax, 1Fh
0x18000749a  ja      short loc_1800074A2
0x18000749c  add     rdx, 27h ; '''
0x1800074a0  jmp     short loc_1800074AC
0x1800074a2  mov     ecx, 5
0x1800074a7  int     29h; Win8: RtlFailFast(ecx)
0x1800074a9  mov     rcx, rax; void *
0x1800074ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800074b1  mov     rax, rdi
0x1800074b4  mov     [rax], rsi
0x1800074b7  add     rsp, 28h
0x1800074bb  pop     r15
0x1800074bd  pop     r14
0x1800074bf  pop     rdi
0x1800074c0  pop     rsi
0x1800074c1  pop     rbp
0x1800074c2  pop     rbx
0x1800074c3  retn
0x1800074c4  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800074ca  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
