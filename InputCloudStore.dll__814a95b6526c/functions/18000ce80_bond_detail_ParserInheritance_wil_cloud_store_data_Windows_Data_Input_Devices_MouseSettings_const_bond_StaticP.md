# bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &>>::Read<Windows::Data::Input::Devices::MouseSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(Windows::Data::Input::Devices::MouseSettings::Schema const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &)

- ea: `0x18000ce80`
- end: `0x18000cf68`
- name: `??$Read@USchema@MouseSettings@Devices@Input@Data@Windows@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$ParserInheritance@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$StaticParser@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@detail@bond@@IEAA_NAEBUSchema@MouseSettings@Devices@Input@Data@Windows@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@2@@Z`
- size: `232`
- prototype: `char __fastcall(_WORD **, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009fd0`

## callees

- `0x18000c5f8`
- `0x18000c830`
- `0x18000ce80`
- `0x180011bcc`
- `0x180011cac`

## pseudocode

```c
char __fastcall bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &>>::Read<Windows::Data::Input::Devices::MouseSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(
        _WORD **a1,
        __int64 a2,
        _BYTE *a3)
{
  _QWORD *v5; // rcx
  unsigned int *v6; // rdx
  char v7; // di
  __int64 v8; // rcx
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = a2;
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
  v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<unsigned short>(
         a3,
         0,
         (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_mousePointerSpeed_metadata,
         *a1);
  if ( !v7 )
  {
    v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
           a3,
           1u,
           (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollPage_metadata,
           (_BYTE *)*a1 + 2);
    if ( !v7 )
    {
      v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<unsigned short>(
             a3,
             2u,
             (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata,
             *a1 + 2);
      if ( !v7 )
        v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
               a3,
               3u,
               (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata,
               (_BYTE *)*a1 + 6);
    }
  }
  v8 = **(_QWORD **)a3;
  LOBYTE(v10) = a3[8] != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v8, &v10);
  return v7;
}

```

## disassembly

```asm
0x18000ce80  mov     [rsp+arg_8], rdx
0x18000ce85  push    rbx
0x18000ce86  push    rsi
0x18000ce87  push    rdi
0x18000ce88  push    r14
0x18000ce8a  sub     rsp, 28h
0x18000ce8e  cmp     byte ptr [r8+8], 0
0x18000ce93  mov     rbx, r8
0x18000ce96  mov     rsi, rcx
0x18000ce99  mov     r14d, 2
0x18000ce9f  jnz     short loc_18000CEC1
0x18000cea1  mov     rcx, [r8]
0x18000cea4  cmp     r14w, [rcx+10h]
0x18000cea9  jnz     short loc_18000CEC1
0x18000ceab  mov     rdx, [rcx+8]
0x18000ceaf  lea     rax, [rdx+4]
0x18000ceb3  mov     [rcx+8], rax
0x18000ceb7  mov     edx, [rdx]
0x18000ceb9  mov     rcx, [rcx]
0x18000cebc  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000cec1  mov     r9, [rsi]
0x18000cec4  lea     r8, ?s_mousePointerSpeed_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_mousePointerSpeed_metadata
0x18000cecb  xor     edx, edx
0x18000cecd  mov     rcx, rbx
0x18000ced0  call    ??$Field@G@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)
0x18000ced5  mov     dil, al
0x18000ced8  test    al, al
0x18000ceda  jnz     short loc_18000CF3B
0x18000cedc  mov     r9, [rsi]
0x18000cedf  lea     r8, ?s_allowScrollPage_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollPage_metadata
0x18000cee6  add     r9, r14
0x18000cee9  mov     edx, 1
0x18000ceee  mov     rcx, rbx
0x18000cef1  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000cef6  mov     dil, al
0x18000cef9  test    al, al
0x18000cefb  jnz     short loc_18000CF3B
0x18000cefd  mov     r9, [rsi]
0x18000cf00  lea     r8, ?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata
0x18000cf07  add     r9, 4
0x18000cf0b  mov     edx, r14d
0x18000cf0e  mov     rcx, rbx
0x18000cf11  call    ??$Field@G@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)
0x18000cf16  mov     dil, al
0x18000cf19  test    al, al
0x18000cf1b  jnz     short loc_18000CF3B
0x18000cf1d  mov     r9, [rsi]
0x18000cf20  lea     r8, ?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata
0x18000cf27  add     r9, 6
0x18000cf2b  mov     edx, 3
0x18000cf30  mov     rcx, rbx
0x18000cf33  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000cf38  mov     dil, al
0x18000cf3b  cmp     byte ptr [rbx+8], 0
0x18000cf3f  lea     rdx, [rsp+48h+arg_8]
0x18000cf44  mov     rax, [rbx]
0x18000cf47  mov     byte ptr [rsp+48h+arg_8], 1
0x18000cf4c  mov     rcx, [rax]
0x18000cf4f  jnz     short loc_18000CF56
0x18000cf51  mov     byte ptr [rsp+48h+arg_8], 0
0x18000cf56  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000cf5b  mov     al, dil
0x18000cf5e  add     rsp, 28h
0x18000cf62  pop     r14
0x18000cf64  pop     rdi
0x18000cf65  pop     rsi
0x18000cf66  pop     rbx
0x18000cf67  retn
```
