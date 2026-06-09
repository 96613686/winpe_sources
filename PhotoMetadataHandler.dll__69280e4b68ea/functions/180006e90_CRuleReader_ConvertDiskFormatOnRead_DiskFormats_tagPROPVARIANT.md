# CRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x180006e90`
- end: `0x180006fb4`
- name: `?ConvertDiskFormatOnRead@CRuleReader@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `292`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006e90`
- `0x180006fc0`
- `0x180007390`
- `0x18001f970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006f54`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006f8e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006f54`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006f8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006efa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006f2d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006efa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006f2d`

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
0x180006e90  mov     [rsp+arg_0], rbx
0x180006e95  push    rdi
0x180006e96  sub     rsp, 40h
0x180006e9a  mov     rbx, r8
0x180006e9d  cmp     edx, 4
0x180006ea0  jz      loc_180006F3D
0x180006ea6  cmp     edx, 2
0x180006ea9  jz      loc_180006F77
0x180006eaf  movzx   ecx, word ptr [r8]
0x180006eb3  mov     eax, 1Eh
0x180006eb8  cmp     ax, cx
0x180006ebb  jz      short loc_180006ED5
0x180006ebd  mov     edx, 101Eh
0x180006ec2  cmp     dx, cx
0x180006ec5  jz      short loc_180006ED5
0x180006ec7  xor     eax, eax
0x180006ec9  mov     rbx, [rsp+48h+arg_0]
0x180006ece  add     rsp, 40h
0x180006ed2  pop     rdi
0x180006ed3  retn
0x180006ed5  xorps   xmm0, xmm0
0x180006ed8  xor     eax, eax
0x180006eda  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180006edf  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180006ee4  lea     rdx, [rsp+48h+pvar]; pvarDest
0x180006ee9  mov     rcx, rbx; pvarSrc
0x180006eec  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006ef1  mov     edi, eax
0x180006ef3  test    eax, eax
0x180006ef5  js      short loc_180006F28
0x180006ef7  mov     rcx, rbx; pvar
0x180006efa  call    cs:__imp_PropVariantClear
0x180006f01  nop     dword ptr [rax+rax+00h]
0x180006f06  movups  xmm0, xmmword ptr [rsp+48h+pvar]
0x180006f0b  movups  xmmword ptr [rbx], xmm0
0x180006f0e  movsd   xmm1, qword ptr [rsp+48h+pvar+10h]
0x180006f14  movsd   qword ptr [rbx+10h], xmm1
0x180006f19  xorps   xmm0, xmm0
0x180006f1c  xor     eax, eax
0x180006f1e  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180006f23  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180006f28  lea     rcx, [rsp+48h+pvar]; pvar
0x180006f2d  call    cs:__imp_PropVariantClear
0x180006f34  nop     dword ptr [rax+rax+00h]
0x180006f39  mov     eax, edi
0x180006f3b  jmp     short loc_180006EC9
0x180006f3d  xorps   xmm0, xmm0
0x180006f40  xor     eax, eax
0x180006f42  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180006f47  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180006f4c  mov     rdx, rbx; pvarSrc
0x180006f4f  lea     rcx, [rsp+48h+pvar]; pvarDest
0x180006f54  call    cs:__imp_PropVariantCopy
0x180006f5b  nop     dword ptr [rax+rax+00h]
0x180006f60  mov     edi, eax
0x180006f62  test    eax, eax
0x180006f64  js      short loc_180006F75
0x180006f66  mov     rdx, rbx; pvarDest
0x180006f69  lea     rcx, [rsp+48h+pvar]; pvarSrc
0x180006f6e  call    ?ConvertExifVersionOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertExifVersionOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006f73  mov     edi, eax
0x180006f75  jmp     short loc_180006F28
0x180006f77  xorps   xmm0, xmm0
0x180006f7a  xor     eax, eax
0x180006f7c  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180006f81  mov     qword ptr [rsp+48h+pvar+10h], rax
0x180006f86  mov     rdx, rbx; pvarSrc
0x180006f89  lea     rcx, [rsp+48h+pvar]; pvarDest
0x180006f8e  call    cs:__imp_PropVariantCopy
0x180006f95  nop     dword ptr [rax+rax+00h]
0x180006f9a  mov     edi, eax
0x180006f9c  test    eax, eax
0x180006f9e  js      short loc_180006F28
0x180006fa0  mov     rdx, rbx; struct tagPROPVARIANT *
0x180006fa3  lea     rcx, [rsp+48h+pvar]; struct tagPROPVARIANT *
0x180006fa8  call    ?ConvertBytesToLPWSTROnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertBytesToLPWSTROnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006fad  mov     edi, eax
0x180006faf  jmp     loc_180006F28
```
