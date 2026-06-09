# Common::DirectoryTreeWalker::Visit(unsigned __int64,ushort *,_WIN32_FIND_DATAW const *,long *)

- ea: `0x180018ef0`
- end: `0x180018ff3`
- name: `?Visit@DirectoryTreeWalker@Common@@AEAAJ_KPEAGPEBU_WIN32_FIND_DATAW@@PEAJ@Z`
- size: `259`
- prototype: `int(Common::DirectoryTreeWalker *__hidden this, unsigned __int64, unsigned __int16 *, const struct _WIN32_FIND_DATAW *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018ffc`

## callees

- `0x180018cc4`
- `0x180018e54`
- `0x180018ef0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::Visit(
        Common::DirectoryTreeWalker *this,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        const struct _WIN32_FIND_DATAW *a4,
        int *a5)
{
  Common::DirectoryTreeWalker *v8; // r11
  unsigned __int64 v9; // rdi
  __int64 v10; // r9
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // ecx
  __int64 result; // rax

  v8 = this;
  v9 = a2;
  if ( (*((_BYTE *)this + 32) & 0x40) != 0 && !Common::DirectoryTreeWalker::IsDirAndShouldBeWalked(this, a4) )
  {
    v11 = (const unsigned __int16 *)(v10 + 44);
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( a2 + 1 > 0x7FFF - v12 && v12 + a2 + 1 > 0x7FFF && v12 > 0x7FFF )
      return 206;
    v9 = v12 + a2 + 1;
    if ( v9 > 0x7FFF )
      return 206;
    a3[a2] = 92;
    RtlStringCchCopyW(&a3[a2 + 1], 0x7FFF - (a2 + 1), v11);
  }
  v13 = 0;
  if ( (*((_BYTE *)v8 + 32) & 0x10) != 0 )
  {
    v13 = v9;
    if ( *((_QWORD *)v8 + 3) + 1LL < v9 )
      v13 = *((_QWORD *)v8 + 3) + 1LL;
  }
  if ( (*((_BYTE *)v8 + 32) & 0x20) != 0 )
  {
    v13 = v9;
    if ( a2 + 1 < v9 )
      v13 = a2 + 1;
  }
  v14 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const struct _WIN32_FIND_DATAW *))v8 + 5))(
          *((_QWORD *)v8 + 6),
          &a3[v13],
          a4);
  result = 1223;
  if ( v14 == 1223 )
  {
    if ( v9 > a2 )
      a3[a2] = 0;
  }
  else
  {
    *a5 = v14;
    if ( v9 > a2 )
      a3[a2] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018ef0  push    rbx
0x180018ef2  push    rbp
0x180018ef3  push    rsi
0x180018ef4  push    rdi
0x180018ef5  push    r14
0x180018ef7  sub     rsp, 20h
0x180018efb  xor     r14d, r14d
0x180018efe  mov     rbp, r9
0x180018f01  test    byte ptr [rcx+20h], 40h
0x180018f05  mov     rsi, r8
0x180018f08  mov     rbx, rdx
0x180018f0b  mov     r11, rcx
0x180018f0e  mov     rdi, rdx
0x180018f11  jz      short loc_180018F73
0x180018f13  mov     rdx, r9; struct _WIN32_FIND_DATAW *
0x180018f16  call    ?IsDirAndShouldBeWalked@DirectoryTreeWalker@Common@@AEBA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::DirectoryTreeWalker::IsDirAndShouldBeWalked(_WIN32_FIND_DATAW const &)
0x180018f1b  test    al, al
0x180018f1d  jnz     short loc_180018F73
0x180018f1f  lea     r8, [r9+2Ch]; unsigned __int16 *
0x180018f23  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018f27  inc     rcx
0x180018f2a  cmp     [r8+rcx*2], r14w
0x180018f2f  jnz     short loc_180018F27
0x180018f31  mov     edx, 7FFFh
0x180018f36  lea     r9, [rbx+1]
0x180018f3a  mov     eax, edx
0x180018f3c  sub     rax, rcx
0x180018f3f  cmp     r9, rax
0x180018f42  jbe     short loc_180018F55
0x180018f44  lea     rax, [rbx+1]
0x180018f48  add     rax, rcx
0x180018f4b  cmp     rax, rdx
0x180018f4e  jbe     short loc_180018F55
0x180018f50  cmp     rcx, rdx
0x180018f53  ja      short loc_180018FCE
0x180018f55  lea     rdi, [rbx+1]
0x180018f59  add     rdi, rcx
0x180018f5c  cmp     rdi, rdx
0x180018f5f  ja      short loc_180018FCE
0x180018f61  sub     rdx, r9; unsigned __int64
0x180018f64  mov     word ptr [rsi+rbx*2], 5Ch ; '\'
0x180018f6a  lea     rcx, [rsi+r9*2]; unsigned __int16 *
0x180018f6e  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018f73  test    byte ptr [r11+20h], 10h
0x180018f78  mov     rcx, r14
0x180018f7b  jz      short loc_180018F8E
0x180018f7d  mov     rax, [r11+18h]
0x180018f81  mov     rcx, rdi
0x180018f84  inc     rax
0x180018f87  cmp     rax, rdi
0x180018f8a  cmovb   rcx, rax
0x180018f8e  test    byte ptr [r11+20h], 20h
0x180018f93  jz      short loc_180018FA3
0x180018f95  lea     rax, [rbx+1]
0x180018f99  mov     rcx, rdi
0x180018f9c  cmp     rax, rdi
0x180018f9f  cmovb   rcx, rax
0x180018fa3  mov     rax, [r11+28h]
0x180018fa7  lea     rdx, [rsi+rcx*2]
0x180018fab  mov     rcx, [r11+30h]
0x180018faf  mov     r8, rbp
0x180018fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb7  mov     ecx, eax
0x180018fb9  mov     eax, 4C7h
0x180018fbe  cmp     ecx, eax
0x180018fc0  jnz     short loc_180018FD5
0x180018fc2  cmp     rdi, rbx
0x180018fc5  jbe     short loc_180018FE8
0x180018fc7  mov     [rsi+rbx*2], r14w
0x180018fcc  jmp     short loc_180018FE8
0x180018fce  mov     eax, 0CEh
0x180018fd3  jmp     short loc_180018FE8
0x180018fd5  mov     rax, [rsp+48h+arg_20]
0x180018fda  mov     [rax], ecx
0x180018fdc  cmp     rdi, rbx
0x180018fdf  jbe     short loc_180018FE6
0x180018fe1  mov     [rsi+rbx*2], r14w
0x180018fe6  xor     eax, eax
0x180018fe8  add     rsp, 20h
0x180018fec  pop     r14
0x180018fee  pop     rdi
0x180018fef  pop     rsi
0x180018ff0  pop     rbp
0x180018ff1  pop     rbx
0x180018ff2  retn
```
