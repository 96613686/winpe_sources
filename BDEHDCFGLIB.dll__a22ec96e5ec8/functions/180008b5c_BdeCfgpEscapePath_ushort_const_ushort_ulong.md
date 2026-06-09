# BdeCfgpEscapePath(ushort const *,ushort *,ulong)

- ea: `0x180008b5c`
- end: `0x180008c97`
- name: `?BdeCfgpEscapePath@@YAJPEBGPEAGK@Z`
- size: `315`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000634c`

## callees

- `0x180008b5c`
- `0x18000990c`
- `0x18001358e`

## import_xrefs

- `msvcrt!wcschr` at `0x180008b85`
- `msvcrt!wcschr` at `0x180008c61`
- `msvcrt!wcschr` at `0x180008b85`
- `msvcrt!wcschr` at `0x180008c61`

## pseudocode

```c
__int64 __fastcall BdeCfgpEscapePath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  wchar_t *i; // rax
  __int64 v5; // r8
  unsigned __int16 *v6; // rcx
  unsigned int v7; // edx
  __int64 v8; // r9
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  unsigned __int16 *v12; // rcx
  wchar_t *v13; // rsi

  memset_0(a2, 0, 0x208u);
  for ( i = wcschr(a1, 0x5Cu); ; i = wcschr(v13 + 1, 0x5Cu) )
  {
    v13 = i;
    if ( !i )
      return (unsigned int)StringCchCatW(a2, 0x104u, a1);
    v5 = 260;
    v6 = a2;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (260 - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
      return v7;
    v9 = i - a1;
    if ( v9 > 0x7FFFFFFE )
      break;
    v10 = &a2[v8];
    v11 = 260 - v8;
    if ( v8 != 260 )
    {
      do
      {
        if ( !v9 )
          break;
        if ( !*a1 )
          break;
        *v10++ = *a1++;
        --v9;
        --v11;
      }
      while ( v11 );
    }
    v12 = v10 - 1;
    if ( v11 )
      v12 = v10;
    v7 = v11 == 0 ? 0x8007007A : 0;
    *v12 = 0;
    if ( !v11 )
      return v7;
    v7 = StringCchCatW(a2, 0x104u, L"\\\\");
    if ( (v7 & 0x80000000) != 0 )
      return v7;
    a1 = v13 + 1;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180008b5c  push    rbx
0x180008b5e  push    rbp
0x180008b5f  push    rsi
0x180008b60  push    rdi
0x180008b61  push    r14
0x180008b63  sub     rsp, 20h
0x180008b67  mov     rdi, rdx
0x180008b6a  mov     rbx, rcx
0x180008b6d  mov     rcx, rdi; void *
0x180008b70  xor     edx, edx; Val
0x180008b72  mov     r8d, 208h; Size
0x180008b78  call    memset_0
0x180008b7d  mov     edx, 5Ch ; '\'; Ch
0x180008b82  mov     rcx, rbx; Str
0x180008b85  call    cs:__imp_wcschr
0x180008b8b  xor     ebp, ebp
0x180008b8d  mov     r14d, 104h
0x180008b93  jmp     loc_180008C67
0x180008b98  mov     r8, r14
0x180008b9b  mov     rcx, rdi
0x180008b9e  cmp     [rcx], bp
0x180008ba1  jz      short loc_180008BAD
0x180008ba3  add     rcx, 2
0x180008ba7  sub     r8, 1
0x180008bab  jnz     short loc_180008B9E
0x180008bad  mov     rax, r8
0x180008bb0  mov     rcx, r14
0x180008bb3  neg     rax
0x180008bb6  mov     rax, r8
0x180008bb9  sbb     edx, edx
0x180008bbb  sub     rcx, r8
0x180008bbe  not     edx
0x180008bc0  and     edx, 80070057h
0x180008bc6  neg     rax
0x180008bc9  sbb     r9, r9
0x180008bcc  and     r9, rcx
0x180008bcf  test    r8, r8
0x180008bd2  jz      loc_180008C83
0x180008bd8  mov     rax, rsi
0x180008bdb  sub     rax, rbx
0x180008bde  sar     rax, 1
0x180008be1  cmp     rax, 7FFFFFFEh
0x180008be7  ja      loc_180008C90
0x180008bed  mov     r8, r14
0x180008bf0  lea     rdx, [rdi+r9*2]
0x180008bf4  sub     r8, r9
0x180008bf7  jz      short loc_180008C1A
0x180008bf9  test    rax, rax
0x180008bfc  jz      short loc_180008C1A
0x180008bfe  movzx   ecx, word ptr [rbx]
0x180008c01  test    cx, cx
0x180008c04  jz      short loc_180008C1A
0x180008c06  mov     [rdx], cx
0x180008c09  add     rbx, 2
0x180008c0d  add     rdx, 2
0x180008c11  dec     rax
0x180008c14  sub     r8, 1
0x180008c18  jnz     short loc_180008BF9
0x180008c1a  lea     rcx, [rdx-2]
0x180008c1e  test    r8, r8
0x180008c21  mov     rax, r8
0x180008c24  cmovnz  rcx, rdx
0x180008c28  neg     rax
0x180008c2b  sbb     edx, edx
0x180008c2d  not     edx
0x180008c2f  and     edx, 8007007Ah
0x180008c35  mov     [rcx], bp
0x180008c38  test    r8, r8
0x180008c3b  jz      short loc_180008C83
0x180008c3d  lea     r8, asc_1800171F8; "\\\\"
0x180008c44  mov     rdx, r14; unsigned __int64
0x180008c47  mov     rcx, rdi; unsigned __int16 *
0x180008c4a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c4f  mov     edx, eax
0x180008c51  test    eax, eax
0x180008c53  js      short loc_180008C83
0x180008c55  lea     rbx, [rsi+2]
0x180008c59  mov     edx, 5Ch ; '\'; Ch
0x180008c5e  mov     rcx, rbx; Str
0x180008c61  call    cs:__imp_wcschr
0x180008c67  mov     rsi, rax
0x180008c6a  test    rax, rax
0x180008c6d  jnz     loc_180008B98
0x180008c73  mov     r8, rbx; unsigned __int16 *
0x180008c76  mov     rdx, r14; unsigned __int64
0x180008c79  mov     rcx, rdi; unsigned __int16 *
0x180008c7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c81  mov     edx, eax
0x180008c83  mov     eax, edx
0x180008c85  add     rsp, 20h
0x180008c89  pop     r14
0x180008c8b  pop     rdi
0x180008c8c  pop     rsi
0x180008c8d  pop     rbp
0x180008c8e  pop     rbx
0x180008c8f  retn
0x180008c90  mov     edx, 80070057h
0x180008c95  jmp     short loc_180008C83
```
