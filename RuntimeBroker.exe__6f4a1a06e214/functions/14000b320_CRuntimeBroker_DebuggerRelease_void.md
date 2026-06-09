# CRuntimeBroker::DebuggerRelease(void)

- ea: `0x14000b320`
- end: `0x14000b369`
- name: `?DebuggerRelease@CRuntimeBroker@@UEAAJXZ`
- size: `73`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000aef0`
- `0x14000b320`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoSetErrorReportingFlags` at `0x14000b35a`
- `api-ms-win-core-winrt-error-l1-1-0!RoSetErrorReportingFlags` at `0x14000b35a`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::DebuggerRelease(CRuntimeBroker *this)
{
  int v1; // ecx
  bool v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v1 = CRuntimeBroker::CheckClient(this, &v3);
  if ( v1 >= 0 )
  {
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&CRuntimeBroker::s_cRefDebugger, 0xFFFFFFFF) == 1 )
        return (unsigned int)RoSetErrorReportingFlags(4);
    }
    else
    {
      return (unsigned int)-2147024891;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000b320  sub     rsp, 28h
0x14000b324  lea     rdx, [rsp+28h+arg_8]; bool *
0x14000b329  mov     [rsp+28h+arg_8], 0
0x14000b32e  call    ?CheckClient@CRuntimeBroker@@AEAAJPEA_N@Z; CRuntimeBroker::CheckClient(bool *)
0x14000b333  mov     ecx, eax
0x14000b335  test    eax, eax
0x14000b337  js      short loc_14000B362
0x14000b339  cmp     [rsp+28h+arg_8], 0
0x14000b33e  jnz     short loc_14000B347
0x14000b340  mov     ecx, 80070005h
0x14000b345  jmp     short loc_14000B362
0x14000b347  or      eax, 0FFFFFFFFh
0x14000b34a  lock xadd cs:?s_cRefDebugger@CRuntimeBroker@@0KA, eax; ulong CRuntimeBroker::s_cRefDebugger
0x14000b352  cmp     eax, 1
0x14000b355  jnz     short loc_14000B362
0x14000b357  lea     ecx, [rax+3]
0x14000b35a  call    cs:__imp_RoSetErrorReportingFlags
0x14000b360  mov     ecx, eax
0x14000b362  mov     eax, ecx
0x14000b364  add     rsp, 28h
0x14000b368  retn
```
