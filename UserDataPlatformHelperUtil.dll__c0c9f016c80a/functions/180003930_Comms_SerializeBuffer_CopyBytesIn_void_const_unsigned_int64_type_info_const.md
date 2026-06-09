# Comms::SerializeBuffer::CopyBytesIn(void const *,unsigned __int64,type_info const &)

- ea: `0x180003930`
- end: `0x180003a77`
- name: `?CopyBytesIn@SerializeBuffer@Comms@@UEAAXPEBX_KAEBVtype_info@@@Z`
- size: `327`
- prototype: `void __fastcall(Comms::SerializeBuffer *this, char *, unsigned __int64, const struct type_info *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002d98`
- `0x180003930`
- `0x18000a15a`

## import_xrefs

- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x180003968`
- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x1800039d7`
- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x180003968`
- `msvcrt!?raw_name@type_info@@QEBAPEBDXZ` at `0x1800039d7`

## pseudocode

```c
void __fastcall Comms::SerializeBuffer::CopyBytesIn(
        Comms::SerializeBuffer *this,
        char *a2,
        unsigned __int64 a3,
        const struct type_info *a4)
{
  char *v4; // rbx
  __int64 v6; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rbp
  size_t v13; // r8
  const char *v14; // rcx
  __int64 v15; // rax
  __int16 v16; // dx
  const char *v17; // r8
  __int64 v18; // rax
  _BYTE *v19; // rax
  char *v20; // rdx
  char v21; // cl
  char *v22; // rdx
  _BYTE *v23; // rax
  _WORD v24[2]; // [rsp+20h] [rbp-58h] BYREF
  char v25; // [rsp+24h] [rbp-54h] BYREF

  v4 = (char *)this + 24;
  v6 = *((_QWORD *)this + 3);
  v9 = *((_QWORD *)this + 4) - v6;
  v11 = v9 + a3;
  if ( *((_BYTE *)this + 16) )
  {
    type_info::raw_name(a4);
    v6 = *(_QWORD *)v4;
    v11 += 4LL;
    v12 = *((_QWORD *)v4 + 1) - *(_QWORD *)v4;
    if ( v11 > v12 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(v4, v11) )
        goto LABEL_10;
      v13 = v11 - v12;
      goto LABEL_9;
    }
LABEL_6:
    *((_QWORD *)v4 + 1) = v11 + v6;
    goto LABEL_10;
  }
  if ( v11 <= v9 )
    goto LABEL_6;
  if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve((char *)this + 24, v9 + a3) )
    goto LABEL_10;
  v13 = a3;
LABEL_9:
  memset_0(*((void **)v4 + 1), 0, v13);
  *((_QWORD *)v4 + 1) = v11 + *(_QWORD *)v4;
LABEL_10:
  if ( *((_BYTE *)this + 16) )
  {
    v14 = type_info::raw_name(a4);
    v24[0] = -1;
    if ( a3 <= 0xFFFF )
      v24[0] = a3;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    v16 = -25147;
    v17 = &v14[v15];
    while ( v14 != v17 )
      v16 = *v14++ ^ (unsigned __int16)(403 * v16);
    v18 = *(_QWORD *)v4;
    v24[1] = v16;
    v19 = (_BYTE *)(v9 + v18);
    v20 = (char *)v24;
    do
    {
      v21 = *v20++;
      *v19++ = v21;
    }
    while ( v20 != &v25 );
    v9 += 4LL;
  }
  v22 = &a2[a3];
  v23 = (_BYTE *)(v9 + *(_QWORD *)v4);
  while ( a2 != v22 )
    *v23++ = *a2++;
}

```

## disassembly

```asm
0x180003930  push    rbx
0x180003932  push    rbp
0x180003933  push    rsi
0x180003934  push    rdi
0x180003935  push    r12
0x180003937  push    r13
0x180003939  push    r14
0x18000393b  push    r15
0x18000393d  sub     rsp, 38h
0x180003941  lea     rbx, [rcx+18h]
0x180003945  mov     r12, r9
0x180003948  mov     rax, [rbx]
0x18000394b  mov     r15, r8
0x18000394e  mov     rsi, [rbx+8]
0x180003952  mov     rdi, rdx
0x180003955  sub     rsi, rax
0x180003958  mov     r13, rcx
0x18000395b  cmp     byte ptr [rcx+10h], 0
0x18000395f  lea     r14, [rsi+r8]
0x180003963  jz      short loc_180003998
0x180003965  mov     rcx, r9
0x180003968  call    cs:__imp_?raw_name@type_info@@QEBAPEBDXZ; type_info::raw_name(void)
0x18000396e  mov     rax, [rbx]
0x180003971  add     r14, 4
0x180003975  mov     rbp, [rbx+8]
0x180003979  sub     rbp, rax
0x18000397c  cmp     r14, rbp
0x18000397f  jbe     short loc_18000399D
0x180003981  mov     rdx, r14
0x180003984  mov     rcx, rbx
0x180003987  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18000398c  test    al, al
0x18000398e  jz      short loc_1800039CD
0x180003990  mov     r8, r14
0x180003993  sub     r8, rbp
0x180003996  jmp     short loc_1800039B8
0x180003998  cmp     r14, rsi
0x18000399b  ja      short loc_1800039A6
0x18000399d  add     rax, r14
0x1800039a0  mov     [rbx+8], rax
0x1800039a4  jmp     short loc_1800039CD
0x1800039a6  mov     rdx, r14
0x1800039a9  mov     rcx, rbx
0x1800039ac  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1800039b1  test    al, al
0x1800039b3  jz      short loc_1800039CD
0x1800039b5  mov     r8, r15; Size
0x1800039b8  mov     rcx, [rbx+8]; void *
0x1800039bc  xor     edx, edx; Val
0x1800039be  call    memset_0
0x1800039c3  mov     rcx, [rbx]
0x1800039c6  add     rcx, r14
0x1800039c9  mov     [rbx+8], rcx
0x1800039cd  cmp     byte ptr [r13+10h], 0
0x1800039d2  jz      short loc_180003A4B
0x1800039d4  mov     rcx, r12
0x1800039d7  call    cs:__imp_?raw_name@type_info@@QEBAPEBDXZ; type_info::raw_name(void)
0x1800039dd  mov     rcx, rax
0x1800039e0  mov     eax, 0FFFFh
0x1800039e5  mov     [rsp+78h+var_58], ax
0x1800039ea  cmp     r15, rax
0x1800039ed  ja      short loc_1800039F5
0x1800039ef  mov     [rsp+78h+var_58], r15w
0x1800039f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800039f9  inc     rax
0x1800039fc  cmp     byte ptr [rcx+rax], 0
0x180003a00  jnz     short loc_1800039F9
0x180003a02  mov     edx, 811C9DC5h
0x180003a07  lea     r8, [rax+rcx]
0x180003a0b  jmp     short loc_180003A1E
0x180003a0d  movsx   rax, byte ptr [rcx]
0x180003a11  imul    rdx, 1000193h
0x180003a18  xor     rdx, rax
0x180003a1b  inc     rcx
0x180003a1e  cmp     rcx, r8
0x180003a21  jnz     short loc_180003A0D
0x180003a23  mov     rax, [rbx]
0x180003a26  mov     [rsp+78h+var_56], dx
0x180003a2b  add     rax, rsi
0x180003a2e  lea     rdx, [rsp+78h+var_58]
0x180003a33  mov     cl, [rdx]
0x180003a35  inc     rdx
0x180003a38  mov     [rax], cl
0x180003a3a  inc     rax
0x180003a3d  lea     rcx, [rsp+78h+var_54]
0x180003a42  cmp     rdx, rcx
0x180003a45  jnz     short loc_180003A33
0x180003a47  add     rsi, 4
0x180003a4b  mov     rax, [rbx]
0x180003a4e  lea     rdx, [rdi+r15]
0x180003a52  add     rax, rsi
0x180003a55  jmp     short loc_180003A61
0x180003a57  mov     cl, [rdi]
0x180003a59  mov     [rax], cl
0x180003a5b  inc     rax
0x180003a5e  inc     rdi
0x180003a61  cmp     rdi, rdx
0x180003a64  jnz     short loc_180003A57
0x180003a66  add     rsp, 38h
0x180003a6a  pop     r15
0x180003a6c  pop     r14
0x180003a6e  pop     r13
0x180003a70  pop     r12
0x180003a72  pop     rdi
0x180003a73  pop     rsi
0x180003a74  pop     rbp
0x180003a75  pop     rbx
0x180003a76  retn
```
