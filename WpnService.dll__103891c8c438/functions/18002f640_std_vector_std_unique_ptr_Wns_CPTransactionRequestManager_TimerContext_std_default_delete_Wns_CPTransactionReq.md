# std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext,std::default_delete<Wns::CPTransactionRequestManager::TimerContext>>,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext,std::default_delete<Wns::CPTransactionRequestManager::TimerContext>>>>::_Emplace_reallocate<Wns::CPTransactionRequestManager::TimerContext *>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext,std::default_delete<Wns::CPTransactionRequestManager::TimerContext>> * const,Wns::CPTransactionRequestManager::TimerContext * &&)

- ea: `0x18002f640`
- end: `0x18002f776`
- name: `??$_Emplace_reallocate@PEAVTimerContext@CPTransactionRequestManager@Wns@@@?$vector@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@1@QEAV21@$$QEAPEAVTimerContext@CPTransactionRequestManager@Wns@@@Z`
- size: `310`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800048b0`

## callees

- `0x180006160`
- `0x180007cf0`
- `0x18001664c`
- `0x180020480`
- `0x18002f640`
- `0x18002f970`
- `0x18002ff14`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f67b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002f67b`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::_Emplace_reallocate<Wns::CPTransactionRequestManager::TimerContext *>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // r8
  _QWORD *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  v23[0] = a1;
  v17 = v14;
  v23[2] = v3;
  v18 = &v14[v11];
  *v18 = v15;
  v19 = a1[1];
  v20 = *a1;
  v25 = v18 + 1;
  v24 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = v16;
  }
  std::_Uninitialized_move<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(v21, a1[1]);
    std::_Deallocate<16>((_QWORD *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = (__int64)v16;
  a1[1] = (__int64)&v16[v8];
  a1[2] = (__int64)&v16[v3];
  std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18002f640  push    rbx
0x18002f642  push    rbp
0x18002f643  push    rsi
0x18002f644  push    rdi
0x18002f645  push    r12
0x18002f647  push    r13
0x18002f649  push    r14
0x18002f64b  push    r15
0x18002f64d  sub     rsp, 58h
0x18002f651  mov     rax, [rcx+8]
0x18002f655  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18002f65f  sub     rax, [rcx]
0x18002f662  mov     r13, r8
0x18002f665  sar     rax, 3
0x18002f669  mov     rbp, rdx
0x18002f66c  mov     rbx, rcx
0x18002f66f  cmp     rax, rdi
0x18002f672  jnz     short loc_18002F682
0x18002f674  lea     rcx, aVectorTooLong; "vector too long"
0x18002f67b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002f682  lea     r14, [rax+1]
0x18002f686  mov     r15, rbp
0x18002f689  sub     r15, [rcx]
0x18002f68c  mov     rax, rdi
0x18002f68f  mov     rcx, [rcx+10h]
0x18002f693  sub     rcx, [rbx]
0x18002f696  sar     rcx, 3
0x18002f69a  mov     rdx, rcx
0x18002f69d  sar     r15, 3
0x18002f6a1  shr     rdx, 1
0x18002f6a4  sub     rax, rdx
0x18002f6a7  cmp     rcx, rax
0x18002f6aa  ja      short loc_18002F6B7
0x18002f6ac  lea     rdi, [rdx+rcx]
0x18002f6b0  cmp     rdi, r14
0x18002f6b3  cmovb   rdi, r14
0x18002f6b7  mov     rcx, rdi
0x18002f6ba  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002f6bf  mov     rcx, rax
0x18002f6c2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002f6c7  mov     rcx, [r13+0]
0x18002f6cb  mov     rsi, rax
0x18002f6ce  mov     [rsp+98h+var_78], rbx
0x18002f6d3  mov     r8, rax
0x18002f6d6  mov     [rsp+98h+var_68], rdi
0x18002f6db  lea     r15, [rax+r15*8]
0x18002f6df  mov     [r15], rcx
0x18002f6e2  lea     r12, [r15+8]
0x18002f6e6  mov     rdx, [rbx+8]
0x18002f6ea  mov     rcx, [rbx]
0x18002f6ed  mov     [rsp+98h+var_58], r12
0x18002f6f2  mov     [rsp+98h+var_60], r15
0x18002f6f7  cmp     rbp, rdx
0x18002f6fa  jz      short loc_18002F713
0x18002f6fc  mov     rdx, rbp
0x18002f6ff  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>> &)
0x18002f704  mov     rdx, [rbx+8]
0x18002f708  mov     r8, r12
0x18002f70b  mov     rcx, rbp
0x18002f70e  mov     [rsp+98h+var_60], rsi
0x18002f713  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>> &)
0x18002f718  mov     rcx, [rbx]
0x18002f71b  mov     [rsp+98h+var_70], 0
0x18002f724  test    rcx, rcx
0x18002f727  jz      short loc_18002F745
0x18002f729  mov     rdx, [rbx+8]
0x18002f72d  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>> &)
0x18002f732  mov     rdx, [rbx+10h]
0x18002f736  sub     rdx, [rbx]
0x18002f739  mov     rcx, [rbx]
0x18002f73c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002f740  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f745  mov     [rbx], rsi
0x18002f748  lea     rcx, [rsi+r14*8]
0x18002f74c  mov     [rbx+8], rcx
0x18002f750  lea     rcx, [rsi+rdi*8]
0x18002f754  mov     [rbx+10h], rcx
0x18002f758  lea     rcx, [rsp+98h+var_78]
0x18002f75d  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002f762  mov     rax, r15
0x18002f765  add     rsp, 58h
0x18002f769  pop     r15
0x18002f76b  pop     r14
0x18002f76d  pop     r13
0x18002f76f  pop     r12
0x18002f771  pop     rdi
0x18002f772  pop     rsi
0x18002f773  pop     rbp
0x18002f774  pop     rbx
0x18002f775  retn
```
