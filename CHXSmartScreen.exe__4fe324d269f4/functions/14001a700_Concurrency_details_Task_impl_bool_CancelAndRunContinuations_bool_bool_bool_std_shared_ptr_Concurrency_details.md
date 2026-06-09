# Concurrency::details::_Task_impl<bool>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x14001a700`
- end: `0x14001a930`
- name: `?_CancelAndRunContinuations@?$_Task_impl@_N@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1400086b0`
- `0x14001a700`
- `0x14001d188`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001a878`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001a878`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a7fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a8f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a7fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a8f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a73b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a73b`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<bool>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 *a5)
{
  struct _RTL_CRITICAL_SECTION *v8; // r14
  int v9; // esi
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rbx
  int v14; // esi
  __int64 (__fastcall ***v15)(_QWORD, char *, __int64 *); // rcx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD v23[3]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-28h]
  __int64 v25; // [rsp+40h] [rbp-20h]
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v9 = 2;
  v10 = *(_DWORD *)(a1 + 16);
  if ( a3 )
  {
    if ( v10 != 4 )
    {
      v11 = a5[1];
      v12 = *a5;
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v13 = *(volatile signed __int32 **)(a1 + 32);
      *(_QWORD *)(a1 + 32) = v11;
      *(_QWORD *)(a1 + 24) = v12;
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      goto LABEL_14;
    }
LABEL_30:
    LeaveCriticalSection(v8);
    return 0;
  }
  if ( v10 == 3 || *(_DWORD *)(a1 + 16) == 4 || *(_DWORD *)(a1 + 16) == 2 && !a2 )
    goto LABEL_30;
LABEL_14:
  if ( a2 || !*(_DWORD *)(a1 + 16) )
  {
    *(_DWORD *)(a1 + 16) = 4;
    v9 = 1;
  }
  else
  {
    *(_DWORD *)(a1 + 16) = 2;
  }
  LeaveCriticalSection(v8);
  v14 = v9 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      v15 = *(__int64 (__fastcall ****)(_QWORD, char *, __int64 *))(a1 + 168);
      if ( v15 )
      {
        v26 = 0;
        v16 = (**v15)(v15, _uuidof__AUIAsyncInfo_Foundation_Windows__, &v26);
        if ( v16 < 0 )
          __abi_WinRTraiseException(v16);
        v17 = v26;
        v25 = v26;
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 72LL))(v26);
        if ( v18 < 0 )
          __abi_WinRTraiseException(v18);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  else
  {
    SetEvent(*(HANDLE *)(a1 + 8));
    if ( *(_QWORD *)(a1 + 104) )
    {
      v23[0] = &std::_Func_impl<std::_Callable_obj<_lambda_bb3ea35c7a129712676a4a6472ecdc6a_,0>,std::allocator<std::_Func_class<void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
      v23[1] = a1;
      v24 = v23;
      Concurrency::details::_ScheduleFuncWithAutoInline(v23, 16);
      v19 = v24;
      if ( v24 )
      {
        v20 = v23;
        LOBYTE(v20) = v24 != v23;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v20);
        v19 = 0;
        v24 = 0;
      }
      if ( v19 )
      {
        v21 = v23;
        LOBYTE(v21) = v19 != v23;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v21);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14001a700  mov     [rsp-28h+arg_8], rbx
0x14001a705  mov     [rsp-28h+arg_10], rsi
0x14001a70a  push    rbp
0x14001a70b  push    rdi
0x14001a70c  push    r12
0x14001a70e  push    r14
0x14001a710  push    r15
0x14001a712  mov     rbp, rsp
0x14001a715  sub     rsp, 60h
0x14001a719  mov     rax, cs:__security_cookie
0x14001a720  xor     rax, rsp
0x14001a723  mov     [rbp+var_10], rax
0x14001a727  mov     bl, r8b
0x14001a72a  mov     r12b, dl
0x14001a72d  mov     rdi, rcx
0x14001a730  mov     r15, [rbp+arg_20]
0x14001a734  lea     r14, [rcx+28h]
0x14001a738  mov     rcx, r14; lpCriticalSection
0x14001a73b  call    cs:__imp_EnterCriticalSection
0x14001a741  mov     esi, 2
0x14001a746  mov     eax, [rdi+10h]
0x14001a749  test    bl, bl
0x14001a74b  jz      short loc_14001A7B5
0x14001a74d  cmp     eax, 4
0x14001a750  jz      loc_14001A8F0
0x14001a756  mov     rax, [r15+8]
0x14001a75a  mov     rcx, [r15]
0x14001a75d  test    rax, rax
0x14001a760  jz      short loc_14001A766
0x14001a762  lock inc dword ptr [rax+8]
0x14001a766  mov     rbx, [rdi+20h]
0x14001a76a  mov     [rdi+20h], rax
0x14001a76e  mov     [rdi+18h], rcx
0x14001a772  test    rbx, rbx
0x14001a775  jz      short loc_14001A7B3
0x14001a777  or      r15d, 0FFFFFFFFh
0x14001a77b  mov     eax, r15d
0x14001a77e  lock xadd [rbx+8], eax
0x14001a783  add     eax, r15d
0x14001a786  jnz     short loc_14001A7B3
0x14001a788  mov     rax, [rbx]
0x14001a78b  mov     rcx, rbx
0x14001a78e  mov     rax, [rax]
0x14001a791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a796  mov     eax, r15d
0x14001a799  lock xadd [rbx+0Ch], eax
0x14001a79e  add     eax, r15d
0x14001a7a1  jnz     short loc_14001A7B3
0x14001a7a3  mov     rax, [rbx]
0x14001a7a6  mov     rcx, rbx
0x14001a7a9  mov     rax, [rax+8]
0x14001a7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a7b2  nop
0x14001a7b3  jmp     short loc_14001A7DA
0x14001a7b5  cmp     eax, 3
0x14001a7b8  jz      loc_14001A8F0
0x14001a7be  mov     eax, [rdi+10h]
0x14001a7c1  cmp     eax, 4
0x14001a7c4  jz      loc_14001A8F0
0x14001a7ca  mov     eax, [rdi+10h]
0x14001a7cd  cmp     eax, esi
0x14001a7cf  jnz     short loc_14001A7DA
0x14001a7d1  test    r12b, r12b
0x14001a7d4  jz      loc_14001A8F0
0x14001a7da  test    r12b, r12b
0x14001a7dd  jnz     short loc_14001A7EB
0x14001a7df  mov     eax, [rdi+10h]
0x14001a7e2  test    eax, eax
0x14001a7e4  jz      short loc_14001A7EB
0x14001a7e6  mov     [rdi+10h], esi
0x14001a7e9  jmp     short loc_14001A7F7
0x14001a7eb  mov     dword ptr [rdi+10h], 4
0x14001a7f2  mov     esi, 1
0x14001a7f7  mov     rcx, r14; lpCriticalSection
0x14001a7fa  call    cs:__imp_LeaveCriticalSection
0x14001a800  sub     esi, 1
0x14001a803  jz      short loc_14001A874
0x14001a805  cmp     esi, 1
0x14001a808  jnz     loc_14001A8EC
0x14001a80e  mov     rcx, [rdi+0A8h]
0x14001a815  test    rcx, rcx
0x14001a818  jz      loc_14001A8EC
0x14001a81e  mov     [rbp+var_18], 0
0x14001a826  mov     rax, [rcx]
0x14001a829  lea     r8, [rbp+var_18]
0x14001a82d  lea     rdx, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x14001a834  mov     rax, [rax]
0x14001a837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a83c  test    eax, eax
0x14001a83e  js      loc_14001A928
0x14001a844  mov     rbx, [rbp+var_18]
0x14001a848  mov     [rbp+var_20], rbx
0x14001a84c  mov     rax, [rbx]
0x14001a84f  mov     rcx, rbx
0x14001a852  mov     rax, [rax+48h]
0x14001a856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a85b  test    eax, eax
0x14001a85d  js      loc_14001A920
0x14001a863  mov     rax, [rbx]
0x14001a866  mov     rcx, rbx
0x14001a869  mov     rax, [rax+10h]
0x14001a86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a872  jmp     short loc_14001A8EC
0x14001a874  mov     rcx, [rdi+8]; hEvent
0x14001a878  call    cs:__imp_SetEvent
0x14001a87e  cmp     qword ptr [rdi+68h], 0
0x14001a883  jz      short loc_14001A8EC
0x14001a885  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_bb3ea35c7a129712676a4a6472ecdc6a_@@$0A@@std@@V?$allocator@V?$_Func_class@XU_Nil@std@@U12@U12@U12@U12@U12@U12@@std@@@2@XU_Nil@2@U42@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_bb3ea35c7a129712676a4a6472ecdc6a_,0>,std::allocator<std::_Func_class<void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14001a88c  mov     [rbp+var_40], rax
0x14001a890  mov     [rbp+var_38], rdi
0x14001a894  lea     rax, [rbp+var_40]
0x14001a898  mov     [rbp+var_28], rax
0x14001a89c  mov     edx, 10h
0x14001a8a1  lea     rcx, [rbp+var_40]
0x14001a8a5  call    Concurrency__details___ScheduleFuncWithAutoInline
0x14001a8aa  nop
0x14001a8ab  mov     rcx, [rbp+var_28]
0x14001a8af  test    rcx, rcx
0x14001a8b2  jz      short loc_14001A8D0
0x14001a8b4  mov     rax, [rcx]
0x14001a8b7  lea     rdx, [rbp+var_40]
0x14001a8bb  cmp     rcx, rdx
0x14001a8be  setnz   dl
0x14001a8c1  mov     rax, [rax+20h]
0x14001a8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a8ca  xor     ecx, ecx
0x14001a8cc  mov     [rbp+var_28], rcx
0x14001a8d0  test    rcx, rcx
0x14001a8d3  jz      short loc_14001A8EC
0x14001a8d5  mov     rax, [rcx]
0x14001a8d8  lea     rdx, [rbp+var_40]
0x14001a8dc  cmp     rcx, rdx
0x14001a8df  setnz   dl
0x14001a8e2  mov     rax, [rax+20h]
0x14001a8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a8eb  nop
0x14001a8ec  mov     al, 1
0x14001a8ee  jmp     short loc_14001A8FB
0x14001a8f0  mov     rcx, r14; lpCriticalSection
0x14001a8f3  call    cs:__imp_LeaveCriticalSection
0x14001a8f9  xor     al, al
0x14001a8fb  mov     rcx, [rbp+var_10]
0x14001a8ff  xor     rcx, rsp; StackCookie
0x14001a902  call    __security_check_cookie
0x14001a907  lea     r11, [rsp+60h+var_s0]
0x14001a90c  mov     rbx, [r11+38h]
0x14001a910  mov     rsi, [r11+40h]
0x14001a914  mov     rsp, r11
0x14001a917  pop     r15
0x14001a919  pop     r14
0x14001a91b  pop     r12
0x14001a91d  pop     rdi
0x14001a91e  pop     rbp
0x14001a91f  retn
0x14001a920  mov     ecx, eax; int
0x14001a922  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001a928  mov     ecx, eax; int
0x14001a92a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
