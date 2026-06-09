# CRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)

- ea: `0x180011e80`
- end: `0x180011f3e`
- name: `?ConvertAndWriteQuery@CRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011940`
- `0x180011dd0`

## callees

- `0x180011e80`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011eb3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011eb3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f2b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleWriter::ConvertAndWriteQuery(
        _QWORD **a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        PROPVARIANT *pvarSrc)
{
  HRESULT v9; // eax
  unsigned int v10; // ebx
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-48h] BYREF

  memset(&pvarDest, 0, sizeof(pvarDest));
  v9 = PropVariantCopy(&pvarDest, pvarSrc);
  v10 = v9;
  if ( v9 < 0
    || (v9 = ((__int64 (__fastcall *)(_QWORD **, _QWORD, PROPVARIANT *))(*a1)[9])(a1, a4, &pvarDest), v10 = v9, v9 < 0)
    || (v9 = ((__int64 (__fastcall *)(_QWORD **, _QWORD, PROPVARIANT *))(*a1)[10])(a1, a3, &pvarDest), v10 = v9, v9 < 0)
    || (v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64, PROPVARIANT *))(*a1[5] + 56LL))(a1[5], a2, &pvarDest),
        v10 = v9,
        v9 < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v9);
  }
  PropVariantClear(&pvarDest);
  return v10;
}

```

## disassembly

```asm
0x180011e80  push    rbx
0x180011e82  push    rbp
0x180011e83  push    rsi
0x180011e84  push    rdi
0x180011e85  push    r14
0x180011e87  sub     rsp, 40h
0x180011e8b  mov     esi, r9d
0x180011e8e  mov     ebp, r8d
0x180011e91  mov     r14, rdx
0x180011e94  mov     rdi, rcx
0x180011e97  xorps   xmm0, xmm0
0x180011e9a  xor     eax, eax
0x180011e9c  movups  xmmword ptr [rsp+68h+pvarDest], xmm0
0x180011ea1  mov     qword ptr [rsp+68h+pvarDest+10h], rax
0x180011ea6  mov     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x180011eae  lea     rcx, [rsp+68h+pvarDest]; pvarDest
0x180011eb3  call    cs:__imp_PropVariantCopy
0x180011eb9  mov     ebx, eax
0x180011ebb  test    eax, eax
0x180011ebd  js      short loc_180011F15
0x180011ebf  mov     rax, [rdi]
0x180011ec2  lea     r8, [rsp+68h+pvarDest]
0x180011ec7  mov     edx, esi
0x180011ec9  mov     rcx, rdi
0x180011ecc  mov     rax, [rax+48h]
0x180011ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed5  mov     ebx, eax
0x180011ed7  test    eax, eax
0x180011ed9  js      short loc_180011F15
0x180011edb  mov     rax, [rdi]
0x180011ede  lea     r8, [rsp+68h+pvarDest]
0x180011ee3  mov     edx, ebp
0x180011ee5  mov     rcx, rdi
0x180011ee8  mov     rax, [rax+50h]
0x180011eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef1  mov     ebx, eax
0x180011ef3  test    eax, eax
0x180011ef5  js      short loc_180011F15
0x180011ef7  mov     rcx, [rdi+28h]
0x180011efb  mov     rax, [rcx]
0x180011efe  lea     r8, [rsp+68h+pvarDest]
0x180011f03  mov     rdx, r14
0x180011f06  mov     rax, [rax+38h]
0x180011f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f0f  mov     ebx, eax
0x180011f11  test    eax, eax
0x180011f13  jns     short loc_180011F26
0x180011f15  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011f1c  jz      short loc_180011F26
0x180011f1e  mov     ecx, eax; int
0x180011f20  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011f25  nop
0x180011f26  lea     rcx, [rsp+68h+pvarDest]; pvar
0x180011f2b  call    cs:__imp_PropVariantClear
0x180011f31  mov     eax, ebx
0x180011f33  add     rsp, 40h
0x180011f37  pop     r14
0x180011f39  pop     rdi
0x180011f3a  pop     rsi
0x180011f3b  pop     rbp
0x180011f3c  pop     rbx
0x180011f3d  retn
```
