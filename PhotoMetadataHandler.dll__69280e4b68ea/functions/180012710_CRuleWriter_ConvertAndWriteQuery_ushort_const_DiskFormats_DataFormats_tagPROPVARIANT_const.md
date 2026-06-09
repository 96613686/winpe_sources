# CRuleWriter::ConvertAndWriteQuery(ushort const *,DiskFormats,DataFormats,tagPROPVARIANT const *)

- ea: `0x180012710`
- end: `0x1800127db`
- name: `?ConvertAndWriteQuery@CRuleWriter@@MEAAJPEBGW4DiskFormats@@W4DataFormats@@PEBUtagPROPVARIANT@@@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012160`
- `0x180012660`

## callees

- `0x180012710`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012743`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012743`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800127c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800127c1`

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
0x180012710  push    rbx
0x180012712  push    rbp
0x180012713  push    rsi
0x180012714  push    rdi
0x180012715  push    r14
0x180012717  sub     rsp, 40h
0x18001271b  mov     esi, r9d
0x18001271e  mov     ebp, r8d
0x180012721  mov     r14, rdx
0x180012724  mov     rdi, rcx
0x180012727  xorps   xmm0, xmm0
0x18001272a  xor     eax, eax
0x18001272c  movups  xmmword ptr [rsp+68h+pvarDest], xmm0
0x180012731  mov     qword ptr [rsp+68h+pvarDest+10h], rax
0x180012736  mov     rdx, [rsp+68h+pvarSrc]; pvarSrc
0x18001273e  lea     rcx, [rsp+68h+pvarDest]; pvarDest
0x180012743  call    cs:__imp_PropVariantCopy
0x18001274a  nop     dword ptr [rax+rax+00h]
0x18001274f  mov     ebx, eax
0x180012751  test    eax, eax
0x180012753  js      short loc_1800127AB
0x180012755  mov     rax, [rdi]
0x180012758  lea     r8, [rsp+68h+pvarDest]
0x18001275d  mov     edx, esi
0x18001275f  mov     rcx, rdi
0x180012762  mov     rax, [rax+48h]
0x180012766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001276b  mov     ebx, eax
0x18001276d  test    eax, eax
0x18001276f  js      short loc_1800127AB
0x180012771  mov     rax, [rdi]
0x180012774  lea     r8, [rsp+68h+pvarDest]
0x180012779  mov     edx, ebp
0x18001277b  mov     rcx, rdi
0x18001277e  mov     rax, [rax+50h]
0x180012782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012787  mov     ebx, eax
0x180012789  test    eax, eax
0x18001278b  js      short loc_1800127AB
0x18001278d  mov     rcx, [rdi+28h]
0x180012791  mov     rax, [rcx]
0x180012794  lea     r8, [rsp+68h+pvarDest]
0x180012799  mov     rdx, r14
0x18001279c  mov     rax, [rax+38h]
0x1800127a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a5  mov     ebx, eax
0x1800127a7  test    eax, eax
0x1800127a9  jns     short loc_1800127BC
0x1800127ab  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800127b2  jz      short loc_1800127BC
0x1800127b4  mov     ecx, eax; int
0x1800127b6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800127bb  nop
0x1800127bc  lea     rcx, [rsp+68h+pvarDest]; pvar
0x1800127c1  call    cs:__imp_PropVariantClear
0x1800127c8  nop     dword ptr [rax+rax+00h]
0x1800127cd  mov     eax, ebx
0x1800127cf  add     rsp, 40h
0x1800127d3  pop     r14
0x1800127d5  pop     rdi
0x1800127d6  pop     rsi
0x1800127d7  pop     rbp
0x1800127d8  pop     rbx
0x1800127d9  retn
```
