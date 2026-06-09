# bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &>>::Read<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>> const &)

- ea: `0x18000d3fc`
- end: `0x18000d4b0`
- name: `??$Read@USchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@V?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@@?$ParserInheritance@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$StaticParser@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@detail@bond@@IEAA_NAEBUSchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@AEBV?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@2@@Z`
- size: `180`
- prototype: `char __fastcall(_BYTE **, __int64, unsigned int ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c1e8`

## callees

- `0x18000c8bc`
- `0x18000d3fc`
- `0x18001c764`
- `0x1800202a0`
- `0x180024a10`

## pseudocode

```c
char __fastcall bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &>>::Read<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(
        _BYTE **a1,
        __int64 a2,
        unsigned int ***a3)
{
  unsigned int *v5; // rbx
  unsigned int *v6; // rdi
  char v7; // r11
  __int64 v8; // rdx
  unsigned int **v9; // rax
  unsigned int *v10; // rcx
  unsigned int v11; // edx

  if ( !*((_BYTE *)a3 + 8) )
  {
    v5 = **a3;
    v6 = (unsigned int *)(*a3 + 37);
    bond::detail::SimpleArray<unsigned int,64>::push(*a3 + 3, *v6);
    bond::detail::SimpleArray<unsigned int,64>::push(v6, *v5);
  }
  v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(
         a3,
         0,
         (__int64)Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_eyeControlEnabled_metadata,
         *a1);
  if ( !v7 )
  {
    v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(
           a3,
           1,
           (__int64)Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_showGazeCursor_metadata,
           *a1 + 1);
    if ( !v7 )
      v7 = ___f0dbd6d012917131eae5d8617fbaca11_(a1, v8, a3);
  }
  v9 = *a3;
  v10 = **a3;
  v11 = *v10;
  if ( *((_BYTE *)a3 + 8) )
  {
    *v10 = v11 + 1;
  }
  else
  {
    *v10 = v11 + 1;
    bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(v9, *v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000d3fc  push    rbx
0x18000d3fe  push    rsi
0x18000d3ff  push    rdi
0x18000d400  push    r14
0x18000d402  sub     rsp, 28h
0x18000d406  cmp     byte ptr [r8+8], 0
0x18000d40b  mov     rsi, r8
0x18000d40e  mov     r14, rcx
0x18000d411  jnz     short loc_18000D435
0x18000d413  mov     rcx, [r8]
0x18000d416  mov     rbx, [rcx]
0x18000d419  lea     rdi, [rcx+128h]
0x18000d420  mov     edx, [rdi]
0x18000d422  add     rcx, 18h
0x18000d426  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x18000d42b  mov     edx, [rbx]
0x18000d42d  mov     rcx, rdi
0x18000d430  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x18000d435  mov     r9, [r14]
0x18000d438  lea     r8, ?s_eyeControlEnabled_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_eyeControlEnabled_metadata
0x18000d43f  xor     edx, edx
0x18000d441  mov     rcx, rsi
0x18000d444  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000d449  mov     r11b, al
0x18000d44c  test    al, al
0x18000d44e  jnz     short loc_18000D47F
0x18000d450  mov     r9, [r14]
0x18000d453  lea     r8, ?s_showGazeCursor_metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::s_showGazeCursor_metadata
0x18000d45a  inc     r9
0x18000d45d  mov     edx, 1
0x18000d462  mov     rcx, rsi
0x18000d465  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000d46a  mov     r11b, al
0x18000d46d  test    al, al
0x18000d46f  jnz     short loc_18000D47F
0x18000d471  mov     r8, rsi
0x18000d474  mov     rcx, r14
0x18000d477  call    ??@f0dbd6d012917131eae5d8617fbaca11@
0x18000d47c  mov     r11b, al
0x18000d47f  cmp     byte ptr [rsi+8], 0
0x18000d483  mov     rax, [rsi]
0x18000d486  mov     rcx, [rax]
0x18000d489  mov     edx, [rcx]
0x18000d48b  jz      short loc_18000D494
0x18000d48d  lea     eax, [rdx+1]
0x18000d490  mov     [rcx], eax
0x18000d492  jmp     short loc_18000D4A3
0x18000d494  inc     edx
0x18000d496  mov     [rcx], edx
0x18000d498  mov     rcx, rax
0x18000d49b  mov     rdx, [rax]
0x18000d49e  call    ?LengthEnd@?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@IEAAXAEAVOutputCounter@2@@Z; bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(bond::OutputCounter &)
0x18000d4a3  mov     al, r11b
0x18000d4a6  add     rsp, 28h
0x18000d4aa  pop     r14
0x18000d4ac  pop     rdi
0x18000d4ad  pop     rsi
0x18000d4ae  pop     rbx
0x18000d4af  retn
```
