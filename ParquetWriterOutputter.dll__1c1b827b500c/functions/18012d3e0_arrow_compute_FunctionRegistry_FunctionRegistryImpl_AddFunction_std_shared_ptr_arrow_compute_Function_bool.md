# arrow::compute::FunctionRegistry::FunctionRegistryImpl::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)

- ea: `0x18012d3e0`
- end: `0x18012d690`
- name: `?AddFunction@FunctionRegistryImpl@FunctionRegistry@compute@arrow@@QEAA?AVStatus@4@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z`
- size: `688`
- prototype: `__int64 __fastcall(_Mtx_t)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18012d340`

## callees

- `0x18001e1f0`
- `0x18009a010`
- `0x1800a1ab0`
- `0x18012cd30`
- `0x18012cd90`
- `0x18012d3e0`
- `0x18012dc20`
- `0x1803065b4`
- `0x180307e68`
- `0x180307e8c`
- `0x180307f98`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x18012d46d`: `Already have a function registered with name: `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall arrow::compute::FunctionRegistry::FunctionRegistryImpl::AddFunction(
        char *a1,
        __int64 a2,
        __int64 *a3,
        char a4)
{
  int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  _BYTE *v13; // rcx
  int v14; // eax
  __int64 *v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rdi
  __int64 *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  volatile signed __int32 *v23; // rbx
  int v24; // eax
  volatile signed __int32 *v25; // rbx
  __int64 v27; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-A8h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-A0h] BYREF
  _QWORD v30[6]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE *v31; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int64 v32; // [rsp+98h] [rbp-50h]

  v30[2] = -2;
  v27 = a2;
  v30[3] = a3;
  v30[4] = a1;
  v8 = Mtx_lock((_Mtx_t)a1);
  if ( v8 )
    std::_Throw_C_error(v8);
  v9 = *a3 + 8;
  std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::find(
    a1 + 80,
    &v28,
    v9);
  if ( v28 == *((_QWORD *)a1 + 11) || a4 )
  {
    std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::find(
      a1 + 80,
      &v29,
      v9);
    v15 = (__int64 *)*((_QWORD *)a1 + 11);
    v16 = v29;
    if ( v29 == v15 )
    {
      v27 = v9;
      v17 = *v15;
      v18 = *(__int64 **)(*v15 + 8);
      v19 = std::_List_buy<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>::_Buynode<std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(
              (int)a1 + 88,
              *v15,
              (_DWORD)v18,
              (unsigned int)word_180391EBA,
              (__int64)&v27);
      v20 = *((_QWORD *)a1 + 12);
      if ( v20 == 0x3FFFFFFFFFFFFFELL )
        std::_Xlength_error("list<T> too long");
      *((_QWORD *)a1 + 12) = v20 + 1;
      *(_QWORD *)(v17 + 8) = v19;
      *v18 = v19;
      std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::_Insert<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>>>>(
        a1 + 80,
        v30,
        **((_QWORD **)a1 + 11) + 16LL);
      v16 = (__int64 *)v30[0];
    }
    else
    {
      v30[0] = v29;
    }
    v21 = *a3;
    v22 = a3[1];
    *a3 = 0;
    a3[1] = 0;
    v16[6] = v21;
    v30[5] = v22;
    v23 = (volatile signed __int32 *)v16[7];
    v16[7] = v22;
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    *(_QWORD *)(a2 + 8) = 0;
    v24 = Mtx_unlock((_Mtx_t)a1);
    if ( v24 )
      std::_Throw_C_error(v24);
    v25 = (volatile signed __int32 *)a3[1];
    if ( v25 )
    {
      if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
  }
  else
  {
    v10 = arrow::util::StringBuilder<char const (&)[35],std::string const &>(
            &v31,
            "Already have a function registered with name: ",
            v9);
    LOBYTE(v11) = 2;
    arrow::Status::Status(a2, v11, v10);
    if ( v32 >= 0x10 )
    {
      v12 = v32 + 1;
      v13 = v31;
      if ( v32 + 1 >= 0x1000 )
      {
        v12 = v32 + 40;
        v13 = (_BYTE *)*((_QWORD *)v31 - 1);
        if ( (unsigned __int64)(v31 - v13 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13, v12);
    }
    v14 = Mtx_unlock((_Mtx_t)a1);
    if ( v14 )
      std::_Throw_C_error(v14);
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(a3);
  }
  return a2;
}

```

## disassembly

```asm
0x18012d3e0  push    rbx
0x18012d3e2  push    rbp
0x18012d3e3  push    rsi
0x18012d3e4  push    rdi
0x18012d3e5  push    r12
0x18012d3e7  push    r14
0x18012d3e9  push    r15
0x18012d3eb  sub     rsp, 0B0h
0x18012d3f2  mov     [rsp+0E8h+var_88], 0FFFFFFFFFFFFFFFEh
0x18012d3fb  mov     rax, cs:__security_cookie
0x18012d402  xor     rax, rsp
0x18012d405  mov     [rsp+0E8h+var_48], rax
0x18012d40d  movzx   r15d, r9b
0x18012d411  mov     rsi, r8
0x18012d414  mov     rbp, rdx
0x18012d417  mov     r14, rcx
0x18012d41a  mov     [rsp+0E8h+var_B0], rdx
0x18012d41f  mov     [rsp+0E8h+var_80], r8
0x18012d424  mov     [rsp+0E8h+var_78], rcx
0x18012d429  call    _Mtx_lock
0x18012d42e  test    eax, eax
0x18012d430  jz      short loc_18012D43A
0x18012d432  mov     ecx, eax; int
0x18012d434  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x18012d439  nop
0x18012d43a  mov     rdi, [rsi]
0x18012d43d  add     rdi, 8
0x18012d441  mov     r8, rdi
0x18012d444  lea     rdx, [rsp+0E8h+var_A8]
0x18012d449  lea     rcx, [r14+50h]
0x18012d44d  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::find(std::string const &)
0x18012d452  mov     rax, [r14+58h]
0x18012d456  cmp     [rsp+0E8h+var_A8], rax
0x18012d45b  jz      loc_18012D4F5
0x18012d461  test    r15b, r15b
0x18012d464  jnz     loc_18012D4F5
0x18012d46a  mov     r8, rdi
0x18012d46d  lea     rdx, aAlreadyHaveAFu; "Already have a function registered with"...
0x18012d474  lea     rcx, [rsp+0E8h+var_68]
0x18012d47c  call    ??$StringBuilder@AEAY0CD@$$CBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0CD@$$CBDAEBV23@@Z; arrow::util::StringBuilder<char const (&)[35],std::string const &>(char const (&)[35],std::string const &)
0x18012d481  nop
0x18012d482  mov     r8, rax
0x18012d485  mov     dl, 2
0x18012d487  mov     rcx, rbp
0x18012d48a  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18012d48f  nop
0x18012d490  mov     rdx, [rsp+0E8h+var_50]
0x18012d498  cmp     rdx, 10h
0x18012d49c  jb      short loc_18012D4D4
0x18012d49e  inc     rdx
0x18012d4a1  mov     rcx, [rsp+0E8h+var_68]
0x18012d4a9  mov     rax, rcx
0x18012d4ac  cmp     rdx, 1000h
0x18012d4b3  jb      short loc_18012D4CE
0x18012d4b5  add     rdx, 27h ; '''; unsigned __int64
0x18012d4b9  mov     rcx, [rcx-8]; void *
0x18012d4bd  sub     rax, rcx
0x18012d4c0  add     rax, 0FFFFFFFFFFFFFFF8h
0x18012d4c4  cmp     rax, 1Fh
0x18012d4c8  ja      loc_18012D68A
0x18012d4ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18012d4d3  nop
0x18012d4d4  mov     rcx, r14; _Mtx_t
0x18012d4d7  call    _Mtx_unlock
0x18012d4dc  test    eax, eax
0x18012d4de  jz      short loc_18012D4E8
0x18012d4e0  mov     ecx, eax; int
0x18012d4e2  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x18012d4e7  nop
0x18012d4e8  mov     rcx, rsi; void *
0x18012d4eb  call    ??1?$TypedBufferBuilder@_JX@arrow@@QEAA@XZ; arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(void)
0x18012d4f0  jmp     loc_18012D658
0x18012d4f5  mov     r8, rdi
0x18012d4f8  lea     rdx, [rsp+0E8h+var_A0]
0x18012d4fd  lea     rcx, [r14+50h]
0x18012d501  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::find(std::string const &)
0x18012d506  mov     rcx, [r14+58h]
0x18012d50a  mov     rax, [rsp+0E8h+var_A0]
0x18012d50f  cmp     rax, rcx
0x18012d512  jnz     loc_18012D59B
0x18012d518  mov     [rsp+0E8h+var_B0], rdi
0x18012d51d  mov     rdi, [rcx]
0x18012d520  mov     r12, [rdi+8]
0x18012d524  lea     rax, [rsp+0E8h+var_B8]
0x18012d529  mov     [rsp+0E8h+var_C0], rax
0x18012d52e  lea     rax, [rsp+0E8h+var_B0]
0x18012d533  mov     [rsp+0E8h+var_C8], rax
0x18012d538  lea     r9, word_180391EBA
0x18012d53f  mov     r8, r12
0x18012d542  mov     rdx, rdi
0x18012d545  lea     rcx, [r14+58h]
0x18012d549  call    ??$_Buynode@AEBUpiecewise_construct_t@std@@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$tuple@$$V@2@@?$_List_buy@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@2@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@PEAX@1@PEAU21@0AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_List_buy<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>::_Buynode<std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(std::_List_node<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>,void *> *,std::_List_node<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>,void *> *,std::piecewise_construct_t const &,std::tuple<std::string const &> &&,std::tuple<> &&)
0x18012d54e  mov     rdx, rax
0x18012d551  mov     rax, [r14+60h]
0x18012d555  mov     rcx, 3FFFFFFFFFFFFFEh
0x18012d55f  sub     rcx, rax
0x18012d562  cmp     rcx, 1
0x18012d566  jb      loc_18012D67D
0x18012d56c  inc     rax
0x18012d56f  mov     [r14+60h], rax
0x18012d573  mov     [rdi+8], rdx
0x18012d577  mov     [r12], rdx
0x18012d57b  mov     r9, [r14+58h]
0x18012d57f  mov     r9, [r9]
0x18012d582  lea     r8, [r9+10h]
0x18012d586  lea     rdx, [rsp+0E8h+var_98]
0x18012d58b  lea     rcx, [r14+50h]
0x18012d58f  call    ??$_Insert@AEAU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@std@@@std@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@1@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VFunction@compute@arrow@@@2@@std@@@std@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<std::string,std::shared_ptr<arrow::compute::Function>,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>,0>>::_Insert<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>>>>(std::pair<std::string const,std::shared_ptr<arrow::compute::Function>> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,std::shared_ptr<arrow::compute::Function>>>>>)
0x18012d594  mov     rax, [rsp+0E8h+var_98]
0x18012d599  jmp     short loc_18012D5A0
0x18012d59b  mov     [rsp+0E8h+var_98], rax
0x18012d5a0  mov     rcx, [rsi]
0x18012d5a3  mov     rdx, [rsi+8]
0x18012d5a7  xor     r15d, r15d
0x18012d5aa  mov     [rsi], r15
0x18012d5ad  mov     [rsi+8], r15
0x18012d5b1  mov     [rax+30h], rcx
0x18012d5b5  mov     [rsp+0E8h+var_70], rdx
0x18012d5ba  mov     rbx, [rax+38h]
0x18012d5be  mov     [rax+38h], rdx
0x18012d5c2  lea     edi, [r15-1]
0x18012d5c6  test    rbx, rbx
0x18012d5c9  jz      short loc_18012D602
0x18012d5cb  mov     eax, edi
0x18012d5cd  lock xadd [rbx+8], eax
0x18012d5d2  cmp     eax, 1
0x18012d5d5  jnz     short loc_18012D602
0x18012d5d7  mov     rax, [rbx]
0x18012d5da  mov     rcx, rbx
0x18012d5dd  mov     rax, [rax]
0x18012d5e0  call    cs:__guard_dispatch_icall_fptr
0x18012d5e6  mov     eax, edi
0x18012d5e8  lock xadd [rbx+0Ch], eax
0x18012d5ed  cmp     eax, 1
0x18012d5f0  jnz     short loc_18012D602
0x18012d5f2  mov     rax, [rbx]
0x18012d5f5  mov     rcx, rbx
0x18012d5f8  mov     rax, [rax+8]
0x18012d5fc  call    cs:__guard_dispatch_icall_fptr
0x18012d602  mov     [rbp+8], r15
0x18012d606  mov     rcx, r14; _Mtx_t
0x18012d609  call    _Mtx_unlock
0x18012d60e  test    eax, eax
0x18012d610  jz      short loc_18012D61A
0x18012d612  mov     ecx, eax; int
0x18012d614  call    ?_Throw_C_error@std@@YAXH@Z; std::_Throw_C_error(int)
0x18012d619  nop
0x18012d61a  mov     rbx, [rsi+8]
0x18012d61e  test    rbx, rbx
0x18012d621  jz      short loc_18012D658
0x18012d623  mov     eax, edi
0x18012d625  lock xadd [rbx+8], eax
0x18012d62a  cmp     eax, 1
0x18012d62d  jnz     short loc_18012D658
0x18012d62f  mov     rax, [rbx]
0x18012d632  mov     rcx, rbx
0x18012d635  mov     rax, [rax]
0x18012d638  call    cs:__guard_dispatch_icall_fptr
0x18012d63e  lock xadd [rbx+0Ch], edi
0x18012d643  cmp     edi, 1
0x18012d646  jnz     short loc_18012D658
0x18012d648  mov     rax, [rbx]
0x18012d64b  mov     rcx, rbx
0x18012d64e  mov     rax, [rax+8]
0x18012d652  call    cs:__guard_dispatch_icall_fptr
0x18012d658  mov     rax, rbp
0x18012d65b  mov     rcx, [rsp+0E8h+var_48]
0x18012d663  xor     rcx, rsp; StackCookie
0x18012d666  call    __security_check_cookie
0x18012d66b  add     rsp, 0B0h
0x18012d672  pop     r15
0x18012d674  pop     r14
0x18012d676  pop     r12
0x18012d678  pop     rdi
0x18012d679  pop     rsi
0x18012d67a  pop     rbp
0x18012d67b  pop     rbx
0x18012d67c  retn
0x18012d67d  lea     rcx, aListTTooLong; "list<T> too long"
0x18012d684  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18012d68a  call    _invalid_parameter_noinfo_noreturn
```
