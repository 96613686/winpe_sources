# bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type const &,bond::value<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)

- ea: `0x18000a094`
- end: `0x18000a138`
- name: `??$Field@UlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlanguageProfile_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z`
- size: `164`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b08`
- `0x18000aa0c`

## callees

- `0x18000a094`
- `0x18000a420`
- `0x18000ab04`
- `0x18000e560`
- `0x180016d40`
- `0x180017210`

## pseudocode

```c
char __fastcall bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::languageProfile_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // eax
  bond *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v11 = a2;
  v3 = *(unsigned int **)a3;
  *(_BYTE *)(a3 + 8) = 0;
  LODWORD(v11) = 0;
  v4 = v3[6];
  if ( v3[4] <= (unsigned __int64)(v4 + 4) )
  {
    bond::GenericReadVariableUnsigned<bond::InputBuffer,unsigned int>((bond::InputBuffer *)v3);
  }
  else
  {
    v5 = *(_QWORD *)v3;
    v10 = *(_QWORD *)v3 + v4;
    bond::input_buffer::VariableUnsignedUnchecked<unsigned int,0>::Read(&v10, &v11);
    v3[6] = v10 - v5;
  }
  LOBYTE(v6) = 2;
  v7 = bond::detail::checked_multiply<unsigned int>((unsigned int)v11, v6);
  v8 = (bond *)(v3[4] - v3[6]);
  if ( v7 > (unsigned int)v8 )
    bond::OutOfBoundStringSizeException(v8);
  bond::detail::ReadStringData<bond::InputBuffer,std::wstring>((bond::InputBuffer *)v3);
  return 0;
}

```

## disassembly

```asm
0x18000a094  mov     r11, rsp
0x18000a097  mov     [r11+18h], rbx
0x18000a09b  mov     [r11+20h], rsi
0x18000a09f  mov     [r11+10h], rdx
0x18000a0a3  push    rdi
0x18000a0a4  sub     rsp, 20h
0x18000a0a8  mov     rdi, [r8]
0x18000a0ab  mov     rsi, [rcx+8]
0x18000a0af  mov     byte ptr [r8+8], 0
0x18000a0b4  mov     dword ptr [rsp+28h+arg_8], 0
0x18000a0bc  mov     edx, [rdi+18h]
0x18000a0bf  mov     eax, [rdi+10h]
0x18000a0c2  lea     rcx, [rdx+4]
0x18000a0c6  cmp     rax, rcx
0x18000a0c9  jbe     short loc_18000A0EE
0x18000a0cb  mov     rbx, [rdi]
0x18000a0ce  lea     rcx, [r11+8]
0x18000a0d2  lea     rax, [rbx+rdx]
0x18000a0d6  lea     rdx, [r11+10h]
0x18000a0da  mov     [r11+8], rax
0x18000a0de  call    ?Read@?$VariableUnsignedUnchecked@I$0A@@input_buffer@bond@@SAXAEAPEBDAEAI@Z; bond::input_buffer::VariableUnsignedUnchecked<uint,0>::Read(char const * &,uint &)
0x18000a0e3  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000a0e7  sub     eax, ebx
0x18000a0e9  mov     [rdi+18h], eax
0x18000a0ec  jmp     short loc_18000A0FB
0x18000a0ee  lea     rdx, [rsp+28h+arg_8]
0x18000a0f3  mov     rcx, rdi; this
0x18000a0f6  call    ??$GenericReadVariableUnsigned@VInputBuffer@bond@@I@bond@@YAXAEAVInputBuffer@0@AEAI@Z; bond::GenericReadVariableUnsigned<bond::InputBuffer,uint>(bond::InputBuffer &,uint &)
0x18000a0fb  mov     ecx, dword ptr [rsp+28h+arg_8]
0x18000a0ff  mov     dl, 2
0x18000a101  call    ??$checked_multiply@I@detail@bond@@YAIIE@Z; bond::detail::checked_multiply<uint>(uint,uchar)
0x18000a106  mov     ecx, [rdi+10h]
0x18000a109  sub     ecx, [rdi+18h]; this
0x18000a10c  cmp     eax, ecx
0x18000a10e  ja      short loc_18000A132
0x18000a110  mov     r8d, dword ptr [rsp+28h+arg_8]
0x18000a115  mov     rdx, rsi
0x18000a118  mov     rcx, rdi; this
0x18000a11b  call    ??$ReadStringData@VInputBuffer@bond@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@detail@bond@@YAXAEAVInputBuffer@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; bond::detail::ReadStringData<bond::InputBuffer,std::wstring>(bond::InputBuffer &,std::wstring &,uint)
0x18000a120  mov     rbx, [rsp+28h+arg_10]
0x18000a125  xor     al, al
0x18000a127  mov     rsi, [rsp+28h+arg_18]
0x18000a12c  add     rsp, 20h
0x18000a130  pop     rdi
0x18000a131  retn
0x18000a132  call    ?OutOfBoundStringSizeException@bond@@YAXXZ; bond::OutOfBoundStringSizeException(void)
```
