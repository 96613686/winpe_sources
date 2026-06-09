# CDateRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000f610`
- end: `0x18000f6da`
- name: `?ConvertDataFormatOnRead@CDateRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `202`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f610`
- `0x18000f6e0`
- `0x18001079c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f64e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f64e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000f6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f663`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f683`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f6bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f663`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f683`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f6bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDateRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  HRESULT v4; // ebx
  int v5; // edx
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  v5 = a2 - 5;
  if ( !v5 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v4 = PropVariantCopy(&pvarDest, a3);
    if ( v4 >= 0 )
    {
      PropVariantClear(a3);
      v4 = ConvertXMPDateStringOnRead(&pvarDest, a3);
    }
    goto LABEL_6;
  }
  if ( v5 == 1 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v4 = PropVariantCopy(&pvarDest, a3);
    if ( v4 >= 0 )
    {
      PropVariantClear(a3);
      v4 = ConvertGPSDateStringOnRead(&pvarDest, a3);
    }
LABEL_6:
    PropVariantClear(&pvarDest);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f610  mov     [rsp+arg_0], rbx
0x18000f615  push    rdi
0x18000f616  sub     rsp, 40h
0x18000f61a  mov     rdi, r8
0x18000f61d  xor     ebx, ebx
0x18000f61f  sub     edx, 5
0x18000f622  jz      short loc_18000F691
0x18000f624  cmp     edx, 1
0x18000f627  jz      short loc_18000F637
0x18000f629  mov     eax, ebx
0x18000f62b  mov     rbx, [rsp+48h+arg_0]
0x18000f630  add     rsp, 40h
0x18000f634  pop     rdi
0x18000f635  retn
0x18000f637  xorps   xmm0, xmm0
0x18000f63a  xor     eax, eax
0x18000f63c  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000f641  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000f646  mov     rdx, rdi; pvarSrc
0x18000f649  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000f64e  call    cs:__imp_PropVariantCopy
0x18000f655  nop     dword ptr [rax+rax+00h]
0x18000f65a  mov     ebx, eax
0x18000f65c  test    eax, eax
0x18000f65e  js      short loc_18000F67E
0x18000f660  mov     rcx, rdi; pvar
0x18000f663  call    cs:__imp_PropVariantClear
0x18000f66a  nop     dword ptr [rax+rax+00h]
0x18000f66f  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000f672  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x18000f677  call    ?ConvertGPSDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertGPSDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000f67c  mov     ebx, eax
0x18000f67e  lea     rcx, [rsp+48h+pvarDest]; pvar
0x18000f683  call    cs:__imp_PropVariantClear
0x18000f68a  nop     dword ptr [rax+rax+00h]
0x18000f68f  jmp     short loc_18000F629
0x18000f691  xorps   xmm0, xmm0
0x18000f694  xor     eax, eax
0x18000f696  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000f69b  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000f6a0  mov     rdx, rdi; pvarSrc
0x18000f6a3  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000f6a8  call    cs:__imp_PropVariantCopy
0x18000f6af  nop     dword ptr [rax+rax+00h]
0x18000f6b4  mov     ebx, eax
0x18000f6b6  test    eax, eax
0x18000f6b8  js      short loc_18000F6D8
0x18000f6ba  mov     rcx, rdi; pvar
0x18000f6bd  call    cs:__imp_PropVariantClear
0x18000f6c4  nop     dword ptr [rax+rax+00h]
0x18000f6c9  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000f6cc  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x18000f6d1  call    ?ConvertXMPDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertXMPDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000f6d6  mov     ebx, eax
0x18000f6d8  jmp     short loc_18000F67E
```
