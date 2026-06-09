# CRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x180008370`
- end: `0x18000848b`
- name: `?ConvertDiskFormatOnRead@CRuleReader@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `283`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008370`
- `0x1800084a0`
- `0x180008840`
- `0x18001eaec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008427`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000846b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008427`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000846b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800083d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008447`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800083d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008447`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleReader::ConvertDiskFormatOnRead(__int64 a1, int a2, PROPVARIANT *a3)
{
  int v5; // edi
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 == 4 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v5 = PropVariantCopy(&pvar, a3);
    if ( v5 >= 0 )
      v5 = ConvertExifVersionOnRead(&pvar, a3);
  }
  else if ( a2 == 2 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v5 = PropVariantCopy(&pvar, a3);
    if ( v5 >= 0 )
      v5 = ConvertBytesToLPWSTROnRead(&pvar, a3);
  }
  else
  {
    if ( a3->vt != 30 && a3->vt != 4126 )
      return 0;
    memset(&pvar, 0, sizeof(pvar));
    v5 = SniffAndConvertToWideString(a3, &pvar);
    if ( v5 >= 0 )
    {
      PropVariantClear(a3);
      *a3 = pvar;
      memset(&pvar, 0, sizeof(pvar));
    }
  }
  PropVariantClear(&pvar);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008370  mov     [rsp+arg_0], rbx
0x180008375  push    rdi
0x180008376  sub     rsp, 40h
0x18000837a  mov     rbx, r8
0x18000837d  cmp     edx, 4
0x180008380  jz      loc_180008410
0x180008386  cmp     edx, 2
0x180008389  jz      loc_180008454
0x18000838f  movzx   ecx, word ptr [r8]
0x180008393  mov     eax, 1Eh
0x180008398  cmp     ax, cx
0x18000839b  jz      short loc_1800083B4
0x18000839d  mov     edx, 101Eh
0x1800083a2  cmp     dx, cx
0x1800083a5  jz      short loc_1800083B4
0x1800083a7  xor     eax, eax
0x1800083a9  mov     rbx, [rsp+48h+arg_0]
0x1800083ae  add     rsp, 40h
0x1800083b2  pop     rdi
0x1800083b3  retn
0x1800083b4  xorps   xmm0, xmm0
0x1800083b7  xor     eax, eax
0x1800083b9  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x1800083be  mov     qword ptr [rsp+48h+pvar+10h], rax
0x1800083c3  lea     rdx, [rsp+48h+pvar]; pvarDest
0x1800083c8  mov     rcx, rbx; pvarSrc
0x1800083cb  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800083d0  mov     edi, eax
0x1800083d2  test    eax, eax
0x1800083d4  js      short loc_180008401
0x1800083d6  mov     rcx, rbx; pvar
0x1800083d9  call    cs:__imp_PropVariantClear
0x1800083df  movups  xmm0, xmmword ptr [rsp+48h+pvar]
0x1800083e4  movups  xmmword ptr [rbx], xmm0
0x1800083e7  movsd   xmm1, qword ptr [rsp+48h+pvar+10h]
0x1800083ed  movsd   qword ptr [rbx+10h], xmm1
0x1800083f2  xorps   xmm0, xmm0
0x1800083f5  xor     eax, eax
0x1800083f7  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x1800083fc  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180008401  lea     rcx, [rsp+48h+pvar]; pvar
0x180008406  call    cs:__imp_PropVariantClear
0x18000840c  mov     eax, edi
0x18000840e  jmp     short loc_1800083A9
0x180008410  xorps   xmm0, xmm0
0x180008413  xor     eax, eax
0x180008415  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18000841a  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18000841f  mov     rdx, rbx; pvarSrc
0x180008422  lea     rcx, [rsp+48h+pvar]; pvarDest
0x180008427  call    cs:__imp_PropVariantCopy
0x18000842d  mov     edi, eax
0x18000842f  test    eax, eax
0x180008431  js      short loc_180008442
0x180008433  mov     rdx, rbx; pvarDest
0x180008436  lea     rcx, [rsp+48h+pvar]; pvarSrc
0x18000843b  call    ?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008440  mov     edi, eax
0x180008442  lea     rcx, [rsp+48h+pvar]; pvar
0x180008447  call    cs:__imp_PropVariantClear
0x18000844d  mov     eax, edi
0x18000844f  jmp     loc_1800083A9
0x180008454  xorps   xmm0, xmm0
0x180008457  xor     eax, eax
0x180008459  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x18000845e  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180008463  mov     rdx, rbx; pvarSrc
0x180008466  lea     rcx, [rsp+48h+pvar]; pvarDest
0x18000846b  call    cs:__imp_PropVariantCopy
0x180008471  mov     edi, eax
0x180008473  test    eax, eax
0x180008475  js      short loc_180008401
0x180008477  mov     rdx, rbx; struct tagPROPVARIANT *
0x18000847a  lea     rcx, [rsp+48h+pvar]; struct tagPROPVARIANT *
0x18000847f  call    ?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008484  mov     edi, eax
0x180008486  jmp     loc_180008401
```
