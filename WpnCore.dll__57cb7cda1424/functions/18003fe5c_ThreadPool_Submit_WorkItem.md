# ThreadPool::Submit(WorkItem *)

- ea: `0x18003fe5c`
- end: `0x18003ffac`
- name: `?Submit@ThreadPool@@QEAAJPEAVWorkItem@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(ThreadPool *__hidden this, struct WorkItem *)`
- caller_count: `58`
- callee_count: `6`
- tags: ``

## callers

- `0x18003d000`
- `0x18003dd5c`
- `0x18003df30`
- `0x18003e188`
- `0x18003e670`
- `0x18003eee4`
- `0x18003f1a8`
- `0x18003f3dc`
- `0x18003f81c`
- `0x180040350`
- `0x180040c98`
- `0x180041c90`
- `0x180041e54`
- `0x180051d08`
- `0x18005c1dc`
- `0x180064ac0`
- `0x18006d730`
- `0x18007d8c4`
- `0x18007dbb8`
- `0x18007e024`
- `0x18008e370`
- `0x180090b10`
- `0x180094abc`
- `0x18009510c`
- `0x1800953a4`
- `0x1800959c0`
- `0x1800965a0`
- `0x18009be68`
- `0x18009d498`
- `0x18009e21c`
- `0x18009f8a8`
- `0x1800ab400`
- `0x1800ac06c`
- `0x1800acbbc`
- `0x1800acfe0`
- `0x1800afb1c`
- `0x1800b0c10`
- `0x1800b1344`
- `0x1800b5410`
- `0x1800b6d84`
- `0x1800b7918`
- `0x1800b8f5c`
- `0x1800b9168`
- `0x1800b9328`
- `0x1800c07f0`
- `0x1800c5c74`
- `0x1800c6ec0`
- `0x1800cb2ec`
- `0x1800d8340`
- `0x1800e62f4`

## callees

- `0x18000e5f4`
- `0x18003fe5c`
- `0x18003ffb4`
- `0x180040110`
- `0x1800ba0d0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fe9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ff2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fe9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ff2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ff1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ff3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ff1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ff3e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ff0e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ff0e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003ff9f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003ff9f`

## string_xrefs

- `0x18003ff71`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\threadpool.cpp`
- `0x18003ff86`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\threadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ThreadPool::Submit(ThreadPool *this, struct WorkItem *a2)
{
  int v4; // eax
  __int64 v5; // r15
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    v4 = (*(__int64 (__fastcall **)(struct WorkItem *))(*(_QWORD *)a2 + 16LL))(a2);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\threadpool.cpp",
        (const char *)(unsigned int)v4,
        v10);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    if ( *((_BYTE *)this + 80) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\threadpool.cpp",
        (const char *)0x80004005LL,
        v10);
    if ( *((_QWORD *)this + 3) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("list too long");
    v5 = *((_QWORD *)this + 2);
    v6 = operator new(0x18u);
    v6[2] = a2;
    ++*((_QWORD *)this + 3);
    v7 = *(_QWORD **)(v5 + 8);
    *v6 = v5;
    v6[1] = v7;
    *(_QWORD *)(v5 + 8) = v6;
    *v7 = v6;
    if ( !*((_BYTE *)this + 81) )
      SubmitThreadpoolWork(*((PTP_WORK *)this + 9));
    if ( this != (ThreadPool *)-32LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    ++*((_DWORD *)this + 34);
    if ( this != (ThreadPool *)-88LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    ThreadPool::WriteTelemetry(this);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x80,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\threadpool.cpp",
                           v8);
  }
  ThreadPool::WriteTelemetryDetailed(this);
  return 0;
}

```

## disassembly

```asm
0x18003fe5c  mov     [rsp+arg_0], rbx
0x18003fe61  mov     [rsp+arg_18], rsi
0x18003fe66  push    rdi
0x18003fe67  push    r14
0x18003fe69  push    r15
0x18003fe6b  sub     rsp, 30h
0x18003fe6f  mov     r14, rdx
0x18003fe72  mov     rbx, rcx
0x18003fe75  mov     [rsp+48h+arg_8], rdx
0x18003fe7a  mov     rax, [rdx]
0x18003fe7d  mov     rcx, rdx
0x18003fe80  mov     rax, [rax+10h]
0x18003fe84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe89  mov     rcx, [rsp+48h]; this
0x18003fe8e  test    eax, eax
0x18003fe90  js      loc_18003FF83
0x18003fe96  lea     rdi, [rbx+20h]
0x18003fe9a  mov     rcx, rdi; lpCriticalSection
0x18003fe9d  call    cs:__imp_EnterCriticalSection
0x18003fea3  mov     [rsp+48h+arg_10], rdi
0x18003fea8  mov     rcx, [rsp+48h]; this
0x18003fead  cmp     byte ptr [rbx+50h], 0
0x18003feb1  jnz     loc_18003FF6B
0x18003feb7  lea     rsi, [rbx+10h]
0x18003febb  mov     rax, 0AAAAAAAAAAAAAAAh
0x18003fec5  cmp     [rsi+8], rax
0x18003fec9  jz      loc_18003FF98
0x18003fecf  mov     r15, [rsi]
0x18003fed2  mov     [rsp+48h+var_28], rsi
0x18003fed7  mov     [rsp+48h+var_20], 0
0x18003fee0  mov     ecx, 18h; Size
0x18003fee5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003feea  mov     [rax+10h], r14
0x18003feee  inc     qword ptr [rsi+8]
0x18003fef2  mov     rdx, [r15+8]
0x18003fef6  mov     [rax], r15
0x18003fef9  mov     [rax+8], rdx
0x18003fefd  mov     [r15+8], rax
0x18003ff01  mov     [rdx], rax
0x18003ff04  cmp     byte ptr [rbx+51h], 0
0x18003ff08  jnz     short loc_18003FF15
0x18003ff0a  mov     rcx, [rbx+48h]; pwk
0x18003ff0e  call    cs:__imp_SubmitThreadpoolWork
0x18003ff14  nop
0x18003ff15  test    rdi, rdi
0x18003ff18  jz      short loc_18003FF23
0x18003ff1a  mov     rcx, rdi; lpCriticalSection
0x18003ff1d  call    cs:__imp_LeaveCriticalSection
0x18003ff23  lea     rdi, [rbx+58h]
0x18003ff27  mov     rcx, rdi; lpCriticalSection
0x18003ff2a  call    cs:__imp_EnterCriticalSection
0x18003ff30  inc     dword ptr [rbx+88h]
0x18003ff36  test    rdi, rdi
0x18003ff39  jz      short loc_18003FF45
0x18003ff3b  mov     rcx, rdi; lpCriticalSection
0x18003ff3e  call    cs:__imp_LeaveCriticalSection
0x18003ff44  nop
0x18003ff45  mov     rcx, rbx; this
0x18003ff48  call    ?WriteTelemetry@ThreadPool@@AEAAXXZ; ThreadPool::WriteTelemetry(void)
0x18003ff4d  mov     rcx, rbx; this
0x18003ff50  call    ?WriteTelemetryDetailed@ThreadPool@@AEAAXXZ; ThreadPool::WriteTelemetryDetailed(void)
0x18003ff55  xor     eax, eax
0x18003ff57  mov     rbx, [rsp+48h+arg_0]
0x18003ff5c  mov     rsi, [rsp+48h+arg_18]
0x18003ff61  add     rsp, 30h
0x18003ff65  pop     r15
0x18003ff67  pop     r14
0x18003ff69  pop     rdi
0x18003ff6a  retn
0x18003ff6b  mov     r9d, 80004005h; char *
0x18003ff71  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003ff78  mov     edx, 71h ; 'q'; void *
0x18003ff7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ff83  mov     r9d, eax; char *
0x18003ff86  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003ff8d  mov     edx, 6Bh ; 'k'; void *
0x18003ff92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ff98  lea     rcx, aListTooLong; "list too long"
0x18003ff9f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18003ffa6  mov     eax, dword ptr [rsp+48h+arg_8]
0x18003ffaa  jmp     short loc_18003FF57
```
