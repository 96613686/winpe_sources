# CWwanDataExecutorState::DeleteWwanTimer(_WwanTimerSpecific *)

- ea: `0x18003b648`
- end: `0x18003b6d9`
- name: `?DeleteWwanTimer@CWwanDataExecutorState@@AEAAXPEAU_WwanTimerSpecific@@@Z`
- size: `145`
- prototype: `void __fastcall(CWwanDataExecutorState *__hidden this, struct _WwanTimerSpecific *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003ab3c`

## callees

- `0x180014f1c`
- `0x18003b648`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x18003b67d`
- `MobileNetworking!StopTimer` at `0x18003b67d`
- `MobileNetworking!DeleteReadWriteLock` at `0x18003b6b7`
- `MobileNetworking!DeleteReadWriteLock` at `0x18003b6b7`
- `MobileNetworking!AcquireWriteLock` at `0x18003b670`
- `MobileNetworking!AcquireWriteLock` at `0x18003b670`
- `MobileNetworking!ReleaseWriteLock` at `0x18003b693`
- `MobileNetworking!ReleaseWriteLock` at `0x18003b693`
- `MobileNetworking!DeleteTimer` at `0x18003b6ae`
- `MobileNetworking!DeleteTimer` at `0x18003b6ae`

## string_xrefs

- `0x18003b660`: `CWwanDataExecutorState::DeleteWwanTimer`
- `0x18003b699`: `Timer Stop Completed`
- `0x18003b6bd`: `Timer Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanDataExecutorState::DeleteWwanTimer(CWwanDataExecutorState *this, struct _WwanTimerSpecific *a2)
{
  if ( *((_DWORD *)a2 + 28) )
  {
    AcquireWriteLock(*((_QWORD *)a2 + 13), a2, "CWwanDataExecutorState::DeleteWwanTimer", 245);
    StopTimer(*((_QWORD *)a2 + 13), "CWwanDataExecutorState::DeleteWwanTimer");
    ReleaseWriteLock(*((_QWORD *)a2 + 13), a2, "CWwanDataExecutorState::DeleteWwanTimer", 247);
    WwanLog::Info("CWwanDataExecutorState::DeleteWwanTimer", 0, L"Timer Stop Completed");
    DeleteTimer(*((_QWORD *)a2 + 13));
    DeleteReadWriteLock(a2);
    WwanLog::Info("CWwanDataExecutorState::DeleteWwanTimer", 0, L"Timer Deinitialization Completed");
  }
}

```

## disassembly

```asm
0x18003b648  mov     [rsp+arg_0], rbx
0x18003b64d  push    rdi
0x18003b64e  sub     rsp, 20h
0x18003b652  mov     eax, [rdx+70h]
0x18003b655  mov     rbx, rdx
0x18003b658  test    eax, eax
0x18003b65a  jz      short loc_18003B6CE
0x18003b65c  mov     rcx, [rdx+68h]
0x18003b660  lea     rdi, aCwwandataexecu_59; "CWwanDataExecutorState::DeleteWwanTimer"
0x18003b667  mov     r8, rdi
0x18003b66a  mov     r9d, 0F5h
0x18003b670  call    cs:__imp_AcquireWriteLock
0x18003b676  mov     rcx, [rbx+68h]
0x18003b67a  mov     rdx, rdi
0x18003b67d  call    cs:__imp_StopTimer
0x18003b683  mov     rcx, [rbx+68h]
0x18003b687  mov     r9d, 0F7h
0x18003b68d  mov     r8, rdi
0x18003b690  mov     rdx, rbx
0x18003b693  call    cs:__imp_ReleaseWriteLock
0x18003b699  lea     r8, aTimerStopCompl; "Timer Stop Completed"
0x18003b6a0  xor     edx, edx; struct _GUID *
0x18003b6a2  mov     rcx, rdi; char *
0x18003b6a5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003b6aa  mov     rcx, [rbx+68h]
0x18003b6ae  call    cs:__imp_DeleteTimer
0x18003b6b4  mov     rcx, rbx
0x18003b6b7  call    cs:__imp_DeleteReadWriteLock
0x18003b6bd  lea     r8, aTimerDeinitial_0; "Timer Deinitialization Completed"
0x18003b6c4  xor     edx, edx; struct _GUID *
0x18003b6c6  mov     rcx, rdi; char *
0x18003b6c9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003b6ce  mov     rbx, [rsp+28h+arg_0]
0x18003b6d3  add     rsp, 20h
0x18003b6d7  pop     rdi
0x18003b6d8  retn
```
