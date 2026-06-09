# bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings> const &)

- ea: `0x18000a018`
- end: `0x18000a0af`
- name: `??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64 **, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bedc`
- `0x180016104`

## callees

- `0x18000a018`
- `0x18000bedc`
- `0x18000c830`
- `0x180011bcc`
- `0x180011cac`

## pseudocode

```c
char __fastcall bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(
        __int64 **a1,
        __int64 a2)
{
  __int64 *v3; // rcx
  unsigned int **v5; // r8
  unsigned int *v7; // rdx
  __int64 v8; // rcx
  char v9; // di
  __int64 v10; // rcx
  bool v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = (unsigned int **)(v3 + 1);
  if ( *((_WORD *)v3 + 8) == 2 && !*v5 )
    return bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(a1);
  if ( !*((_BYTE *)a1 + 8) && *((_WORD *)v3 + 8) == 2 )
  {
    v7 = *v5;
    v8 = *v3;
    ++*v5;
    bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned int>(v8, *v7);
  }
  v9 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
         a1,
         0,
         Windows::Data::Input::Devices::MouseSyncedSettings::Schema::s_swapPrimaryButton_metadata,
         a2);
  v10 = **a1;
  v11 = *((_BYTE *)a1 + 8) != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v10, &v11);
  return v9;
}

```

## disassembly

```asm
0x18000a018  mov     [rsp+arg_8], rbx
0x18000a01d  push    rdi
0x18000a01e  sub     rsp, 20h
0x18000a022  mov     rbx, rcx
0x18000a025  mov     eax, 2
0x18000a02a  mov     rcx, [rcx]
0x18000a02d  mov     rdi, rdx
0x18000a030  lea     r8, [rcx+8]
0x18000a034  cmp     ax, [rcx+10h]
0x18000a038  jnz     short loc_18000A04A
0x18000a03a  cmp     qword ptr [r8], 0
0x18000a03e  jnz     short loc_18000A04A
0x18000a040  mov     rcx, rbx
0x18000a043  call    ??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings> const &)
0x18000a048  jmp     short loc_18000A0A4
0x18000a04a  cmp     byte ptr [rbx+8], 0
0x18000a04e  jnz     short loc_18000A06A
0x18000a050  cmp     ax, [rcx+10h]
0x18000a054  jnz     short loc_18000A06A
0x18000a056  mov     rdx, [r8]
0x18000a059  mov     rcx, [rcx]
0x18000a05c  lea     rax, [rdx+4]
0x18000a060  mov     [r8], rax
0x18000a063  mov     edx, [rdx]
0x18000a065  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000a06a  xor     edx, edx
0x18000a06c  lea     r8, ?s_swapPrimaryButton_metadata@Schema@MouseSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSyncedSettings::Schema::s_swapPrimaryButton_metadata
0x18000a073  mov     r9, rdi
0x18000a076  mov     rcx, rbx
0x18000a079  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000a07e  cmp     byte ptr [rbx+8], 0
0x18000a082  lea     rdx, [rsp+28h+arg_0]
0x18000a087  mov     dil, al
0x18000a08a  mov     [rsp+28h+arg_0], 1
0x18000a08f  mov     rax, [rbx]
0x18000a092  mov     rcx, [rax]
0x18000a095  jnz     short loc_18000A09C
0x18000a097  mov     [rsp+28h+arg_0], 0
0x18000a09c  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a0a1  mov     al, dil
0x18000a0a4  mov     rbx, [rsp+28h+arg_8]
0x18000a0a9  add     rsp, 20h
0x18000a0ad  pop     rdi
0x18000a0ae  retn
```
