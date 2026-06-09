# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &)

- ea: `0x180023680`
- end: `0x1800237db`
- name: `??$marshal@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bce8`

## callees

- `0x180006afc`
- `0x18001fa54`
- `0x180023814`
- `0x180023850`
- `0x18002395c`
- `0x1800239d8`
- `0x18002a030`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v5; // [rsp+28h] [rbp-D8h] BYREF
  char v6; // [rsp+30h] [rbp-D0h]
  _BYTE v7[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+48h] [rbp-B8h]
  __int64 v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+64h] [rbp-9Ch]
  int v13; // [rsp+68h] [rbp-98h]
  __int64 v14; // [rsp+70h] [rbp-90h]
  _BYTE v15[24]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v17; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v18[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v19; // [rsp+B0h] [rbp-50h] BYREF
  char *v20; // [rsp+1B0h] [rbp+B0h]
  _DWORD v21[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v22; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v23; // [rsp+2C0h] [rbp+1C0h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 32;
  v13 = -1;
  v14 = 0;
  std::vector<bond::blob>::vector<bond::blob>(v15);
  v16[0] = v7;
  v16[1] = 0;
  v17 = 1;
  v18[0] = 0;
  v18[1] = 64;
  v20 = &v19;
  v21[0] = 0;
  v21[1] = 64;
  v23 = &v22;
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(
    v7,
    &bond::CompactBinaryReader<bond::OutputMemoryStream<std::allocator<char>>>::magic);
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(v16[0], &v17);
  v5 = v16;
  v6 = 0;
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(
    (__int64)&v5,
    a2);
  wil::cloud_store::output_buffer_to_buffer(a1, v7);
  bond::detail::SimpleArray<unsigned int,64>::memfree(v21);
  bond::detail::SimpleArray<unsigned int,64>::memfree(v18);
  bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v7);
  return a1;
}

```

## disassembly

```asm
0x180023680  mov     [rsp-8+arg_10], rbx
0x180023685  mov     [rsp-8+arg_18], rdi
0x18002368a  push    rbp
0x18002368b  lea     rbp, [rsp-1E0h]
0x180023693  sub     rsp, 2E0h
0x18002369a  mov     rax, cs:__security_cookie
0x1800236a1  xor     rax, rsp
0x1800236a4  mov     [rbp+1E0h+var_10], rax
0x1800236ab  mov     rbx, rdx
0x1800236ae  mov     rdi, rcx
0x1800236b1  mov     [rsp+2E0h+var_2B8], rcx
0x1800236b6  mov     [rsp+2E0h+var_298], 0
0x1800236bf  mov     [rsp+2E0h+var_290], 0
0x1800236c8  mov     [rsp+2E0h+var_288], 0
0x1800236d1  mov     [rsp+2E0h+var_280], 0
0x1800236d9  mov     [rsp+2E0h+var_27C], 20h ; ' '
0x1800236e1  mov     [rsp+2E0h+var_278], 0FFFFFFFFh
0x1800236e9  mov     [rsp+2E0h+var_270], 0
0x1800236f2  lea     rcx, [rsp+2E0h+var_268]
0x1800236f7  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x1800236fc  nop
0x1800236fd  lea     rax, [rsp+2E0h+var_2A0]
0x180023702  mov     [rbp+1E0h+var_250], rax
0x180023706  mov     [rbp+1E0h+var_248], 0
0x18002370e  mov     eax, 1
0x180023713  mov     [rbp+1E0h+var_240], ax
0x180023717  mov     [rbp+1E0h+var_238], 0
0x18002371e  lea     ecx, [rax+3Fh]
0x180023721  mov     [rbp+1E0h+var_234], ecx
0x180023724  lea     rax, [rbp+1E0h+var_230]
0x180023728  mov     [rbp+1E0h+var_130], rax
0x18002372f  mov     [rbp+1E0h+var_128], 0
0x180023739  mov     [rbp+1E0h+var_124], ecx
0x18002373f  lea     rax, [rbp+1E0h+var_120]
0x180023746  mov     [rbp+1E0h+var_20], rax
0x18002374d  lea     rdx, ?magic@?$CompactBinaryReader@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@2GB; ushort const bond::CompactBinaryReader<bond::OutputMemoryStream<std::allocator<char>>>::magic
0x180023754  lea     rcx, [rsp+2E0h+var_2A0]
0x180023759  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18002375e  lea     rdx, [rbp+1E0h+var_240]
0x180023762  mov     rcx, [rbp+1E0h+var_250]
0x180023766  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18002376b  lea     rax, [rbp+1E0h+var_250]
0x18002376f  mov     [rsp+2E0h+var_2B8], rax
0x180023774  mov     [rsp+2E0h+var_2B0], 0
0x180023779  mov     rdx, rbx
0x18002377c  lea     rcx, [rsp+2E0h+var_2B8]
0x180023781  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &)
0x180023786  lea     rdx, [rsp+2E0h+var_2A0]
0x18002378b  mov     rcx, rdi
0x18002378e  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x180023793  nop
0x180023794  lea     rcx, [rbp+1E0h+var_128]
0x18002379b  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x1800237a0  lea     rcx, [rbp+1E0h+var_238]
0x1800237a4  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x1800237a9  nop
0x1800237aa  lea     rcx, [rsp+2E0h+var_2A0]
0x1800237af  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x1800237b4  mov     rax, rdi
0x1800237b7  mov     rcx, [rbp+1E0h+var_10]
0x1800237be  xor     rcx, rsp; StackCookie
0x1800237c1  call    __security_check_cookie
0x1800237c6  lea     r11, [rsp+2E0h+var_s0]
0x1800237ce  mov     rbx, [r11+20h]
0x1800237d2  mov     rdi, [r11+28h]
0x1800237d6  mov     rsp, r11
0x1800237d9  pop     rbp
0x1800237da  retn
```
