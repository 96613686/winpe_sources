# CDateRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000ef00`
- end: `0x18000efab`
- name: `?ConvertDataFormatOnRead@CDateRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `171`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ef00`
- `0x18000efb4`
- `0x18000ff94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ef3d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ef85`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ef3d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000ef85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef4c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ef94`

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
0x18000ef00  mov     [rsp+arg_0], rbx
0x18000ef05  push    rdi
0x18000ef06  sub     rsp, 40h
0x18000ef0a  mov     rdi, r8
0x18000ef0d  xor     ebx, ebx
0x18000ef0f  sub     edx, 5
0x18000ef12  jz      short loc_18000EF6E
0x18000ef14  cmp     edx, 1
0x18000ef17  jz      short loc_18000EF26
0x18000ef19  mov     eax, ebx
0x18000ef1b  mov     rbx, [rsp+48h+arg_0]
0x18000ef20  add     rsp, 40h
0x18000ef24  pop     rdi
0x18000ef25  retn
0x18000ef26  xorps   xmm0, xmm0
0x18000ef29  xor     eax, eax
0x18000ef2b  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000ef30  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000ef35  mov     rdx, rdi; pvarSrc
0x18000ef38  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000ef3d  call    cs:__imp_PropVariantCopy
0x18000ef43  mov     ebx, eax
0x18000ef45  test    eax, eax
0x18000ef47  js      short loc_18000EF61
0x18000ef49  mov     rcx, rdi; pvar
0x18000ef4c  call    cs:__imp_PropVariantClear
0x18000ef52  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000ef55  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x18000ef5a  call    ?ConvertGPSDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertGPSDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000ef5f  mov     ebx, eax
0x18000ef61  lea     rcx, [rsp+48h+pvarDest]; pvar
0x18000ef66  call    cs:__imp_PropVariantClear
0x18000ef6c  jmp     short loc_18000EF19
0x18000ef6e  xorps   xmm0, xmm0
0x18000ef71  xor     eax, eax
0x18000ef73  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x18000ef78  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x18000ef7d  mov     rdx, rdi; pvarSrc
0x18000ef80  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x18000ef85  call    cs:__imp_PropVariantCopy
0x18000ef8b  mov     ebx, eax
0x18000ef8d  test    eax, eax
0x18000ef8f  js      short loc_18000EFA9
0x18000ef91  mov     rcx, rdi; pvar
0x18000ef94  call    cs:__imp_PropVariantClear
0x18000ef9a  mov     rdx, rdi; struct tagPROPVARIANT *
0x18000ef9d  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x18000efa2  call    ?ConvertXMPDateStringOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertXMPDateStringOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000efa7  mov     ebx, eax
0x18000efa9  jmp     short loc_18000EF61
```
