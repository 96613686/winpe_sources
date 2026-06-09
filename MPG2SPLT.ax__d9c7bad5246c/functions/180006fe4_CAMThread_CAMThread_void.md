# CAMThread::~CAMThread(void)

- ea: `0x180006fe4`
- end: `0x18000704e`
- name: `??1CAMThread@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CAMThread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e4ec`
- `0x18001a7a8`

## callees

- `0x180006fe4`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180007002`
- `KERNEL32!WaitForSingleObject` at `0x180007002`
- `KERNEL32!CloseHandle` at `0x18000700b`
- `KERNEL32!CloseHandle` at `0x18000702e`
- `KERNEL32!CloseHandle` at `0x18000703d`
- `KERNEL32!CloseHandle` at `0x18000700b`
- `KERNEL32!CloseHandle` at `0x18000702e`
- `KERNEL32!CloseHandle` at `0x18000703d`
- `KERNEL32!DeleteCriticalSection` at `0x180007015`
- `KERNEL32!DeleteCriticalSection` at `0x18000701f`
- `KERNEL32!DeleteCriticalSection` at `0x180007015`
- `KERNEL32!DeleteCriticalSection` at `0x18000701f`

## pseudocode

```c
void __fastcall CAMThread::~CAMThread(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rdi
  HANDLE OwningThread; // rcx
  void *v4; // rcx

  v2 = (void *)_InterlockedExchange64((volatile __int64 *)&this->SpinCount, 0);
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(v2);
  }
  DeleteCriticalSection(this + 2);
  DeleteCriticalSection(this + 1);
  OwningThread = this->OwningThread;
  if ( OwningThread )
    CloseHandle(OwningThread);
  v4 = *(void **)&this->LockCount;
  if ( v4 )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x180006fe4  mov     [rsp+arg_0], rbx
0x180006fe9  push    rdi
0x180006fea  sub     rsp, 20h
0x180006fee  xor     edi, edi
0x180006ff0  mov     rbx, rcx
0x180006ff3  xchg    rdi, [rcx+20h]
0x180006ff7  test    rdi, rdi
0x180006ffa  jz      short loc_180007011
0x180006ffc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006fff  mov     rcx, rdi; hHandle
0x180007002  call    cs:__imp_WaitForSingleObject
0x180007008  mov     rcx, rdi; hObject
0x18000700b  call    cs:__imp_CloseHandle
0x180007011  lea     rcx, [rbx+50h]; lpCriticalSection
0x180007015  call    cs:__imp_DeleteCriticalSection
0x18000701b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000701f  call    cs:__imp_DeleteCriticalSection
0x180007025  mov     rcx, [rbx+10h]; hObject
0x180007029  test    rcx, rcx
0x18000702c  jz      short loc_180007034
0x18000702e  call    cs:__imp_CloseHandle
0x180007034  mov     rcx, [rbx+8]; hObject
0x180007038  test    rcx, rcx
0x18000703b  jz      short loc_180007043
0x18000703d  call    cs:__imp_CloseHandle
0x180007043  mov     rbx, [rsp+28h+arg_0]
0x180007048  add     rsp, 20h
0x18000704c  pop     rdi
0x18000704d  retn
```
