# AsyncWorkQueue::_AsyncCallback(void)

- ea: `0x180005720`
- end: `0x1800058bf`
- name: `?_AsyncCallback@AsyncWorkQueue@@AEAAXXZ`
- size: `415`
- prototype: `void __fastcall(AsyncWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800056e0`

## callees

- `0x18000266c`
- `0x180003da4`
- `0x180005720`
- `0x18000a8e0`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005880`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005741`

## pseudocode

```c
void __fastcall AsyncWorkQueue::_AsyncCallback(AsyncWorkQueue *this)
{
  __int64 **v2; // r14
  __int64 *v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 *v8; // rdi
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, GetCurrentThreadId(), 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v12 = 0;
  v13 = 0;
  v2 = (__int64 **)((char *)this + 56);
  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = v3[2];
    v5 = v12;
    if ( v12 != v4 )
    {
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v3[2]);
        v5 = v12;
      }
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v12 = v4;
    }
    v6 = v3[3];
    v7 = v13;
    if ( v13 != v6 )
    {
      if ( v6 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v3[3]);
        v7 = v13;
      }
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v13 = v6;
    }
    v8 = *v2;
    v9 = (__int64 *)(*v2)[1];
    v10 = **v2;
    *v9 = v10;
    *(_QWORD *)(v10 + 8) = v9;
    v11 = v8[3];
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(v8 + 2);
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    --*((_QWORD *)this + 9);
    *((_QWORD *)this + 10) = &v12;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, v13);
  }
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_DWORD *)this + 22) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(&v12);
}

```

## disassembly

```asm
0x180005720  push    rbp
0x180005722  push    rbx
0x180005723  push    rsi
0x180005724  push    rdi
0x180005725  push    r14
0x180005727  push    r15
0x180005729  mov     rbp, rsp
0x18000572c  sub     rsp, 48h
0x180005730  mov     rax, cs:__security_cookie
0x180005737  xor     rax, rsp
0x18000573a  mov     [rbp+var_10], rax
0x18000573e  mov     rbx, rcx
0x180005741  call    cs:__imp_GetCurrentThreadId
0x180005747  mov     edx, eax
0x180005749  xor     eax, eax
0x18000574b  lock cmpxchg [rbx+68h], edx
0x180005750  jz      short loc_180005758
0x180005752  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005757  nop
0x180005758  mov     [rbp+var_20], 0
0x180005760  mov     [rbp+var_18], 0
0x180005768  lea     r15, [rbx+10h]
0x18000576c  lea     r14, [rbx+38h]
0x180005770  mov     rcx, r15; lpCriticalSection
0x180005773  call    cs:__imp_EnterCriticalSection
0x180005779  mov     rsi, [r14]
0x18000577c  cmp     rsi, r14
0x18000577f  jz      loc_180005867
0x180005785  mov     rdi, [rsi+10h]
0x180005789  mov     rcx, [rbp+var_20]
0x18000578d  cmp     rcx, rdi
0x180005790  jz      short loc_1800057BF
0x180005792  test    rdi, rdi
0x180005795  jz      short loc_1800057AA
0x180005797  mov     rax, [rdi]
0x18000579a  mov     rcx, rdi
0x18000579d  mov     rax, [rax+8]
0x1800057a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a6  mov     rcx, [rbp+var_20]
0x1800057aa  test    rcx, rcx
0x1800057ad  jz      short loc_1800057BB
0x1800057af  mov     rax, [rcx]
0x1800057b2  mov     rax, [rax+10h]
0x1800057b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057bb  mov     [rbp+var_20], rdi
0x1800057bf  mov     rdi, [rsi+18h]
0x1800057c3  mov     rcx, [rbp+var_18]
0x1800057c7  cmp     rcx, rdi
0x1800057ca  jz      short loc_1800057F9
0x1800057cc  test    rdi, rdi
0x1800057cf  jz      short loc_1800057E4
0x1800057d1  mov     rax, [rdi]
0x1800057d4  mov     rcx, rdi
0x1800057d7  mov     rax, [rax+8]
0x1800057db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e0  mov     rcx, [rbp+var_18]
0x1800057e4  test    rcx, rcx
0x1800057e7  jz      short loc_1800057F5
0x1800057e9  mov     rax, [rcx]
0x1800057ec  mov     rax, [rax+10h]
0x1800057f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f5  mov     [rbp+var_18], rdi
0x1800057f9  mov     rdi, [r14]
0x1800057fc  mov     rcx, [rdi+8]
0x180005800  mov     rax, [rdi]
0x180005803  mov     [rcx], rax
0x180005806  mov     [rax+8], rcx
0x18000580a  mov     rcx, [rdi+18h]
0x18000580e  test    rcx, rcx
0x180005811  jz      short loc_180005820
0x180005813  mov     rax, [rcx]
0x180005816  mov     rax, [rax+10h]
0x18000581a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581f  nop
0x180005820  lea     rcx, [rdi+10h]
0x180005824  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005829  nop
0x18000582a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005831  mov     rcx, rdi; void *
0x180005834  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005839  dec     qword ptr [r14+10h]
0x18000583d  lea     rax, [rbp+var_20]
0x180005841  mov     [rbx+50h], rax
0x180005845  mov     rcx, r15; lpCriticalSection
0x180005848  call    cs:__imp_LeaveCriticalSection
0x18000584e  mov     rcx, [rbp+var_20]
0x180005852  mov     rax, [rcx]
0x180005855  mov     rdx, [rbp+var_18]
0x180005859  mov     rax, [rax+18h]
0x18000585d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005862  jmp     loc_180005770
0x180005867  mov     qword ptr [rbx+50h], 0
0x18000586f  mov     dword ptr [rbx+68h], 0
0x180005876  mov     dword ptr [rbx+58h], 0
0x18000587d  mov     rcx, r15; lpCriticalSection
0x180005880  call    cs:__imp_LeaveCriticalSection
0x180005886  mov     rcx, [rbp+var_18]
0x18000588a  test    rcx, rcx
0x18000588d  jz      short loc_18000589C
0x18000588f  mov     rax, [rcx]
0x180005892  mov     rax, [rax+10h]
0x180005896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589b  nop
0x18000589c  lea     rcx, [rbp+var_20]
0x1800058a0  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x1800058a5  nop
0x1800058a6  mov     rcx, [rbp+var_10]
0x1800058aa  xor     rcx, rsp; StackCookie
0x1800058ad  call    __security_check_cookie
0x1800058b2  add     rsp, 48h
0x1800058b6  pop     r15
0x1800058b8  pop     r14
0x1800058ba  pop     rdi
0x1800058bb  pop     rsi
0x1800058bc  pop     rbx
0x1800058bd  pop     rbp
0x1800058be  retn
```
