# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>(wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &)

- ea: `0x180016618`
- end: `0x180016716`
- name: `??$marshal@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@1@@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014738`

## callees

- `0x180003560`
- `0x18000a288`
- `0x180019b0c`
- `0x18001af44`
- `0x18001af8c`
- `0x180022904`
- `0x1800248ec`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v5; // [rsp+28h] [rbp-D8h] BYREF
  char v6; // [rsp+30h] [rbp-D0h]
  _BYTE v7[80]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v8[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v9; // [rsp+A0h] [rbp-60h]
  int v10; // [rsp+A8h] [rbp-58h]
  int v11; // [rsp+ACh] [rbp-54h]
  char v12; // [rsp+B0h] [rbp-50h] BYREF
  char *v13; // [rsp+1B0h] [rbp+B0h]
  int v14; // [rsp+1B8h] [rbp+B8h]
  int v15; // [rsp+1BCh] [rbp+BCh]
  char v16; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v17; // [rsp+2C0h] [rbp+1C0h]

  bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(v7);
  v8[0] = v7;
  v8[1] = 0;
  v9 = 1;
  v10 = 0;
  v11 = 64;
  v13 = &v12;
  v14 = 0;
  v15 = 64;
  v17 = &v16;
  bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(v8);
  v5 = v8;
  v6 = 0;
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>(
    (__int64)&v5,
    a2);
  wil::cloud_store::output_buffer_to_buffer(a1, v7);
  bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(v8);
  bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v7);
  return a1;
}

```

## disassembly

```asm
0x180016618  mov     [rsp-8+arg_10], rbx
0x18001661d  mov     [rsp-8+arg_18], rdi
0x180016622  push    rbp
0x180016623  lea     rbp, [rsp-1E0h]
0x18001662b  sub     rsp, 2E0h
0x180016632  mov     rax, cs:__security_cookie
0x180016639  xor     rax, rsp
0x18001663c  mov     [rbp+1E0h+var_10], rax
0x180016643  mov     rbx, rdx
0x180016646  mov     rdi, rcx
0x180016649  mov     [rsp+2E0h+var_2B8], rcx
0x18001664e  lea     rcx, [rsp+2E0h+var_2A0]
0x180016653  call    ??0?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@AEBV?$allocator@D@std@@@Z; bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(std::allocator<char> const &)
0x180016658  nop
0x180016659  lea     rax, [rsp+2E0h+var_2A0]
0x18001665e  mov     [rbp+1E0h+var_250], rax
0x180016662  mov     [rbp+1E0h+var_248], 0
0x18001666a  mov     eax, 1
0x18001666f  mov     [rbp+1E0h+var_240], ax
0x180016673  mov     [rbp+1E0h+var_238], 0
0x18001667a  lea     ecx, [rax+3Fh]
0x18001667d  mov     [rbp+1E0h+var_234], ecx
0x180016680  lea     rax, [rbp+1E0h+var_230]
0x180016684  mov     [rbp+1E0h+var_130], rax
0x18001668b  mov     [rbp+1E0h+var_128], 0
0x180016695  mov     [rbp+1E0h+var_124], ecx
0x18001669b  lea     rax, [rbp+1E0h+var_120]
0x1800166a2  mov     [rbp+1E0h+var_20], rax
0x1800166a9  lea     rcx, [rbp+1E0h+var_250]
0x1800166ad  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x1800166b2  lea     rax, [rbp+1E0h+var_250]
0x1800166b6  mov     [rsp+2E0h+var_2B8], rax
0x1800166bb  mov     [rsp+2E0h+var_2B0], 0
0x1800166c0  mov     rdx, rbx
0x1800166c3  lea     rcx, [rsp+2E0h+var_2B8]
0x1800166c8  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings> const &)
0x1800166cd  lea     rdx, [rsp+2E0h+var_2A0]
0x1800166d2  mov     rcx, rdi
0x1800166d5  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x1800166da  nop
0x1800166db  lea     rcx, [rbp+1E0h+var_250]
0x1800166df  call    ??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)
0x1800166e4  nop
0x1800166e5  lea     rcx, [rsp+2E0h+var_2A0]
0x1800166ea  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x1800166ef  mov     rax, rdi
0x1800166f2  mov     rcx, [rbp+1E0h+var_10]
0x1800166f9  xor     rcx, rsp; StackCookie
0x1800166fc  call    __security_check_cookie
0x180016701  lea     r11, [rsp+2E0h+var_s0]
0x180016709  mov     rbx, [r11+20h]
0x18001670d  mov     rdi, [r11+28h]
0x180016711  mov     rsp, r11
0x180016714  pop     rbp
0x180016715  retn
```
