# bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings> const &)

- ea: `0x18000a2d0`
- end: `0x18000a367`
- name: `??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64 **, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c4f4`
- `0x18001671c`

## callees

- `0x18000a2d0`
- `0x18000c4f4`
- `0x18000c830`
- `0x180011bcc`
- `0x180011cac`

## pseudocode

```c
char __fastcall bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>(
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
    return bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>(a1);
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
         Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata,
         a2);
  v10 = **a1;
  v11 = *((_BYTE *)a1 + 8) != 0;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned char>(v10, &v11);
  return v9;
}

```

## disassembly

```asm
0x18000a2d0  mov     [rsp+arg_8], rbx
0x18000a2d5  push    rdi
0x18000a2d6  sub     rsp, 20h
0x18000a2da  mov     rbx, rcx
0x18000a2dd  mov     eax, 2
0x18000a2e2  mov     rcx, [rcx]
0x18000a2e5  mov     rdi, rdx
0x18000a2e8  lea     r8, [rcx+8]
0x18000a2ec  cmp     ax, [rcx+10h]
0x18000a2f0  jnz     short loc_18000A302
0x18000a2f2  cmp     qword ptr [r8], 0
0x18000a2f6  jnz     short loc_18000A302
0x18000a2f8  mov     rcx, rbx
0x18000a2fb  call    ??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UTouchpadSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSyncedSettings> const &)
0x18000a300  jmp     short loc_18000A35C
0x18000a302  cmp     byte ptr [rbx+8], 0
0x18000a306  jnz     short loc_18000A322
0x18000a308  cmp     ax, [rcx+10h]
0x18000a30c  jnz     short loc_18000A322
0x18000a30e  mov     rdx, [r8]
0x18000a311  mov     rcx, [rcx]
0x18000a314  lea     rax, [rdx+4]
0x18000a318  mov     [r8], rax
0x18000a31b  mov     edx, [rdx]
0x18000a31d  call    ??$WriteVariableUnsigned@I@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXI@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<uint>(uint)
0x18000a322  xor     edx, edx
0x18000a324  lea     r8, ?s_scrollInverted_metadata@Schema@TouchpadSyncedSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::TouchpadSyncedSettings::Schema::s_scrollInverted_metadata
0x18000a32b  mov     r9, rdi
0x18000a32e  mov     rcx, rbx
0x18000a331  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000a336  cmp     byte ptr [rbx+8], 0
0x18000a33a  lea     rdx, [rsp+28h+arg_0]
0x18000a33f  mov     dil, al
0x18000a342  mov     [rsp+28h+arg_0], 1
0x18000a347  mov     rax, [rbx]
0x18000a34a  mov     rcx, [rax]
0x18000a34d  jnz     short loc_18000A354
0x18000a34f  mov     [rsp+28h+arg_0], 0
0x18000a354  call    ??$Write@E@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBE@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<uchar>(uchar const &)
0x18000a359  mov     al, dil
0x18000a35c  mov     rbx, [rsp+28h+arg_8]
0x18000a361  add     rsp, 20h
0x18000a365  pop     rdi
0x18000a366  retn
```
