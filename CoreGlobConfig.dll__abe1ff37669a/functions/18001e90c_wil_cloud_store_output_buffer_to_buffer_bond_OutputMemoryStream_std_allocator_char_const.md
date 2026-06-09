# wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)

- ea: `0x18001e90c`
- end: `0x18001e9d1`
- name: `?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ea04`

## callees

- `0x18000a6bc`
- `0x18000eb2c`
- `0x18000ebf8`
- `0x18001052c`
- `0x180011228`
- `0x18001b4e4`
- `0x18001e90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall wil::cloud_store::output_buffer_to_buffer(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  _BYTE v9[24]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v10[24]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v11[32]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  bond::blob::blob(v9, a2 + 8, *(unsigned int *)(a2 + 32));
  v5 = bond::merge<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<bond::blob>>>,std::allocator<char>>(
         v11,
         v4,
         *(_QWORD *)(a2 + 56),
         *(_QWORD *)(a2 + 64),
         0);
  bond::merge<std::allocator<char>>(v10, v6, v5, v9);
  boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(v11);
  boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(v9);
  *a1 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<wil::details::BufferOverBlob,Windows::Storage::Streams::IBuffer,bond::blob &>(
         a1,
         v10);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6DB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v7,
      3);
  boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(v10);
  return a1;
}

```

## disassembly

```asm
0x18001e90c  mov     rax, rsp
0x18001e90f  mov     [rax+10h], rbx
0x18001e913  mov     [rax+8], rcx
0x18001e917  push    rdi
0x18001e918  sub     rsp, 70h
0x18001e91c  mov     rbx, rdx
0x18001e91f  mov     rdi, rcx
0x18001e922  mov     dword ptr [rax-58h], 0
0x18001e929  add     rdx, 8
0x18001e92d  mov     r9d, [rbx+1Ch]
0x18001e931  mov     r8d, [rbx+20h]
0x18001e935  lea     rcx, [rax-50h]
0x18001e939  call    ??0blob@bond@@QEAA@AEBV?$shared_ptr@$$BY0A@D@boost@@II@Z; bond::blob::blob(boost::shared_ptr<char [0]> const &,uint,uint)
0x18001e93e  nop
0x18001e93f  mov     r9, [rbx+40h]
0x18001e943  mov     r8, [rbx+38h]
0x18001e947  lea     rcx, [rsp+78h+var_20]
0x18001e94c  call    ??$merge@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@Vblob@bond@@@std@@@std@@@std@@V?$allocator@D@2@@bond@@YA?AVblob@0@AEBV?$allocator@D@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@Vblob@bond@@@std@@@std@@@3@1@Z; bond::merge<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<bond::blob>>>,std::allocator<char>>(std::allocator<char> const &,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<bond::blob>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<bond::blob>>>)
0x18001e951  nop
0x18001e952  lea     r9, [rsp+78h+var_50]
0x18001e957  mov     r8, rax
0x18001e95a  lea     rcx, [rsp+78h+var_38]
0x18001e95f  call    ??$merge@V?$allocator@D@std@@@bond@@YA?AVblob@0@AEBV?$allocator@D@std@@AEBV10@1@Z; bond::merge<std::allocator<char>>(std::allocator<char> const &,bond::blob const &,bond::blob const &)
0x18001e964  nop
0x18001e965  lea     rcx, [rsp+78h+var_20]
0x18001e96a  call    ??1?$shared_ptr@$$BY0A@$$CBD@boost@@QEAA@XZ; boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(void)
0x18001e96f  nop
0x18001e970  lea     rcx, [rsp+78h+var_50]
0x18001e975  call    ??1?$shared_ptr@$$BY0A@$$CBD@boost@@QEAA@XZ; boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(void)
0x18001e97a  nop
0x18001e97b  mov     [rsp+78h+var_58], 3; int
0x18001e983  mov     qword ptr [rdi], 0
0x18001e98a  lea     rdx, [rsp+78h+var_38]
0x18001e98f  mov     rcx, rdi
0x18001e992  call    ??$MakeAndInitialize@VBufferOverBlob@details@wil@@UIBuffer@Streams@Storage@Windows@@AEAVblob@bond@@@Details@WRL@Microsoft@@YAJPEAPEAUIBuffer@Streams@Storage@Windows@@AEAVblob@bond@@@Z; Microsoft::WRL::Details::MakeAndInitialize<wil::details::BufferOverBlob,Windows::Storage::Streams::IBuffer,bond::blob &>(Windows::Storage::Streams::IBuffer * *,bond::blob &)
0x18001e997  mov     rcx, [rsp+78h]; this
0x18001e99c  test    eax, eax
0x18001e99e  jns     short loc_18001E9B5
0x18001e9a0  mov     r9d, eax; char *
0x18001e9a3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001e9aa  mov     edx, 6DBh; void *
0x18001e9af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e9b5  lea     rcx, [rsp+78h+var_38]
0x18001e9ba  call    ??1?$shared_ptr@$$BY0A@$$CBD@boost@@QEAA@XZ; boost::shared_ptr<char const [0]>::~shared_ptr<char const [0]>(void)
0x18001e9bf  mov     rax, rdi
0x18001e9c2  mov     rbx, [rsp+78h+arg_8]
0x18001e9ca  add     rsp, 70h
0x18001e9ce  pop     rdi
0x18001e9cf  retn
```
