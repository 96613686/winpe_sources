# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x14001a4c0`
- end: `0x14001a6f0`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1400086b0`
- `0x14001a4c0`
- `0x14001d188`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001a638`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001a638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a5ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a6b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a5ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a6b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a4fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a4fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
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
      v23[0] = &std::_Func_impl<std::_Callable_obj<_lambda_763529b0c7473cbc215a52d189ac9b18_,0>,std::allocator<std::_Func_class<void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
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
0x14001a4c0  mov     [rsp-28h+arg_8], rbx
0x14001a4c5  mov     [rsp-28h+arg_10], rsi
0x14001a4ca  push    rbp
0x14001a4cb  push    rdi
0x14001a4cc  push    r12
0x14001a4ce  push    r14
0x14001a4d0  push    r15
0x14001a4d2  mov     rbp, rsp
0x14001a4d5  sub     rsp, 60h
0x14001a4d9  mov     rax, cs:__security_cookie
0x14001a4e0  xor     rax, rsp
0x14001a4e3  mov     [rbp+var_10], rax
0x14001a4e7  mov     bl, r8b
0x14001a4ea  mov     r12b, dl
0x14001a4ed  mov     rdi, rcx
0x14001a4f0  mov     r15, [rbp+arg_20]
0x14001a4f4  lea     r14, [rcx+28h]
0x14001a4f8  mov     rcx, r14; lpCriticalSection
0x14001a4fb  call    cs:__imp_EnterCriticalSection
0x14001a501  mov     esi, 2
0x14001a506  mov     eax, [rdi+10h]
0x14001a509  test    bl, bl
0x14001a50b  jz      short loc_14001A575
0x14001a50d  cmp     eax, 4
0x14001a510  jz      loc_14001A6B0
0x14001a516  mov     rax, [r15+8]
0x14001a51a  mov     rcx, [r15]
0x14001a51d  test    rax, rax
0x14001a520  jz      short loc_14001A526
0x14001a522  lock inc dword ptr [rax+8]
0x14001a526  mov     rbx, [rdi+20h]
0x14001a52a  mov     [rdi+20h], rax
0x14001a52e  mov     [rdi+18h], rcx
0x14001a532  test    rbx, rbx
0x14001a535  jz      short loc_14001A573
0x14001a537  or      r15d, 0FFFFFFFFh
0x14001a53b  mov     eax, r15d
0x14001a53e  lock xadd [rbx+8], eax
0x14001a543  add     eax, r15d
0x14001a546  jnz     short loc_14001A573
0x14001a548  mov     rax, [rbx]
0x14001a54b  mov     rcx, rbx
0x14001a54e  mov     rax, [rax]
0x14001a551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a556  mov     eax, r15d
0x14001a559  lock xadd [rbx+0Ch], eax
0x14001a55e  add     eax, r15d
0x14001a561  jnz     short loc_14001A573
0x14001a563  mov     rax, [rbx]
0x14001a566  mov     rcx, rbx
0x14001a569  mov     rax, [rax+8]
0x14001a56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a572  nop
0x14001a573  jmp     short loc_14001A59A
0x14001a575  cmp     eax, 3
0x14001a578  jz      loc_14001A6B0
0x14001a57e  mov     eax, [rdi+10h]
0x14001a581  cmp     eax, 4
0x14001a584  jz      loc_14001A6B0
0x14001a58a  mov     eax, [rdi+10h]
0x14001a58d  cmp     eax, esi
0x14001a58f  jnz     short loc_14001A59A
0x14001a591  test    r12b, r12b
0x14001a594  jz      loc_14001A6B0
0x14001a59a  test    r12b, r12b
0x14001a59d  jnz     short loc_14001A5AB
0x14001a59f  mov     eax, [rdi+10h]
0x14001a5a2  test    eax, eax
0x14001a5a4  jz      short loc_14001A5AB
0x14001a5a6  mov     [rdi+10h], esi
0x14001a5a9  jmp     short loc_14001A5B7
0x14001a5ab  mov     dword ptr [rdi+10h], 4
0x14001a5b2  mov     esi, 1
0x14001a5b7  mov     rcx, r14; lpCriticalSection
0x14001a5ba  call    cs:__imp_LeaveCriticalSection
0x14001a5c0  sub     esi, 1
0x14001a5c3  jz      short loc_14001A634
0x14001a5c5  cmp     esi, 1
0x14001a5c8  jnz     loc_14001A6AC
0x14001a5ce  mov     rcx, [rdi+0A8h]
0x14001a5d5  test    rcx, rcx
0x14001a5d8  jz      loc_14001A6AC
0x14001a5de  mov     [rbp+var_18], 0
0x14001a5e6  mov     rax, [rcx]
0x14001a5e9  lea     r8, [rbp+var_18]
0x14001a5ed  lea     rdx, __uuidof_?AUIAsyncInfo@Foundation@Windows@@
0x14001a5f4  mov     rax, [rax]
0x14001a5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5fc  test    eax, eax
0x14001a5fe  js      loc_14001A6E8
0x14001a604  mov     rbx, [rbp+var_18]
0x14001a608  mov     [rbp+var_20], rbx
0x14001a60c  mov     rax, [rbx]
0x14001a60f  mov     rcx, rbx
0x14001a612  mov     rax, [rax+48h]
0x14001a616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a61b  test    eax, eax
0x14001a61d  js      loc_14001A6E0
0x14001a623  mov     rax, [rbx]
0x14001a626  mov     rcx, rbx
0x14001a629  mov     rax, [rax+10h]
0x14001a62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a632  jmp     short loc_14001A6AC
0x14001a634  mov     rcx, [rdi+8]; hEvent
0x14001a638  call    cs:__imp_SetEvent
0x14001a63e  cmp     qword ptr [rdi+68h], 0
0x14001a643  jz      short loc_14001A6AC
0x14001a645  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@$0A@@std@@V?$allocator@V?$_Func_class@XU_Nil@std@@U12@U12@U12@U12@U12@U12@@std@@@2@XU_Nil@2@U42@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_763529b0c7473cbc215a52d189ac9b18_,0>,std::allocator<std::_Func_class<void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14001a64c  mov     [rbp+var_40], rax
0x14001a650  mov     [rbp+var_38], rdi
0x14001a654  lea     rax, [rbp+var_40]
0x14001a658  mov     [rbp+var_28], rax
0x14001a65c  mov     edx, 10h
0x14001a661  lea     rcx, [rbp+var_40]
0x14001a665  call    Concurrency__details___ScheduleFuncWithAutoInline
0x14001a66a  nop
0x14001a66b  mov     rcx, [rbp+var_28]
0x14001a66f  test    rcx, rcx
0x14001a672  jz      short loc_14001A690
0x14001a674  mov     rax, [rcx]
0x14001a677  lea     rdx, [rbp+var_40]
0x14001a67b  cmp     rcx, rdx
0x14001a67e  setnz   dl
0x14001a681  mov     rax, [rax+20h]
0x14001a685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a68a  xor     ecx, ecx
0x14001a68c  mov     [rbp+var_28], rcx
0x14001a690  test    rcx, rcx
0x14001a693  jz      short loc_14001A6AC
0x14001a695  mov     rax, [rcx]
0x14001a698  lea     rdx, [rbp+var_40]
0x14001a69c  cmp     rcx, rdx
0x14001a69f  setnz   dl
0x14001a6a2  mov     rax, [rax+20h]
0x14001a6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a6ab  nop
0x14001a6ac  mov     al, 1
0x14001a6ae  jmp     short loc_14001A6BB
0x14001a6b0  mov     rcx, r14; lpCriticalSection
0x14001a6b3  call    cs:__imp_LeaveCriticalSection
0x14001a6b9  xor     al, al
0x14001a6bb  mov     rcx, [rbp+var_10]
0x14001a6bf  xor     rcx, rsp; StackCookie
0x14001a6c2  call    __security_check_cookie
0x14001a6c7  lea     r11, [rsp+60h+var_s0]
0x14001a6cc  mov     rbx, [r11+38h]
0x14001a6d0  mov     rsi, [r11+40h]
0x14001a6d4  mov     rsp, r11
0x14001a6d7  pop     r15
0x14001a6d9  pop     r14
0x14001a6db  pop     r12
0x14001a6dd  pop     rdi
0x14001a6de  pop     rbp
0x14001a6df  retn
0x14001a6e0  mov     ecx, eax; int
0x14001a6e2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001a6e8  mov     ecx, eax; int
0x14001a6ea  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
