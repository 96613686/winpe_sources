# Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1800126c0`
- end: `0x1800127b3`
- name: `?Convert2CRC@@YAXPEBG00PEAGK@Z`
- size: `243`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800121d8`
- `0x1800127bc`
- `0x180012d50`
- `0x180013acc`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x1800126c0`
- `0x1800172dc`
- `0x18001b980`

## pseudocode

```c
void __fastcall Convert2CRC(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  const unsigned __int16 *v7; // r11
  unsigned __int8 *v8; // rdi
  __int64 v9; // rbp
  unsigned __int64 v10; // rbx
  unsigned int i; // ebx
  unsigned __int64 v13; // rax
  __int64 v14; // rbx
  unsigned __int16 v15[1536]; // [rsp+20h] [rbp-C48h] BYREF

  StringCchCopyW(v15, 0x600u, a1);
  StringCchCatW(v15, 0x600u, v7);
  if ( a3 )
    StringCchCatW(v15, 0x600u, a3);
  v8 = (unsigned __int8 *)v15;
  LODWORD(v9) = 0;
  v10 = -1;
  do
    ++v10;
  while ( v15[v10] );
  for ( i = 2 * (v10 >> 1); i; i = 2 * v14 )
  {
    v9 = CRC32Compute(v8, i, v9);
    StringCchPrintfW(a4, a5, L"%08x", v9);
    a4 += 8;
    v13 = (unsigned __int64)i >> 1;
    a5 -= 8;
    v14 = -1;
    v8 += 2 * v13;
    do
      ++v14;
    while ( *(_WORD *)&v8[2 * v14] );
  }
}

```

## disassembly

```asm
0x1800126c0  push    rbx
0x1800126c2  push    rbp
0x1800126c3  push    rsi
0x1800126c4  push    rdi
0x1800126c5  push    r14
0x1800126c7  push    r15
0x1800126c9  sub     rsp, 0C38h
0x1800126d0  mov     rax, cs:__security_cookie
0x1800126d7  xor     rax, rsp
0x1800126da  mov     [rsp+0C68h+var_48], rax
0x1800126e2  mov     rbx, r8
0x1800126e5  mov     r11, rdx
0x1800126e8  mov     r8, rcx; unsigned __int16 *
0x1800126eb  mov     edi, 600h
0x1800126f0  mov     edx, edi; unsigned __int64
0x1800126f2  lea     rcx, [rsp+0C68h+var_C48]; unsigned __int16 *
0x1800126f7  mov     r14, r9
0x1800126fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800126ff  mov     r8, r11; unsigned __int16 *
0x180012702  lea     rcx, [rsp+0C68h+var_C48]; unsigned __int16 *
0x180012707  mov     edx, edi; unsigned __int64
0x180012709  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001270e  xor     r15d, r15d
0x180012711  test    rbx, rbx
0x180012714  jz      short loc_180012725
0x180012716  mov     r8, rbx; unsigned __int16 *
0x180012719  lea     rcx, [rsp+0C68h+var_C48]; unsigned __int16 *
0x18001271e  mov     edx, edi; unsigned __int64
0x180012720  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012725  lea     rdi, [rsp+0C68h+var_C48]
0x18001272a  mov     ebp, r15d
0x18001272d  lea     rax, [rsp+0C68h+var_C48]
0x180012732  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012736  inc     rbx
0x180012739  cmp     [rax+rbx*2], r15w
0x18001273e  jnz     short loc_180012736
0x180012740  shr     rbx, 1
0x180012743  add     ebx, ebx
0x180012745  jz      short loc_180012793
0x180012747  mov     esi, [rsp+0C68h+arg_20]
0x18001274e  mov     r8d, ebp; unsigned int
0x180012751  mov     edx, ebx; unsigned int
0x180012753  mov     rcx, rdi; unsigned __int8 *
0x180012756  call    ?CRC32Compute@@YAKPEAEIK@Z; CRC32Compute(uchar *,uint,ulong)
0x18001275b  mov     edx, esi; unsigned __int64
0x18001275d  lea     r8, a08x; "%08x"
0x180012764  mov     r9d, eax
0x180012767  mov     rcx, r14; unsigned __int16 *
0x18001276a  mov     ebp, eax
0x18001276c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012771  mov     eax, ebx
0x180012773  add     r14, 10h
0x180012777  shr     rax, 1
0x18001277a  add     esi, 0FFFFFFF8h
0x18001277d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012781  lea     rdi, [rdi+rax*2]
0x180012785  inc     rbx
0x180012788  cmp     [rdi+rbx*2], r15w
0x18001278d  jnz     short loc_180012785
0x18001278f  add     ebx, ebx
0x180012791  jnz     short loc_18001274E
0x180012793  mov     rcx, [rsp+0C68h+var_48]
0x18001279b  xor     rcx, rsp; StackCookie
0x18001279e  call    __security_check_cookie
0x1800127a3  add     rsp, 0C38h
0x1800127aa  pop     r15
0x1800127ac  pop     r14
0x1800127ae  pop     rdi
0x1800127af  pop     rsi
0x1800127b0  pop     rbp
0x1800127b1  pop     rbx
0x1800127b2  retn
```
