# CSPath::AddComponent(ushort const *,ushort const *)

- ea: `0x18000ca60`
- end: `0x18000cb8f`
- name: `?AddComponent@CSPath@@QEAAKPEBG0@Z`
- size: `303`
- prototype: `const unsigned __int16 *__fastcall(HLOCAL *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001069c`
- `0x180011ac0`

## callees

- `0x180002aa0`
- `0x18000ca60`
- `0x18000cc10`
- `0x18001b1a0`
- `0x18001bcc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000caff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000caff`

## pseudocode

```c
const unsigned __int16 *__fastcall CSPath::AddComponent(
        HLOCAL *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *result; // rax
  unsigned int ClassStorePath; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  unsigned int v9; // ecx
  __int64 v10; // rcx
  HLOCAL v11; // rdi
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  unsigned __int64 v15; // rsi
  int v16; // eax
  unsigned __int16 v17; // bp
  unsigned __int16 *v18; // rcx
  int v19; // eax
  int v20; // eax
  HLOCAL hMem; // [rsp+68h] [rbp+10h] BYREF

  hMem = 0;
  result = a2;
  if ( a2 )
  {
    ClassStorePath = CsGetClassStorePath(a2, &hMem);
    v7 = ClassStorePath;
    if ( ClassStorePath )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xBF9u, a3, ClassStorePath);
      return (const unsigned __int16 *)v7;
    }
    v8 = -1;
    v9 = 0;
    if ( *this )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)*this + v10) );
      v9 = 2 * v10;
    }
    v11 = hMem;
    if ( hMem )
    {
      do
        ++v8;
      while ( *((_WORD *)hMem + v8) );
      v9 += 2 * v8 + 4;
    }
    v12 = v9;
    v13 = (unsigned __int16 *)LocalAlloc(0, v9);
    v14 = v13;
    if ( !v13 )
    {
      v7 = 8;
LABEL_21:
      LocalFree(v11);
      return (const unsigned __int16 *)v7;
    }
    v15 = v12 >> 1;
    v16 = StringCchCopyW(v13, v15, (const unsigned __int16 *)v11);
    v17 = v16;
    v18 = v14;
    if ( v16 >= 0 )
    {
      v19 = StringCchCatW(v14, v15, L";");
      v17 = v19;
      if ( v19 >= 0 )
      {
        if ( !*this || (v20 = StringCchCatW(v14, v15, (const unsigned __int16 *)*this), v17 = v20, v20 >= 0) )
        {
          LocalFree(*this);
          *this = v14;
          v7 = 0;
          goto LABEL_21;
        }
      }
      v18 = v14;
    }
    LocalFree(v18);
    v7 = v17;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x18000ca60  push    rbx
0x18000ca62  push    rbp
0x18000ca63  push    rsi
0x18000ca64  push    rdi
0x18000ca65  push    r14
0x18000ca67  push    r15
0x18000ca69  sub     rsp, 28h
0x18000ca6d  xor     r15d, r15d
0x18000ca70  mov     rdi, r8
0x18000ca73  mov     [rsp+58h+hMem], r15
0x18000ca78  mov     rax, rdx
0x18000ca7b  mov     r14, rcx
0x18000ca7e  test    rdx, rdx
0x18000ca81  jz      loc_18000CB82
0x18000ca87  lea     rdx, [rsp+58h+hMem]
0x18000ca8c  mov     rcx, rax
0x18000ca8f  call    CsGetClassStorePath
0x18000ca94  mov     ebx, eax
0x18000ca96  test    eax, eax
0x18000ca98  jz      short loc_18000CAC1
0x18000ca9a  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000caa1  jz      loc_18000CB80
0x18000caa7  mov     r9d, eax
0x18000caaa  mov     r8, rdi
0x18000caad  mov     edx, 0BF9h; unsigned int
0x18000cab2  mov     ecx, 4; unsigned int
0x18000cab7  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000cabc  jmp     loc_18000CB80
0x18000cac1  mov     rdx, [r14]
0x18000cac4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cac8  mov     ecx, r15d
0x18000cacb  test    rdx, rdx
0x18000cace  jz      short loc_18000CADF
0x18000cad0  mov     rcx, rax
0x18000cad3  inc     rcx
0x18000cad6  cmp     [rdx+rcx*2], r15w
0x18000cadb  jnz     short loc_18000CAD3
0x18000cadd  add     ecx, ecx
0x18000cadf  mov     rdi, [rsp+58h+hMem]
0x18000cae4  test    rdi, rdi
0x18000cae7  jz      short loc_18000CAF9
0x18000cae9  inc     rax
0x18000caec  cmp     [rdi+rax*2], r15w
0x18000caf1  jnz     short loc_18000CAE9
0x18000caf3  lea     ecx, [rcx+rax*2]
0x18000caf6  add     ecx, 4
0x18000caf9  mov     esi, ecx
0x18000cafb  mov     edx, ecx; uBytes
0x18000cafd  xor     ecx, ecx; uFlags
0x18000caff  call    cs:__imp_LocalAlloc
0x18000cb05  mov     rbx, rax
0x18000cb08  test    rax, rax
0x18000cb0b  jnz     short loc_18000CB12
0x18000cb0d  lea     ebx, [rax+8]
0x18000cb10  jmp     short loc_18000CB77
0x18000cb12  shr     rsi, 1
0x18000cb15  mov     r8, rdi; unsigned __int16 *
0x18000cb18  mov     rdx, rsi; unsigned __int64
0x18000cb1b  mov     rcx, rbx; unsigned __int16 *
0x18000cb1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cb23  mov     ebp, eax
0x18000cb25  mov     rcx, rbx; unsigned __int16 *
0x18000cb28  test    eax, eax
0x18000cb2a  js      short loc_18000CB6E
0x18000cb2c  lea     r8, asc_18002FEBC; ";"
0x18000cb33  mov     rdx, rsi; unsigned __int64
0x18000cb36  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb3b  mov     ebp, eax
0x18000cb3d  test    eax, eax
0x18000cb3f  js      short loc_18000CB6B
0x18000cb41  mov     r8, [r14]; unsigned __int16 *
0x18000cb44  test    r8, r8
0x18000cb47  jz      short loc_18000CB5A
0x18000cb49  mov     rdx, rsi; unsigned __int64
0x18000cb4c  mov     rcx, rbx; unsigned __int16 *
0x18000cb4f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb54  mov     ebp, eax
0x18000cb56  test    eax, eax
0x18000cb58  js      short loc_18000CB6B
0x18000cb5a  mov     rcx, [r14]; hMem
0x18000cb5d  call    cs:__imp_LocalFree
0x18000cb63  mov     [r14], rbx
0x18000cb66  mov     ebx, r15d
0x18000cb69  jmp     short loc_18000CB77
0x18000cb6b  mov     rcx, rbx; hMem
0x18000cb6e  call    cs:__imp_LocalFree
0x18000cb74  movzx   ebx, bp
0x18000cb77  mov     rcx, rdi; hMem
0x18000cb7a  call    cs:__imp_LocalFree
0x18000cb80  mov     eax, ebx
0x18000cb82  add     rsp, 28h
0x18000cb86  pop     r15
0x18000cb88  pop     r14
0x18000cb8a  pop     rdi
0x18000cb8b  pop     rsi
0x18000cb8c  pop     rbp
0x18000cb8d  pop     rbx
0x18000cb8e  retn
```
