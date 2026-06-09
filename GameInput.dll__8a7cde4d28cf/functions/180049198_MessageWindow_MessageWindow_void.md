# MessageWindow::~MessageWindow(void)

- ea: `0x180049198`
- end: `0x18004920a`
- name: `??1MessageWindow@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(MessageWindow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180048f88`
- `0x1800495e4`

## callees

- `0x180049198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800491d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800491d5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800491a9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800491a9`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800491e8`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800491e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800491f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800491f7`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x1800491c1`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x1800491c1`

## pseudocode

```c
void __fastcall MessageWindow::~MessageWindow(HANDLE *this)
{
  HANDLE v2; // rcx
  DWORD ThreadId; // eax

  v2 = *this;
  if ( v2 )
  {
    ThreadId = GetThreadId(v2);
    PostThreadMessageW(ThreadId, 0x12u, 0, 0);
    if ( WaitForSingleObject(*this, 0x7D0u) )
      SuspendThread(*this);
    CloseHandle(*this);
  }
}

```

## disassembly

```asm
0x180049198  push    rbx
0x18004919a  sub     rsp, 20h
0x18004919e  mov     rbx, rcx
0x1800491a1  mov     rcx, [rcx]; Thread
0x1800491a4  test    rcx, rcx
0x1800491a7  jz      short loc_180049203
0x1800491a9  call    cs:__imp_GetThreadId
0x1800491b0  nop     dword ptr [rax+rax+00h]
0x1800491b5  xor     r9d, r9d; lParam
0x1800491b8  xor     r8d, r8d; wParam
0x1800491bb  mov     ecx, eax; idThread
0x1800491bd  lea     edx, [r9+12h]; Msg
0x1800491c1  call    cs:__imp_PostThreadMessageW
0x1800491c8  nop     dword ptr [rax+rax+00h]
0x1800491cd  mov     rcx, [rbx]; hHandle
0x1800491d0  mov     edx, 7D0h; dwMilliseconds
0x1800491d5  call    cs:__imp_WaitForSingleObject
0x1800491dc  nop     dword ptr [rax+rax+00h]
0x1800491e1  test    eax, eax
0x1800491e3  jz      short loc_1800491F4
0x1800491e5  mov     rcx, [rbx]; hThread
0x1800491e8  call    cs:__imp_SuspendThread
0x1800491ef  nop     dword ptr [rax+rax+00h]
0x1800491f4  mov     rcx, [rbx]; hObject
0x1800491f7  call    cs:__imp_CloseHandle
0x1800491fe  nop     dword ptr [rax+rax+00h]
0x180049203  add     rsp, 20h
0x180049207  pop     rbx
0x180049208  retn
```
