# bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &>>::Read<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &)

- ea: `0x18000d334`
- end: `0x18000d3f6`
- name: `??$Read@USchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@@?$ParserInheritance@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$StaticParser@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@detail@bond@@IEAA_NAEBUSchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@AEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@2@@Z`
- size: `194`
- prototype: `char __fastcall(_BYTE **, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a1f8`

## callees

- `0x18000c830`
- `0x18000d334`
- `0x180011bcc`
- `0x180011cac`
- `0x18001bdac`

## pseudocode

```c
char __fastcall bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &>>::Read<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>>(
        _BYTE **a1,
        __int64 a2,
        _BYTE *a3)
{
  _QWORD *v5; // rcx
  unsigned int *v6; // rdx
  char v7; // di
  __int64 v8; // rdx
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
  v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
         a3,
         0,
         (__int64)Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_eyeControlEnabled_metadata,
         *a1);
  if ( !v7 )
  {
    v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
           a3,
           1u,
           (__int64)Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_showGazeCursor_metadata,
           *a1 + 1);
    if ( !v7 )
      v7 = __(a1, v8, a3);
  }
  v9 = **(_QWORD **)a3;
  LOBYTE(v11) = a3[8] != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v9, &v11);
  return v7;
}

```

## disassembly

```asm
0x18000d334  mov     [rsp+arg_0], rbx
0x18000d339  mov     [rsp+arg_10], rsi
0x18000d33e  mov     [rsp+arg_8], rdx
0x18000d343  push    rdi
0x18000d344  sub     rsp, 20h
0x18000d348  cmp     byte ptr [r8+8], 0
0x18000d34d  mov     rbx, r8
0x18000d350  mov     rsi, rcx
0x18000d353  jnz     short loc_18000D379
0x18000d355  mov     rcx, [r8]
0x18000d358  mov     eax, 2
0x18000d35d  cmp     ax, [rcx+10h]
0x18000d361  jnz     short loc_18000D379
0x18000d363  mov     rdx, [rcx+8]
0x18000d367  lea     rax, [rdx+4]
0x18000d36b  mov     [rcx+8], rax
0x18000d36f  mov     edx, [rdx]
0x18000d371  mov     rcx, [rcx]
0x18000d374  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000d379  mov     r9, [rsi]
0x18000d37c  lea     r8, ?s_eyeControlEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_eyeControlEnabled_metadata
0x18000d383  xor     edx, edx
0x18000d385  mov     rcx, rbx
0x18000d388  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000d38d  mov     dil, al
0x18000d390  test    al, al
0x18000d392  jnz     short loc_18000D3C3
0x18000d394  mov     r9, [rsi]
0x18000d397  lea     r8, ?s_showGazeCursor_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_showGazeCursor_metadata
0x18000d39e  inc     r9
0x18000d3a1  mov     edx, 1
0x18000d3a6  mov     rcx, rbx
0x18000d3a9  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000d3ae  mov     dil, al
0x18000d3b1  test    al, al
0x18000d3b3  jnz     short loc_18000D3C3
0x18000d3b5  mov     r8, rbx
0x18000d3b8  mov     rcx, rsi
0x18000d3bb  call    ??@1738a9bc70f2c7b97dec4e688edd6b3c@
0x18000d3c0  mov     dil, al
0x18000d3c3  cmp     byte ptr [rbx+8], 0
0x18000d3c7  lea     rdx, [rsp+28h+arg_8]
0x18000d3cc  mov     rax, [rbx]
0x18000d3cf  mov     byte ptr [rsp+28h+arg_8], 1
0x18000d3d4  mov     rcx, [rax]
0x18000d3d7  jnz     short loc_18000D3DE
0x18000d3d9  mov     byte ptr [rsp+28h+arg_8], 0
0x18000d3de  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000d3e3  mov     rbx, [rsp+28h+arg_0]
0x18000d3e8  mov     al, dil
0x18000d3eb  mov     rsi, [rsp+28h+arg_10]
0x18000d3f0  add     rsp, 20h
0x18000d3f4  pop     rdi
0x18000d3f5  retn
```
