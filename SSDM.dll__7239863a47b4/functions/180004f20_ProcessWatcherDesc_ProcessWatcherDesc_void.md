# ProcessWatcherDesc::~ProcessWatcherDesc(void)

- ea: `0x180004f20`
- end: `0x180004f9e`
- name: `??1ProcessWatcherDesc@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(ProcessWatcherDesc *this, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046f4`
- `0x180004990`
- `0x180004e34`
- `0x180006810`
- `0x18000c1c0`
- `0x18000c334`

## callees

- `0x180004f20`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004f52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180004f52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180004f60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180004f60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180004f69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180004f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f3b`

## pseudocode

```c
void __fastcall ProcessWatcherDesc::~ProcessWatcherDesc(ProcessWatcherDesc *this, __int64 a2)
{
  char *v3; // rcx
  struct _TP_WAIT *v4; // rdi
  ProcessWatcherDesc *v5; // rcx

  v3 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v4 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 4), 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
  }
  v5 = (ProcessWatcherDesc *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    LOBYTE(a2) = v5 != this;
    (*(void (__fastcall **)(ProcessWatcherDesc *, __int64))(*(_QWORD *)v5 + 32LL))(v5, a2);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180004f20  mov     [rsp+arg_0], rbx
0x180004f25  push    rdi
0x180004f26  sub     rsp, 20h
0x180004f2a  mov     rbx, rcx
0x180004f2d  mov     rcx, [rcx+28h]; hObject
0x180004f31  lea     rax, [rcx-1]
0x180004f35  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004f39  ja      short loc_180004F41
0x180004f3b  call    cs:__imp_CloseHandle
0x180004f41  mov     rdi, [rbx+20h]
0x180004f45  test    rdi, rdi
0x180004f48  jz      short loc_180004F70
0x180004f4a  xor     r8d, r8d; pftTimeout
0x180004f4d  xor     edx, edx; h
0x180004f4f  mov     rcx, rdi; pwa
0x180004f52  call    cs:__imp_SetThreadpoolWait
0x180004f58  mov     edx, 1; fCancelPendingCallbacks
0x180004f5d  mov     rcx, rdi; pwa
0x180004f60  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180004f66  mov     rcx, rdi; pwa
0x180004f69  call    cs:__imp_CloseThreadpoolWait
0x180004f6f  nop
0x180004f70  mov     rcx, [rbx+18h]
0x180004f74  test    rcx, rcx
0x180004f77  jz      short loc_180004F93
0x180004f79  mov     rax, [rcx]
0x180004f7c  cmp     rcx, rbx
0x180004f7f  setnz   dl
0x180004f82  mov     rax, [rax+20h]
0x180004f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f8b  mov     qword ptr [rbx+18h], 0
0x180004f93  mov     rbx, [rsp+28h+arg_0]
0x180004f98  add     rsp, 20h
0x180004f9c  pop     rdi
0x180004f9d  retn
```
