# Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback

- ea: `0x140003650`
- end: `0x140003666`
- name: `Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003614`

## callees

- `0x140003690`

## pseudocode

```c
__int64 __fastcall Feature_AgenticAppContainerBfsSupport__private_IsEnabledFallback(__int64 a1, __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_AgenticAppContainerBfsSupport__private_descriptor);
}

```

## disassembly

```asm
0x140003650  sub     rsp, 28h
0x140003654  lea     r8, Feature_AgenticAppContainerBfsSupport__private_descriptor
0x14000365b  call    wil_details_IsEnabledFallback
0x140003660  add     rsp, 28h
0x140003664  retn
```
