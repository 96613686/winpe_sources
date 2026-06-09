# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>(wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &)

- ea: `0x180016000`
- end: `0x1800160fe`
- name: `??$marshal@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@1@@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013824`

## callees

- `0x180003560`
- `0x180009fd0`
- `0x180019b0c`
- `0x18001af44`
- `0x18001af8c`
- `0x180022904`
- `0x1800248ec`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>(
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
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>(
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
0x180016000  mov     [rsp-8+arg_10], rbx
0x180016005  mov     [rsp-8+arg_18], rdi
0x18001600a  push    rbp
0x18001600b  lea     rbp, [rsp-1E0h]
0x180016013  sub     rsp, 2E0h
0x18001601a  mov     rax, cs:__security_cookie
0x180016021  xor     rax, rsp
0x180016024  mov     [rbp+1E0h+var_10], rax
0x18001602b  mov     rbx, rdx
0x18001602e  mov     rdi, rcx
0x180016031  mov     [rsp+2E0h+var_2B8], rcx
0x180016036  lea     rcx, [rsp+2E0h+var_2A0]
0x18001603b  call    ??0?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@AEBV?$allocator@D@std@@@Z; bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(std::allocator<char> const &)
0x180016040  nop
0x180016041  lea     rax, [rsp+2E0h+var_2A0]
0x180016046  mov     [rbp+1E0h+var_250], rax
0x18001604a  mov     [rbp+1E0h+var_248], 0
0x180016052  mov     eax, 1
0x180016057  mov     [rbp+1E0h+var_240], ax
0x18001605b  mov     [rbp+1E0h+var_238], 0
0x180016062  lea     ecx, [rax+3Fh]
0x180016065  mov     [rbp+1E0h+var_234], ecx
0x180016068  lea     rax, [rbp+1E0h+var_230]
0x18001606c  mov     [rbp+1E0h+var_130], rax
0x180016073  mov     [rbp+1E0h+var_128], 0
0x18001607d  mov     [rbp+1E0h+var_124], ecx
0x180016083  lea     rax, [rbp+1E0h+var_120]
0x18001608a  mov     [rbp+1E0h+var_20], rax
0x180016091  lea     rcx, [rbp+1E0h+var_250]
0x180016095  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x18001609a  lea     rax, [rbp+1E0h+var_250]
0x18001609e  mov     [rsp+2E0h+var_2B8], rax
0x1800160a3  mov     [rsp+2E0h+var_2B0], 0
0x1800160a8  mov     rdx, rbx
0x1800160ab  lea     rcx, [rsp+2E0h+var_2B8]
0x1800160b0  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings> const &)
0x1800160b5  lea     rdx, [rsp+2E0h+var_2A0]
0x1800160ba  mov     rcx, rdi
0x1800160bd  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x1800160c2  nop
0x1800160c3  lea     rcx, [rbp+1E0h+var_250]
0x1800160c7  call    ??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)
0x1800160cc  nop
0x1800160cd  lea     rcx, [rsp+2E0h+var_2A0]
0x1800160d2  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x1800160d7  mov     rax, rdi
0x1800160da  mov     rcx, [rbp+1E0h+var_10]
0x1800160e1  xor     rcx, rsp; StackCookie
0x1800160e4  call    __security_check_cookie
0x1800160e9  lea     r11, [rsp+2E0h+var_s0]
0x1800160f1  mov     rbx, [r11+20h]
0x1800160f5  mov     rdi, [r11+28h]
0x1800160f9  mov     rsp, r11
0x1800160fc  pop     rbp
0x1800160fd  retn
```
