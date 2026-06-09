# RfbFileFolderWmiQuery::Query(ulong)

- ea: `0x1800149a0`
- end: `0x180014a32`
- name: `?Query@RfbFileFolderWmiQuery@@UEAAXK@Z`
- size: `146`
- prototype: `void __fastcall(RfbFileFolderWmiQuery *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180010fc0`
- `0x180013b1c`
- `0x1800149a0`
- `0x180017174`

## string_xrefs

- `0x1800149fd`: `ASSOCIATORS OF {CIM_Directory.Name="%s"} WHERE AssocClass = CIM_DirectoryContainsFile ResultRole = PartComponent `
- `0x1800149ca`: `Associators of {Win32_Directory.Name="%s"} WHERE AssocClass = Win32_SubDirectory ResultRole = PartComponent `

## pseudocode

```c
void __fastcall RfbFileFolderWmiQuery::Query(RfbFileFolderWmiQuery *this, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  _BYTE Src[40]; // [rsp+20h] [rbp-28h] BYREF

  v4 = FormatString(
         Src,
         (wchar_t *)L"Associators of {Win32_Directory.Name=\"%s\"} WHERE AssocClass = Win32_SubDirectory ResultRole = PartComponent ");
  RfbWmiQuery::AddWmiQuery(this, v4);
  if ( a2 && (a2 & 0x40) != 0 )
  {
    v5 = FormatString(
           Src,
           (wchar_t *)L"ASSOCIATORS OF {CIM_Directory.Name=\"%s\"} WHERE AssocClass = CIM_DirectoryContainsFile ResultRole"
                       " = PartComponent ");
    RfbWmiQuery::AddWmiQuery(this, v5);
  }
  RfbWmiQuery::Query(this, a2);
}

```

## disassembly

```asm
0x1800149a0  mov     [rsp+arg_8], rbx
0x1800149a5  mov     [rsp+arg_10], rsi
0x1800149aa  push    rdi
0x1800149ab  sub     rsp, 40h
0x1800149af  lea     rbx, [rcx+0C0h]
0x1800149b6  mov     esi, edx
0x1800149b8  cmp     qword ptr [rbx+18h], 7
0x1800149bd  mov     rdi, rcx
0x1800149c0  jbe     short loc_1800149C7
0x1800149c2  mov     r8, [rbx]
0x1800149c5  jmp     short loc_1800149CA
0x1800149c7  mov     r8, rbx
0x1800149ca  lea     rdx, ?gm_Win32SubDirectoryAssociatorQueryFormat@RfbFileFolderWmiQuery@@0QBGB; "Associators of {Win32_Directory.Name=\""...
0x1800149d1  lea     rcx, [rsp+48h+Src]; Src
0x1800149d6  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; FormatString(ushort const *,...)
0x1800149db  mov     rdx, rax
0x1800149de  mov     rcx, rdi
0x1800149e1  call    ?AddWmiQuery@RfbWmiQuery@@IEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::AddWmiQuery(std::wstring)
0x1800149e6  test    esi, esi
0x1800149e8  jz      short loc_180014A19
0x1800149ea  test    sil, 40h
0x1800149ee  jz      short loc_180014A19
0x1800149f0  cmp     qword ptr [rbx+18h], 7
0x1800149f5  jbe     short loc_1800149FA
0x1800149f7  mov     rbx, [rbx]
0x1800149fa  mov     r8, rbx
0x1800149fd  lea     rdx, ?gm_CimDirectoryContainsFilesAssociatorQueryFormat@RfbFileFolderWmiQuery@@0QBGB; "ASSOCIATORS OF {CIM_Directory.Name=\"%s"...
0x180014a04  lea     rcx, [rsp+48h+Src]; Src
0x180014a09  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; FormatString(ushort const *,...)
0x180014a0e  mov     rdx, rax
0x180014a11  mov     rcx, rdi
0x180014a14  call    ?AddWmiQuery@RfbWmiQuery@@IEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::AddWmiQuery(std::wstring)
0x180014a19  mov     edx, esi; unsigned int
0x180014a1b  mov     rcx, rdi; this
0x180014a1e  mov     rbx, [rsp+48h+arg_8]
0x180014a23  mov     rsi, [rsp+48h+arg_10]
0x180014a28  add     rsp, 40h
0x180014a2c  pop     rdi
0x180014a2d  jmp     ?Query@RfbWmiQuery@@UEAAXK@Z; RfbWmiQuery::Query(ulong)
```
