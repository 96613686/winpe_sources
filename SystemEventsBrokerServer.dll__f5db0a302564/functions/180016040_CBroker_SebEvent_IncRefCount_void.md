# CBroker::SebEvent::IncRefCount(void)

- ea: `0x180016040`
- end: `0x180016085`
- name: `?IncRefCount@SebEvent@CBroker@@QEAAHXZ`
- size: `69`
- prototype: `__int64 __fastcall(CBroker::SebEvent *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006e00`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016057`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016057`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016072`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001605d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001605d`

## pseudocode

```c
__int64 __fastcall CBroker::SebEvent::IncRefCount(CBroker::SebEvent *this)
{
  char *v1; // rdi
  CBroker::SebEvent *v2; // rbx

  v1 = (char *)this + 240;
  v2 = this;
  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  LODWORD(v2) = ++*((_DWORD *)v2 + 63);
  RtlReleaseSRWLockExclusive(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016040  mov     [rsp+arg_0], rbx
0x180016045  push    rdi
0x180016046  sub     rsp, 20h
0x18001604a  lea     rdi, [rcx+0F0h]
0x180016051  mov     rbx, rcx
0x180016054  mov     rcx, rdi
0x180016057  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001605d  call    cs:__imp_GetCurrentThreadId
0x180016063  inc     dword ptr [rbx+0FCh]
0x180016069  mov     rcx, rdi
0x18001606c  mov     ebx, [rbx+0FCh]
0x180016072  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180016078  mov     eax, ebx
0x18001607a  mov     rbx, [rsp+28h+arg_0]
0x18001607f  add     rsp, 20h
0x180016083  pop     rdi
0x180016084  retn
```
