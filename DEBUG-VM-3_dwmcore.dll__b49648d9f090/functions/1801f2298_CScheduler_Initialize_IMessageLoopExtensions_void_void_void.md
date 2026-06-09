# CScheduler::Initialize(IMessageLoopExtensions *,void *,void *,void *)

- ea: `0x1801f2298`
- end: `0x1801f233d`
- name: `?Initialize@CScheduler@@QEAAJPEAUIMessageLoopExtensions@@PEAX11@Z`
- size: `165`
- prototype: `__int64 __fastcall(CScheduler *__hidden this, struct IMessageLoopExtensions *, void *, void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006fe0`

## callees

- `0x1800098f8`
- `0x180042de0`
- `0x1801f2298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801f22b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801f22b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f22d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f22d4`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801f22c6`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801f22c6`

## pseudocode

```c
__int64 __fastcall CScheduler::Initialize(
        CScheduler *this,
        struct IMessageLoopExtensions *a2,
        void *a3,
        void *a4,
        void *a5)
{
  HANDLE WaitableTimerW; // rax
  HANDLE v9; // rsi
  signed int LastError; // eax
  signed int v11; // ebx

  *(_QWORD *)this = a5;
  SetLastError(0);
  WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
  v9 = WaitableTimerW;
  if ( WaitableTimerW )
  {
    v11 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 8,
      WaitableTimerW);
    *((_QWORD *)this + 3) = a3;
    *((_QWORD *)this + 4) = a4;
    *((_QWORD *)this + 5) = v9;
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x1Du, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801f2298  push    rbx
0x1801f229a  push    rbp
0x1801f229b  push    rsi
0x1801f229c  push    rdi
0x1801f229d  push    r14
0x1801f229f  sub     rsp, 30h
0x1801f22a3  mov     rax, [rsp+58h+arg_20]
0x1801f22ab  mov     rdi, rcx
0x1801f22ae  mov     [rcx], rax
0x1801f22b1  mov     rbp, r9
0x1801f22b4  xor     ecx, ecx; dwErrCode
0x1801f22b6  mov     r14, r8
0x1801f22b9  call    cs:__imp_SetLastError
0x1801f22bf  xor     r8d, r8d; lpTimerName
0x1801f22c2  xor     edx, edx; bManualReset
0x1801f22c4  xor     ecx, ecx; lpTimerAttributes
0x1801f22c6  call    cs:__imp_CreateWaitableTimerW
0x1801f22cc  mov     rsi, rax
0x1801f22cf  test    rax, rax
0x1801f22d2  jnz     short loc_1801F2316
0x1801f22d4  call    cs:__imp_GetLastError
0x1801f22da  mov     ebx, eax
0x1801f22dc  test    eax, eax
0x1801f22de  jle     short loc_1801F22E9
0x1801f22e0  movzx   ebx, ax
0x1801f22e3  or      ebx, 80070000h
0x1801f22e9  test    ebx, ebx
0x1801f22eb  mov     [rsp+58h+var_30], 0; void *
0x1801f22f4  mov     eax, 88980003h
0x1801f22f9  mov     [rsp+58h+var_38], 1Dh; unsigned int
0x1801f2301  cmovns  ebx, eax
0x1801f2304  xor     edx, edx; int *
0x1801f2306  mov     r9d, ebx; int
0x1801f2309  xor     r8d, r8d; unsigned int
0x1801f230c  lea     ecx, [rdx+14h]; unsigned int
0x1801f230f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801f2314  jmp     short loc_1801F2330
0x1801f2316  xor     ebx, ebx
0x1801f2318  lea     rcx, [rdi+8]
0x1801f231c  mov     rdx, rsi
0x1801f231f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801f2324  mov     [rdi+18h], r14
0x1801f2328  mov     [rdi+20h], rbp
0x1801f232c  mov     [rdi+28h], rsi
0x1801f2330  mov     eax, ebx
0x1801f2332  add     rsp, 30h
0x1801f2336  pop     r14
0x1801f2338  pop     rdi
0x1801f2339  pop     rsi
0x1801f233a  pop     rbp
0x1801f233b  pop     rbx
0x1801f233c  retn
```
