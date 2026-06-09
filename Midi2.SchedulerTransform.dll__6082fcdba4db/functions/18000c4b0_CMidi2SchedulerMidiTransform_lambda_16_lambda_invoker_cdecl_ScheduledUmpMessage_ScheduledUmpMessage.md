# CMidi2SchedulerMidiTransform::_lambda_16__::_lambda_invoker_cdecl_(ScheduledUmpMessage &,ScheduledUmpMessage &)

- ea: `0x18000c4b0`
- end: `0x18000c4c2`
- name: `?_lambda_invoker_cdecl_@_lambda_16__@CMidi2SchedulerMidiTransform@@SA_NAEAUScheduledUmpMessage@@0@Z`
- size: `18`
- prototype: `bool __fastcall(struct ScheduledUmpMessage *, struct ScheduledUmpMessage *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000c4b0`

## pseudocode

```c
bool __fastcall CMidi2SchedulerMidiTransform::_lambda_16__::_lambda_invoker_cdecl_(
        struct ScheduledUmpMessage *a1,
        struct ScheduledUmpMessage *a2)
{
  bool v2; // cf
  bool v3; // zf
  unsigned int v4; // eax

  v2 = *(_QWORD *)a1 < *(_QWORD *)a2;
  v3 = *(_QWORD *)a1 == *(_QWORD *)a2;
  if ( *(_QWORD *)a1 == *(_QWORD *)a2 )
  {
    v4 = *((_DWORD *)a2 + 2);
    v2 = *((_DWORD *)a1 + 2) < v4;
    v3 = *((_DWORD *)a1 + 2) == v4;
  }
  return !v2 && !v3;
}

```

## disassembly

```asm
0x18000c4b0  mov     rax, [rcx]
0x18000c4b3  cmp     rax, [rdx]
0x18000c4b6  jnz     short loc_18000C4BE
0x18000c4b8  mov     eax, [rdx+8]
0x18000c4bb  cmp     [rcx+8], eax
0x18000c4be  setnbe  al
0x18000c4c1  retn
```
