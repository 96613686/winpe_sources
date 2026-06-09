# CAMThread::Create(void)

- ea: `0x1800c7038`
- end: `0x1800c70c2`
- name: `?Create@CAMThread@@QEAAHXZ`
- size: `138`
- prototype: `__int64 __fastcall(CAMThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b645c`
- `0x1800c7310`

## callees

- `0x1800c7038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c70a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c70a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c7054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c7054`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c7087`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c7087`

## pseudocode

```c
_BOOL8 __fastcall CAMThread::Create(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE v3; // rax
  BOOL v4; // ebx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = this + 1;
  ThreadId = 0;
  EnterCriticalSection(this + 1);
  v4 = 0;
  if ( !this->SpinCount )
  {
    v3 = CreateThread(0, 0, CAMThread::InitialThreadProc, this, 0, &ThreadId);
    this->SpinCount = (ULONG_PTR)v3;
    if ( v3 )
      v4 = 1;
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x1800c7038  mov     [rsp+arg_8], rbx
0x1800c703d  push    rdi
0x1800c703e  sub     rsp, 30h
0x1800c7042  lea     rdi, [rcx+28h]
0x1800c7046  mov     [rsp+38h+ThreadId], 0
0x1800c704e  mov     rbx, rcx
0x1800c7051  mov     rcx, rdi; lpCriticalSection
0x1800c7054  call    cs:__imp_EnterCriticalSection
0x1800c705b  nop     dword ptr [rax+rax+00h]
0x1800c7060  cmp     qword ptr [rbx+20h], 0
0x1800c7065  jnz     short loc_1800C70A3
0x1800c7067  lea     rax, [rsp+38h+ThreadId]
0x1800c706c  mov     r9, rbx; lpParameter
0x1800c706f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800c7074  lea     r8, ?InitialThreadProc@CAMThread@@SAKPEAX@Z; lpStartAddress
0x1800c707b  xor     edx, edx; dwStackSize
0x1800c707d  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800c7085  xor     ecx, ecx; lpThreadAttributes
0x1800c7087  call    cs:__imp_CreateThread
0x1800c708e  nop     dword ptr [rax+rax+00h]
0x1800c7093  mov     [rbx+20h], rax
0x1800c7097  test    rax, rax
0x1800c709a  jz      short loc_1800C70A3
0x1800c709c  mov     ebx, 1
0x1800c70a1  jmp     short loc_1800C70A5
0x1800c70a3  xor     ebx, ebx
0x1800c70a5  mov     rcx, rdi; lpCriticalSection
0x1800c70a8  call    cs:__imp_LeaveCriticalSection
0x1800c70af  nop     dword ptr [rax+rax+00h]
0x1800c70b4  mov     eax, ebx
0x1800c70b6  mov     rbx, [rsp+38h+arg_8]
0x1800c70bb  add     rsp, 30h
0x1800c70bf  pop     rdi
0x1800c70c0  retn
```
