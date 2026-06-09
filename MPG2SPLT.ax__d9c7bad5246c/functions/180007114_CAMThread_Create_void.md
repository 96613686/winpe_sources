# CAMThread::Create(void)

- ea: `0x180007114`
- end: `0x18000718b`
- name: `?Create@CAMThread@@QEAAHXZ`
- size: `119`
- prototype: `__int64 __fastcall(CAMThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ed0c`
- `0x18001bc80`

## callees

- `0x180007114`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18000715d`
- `KERNEL32!CreateThread` at `0x18000715d`
- `KERNEL32!LeaveCriticalSection` at `0x180007178`
- `KERNEL32!LeaveCriticalSection` at `0x180007178`
- `KERNEL32!EnterCriticalSection` at `0x180007130`
- `KERNEL32!EnterCriticalSection` at `0x180007130`

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
0x180007114  mov     [rsp+arg_8], rbx
0x180007119  push    rdi
0x18000711a  sub     rsp, 30h
0x18000711e  lea     rdi, [rcx+28h]
0x180007122  mov     [rsp+38h+ThreadId], 0
0x18000712a  mov     rbx, rcx
0x18000712d  mov     rcx, rdi; lpCriticalSection
0x180007130  call    cs:__imp_EnterCriticalSection
0x180007136  cmp     qword ptr [rbx+20h], 0
0x18000713b  jnz     short loc_180007173
0x18000713d  lea     rax, [rsp+38h+ThreadId]
0x180007142  mov     r9, rbx; lpParameter
0x180007145  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000714a  lea     r8, ?InitialThreadProc@CAMThread@@SAKPEAX@Z; lpStartAddress
0x180007151  xor     edx, edx; dwStackSize
0x180007153  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000715b  xor     ecx, ecx; lpThreadAttributes
0x18000715d  call    cs:__imp_CreateThread
0x180007163  mov     [rbx+20h], rax
0x180007167  test    rax, rax
0x18000716a  jz      short loc_180007173
0x18000716c  mov     ebx, 1
0x180007171  jmp     short loc_180007175
0x180007173  xor     ebx, ebx
0x180007175  mov     rcx, rdi; lpCriticalSection
0x180007178  call    cs:__imp_LeaveCriticalSection
0x18000717e  mov     eax, ebx
0x180007180  mov     rbx, [rsp+38h+arg_8]
0x180007185  add     rsp, 30h
0x180007189  pop     rdi
0x18000718a  retn
```
