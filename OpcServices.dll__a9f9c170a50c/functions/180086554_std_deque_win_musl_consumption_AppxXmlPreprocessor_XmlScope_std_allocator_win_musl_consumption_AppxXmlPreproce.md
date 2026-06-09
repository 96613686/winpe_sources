# std::deque<win_musl::consumption::AppxXmlPreprocessor::XmlScope,std::allocator<win_musl::consumption::AppxXmlPreprocessor::XmlScope>>::_Growmap(unsigned __int64)

- ea: `0x180086554`
- end: `0x180086734`
- name: `?_Growmap@?$deque@VXmlScope@AppxXmlPreprocessor@consumption@win_musl@@V?$allocator@VXmlScope@AppxXmlPreprocessor@consumption@win_musl@@@std@@@std@@IEAAX_K@Z`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180035b90`
- `0x180035ce0`

## callees

- `0x1800297e0`
- `0x180044804`
- `0x180086554`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800d5fe4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18008661e`
- `msvcrt!memmove_s` at `0x180086650`
- `msvcrt!memmove_s` at `0x18008661e`
- `msvcrt!memmove_s` at `0x180086650`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180086710`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180086710`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::deque<win_musl::consumption::AppxXmlPreprocessor::XmlScope>::_Growmap(_QWORD *a1, const char *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rbp
  char *v8; // rax
  void *v9; // r12
  __int64 v10; // rsi
  char *v11; // r15
  char *v12; // r10
  __int64 v13; // rcx
  __int64 v14; // r14
  char *v15; // r15
  size_t v16; // r8
  void *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  const char *v21; // [rsp+78h] [rbp+10h] BYREF

  v21 = a2;
  v3 = a1[2];
  v4 = 1;
  if ( v3 == 0x2E8BA2E8BA2E8BALL )
    std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(0x2E8BA2E8BA2E8BALL);
  v5 = v3 >> 1;
  if ( v3 >> 1 < 8 )
    v5 = 8;
  if ( v3 <= 0x2E8BA2E8BA2E8BALL - v5 )
    v4 = v5;
  v6 = v4 + v3;
  if ( v6 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v6 < 8 )
    {
      v21 = 0;
      exception::exception((exception *)pExceptionObject, &v21);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = a1[3];
  v8 = (char *)operator new(8 * v6);
  v9 = v8;
  v10 = 8 * v7;
  v11 = &v8[8 * v7];
  v12 = (char *)a1[1];
  v13 = (__int64)(8LL * a1[2] - 8 * v7) >> 3;
  v14 = 8 * v13;
  if ( v13 )
  {
    memmove_s(&v8[8 * v7], 8 * v13, &v12[8 * v7], 8 * v13);
    v12 = (char *)a1[1];
  }
  v15 = &v11[v14];
  if ( v7 > v4 )
  {
    std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(v12);
    v19 = std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>((void *)(8 * v4 + a1[1]));
    if ( v4 )
    {
      v16 = 8 * v4;
      v17 = (void *)v19;
      goto LABEL_17;
    }
  }
  else
  {
    if ( v10 >> 3 )
      memmove_s(v15, 8 * (v10 >> 3), v12, 8 * (v10 >> 3));
    if ( v4 != v7 )
      memset_0(&v15[8 * (v10 >> 3)], 0, 8 * (v4 - v7));
    if ( v7 )
    {
      v16 = 8 * v7;
      v17 = v9;
LABEL_17:
      memset_0(v17, 0, v16);
    }
  }
  v18 = (void *)a1[1];
  if ( v18 )
    operator delete(v18);
  a1[1] = v9;
  a1[2] += v4;
}

```

## disassembly

```asm
0x180086554  mov     rax, rsp
0x180086557  mov     [rax+10h], rdx
0x18008655b  push    rsi
0x18008655c  push    rdi
0x18008655d  push    r12
0x18008655f  push    r14
0x180086561  push    r15
0x180086563  sub     rsp, 40h
0x180086567  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18008656f  mov     [rax+8], rbx
0x180086573  mov     [rax+18h], rbp
0x180086577  mov     rbx, rcx
0x18008657a  mov     rcx, [rcx+10h]
0x18008657e  mov     rdx, 2E8BA2E8BA2E8BAh
0x180086588  mov     rax, rdx
0x18008658b  sub     rax, rcx
0x18008658e  mov     edi, 1
0x180086593  cmp     rax, rdi
0x180086596  jb      loc_1800866F0
0x18008659c  mov     rax, rcx
0x18008659f  shr     rax, 1
0x1800865a2  lea     r8d, [rdi+7]
0x1800865a6  cmp     rax, r8
0x1800865a9  cmovb   rax, r8
0x1800865ad  sub     rdx, rax
0x1800865b0  cmp     rcx, rdx
0x1800865b3  cmovbe  rdi, rax
0x1800865b7  add     rcx, rdi
0x1800865ba  jz      loc_1800866F6
0x1800865c0  xor     edx, edx
0x1800865c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800865c6  div     rcx
0x1800865c9  cmp     rax, r8
0x1800865cc  jb      loc_1800866FD
0x1800865d2  mov     rbp, [rbx+18h]
0x1800865d6  shl     rcx, 3; Size
0x1800865da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800865df  mov     r12, rax
0x1800865e2  lea     rsi, ds:0[rbp*8]
0x1800865ea  lea     r15, [rsi+rax]
0x1800865ee  mov     r10, [rbx+8]
0x1800865f2  lea     r8, [r10+rsi]; Source
0x1800865f6  mov     rcx, [rbx+10h]
0x1800865fa  shl     rcx, 3
0x1800865fe  sub     rcx, r8
0x180086601  add     rcx, r10
0x180086604  sar     rcx, 3
0x180086608  lea     r14, ds:0[rcx*8]
0x180086610  test    rcx, rcx
0x180086613  jz      short loc_180086628
0x180086615  mov     r9, r14; SourceSize
0x180086618  mov     rdx, r14; DestinationSize
0x18008661b  mov     rcx, r15; Destination
0x18008661e  call    cs:__imp_memmove_s
0x180086624  mov     r10, [rbx+8]
0x180086628  add     r15, r14
0x18008662b  cmp     rbp, rdi
0x18008662e  ja      short loc_1800866AD
0x180086630  mov     rax, rsi
0x180086633  sar     rax, 3
0x180086637  lea     r14, ds:0[rax*8]
0x18008663f  test    rax, rax
0x180086642  jz      short loc_180086656
0x180086644  mov     r9, r14; SourceSize
0x180086647  mov     r8, r10; Source
0x18008664a  mov     rdx, r14; DestinationSize
0x18008664d  mov     rcx, r15; Destination
0x180086650  call    cs:__imp_memmove_s
0x180086656  mov     r8, rdi
0x180086659  sub     r8, rbp
0x18008665c  lea     rcx, [r14+r15]; void *
0x180086660  jz      short loc_18008666D
0x180086662  shl     r8, 3; Size
0x180086666  xor     edx, edx; Val
0x180086668  call    memset_0
0x18008666d  test    rbp, rbp
0x180086670  jz      short loc_180086683
0x180086672  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180086676  mov     r8, rsi; Size
0x180086679  mov     rcx, r12; void *
0x18008667c  xor     edx, edx; Val
0x18008667e  call    memset_0
0x180086683  mov     rcx, [rbx+8]; Block
0x180086687  test    rcx, rcx
0x18008668a  jnz     short loc_1800866E9
0x18008668c  mov     [rbx+8], r12
0x180086690  add     [rbx+10h], rdi
0x180086694  lea     r11, [rsp+68h+var_28]
0x180086699  mov     rbx, [r11+30h]
0x18008669d  mov     rbp, [r11+40h]
0x1800866a1  mov     rsp, r11
0x1800866a4  pop     r15
0x1800866a6  pop     r14
0x1800866a8  pop     r12
0x1800866aa  pop     rdi
0x1800866ab  pop     rsi
0x1800866ac  retn
0x1800866ad  lea     r14, ds:0[rdi*8]
0x1800866b5  lea     rdx, [r14+r10]
0x1800866b9  mov     r8, r15
0x1800866bc  mov     rcx, r10; Source
0x1800866bf  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x1800866c4  mov     rax, [rbx+8]
0x1800866c8  lea     rdx, [rax+rsi]
0x1800866cc  lea     rcx, [r14+rax]; Source
0x1800866d0  mov     r8, r12
0x1800866d3  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x1800866d8  test    rdi, rdi
0x1800866db  jz      short loc_180086683
0x1800866dd  and     r14, 0FFFFFFFFFFFFFFF8h
0x1800866e1  mov     r8, r14
0x1800866e4  mov     rcx, rax
0x1800866e7  jmp     short loc_18008667C
0x1800866e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800866ee  jmp     short loc_18008668C
0x1800866f0  call    ?_Xlen@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@KAXXZ; std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(void)
0x1800866f6  xor     ecx, ecx
0x1800866f8  jmp     loc_1800865D2
0x1800866fd  mov     [rsp+68h+arg_8], 0
0x180086706  lea     rdx, [rsp+68h+arg_8]
0x18008670b  lea     rcx, [rsp+68h+pExceptionObject]
0x180086710  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180086716  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18008671d  mov     [rsp+68h+pExceptionObject], rax
0x180086722  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180086729  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18008672e  call    _CxxThrowException_0
```
