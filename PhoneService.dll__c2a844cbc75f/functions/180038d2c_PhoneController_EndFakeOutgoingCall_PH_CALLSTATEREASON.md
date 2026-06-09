# PhoneController::_EndFakeOutgoingCall(PH_CALLSTATEREASON)

- ea: `0x180038d2c`
- end: `0x180038fff`
- name: `?_EndFakeOutgoingCall@PhoneController@@IEAAJW4PH_CALLSTATEREASON@@@Z`
- size: `723`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800243e0`
- `0x18003d070`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180038d2c`
- `0x180041858`
- `0x18004b778`
- `0x18004ef10`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038d7e`

## string_xrefs

- `0x180038d72`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038e49`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038ecc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038f4b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_EndFakeOutgoingCall(__int64 a1, int a2)
{
  __int64 v4; // rcx
  _DWORD *v5; // rsi
  _WORD *v6; // rcx
  __int64 v7; // r9
  BackTraceCollection *v8; // r10
  __int64 v9; // rax
  BackTraceCollection *v10; // rcx
  unsigned int v11; // ebx
  BackTraceCollection *v13; // rcx
  __int64 v14; // rbx
  int v15; // eax
  BackTraceCollection *v16; // rcx
  unsigned int v17; // esi
  __int64 v18; // rcx
  struct _GUID v19; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  char v24; // [rsp+118h] [rbp+18h] BYREF
  int v25; // [rsp+358h] [rbp+258h]
  int v26; // [rsp+35Ch] [rbp+25Ch]
  int v27; // [rsp+360h] [rbp+260h]

  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3011);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *(_DWORD **)(a1 + 176);
  if ( !v5 )
    return 0;
  memset_0(&v22, 0, 0xF40u);
  v6 = v5 + 46;
  *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v21 = -1;
  v7 = 64;
  v8 = (BackTraceCollection *)&v24;
  v22 = v5[767];
  v9 = 2147483646;
  *(_QWORD *)&v19.Data1 = 0;
  v23 = 232;
  do
  {
    if ( !v9 )
      break;
    if ( !*v6 )
      break;
    *(_WORD *)v8 = *v6++;
    v8 = (BackTraceCollection *)((char *)v8 + 2);
    --v9;
    --v7;
  }
  while ( v7 );
  v10 = (BackTraceCollection *)((char *)v8 - 2);
  v11 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v10 = v8;
  *(_WORD *)v10 = 0;
  if ( !v7 )
  {
    BackTraceCollection::Capture(v10, v11);
    Log_HREvent_7(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3027);
    if ( Block[0] != (void *)-1LL )
    {
      Block[1] = Block[0];
      operator delete(Block[0]);
    }
    return v11;
  }
  v27 = 2;
  v25 = 5;
  v26 = a2;
  CallInfo::GetPhoneLine((CallInfo *)v5, (struct PhoneLine **)&v19);
  if ( !(unsigned __int8)utl::vector<CallUpdate,utl::allocator<CallUpdate>>::push_back(Block, &v22) )
  {
    v11 = -2147024882;
    BackTraceCollection::Capture(v13, -2147024882);
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3034);
    if ( Block[0] != (void *)-1LL )
    {
      Block[1] = Block[0];
      operator delete(Block[0]);
    }
    if ( *(_QWORD *)&v19.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v19.Data1 + 16LL))(*(_QWORD *)&v19.Data1);
    return v11;
  }
  v14 = *(_QWORD *)&v19.Data1;
  v19 = *(struct _GUID *)(*(_QWORD *)&v19.Data1 + 88LL);
  v15 = PhoneController::_OnCallsChanged((PhoneController *)a1, &v19, (__int64)Block);
  v17 = v15;
  if ( v15 >= 0 )
  {
    v18 = *(_QWORD *)(a1 + 176);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      *(_QWORD *)(a1 + 176) = 0;
    }
    if ( Block[0] != (void *)-1LL )
    {
      Block[1] = Block[0];
      operator delete(Block[0]);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return 0;
  }
  BackTraceCollection::Capture(v16, v15);
  Log_HREvent_7(v17, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3035);
  if ( Block[0] != (void *)-1LL )
  {
    Block[1] = Block[0];
    operator delete(Block[0]);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v17;
}

```

## disassembly

```asm
0x180038d2c  mov     [rsp-8+arg_10], rbx
0x180038d31  push    rbp
0x180038d32  push    rsi
0x180038d33  push    rdi
0x180038d34  push    r14
0x180038d36  push    r15
0x180038d38  lea     rbp, [rsp-0EB0h]
0x180038d40  sub     rsp, 0FB0h
0x180038d47  mov     rax, cs:__security_cookie
0x180038d4e  xor     rax, rsp
0x180038d51  mov     [rbp+0ED0h+var_30], rax
0x180038d58  mov     r14d, edx
0x180038d5b  mov     rdi, rcx
0x180038d5e  call    cs:__imp_GetCurrentThreadId
0x180038d64  cmp     [rdi+0F0h], eax
0x180038d6a  jz      short loc_180038D91
0x180038d6c  mov     r8d, 0BC3h
0x180038d72  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038d79  call    Log_AssertionEvent_3
0x180038d7e  call    cs:__imp_GetCurrentThreadId
0x180038d84  cmp     [rdi+0F0h], eax
0x180038d8a  jz      short loc_180038D91
0x180038d8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038d91  mov     rsi, [rdi+0B0h]
0x180038d98  xor     r15d, r15d
0x180038d9b  test    rsi, rsi
0x180038d9e  jz      loc_180038FD7
0x180038da4  xor     edx, edx; Val
0x180038da6  lea     rcx, [rsp+0FD0h+var_F70]; void *
0x180038dab  mov     r8d, 0F40h; Size
0x180038db1  call    memset_0
0x180038db6  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180038dbe  lea     rcx, [rsi+0B8h]
0x180038dc5  movdqu  xmmword ptr [rsp+0FD0h+Block], xmm0
0x180038dcb  mov     [rsp+0FD0h+var_F80], 0FFFFFFFFFFFFFFFFh
0x180038dd4  lea     r9d, [r15+40h]
0x180038dd8  mov     eax, [rsi+0BFCh]
0x180038dde  lea     r10, [rbp+0ED0h+var_EB8]
0x180038de2  mov     [rsp+0FD0h+var_F70], eax
0x180038de6  mov     eax, 7FFFFFFEh
0x180038deb  mov     qword ptr [rsp+0FD0h+var_FA0.Data1], r15
0x180038df0  mov     [rsp+0FD0h+var_F68], 0E8h
0x180038df9  test    rax, rax
0x180038dfc  jz      short loc_180038E1B
0x180038dfe  movzx   edx, word ptr [rcx]
0x180038e01  test    dx, dx
0x180038e04  jz      short loc_180038E1B
0x180038e06  mov     [r10], dx
0x180038e0a  add     rcx, 2
0x180038e0e  add     r10, 2
0x180038e12  dec     rax
0x180038e15  sub     r9, 1
0x180038e19  jnz     short loc_180038DF9
0x180038e1b  mov     rax, r9
0x180038e1e  lea     rcx, [r10-2]
0x180038e22  neg     rax
0x180038e25  sbb     ebx, ebx
0x180038e27  not     ebx
0x180038e29  and     ebx, 8007007Ah
0x180038e2f  test    r9, r9
0x180038e32  cmovnz  rcx, r10; this
0x180038e36  mov     [rcx], r15w
0x180038e3a  jnz     short loc_180038E7F
0x180038e3c  mov     edx, ebx; int
0x180038e3e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180038e43  mov     r9d, 0BD3h
0x180038e49  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038e50  mov     edx, 1
0x180038e55  mov     ecx, ebx
0x180038e57  call    Log_HREvent_7
0x180038e5c  mov     rcx, [rsp+0FD0h+Block]; Block
0x180038e61  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038e65  jz      short loc_180038E78
0x180038e67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180038e6e  mov     [rsp+0FD0h+Block+8], rcx
0x180038e73  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038e78  mov     eax, ebx
0x180038e7a  jmp     loc_180038FD9
0x180038e7f  lea     rdx, [rsp+0FD0h+var_FA0]; struct PhoneLine **
0x180038e84  mov     [rbp+0ED0h+var_C70], 2
0x180038e8e  mov     rcx, rsi; this
0x180038e91  mov     [rbp+0ED0h+var_C78], 5
0x180038e9b  mov     [rbp+0ED0h+var_C74], r14d
0x180038ea2  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180038ea7  lea     rdx, [rsp+0FD0h+var_F70]
0x180038eac  lea     rcx, [rsp+0FD0h+Block]
0x180038eb1  call    ?push_back@?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@QEAA_N$$QEAUCallUpdate@@@Z; utl::vector<CallUpdate,utl::allocator<CallUpdate>>::push_back(CallUpdate &&)
0x180038eb6  test    al, al
0x180038eb8  jnz     short loc_180038F17
0x180038eba  mov     ebx, 8007000Eh
0x180038ebf  mov     edx, ebx; int
0x180038ec1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180038ec6  mov     r9d, 0BDAh
0x180038ecc  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038ed3  xor     edx, edx
0x180038ed5  mov     ecx, ebx
0x180038ed7  call    Log_HREvent_7
0x180038edc  mov     rcx, [rsp+0FD0h+Block]; Block
0x180038ee1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038ee5  jz      short loc_180038EF8
0x180038ee7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180038eee  mov     [rsp+0FD0h+Block+8], rcx
0x180038ef3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038ef8  mov     rcx, qword ptr [rsp+0FD0h+var_FA0.Data1]
0x180038efd  test    rcx, rcx
0x180038f00  jz      loc_180038E78
0x180038f06  mov     rdx, [rcx]
0x180038f09  mov     rax, [rdx+10h]
0x180038f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f12  jmp     loc_180038E78
0x180038f17  mov     rbx, qword ptr [rsp+0FD0h+var_FA0.Data1]
0x180038f1c  lea     r8, [rsp+0FD0h+Block]
0x180038f21  lea     rdx, [rsp+0FD0h+var_FA0]; struct _GUID *
0x180038f26  mov     rcx, rdi; this
0x180038f29  movups  xmm0, xmmword ptr [rbx+58h]
0x180038f2d  movdqu  xmmword ptr [rsp+0FD0h+var_FA0.Data1], xmm0
0x180038f33  call    ?_OnCallsChanged@PhoneController@@IEAAJAEBU_GUID@@AEBV?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@@Z; PhoneController::_OnCallsChanged(_GUID const &,utl::vector<CallUpdate,utl::allocator<CallUpdate>> const &)
0x180038f38  mov     esi, eax
0x180038f3a  test    eax, eax
0x180038f3c  jns     short loc_180038F8D
0x180038f3e  mov     edx, eax; int
0x180038f40  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180038f45  mov     r9d, 0BDBh
0x180038f4b  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180038f52  mov     edx, 1
0x180038f57  mov     ecx, esi
0x180038f59  call    Log_HREvent_7
0x180038f5e  mov     rcx, [rsp+0FD0h+Block]; Block
0x180038f63  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038f67  jz      short loc_180038F7A
0x180038f69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180038f70  mov     [rsp+0FD0h+Block+8], rcx
0x180038f75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038f7a  mov     rax, [rbx]
0x180038f7d  mov     rcx, rbx
0x180038f80  mov     rax, [rax+10h]
0x180038f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f89  mov     eax, esi
0x180038f8b  jmp     short loc_180038FD9
0x180038f8d  mov     rcx, [rdi+0B0h]
0x180038f94  test    rcx, rcx
0x180038f97  jz      short loc_180038FAC
0x180038f99  mov     rax, [rcx]
0x180038f9c  mov     rax, [rax+10h]
0x180038fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fa5  mov     [rdi+0B0h], r15
0x180038fac  mov     rcx, [rsp+0FD0h+Block]; Block
0x180038fb1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038fb5  jz      short loc_180038FC8
0x180038fb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180038fbe  mov     [rsp+0FD0h+Block+8], rcx
0x180038fc3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038fc8  mov     rax, [rbx]
0x180038fcb  mov     rcx, rbx
0x180038fce  mov     rax, [rax+10h]
0x180038fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fd7  xor     eax, eax
0x180038fd9  mov     rcx, [rbp+0ED0h+var_30]
0x180038fe0  xor     rcx, rsp; StackCookie
0x180038fe3  call    __security_check_cookie
0x180038fe8  mov     rbx, [rsp+0FD0h+arg_10]
0x180038ff0  add     rsp, 0FB0h
0x180038ff7  pop     r15
0x180038ff9  pop     r14
0x180038ffb  pop     rdi
0x180038ffc  pop     rsi
0x180038ffd  pop     rbp
0x180038ffe  retn
```
