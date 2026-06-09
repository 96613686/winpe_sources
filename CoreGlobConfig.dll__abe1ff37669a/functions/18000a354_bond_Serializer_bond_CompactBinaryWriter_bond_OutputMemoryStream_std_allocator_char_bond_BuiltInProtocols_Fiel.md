# bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>::Field<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(ushort,bond::Metadata const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000a354`
- end: `0x18000a418`
- name: `??$Field@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@UBuiltInProtocols@2@@bond@@QEBA_NGAEBUMetadata@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `196`
- prototype: `char __fastcall(_QWORD *, unsigned __int16, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a998`

## callees

- `0x18000a354`
- `0x18000c178`
- `0x18000c1b0`
- `0x18000c1ec`
- `0x18000e71c`
- `0x18001bcc0`
- `0x18001d564`

## pseudocode

```c
char __fastcall bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>,bond::BuiltInProtocols>::Field<std::wstring>(
        _QWORD *a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rax
  _WORD v13[12]; // [rsp+20h] [rbp-18h] BYREF
  char v14; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_DWORD *)(a3 + 80) || !(unsigned __int8)bond::detail::is_default<std::wstring>(a4, a3) )
  {
    v7 = (_QWORD *)*a1;
    v13[0] = a2;
    if ( a2 > 5u )
    {
      v8 = *v7;
      if ( a2 > 0xFFu )
      {
        v14 = -14;
        bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v8, &v14);
        bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(*v7, v13);
        goto LABEL_9;
      }
      v14 = -46;
      bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v8, &v14);
    }
    else
    {
      LOBYTE(a2) = (32 * a2) | 0x12;
    }
    v9 = *v7;
    v14 = a2;
    bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v9, &v14);
LABEL_9:
    v10 = *(_DWORD *)(a4 + 16);
    bond::WriteVariableUnsigned<bond::OutputMemoryStream<std::allocator<char>>,unsigned int>(*v7, v10);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    bond::OutputMemoryStream<std::allocator<char>>::Write(*v7, v11, 2 * v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a354  mov     [rsp+arg_0], rbx
0x18000a359  mov     [rsp+arg_8], rsi
0x18000a35e  push    rdi
0x18000a35f  sub     rsp, 30h
0x18000a363  cmp     dword ptr [r8+50h], 0
0x18000a368  mov     rsi, r9
0x18000a36b  movzx   ebx, dx
0x18000a36e  mov     rdi, rcx
0x18000a371  jnz     short loc_18000A386
0x18000a373  mov     rdx, r8
0x18000a376  mov     rcx, r9
0x18000a379  call    ??$is_default@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@detail@bond@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUMetadata@1@@Z; bond::detail::is_default<std::wstring>(std::wstring const &,bond::Metadata const &)
0x18000a37e  test    al, al
0x18000a380  jnz     loc_18000A406
0x18000a386  mov     rdi, [rdi]
0x18000a389  mov     [rsp+38h+var_18], bx
0x18000a38e  cmp     bx, 5
0x18000a392  ja      short loc_18000A39C
0x18000a394  shl     bl, 5
0x18000a397  or      bl, 12h
0x18000a39a  jmp     short loc_18000A3B8
0x18000a39c  mov     rcx, [rdi]
0x18000a39f  lea     rdx, [rsp+38h+arg_10]
0x18000a3a4  mov     eax, 0FFh
0x18000a3a9  cmp     bx, ax
0x18000a3ac  ja      short loc_18000A3CB
0x18000a3ae  mov     [rsp+38h+arg_10], 0D2h
0x18000a3b3  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a3b8  mov     rcx, [rdi]
0x18000a3bb  lea     rdx, [rsp+38h+arg_10]
0x18000a3c0  mov     [rsp+38h+arg_10], bl
0x18000a3c4  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a3c9  jmp     short loc_18000A3E2
0x18000a3cb  mov     [rsp+38h+arg_10], 0F2h
0x18000a3d0  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a3d5  mov     rcx, [rdi]
0x18000a3d8  lea     rdx, [rsp+38h+var_18]
0x18000a3dd  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18000a3e2  mov     ebx, [rsi+10h]
0x18000a3e5  mov     edx, ebx
0x18000a3e7  mov     rcx, [rdi]
0x18000a3ea  call    ??$WriteVariableUnsigned@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@I@bond@@YAXAEAV?$OutputMemoryStream@V?$allocator@D@std@@@0@I@Z; bond::WriteVariableUnsigned<bond::OutputMemoryStream<std::allocator<char>>,uint>(bond::OutputMemoryStream<std::allocator<char>> &,uint)
0x18000a3ef  mov     rcx, rsi
0x18000a3f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000a3f7  mov     rcx, [rdi]
0x18000a3fa  lea     r8d, [rbx+rbx]
0x18000a3fe  mov     rdx, rax
0x18000a401  call    ?Write@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXPEBXI@Z; bond::OutputMemoryStream<std::allocator<char>>::Write(void const *,uint)
0x18000a406  mov     rbx, [rsp+38h+arg_0]
0x18000a40b  xor     al, al
0x18000a40d  mov     rsi, [rsp+38h+arg_8]
0x18000a412  add     rsp, 30h
0x18000a416  pop     rdi
0x18000a417  retn
```
