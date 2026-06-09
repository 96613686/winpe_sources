# std::priority_queue<ScheduledUmpMessage,std::deque<ScheduledUmpMessage,std::allocator<ScheduledUmpMessage>>,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>::emplace<__int64 &,std::atomic<uint> &,uint &,uchar *>(__int64 &,std::atomic<uint> &,uint &,uchar * &&)

- ea: `0x18000a518`
- end: `0x18000a6ba`
- name: `??$emplace@AEA_JAEAU?$atomic@I@std@@AEAIPEAE@?$priority_queue@UScheduledUmpMessage@@V?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@P6A_NAEAU1@0@Z@std@@QEAAXAEA_JAEAU?$atomic@I@1@AEAI$$QEAPEAE@Z`
- size: `418`
- prototype: `__int64 *__fastcall(__int64, __int64 *, int *, unsigned int *, const void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x180002050`
- `0x18000a1e4`
- `0x18000a3e0`
- `0x18000a518`
- `0x18000a83c`
- `0x18000be34`
- `0x18000cc60`

## pseudocode

```c
__int64 *__fastcall std::priority_queue<ScheduledUmpMessage,std::deque<ScheduledUmpMessage>,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>::emplace<__int64 &,std::atomic<unsigned int> &,unsigned int &,unsigned char *>(
        __int64 a1,
        __int64 *a2,
        int *a3,
        unsigned int *a4,
        const void **a5)
{
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rdi
  const void *v13; // r13
  size_t v14; // r15
  __int64 v15; // r12
  __int64 v16; // rsi
  __int64 *result; // rax
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // r11
  __int64 v21; // r10
  __int64 *v22; // r9
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rax
  _QWORD v26[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-38h] BYREF
  int v28; // [rsp+48h] [rbp-30h]
  int v29; // [rsp+4Ch] [rbp-2Ch]
  _QWORD v30[5]; // [rsp+50h] [rbp-28h] BYREF
  int v31; // [rsp+E0h] [rbp+68h]

  if ( *(_QWORD *)(a1 + 16) <= (unsigned __int64)(*(_QWORD *)(a1 + 32) + 1LL) )
    std::deque<ScheduledUmpMessage>::_Growmap();
  v9 = *(_QWORD *)(a1 + 16) - 1LL;
  *(_QWORD *)(a1 + 24) &= v9;
  v10 = *(_QWORD *)(a1 + 24) + *(_QWORD *)(a1 + 32);
  v11 = v10 & v9;
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v11) )
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v11) = operator new(0x28u);
  v12 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * (v10 & (*(_QWORD *)(a1 + 16) - 1LL)));
  v13 = *a5;
  v14 = *a4;
  v31 = *a3;
  v15 = *a2;
  *(_QWORD *)v12 = 0;
  *(_QWORD *)(v12 + 8) = 0;
  *(_QWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 24) = 0;
  *(_QWORD *)(v12 + 32) = 0;
  if ( (_DWORD)v14 )
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v12 + 16, (unsigned int)v14);
  if ( *(_QWORD *)(v12 + 24) - *(_QWORD *)(v12 + 16) == v14 )
  {
    memcpy_0(*(void **)(v12 + 16), v13, v14);
    *(_DWORD *)(v12 + 12) = v14;
    *(_QWORD *)v12 = v15;
    *(_DWORD *)(v12 + 8) = v31;
  }
  v16 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = v16 + 1;
  result = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v18 = *result;
    v19 = *result;
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  if ( v16 + 1 >= 2 )
  {
    v20 = *(_QWORD *)(a1 + 40);
    v21 = *(_QWORD *)(a1 + 24);
    v22 = *(__int64 **)(*(_QWORD *)(v18 + 8) + 8 * ((*(_QWORD *)(v18 + 16) - 1LL) & (v21 + v16)));
    v27 = *v22;
    v28 = *((_DWORD *)v22 + 2);
    v29 = *((_DWORD *)v22 + 3);
    v23 = v22[4];
    v22[4] = 0;
    v24 = v22[3];
    v22[3] = 0;
    v25 = v22[2];
    v22[2] = 0;
    v30[0] = v25;
    v30[1] = v24;
    v30[2] = v23;
    v26[0] = v19;
    v26[1] = v21;
    std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(
      (unsigned int)v26,
      v16,
      v23,
      (unsigned int)&v27,
      v20);
    return (__int64 *)std::vector<unsigned char>::~vector<unsigned char>(v30);
  }
  return result;
}

```

## disassembly

```asm
0x18000a518  push    rbp
0x18000a51a  push    rbx
0x18000a51b  push    rsi
0x18000a51c  push    rdi
0x18000a51d  push    r12
0x18000a51f  push    r13
0x18000a521  push    r14
0x18000a523  push    r15
0x18000a525  mov     rbp, rsp
0x18000a528  sub     rsp, 78h
0x18000a52c  mov     r15, r9
0x18000a52f  mov     r14, r8
0x18000a532  mov     r12, rdx
0x18000a535  mov     rbx, rcx
0x18000a538  mov     rax, [rcx+20h]
0x18000a53c  inc     rax
0x18000a53f  cmp     [rcx+10h], rax
0x18000a543  ja      short loc_18000A54A
0x18000a545  call    ?_Growmap@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@AEAAX_K@Z; std::deque<ScheduledUmpMessage>::_Growmap(unsigned __int64)
0x18000a54a  mov     rdi, [rbx+10h]
0x18000a54e  dec     rdi
0x18000a551  and     [rbx+18h], rdi
0x18000a555  mov     rsi, [rbx+20h]
0x18000a559  add     rsi, [rbx+18h]
0x18000a55d  and     rdi, rsi
0x18000a560  mov     rax, [rbx+8]
0x18000a564  xor     edx, edx
0x18000a566  cmp     [rax+rdi*8], rdx
0x18000a56a  jnz     short loc_18000A57E
0x18000a56c  lea     ecx, [rdx+28h]; Size
0x18000a56f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a574  mov     rcx, [rbx+8]
0x18000a578  mov     [rcx+rdi*8], rax
0x18000a57c  xor     edx, edx
0x18000a57e  mov     rcx, [rbx+10h]
0x18000a582  dec     rcx
0x18000a585  and     rcx, rsi
0x18000a588  mov     rax, [rbx+8]
0x18000a58c  mov     rdi, [rax+rcx*8]
0x18000a590  mov     [rbp+arg_0], rdi
0x18000a594  mov     rax, [rbp+arg_20]
0x18000a598  mov     r13, [rax]
0x18000a59b  mov     r15d, [r15]
0x18000a59e  mov     eax, [r14]
0x18000a5a1  mov     dword ptr [rbp+arg_20], eax
0x18000a5a4  nop
0x18000a5a5  mov     r12, [r12]
0x18000a5a9  mov     [rdi], rdx
0x18000a5ac  mov     qword ptr [rdi+8], 0
0x18000a5b4  lea     rsi, [rdi+10h]
0x18000a5b8  mov     [rsi], rdx
0x18000a5bb  mov     [rsi+8], rdx
0x18000a5bf  mov     [rsi+10h], rdx
0x18000a5c3  test    r15d, r15d
0x18000a5c6  jz      short loc_18000A5D3
0x18000a5c8  mov     edx, r15d
0x18000a5cb  mov     rcx, rsi
0x18000a5ce  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000a5d3  mov     rax, [rsi+8]
0x18000a5d7  sub     rax, [rsi]
0x18000a5da  cmp     rax, r15
0x18000a5dd  jnz     short loc_18000A5FA
0x18000a5df  mov     r8, r15; Size
0x18000a5e2  mov     rdx, r13; Src
0x18000a5e5  mov     rcx, [rsi]; void *
0x18000a5e8  call    memcpy_0
0x18000a5ed  mov     [rdi+0Ch], r15d
0x18000a5f1  mov     [rdi], r12
0x18000a5f4  mov     eax, dword ptr [rbp+arg_20]
0x18000a5f7  mov     [rdi+8], eax
0x18000a5fa  mov     rsi, [rbx+20h]
0x18000a5fe  lea     rcx, [rsi+1]
0x18000a602  mov     [rbx+20h], rcx
0x18000a606  mov     rax, [rbx]
0x18000a609  xor     r14d, r14d
0x18000a60c  test    rax, rax
0x18000a60f  jz      short loc_18000A619
0x18000a611  mov     rdx, [rax]
0x18000a614  mov     rdi, rdx
0x18000a617  jmp     short loc_18000A61F
0x18000a619  mov     rdx, r14
0x18000a61c  mov     rdi, r14
0x18000a61f  cmp     rcx, 2
0x18000a623  jl      loc_18000A6A9
0x18000a629  mov     r11, [rbx+28h]
0x18000a62d  mov     r10, [rbx+18h]
0x18000a631  dec     rcx
0x18000a634  add     rcx, r10
0x18000a637  mov     rax, [rdx+10h]
0x18000a63b  dec     rax
0x18000a63e  and     rcx, rax
0x18000a641  mov     rax, [rdx+8]
0x18000a645  mov     r9, [rax+rcx*8]
0x18000a649  mov     rax, [r9]
0x18000a64c  mov     [rbp+var_38], rax
0x18000a650  mov     eax, [r9+8]
0x18000a654  mov     [rbp+var_30], eax
0x18000a657  mov     eax, [r9+0Ch]
0x18000a65b  mov     [rbp+var_2C], eax
0x18000a65e  mov     r8, [r9+20h]
0x18000a662  mov     [r9+20h], r14
0x18000a666  mov     rcx, [r9+18h]
0x18000a66a  mov     [r9+18h], r14
0x18000a66e  mov     rax, [r9+10h]
0x18000a672  mov     [r9+10h], r14
0x18000a676  mov     [rbp+var_28], rax
0x18000a67a  mov     [rbp+var_20], rcx
0x18000a67e  mov     [rbp+var_18], r8
0x18000a682  mov     [rbp+var_48], rdi
0x18000a686  mov     [rbp+var_40], r10
0x18000a68a  mov     [rsp+78h+var_58], r11
0x18000a68f  lea     r9, [rbp+var_38]
0x18000a693  mov     rdx, rsi
0x18000a696  lea     rcx, [rbp+var_48]
0x18000a69a  call    ??$_Push_heap_by_index@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@std@@UScheduledUmpMessage@@P6A_NAEAU3@0@Z@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@0@_J1$$QEAUScheduledUmpMessage@@P6A_NAEAU2@3@Z@Z; std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,__int64,__int64,ScheduledUmpMessage &&,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &))
0x18000a69f  nop
0x18000a6a0  lea     rcx, [rbp+var_28]
0x18000a6a4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000a6a9  add     rsp, 78h
0x18000a6ad  pop     r15
0x18000a6af  pop     r14
0x18000a6b1  pop     r13
0x18000a6b3  pop     r12
0x18000a6b5  pop     rdi
0x18000a6b6  pop     rsi
0x18000a6b7  pop     rbx
0x18000a6b8  pop     rbp
0x18000a6b9  retn
```
