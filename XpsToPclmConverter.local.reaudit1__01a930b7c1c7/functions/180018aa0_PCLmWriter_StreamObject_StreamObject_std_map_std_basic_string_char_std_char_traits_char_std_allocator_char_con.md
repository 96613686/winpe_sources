# PCLmWriter::StreamObject::StreamObject(std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> const &,std::shared_ptr<PCLmWriter::IByteStream> const &,std::shared_ptr<PCLmWriter::IPDFFactory>,bool,uint,uint)

- ea: `0x180018aa0`
- end: `0x180018b83`
- name: `??0StreamObject@PCLmWriter@@QEAA@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEBV?$shared_ptr@VIByteStream@PCLmWriter@@@3@V?$shared_ptr@VIPDFFactory@PCLmWriter@@@3@_NII@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012a80`

## callees

- `0x18000e7c8`
- `0x1800101cc`
- `0x18001496c`
- `0x180018aa0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PCLmWriter::StreamObject::StreamObject(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        int a6,
        int a7)
{
  _QWORD *v9; // r9
  _QWORD *v10; // rcx
  __int64 v11; // r10
  __int64 *v12; // rax
  std::_Ref_count_base *v13; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v16; // [rsp+38h] [rbp-10h]

  *(_DWORD *)(a1 + 8) = a6;
  *(_DWORD *)(a1 + 12) = a7;
  *(_DWORD *)(a1 + 16) = 6;
  *(_QWORD *)a1 = &PCLmWriter::StreamObject::`vftable';
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)(a1 + 24), a3);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)(a1 + 40), v9);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_BYTE *)(a1 + 88) = a5;
  v12 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD, _DWORD))(*(_QWORD *)*v10 + 40LL))(
                     *v10,
                     v15,
                     v11,
                     0,
                     0);
  std::shared_ptr<PCLmWriter::IByteStream>::operator=((_QWORD *)(a1 + 56), v12);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v13 = *(std::_Ref_count_base **)(a4 + 8);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  return a1;
}

```

## disassembly

```asm
0x180018aa0  mov     rax, rsp
0x180018aa3  mov     [rax+10h], rbx
0x180018aa7  mov     [rax+18h], rsi
0x180018aab  mov     [rax+20h], r9
0x180018aaf  mov     [rax+8], rcx
0x180018ab3  push    rdi
0x180018ab4  sub     rsp, 40h
0x180018ab8  mov     rsi, r9
0x180018abb  mov     r10, rdx
0x180018abe  mov     rdi, rcx
0x180018ac1  mov     eax, [rsp+48h+arg_28]
0x180018ac5  mov     [rcx+8], eax
0x180018ac8  mov     eax, [rsp+48h+arg_30]
0x180018acf  mov     [rcx+0Ch], eax
0x180018ad2  mov     dword ptr [rcx+10h], 6
0x180018ad9  lea     rax, ??_7StreamObject@PCLmWriter@@6B@; const PCLmWriter::StreamObject::`vftable'
0x180018ae0  mov     [rcx], rax
0x180018ae3  add     rcx, 18h
0x180018ae7  mov     rdx, r8
0x180018aea  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180018aef  nop
0x180018af0  lea     rcx, [rdi+28h]
0x180018af4  mov     rdx, r9
0x180018af7  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180018afc  nop
0x180018afd  mov     qword ptr [rdi+38h], 0
0x180018b05  mov     qword ptr [rdi+40h], 0
0x180018b0d  mov     qword ptr [rdi+48h], 0
0x180018b15  mov     qword ptr [rdi+50h], 0
0x180018b1d  mov     al, [rsp+48h+arg_20]
0x180018b21  mov     [rdi+58h], al
0x180018b24  mov     rcx, [rcx]
0x180018b27  mov     rax, [rcx]
0x180018b2a  mov     [rsp+48h+var_28], 0
0x180018b32  xor     r9d, r9d
0x180018b35  mov     r8, r10
0x180018b38  lea     rdx, [rsp+48h+var_18]
0x180018b3d  mov     rax, [rax+28h]
0x180018b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b46  mov     rdx, rax
0x180018b49  lea     rcx, [rdi+38h]
0x180018b4d  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x180018b52  mov     rcx, [rsp+48h+var_10]; this
0x180018b57  test    rcx, rcx
0x180018b5a  jz      short loc_180018B62
0x180018b5c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b61  nop
0x180018b62  mov     rcx, [rsi+8]; this
0x180018b66  test    rcx, rcx
0x180018b69  jz      short loc_180018B70
0x180018b6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b70  mov     rax, rdi
0x180018b73  mov     rbx, [rsp+48h+arg_8]
0x180018b78  mov     rsi, [rsp+48h+arg_10]
0x180018b7d  add     rsp, 40h
0x180018b81  pop     rdi
0x180018b82  retn
```
