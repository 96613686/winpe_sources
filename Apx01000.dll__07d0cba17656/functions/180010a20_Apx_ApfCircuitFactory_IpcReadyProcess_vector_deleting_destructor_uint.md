# Apx::ApfCircuitFactory_IpcReadyProcess::`vector deleting destructor'(uint)

- ea: `0x180010a20`
- end: `0x180010a7b`
- name: `??_EApfCircuitFactory_IpcReadyProcess@Apx@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Apx::ApfCircuitFactory_IpcReadyProcess *__fastcall(Apx::ApfCircuitFactory_IpcReadyProcess *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x180010a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010a42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010a42`

## pseudocode

```c
Apx::ApfCircuitFactory_IpcReadyProcess *__fastcall Apx::ApfCircuitFactory_IpcReadyProcess::`vector deleting destructor'(
        Apx::ApfCircuitFactory_IpcReadyProcess *this,
        char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &Apx::ApfCircuitFactory_IpcReadyProcess::`vftable';
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    SetEvent(v4);
    *((_QWORD *)this + 3) = 0;
  }
  *(_QWORD *)this = &Apx::ApfWorkItemBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180010a20  mov     [rsp+arg_0], rbx
0x180010a25  push    rdi
0x180010a26  sub     rsp, 20h
0x180010a2a  lea     rax, ??_7ApfCircuitFactory_IpcReadyProcess@Apx@@6B@; const Apx::ApfCircuitFactory_IpcReadyProcess::`vftable'
0x180010a31  mov     rbx, rcx
0x180010a34  mov     [rcx], rax
0x180010a37  mov     edi, edx
0x180010a39  mov     rcx, [rcx+18h]; hEvent
0x180010a3d  test    rcx, rcx
0x180010a40  jz      short loc_180010A50
0x180010a42  call    cs:__imp_SetEvent
0x180010a48  mov     qword ptr [rbx+18h], 0
0x180010a50  lea     rax, ??_7ApfWorkItemBase@Apx@@6B@; const Apx::ApfWorkItemBase::`vftable'
0x180010a57  mov     [rbx], rax
0x180010a5a  test    dil, 1
0x180010a5e  jz      short loc_180010A6D
0x180010a60  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180010a65  mov     rcx, rbx; void *
0x180010a68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010a6d  mov     rax, rbx
0x180010a70  mov     rbx, [rsp+28h+arg_0]
0x180010a75  add     rsp, 20h
0x180010a79  pop     rdi
0x180010a7a  retn
```
