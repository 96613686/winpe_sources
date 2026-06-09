# CMp2PullPin::ThreadProc(void)

- ea: `0x18001bdf0`
- end: `0x18001be6b`
- name: `?ThreadProc@CMp2PullPin@@MEAAKXZ`
- size: `123`
- prototype: `unsigned int __fastcall(CMp2PullPin *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800071e4`
- `0x18000e55c`
- `0x18001b4f0`
- `0x18001bdf0`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001be00`
- `KERNEL32!WaitForSingleObject` at `0x18001be00`

## pseudocode

```c
__int64 __fastcall CMp2PullPin::ThreadProc(HANDLE *this)
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
    CMp2PullPin::Process((CMp2PullPin *)this);
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
0x18001bdf0  push    rbx
0x18001bdf2  sub     rsp, 20h
0x18001bdf6  mov     rbx, rcx
0x18001bdf9  mov     rcx, [rbx+8]; hHandle
0x18001bdfd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001be00  call    cs:__imp_WaitForSingleObject
0x18001be06  mov     ecx, [rbx+18h]
0x18001be09  test    ecx, ecx
0x18001be0b  jz      short loc_18001BE39
0x18001be0d  sub     ecx, 1
0x18001be10  jz      short loc_18001BE27
0x18001be12  cmp     ecx, 1
0x18001be15  jnz     short loc_18001BE41
0x18001be17  mov     rcx, rbx; this
0x18001be1a  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18001be1f  xor     eax, eax
0x18001be21  add     rsp, 20h
0x18001be25  pop     rbx
0x18001be26  retn
0x18001be27  mov     rcx, rbx; this
0x18001be2a  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18001be2f  mov     rcx, rbx; this
0x18001be32  call    ?Process@CMp2PullPin@@IEAAXXZ; CMp2PullPin::Process(void)
0x18001be37  jmp     short loc_18001BE41
0x18001be39  mov     rcx, rbx; this
0x18001be3c  call    ?Reply@CAMThread@@QEAAXK@Z; CAMThread::Reply(ulong)
0x18001be41  mov     rcx, [rbx+78h]
0x18001be45  mov     rax, [rcx]
0x18001be48  mov     rax, [rax+48h]
0x18001be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be51  mov     rcx, rbx; this
0x18001be54  call    ?CleanupCancelled@CMMPullPin@@IEAAXXZ; CMMPullPin::CleanupCancelled(void)
0x18001be59  mov     rcx, [rbx+78h]
0x18001be5d  mov     rax, [rcx]
0x18001be60  mov     rax, [rax+50h]
0x18001be64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be69  jmp     short loc_18001BDF9
```
