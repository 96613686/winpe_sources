# bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType,ushort)

- ea: `0x180022850`
- end: `0x1800228cf`
- name: `?WriteFieldBegin@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@G@Z`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c5f8`
- `0x18000c6a8`
- `0x18000c768`
- `0x18000c830`
- `0x18001bce4`

## callees

- `0x180011bcc`
- `0x180011c04`
- `0x180022850`

## pseudocode

```c
char __fastcall bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(
        __int64 *a1,
        char a2,
        unsigned __int16 a3)
{
  __int64 v4; // rcx
  char v5; // bl
  unsigned __int16 v7; // [rsp+40h] [rbp+18h] BYREF
  char v8; // [rsp+48h] [rbp+20h] BYREF

  v7 = a3;
  v4 = *a1;
  v5 = a3;
  if ( a3 <= 5u )
  {
    v5 = a2 | (32 * a3);
LABEL_5:
    LOBYTE(v7) = v5;
    return bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v4, (char *)&v7);
  }
  if ( a3 <= 0xFFu )
  {
    LOBYTE(v7) = a2 | 0xC0;
    bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v4, (char *)&v7);
    v4 = *a1;
    goto LABEL_5;
  }
  v8 = a2 | 0xE0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v4, &v8);
  return bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(*a1, &v7);
}

```

## disassembly

```asm
0x180022850  mov     [rsp+arg_0], rbx
0x180022855  mov     [rsp+arg_10], r8w
0x18002285b  push    rdi
0x18002285c  sub     rsp, 20h
0x180022860  mov     rdi, rcx
0x180022863  mov     rcx, [rcx]
0x180022866  movzx   ebx, r8w
0x18002286a  cmp     r8w, 5
0x18002286f  ja      short loc_180022878
0x180022871  shl     bl, 5
0x180022874  or      bl, dl
0x180022876  jmp     short loc_180022896
0x180022878  mov     eax, 0FFh
0x18002287d  cmp     bx, ax
0x180022880  ja      short loc_1800228A6
0x180022882  or      dl, 0C0h
0x180022885  mov     byte ptr [rsp+28h+arg_10], dl
0x180022889  lea     rdx, [rsp+28h+arg_10]
0x18002288e  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x180022893  mov     rcx, [rdi]
0x180022896  lea     rdx, [rsp+28h+arg_10]
0x18002289b  mov     byte ptr [rsp+28h+arg_10], bl
0x18002289f  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x1800228a4  jmp     short loc_1800228C4
0x1800228a6  or      dl, 0E0h
0x1800228a9  mov     [rsp+28h+arg_18], dl
0x1800228ad  lea     rdx, [rsp+28h+arg_18]
0x1800228b2  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x1800228b7  mov     rcx, [rdi]
0x1800228ba  lea     rdx, [rsp+28h+arg_10]
0x1800228bf  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x1800228c4  mov     rbx, [rsp+28h+arg_0]
0x1800228c9  add     rsp, 20h
0x1800228cd  pop     rdi
0x1800228ce  retn
```
