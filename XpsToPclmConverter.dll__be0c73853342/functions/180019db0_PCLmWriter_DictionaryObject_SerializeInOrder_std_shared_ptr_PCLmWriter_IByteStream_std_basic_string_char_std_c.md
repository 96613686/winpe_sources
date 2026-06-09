# PCLmWriter::DictionaryObject::SerializeInOrder(std::shared_ptr<PCLmWriter::IByteStream>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const * const,unsigned __int64)

- ea: `0x180019db0`
- end: `0x180019f6e`
- name: `?SerializeInOrder@DictionaryObject@PCLmWriter@@QEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_K@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180018fb0`

## callees

- `0x1800015f0`
- `0x180002154`
- `0x18000e7c8`
- `0x18000f3e0`
- `0x1800101cc`
- `0x180010618`
- `0x180010718`
- `0x180011600`
- `0x1800189c4`
- `0x180018b8c`
- `0x1800196c0`
- `0x180019db0`
- `0x18001a0e8`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PCLmWriter::DictionaryObject::SerializeInOrder(__int64 a1, _QWORD *a2, __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 i; // rsi
  __int64 v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  void (__fastcall *v12)(__int64, _QWORD *); // r8
  __int64 v13; // r9
  std::_Ref_count_base *v14; // rcx
  __int16 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v18; // [rsp+40h] [rbp-C0h]
  _QWORD *v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[56]; // [rsp+D0h] [rbp-30h] BYREF

  v19 = a2;
  v15 = 2592;
  for ( i = 0; i < a4; ++i )
  {
    (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, (char *)&v15 + 1, 1);
    v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(a3 + 32 * i);
    std::string::string(pExceptionObject, v9);
    PCLmWriter::NameObject::NameObject(v24, pExceptionObject, 0, 0);
    std::string::_Tidy_deallocate(pExceptionObject);
    v10 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v20, a2);
    PCLmWriter::NameObject::Serialize((__int64)v24, (__int64)v10);
    (*(void (__fastcall **)(_QWORD, __int16 *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, &v15, 1);
    std::string::string(v22, v9);
    std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(
      a1 + 24,
      &v16,
      v22);
    std::string::_Tidy_deallocate(v22);
    if ( *(_QWORD *)(a1 + 24) == v16 )
    {
      std::string::string(v22, "nullptr found in dictionary object key ");
      PCLmWriter::Exception::Exception((std::exception *)pExceptionObject);
      throw (PCLmWriter::Exception *)pExceptionObject;
    }
    std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v17, (_QWORD *)(v16 + 64));
    v11 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v21, a2);
    v12(v13, v11);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    PCLmWriter::NameObject::~NameObject((PCLmWriter::NameObject *)v24);
  }
  v14 = (std::_Ref_count_base *)a2[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
}

```

## disassembly

```asm
0x180019db0  push    rbp
0x180019db2  push    rbx
0x180019db3  push    rsi
0x180019db4  push    rdi
0x180019db5  push    r12
0x180019db7  push    r14
0x180019db9  push    r15
0x180019dbb  lea     rbp, [rsp-10h]
0x180019dc0  sub     rsp, 110h
0x180019dc7  mov     rax, cs:__security_cookie
0x180019dce  xor     rax, rsp
0x180019dd1  mov     [rbp+40h+var_38], rax
0x180019dd5  mov     r14, r9
0x180019dd8  mov     r12, r8
0x180019ddb  mov     rdi, rdx
0x180019dde  mov     r15, rcx
0x180019de1  mov     [rsp+140h+var_F8], rdx
0x180019de6  mov     [rsp+140h+var_120], 0A20h
0x180019ded  xor     esi, esi
0x180019def  cmp     rsi, r14
0x180019df2  jnb     loc_180019F42
0x180019df8  mov     rcx, [rdi]
0x180019dfb  mov     rax, [rcx]
0x180019dfe  mov     r8d, 1
0x180019e04  lea     rdx, [rsp+140h+var_120+1]
0x180019e09  mov     rax, [rax+18h]
0x180019e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e12  mov     rcx, rsi
0x180019e15  shl     rcx, 5
0x180019e19  add     rcx, r12
0x180019e1c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180019e21  mov     rbx, rax
0x180019e24  mov     rdx, rax
0x180019e27  lea     rcx, [rbp+40h+pExceptionObject]
0x180019e2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019e30  nop
0x180019e31  xor     r9d, r9d
0x180019e34  xor     r8d, r8d
0x180019e37  lea     rdx, [rbp+40h+pExceptionObject]
0x180019e3b  lea     rcx, [rbp+40h+var_70]
0x180019e3f  call    ??0NameObject@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@II@Z; PCLmWriter::NameObject::NameObject(std::string const &,uint,uint)
0x180019e44  nop
0x180019e45  lea     rcx, [rbp+40h+pExceptionObject]
0x180019e49  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019e4e  mov     rdx, rdi
0x180019e51  lea     rcx, [rsp+140h+var_F0]
0x180019e56  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019e5b  mov     rdx, rax
0x180019e5e  lea     rcx, [rbp+40h+var_70]
0x180019e62  call    ?Serialize@NameObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z; PCLmWriter::NameObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)
0x180019e67  mov     rcx, [rdi]
0x180019e6a  mov     rax, [rcx]
0x180019e6d  mov     r8d, 1
0x180019e73  lea     rdx, [rsp+140h+var_120]
0x180019e78  mov     rax, [rax+18h]
0x180019e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e81  mov     rdx, rbx
0x180019e84  lea     rcx, [rsp+140h+var_D0]
0x180019e89  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019e8e  lea     r8, [rsp+140h+var_D0]
0x180019e93  lea     rdx, [rsp+140h+var_118]
0x180019e98  lea     rcx, [r15+18h]
0x180019e9c  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(std::string const &)
0x180019ea1  lea     rcx, [rsp+140h+var_D0]
0x180019ea6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019eab  mov     rdx, [rsp+140h+var_118]
0x180019eb0  cmp     [r15+18h], rdx
0x180019eb4  jz      short loc_180019F0E
0x180019eb6  add     rdx, 40h ; '@'
0x180019eba  lea     rcx, [rsp+140h+var_108]
0x180019ebf  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019ec4  nop
0x180019ec5  mov     r9, [rsp+140h+var_108]
0x180019eca  mov     rax, [r9]
0x180019ecd  mov     r8, [rax+20h]
0x180019ed1  mov     rdx, rdi
0x180019ed4  lea     rcx, [rsp+140h+var_E0]
0x180019ed9  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019ede  mov     rdx, rax
0x180019ee1  mov     rcx, r9
0x180019ee4  mov     rax, r8
0x180019ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eec  nop
0x180019eed  mov     rcx, [rsp+140h+var_100]; this
0x180019ef2  test    rcx, rcx
0x180019ef5  jz      short loc_180019EFD
0x180019ef7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019efc  nop
0x180019efd  lea     rcx, [rbp+40h+var_70]; this
0x180019f01  call    ??1NameObject@PCLmWriter@@UEAA@XZ; PCLmWriter::NameObject::~NameObject(void)
0x180019f06  inc     rsi
0x180019f09  jmp     loc_180019DEF
0x180019f0e  lea     rdx, aNullptrFoundIn; "nullptr found in dictionary object key "
0x180019f15  lea     rcx, [rsp+140h+var_D0]
0x180019f1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019f1f  nop
0x180019f20  xor     r8d, r8d
0x180019f23  lea     rdx, [rsp+140h+var_D0]
0x180019f28  lea     rcx, [rbp+40h+pExceptionObject]; this
0x180019f2c  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x180019f31  lea     rdx, _TI2?AVException@PCLmWriter@@; pThrowInfo
0x180019f38  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x180019f3c  call    _CxxThrowException_0
0x180019f42  mov     rcx, [rdi+8]; this
0x180019f46  test    rcx, rcx
0x180019f49  jz      short loc_180019F50
0x180019f4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019f50  mov     rcx, [rbp+40h+var_38]
0x180019f54  xor     rcx, rsp; StackCookie
0x180019f57  call    __security_check_cookie
0x180019f5c  add     rsp, 110h
0x180019f63  pop     r15
0x180019f65  pop     r14
0x180019f67  pop     r12
0x180019f69  pop     rdi
0x180019f6a  pop     rsi
0x180019f6b  pop     rbx
0x180019f6c  pop     rbp
0x180019f6d  retn
```
