# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme> const &)

- ea: `0x180011d9c`
- end: `0x180011e9a`
- name: `??$marshal@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@1@@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800116e4`

## callees

- `0x180003980`
- `0x18000f168`
- `0x18001259c`
- `0x180013260`
- `0x1800132dc`
- `0x180016454`
- `0x180017024`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(
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
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(
    &v5,
    a2);
  wil::cloud_store::output_buffer_to_buffer(a1, v7);
  bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>((__int64)v8);
  bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v7);
  return a1;
}

```

## disassembly

```asm
0x180011d9c  mov     [rsp-8+arg_10], rbx
0x180011da1  mov     [rsp-8+arg_18], rdi
0x180011da6  push    rbp
0x180011da7  lea     rbp, [rsp-1E0h]
0x180011daf  sub     rsp, 2E0h
0x180011db6  mov     rax, cs:__security_cookie
0x180011dbd  xor     rax, rsp
0x180011dc0  mov     [rbp+1E0h+var_10], rax
0x180011dc7  mov     rbx, rdx
0x180011dca  mov     rdi, rcx
0x180011dcd  mov     [rsp+2E0h+var_2B8], rcx
0x180011dd2  lea     rcx, [rsp+2E0h+var_2A0]
0x180011dd7  call    ??0?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@AEBV?$allocator@D@std@@@Z; bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(std::allocator<char> const &)
0x180011ddc  nop
0x180011ddd  lea     rax, [rsp+2E0h+var_2A0]
0x180011de2  mov     [rbp+1E0h+var_250], rax
0x180011de6  mov     [rbp+1E0h+var_248], 0
0x180011dee  mov     eax, 1
0x180011df3  mov     [rbp+1E0h+var_240], ax
0x180011df7  mov     [rbp+1E0h+var_238], 0
0x180011dfe  lea     ecx, [rax+3Fh]
0x180011e01  mov     [rbp+1E0h+var_234], ecx
0x180011e04  lea     rax, [rbp+1E0h+var_230]
0x180011e08  mov     [rbp+1E0h+var_130], rax
0x180011e0f  mov     [rbp+1E0h+var_128], 0
0x180011e19  mov     [rbp+1E0h+var_124], ecx
0x180011e1f  lea     rax, [rbp+1E0h+var_120]
0x180011e26  mov     [rbp+1E0h+var_20], rax
0x180011e2d  lea     rcx, [rbp+1E0h+var_250]
0x180011e31  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x180011e36  lea     rax, [rbp+1E0h+var_250]
0x180011e3a  mov     [rsp+2E0h+var_2B8], rax
0x180011e3f  mov     [rsp+2E0h+var_2B0], 0
0x180011e44  mov     rdx, rbx
0x180011e47  lea     rcx, [rsp+2E0h+var_2B8]
0x180011e4c  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UFocusSessionActiveTheme@Shell@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Shell::FocusSessionActiveTheme> const &)
0x180011e51  lea     rdx, [rsp+2E0h+var_2A0]
0x180011e56  mov     rcx, rdi
0x180011e59  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x180011e5e  nop
0x180011e5f  lea     rcx, [rbp+1E0h+var_250]
0x180011e63  call    ??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)
0x180011e68  nop
0x180011e69  lea     rcx, [rsp+2E0h+var_2A0]
0x180011e6e  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x180011e73  mov     rax, rdi
0x180011e76  mov     rcx, [rbp+1E0h+var_10]
0x180011e7d  xor     rcx, rsp; StackCookie
0x180011e80  call    __security_check_cookie
0x180011e85  lea     r11, [rsp+2E0h+var_s0]
0x180011e8d  mov     rbx, [r11+20h]
0x180011e91  mov     rdi, [r11+28h]
0x180011e95  mov     rsp, r11
0x180011e98  pop     rbp
0x180011e99  retn
```
