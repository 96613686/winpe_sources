# CSessionConfigTaskThread::~CSessionConfigTaskThread(void)

- ea: `0x18002daf8`
- end: `0x18002db82`
- name: `??1CSessionConfigTaskThread@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(const char **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002c868`

## callees

- `0x180003f30`
- `0x18002daf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002db76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002db76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002db33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002db33`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002db0a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002db55`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002db0a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002db55`

## string_xrefs

- `0x18002db13`: `Waiting for %s thread to stop:  id = 0x%X  obj = 0x%X`
- `0x18002db40`: `thread failed to stop with error %u`
- `0x18002db5e`: `thread stopped:  id = 0x%X  obj = 0x%X`

## pseudocode

```c
void __fastcall CSessionConfigTaskThread::~CSessionConfigTaskThread(const char **this)
{
  char *v2; // rcx
  DWORD ThreadId; // eax
  DWORD v4; // eax
  DWORD v5; // eax

  v2 = (char *)this[1];
  if ( v2 )
  {
    ThreadId = GetThreadId(v2);
    _DbgPrintMessage(1, "Waiting for %s thread to stop:  id = 0x%X  obj = 0x%X", *this, ThreadId, (_DWORD)this);
    v4 = WaitForSingleObject((HANDLE)this[1], 0xFFFFFFFF);
    if ( v4 )
      _DbgPrintMessage(1, "thread failed to stop with error %u", v4);
    v5 = GetThreadId((HANDLE)this[1]);
    _DbgPrintMessage(1, "thread stopped:  id = 0x%X  obj = 0x%X", v5, (_DWORD)this);
    CloseHandle((HANDLE)this[1]);
  }
}

```

## disassembly

```asm
0x18002daf8  push    rbx
0x18002dafa  sub     rsp, 30h
0x18002dafe  mov     rbx, rcx
0x18002db01  mov     rcx, [rcx+8]; Thread
0x18002db05  test    rcx, rcx
0x18002db08  jz      short loc_18002DB7C
0x18002db0a  call    cs:__imp_GetThreadId
0x18002db10  mov     r8, [rbx]
0x18002db13  lea     rdx, aWaitingForSThr; "Waiting for %s thread to stop:  id = 0x"...
0x18002db1a  mov     r9d, eax
0x18002db1d  mov     [rsp+38h+var_18], rbx
0x18002db22  mov     ecx, 1; int
0x18002db27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db2c  mov     rcx, [rbx+8]; hHandle
0x18002db30  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002db33  call    cs:__imp_WaitForSingleObject
0x18002db39  test    eax, eax
0x18002db3b  jz      short loc_18002DB51
0x18002db3d  mov     r8d, eax
0x18002db40  lea     rdx, aThreadFailedTo; "thread failed to stop with error %u"
0x18002db47  mov     ecx, 1; int
0x18002db4c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db51  mov     rcx, [rbx+8]; Thread
0x18002db55  call    cs:__imp_GetThreadId
0x18002db5b  mov     r9, rbx
0x18002db5e  lea     rdx, aThreadStoppedI; "thread stopped:  id = 0x%X  obj = 0x%X"
0x18002db65  mov     r8d, eax
0x18002db68  mov     ecx, 1; int
0x18002db6d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002db72  mov     rcx, [rbx+8]; hObject
0x18002db76  call    cs:__imp_CloseHandle
0x18002db7c  add     rsp, 30h
0x18002db80  pop     rbx
0x18002db81  retn
```
