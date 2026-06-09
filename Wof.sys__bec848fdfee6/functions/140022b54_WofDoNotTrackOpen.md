# WofDoNotTrackOpen

- ea: `0x140022b54`
- end: `0x140022c1f`
- name: `WofDoNotTrackOpen`
- size: `203`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400331d0`

## callees

- `0x14000a914`
- `0x140022b54`
- `0x140036670`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022bef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022bef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022bbd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022bbd`
- `FLTMGR!FltGetStreamContext` at `0x140022b7e`
- `FLTMGR!FltGetStreamContext` at `0x140022b7e`
- `FLTMGR!FltReleaseContext` at `0x140022c00`
- `FLTMGR!FltReleaseContext` at `0x140022c00`

## pseudocode

```c
__int64 __fastcall WofDoNotTrackOpen(__int64 a1)
{
  struct _FILE_OBJECT *v1; // rdx
  char v3; // di
  NTSTATUS StreamContext; // eax
  PFLT_CONTEXT v5; // rdx
  int v6; // ebx
  PFLT_CONTEXT v7; // rcx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(struct _FILE_OBJECT **)(a1 + 32);
  Context = 0;
  v3 = 0;
  StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a1 + 24), v1, &Context);
  v5 = Context;
  v6 = StreamContext;
  if ( Context )
  {
    v6 = WofEnsureExtdFileContext(*(_QWORD *)Context);
    if ( v6 >= 0 )
    {
      WofEnsureExtdFileContext(*(_QWORD *)Context);
      ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
      v3 = 1;
    }
    v5 = Context;
  }
  WofMarkFileAsInflated(a1, v5);
  v7 = Context;
  if ( Context )
  {
    if ( v3 )
    {
      ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
      v7 = Context;
    }
    FltReleaseContext(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140022b54  mov     rax, rsp
0x140022b57  mov     [rax+10h], rbx
0x140022b5b  mov     [rax+18h], rsi
0x140022b5f  push    rdi
0x140022b60  sub     rsp, 20h
0x140022b64  mov     rdx, [rcx+20h]; FileObject
0x140022b68  lea     r8, [rax+8]; Context
0x140022b6c  mov     rsi, rcx
0x140022b6f  mov     qword ptr [rax+8], 0
0x140022b77  mov     rcx, [rcx+18h]; Instance
0x140022b7b  xor     dil, dil
0x140022b7e  call    cs:__imp_FltGetStreamContext
0x140022b85  nop     dword ptr [rax+rax+00h]
0x140022b8a  mov     rdx, [rsp+28h+Context]
0x140022b8f  mov     ebx, eax
0x140022b91  test    rdx, rdx
0x140022b94  jz      short loc_140022BD1
0x140022b96  mov     rcx, [rdx]
0x140022b99  call    WofEnsureExtdFileContext
0x140022b9e  mov     ebx, eax
0x140022ba0  test    eax, eax
0x140022ba2  js      short loc_140022BCC
0x140022ba4  mov     rcx, [rsp+28h+Context]
0x140022ba9  mov     rcx, [rcx]
0x140022bac  call    WofEnsureExtdFileContext
0x140022bb1  mov     rcx, [rsp+28h+Context]
0x140022bb6  mov     rcx, [rcx]
0x140022bb9  mov     rcx, [rcx+10h]; FastMutex
0x140022bbd  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022bc4  nop     dword ptr [rax+rax+00h]
0x140022bc9  mov     dil, 1
0x140022bcc  mov     rdx, [rsp+28h+Context]
0x140022bd1  mov     rcx, rsi
0x140022bd4  call    WofMarkFileAsInflated
0x140022bd9  mov     rcx, [rsp+28h+Context]
0x140022bde  test    rcx, rcx
0x140022be1  jz      short loc_140022C0C
0x140022be3  test    dil, dil
0x140022be6  jz      short loc_140022C00
0x140022be8  mov     rcx, [rcx]
0x140022beb  mov     rcx, [rcx+10h]; FastMutex
0x140022bef  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022bf6  nop     dword ptr [rax+rax+00h]
0x140022bfb  mov     rcx, [rsp+28h+Context]; Context
0x140022c00  call    cs:__imp_FltReleaseContext
0x140022c07  nop     dword ptr [rax+rax+00h]
0x140022c0c  mov     rsi, [rsp+28h+arg_10]
0x140022c11  mov     eax, ebx
0x140022c13  mov     rbx, [rsp+28h+arg_8]
0x140022c18  add     rsp, 20h
0x140022c1c  pop     rdi
0x140022c1d  retn
```
