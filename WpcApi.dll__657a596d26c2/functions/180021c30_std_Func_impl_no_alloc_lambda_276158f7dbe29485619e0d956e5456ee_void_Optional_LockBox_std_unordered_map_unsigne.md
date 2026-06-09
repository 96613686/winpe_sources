# std::_Func_impl_no_alloc<_lambda_276158f7dbe29485619e0d956e5456ee_,void,Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>> &>::_Do_call(Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>> &)

- ea: `0x180021c30`
- end: `0x180021d77`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_276158f7dbe29485619e0d956e5456ee_@@XAEAV?$Optional@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@@std@@EEAAXAEAV?$Optional@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@@Z`
- size: `327`
- prototype: `void __fastcall(__int64, RTL_SRWLOCK *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800032c4`
- `0x1800036e4`
- `0x180020f84`
- `0x1800211b0`
- `0x1800215b0`
- `0x180021a80`
- `0x180021c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180021ce0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180021ce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Func_impl_no_alloc<_lambda_276158f7dbe29485619e0d956e5456ee_,void,Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>> &>::_Do_call(
        __int64 a1,
        RTL_SRWLOCK *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rdi
  _QWORD **v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx
  _QWORD **v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  int v11; // [rsp+20h] [rbp-59h] BYREF
  void *Block; // [rsp+28h] [rbp-51h]
  __int64 v13; // [rsp+30h] [rbp-49h]
  __int128 v14; // [rsp+38h] [rbp-41h] BYREF
  __int64 v15; // [rsp+48h] [rbp-31h]
  __int64 v16; // [rsp+50h] [rbp-29h]
  __int64 v17; // [rsp+58h] [rbp-21h]
  _BYTE v18[112]; // [rsp+60h] [rbp-19h] BYREF

  v13 = 0;
  v3 = operator new(0x20u);
  *v3 = v3;
  v3[1] = v3;
  Block = v3;
  v14 = 0;
  v15 = 0;
  v16 = 7;
  v17 = 8;
  v11 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::_Assign_grow(
    (__int64)&v14,
    0x10u,
    (unsigned __int64)v3);
  Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::Reset(a2);
  v4 = std::unordered_map<unsigned __int64,Private::ThreadInfo *>::unordered_map<unsigned __int64,Private::ThreadInfo *>(
         (__int64)v18,
         (__int64)&v11);
  a2[1].Ptr = &LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>::`vftable';
  std::unordered_map<unsigned __int64,Private::ThreadInfo *>::unordered_map<unsigned __int64,Private::ThreadInfo *>(
    (__int64)&a2[3],
    v4);
  InitializeSRWLock(a2 + 2);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>((char **)(v4 + 24));
  v5 = *(_QWORD ***)(v4 + 8);
  *v5[1] = 0;
  v6 = *v5;
  if ( v6 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      operator delete(v6);
      v6 = v7;
    }
    while ( v7 );
  }
  operator delete(*(void **)(v4 + 8));
  a2[11].Ptr = &a2[1];
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>((char **)&v14);
  v8 = (_QWORD **)Block;
  **((_QWORD **)Block + 1) = 0;
  v9 = *v8;
  if ( *v8 )
  {
    do
    {
      v10 = (_QWORD *)*v9;
      operator delete(v9);
      v9 = v10;
    }
    while ( v10 );
  }
  operator delete(v8);
}

```

## disassembly

```asm
0x180021c30  mov     [rsp-8+arg_0], rcx
0x180021c35  push    rbp
0x180021c36  push    rbx
0x180021c37  push    rsi
0x180021c38  push    rdi
0x180021c39  push    r12
0x180021c3b  push    r14
0x180021c3d  lea     rbp, [rsp-2Fh]
0x180021c42  sub     rsp, 0A8h
0x180021c49  mov     r14, rdx
0x180021c4c  mov     [rbp+57h+var_A0], 0
0x180021c54  mov     r12d, 20h ; ' '
0x180021c5a  mov     ecx, r12d; Size
0x180021c5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c62  mov     [rax], rax
0x180021c65  mov     [rax+8], rax
0x180021c69  mov     [rbp+57h+Block], rax
0x180021c6d  xorps   xmm0, xmm0
0x180021c70  movdqu  [rbp+57h+var_98], xmm0
0x180021c75  mov     [rbp+57h+var_88], 0
0x180021c7d  mov     [rbp+57h+var_80], 7
0x180021c85  mov     [rbp+57h+var_78], 8
0x180021c8d  mov     [rbp+57h+var_B0], 3F800000h
0x180021c94  mov     r8, rax
0x180021c97  lea     edx, [r12-10h]
0x180021c9c  lea     rcx, [rbp+57h+var_98]
0x180021ca0  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>)
0x180021ca5  nop
0x180021ca6  mov     rcx, r14
0x180021ca9  call    ?Reset@?$Optional@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAXXZ; Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::Reset(void)
0x180021cae  lea     rsi, [r14+8]
0x180021cb2  lea     rdx, [rbp+57h+var_B0]
0x180021cb6  lea     rcx, [rbp+57h+var_70]
0x180021cba  call    ??0?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@QEAA@$$QEAV01@@Z; std::unordered_map<unsigned __int64,Private::ThreadInfo *>::unordered_map<unsigned __int64,Private::ThreadInfo *>(std::unordered_map<unsigned __int64,Private::ThreadInfo *> &&)
0x180021cbf  mov     rdi, rax
0x180021cc2  mov     [rbp+57h+arg_0], rax
0x180021cc6  lea     rax, ??_7?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@6B@; const LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>::`vftable'
0x180021ccd  mov     [rsi], rax
0x180021cd0  lea     rcx, [rsi+10h]
0x180021cd4  mov     rdx, rdi
0x180021cd7  call    ??0?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@QEAA@$$QEAV01@@Z; std::unordered_map<unsigned __int64,Private::ThreadInfo *>::unordered_map<unsigned __int64,Private::ThreadInfo *>(std::unordered_map<unsigned __int64,Private::ThreadInfo *> &&)
0x180021cdc  lea     rcx, [rsi+8]; SRWLock
0x180021ce0  call    cs:__imp_InitializeSRWLock
0x180021ce6  nop
0x180021ce7  lea     rcx, [rdi+18h]
0x180021ceb  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(void)
0x180021cf0  mov     rcx, [rdi+8]
0x180021cf4  mov     rax, [rcx+8]
0x180021cf8  mov     qword ptr [rax], 0
0x180021cff  mov     rcx, [rcx]; Block
0x180021d02  test    rcx, rcx
0x180021d05  jz      short loc_180021D1A
0x180021d07  mov     rbx, [rcx]
0x180021d0a  mov     rdx, r12
0x180021d0d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021d12  mov     rcx, rbx
0x180021d15  test    rbx, rbx
0x180021d18  jnz     short loc_180021D07
0x180021d1a  mov     rdx, r12
0x180021d1d  mov     rcx, [rdi+8]; Block
0x180021d21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021d26  mov     [r14+58h], rsi
0x180021d2a  lea     rcx, [rbp+57h+var_98]
0x180021d2e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(void)
0x180021d33  mov     rdi, [rbp+57h+Block]
0x180021d37  mov     rax, [rdi+8]
0x180021d3b  mov     qword ptr [rax], 0
0x180021d42  mov     rcx, [rdi]; Block
0x180021d45  test    rcx, rcx
0x180021d48  jz      short loc_180021D5D
0x180021d4a  mov     rbx, [rcx]
0x180021d4d  mov     rdx, r12
0x180021d50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021d55  mov     rcx, rbx
0x180021d58  test    rbx, rbx
0x180021d5b  jnz     short loc_180021D4A
0x180021d5d  mov     rdx, r12
0x180021d60  mov     rcx, rdi; Block
0x180021d63  add     rsp, 0A8h
0x180021d6a  pop     r14
0x180021d6c  pop     r12
0x180021d6e  pop     rdi
0x180021d6f  pop     rsi
0x180021d70  pop     rbx
0x180021d71  pop     rbp
0x180021d72  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
