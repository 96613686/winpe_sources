# bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type const &,bond::value<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &)

- ea: `0x18000a140`
- end: `0x18000a1e5`
- name: `??$Field@Ulocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@V?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@QEBA_NAEBUlocale_type@var@Schema@CultureSettings@Culture@Globalization@Data@Windows@@AEBV?$value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z`
- size: `165`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009b08`
- `0x18000a7a4`

## callees

- `0x18000a140`
- `0x18000a420`
- `0x18000ab04`
- `0x18000e560`
- `0x180016d40`
- `0x180017210`

## pseudocode

```c
char __fastcall bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>::Field<Windows::Data::Globalization::Culture::CultureSettings::Schema::var::locale_type,bond::value<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
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
0x18000a140  mov     r11, rsp
0x18000a143  mov     [r11+18h], rbx
0x18000a147  mov     [r11+20h], rsi
0x18000a14b  mov     [r11+10h], rdx
0x18000a14f  push    rdi
0x18000a150  sub     rsp, 20h
0x18000a154  mov     rdi, [r8]
0x18000a157  mov     rsi, [rcx+8]
0x18000a15b  mov     byte ptr [r8+8], 0
0x18000a160  mov     dword ptr [rsp+28h+arg_8], 0
0x18000a168  mov     edx, [rdi+18h]
0x18000a16b  mov     eax, [rdi+10h]
0x18000a16e  lea     rcx, [rdx+4]
0x18000a172  cmp     rax, rcx
0x18000a175  jbe     short loc_18000A19A
0x18000a177  mov     rbx, [rdi]
0x18000a17a  lea     rcx, [r11+8]
0x18000a17e  lea     rax, [rbx+rdx]
0x18000a182  lea     rdx, [r11+10h]
0x18000a186  mov     [r11+8], rax
0x18000a18a  call    ?Read@?$VariableUnsignedUnchecked@I$0A@@input_buffer@bond@@SAXAEAPEBDAEAI@Z; bond::input_buffer::VariableUnsignedUnchecked<uint,0>::Read(char const * &,uint &)
0x18000a18f  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000a193  sub     eax, ebx
0x18000a195  mov     [rdi+18h], eax
0x18000a198  jmp     short loc_18000A1A7
0x18000a19a  lea     rdx, [rsp+28h+arg_8]
0x18000a19f  mov     rcx, rdi; this
0x18000a1a2  call    ??$GenericReadVariableUnsigned@VInputBuffer@bond@@I@bond@@YAXAEAVInputBuffer@0@AEAI@Z; bond::GenericReadVariableUnsigned<bond::InputBuffer,uint>(bond::InputBuffer &,uint &)
0x18000a1a7  mov     ecx, dword ptr [rsp+28h+arg_8]
0x18000a1ab  mov     dl, 2
0x18000a1ad  call    ??$checked_multiply@I@detail@bond@@YAIIE@Z; bond::detail::checked_multiply<uint>(uint,uchar)
0x18000a1b2  mov     ecx, [rdi+10h]
0x18000a1b5  sub     ecx, [rdi+18h]; this
0x18000a1b8  cmp     eax, ecx
0x18000a1ba  ja      short loc_18000A1DF
0x18000a1bc  mov     r8d, dword ptr [rsp+28h+arg_8]
0x18000a1c1  lea     rdx, [rsi+40h]
0x18000a1c5  mov     rcx, rdi; this
0x18000a1c8  call    ??$ReadStringData@VInputBuffer@bond@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@detail@bond@@YAXAEAVInputBuffer@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; bond::detail::ReadStringData<bond::InputBuffer,std::wstring>(bond::InputBuffer &,std::wstring &,uint)
0x18000a1cd  mov     rbx, [rsp+28h+arg_10]
0x18000a1d2  xor     al, al
0x18000a1d4  mov     rsi, [rsp+28h+arg_18]
0x18000a1d9  add     rsp, 20h
0x18000a1dd  pop     rdi
0x18000a1de  retn
0x18000a1df  call    ?OutOfBoundStringSizeException@bond@@YAXXZ; bond::OutOfBoundStringSizeException(void)
```
