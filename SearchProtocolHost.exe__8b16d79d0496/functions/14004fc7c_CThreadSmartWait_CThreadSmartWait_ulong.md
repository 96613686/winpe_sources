# CThreadSmartWait::CThreadSmartWait(ulong)

- ea: `0x14004fc7c`
- end: `0x14004fccd`
- name: `??0CThreadSmartWait@@QEAA@K@Z`
- size: `81`
- prototype: `CThreadSmartWait *__fastcall(CThreadSmartWait *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140050880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004fca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004fca0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14004fc97`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14004fc97`

## pseudocode

```c
CThreadSmartWait *__fastcall CThreadSmartWait::CThreadSmartWait(CThreadSmartWait *this, int a2)
{
  CThreadSmartWait *result; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = a2;
  *((_DWORD *)this + 5) = GetTickCount();
  *((_DWORD *)this + 6) = GetCurrentThreadId();
  result = this;
  *((_BYTE *)this + 28) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x14004fc7c  push    rbx
0x14004fc7e  sub     rsp, 20h
0x14004fc82  mov     qword ptr [rcx], 0
0x14004fc89  mov     rbx, rcx
0x14004fc8c  mov     qword ptr [rcx+8], 0
0x14004fc94  mov     [rcx+10h], edx
0x14004fc97  call    cs:__imp_GetTickCount
0x14004fc9d  mov     [rbx+14h], eax
0x14004fca0  call    cs:__imp_GetCurrentThreadId
0x14004fca6  mov     [rbx+18h], eax
0x14004fca9  mov     rax, rbx
0x14004fcac  mov     byte ptr [rbx+1Ch], 0
0x14004fcb0  mov     dword ptr [rbx+20h], 0
0x14004fcb7  mov     qword ptr [rbx+28h], 0
0x14004fcbf  mov     qword ptr [rbx+30h], 0
0x14004fcc7  add     rsp, 20h
0x14004fccb  pop     rbx
0x14004fccc  retn
```
