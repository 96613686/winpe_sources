# Concurrency::details::_ThenImplOptions::_CreateOptions(Concurrency::task_options const &,Concurrency::task_continuation_context const &,Concurrency::scheduler_ptr const &)

- ea: `0x18001c9bc`
- end: `0x18001cc20`
- name: `?_CreateOptions@_ThenImplOptions@details@Concurrency@@SA?AU123@AEBVtask_options@3@AEBVtask_continuation_context@3@AEBUscheduler_ptr@3@@Z`
- size: `612`
- prototype: `__int64 __fastcall(__int64, __int64, Concurrency::details::_RefCounter *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000ee28`

## callees

- `0x18000f958`
- `0x18000f9e4`
- `0x1800102c4`
- `0x18001030c`
- `0x18001c9bc`
- `0x18001cc40`
- `0x18001d7a0`
- `0x18001dd48`
- `0x18001e61c`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001cae4`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001cae4`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_ThenImplOptions::_CreateOptions(
        __int64 a1,
        __int64 a2,
        Concurrency::details::_RefCounter *a3,
        _QWORD *a4)
{
  char v7; // bl
  __int64 v8; // rsi
  Concurrency::details::_RefCounter *v9; // rcx
  _QWORD **v10; // rax
  char v11; // bl
  _QWORD *v12; // rcx
  std::_Ref_count_base *v13; // r14
  _QWORD *v14; // r12
  int v15; // r13d
  __int64 *v16; // rax
  char v17; // di
  char v18; // di
  Concurrency::details::_TaskCreationCallstack *v19; // rbx
  _QWORD *v21; // [rsp+28h] [rbp-B9h] BYREF
  std::_Ref_count_base *v22; // [rsp+30h] [rbp-B1h]
  _QWORD *v23; // [rsp+38h] [rbp-A9h]
  _QWORD *v24; // [rsp+40h] [rbp-A1h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+48h] [rbp-99h] BYREF
  int v26; // [rsp+60h] [rbp-81h]
  _QWORD v27[3]; // [rsp+68h] [rbp-79h] BYREF
  __int64 v28; // [rsp+80h] [rbp-61h] BYREF
  _BYTE v29[24]; // [rsp+88h] [rbp-59h] BYREF
  char v30; // [rsp+A0h] [rbp-41h]
  char v31[8]; // [rsp+A8h] [rbp-39h] BYREF
  char v32[24]; // [rsp+B0h] [rbp-31h] BYREF
  char v33[8]; // [rsp+C8h] [rbp-19h] BYREF
  char v34[24]; // [rsp+D0h] [rbp-11h] BYREF
  char v35[80]; // [rsp+E8h] [rbp+7h] BYREF

  v7 = 0;
  v26 = 0;
  if ( *(_BYTE *)(a2 + 88) )
  {
    v8 = *(_QWORD *)(a2 + 24);
    v9 = (Concurrency::details::_RefCounter *)v8;
    v7 = 1;
    if ( v8 )
      _InterlockedAdd((volatile signed __int32 *)(v8 + 8), 1u);
    else
      v8 = 2;
  }
  else
  {
    v8 = 0;
    v9 = a3;
  }
  if ( (v7 & 1) != 0 )
  {
    v7 &= ~1u;
    if ( v9 )
      Concurrency::details::_RefCounter::_Release(v9);
  }
  if ( *(_BYTE *)(a2 + 89) )
  {
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      &v24,
      (_QWORD *)a2);
    v25[1] = *(std::_Ref_count_base **)(a2 + 16);
    v10 = &v24;
    v11 = v7 | 2;
    v12 = v24;
  }
  else
  {
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      &v21,
      a4);
    v23 = (_QWORD *)a4[2];
    v10 = &v21;
    v11 = v7 | 4;
    v12 = v21;
  }
  v27[0] = v12;
  v13 = (std::_Ref_count_base *)v10[1];
  v27[1] = v13;
  *v10 = 0;
  v10[1] = 0;
  v14 = v10[2];
  v27[2] = v14;
  if ( (v11 & 4) != 0 )
  {
    v11 &= ~4u;
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    if ( v25[0] )
      std::_Ref_count_base::_Decref(v25[0]);
  }
  v15 = -(*(_BYTE *)(Concurrency::task_options::get_continuation_context(a2, &v24) + 8) != 0);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)&v24);
  v30 = *(_BYTE *)(a2 + 48);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)v31,
    (const struct Concurrency::details::_TaskCreationCallstack *)(a2 + 56));
  if ( v30 )
  {
    v16 = (__int64 *)Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
                       (Concurrency::details::_TaskCreationCallstack *)v33,
                       (const struct Concurrency::details::_TaskCreationCallstack *)v31);
    v17 = 8;
  }
  else
  {
    v16 = Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v24);
    v17 = 16;
  }
  v18 = v11 | v17;
  v28 = *v16;
  std::vector<void *>::vector<void *>(v29, v16 + 1);
  if ( (v18 & 0x10) != 0 )
  {
    v18 &= ~0x10u;
    std::vector<void *>::_Tidy(v25);
  }
  if ( (v18 & 8) != 0 )
    std::vector<void *>::_Tidy(v34);
  v19 = Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
          (Concurrency::details::_TaskCreationCallstack *)v35,
          (const struct Concurrency::details::_TaskCreationCallstack *)&v28);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v21,
    v27);
  v23 = v14;
  v24 = &v21;
  *(_QWORD *)a1 = v8;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 8),
    &v21);
  *(_QWORD *)(a1 + 24) = v23;
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
    (Concurrency::details::_TaskCreationCallstack *)(a1 + 32),
    v19);
  *(_DWORD *)(a1 + 64) = v15;
  *(_QWORD *)(a1 + 72) = a3;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  std::vector<void *>::_Tidy((char *)v19 + 8);
  std::vector<void *>::_Tidy(v29);
  std::vector<void *>::_Tidy(v32);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  return a1;
}

```

## disassembly

```asm
0x18001c9bc  mov     rax, rsp
0x18001c9bf  mov     [rax+20h], rbx
0x18001c9c3  mov     [rax+18h], r8
0x18001c9c7  mov     [rax+8], rcx
0x18001c9cb  push    rbp
0x18001c9cc  push    rsi
0x18001c9cd  push    rdi
0x18001c9ce  push    r12
0x18001c9d0  push    r13
0x18001c9d2  push    r14
0x18001c9d4  push    r15
0x18001c9d6  lea     rbp, [rax-5Fh]
0x18001c9da  sub     rsp, 100h
0x18001c9e1  mov     r14, r9
0x18001c9e4  mov     rdi, rdx
0x18001c9e7  mov     r15, rcx
0x18001c9ea  xor     ebx, ebx
0x18001c9ec  mov     [rsp+130h+var_D8], ebx
0x18001c9f0  lea     eax, [rbx+1]
0x18001c9f3  cmp     [rdx+58h], bl
0x18001c9f6  jz      short loc_18001CA13
0x18001c9f8  mov     rsi, [rdx+18h]
0x18001c9fc  mov     rcx, rsi
0x18001c9ff  mov     ebx, eax
0x18001ca01  test    rsi, rsi
0x18001ca04  jz      short loc_18001CA0C
0x18001ca06  lock add [rsi+8], eax
0x18001ca0a  jmp     short loc_18001CA19
0x18001ca0c  mov     esi, 2
0x18001ca11  jmp     short loc_18001CA19
0x18001ca13  xor     esi, esi
0x18001ca15  mov     rcx, [rbp+57h+arg_10]; this
0x18001ca19  test    al, bl
0x18001ca1b  jz      short loc_18001CA2B
0x18001ca1d  and     ebx, 0FFFFFFFEh
0x18001ca20  test    rcx, rcx
0x18001ca23  jz      short loc_18001CA2B
0x18001ca25  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001ca2a  nop
0x18001ca2b  cmp     byte ptr [rdi+59h], 0
0x18001ca2f  jz      short loc_18001CA56
0x18001ca31  mov     rdx, rdi
0x18001ca34  lea     rcx, [rsp+130h+var_F8]
0x18001ca39  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001ca3e  mov     rcx, [rdi+10h]
0x18001ca42  mov     [rsp+48h], rcx
0x18001ca47  lea     rax, [rsp+130h+var_F8]
0x18001ca4c  or      ebx, 2
0x18001ca4f  mov     rcx, [rsp+130h+var_F8]
0x18001ca54  jmp     short loc_18001CA79
0x18001ca56  mov     rdx, r14
0x18001ca59  lea     rcx, [rsp+130h+var_110]
0x18001ca5e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001ca63  mov     rcx, [r14+10h]
0x18001ca67  mov     [rsp+130h+var_100], rcx
0x18001ca6c  lea     rax, [rsp+130h+var_110]
0x18001ca71  or      ebx, 4
0x18001ca74  mov     rcx, [rsp+130h+var_110]
0x18001ca79  mov     [rbp+57h+var_D0], rcx
0x18001ca7d  mov     r14, [rax+8]
0x18001ca81  mov     [rbp+57h+var_C8], r14
0x18001ca85  mov     qword ptr [rax], 0
0x18001ca8c  mov     qword ptr [rax+8], 0
0x18001ca94  mov     r12, [rax+10h]
0x18001ca98  mov     [rbp+57h+var_C0], r12
0x18001ca9c  test    bl, 4
0x18001ca9f  jz      short loc_18001CAB3
0x18001caa1  and     ebx, 0FFFFFFFBh
0x18001caa4  mov     rcx, [rsp+130h+var_108]; this
0x18001caa9  test    rcx, rcx
0x18001caac  jz      short loc_18001CAB3
0x18001caae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cab3  test    bl, 2
0x18001cab6  jz      short loc_18001CACA
0x18001cab8  and     ebx, 0FFFFFFFDh
0x18001cabb  mov     rcx, [rsp+130h+var_F0]; this
0x18001cac0  test    rcx, rcx
0x18001cac3  jz      short loc_18001CACA
0x18001cac5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001caca  lea     rdx, [rsp+130h+var_F8]
0x18001cacf  mov     rcx, rdi
0x18001cad2  call    ?get_continuation_context@task_options@Concurrency@@QEBA?AVtask_continuation_context@2@XZ; Concurrency::task_options::get_continuation_context(void)
0x18001cad7  mov     cl, [rax+8]
0x18001cada  neg     cl
0x18001cadc  sbb     r13d, r13d
0x18001cadf  lea     rcx, [rsp+130h+var_F8]
0x18001cae4  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18001caea  nop
0x18001caeb  mov     al, [rdi+30h]
0x18001caee  mov     [rbp+57h+var_98], al
0x18001caf1  lea     rdx, [rdi+38h]; struct Concurrency::details::_TaskCreationCallstack *
0x18001caf5  lea     rcx, [rbp+57h+var_90]; this
0x18001caf9  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001cafe  nop
0x18001caff  cmp     [rbp+57h+var_98], 0
0x18001cb03  jz      short loc_18001CB19
0x18001cb05  lea     rdx, [rbp+57h+var_90]; struct Concurrency::details::_TaskCreationCallstack *
0x18001cb09  lea     rcx, [rbp+57h+var_70]; this
0x18001cb0d  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001cb12  mov     edi, 8
0x18001cb17  jmp     short loc_18001CB28
0x18001cb19  lea     rcx, [rsp+130h+var_F8]; this
0x18001cb1e  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18001cb23  mov     edi, 10h
0x18001cb28  mov     rdx, rax
0x18001cb2b  or      edi, ebx
0x18001cb2d  mov     rax, [rax]
0x18001cb30  mov     [rbp+57h+var_B8], rax
0x18001cb34  add     rdx, 8
0x18001cb38  lea     rcx, [rbp+57h+var_B0]
0x18001cb3c  call    ??0?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<void *>::vector<void *>(std::vector<void *> &&)
0x18001cb41  nop
0x18001cb42  test    dil, 10h
0x18001cb46  jz      short loc_18001CB55
0x18001cb48  and     edi, 0FFFFFFEFh
0x18001cb4b  lea     rcx, [rsp+130h+var_F0]
0x18001cb50  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001cb55  test    dil, 8
0x18001cb59  jz      short loc_18001CB64
0x18001cb5b  lea     rcx, [rbp+57h+var_68]
0x18001cb5f  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001cb64  lea     rdx, [rbp+57h+var_B8]; struct Concurrency::details::_TaskCreationCallstack *
0x18001cb68  lea     rcx, [rbp+57h+var_50]; this
0x18001cb6c  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001cb71  mov     rbx, rax
0x18001cb74  mov     [rbp+57h+arg_8], rax
0x18001cb78  lea     rdx, [rbp+57h+var_D0]
0x18001cb7c  lea     rcx, [rsp+130h+var_110]
0x18001cb81  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001cb86  mov     [rsp+130h+var_100], r12
0x18001cb8b  lea     rax, [rsp+130h+var_110]
0x18001cb90  mov     [rsp+130h+var_F8], rax
0x18001cb95  mov     [r15], rsi
0x18001cb98  lea     rdx, [rsp+130h+var_110]
0x18001cb9d  lea     rcx, [r15+8]
0x18001cba1  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001cba6  mov     rcx, [rsp+130h+var_100]
0x18001cbab  mov     [r15+18h], rcx
0x18001cbaf  lea     rcx, [r15+20h]; this
0x18001cbb3  mov     rdx, rbx; struct Concurrency::details::_TaskCreationCallstack *
0x18001cbb6  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18001cbbb  mov     [r15+40h], r13d
0x18001cbbf  mov     rax, [rbp+57h+arg_10]
0x18001cbc3  mov     [r15+48h], rax
0x18001cbc7  mov     rcx, [rsp+130h+var_108]; this
0x18001cbcc  test    rcx, rcx
0x18001cbcf  jz      short loc_18001CBD7
0x18001cbd1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cbd6  nop
0x18001cbd7  lea     rcx, [rbx+8]
0x18001cbdb  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001cbe0  nop
0x18001cbe1  lea     rcx, [rbp+57h+var_B0]
0x18001cbe5  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001cbea  nop
0x18001cbeb  lea     rcx, [rbp+57h+var_88]
0x18001cbef  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001cbf4  nop
0x18001cbf5  test    r14, r14
0x18001cbf8  jz      short loc_18001CC02
0x18001cbfa  mov     rcx, r14; this
0x18001cbfd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cc02  mov     rax, r15
0x18001cc05  mov     rbx, [rsp+130h+arg_18]
0x18001cc0d  add     rsp, 100h
0x18001cc14  pop     r15
0x18001cc16  pop     r14
0x18001cc18  pop     r13
0x18001cc1a  pop     r12
0x18001cc1c  pop     rdi
0x18001cc1d  pop     rsi
0x18001cc1e  pop     rbp
0x18001cc1f  retn
```
