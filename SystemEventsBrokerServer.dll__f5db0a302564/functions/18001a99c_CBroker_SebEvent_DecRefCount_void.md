# CBroker::SebEvent::DecRefCount(void)

- ea: `0x18001a99c`
- end: `0x18001a9e1`
- name: `?DecRefCount@SebEvent@CBroker@@QEAAHXZ`
- size: `69`
- prototype: `__int64 __fastcall(CBroker::SebEvent *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b3d0`
- `0x180014910`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a9b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a9b3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a9ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a9ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9b9`

## pseudocode

```c
__int64 __fastcall CBroker::SebEvent::DecRefCount(CBroker::SebEvent *this)
{
  char *v1; // rdi
  CBroker::SebEvent *v2; // rbx

  v1 = (char *)this + 240;
  v2 = this;
  RtlAcquireSRWLockExclusive((char *)this + 240);
  GetCurrentThreadId();
  LODWORD(v2) = --*((_DWORD *)v2 + 63);
  RtlReleaseSRWLockExclusive(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a99c  mov     [rsp+arg_0], rbx
0x18001a9a1  push    rdi
0x18001a9a2  sub     rsp, 20h
0x18001a9a6  lea     rdi, [rcx+0F0h]
0x18001a9ad  mov     rbx, rcx
0x18001a9b0  mov     rcx, rdi
0x18001a9b3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a9b9  call    cs:__imp_GetCurrentThreadId
0x18001a9bf  dec     dword ptr [rbx+0FCh]
0x18001a9c5  mov     rcx, rdi
0x18001a9c8  mov     ebx, [rbx+0FCh]
0x18001a9ce  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a9d4  mov     eax, ebx
0x18001a9d6  mov     rbx, [rsp+28h+arg_0]
0x18001a9db  add     rsp, 20h
0x18001a9df  pop     rdi
0x18001a9e0  retn
```
