# CThread::thread_list(locked_pointer<std::list<CThread *,std::allocator<CThread *>>> *)

- ea: `0x180006edc`
- end: `0x180007051`
- name: `?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006700`
- `0x180006c3c`
- `0x180006d00`

## callees

- `0x1800019c0`
- `0x180001ec8`
- `0x180002090`
- `0x18000223c`
- `0x1800022a4`
- `0x1800068f8`
- `0x1800069e8`
- `0x180006edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f2d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007027`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f46`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThread::thread_list(_QWORD *a1)
{
  __int64 v2; // rdi
  _QWORD *v5; // rax
  _QWORD v6[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD pExceptionObject[4]; // [rsp+30h] [rbp-48h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180010608 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180010608);
    if ( dword_180010608 == -1 )
    {
      v5 = operator new(0x18u);
      *v5 = v5;
      v5[1] = v5;
      qword_180010610 = v5;
      atexit(CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__list__);
      Init_thread_footer(&dword_180010608);
    }
  }
  if ( dword_180010620 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180010620);
    if ( dword_180010620 == -1 )
    {
      if ( !InitializeCriticalSectionAndSpinCount(&stru_180010628, 0x80000400) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
      atexit(CThread::thread_list_::_2_::_dynamic_atexit_destructor_for__lock__);
      Init_thread_footer(&dword_180010620);
    }
  }
  if ( a1 )
  {
    EnterCriticalSection(&stru_180010628);
    if ( !dword_180010654++ )
      dword_180010650 = GetCurrentThreadId();
    pExceptionObject[0] = 0;
    v6[0] = *a1;
    *a1 = &qword_180010610;
    v6[1] = a1[1];
    a1[1] = &stru_180010628;
    locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>((__int64)v6);
    locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>((__int64)pExceptionObject);
  }
  return 0;
}

```

## disassembly

```asm
0x180006edc  push    rbx
0x180006ede  push    rbp
0x180006edf  push    rsi
0x180006ee0  push    rdi
0x180006ee1  sub     rsp, 58h
0x180006ee5  mov     rbx, rcx
0x180006ee8  mov     edx, cs:_tls_index
0x180006eee  mov     rax, gs:58h
0x180006ef7  mov     ebp, 4
0x180006efc  mov     rdi, [rax+rdx*8]
0x180006f00  mov     eax, [rdi+rbp]
0x180006f03  cmp     cs:dword_180010608, eax
0x180006f09  jg      loc_180006FB7
0x180006f0f  lea     rsi, stru_180010628
0x180006f16  mov     eax, [rdi+rbp]
0x180006f19  cmp     cs:dword_180010620, eax
0x180006f1f  jg      loc_180007006
0x180006f25  test    rbx, rbx
0x180006f28  jz      short loc_180006F8E
0x180006f2a  mov     rcx, rsi; lpCriticalSection
0x180006f2d  call    cs:__imp_EnterCriticalSection
0x180006f33  mov     ecx, cs:dword_180010654
0x180006f39  lea     eax, [rcx+1]
0x180006f3c  mov     cs:dword_180010654, eax
0x180006f42  test    ecx, ecx
0x180006f44  jnz     short loc_180006F52
0x180006f46  call    cs:__imp_GetCurrentThreadId
0x180006f4c  mov     cs:dword_180010650, eax
0x180006f52  xorps   xmm0, xmm0
0x180006f55  movdqu  [rsp+78h+pExceptionObject], xmm0
0x180006f5b  mov     rax, [rbx]
0x180006f5e  mov     [rsp+78h+var_58], rax
0x180006f63  lea     rax, qword_180010610
0x180006f6a  mov     [rbx], rax
0x180006f6d  mov     rax, [rbx+8]
0x180006f71  mov     [rsp+78h+var_50], rax
0x180006f76  mov     [rbx+8], rsi
0x180006f7a  lea     rcx, [rsp+78h+var_58]
0x180006f7f  call    ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
0x180006f84  lea     rcx, [rsp+78h+pExceptionObject]
0x180006f89  call    ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
0x180006f8e  xor     eax, eax
0x180006f90  add     rsp, 58h
0x180006f94  pop     rdi
0x180006f95  pop     rsi
0x180006f96  pop     rbp
0x180006f97  pop     rbx
0x180006f98  retn
0x180006f99  lea     rcx, _CThread__thread_list____2____dynamic_atexit_destructor_for__lock__; void (__cdecl *)()
0x180006fa0  call    atexit
0x180006fa5  nop
0x180006fa6  lea     rcx, dword_180010620
0x180006fad  call    _Init_thread_footer
0x180006fb2  jmp     loc_180006F25
0x180006fb7  lea     rcx, dword_180010608
0x180006fbe  call    _Init_thread_header
0x180006fc3  cmp     cs:dword_180010608, 0FFFFFFFFh
0x180006fca  jnz     loc_180006F0F
0x180006fd0  mov     ecx, 18h; Size
0x180006fd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fda  mov     [rax], rax
0x180006fdd  mov     [rax+8], rax
0x180006fe1  mov     cs:qword_180010610, rax
0x180006fe8  lea     rcx, _CThread__thread_list____2____dynamic_atexit_destructor_for__list__; void (__cdecl *)()
0x180006fef  call    atexit
0x180006ff4  nop
0x180006ff5  lea     rcx, dword_180010608
0x180006ffc  call    _Init_thread_footer
0x180007001  jmp     loc_180006F0F
0x180007006  lea     rcx, dword_180010620
0x18000700d  call    _Init_thread_header
0x180007012  cmp     cs:dword_180010620, 0FFFFFFFFh
0x180007019  jnz     loc_180006F25
0x18000701f  mov     edx, 80000400h; dwSpinCount
0x180007024  mov     rcx, rsi; lpCriticalSection
0x180007027  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000702d  test    eax, eax
0x18000702f  jnz     loc_180006F99
0x180007035  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000703a  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000703f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180007046  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000704b  call    _CxxThrowException_0
```
