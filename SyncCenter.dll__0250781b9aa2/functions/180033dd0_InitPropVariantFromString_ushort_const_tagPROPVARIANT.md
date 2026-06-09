# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x180033dd0`
- end: `0x180033e49`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800388e0`
- `0x18004e1d0`

## callees

- `0x180033dd0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180033e20`
- `msvcrt!memcpy_s` at `0x180033e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033e05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033e05`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Source, struct tagPROPVARIANT *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rax
  __int64 v6; // rbp
  void *v7; // rax

  v2 = 0;
  if ( !Source )
  {
    v2 = -2147024809;
LABEL_8:
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    return v2;
  }
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  v6 = 2 * v5 + 2;
  v7 = CoTaskMemAlloc(v6);
  a2->hVal.QuadPart = (LONGLONG)v7;
  if ( !v7 )
  {
    v2 = -2147024882;
    goto LABEL_8;
  }
  memcpy_s(v7, v6, Source, v6);
  a2->vt = 31;
  return v2;
}

```

## disassembly

```asm
0x180033dd0  push    rbx
0x180033dd2  push    rbp
0x180033dd3  push    rsi
0x180033dd4  push    rdi
0x180033dd5  sub     rsp, 28h
0x180033dd9  xor     ebx, ebx
0x180033ddb  mov     rdi, rdx
0x180033dde  mov     rsi, rcx
0x180033de1  test    rcx, rcx
0x180033de4  jnz     short loc_180033DED
0x180033de6  mov     ebx, 80070057h
0x180033deb  jmp     short loc_180033E32
0x180033ded  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033df1  inc     rax
0x180033df4  cmp     [rcx+rax*2], bx
0x180033df8  jnz     short loc_180033DF1
0x180033dfa  lea     rbp, ds:2[rax*2]
0x180033e02  mov     rcx, rbp; cb
0x180033e05  call    cs:__imp_CoTaskMemAlloc
0x180033e0b  mov     [rdi+8], rax
0x180033e0f  test    rax, rax
0x180033e12  jz      short loc_180033E2D
0x180033e14  mov     r9, rbp; SourceSize
0x180033e17  mov     r8, rsi; Source
0x180033e1a  mov     rdx, rbp; DestinationSize
0x180033e1d  mov     rcx, rax; Destination
0x180033e20  call    cs:__imp_memcpy_s
0x180033e26  mov     word ptr [rdi], 1Fh
0x180033e2b  jmp     short loc_180033E3E
0x180033e2d  mov     ebx, 8007000Eh
0x180033e32  xorps   xmm0, xmm0
0x180033e35  xor     eax, eax
0x180033e37  movups  xmmword ptr [rdi], xmm0
0x180033e3a  mov     [rdi+10h], rax
0x180033e3e  mov     eax, ebx
0x180033e40  add     rsp, 28h
0x180033e44  pop     rdi
0x180033e45  pop     rsi
0x180033e46  pop     rbp
0x180033e47  pop     rbx
0x180033e48  retn
```
