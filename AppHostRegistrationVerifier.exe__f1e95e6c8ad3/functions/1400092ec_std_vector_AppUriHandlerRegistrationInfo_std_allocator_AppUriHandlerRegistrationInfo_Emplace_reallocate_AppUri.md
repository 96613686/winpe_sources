# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::_Emplace_reallocate<AppUriHandlerRegistrationInfo>(AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo &&)

- ea: `0x1400092ec`
- end: `0x140009459`
- name: `??$_Emplace_reallocate@UAppUriHandlerRegistrationInfo@@@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@AEAAPEAUAppUriHandlerRegistrationInfo@@QEAU2@$$QEAU2@@Z`
- size: `365`
- prototype: `_QWORD *__fastcall(AppUriHandlerRegistrationInfo **, AppUriHandlerRegistrationInfo *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009794`

## callees

- `0x140003ad4`
- `0x140003cd8`
- `0x1400076e8`
- `0x140009294`
- `0x1400092ec`
- `0x14000964c`
- `0x14000a474`
- `0x14000fd44`

## pseudocode

```c
_QWORD *__fastcall std::vector<AppUriHandlerRegistrationInfo>::_Emplace_reallocate<AppUriHandlerRegistrationInfo>(
        AppUriHandlerRegistrationInfo **a1,
        AppUriHandlerRegistrationInfo *a2,
        __int64 *a3)
{
  AppUriHandlerRegistrationInfo *v3; // r14
  __int64 v4; // rbp
  __int64 v7; // rdi
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rsi
  __int64 v13; // rcx
  _QWORD *v14; // r12
  _QWORD *v15; // r14
  __int64 v16; // rax
  AppUriHandlerRegistrationInfo *v17; // rdx
  AppUriHandlerRegistrationInfo *v18; // rcx
  AppUriHandlerRegistrationInfo *v19; // rcx
  _QWORD v21[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v22; // [rsp+38h] [rbp-60h]
  _QWORD *v23; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v4 = 0xFFFFFFFFFFFFFFFLL;
  v7 = (a1[1] - *a1) >> 4;
  if ( v7 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<AppUriHandlerRegistrationInfo>::_Xlength();
  v8 = v7 + 1;
  v9 = (a1[2] - v3) >> 4;
  if ( v9 <= 0xFFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v10 = (v9 >> 1) + v9;
    v11 = v8;
    if ( v10 >= v8 )
      v11 = v10;
    if ( v11 > 0xFFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v4 = v11;
  }
  v21[2] = v4;
  v21[0] = a1;
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(16 * v4);
  v13 = *a3;
  v14 = (_QWORD *)((char *)v12 + ((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL));
  v22 = v14;
  *v14 = v13;
  v15 = v14 + 2;
  v16 = a3[1];
  *a3 = 0;
  v14[1] = v16;
  a3[1] = 0;
  v17 = a1[1];
  v18 = *a1;
  v23 = v14 + 2;
  if ( a2 == v17 )
  {
    v15 = v12;
  }
  else
  {
    std::_Uninitialized_move<AppUriHandlerRegistrationInfo *>(v18, a2, v12, a1, v21[0]);
    v17 = a1[1];
    v18 = a2;
    v22 = v12;
  }
  std::_Uninitialized_move<AppUriHandlerRegistrationInfo *>(v18, v17, v15, a1, v21[0]);
  v19 = *a1;
  v21[1] = 0;
  if ( v19 )
  {
    std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(v19, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  *a1 = (AppUriHandlerRegistrationInfo *)v12;
  a1[1] = (AppUriHandlerRegistrationInfo *)&v12[2 * v8];
  a1[2] = (AppUriHandlerRegistrationInfo *)&v12[2 * v4];
  std::vector<AppUriHandlerRegistrationInfo>::_Reallocation_guard::~_Reallocation_guard(v21);
  return v14;
}

```

## disassembly

```asm
0x1400092ec  mov     [rsp+arg_10], r8
0x1400092f1  push    rbx
0x1400092f2  push    rbp
0x1400092f3  push    rsi
0x1400092f4  push    rdi
0x1400092f5  push    r12
0x1400092f7  push    r13
0x1400092f9  push    r14
0x1400092fb  push    r15
0x1400092fd  sub     rsp, 58h
0x140009301  mov     r14, [rcx]
0x140009304  mov     rbp, 0FFFFFFFFFFFFFFFh
0x14000930e  mov     rdi, [rcx+8]
0x140009312  mov     r15, rdx
0x140009315  sub     rdi, r14
0x140009318  mov     rbx, rcx
0x14000931b  sar     rdi, 4
0x14000931f  cmp     rdi, rbp
0x140009322  jz      loc_140009453
0x140009328  mov     rcx, [rcx+10h]
0x14000932c  mov     rax, rbp
0x14000932f  sub     rcx, r14
0x140009332  inc     rdi
0x140009335  sar     rcx, 4
0x140009339  mov     rdx, rcx
0x14000933c  shr     rdx, 1
0x14000933f  sub     rax, rdx
0x140009342  cmp     rcx, rax
0x140009345  ja      short loc_140009361
0x140009347  lea     rax, [rdx+rcx]
0x14000934b  mov     rcx, rdi
0x14000934e  cmp     rax, rdi
0x140009351  cmovnb  rcx, rax
0x140009355  cmp     rcx, rbp
0x140009358  ja      loc_14000944D
0x14000935e  mov     rbp, rcx
0x140009361  mov     r13, rbp
0x140009364  shl     r13, 4
0x140009368  mov     rcx, r13
0x14000936b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140009370  mov     rdx, [rsp+98h+arg_10]
0x140009378  mov     r12, r15
0x14000937b  sub     r12, r14
0x14000937e  mov     [rsp+98h+var_68], rbp
0x140009383  xor     ebp, ebp
0x140009385  mov     [rsp+98h+var_78], rbx
0x14000938a  and     r12, 0FFFFFFFFFFFFFFF0h
0x14000938e  mov     rsi, rax
0x140009391  mov     rcx, [rdx]
0x140009394  add     r12, rax
0x140009397  mov     [rsp+98h+var_60], r12
0x14000939c  mov     [r12], rcx
0x1400093a0  lea     r14, [r12+10h]
0x1400093a5  mov     rax, [rdx+8]
0x1400093a9  mov     [rdx], rbp
0x1400093ac  mov     [r12+8], rax
0x1400093b1  mov     [rdx+8], rbp
0x1400093b5  mov     rdx, [rbx+8]
0x1400093b9  mov     rcx, [rbx]
0x1400093bc  mov     [rsp+98h+var_58], r14
0x1400093c1  cmp     r15, rdx
0x1400093c4  jnz     short loc_1400093CB
0x1400093c6  mov     r14, rsi
0x1400093c9  jmp     short loc_1400093E5
0x1400093cb  mov     r9, rbx
0x1400093ce  mov     r8, rsi
0x1400093d1  mov     rdx, r15
0x1400093d4  call    ??$_Uninitialized_move@PEAUAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAPEAUAppUriHandlerRegistrationInfo@@QEAU1@0PEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Uninitialized_move<AppUriHandlerRegistrationInfo *>(AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo *,std::allocator<AppUriHandlerRegistrationInfo> &)
0x1400093d9  mov     rdx, [rbx+8]
0x1400093dd  mov     rcx, r15
0x1400093e0  mov     [rsp+98h+var_60], rsi
0x1400093e5  mov     r9, rbx
0x1400093e8  mov     r8, r14
0x1400093eb  call    ??$_Uninitialized_move@PEAUAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAPEAUAppUriHandlerRegistrationInfo@@QEAU1@0PEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Uninitialized_move<AppUriHandlerRegistrationInfo *>(AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo *,std::allocator<AppUriHandlerRegistrationInfo> &)
0x1400093f0  mov     rcx, [rbx]; this
0x1400093f3  mov     [rsp+98h+var_70], rbp
0x1400093f8  test    rcx, rcx
0x1400093fb  jz      short loc_140009419
0x1400093fd  mov     rdx, [rbx+8]
0x140009401  call    ??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)
0x140009406  mov     rdx, [rbx+10h]
0x14000940a  sub     rdx, [rbx]
0x14000940d  mov     rcx, [rbx]
0x140009410  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140009414  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140009419  mov     [rbx], rsi
0x14000941c  lea     rcx, [rsi+r13]
0x140009420  shl     rdi, 4
0x140009424  add     rdi, rsi
0x140009427  mov     [rbx+8], rdi
0x14000942b  mov     [rbx+10h], rcx
0x14000942f  lea     rcx, [rsp+98h+var_78]
0x140009434  call    ??1_Reallocation_guard@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ; std::vector<AppUriHandlerRegistrationInfo>::_Reallocation_guard::~_Reallocation_guard(void)
0x140009439  mov     rax, r12
0x14000943c  add     rsp, 58h
0x140009440  pop     r15
0x140009442  pop     r14
0x140009444  pop     r13
0x140009446  pop     r12
0x140009448  pop     rdi
0x140009449  pop     rsi
0x14000944a  pop     rbp
0x14000944b  pop     rbx
0x14000944c  retn
0x14000944d  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140009453  call    ?_Xlength@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@CAXXZ; std::vector<AppUriHandlerRegistrationInfo>::_Xlength(void)
```
