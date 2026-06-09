# CThread::ThreadStartup(void *)

- ea: `0x180006da0`
- end: `0x180006df0`
- name: `?ThreadStartup@CThread@@CAKPEAX@Z`
- size: `80`
- prototype: `void __fastcall __noreturn(volatile signed __int32 *Parameter, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800037e4`
- `0x180006c3c`
- `0x180006d6c`
- `0x180006da0`

## string_xrefs

- `0x180006dcb`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`

## pseudocode

```c
void __fastcall __noreturn CThread::ThreadStartup(
        volatile signed __int32 *Parameter,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( _InterlockedCompareExchange(Parameter + 26, 2, 1) != 1 && _InterlockedCompareExchange(Parameter + 26, 3, 3) != 3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
      a4);
  v5 = CThread::ThreadMain((CThread *)Parameter);
  CThread::Exit((CThread *)Parameter, v5);
}

```

## disassembly

```asm
0x180006da0  push    rbx
0x180006da2  sub     rsp, 20h
0x180006da6  mov     rbx, rcx
0x180006da9  mov     ecx, 2
0x180006dae  lea     eax, [rcx-1]
0x180006db1  lock cmpxchg [rbx+68h], ecx
0x180006db6  jz      short loc_180006DDD
0x180006db8  mov     ecx, 3
0x180006dbd  mov     eax, ecx
0x180006dbf  lock cmpxchg [rbx+68h], ecx
0x180006dc4  jz      short loc_180006DDD
0x180006dc6  mov     rcx, [rsp+28h]; this
0x180006dcb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\cred"...
0x180006dd2  mov     edx, 1FCh; void *
0x180006dd7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006ddd  mov     rcx, rbx; this
0x180006de0  call    ?ThreadMain@CThread@@AEAAJXZ; CThread::ThreadMain(void)
0x180006de5  mov     edx, eax; dwExitCode
0x180006de7  mov     rcx, rbx; this
0x180006dea  call    ?Exit@CThread@@AEAAXJ@Z; CThread::Exit(long)
```
