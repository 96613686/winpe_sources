# BackgroundTaskScheduler::Scheduler::SetSchedulingModeImpl(BackgroundTaskScheduler::SchedulingMode,std::unique_lock<std::mutex> &,bool)

- ea: `0x180013140`
- end: `0x180013488`
- name: `?SetSchedulingModeImpl@Scheduler@BackgroundTaskScheduler@@IEAAXUSchedulingMode@2@AEAV?$unique_lock@Vmutex@std@@@std@@_N@Z`
- size: `840`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c2c`
- `0x180012d80`
- `0x180012ebc`
- `0x1800b3684`
- `0x1801524d4`

## callees

- `0x180004a20`
- `0x18000b920`
- `0x18000bb58`
- `0x180013140`
- `0x180013534`
- `0x180013588`
- `0x180013720`
- `0x180013758`
- `0x1800138cc`
- `0x18001391c`
- `0x180014828`
- `0x180014950`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x1800133f5`
- `msvcp_win!_Cnd_wait` at `0x1800133f5`
- `msvcp_win!_Cnd_broadcast` at `0x1800132f6`
- `msvcp_win!_Cnd_broadcast` at `0x1800132f6`
- `msvcp_win!_Thrd_id` at `0x180013273`
- `msvcp_win!_Thrd_id` at `0x180013273`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001345f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001345f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001344c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001344c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001338c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001338c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800131e9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180231f7c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800131e9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180231f7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall BackgroundTaskScheduler::Scheduler::SetSchedulingModeImpl(__int64 a1, __int64 a2, _Mtx_t *a3, char a4)
{
  __int64 v7; // rdx
  unsigned __int64 v8; // rdi
  __int64 *v9; // rsi
  unsigned __int64 v10; // r12
  int v11; // r15d
  int v12; // r14d
  unsigned __int64 i; // rbx
  unsigned __int64 v14; // r14
  __int64 v15; // rbx
  _Thrd_id_t v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  std::thread *v20; // rbx
  char *v21; // rax
  std::thread *v22; // rbx
  std::thread *v23; // rdi
  unsigned __int64 v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rax
  __int128 v29; // xmm1
  HANDLE *v30; // rbx
  HANDLE *v31; // rsi
  __int128 v32; // [rsp+40h] [rbp-30h] BYREF
  std::thread *v33; // [rsp+50h] [rbp-20h] BYREF
  char *v34; // [rsp+58h] [rbp-18h]
  char *v35; // [rsp+60h] [rbp-10h]
  __int64 v36; // [rsp+B0h] [rbp+40h]
  int v37; // [rsp+BCh] [rbp+4Ch]

  v37 = HIDWORD(a2);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(&v33);
  v36 = *(_QWORD *)(a1 + 320);
  *(_QWORD *)(a1 + 320) = v7;
  v8 = (unsigned int)v7;
  v9 = (__int64 *)(a1 + 72);
  v10 = (__int64)(*(_QWORD *)(a1 + 80) - *(_QWORD *)(a1 + 72)) >> 4;
  if ( (unsigned int)v7 < v10 )
  {
    std::vector<std::thread>::reserve(&v33, v10 - (unsigned int)v7);
    v14 = v8;
    do
    {
      v15 = 16 * v14;
      if ( *(_DWORD *)(16 * v14 + *v9 + 8) )
      {
        v16 = _Thrd_id();
        v17 = v15 + *v9;
        if ( *(_DWORD *)(v17 + 8) != v16 && a4 )
        {
          v21 = v34;
          if ( v34 == v35 )
          {
            std::vector<std::thread>::_Emplace_reallocate<std::thread>(&v33, v34, v15 + *v9);
          }
          else
          {
            v29 = *(_OWORD *)v17;
            *(_OWORD *)v17 = 0;
            *(_OWORD *)v21 = v29;
            v34 += 16;
          }
        }
        else
        {
          std::vector<std::thread>::_Emplace_one_at_back<std::thread>(a1 + 96);
        }
      }
      ++v14;
    }
    while ( v14 < v10 );
    v18 = *v9;
    v19 = (__int64)(*(_QWORD *)(a1 + 80) - *(_QWORD *)(a1 + 72)) >> 4;
    if ( v8 >= v19 )
    {
      if ( v8 > v19 )
      {
        if ( v8 <= (*(_QWORD *)(a1 + 88) - v18) >> 4 )
LABEL_49:
          *(_QWORD *)(a1 + 80) = std::_Uninitialized_value_construct_n<std::allocator<std::thread>>(*(std::thread **)(a1 + 80));
        else
          std::vector<std::thread>::_Resize_reallocate<std::_Value_init_tag>(a1 + 72, v8);
      }
    }
    else
    {
      v20 = (std::thread *)(v18 + 16 * v8);
      std::_Destroy_range<std::allocator<std::thread>>(v20);
      *(_QWORD *)(a1 + 80) = v20;
    }
  }
  else if ( (unsigned int)v7 > v10 && !*(_BYTE *)(a1 + 328) )
  {
    if ( (unsigned int)v7 <= (unsigned __int64)((__int64)(*(_QWORD *)(a1 + 88) - *(_QWORD *)(a1 + 72)) >> 4) )
      *(_QWORD *)(a1 + 80) = std::_Uninitialized_value_construct_n<std::allocator<std::thread>>(*(std::thread **)(a1 + 80));
    else
      std::vector<std::thread>::_Resize_reallocate<std::_Value_init_tag>(a1 + 72, (unsigned int)v7);
    v24 = v10;
    do
    {
      v25 = operator new(0x10u);
      if ( v25 )
      {
        *v25 = a1;
        v25[1] = v24;
      }
      v26 = _o__beginthreadex(
              0,
              0,
              std::thread::_Invoke_std::tuple__lambda_d1dcd43984ff6503e4a6a4b61a501ad9____0_,
              v25,
              0,
              (char *)&v32 + 8,
              v25);
      if ( !v26 )
        goto LABEL_48;
      v27 = *v9;
      if ( *(_DWORD *)(*v9 + 16 * v24 + 8)
        || (v28 = *((_QWORD *)&v32 + 1),
            v32 = 0,
            *(_QWORD *)(v27 + 16 * v24) = v26,
            *(_QWORD *)(v27 + 16 * v24 + 8) = v28,
            DWORD2(v32)) )
      {
        _o_terminate(2 * v24, v27, v26);
LABEL_48:
        DWORD2(v32) = 0;
        std::_Throw_Cpp_error(6);
        goto LABEL_49;
      }
      ++v24;
    }
    while ( v24 < v8 );
    while ( *(unsigned int *)(a1 + 68) < v8 )
      _Cnd_wait((_Cnd_t)(a1 + 240), *a3);
  }
  v11 = -15;
  if ( v37 )
    v12 = 0;
  else
    v12 = -15;
  if ( HIDWORD(v36) )
    v11 = 0;
  for ( i = 0; i < v8; ++i )
  {
    if ( v12 != (i < v10 ? v11 : 0) )
      SetThreadPriority(*(HANDLE *)(*v9 + 16 * i), v12);
  }
  if ( v12 > v11 )
  {
    v30 = (HANDLE *)v33;
    v31 = (HANDLE *)v34;
    while ( v30 != v31 )
    {
      SetThreadPriority(*v30, v12);
      v30 += 2;
    }
  }
  std::unique_lock<std::mutex>::unlock(a3);
  if ( v8 < v10 )
  {
    _Cnd_broadcast((_Cnd_t)(a1 + 240));
    v22 = v33;
    v23 = (std::thread *)v34;
    while ( v22 != v23 )
    {
      std::thread::join(v22);
      v22 = (std::thread *)((char *)v22 + 16);
    }
  }
  if ( v33 )
  {
    std::_Destroy_range<std::allocator<std::thread>>(v33);
    std::_Deallocate<16>(v33, (v35 - (char *)v33) & 0xFFFFFFFFFFFFFFF0uLL);
  }
}

```

## disassembly

```asm
0x180013140  mov     [rsp-38h+arg_18], rbx
0x180013145  mov     [rsp-38h+arg_10], r8
0x18001314a  mov     [rsp-38h+arg_8], rdx
0x18001314f  push    rbp
0x180013150  push    rsi
0x180013151  push    rdi
0x180013152  push    r12
0x180013154  push    r13
0x180013156  push    r14
0x180013158  push    r15
0x18001315a  mov     rbp, rsp
0x18001315d  sub     rsp, 70h
0x180013161  mov     r15b, r9b
0x180013164  mov     r14, r8
0x180013167  mov     r13, rcx
0x18001316a  lea     rcx, [rbp+var_20]; void *
0x18001316e  call    ??$?0AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(std::allocator<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>> const &)
0x180013173  nop
0x180013174  mov     rax, [r13+140h]
0x18001317b  mov     [rbp+arg_0], rax
0x18001317f  mov     [r13+140h], rdx
0x180013186  mov     edi, edx
0x180013188  lea     rsi, [r13+48h]
0x18001318c  mov     rcx, [rsi+8]; this
0x180013190  mov     r12, rcx
0x180013193  sub     r12, [rsi]
0x180013196  sar     r12, 4
0x18001319a  cmp     rdi, r12
0x18001319d  jb      loc_180013250
0x1800131a3  ja      loc_180013323
0x1800131a9  mov     r15d, 0FFFFFFF1h
0x1800131af  cmp     dword ptr [rbp+arg_8+4], 0
0x1800131b3  jz      loc_18001331B
0x1800131b9  xor     r14d, r14d
0x1800131bc  cmp     dword ptr [rbp+arg_0+4], 0
0x1800131c0  jz      short loc_1800131C5
0x1800131c2  xor     r15d, r15d
0x1800131c5  xor     ebx, ebx
0x1800131c7  test    rdi, rdi
0x1800131ca  jz      short loc_1800131F7
0x1800131cc  cmp     rbx, r12
0x1800131cf  sbb     eax, eax
0x1800131d1  and     eax, r15d
0x1800131d4  cmp     r14d, eax
0x1800131d7  jz      short loc_1800131EF
0x1800131d9  mov     rax, rbx
0x1800131dc  add     rax, rax
0x1800131df  mov     rcx, [rsi]
0x1800131e2  mov     edx, r14d; nPriority
0x1800131e5  mov     rcx, [rcx+rax*8]; hThread
0x1800131e9  call    cs:__imp_SetThreadPriority
0x1800131ef  inc     rbx
0x1800131f2  cmp     rbx, rdi
0x1800131f5  jb      short loc_1800131CC
0x1800131f7  cmp     r14d, r15d
0x1800131fa  jg      loc_18001347B
0x180013200  mov     rcx, [rbp+arg_10]
0x180013204  call    ?unlock@?$unique_lock@Vmutex@std@@@std@@QEAAXXZ; std::unique_lock<std::mutex>::unlock(void)
0x180013209  cmp     rdi, r12
0x18001320c  jb      loc_1800132EF
0x180013212  mov     rcx, [rbp+var_20]; this
0x180013216  test    rcx, rcx
0x180013219  jz      short loc_180013238
0x18001321b  mov     rdx, [rbp+var_18]
0x18001321f  call    ??$_Destroy_range@V?$allocator@Vthread@std@@@std@@@std@@YAXPEAVthread@0@QEAV10@AEAV?$allocator@Vthread@std@@@0@@Z; std::_Destroy_range<std::allocator<std::thread>>(std::thread *,std::thread * const,std::allocator<std::thread> &)
0x180013224  mov     rcx, [rbp+var_20]
0x180013228  mov     rdx, [rbp+var_10]
0x18001322c  sub     rdx, rcx
0x18001322f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180013233  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013238  mov     rbx, [rsp+70h+arg_18]
0x180013240  add     rsp, 70h
0x180013244  pop     r15
0x180013246  pop     r14
0x180013248  pop     r13
0x18001324a  pop     r12
0x18001324c  pop     rdi
0x18001324d  pop     rsi
0x18001324e  pop     rbp
0x18001324f  retn
0x180013250  mov     rdx, r12
0x180013253  sub     rdx, rdi
0x180013256  lea     rcx, [rbp+var_20]
0x18001325a  call    ?reserve@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAX_K@Z; std::vector<std::thread>::reserve(unsigned __int64)
0x18001325f  mov     r14, rdi
0x180013262  mov     rbx, r14
0x180013265  shl     rbx, 4
0x180013269  mov     rax, [rsi]
0x18001326c  cmp     dword ptr [rbx+rax+8], 0
0x180013271  jz      short loc_180013292
0x180013273  call    cs:__imp__Thrd_id
0x180013279  mov     rdx, [rsi]
0x18001327c  add     rdx, rbx
0x18001327f  cmp     [rdx+8], eax
0x180013282  jz      short loc_180013289
0x180013284  test    r15b, r15b
0x180013287  jnz     short loc_1800132D0
0x180013289  lea     rcx, [r13+60h]
0x18001328d  call    ??$_Emplace_one_at_back@Vthread@std@@@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAAEAVthread@1@$$QEAV21@@Z; std::vector<std::thread>::_Emplace_one_at_back<std::thread>(std::thread &&)
0x180013292  inc     r14
0x180013295  cmp     r14, r12
0x180013298  jb      short loc_180013262
0x18001329a  mov     r8, [rsi]
0x18001329d  mov     rcx, [rsi+8]
0x1800132a1  sub     rcx, r8
0x1800132a4  sar     rcx, 4
0x1800132a8  cmp     rdi, rcx
0x1800132ab  jnb     loc_1800133FD
0x1800132b1  mov     rbx, rdi
0x1800132b4  shl     rbx, 4
0x1800132b8  add     rbx, r8
0x1800132bb  mov     rdx, [rsi+8]
0x1800132bf  mov     rcx, rbx; this
0x1800132c2  call    ??$_Destroy_range@V?$allocator@Vthread@std@@@std@@@std@@YAXPEAVthread@0@QEAV10@AEAV?$allocator@Vthread@std@@@0@@Z; std::_Destroy_range<std::allocator<std::thread>>(std::thread *,std::thread * const,std::allocator<std::thread> &)
0x1800132c7  mov     [rsi+8], rbx
0x1800132cb  jmp     loc_1800131A9
0x1800132d0  mov     rax, [rbp+var_18]
0x1800132d4  cmp     rax, [rbp+var_10]
0x1800132d8  jnz     loc_180013423
0x1800132de  mov     r8, rdx
0x1800132e1  mov     rdx, rax
0x1800132e4  lea     rcx, [rbp+var_20]
0x1800132e8  call    ??$_Emplace_reallocate@Vthread@std@@@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAPEAVthread@1@QEAV21@$$QEAV21@@Z; std::vector<std::thread>::_Emplace_reallocate<std::thread>(std::thread * const,std::thread &&)
0x1800132ed  jmp     short loc_180013292
0x1800132ef  lea     rcx, [r13+0F0h]; _Cnd_t
0x1800132f6  call    cs:__imp__Cnd_broadcast
0x1800132fc  mov     rbx, [rbp+var_20]
0x180013300  mov     rdi, [rbp+var_18]
0x180013304  cmp     rbx, rdi
0x180013307  jz      loc_180013212
0x18001330d  mov     rcx, rbx; this
0x180013310  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180013315  add     rbx, 10h
0x180013319  jmp     short loc_180013304
0x18001331b  mov     r14d, r15d
0x18001331e  jmp     loc_1800131BC
0x180013323  cmp     byte ptr [r13+148h], 0
0x18001332b  jnz     loc_1800131A9
0x180013331  mov     rax, [rsi+10h]
0x180013335  sub     rax, [rsi]
0x180013338  sar     rax, 4
0x18001333c  mov     rdx, rdi
0x18001333f  cmp     rdi, rax
0x180013342  jbe     loc_18001343B
0x180013348  mov     rcx, rsi
0x18001334b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::thread>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180013350  mov     rbx, r12
0x180013353  mov     ecx, 10h; dwBytes
0x180013358  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001335d  test    rax, rax
0x180013360  jz      short loc_180013369
0x180013362  mov     [rax], r13
0x180013365  mov     [rax+8], rbx
0x180013369  mov     [rbp+var_40], rax
0x18001336d  lea     rcx, [rbp+var_30+8]
0x180013371  mov     [rsp+70h+var_48], rcx
0x180013376  mov     [rsp+70h+var_50], 0
0x18001337e  mov     r9, rax
0x180013381  lea     r8, std__thread___Invoke_std__tuple__lambda_d1dcd43984ff6503e4a6a4b61a501ad9____0_
0x180013388  xor     edx, edx
0x18001338a  xor     ecx, ecx
0x18001338c  call    cs:__imp__o__beginthreadex
0x180013392  mov     r8, rax
0x180013395  mov     qword ptr [rbp+var_30], rax
0x180013399  test    rax, rax
0x18001339c  jz      loc_180013453
0x1800133a2  mov     rcx, rbx
0x1800133a5  add     rcx, rcx
0x1800133a8  mov     rdx, [rsi]
0x1800133ab  cmp     dword ptr [rdx+rcx*8+8], 0
0x1800133b0  jnz     loc_18001344C
0x1800133b6  xorps   xmm0, xmm0
0x1800133b9  mov     rax, qword ptr [rbp+var_30+8]
0x1800133bd  movdqa  [rbp+var_30], xmm0
0x1800133c2  mov     [rdx+rcx*8], r8
0x1800133c6  mov     [rdx+rcx*8+8], rax
0x1800133cb  cmp     dword ptr [rbp+var_30+8], 0
0x1800133cf  jnz     short loc_18001344C
0x1800133d1  inc     rbx
0x1800133d4  cmp     rbx, rdi
0x1800133d7  jb      loc_180013353
0x1800133dd  mov     eax, [r13+44h]
0x1800133e1  nop
0x1800133e2  cmp     rax, rdi
0x1800133e5  jnb     loc_1800131A9
0x1800133eb  lea     rcx, [r13+0F0h]; _Cnd_t
0x1800133f2  mov     rdx, [r14]; _Mtx_t
0x1800133f5  call    cs:__imp__Cnd_wait
0x1800133fb  jmp     short loc_1800133DD
0x1800133fd  jbe     loc_1800131A9
0x180013403  mov     rax, [rsi+10h]
0x180013407  sub     rax, r8
0x18001340a  sar     rax, 4
0x18001340e  mov     rdx, rdi
0x180013411  cmp     rdi, rax
0x180013414  jbe     short loc_180013466
0x180013416  mov     rcx, rsi
0x180013419  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::thread>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001341e  jmp     loc_1800131A9
0x180013423  xorps   xmm0, xmm0
0x180013426  movups  xmm1, xmmword ptr [rdx]
0x180013429  movdqu  xmmword ptr [rdx], xmm0
0x18001342d  movdqu  xmmword ptr [rax], xmm1
0x180013431  add     [rbp+var_18], 10h
0x180013436  jmp     loc_180013292
0x18001343b  sub     rdx, r12
0x18001343e  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vthread@std@@@std@@@std@@YAPEAVthread@0@PEAV10@_KAEAV?$allocator@Vthread@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::thread>>(std::thread *,unsigned __int64,std::allocator<std::thread> &)
0x180013443  mov     [rsi+8], rax
0x180013447  jmp     loc_180013350
0x18001344c  call    cs:__imp__o_terminate
0x180013452  nop
0x180013453  mov     dword ptr [rbp+var_30+8], 0
0x18001345a  mov     ecx, 6
0x18001345f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180013465  nop
0x180013466  sub     rdx, rcx
0x180013469  mov     rcx, [rsi+8]; this
0x18001346d  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vthread@std@@@std@@@std@@YAPEAVthread@0@PEAV10@_KAEAV?$allocator@Vthread@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::thread>>(std::thread *,unsigned __int64,std::allocator<std::thread> &)
0x180013472  mov     [rsi+8], rax
0x180013476  jmp     loc_1800131A9
0x18001347b  mov     rbx, [rbp+var_20]
0x18001347f  mov     rsi, [rbp+var_18]
0x180013483  jmp     loc_180231F86
0x180231f76  mov     edx, r14d; nPriority
0x180231f79  mov     rcx, [rbx]; hThread
0x180231f7c  call    cs:__imp_SetThreadPriority
0x180231f82  add     rbx, 10h
0x180231f86  cmp     rbx, rsi
0x180231f89  jnz     short loc_180231F76
0x180231f8b  jmp     loc_180013200
```
