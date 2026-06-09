# CMMPullPin::ThreadProc(void)

- ea: `0x18000ee80`
- end: `0x18000eefb`
- name: `?ThreadProc@CMMPullPin@@MEAAKXZ`
- size: `123`
- prototype: `unsigned int __fastcall(CMMPullPin *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800071e4`
- `0x18000e55c`
- `0x18000e938`
- `0x18000ee80`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000ee90`
- `KERNEL32!WaitForSingleObject` at `0x18000ee90`

## pseudocode

```c
__int64 __fastcall CMMPullPin::ThreadProc(HANDLE *this)
{
  unsigned int v2; // edx
  int v3; // ecx
  int v4; // ecx

  while ( 1 )
  {
    WaitForSingleObject(this[1], 0xFFFFFFFF);
    v3 = *((_DWORD *)this + 6);
    if ( v3 )
      break;
    CAMThread::Reply((CAMThread *)this, v2);
LABEL_7:
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)this[15] + 72LL))(this[15]);
    CMMPullPin::CleanupCancelled((CMMPullPin *)this);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)this[15] + 80LL))(this[15]);
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    CAMThread::Reply((CAMThread *)this, v2);
    CMMPullPin::Process((CMMPullPin *)this);
    goto LABEL_7;
  }
  if ( v4 != 1 )
    goto LABEL_7;
  CAMThread::Reply((CAMThread *)this, v2);
  return 0;
}

```

## disassembly

```asm
0x18000ee80  push    rbx
0x18000ee82  sub     rsp, 20h
0x18000ee86  mov     rbx, rcx
0x18000ee89  mov     rcx, [rbx+8]; hHandle
0x18000ee8d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ee90  call    cs:__imp_WaitForSingleObject
0x18000ee96  mov     ecx, [rbx+18h]
0x18000ee99  test    ecx, ecx
0x18000ee9b  jz      short loc_18000EEC9
0x18000ee9d  sub     ecx, 1
0x18000eea0  jz      short loc_18000EEB7
0x18000eea2  cmp     ecx, 1
0x18000eea5  jnz     short loc_18000EED1
0x18000eea7  mov     rcx, rbx; this
0x18000eeaa  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18000eeaf  xor     eax, eax
0x18000eeb1  add     rsp, 20h
0x18000eeb5  pop     rbx
0x18000eeb6  retn
0x18000eeb7  mov     rcx, rbx; this
0x18000eeba  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18000eebf  mov     rcx, rbx; this
0x18000eec2  call    ?Process@CMMPullPin@@IEAAXXZ; CMMPullPin::Process(void)
0x18000eec7  jmp     short loc_18000EED1
0x18000eec9  mov     rcx, rbx; this
0x18000eecc  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18000eed1  mov     rcx, [rbx+78h]
0x18000eed5  mov     rax, [rcx]
0x18000eed8  mov     rax, [rax+48h]
0x18000eedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee1  mov     rcx, rbx; this
0x18000eee4  call    ?CleanupCancelled@CMMPullPin@@IEAAXXZ; CMMPullPin::CleanupCancelled(void)
0x18000eee9  mov     rcx, [rbx+78h]
0x18000eeed  mov     rax, [rcx]
0x18000eef0  mov     rax, [rax+50h]
0x18000eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef9  jmp     short loc_18000EE89
```
