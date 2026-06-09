# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>(wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme> const &)

- ea: `0x180018f04`
- end: `0x180019002`
- name: `??$marshal@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@1@@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x180003980`
- `0x18001259c`
- `0x180013260`
- `0x1800132dc`
- `0x180016454`
- `0x180017024`
- `0x180017824`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>(
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
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>(
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
0x180018f04  mov     [rsp-8+arg_10], rbx
0x180018f09  mov     [rsp-8+arg_18], rdi
0x180018f0e  push    rbp
0x180018f0f  lea     rbp, [rsp-1E0h]
0x180018f17  sub     rsp, 2E0h
0x180018f1e  mov     rax, cs:__security_cookie
0x180018f25  xor     rax, rsp
0x180018f28  mov     [rbp+1E0h+var_10], rax
0x180018f2f  mov     rbx, rdx
0x180018f32  mov     rdi, rcx
0x180018f35  mov     [rsp+2E0h+var_2B8], rcx
0x180018f3a  lea     rcx, [rsp+2E0h+var_2A0]
0x180018f3f  call    ??0?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@AEBV?$allocator@D@std@@@Z; bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(std::allocator<char> const &)
0x180018f44  nop
0x180018f45  lea     rax, [rsp+2E0h+var_2A0]
0x180018f4a  mov     [rbp+1E0h+var_250], rax
0x180018f4e  mov     [rbp+1E0h+var_248], 0
0x180018f56  mov     eax, 1
0x180018f5b  mov     [rbp+1E0h+var_240], ax
0x180018f5f  mov     [rbp+1E0h+var_238], 0
0x180018f66  lea     ecx, [rax+3Fh]
0x180018f69  mov     [rbp+1E0h+var_234], ecx
0x180018f6c  lea     rax, [rbp+1E0h+var_230]
0x180018f70  mov     [rbp+1E0h+var_130], rax
0x180018f77  mov     [rbp+1E0h+var_128], 0
0x180018f81  mov     [rbp+1E0h+var_124], ecx
0x180018f87  lea     rax, [rbp+1E0h+var_120]
0x180018f8e  mov     [rbp+1E0h+var_20], rax
0x180018f95  lea     rcx, [rbp+1E0h+var_250]
0x180018f99  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x180018f9e  lea     rax, [rbp+1E0h+var_250]
0x180018fa2  mov     [rsp+2E0h+var_2B8], rax
0x180018fa7  mov     [rsp+2E0h+var_2B0], 0
0x180018fac  mov     rdx, rbx
0x180018faf  lea     rcx, [rsp+2E0h+var_2B8]
0x180018fb4  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme> const &)
0x180018fb9  lea     rdx, [rsp+2E0h+var_2A0]
0x180018fbe  mov     rcx, rdi
0x180018fc1  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x180018fc6  nop
0x180018fc7  lea     rcx, [rbp+1E0h+var_250]
0x180018fcb  call    ??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)
0x180018fd0  nop
0x180018fd1  lea     rcx, [rsp+2E0h+var_2A0]
0x180018fd6  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x180018fdb  mov     rax, rdi
0x180018fde  mov     rcx, [rbp+1E0h+var_10]
0x180018fe5  xor     rcx, rsp; StackCookie
0x180018fe8  call    __security_check_cookie
0x180018fed  lea     r11, [rsp+2E0h+var_s0]
0x180018ff5  mov     rbx, [r11+20h]
0x180018ff9  mov     rdi, [r11+28h]
0x180018ffd  mov     rsp, r11
0x180019000  pop     rbp
0x180019001  retn
```
