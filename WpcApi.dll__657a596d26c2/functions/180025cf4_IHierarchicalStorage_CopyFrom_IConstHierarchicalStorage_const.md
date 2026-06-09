# IHierarchicalStorage::CopyFrom(IConstHierarchicalStorage const &)

- ea: `0x180025cf4`
- end: `0x180026049`
- name: `?CopyFrom@IHierarchicalStorage@@QEAAXAEBUIConstHierarchicalStorage@@@Z`
- size: `853`
- prototype: `void __fastcall(IHierarchicalStorage *__hidden this, const struct IConstHierarchicalStorage *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800273a4`

## callees

- `0x1800032c4`
- `0x180016804`
- `0x18001938c`
- `0x18001941c`
- `0x180024550`
- `0x180024b1c`
- `0x180025cf4`
- `0x18002c010`

## pseudocode

```c
void __fastcall IHierarchicalStorage::CopyFrom(IHierarchicalStorage *this, const struct IConstHierarchicalStorage *a2)
{
  __int64 v4; // rsi
  __int64 v5; // r14
  char *v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rdi
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rbx
  __int64 v23; // [rsp+20h] [rbp-49h] BYREF
  volatile signed __int32 *v24; // [rsp+28h] [rbp-41h]
  _QWORD v25[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  volatile signed __int32 *v27; // [rsp+48h] [rbp-21h]
  char v28[8]; // [rsp+50h] [rbp-19h] BYREF
  volatile signed __int32 *v29; // [rsp+58h] [rbp-11h]
  _BYTE v30[16]; // [rsp+60h] [rbp-9h] BYREF
  char v31[8]; // [rsp+70h] [rbp+7h] BYREF
  volatile signed __int32 *v32; // [rsp+78h] [rbp+Fh]
  char v33[8]; // [rsp+80h] [rbp+17h] BYREF
  volatile signed __int32 *v34; // [rsp+88h] [rbp+1Fh]
  char *v35; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v36; // [rsp+E0h] [rbp+77h] BYREF

  v4 = (*(__int64 (__fastcall **)(const struct IConstHierarchicalStorage *, char *))(*(_QWORD *)a2 + 16LL))(a2, v33);
  v5 = (*(__int64 (__fastcall **)(const struct IConstHierarchicalStorage *, char *))(*(_QWORD *)a2 + 8LL))(a2, v31);
  v6 = (char *)operator new(0x28u);
  *(_OWORD *)v6 = 0;
  *((_DWORD *)v6 + 2) = 1;
  *((_DWORD *)v6 + 3) = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable';
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  v25[0] = v6 + 16;
  v25[1] = v6;
  v35 = v28;
  v8 = Collections::Enumerable<std::wstring>::end(v7, v28);
  v9 = Collections::Enumerable<std::wstring>::begin(v4, v30);
  std::copy<Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>>(
    &v35,
    v9,
    v8,
    (__int64)(v6 + 16));
  v35 = v30;
  v11 = Collections::Enumerable<std::wstring>::end(v10, v30);
  v12 = Collections::Enumerable<std::wstring>::begin(v5, v28);
  std::copy<Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>>(
    &v35,
    v12,
    v11,
    (__int64)(v6 + 16));
  Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(v28, v25);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v6)(v6);
    if ( !_InterlockedDecrement((volatile signed __int32 *)v6 + 3) )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  }
  v13 = v32;
  if ( v32 )
  {
    if ( !_InterlockedDecrement(v32 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( !_InterlockedDecrement(v13 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = v34;
  if ( v34 )
  {
    if ( !_InterlockedDecrement(v34 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( !_InterlockedDecrement(v14 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  Collections::Enumerable<std::wstring>::begin(v28, &v23);
  Collections::Enumerable<std::wstring>::end(v15, &v26);
  while ( v23 != v26 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v17 = *(_QWORD *)(**(__int64 (__fastcall ***)(IHierarchicalStorage *, __int64 *, __int64))this)(this, &v36, v16);
    v18 = (_QWORD *)(*(__int64 (__fastcall **)(const struct IConstHierarchicalStorage *, char **, __int64))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      &v35,
                      v16);
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 64LL))(*v18, v17);
    if ( v35 )
      (**(void (__fastcall ***)(char *, __int64))v35)(v35, 1);
    if ( v36 )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(v36 + *(int *)(*(_QWORD *)(v36 + 8) + 4LL) + 8LL);
      (**v19)(v19, 1);
    }
    Collections::Private::EnumerableIterator<std::wstring>::operator++(&v23);
  }
  v20 = v27;
  if ( v27 )
  {
    if ( !_InterlockedDecrement(v27 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( !_InterlockedDecrement(v20 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = v24;
  if ( v24 )
  {
    if ( !_InterlockedDecrement(v24 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( !_InterlockedDecrement(v21 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v22 = v29;
  if ( v29 )
  {
    if ( !_InterlockedDecrement(v29 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
}

```

## disassembly

```asm
0x180025cf4  mov     [rsp-8+arg_0], rbx
0x180025cf9  push    rbp
0x180025cfa  push    rsi
0x180025cfb  push    rdi
0x180025cfc  push    r12
0x180025cfe  push    r13
0x180025d00  push    r14
0x180025d02  push    r15
0x180025d04  lea     rbp, [rsp-27h]
0x180025d09  sub     rsp, 90h
0x180025d10  mov     r12, rdx
0x180025d13  mov     r13, rcx
0x180025d16  xor     ebx, ebx
0x180025d18  mov     rax, [rdx]
0x180025d1b  lea     rdx, [rbp+57h+var_40]
0x180025d1f  mov     rcx, r12
0x180025d22  mov     rax, [rax+10h]
0x180025d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d2b  mov     rsi, rax
0x180025d2e  mov     rcx, [r12]
0x180025d32  mov     rax, [rcx+8]
0x180025d36  lea     rdx, [rbp+57h+var_50]
0x180025d3a  mov     rcx, r12
0x180025d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d42  mov     r14, rax
0x180025d45  lea     ecx, [rbx+28h]; Size
0x180025d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025d4d  mov     r15, rax
0x180025d50  mov     [rbp+57h+arg_8], rax
0x180025d54  xorps   xmm0, xmm0
0x180025d57  movups  xmmword ptr [rax], xmm0
0x180025d5a  lea     eax, [rbx+1]
0x180025d5d  mov     [r15+8], eax
0x180025d61  mov     [r15+0Ch], eax
0x180025d65  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable'
0x180025d6c  mov     [r15], rax
0x180025d6f  lea     rdi, [r15+10h]
0x180025d73  mov     [rdi], rbx
0x180025d76  mov     [rdi+8], rbx
0x180025d7a  mov     [rdi+10h], rbx
0x180025d7e  mov     [rbp+57h+var_90], rdi
0x180025d82  mov     [rbp+57h+var_88], r15
0x180025d86  lea     rax, [rbp+57h+var_70]
0x180025d8a  mov     [rbp+57h+arg_8], rax
0x180025d8e  lea     rdx, [rbp+57h+var_70]
0x180025d92  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x180025d97  mov     rbx, rax
0x180025d9a  lea     rdx, [rbp+57h+var_60]
0x180025d9e  mov     rcx, rsi
0x180025da1  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x180025da6  nop
0x180025da7  mov     r9, rdi
0x180025daa  mov     r8, rbx
0x180025dad  mov     rdx, rax
0x180025db0  lea     rcx, [rbp+57h+arg_8]
0x180025db4  call    ??$copy@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@0V10@@Z; std::copy<Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>>(Collections::Private::EnumerableIterator<std::wstring>,Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>)
0x180025db9  lea     rax, [rbp+57h+var_60]
0x180025dbd  mov     [rbp+57h+arg_8], rax
0x180025dc1  lea     rdx, [rbp+57h+var_60]
0x180025dc5  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x180025dca  mov     rbx, rax
0x180025dcd  lea     rdx, [rbp+57h+var_70]
0x180025dd1  mov     rcx, r14
0x180025dd4  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x180025dd9  nop
0x180025dda  mov     r9, rdi
0x180025ddd  mov     r8, rbx
0x180025de0  mov     rdx, rax
0x180025de3  lea     rcx, [rbp+57h+arg_8]
0x180025de7  call    ??$copy@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@0V10@@Z; std::copy<Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>>(Collections::Private::EnumerableIterator<std::wstring>,Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>)
0x180025dec  lea     rdx, [rbp+57h+var_90]
0x180025df0  lea     rcx, [rbp+57h+var_70]
0x180025df4  call    ??$?0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEAA@AEBV?$shared_ptr@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@Z; Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(std::shared_ptr<std::vector<std::wstring>> const &)
0x180025df9  nop
0x180025dfa  or      esi, 0FFFFFFFFh
0x180025dfd  mov     eax, esi
0x180025dff  lock xadd [r15+8], eax
0x180025e05  add     eax, esi
0x180025e07  jnz     short loc_180025E33
0x180025e09  mov     rax, [r15]
0x180025e0c  mov     rcx, r15
0x180025e0f  mov     rax, [rax]
0x180025e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e17  mov     eax, esi
0x180025e19  lock xadd [r15+0Ch], eax
0x180025e1f  add     eax, esi
0x180025e21  jnz     short loc_180025E33
0x180025e23  mov     rax, [r15]
0x180025e26  mov     rcx, r15
0x180025e29  mov     rax, [rax+8]
0x180025e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e32  nop
0x180025e33  mov     rbx, [rbp+57h+var_48]
0x180025e37  test    rbx, rbx
0x180025e3a  jz      short loc_180025E70
0x180025e3c  mov     eax, esi
0x180025e3e  lock xadd [rbx+8], eax
0x180025e43  add     eax, esi
0x180025e45  jnz     short loc_180025E70
0x180025e47  mov     rax, [rbx]
0x180025e4a  mov     rcx, rbx
0x180025e4d  mov     rax, [rax]
0x180025e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e55  mov     eax, esi
0x180025e57  lock xadd [rbx+0Ch], eax
0x180025e5c  add     eax, esi
0x180025e5e  jnz     short loc_180025E70
0x180025e60  mov     rax, [rbx]
0x180025e63  mov     rcx, rbx
0x180025e66  mov     rax, [rax+8]
0x180025e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e6f  nop
0x180025e70  mov     rbx, [rbp+57h+var_38]
0x180025e74  test    rbx, rbx
0x180025e77  jz      short loc_180025EAC
0x180025e79  mov     eax, esi
0x180025e7b  lock xadd [rbx+8], eax
0x180025e80  add     eax, esi
0x180025e82  jnz     short loc_180025EAC
0x180025e84  mov     rax, [rbx]
0x180025e87  mov     rcx, rbx
0x180025e8a  mov     rax, [rax]
0x180025e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e92  mov     eax, esi
0x180025e94  lock xadd [rbx+0Ch], eax
0x180025e99  add     eax, esi
0x180025e9b  jnz     short loc_180025EAC
0x180025e9d  mov     rax, [rbx]
0x180025ea0  mov     rcx, rbx
0x180025ea3  mov     rax, [rax+8]
0x180025ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eac  lea     rdx, [rbp+57h+var_A0]
0x180025eb0  lea     rcx, [rbp+57h+var_70]
0x180025eb4  call    ?begin@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::begin(void)
0x180025eb9  nop
0x180025eba  lea     rdx, [rbp+57h+var_80]
0x180025ebe  call    ?end@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEBA?AV?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@2@XZ; Collections::Enumerable<std::wstring>::end(void)
0x180025ec3  nop
0x180025ec4  mov     r14d, 1
0x180025eca  mov     rcx, [rbp+57h+var_A0]
0x180025ece  cmp     rcx, [rbp+57h+var_80]
0x180025ed2  jz      loc_180025F78
0x180025ed8  mov     rax, [rcx]
0x180025edb  mov     rax, [rax+10h]
0x180025edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ee4  mov     rbx, rax
0x180025ee7  mov     rcx, [r13+0]
0x180025eeb  mov     rax, [rcx]
0x180025eee  mov     r8, rbx
0x180025ef1  lea     rdx, [rbp+57h+arg_10]
0x180025ef5  mov     rcx, r13
0x180025ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025efd  nop
0x180025efe  mov     rdi, [rax]
0x180025f01  mov     rcx, [r12]
0x180025f05  mov     rax, [rcx+18h]
0x180025f09  mov     r8, rbx
0x180025f0c  lea     rdx, [rbp+57h+arg_8]
0x180025f10  mov     rcx, r12
0x180025f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f18  nop
0x180025f19  mov     rcx, [rax]
0x180025f1c  mov     rax, [rcx]
0x180025f1f  mov     rdx, rdi
0x180025f22  mov     rax, [rax+40h]
0x180025f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f2b  nop
0x180025f2c  mov     rcx, [rbp+57h+arg_8]
0x180025f30  test    rcx, rcx
0x180025f33  jz      short loc_180025F44
0x180025f35  mov     rax, [rcx]
0x180025f38  mov     edx, r14d
0x180025f3b  mov     rax, [rax]
0x180025f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f43  nop
0x180025f44  mov     rdx, [rbp+57h+arg_10]
0x180025f48  test    rdx, rdx
0x180025f4b  jz      short loc_180025F6A
0x180025f4d  mov     rax, [rdx+8]
0x180025f51  movsxd  rcx, dword ptr [rax+4]
0x180025f55  add     rcx, 8
0x180025f59  add     rcx, rdx
0x180025f5c  mov     rax, [rcx]
0x180025f5f  mov     edx, r14d
0x180025f62  mov     rax, [rax]
0x180025f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f6a  lea     rcx, [rbp+57h+var_A0]
0x180025f6e  call    ??E?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAAAEAV012@XZ; Collections::Private::EnumerableIterator<std::wstring>::operator++(void)
0x180025f73  jmp     loc_180025ECA
0x180025f78  mov     rbx, [rbp+57h+var_78]
0x180025f7c  test    rbx, rbx
0x180025f7f  jz      short loc_180025FB5
0x180025f81  mov     eax, esi
0x180025f83  lock xadd [rbx+8], eax
0x180025f88  add     eax, esi
0x180025f8a  jnz     short loc_180025FB5
0x180025f8c  mov     rax, [rbx]
0x180025f8f  mov     rcx, rbx
0x180025f92  mov     rax, [rax]
0x180025f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f9a  mov     eax, esi
0x180025f9c  lock xadd [rbx+0Ch], eax
0x180025fa1  add     eax, esi
0x180025fa3  jnz     short loc_180025FB5
0x180025fa5  mov     rax, [rbx]
0x180025fa8  mov     rcx, rbx
0x180025fab  mov     rax, [rax+8]
0x180025faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fb4  nop
0x180025fb5  mov     rbx, [rbp+57h+var_98]
0x180025fb9  test    rbx, rbx
0x180025fbc  jz      short loc_180025FF2
0x180025fbe  mov     eax, esi
0x180025fc0  lock xadd [rbx+8], eax
0x180025fc5  add     eax, esi
0x180025fc7  jnz     short loc_180025FF2
0x180025fc9  mov     rax, [rbx]
0x180025fcc  mov     rcx, rbx
0x180025fcf  mov     rax, [rax]
0x180025fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fd7  mov     eax, esi
0x180025fd9  lock xadd [rbx+0Ch], eax
0x180025fde  add     eax, esi
0x180025fe0  jnz     short loc_180025FF2
0x180025fe2  mov     rax, [rbx]
0x180025fe5  mov     rcx, rbx
0x180025fe8  mov     rax, [rax+8]
0x180025fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ff1  nop
0x180025ff2  mov     rbx, [rbp+57h+var_68]
0x180025ff6  test    rbx, rbx
0x180025ff9  jz      short loc_18002602E
0x180025ffb  mov     eax, esi
0x180025ffd  lock xadd [rbx+8], eax
0x180026002  add     eax, esi
0x180026004  jnz     short loc_18002602E
0x180026006  mov     rax, [rbx]
0x180026009  mov     rcx, rbx
0x18002600c  mov     rax, [rax]
0x18002600f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026014  mov     eax, esi
0x180026016  lock xadd [rbx+0Ch], eax
0x18002601b  add     eax, esi
0x18002601d  jnz     short loc_18002602E
0x18002601f  mov     rax, [rbx]
0x180026022  mov     rcx, rbx
0x180026025  mov     rax, [rax+8]
0x180026029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002602e  mov     rbx, [rsp+0C0h+arg_0]
0x180026036  add     rsp, 90h
0x18002603d  pop     r15
0x18002603f  pop     r14
0x180026041  pop     r13
0x180026043  pop     r12
0x180026045  pop     rdi
0x180026046  pop     rsi
0x180026047  pop     rbp
0x180026048  retn
```
