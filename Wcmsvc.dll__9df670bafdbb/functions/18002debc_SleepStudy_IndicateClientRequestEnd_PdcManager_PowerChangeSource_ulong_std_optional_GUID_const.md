# SleepStudy::IndicateClientRequestEnd(PdcManager::PowerChangeSource,ulong,std::optional<_GUID> const &)

- ea: `0x18002debc`
- end: `0x18002e083`
- name: `?IndicateClientRequestEnd@SleepStudy@@YAXW4PowerChangeSource@PdcManager@@KAEBV?$optional@U_GUID@@@std@@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011320`

## callees

- `0x18002debc`
- `0x18007103c`
- `0x1800af964`
- `0x1800af9a0`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002df90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e073`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002df90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e073`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dee7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dee7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002dfa5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002dfa5`

## string_xrefs

- `0x18002e009`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SleepStudy::IndicateClientRequestEnd(int a1, int a2, __int128 *a3)
{
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdi
  const char *v8; // r9
  unsigned int v9; // [rsp+20h] [rbp-58h]
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  int v11; // [rsp+38h] [rbp-40h]
  int v12; // [rsp+3Ch] [rbp-3Ch]
  __int128 v13; // [rsp+40h] [rbp-38h]
  int v14; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  AcquireSRWLockShared(&SleepStudy::Singleton::s_lock);
  v6 = (volatile signed __int32 *)qword_18013EFD8;
  if ( qword_18013EFD8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_18013EFD8 + 2);
    v6 = (volatile signed __int32 *)qword_18013EFD8;
  }
  v7 = *(_QWORD *)&SleepStudy::Singleton::s_instance;
  v9 = SleepStudy::Singleton::s_instance;
  ReleaseSRWLockShared(&SleepStudy::Singleton::s_lock);
  try
  {
    if ( v7 )
    {
      v10 = v7;
      v11 = a1;
      v12 = a2;
      v13 = *a3;
      v14 = *((_DWORD *)a3 + 4);
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
      if ( *(_BYTE *)(v7 + 392) )
      {
        if ( v7 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
      }
      else
      {
        if ( *(_DWORD *)(v7 + 120) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__SleepStudy::IndicateClientRequestEnd_::_3_::_lambda_1___(
            v7 + 272,
            &v10);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__SleepStudy::IndicateClientRequestEnd_::_3_::_lambda_1___(
            v7 + 352,
            &v10);
        if ( v7 != -128 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 128));
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 256));
        SubmitThreadpoolWork(*(PTP_WORK *)(v7 + 248));
      }
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( !_InterlockedDecrement(v6 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x3D6,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
        (const char *)0x139F,
        v9);
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( !_InterlockedDecrement(v6 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x409,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x18002debc  mov     [rsp+arg_0], rbx
0x18002dec1  mov     [rsp+arg_8], rsi
0x18002dec6  push    rdi
0x18002dec7  push    r14
0x18002dec9  push    r15
0x18002decb  sub     rsp, 60h
0x18002decf  mov     rsi, r8
0x18002ded2  mov     r14d, edx
0x18002ded5  mov     r15d, ecx
0x18002ded8  xorps   xmm0, xmm0
0x18002dedb  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x18002dee0  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x18002dee7  call    cs:__imp_AcquireSRWLockShared
0x18002deed  mov     rbx, cs:qword_18013EFD8
0x18002def4  test    rbx, rbx
0x18002def7  jz      short loc_18002DF04
0x18002def9  lock inc dword ptr [rbx+8]
0x18002defd  mov     rbx, cs:qword_18013EFD8
0x18002df04  mov     rdi, cs:?s_instance@Singleton@SleepStudy@@0V?$shared_ptr@VSingleton@SleepStudy@@@std@@A; std::shared_ptr<SleepStudy::Singleton> SleepStudy::Singleton::s_instance
0x18002df0b  mov     qword ptr [rsp+78h+var_58], rdi; unsigned int
0x18002df10  mov     qword ptr [rsp+78h+var_58+8], rbx
0x18002df15  lea     rcx, ?s_lock@Singleton@SleepStudy@@0Vsrwlock@wil@@A; SRWLock
0x18002df1c  call    cs:__imp_ReleaseSRWLockShared
0x18002df22  nop
0x18002df23  test    rdi, rdi
0x18002df26  jz      loc_18002DFFE
0x18002df2c  mov     [rsp+78h+var_48], rdi
0x18002df31  mov     [rsp+78h+var_40], r15d
0x18002df36  mov     [rsp+78h+var_3C], r14d
0x18002df3b  movups  xmm0, xmmword ptr [rsi]
0x18002df3e  movups  [rsp+78h+var_38], xmm0
0x18002df43  mov     eax, [rsi+10h]
0x18002df46  mov     [rsp+78h+var_28], eax
0x18002df4a  lea     rsi, [rdi+80h]
0x18002df51  mov     rcx, rsi; lpCriticalSection
0x18002df54  call    cs:__imp_EnterCriticalSection
0x18002df5a  mov     [rsp+78h+arg_18], rsi
0x18002df62  lea     rcx, [rdi+110h]
0x18002df69  cmp     byte ptr [rcx+78h], 0
0x18002df6d  jnz     loc_18002E067
0x18002df73  lea     rdx, [rsp+78h+var_48]
0x18002df78  cmp     dword ptr [rdi+78h], 1
0x18002df7c  jnz     loc_18002E059
0x18002df82  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__SleepStudy__IndicateClientRequestEnd____3____lambda_1___
0x18002df87  nop
0x18002df88  test    rsi, rsi
0x18002df8b  jz      short loc_18002DF96
0x18002df8d  mov     rcx, rsi; lpCriticalSection
0x18002df90  call    cs:__imp_LeaveCriticalSection
0x18002df96  lock inc qword ptr [rdi+100h]
0x18002df9e  mov     rcx, [rdi+0F8h]; pwk
0x18002dfa5  call    cs:__imp_SubmitThreadpoolWork
0x18002dfab  nop
0x18002dfac  test    rbx, rbx
0x18002dfaf  jz      short loc_18002DFE8
0x18002dfb1  or      edi, 0FFFFFFFFh
0x18002dfb4  mov     eax, edi
0x18002dfb6  lock xadd [rbx+8], eax
0x18002dfbb  add     eax, edi
0x18002dfbd  jnz     short loc_18002DFE8
0x18002dfbf  mov     rax, [rbx]
0x18002dfc2  mov     rcx, rbx
0x18002dfc5  mov     rax, [rax]
0x18002dfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfcd  mov     eax, edi
0x18002dfcf  lock xadd [rbx+0Ch], eax
0x18002dfd4  add     eax, edi
0x18002dfd6  jnz     short loc_18002DFE8
0x18002dfd8  mov     rax, [rbx]
0x18002dfdb  mov     rcx, rbx
0x18002dfde  mov     rax, [rax+8]
0x18002dfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfe7  nop
0x18002dfe8  lea     r11, [rsp+78h+var_18]
0x18002dfed  mov     rbx, [r11+20h]
0x18002dff1  mov     rsi, [r11+28h]
0x18002dff5  mov     rsp, r11
0x18002dff8  pop     r15
0x18002dffa  pop     r14
0x18002dffc  pop     rdi
0x18002dffd  retn
0x18002dffe  mov     rcx, [rsp+78h]; this
0x18002e003  mov     r9d, 139Fh; char *
0x18002e009  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18002e010  mov     edx, 3D6h; void *
0x18002e015  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002e01a  nop
0x18002e01b  test    rbx, rbx
0x18002e01e  jz      short loc_18002E057
0x18002e020  or      edi, 0FFFFFFFFh
0x18002e023  mov     eax, edi
0x18002e025  lock xadd [rbx+8], eax
0x18002e02a  add     eax, edi
0x18002e02c  jnz     short loc_18002E057
0x18002e02e  mov     rax, [rbx]
0x18002e031  mov     rcx, rbx
0x18002e034  mov     rax, [rax]
0x18002e037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e03c  mov     eax, edi
0x18002e03e  lock xadd [rbx+0Ch], eax
0x18002e043  add     eax, edi
0x18002e045  jnz     short loc_18002E057
0x18002e047  mov     rax, [rbx]
0x18002e04a  mov     rcx, rbx
0x18002e04d  mov     rax, [rax+8]
0x18002e051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e056  nop
0x18002e057  jmp     short loc_18002DFE8
0x18002e059  add     rcx, 50h ; 'P'
0x18002e05d  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__SleepStudy__IndicateClientRequestEnd____3____lambda_1___
0x18002e062  jmp     loc_18002DF88
0x18002e067  test    rsi, rsi
0x18002e06a  jz      loc_18002DFAC
0x18002e070  mov     rcx, rsi; lpCriticalSection
0x18002e073  call    cs:__imp_LeaveCriticalSection
0x18002e079  jmp     loc_18002DFAC
0x18002e07e  jmp     loc_18002DFE8
```
