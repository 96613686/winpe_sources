# TimerBrokerTimeChange(__int64)

- ea: `0x18000cec0`
- end: `0x18000cf32`
- name: `?TimerBrokerTimeChange@@YAX_J@Z`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000ce00`

## callees

- `0x18000cec0`
- `0x180012df4`
- `0x1800131e4`

## import_xrefs

- `ntdll!TpReleaseWork` at `0x18000cf21`
- `ntdll!TpReleaseWork` at `0x18000cf21`
- `ntdll!TpPostWork` at `0x18000cf16`
- `ntdll!TpPostWork` at `0x18000cf16`
- `ntdll!TpAllocWork` at `0x18000cef8`
- `ntdll!TpAllocWork` at `0x18000cef8`

## pseudocode

```c
void __fastcall TimerBrokerTimeChange(__int64 a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = operator new(8u);
  *v2 = a1;
  if ( (int)TpAllocWork(&v3, TimerBrokerTimeChangeCallback, v2, 0) >= 0 )
  {
    TpPostWork(v3);
    TpReleaseWork(v3);
  }
  else
  {
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000cec0  mov     [rsp+arg_0], rbx
0x18000cec5  push    rdi
0x18000cec6  sub     rsp, 20h
0x18000ceca  mov     rbx, rcx
0x18000cecd  mov     [rsp+28h+arg_8], 0
0x18000ced6  mov     ecx, 8; Size
0x18000cedb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cee0  xor     r9d, r9d
0x18000cee3  lea     rdx, ?TimerBrokerTimeChangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; TimerBrokerTimeChangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18000ceea  mov     r8, rax
0x18000ceed  lea     rcx, [rsp+28h+arg_8]
0x18000cef2  mov     rdi, rax
0x18000cef5  mov     [rax], rbx
0x18000cef8  call    cs:__imp_TpAllocWork
0x18000cefe  test    eax, eax
0x18000cf00  jns     short loc_18000CF11
0x18000cf02  mov     edx, 8; unsigned __int64
0x18000cf07  mov     rcx, rdi; void *
0x18000cf0a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf0f  jmp     short loc_18000CF27
0x18000cf11  mov     rcx, [rsp+28h+arg_8]
0x18000cf16  call    cs:__imp_TpPostWork
0x18000cf1c  mov     rcx, [rsp+28h+arg_8]
0x18000cf21  call    cs:__imp_TpReleaseWork
0x18000cf27  mov     rbx, [rsp+28h+arg_0]
0x18000cf2c  add     rsp, 20h
0x18000cf30  pop     rdi
0x18000cf31  retn
```
