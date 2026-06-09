# _dynamic_atexit_destructor_for__g_tpCallbackEnv__

- ea: `0x18001c9c0`
- end: `0x18001ca16`
- name: `_dynamic_atexit_destructor_for__g_tpCallbackEnv__`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001c9c0`
- `0x18001ca80`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c9e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c9e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ca05`

## pseudocode

```c
int dynamic_atexit_destructor_for__g_tpCallbackEnv__()
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v2; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  InitOnceBeginInitialize(&InitOnce, 0, &v1, &v2);
  if ( v2 )
    return wil_StagingConfig_LogFeatureProcessUsage();
  else
    return InitOnceComplete(&InitOnce, 0, 0);
}

```

## disassembly

```asm
0x18001c9c0  mov     rax, rsp
0x18001c9c3  sub     rsp, 28h
0x18001c9c7  lea     r9, [rax+10h]; lpContext
0x18001c9cb  mov     dword ptr [rax+8], 0
0x18001c9d2  lea     r8, [rax+8]; fPending
0x18001c9d6  mov     qword ptr [rax+10h], 0
0x18001c9de  xor     edx, edx; dwFlags
0x18001c9e0  lea     rcx, InitOnce; lpInitOnce
0x18001c9e7  call    cs:__imp_InitOnceBeginInitialize
0x18001c9ed  cmp     [rsp+28h+arg_8], 0
0x18001c9f3  jnz     short loc_18001CA0C
0x18001c9f5  xor     r8d, r8d
0x18001c9f8  lea     rcx, InitOnce
0x18001c9ff  xor     edx, edx
0x18001ca01  add     rsp, 28h
0x18001ca05  jmp     cs:__imp_InitOnceComplete
0x18001ca0c  call    wil_StagingConfig_LogFeatureProcessUsage
0x18001ca11  add     rsp, 28h
0x18001ca15  retn
```
