# CThreadSmartWait::CThreadSmartWait(ulong)

- ea: `0x14002be14`
- end: `0x14002be65`
- name: `??0CThreadSmartWait@@QEAA@K@Z`
- size: `81`
- prototype: `CThreadSmartWait *__fastcall(CThreadSmartWait *this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14002c8dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002be38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002be38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002be2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002be2f`

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
0x14002be14  push    rbx
0x14002be16  sub     rsp, 20h
0x14002be1a  mov     qword ptr [rcx], 0
0x14002be21  mov     rbx, rcx
0x14002be24  mov     qword ptr [rcx+8], 0
0x14002be2c  mov     [rcx+10h], edx
0x14002be2f  call    cs:__imp_GetTickCount
0x14002be35  mov     [rbx+14h], eax
0x14002be38  call    cs:__imp_GetCurrentThreadId
0x14002be3e  mov     [rbx+18h], eax
0x14002be41  mov     rax, rbx
0x14002be44  mov     byte ptr [rbx+1Ch], 0
0x14002be48  mov     dword ptr [rbx+20h], 0
0x14002be4f  mov     qword ptr [rbx+28h], 0
0x14002be57  mov     qword ptr [rbx+30h], 0
0x14002be5f  add     rsp, 20h
0x14002be63  pop     rbx
0x14002be64  retn
```
