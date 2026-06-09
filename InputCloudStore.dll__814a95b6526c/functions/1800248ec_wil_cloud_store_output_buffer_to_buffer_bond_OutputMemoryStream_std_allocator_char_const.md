# wil::cloud_store::output_buffer_to_buffer(bond::OutputMemoryStream<std::allocator<char>> const &)

- ea: `0x1800248ec`
- end: `0x180024960`
- name: `?output_buffer_to_buffer@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@AEBV?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016000`
- `0x180016104`
- `0x180016208`
- `0x18001630c`
- `0x180016410`
- `0x180016514`
- `0x180016618`
- `0x18001671c`

## callees

- `0x18000cce8`
- `0x18001b8d8`
- `0x18001f6f8`
- `0x180022b80`
- `0x1800248ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::cloud_store::output_buffer_to_buffer(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  _BYTE v5[8]; // [rsp+28h] [rbp-30h] BYREF
  _BYTE v6[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  bond::OutputMemoryStream<std::allocator<char>>::GetBuffer(a2, v5);
  *a1 = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<wil::details::BufferOverBlob,Windows::Storage::Streams::IBuffer,bond::blob &>(
         a1,
         v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6DB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v3,
      1);
  boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v6);
  return a1;
}

```

## disassembly

```asm
0x1800248ec  mov     [rsp+arg_0], rcx
0x1800248f1  push    rbx
0x1800248f2  sub     rsp, 50h
0x1800248f6  mov     rax, rdx
0x1800248f9  mov     rbx, rcx
0x1800248fc  mov     [rsp+58h+var_38], 0
0x180024904  lea     rdx, [rsp+58h+var_30]
0x180024909  mov     rcx, rax
0x18002490c  call    ?GetBuffer@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEBA?AVblob@2@XZ; bond::OutputMemoryStream<std::allocator<char>>::GetBuffer(void)
0x180024911  nop
0x180024912  mov     [rsp+58h+var_38], 1; int
0x18002491a  mov     qword ptr [rbx], 0
0x180024921  lea     rdx, [rsp+58h+var_30]
0x180024926  mov     rcx, rbx
0x180024929  call    ??$MakeAndInitialize@VBufferOverBlob@details@wil@@UIBuffer@Streams@Storage@Windows@@AEAVblob@bond@@@Details@WRL@Microsoft@@YAJPEAPEAUIBuffer@Streams@Storage@Windows@@AEAVblob@bond@@@Z; Microsoft::WRL::Details::MakeAndInitialize<wil::details::BufferOverBlob,Windows::Storage::Streams::IBuffer,bond::blob &>(Windows::Storage::Streams::IBuffer * *,bond::blob &)
0x18002492e  mov     rcx, [rsp+58h]; this
0x180024933  test    eax, eax
0x180024935  jns     short loc_18002494C
0x180024937  mov     r9d, eax; char *
0x18002493a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180024941  mov     edx, 6DBh; void *
0x180024946  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002494c  lea     rcx, [rsp+58h+var_28]; this
0x180024951  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180024956  mov     rax, rbx
0x180024959  add     rsp, 50h
0x18002495d  pop     rbx
0x18002495e  retn
```
