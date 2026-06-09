# std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>,std::allocator<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>>::_Growmap(unsigned __int64)

- ea: `0x18007c114`
- end: `0x18007c2d4`
- name: `?_Growmap@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@IEAAX_K@Z`
- size: `448`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180012874`
- `0x180012d18`
- `0x180015180`

## callees

- `0x1800297e0`
- `0x180044804`
- `0x18007c114`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800d5fe4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18007c1d0`
- `msvcrt!memmove_s` at `0x18007c1d0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18007c273`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18007c273`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Growmap(
        _QWORD *a1,
        const char *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r14
  char *v8; // rax
  void *v9; // r12
  __int64 v10; // rdx
  void *v11; // rcx
  void *v12; // rax
  size_t v13; // r8
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rax
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  const char *v18; // [rsp+78h] [rbp+10h] BYREF

  v18 = a2;
  v3 = a1[2];
  v4 = 1;
  if ( v3 == 0xFFFFFFFFFFFFFFFLL )
    std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(0xFFFFFFFFFFFFFFFLL);
  v5 = v3 >> 1;
  if ( v3 >> 1 < 8 )
    v5 = 8;
  if ( v3 <= 0xFFFFFFFFFFFFFFFLL - v5 )
    v4 = v5;
  v6 = v4 + v3;
  if ( v6 && 0xFFFFFFFFFFFFFFFFuLL / v6 < 8 )
  {
    v18 = 0;
    exception::exception((exception *)pExceptionObject, &v18);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v7 = a1[3];
  v8 = (char *)operator new(8 * v6);
  v9 = v8;
  v10 = (__int64)(8LL * a1[2] - 8 * v7) >> 3;
  if ( v10 )
    memmove_s(&v8[8 * v7], 8 * v10, (const void *const)(a1[1] + 8 * v7), 8 * v10);
  v11 = (void *)a1[1];
  if ( v7 > v4 )
  {
    std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(v11);
    v16 = std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>((void *)(8 * v4 + a1[1]));
    if ( v4 )
    {
      v13 = 8 * v4;
      v14 = (void *)v16;
      goto LABEL_15;
    }
  }
  else
  {
    v12 = (void *)std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(v11);
    if ( v4 != v7 )
      memset_0(v12, 0, 8 * (v4 - v7));
    if ( v7 )
    {
      v13 = 8 * v7;
      v14 = v9;
LABEL_15:
      memset_0(v14, 0, v13);
    }
  }
  v15 = (void *)a1[1];
  if ( v15 )
    operator delete(v15);
  a1[1] = v9;
  a1[2] += v4;
}

```

## disassembly

```asm
0x18007c114  mov     rax, rsp
0x18007c117  mov     [rax+10h], rdx
0x18007c11b  push    rsi
0x18007c11c  push    rdi
0x18007c11d  push    r12
0x18007c11f  push    r14
0x18007c121  push    r15
0x18007c123  sub     rsp, 40h
0x18007c127  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18007c12f  mov     [rax+8], rbx
0x18007c133  mov     [rax+18h], rbp
0x18007c137  mov     rbx, rcx
0x18007c13a  mov     rcx, [rcx+10h]
0x18007c13e  mov     rdx, 0FFFFFFFFFFFFFFFh
0x18007c148  mov     rax, rdx
0x18007c14b  sub     rax, rcx
0x18007c14e  mov     edi, 1
0x18007c153  cmp     rax, rdi
0x18007c156  jnb     short loc_18007C15E
0x18007c158  call    ?_Xlen@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@KAXXZ; std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(void)
0x18007c15e  mov     rax, rcx
0x18007c161  shr     rax, 1
0x18007c164  mov     r8d, 8
0x18007c16a  cmp     rax, r8
0x18007c16d  cmovb   rax, r8
0x18007c171  sub     rdx, rax
0x18007c174  cmp     rcx, rdx
0x18007c177  cmovbe  rdi, rax
0x18007c17b  add     rcx, rdi
0x18007c17e  jnz     loc_18007C24E
0x18007c184  mov     r14, [rbx+18h]
0x18007c188  shl     rcx, 3; Size
0x18007c18c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c191  mov     r12, rax
0x18007c194  lea     rsi, ds:0[r14*8]
0x18007c19c  lea     rbp, [rsi+rax]
0x18007c1a0  mov     rcx, [rbx+8]
0x18007c1a4  lea     r8, [rcx+rsi]; Source
0x18007c1a8  mov     rdx, [rbx+10h]
0x18007c1ac  shl     rdx, 3
0x18007c1b0  sub     rdx, r8
0x18007c1b3  add     rdx, rcx
0x18007c1b6  sar     rdx, 3
0x18007c1ba  lea     r15, ds:0[rdx*8]
0x18007c1c2  test    rdx, rdx
0x18007c1c5  jz      short loc_18007C1D6
0x18007c1c7  mov     r9, r15; SourceSize
0x18007c1ca  mov     rdx, r15; DestinationSize
0x18007c1cd  mov     rcx, rbp; Destination
0x18007c1d0  call    cs:__imp_memmove_s
0x18007c1d6  lea     r8, [r15+rbp]
0x18007c1da  mov     rcx, [rbx+8]; Source
0x18007c1de  cmp     r14, rdi
0x18007c1e1  ja      loc_18007C297
0x18007c1e7  mov     rbp, rdi
0x18007c1ea  lea     rdx, [rcx+rsi]
0x18007c1ee  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x18007c1f3  sub     rbp, r14
0x18007c1f6  jz      short loc_18007C209
0x18007c1f8  shl     rbp, 3
0x18007c1fc  mov     r8, rbp; Size
0x18007c1ff  xor     edx, edx; Val
0x18007c201  mov     rcx, rax; void *
0x18007c204  call    memset_0
0x18007c209  test    r14, r14
0x18007c20c  jz      short loc_18007C21F
0x18007c20e  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18007c212  mov     r8, rsi; Size
0x18007c215  mov     rcx, r12; void *
0x18007c218  xor     edx, edx; Val
0x18007c21a  call    memset_0
0x18007c21f  mov     rcx, [rbx+8]; Block
0x18007c223  test    rcx, rcx
0x18007c226  jz      short loc_18007C22D
0x18007c228  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c22d  mov     [rbx+8], r12
0x18007c231  add     [rbx+10h], rdi
0x18007c235  lea     r11, [rsp+68h+var_28]
0x18007c23a  mov     rbx, [r11+30h]
0x18007c23e  mov     rbp, [r11+40h]
0x18007c242  mov     rsp, r11
0x18007c245  pop     r15
0x18007c247  pop     r14
0x18007c249  pop     r12
0x18007c24b  pop     rdi
0x18007c24c  pop     rsi
0x18007c24d  retn
0x18007c24e  xor     edx, edx
0x18007c250  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c254  div     rcx
0x18007c257  cmp     rax, r8
0x18007c25a  jnb     loc_18007C184
0x18007c260  mov     [rsp+68h+arg_8], 0
0x18007c269  lea     rdx, [rsp+68h+arg_8]
0x18007c26e  lea     rcx, [rsp+68h+pExceptionObject]
0x18007c273  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18007c279  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18007c280  mov     [rsp+68h+pExceptionObject], rax
0x18007c285  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18007c28c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18007c291  call    _CxxThrowException_0
0x18007c297  lea     r14, ds:0[rdi*8]
0x18007c29f  lea     rdx, [r14+rcx]
0x18007c2a3  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x18007c2a8  mov     rax, [rbx+8]
0x18007c2ac  lea     rdx, [rax+rsi]
0x18007c2b0  lea     rcx, [r14+rax]; Source
0x18007c2b4  mov     r8, r12
0x18007c2b7  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x18007c2bc  test    rdi, rdi
0x18007c2bf  jz      loc_18007C21F
0x18007c2c5  and     r14, 0FFFFFFFFFFFFFFF8h
0x18007c2c9  mov     r8, r14
0x18007c2cc  mov     rcx, rax
0x18007c2cf  jmp     loc_18007C218
```
