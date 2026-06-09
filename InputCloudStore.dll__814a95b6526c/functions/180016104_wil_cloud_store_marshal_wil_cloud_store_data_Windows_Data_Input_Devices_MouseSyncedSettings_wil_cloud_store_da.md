# wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings> const &)

- ea: `0x180016104`
- end: `0x180016202`
- name: `??$marshal@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@1@@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013aa4`

## callees

- `0x180003560`
- `0x18000a018`
- `0x180019b0c`
- `0x18001af44`
- `0x18001af8c`
- `0x180022904`
- `0x1800248ec`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v5; // [rsp+28h] [rbp-D8h] BYREF
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
  bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(
    &v5,
    a2);
  wil::cloud_store::output_buffer_to_buffer(a1, v7);
  bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(v8);
  bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(v7);
  return a1;
}

```

## disassembly

```asm
0x180016104  mov     [rsp-8+arg_10], rbx
0x180016109  mov     [rsp-8+arg_18], rdi
0x18001610e  push    rbp
0x18001610f  lea     rbp, [rsp-1E0h]
0x180016117  sub     rsp, 2E0h
0x18001611e  mov     rax, cs:__security_cookie
0x180016125  xor     rax, rsp
0x180016128  mov     [rbp+1E0h+var_10], rax
0x18001612f  mov     rbx, rdx
0x180016132  mov     rdi, rcx
0x180016135  mov     [rsp+2E0h+var_2B8], rcx
0x18001613a  lea     rcx, [rsp+2E0h+var_2A0]
0x18001613f  call    ??0?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@AEBV?$allocator@D@std@@@Z; bond::OutputMemoryStream<std::allocator<char>>::OutputMemoryStream<std::allocator<char>>(std::allocator<char> const &)
0x180016144  nop
0x180016145  lea     rax, [rsp+2E0h+var_2A0]
0x18001614a  mov     [rbp+1E0h+var_250], rax
0x18001614e  mov     [rbp+1E0h+var_248], 0
0x180016156  mov     eax, 1
0x18001615b  mov     [rbp+1E0h+var_240], ax
0x18001615f  mov     [rbp+1E0h+var_238], 0
0x180016166  lea     ecx, [rax+3Fh]
0x180016169  mov     [rbp+1E0h+var_234], ecx
0x18001616c  lea     rax, [rbp+1E0h+var_230]
0x180016170  mov     [rbp+1E0h+var_130], rax
0x180016177  mov     [rbp+1E0h+var_128], 0
0x180016181  mov     [rbp+1E0h+var_124], ecx
0x180016187  lea     rax, [rbp+1E0h+var_120]
0x18001618e  mov     [rbp+1E0h+var_20], rax
0x180016195  lea     rcx, [rbp+1E0h+var_250]
0x180016199  call    ?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)
0x18001619e  lea     rax, [rbp+1E0h+var_250]
0x1800161a2  mov     [rsp+2E0h+var_2B8], rax
0x1800161a7  mov     [rsp+2E0h+var_2B0], 0
0x1800161ac  mov     rdx, rbx
0x1800161af  lea     rcx, [rsp+2E0h+var_2B8]
0x1800161b4  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings> const &)
0x1800161b9  lea     rdx, [rsp+2E0h+var_2A0]
0x1800161be  mov     rcx, rdi
0x1800161c1  call    ?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z; wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)
0x1800161c6  nop
0x1800161c7  lea     rcx, [rbp+1E0h+var_250]
0x1800161cb  call    ??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ; bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)
0x1800161d0  nop
0x1800161d1  lea     rcx, [rsp+2E0h+var_2A0]
0x1800161d6  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x1800161db  mov     rax, rdi
0x1800161de  mov     rcx, [rbp+1E0h+var_10]
0x1800161e5  xor     rcx, rsp; StackCookie
0x1800161e8  call    __security_check_cookie
0x1800161ed  lea     r11, [rsp+2E0h+var_s0]
0x1800161f5  mov     rbx, [r11+20h]
0x1800161f9  mov     rdi, [r11+28h]
0x1800161fd  mov     rsp, r11
0x180016200  pop     rbp
0x180016201  retn
```
