# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Construct_n<std::shared_ptr<PCLmWriter::IObject const> * const &,std::shared_ptr<PCLmWriter::IObject const> * const &>(unsigned __int64,std::shared_ptr<PCLmWriter::IObject const> * const &,std::shared_ptr<PCLmWriter::IObject const> * const &)

- ea: `0x180010c08`
- end: `0x180010c79`
- name: `??$_Construct_n@AEBQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@AEBQEAV12@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAX_KAEBQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@1@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800114fc`

## callees

- `0x18000e7c8`
- `0x18000ee2c`
- `0x180010c08`
- `0x1800117e4`
- `0x180012d34`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Construct_n<std::shared_ptr<PCLmWriter::IObject const> * const &,std::shared_ptr<PCLmWriter::IObject const> * const &>(
        __int64 a1,
        __int64 a2,
        _QWORD **a3,
        _QWORD *a4)
{
  _QWORD *v7; // r9
  _QWORD *v8; // rbx
  _QWORD *i; // rdx
  __int64 v10; // rdx
  __int64 result; // rax
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Buy_nonzero();
    v7 = (_QWORD *)*a4;
    v8 = *(_QWORD **)a1;
    for ( i = *a3; i != v7; i = (_QWORD *)(v10 + 16) )
    {
      std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v8, i);
      v8 += 2;
    }
    std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>((__int64)v8, (__int64)v8);
    *(_QWORD *)(a1 + 8) = v8;
    v12 = 0;
    return std::_Tidy_guard<std::vector<std::shared_ptr<PCLmWriter::IObject const>>>::~_Tidy_guard<std::vector<std::shared_ptr<PCLmWriter::IObject const>>>(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x180010c08  test    rdx, rdx
0x180010c0b  jz      short locret_180010C78
0x180010c0d  mov     [rsp+arg_8], rbx
0x180010c12  mov     [rsp+arg_10], rsi
0x180010c17  push    rdi
0x180010c18  sub     rsp, 20h
0x180010c1c  mov     rbx, r9
0x180010c1f  mov     rsi, r8
0x180010c22  mov     rdi, rcx
0x180010c25  call    ?_Buy_nonzero@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Buy_nonzero(unsigned __int64)
0x180010c2a  mov     r9, [rbx]
0x180010c2d  mov     rbx, [rdi]
0x180010c30  mov     rdx, [rsi]
0x180010c33  jmp     short loc_180010C42
0x180010c35  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180010c3a  add     rbx, 10h
0x180010c3e  add     rdx, 10h
0x180010c42  mov     rcx, rbx
0x180010c45  cmp     rdx, r9
0x180010c48  jnz     short loc_180010C35
0x180010c4a  mov     rdx, rbx
0x180010c4d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x180010c52  lea     rcx, [rsp+28h+arg_0]
0x180010c57  mov     [rdi+8], rbx
0x180010c5b  mov     [rsp+28h+arg_0], 0
0x180010c64  call    ??1?$_Tidy_guard@V?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<std::shared_ptr<PCLmWriter::IObject const>>>::~_Tidy_guard<std::vector<std::shared_ptr<PCLmWriter::IObject const>>>(void)
0x180010c69  mov     rbx, [rsp+28h+arg_8]
0x180010c6e  mov     rsi, [rsp+28h+arg_10]
0x180010c73  add     rsp, 20h
0x180010c77  pop     rdi
0x180010c78  retn
```
