# bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &>>::Read<Windows::Data::Input::Devices::TouchpadSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(Windows::Data::Input::Devices::TouchpadSettings::Schema const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &)

- ea: `0x18000d66c`
- end: `0x18000d70d`
- name: `??$Read@USchema@TouchpadSettings@Devices@Input@Data@Windows@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$ParserInheritance@AEBV?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$StaticParser@AEBV?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@detail@bond@@IEAA_NAEBUSchema@TouchpadSettings@Devices@Input@Data@Windows@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@2@@Z`
- size: `161`
- prototype: `char __fastcall(_WORD **, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a288`

## callees

- `0x18000c5f8`
- `0x18000d66c`
- `0x180011bcc`
- `0x180011cac`
- `0x18001bce4`

## pseudocode

```c
char __fastcall bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &>>::Read<Windows::Data::Input::Devices::TouchpadSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(
        _WORD **a1,
        __int64 a2,
        _BYTE *a3)
{
  _QWORD *v5; // rcx
  unsigned int *v6; // rdx
  __int64 v7; // rdx
  char v8; // di
  __int64 v9; // rcx
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v11 = a2;
  if ( !a3[8] )
  {
    v5 = *(_QWORD **)a3;
    if ( *(_WORD *)(*(_QWORD *)a3 + 16LL) == 2 )
    {
      v6 = (unsigned int *)v5[1];
      v5[1] = v6 + 1;
      bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(*v5, *v6);
    }
  }
  v8 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<unsigned short>(
         a3,
         0,
         (__int64)Windows::Data::Input::Devices::TouchpadSettings::Schema::s_cursorSpeed_metadata,
         *a1);
  if ( !v8 )
    v8 = __(a1, v7, a3);
  v9 = **(_QWORD **)a3;
  LOBYTE(v11) = a3[8] != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v9, &v11);
  return v8;
}

```

## disassembly

```asm
0x18000d66c  mov     [rsp+arg_0], rbx
0x18000d671  mov     [rsp+arg_10], rsi
0x18000d676  mov     [rsp+arg_8], rdx
0x18000d67b  push    rdi
0x18000d67c  sub     rsp, 20h
0x18000d680  cmp     byte ptr [r8+8], 0
0x18000d685  mov     rbx, r8
0x18000d688  mov     rsi, rcx
0x18000d68b  jnz     short loc_18000D6B1
0x18000d68d  mov     rcx, [r8]
0x18000d690  mov     eax, 2
0x18000d695  cmp     ax, [rcx+10h]
0x18000d699  jnz     short loc_18000D6B1
0x18000d69b  mov     rdx, [rcx+8]
0x18000d69f  lea     rax, [rdx+4]
0x18000d6a3  mov     [rcx+8], rax
0x18000d6a7  mov     edx, [rdx]
0x18000d6a9  mov     rcx, [rcx]
0x18000d6ac  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000d6b1  mov     r9, [rsi]
0x18000d6b4  lea     r8, ?s_cursorSpeed_metadata@Schema@TouchpadSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::TouchpadSettings::Schema::s_cursorSpeed_metadata
0x18000d6bb  xor     edx, edx
0x18000d6bd  mov     rcx, rbx
0x18000d6c0  call    ??$Field@G@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)
0x18000d6c5  mov     dil, al
0x18000d6c8  test    al, al
0x18000d6ca  jnz     short loc_18000D6DA
0x18000d6cc  mov     r8, rbx
0x18000d6cf  mov     rcx, rsi
0x18000d6d2  call    ??@122123c46767024e350273e5bcce7adf@
0x18000d6d7  mov     dil, al
0x18000d6da  cmp     byte ptr [rbx+8], 0
0x18000d6de  lea     rdx, [rsp+28h+arg_8]
0x18000d6e3  mov     rcx, [rbx]
0x18000d6e6  mov     byte ptr [rsp+28h+arg_8], 1
0x18000d6eb  mov     rcx, [rcx]
0x18000d6ee  jnz     short loc_18000D6F5
0x18000d6f0  mov     byte ptr [rsp+28h+arg_8], 0
0x18000d6f5  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000d6fa  mov     rbx, [rsp+28h+arg_0]
0x18000d6ff  mov     al, dil
0x18000d702  mov     rsi, [rsp+28h+arg_10]
0x18000d707  add     rsp, 20h
0x18000d70b  pop     rdi
0x18000d70c  retn
```
