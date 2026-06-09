# _dynamic_atexit_destructor_for__g_messagingServiceInstance__

- ea: `0x18000b040`
- end: `0x18000b06c`
- name: `_dynamic_atexit_destructor_for__g_messagingServiceInstance__`
- size: `44`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d18`
- `0x18000b040`
- `0x18000c010`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_messagingServiceInstance__()
{
  if ( qword_180013160 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180013160 + 16LL))(qword_180013160);
  ServiceBase::~ServiceBase((ServiceBase *)&off_1800130A0);
}

```

## disassembly

```asm
0x18000b040  sub     rsp, 28h
0x18000b044  mov     rcx, cs:qword_180013160
0x18000b04b  test    rcx, rcx
0x18000b04e  jz      short loc_18000B05C
0x18000b050  mov     rax, [rcx]
0x18000b053  mov     rax, [rax+10h]
0x18000b057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b05c  lea     rcx, off_1800130A0; this
0x18000b063  add     rsp, 28h
0x18000b067  jmp     ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
```
