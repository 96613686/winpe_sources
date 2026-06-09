# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &)

- ea: `0x18000ea04`
- end: `0x18000eb23`
- name: `??$marshal@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@1@@Z`
- size: `287`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e24c`

## callees

- `0x180002380`
- `0x18000b920`
- `0x18000c1b0`
- `0x18000f93c`
- `0x18000fa14`
- `0x180010aec`
- `0x180010b34`
- `0x18001e90c`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  _BYTE v7[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[16]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+54h] [rbp-ACh]
  int v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+60h] [rbp-A0h]
  _BYTE v14[24]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v15; // [rsp+80h] [rbp-80h]
  _QWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v17; // [rsp+A0h] [rbp-60h] BYREF
  int v18; // [rsp+A8h] [rbp-58h]
  int v19; // [rsp+ACh] [rbp-54h]
  char v20; // [rsp+B0h] [rbp-50h] BYREF
  char *v21; // [rsp+1B0h] [rbp+B0h]
  int v22; // [rsp+1B8h] [rbp+B8h]
  int v23; // [rsp+1BCh] [rbp+BCh]
  char v24; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v25; // [rsp+2C0h] [rbp+1C0h]

  v15 = a1;
  boost::shared_ptr<char const [0]>::shared_ptr<char const [0]>(v8, 0);
  v9 = v4;
  v10 = v4;
  v11 = 32;
  v12 = -1;
  v13 = v4;
  std::vector<bond::blob>::vector<bond::blob>(v14);
  v16[0] = v7;
  v16[1] = v5;
  v17 = v5 + 1;
  v18 = v5;
  v19 = v5 + 64;
  v21 = &v20;
  v22 = v5;
  v23 = v5 + 64;
  v25 = &v24;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(v7, "CB");
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(v16[0], &v17);
  bond::Serialize<bond::BuiltInProtocols,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>(
    a2,
    v16);
  wil::cloud_store::output_buffer_to_buffer(a1, v7);
  bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::~CompactBinaryWriter<bond::CompactBinaryCounter::type>(v16);
  bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v7);
  return a1;
}

```

## disassembly

```asm
0x18000ea04  mov     [rsp-8+arg_10], rbx
0x18000ea09  mov     [rsp-8+arg_18], rdi
0x18000ea0e  push    rbp
0x18000ea0f  lea     rbp, [rsp-1E0h]
0x18000ea17  sub     rsp, 2E0h
0x18000ea1e  mov     rax, cs:__security_cookie
0x18000ea25  xor     rax, rsp
0x18000ea28  mov     [rbp+1E0h+var_10], rax
0x18000ea2f  mov     rbx, rdx
0x18000ea32  mov     rdi, rcx
0x18000ea35  mov     [rbp+1E0h+var_260], rcx
0x18000ea39  xor     edx, edx
0x18000ea3b  lea     rcx, [rsp+2E0h+var_2A8]
0x18000ea40  call    ??0?$shared_ptr@$$BY0A@$$CBD@boost@@QEAA@XZ; boost::shared_ptr<char const [0]>::shared_ptr<char const [0]>(void)
0x18000ea45  mov     [rsp+2E0h+var_298], rdx
0x18000ea4a  mov     [rsp+2E0h+var_290], edx
0x18000ea4e  mov     [rsp+2E0h+var_28C], 20h ; ' '
0x18000ea56  mov     [rsp+2E0h+var_288], 0FFFFFFFFh
0x18000ea5e  mov     [rsp+2E0h+var_280], rdx
0x18000ea63  lea     rcx, [rsp+2E0h+var_278]
0x18000ea68  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18000ea6d  nop
0x18000ea6e  lea     rax, [rsp+2E0h+var_2B0]
0x18000ea73  mov     [rbp+1E0h+var_250], rax
0x18000ea77  mov     [rbp+1E0h+var_248], rdx
0x18000ea7b  lea     eax, [rdx+1]
0x18000ea7e  mov     [rbp+1E0h+var_240], ax
0x18000ea82  mov     [rbp+1E0h+var_238], edx
0x18000ea85  lea     ecx, [rdx+40h]
0x18000ea88  mov     [rbp+1E0h+var_234], ecx
0x18000ea8b  lea     rax, [rbp+1E0h+var_230]
0x18000ea8f  mov     [rbp+1E0h+var_130], rax
0x18000ea96  mov     [rbp+1E0h+var_128], edx
0x18000ea9c  mov     [rbp+1E0h+var_124], ecx
0x18000eaa2  lea     rax, [rbp+1E0h+var_120]
0x18000eaa9  mov     [rbp+1E0h+var_20], rax
0x18000eab0  lea     rdx, ?magic@?$CompactBinaryReader@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@2GB; "CB"
0x18000eab7  lea     rcx, [rsp+2E0h+var_2B0]
0x18000eabc  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18000eac1  lea     rdx, [rbp+1E0h+var_240]
0x18000eac5  mov     rcx, [rbp+1E0h+var_250]
0x18000eac9  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18000eace  lea     rdx, [rbp+1E0h+var_250]
0x18000ead2  mov     rcx, rbx
0x18000ead5  call    ??$Serialize@UBuiltInProtocols@bond@@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@2@@bond@@YAXAEBV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@AEAV?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@0@@Z; bond::Serialize<bond::BuiltInProtocols,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>(wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> const &,bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>> &)
0x18000eada  lea     rdx, [rsp+2E0h+var_2B0]
0x18000eadf  mov     rcx, rdi
0x18000eae2  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x18000eae7  nop
0x18000eae8  lea     rcx, [rbp+1E0h+var_250]
0x18000eaec  call    ??1?$CompactBinaryWriter@Utype@CompactBinaryCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::CompactBinaryCounter::type>::~CompactBinaryWriter<bond::CompactBinaryCounter::type>(void)
0x18000eaf1  nop
0x18000eaf2  lea     rcx, [rsp+2E0h+var_2B0]
0x18000eaf7  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x18000eafc  mov     rax, rdi
0x18000eaff  mov     rcx, [rbp+1E0h+var_10]
0x18000eb06  xor     rcx, rsp; StackCookie
0x18000eb09  call    __security_check_cookie
0x18000eb0e  lea     r11, [rsp+2E0h+var_s0]
0x18000eb16  mov     rbx, [r11+20h]
0x18000eb1a  mov     rdi, [r11+28h]
0x18000eb1e  mov     rsp, r11
0x18000eb21  pop     rbp
0x18000eb22  retn
```
