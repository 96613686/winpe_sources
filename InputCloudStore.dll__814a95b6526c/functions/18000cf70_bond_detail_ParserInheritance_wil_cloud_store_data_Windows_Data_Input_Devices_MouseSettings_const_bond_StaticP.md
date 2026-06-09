# bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &>>::Read<Windows::Data::Input::Devices::MouseSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(Windows::Data::Input::Devices::MouseSettings::Schema const &,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>> const &)

- ea: `0x18000cf70`
- end: `0x18000d0aa`
- name: `??$Read@USchema@MouseSettings@Devices@Input@Data@Windows@@V?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@@?$ParserInheritance@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$StaticParser@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@detail@bond@@IEAA_NAEBUSchema@MouseSettings@Devices@Input@Data@Windows@@AEBV?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@2@@Z`
- size: `314`
- prototype: `char __fastcall(_WORD **, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bdd8`

## callees

- `0x18000c64c`
- `0x18000c8bc`
- `0x18000cf70`
- `0x180024a10`

## pseudocode

```c
char __fastcall bond::detail::ParserInheritance<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &,bond::StaticParser<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &>>::Read<Windows::Data::Input::Devices::MouseSettings::Schema,bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>>(
        _WORD **a1,
        __int64 a2,
        _BYTE *a3)
{
  unsigned int *v5; // rbx
  unsigned int *v6; // rdi
  char v7; // r8
  unsigned int v8; // r11d
  __int64 v9; // r9
  bool v10; // zf
  int *v11; // r10
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int v14; // ecx
  int v15; // eax

  if ( !a3[8] )
  {
    v5 = **(unsigned int ***)a3;
    v6 = (unsigned int *)(*(_QWORD *)a3 + 296LL);
    bond::detail::SimpleArray<unsigned int,64>::push(*(_QWORD *)a3 + 24LL, *v6);
    bond::detail::SimpleArray<unsigned int,64>::push(v6, *v5);
  }
  v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<unsigned short>(
         a3,
         0,
         (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_mousePointerSpeed_metadata,
         *a1);
  v8 = 3;
  if ( !v7 )
  {
    v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(
           a3,
           1,
           (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollPage_metadata,
           (_BYTE *)*a1 + 2);
    if ( !v7 )
    {
      v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<unsigned short>(
             a3,
             v8 - 1,
             (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata,
             *a1 + 2);
      if ( !v7 )
        v7 = bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(
               a3,
               v8,
               (__int64)Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata,
               (_BYTE *)*a1 + 6);
    }
  }
  v9 = *(_QWORD *)a3;
  v10 = a3[8] == 0;
  ++***(_DWORD ***)a3;
  if ( v10 )
  {
    v11 = *(int **)v9;
    v12 = *(unsigned int *)(*(_QWORD *)(v9 + 288) + 4LL * (unsigned int)--*(_DWORD *)(v9 + 24));
    v13 = *(_QWORD *)(v9 + 560);
    v14 = *v11 - *(_DWORD *)(v13 + 4 * v12);
    *(_DWORD *)(v13 + 4 * v12) = v14;
    v15 = *v11;
    if ( v14 < 0x80 )
    {
      *v11 = v15 + 1;
    }
    else
    {
      if ( v14 < 0x4000 )
      {
        v8 = 2;
      }
      else if ( v14 >= 0x200000 )
      {
        v8 = 5 - (v14 < 0x10000000);
      }
      *v11 = v8 + v15;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000cf70  push    rbx
0x18000cf72  push    rsi
0x18000cf73  push    rdi
0x18000cf74  push    r14
0x18000cf76  sub     rsp, 28h
0x18000cf7a  cmp     byte ptr [r8+8], 0
0x18000cf7f  mov     rsi, r8
0x18000cf82  mov     r14, rcx
0x18000cf85  jnz     short loc_18000CFA9
0x18000cf87  mov     rcx, [r8]
0x18000cf8a  mov     rbx, [rcx]
0x18000cf8d  lea     rdi, [rcx+128h]
0x18000cf94  mov     edx, [rdi]
0x18000cf96  add     rcx, 18h
0x18000cf9a  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x18000cf9f  mov     edx, [rbx]
0x18000cfa1  mov     rcx, rdi
0x18000cfa4  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x18000cfa9  mov     r9, [r14]
0x18000cfac  lea     r8, ?s_mousePointerSpeed_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_mousePointerSpeed_metadata
0x18000cfb3  xor     edx, edx
0x18000cfb5  mov     rcx, rsi
0x18000cfb8  call    ??$Field@G@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)
0x18000cfbd  mov     r8b, al
0x18000cfc0  mov     r11d, 3
0x18000cfc6  test    al, al
0x18000cfc8  jnz     short loc_18000D028
0x18000cfca  mov     r9, [r14]
0x18000cfcd  lea     edx, [r11-2]
0x18000cfd1  add     r9, 2
0x18000cfd5  lea     r8, ?s_allowScrollPage_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollPage_metadata
0x18000cfdc  mov     rcx, rsi
0x18000cfdf  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000cfe4  mov     r8b, al
0x18000cfe7  test    al, al
0x18000cfe9  jnz     short loc_18000D028
0x18000cfeb  mov     r9, [r14]
0x18000cfee  lea     edx, [r11-1]
0x18000cff2  add     r9, 4
0x18000cff6  lea     r8, ?s_scrollLines_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_scrollLines_metadata
0x18000cffd  mov     rcx, rsi
0x18000d000  call    ??$Field@G@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)
0x18000d005  mov     r8b, al
0x18000d008  test    al, al
0x18000d00a  jnz     short loc_18000D028
0x18000d00c  mov     r9, [r14]
0x18000d00f  lea     r8, ?s_allowScrollInactiveWindows_metadata@Schema@MouseSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::MouseSettings::Schema::s_allowScrollInactiveWindows_metadata
0x18000d016  add     r9, 6
0x18000d01a  mov     edx, r11d
0x18000d01d  mov     rcx, rsi
0x18000d020  call    ??$Field@_N@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(ushort,bond::Metadata const &,bool const &)
0x18000d025  mov     r8b, al
0x18000d028  mov     r9, [rsi]
0x18000d02b  mov     rcx, [r9]
0x18000d02e  mov     eax, [rcx]
0x18000d030  inc     eax
0x18000d032  cmp     byte ptr [rsi+8], 0
0x18000d036  mov     [rcx], eax
0x18000d038  jnz     short loc_18000D09D
0x18000d03a  mov     r10, [r9]
0x18000d03d  dec     dword ptr [r9+18h]
0x18000d041  mov     ecx, [r9+18h]
0x18000d045  mov     rax, [r9+120h]
0x18000d04c  mov     edx, [rax+rcx*4]
0x18000d04f  mov     rax, [r9+230h]
0x18000d056  mov     ecx, [r10]
0x18000d059  sub     ecx, [rax+rdx*4]
0x18000d05c  mov     [rax+rdx*4], ecx
0x18000d05f  mov     eax, [r10]
0x18000d062  cmp     ecx, 80h
0x18000d068  jb      short loc_18000D097
0x18000d06a  cmp     ecx, 4000h
0x18000d070  jb      short loc_18000D089
0x18000d072  cmp     ecx, 200000h
0x18000d078  jb      short loc_18000D08F
0x18000d07a  cmp     ecx, 10000000h
0x18000d080  sbb     r11d, r11d
0x18000d083  add     r11d, 5
0x18000d087  jmp     short loc_18000D08F
0x18000d089  mov     r11d, 2
0x18000d08f  add     eax, r11d
0x18000d092  mov     [r10], eax
0x18000d095  jmp     short loc_18000D09D
0x18000d097  lea     ecx, [rax+1]
0x18000d09a  mov     [r10], ecx
0x18000d09d  mov     al, r8b
0x18000d0a0  add     rsp, 28h
0x18000d0a4  pop     r14
0x18000d0a6  pop     rdi
0x18000d0a7  pop     rsi
0x18000d0a8  pop     rbx
0x18000d0a9  retn
```
