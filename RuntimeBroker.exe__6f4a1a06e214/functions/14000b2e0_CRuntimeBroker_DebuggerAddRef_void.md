# CRuntimeBroker::DebuggerAddRef(void)

- ea: `0x14000b2e0`
- end: `0x14000b311`
- name: `?DebuggerAddRef@CRuntimeBroker@@UEAAJXZ`
- size: `49`
- prototype: `__int64 __fastcall(CRuntimeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000aef0`
- `0x14000b2e0`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::DebuggerAddRef(CRuntimeBroker *this)
{
  __int64 result; // rax
  bool v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  result = CRuntimeBroker::CheckClient(this, &v2);
  if ( (int)result >= 0 )
  {
    if ( v2 )
      _InterlockedIncrement((volatile signed __int32 *)&CRuntimeBroker::s_cRefDebugger);
    else
      return 2147942405LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000b2e0  sub     rsp, 28h
0x14000b2e4  lea     rdx, [rsp+28h+arg_8]; bool *
0x14000b2e9  mov     [rsp+28h+arg_8], 0
0x14000b2ee  call    ?CheckClient@CRuntimeBroker@@AEAAJPEA_N@Z; CRuntimeBroker::CheckClient(bool *)
0x14000b2f3  test    eax, eax
0x14000b2f5  js      short loc_14000B30C
0x14000b2f7  cmp     [rsp+28h+arg_8], 0
0x14000b2fc  jnz     short loc_14000B305
0x14000b2fe  mov     eax, 80070005h
0x14000b303  jmp     short loc_14000B30C
0x14000b305  lock inc cs:?s_cRefDebugger@CRuntimeBroker@@0KA; ulong CRuntimeBroker::s_cRefDebugger
0x14000b30c  add     rsp, 28h
0x14000b310  retn
```
