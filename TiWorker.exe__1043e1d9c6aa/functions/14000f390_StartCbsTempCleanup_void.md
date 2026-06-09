# StartCbsTempCleanup(void *)

- ea: `0x14000f390`
- end: `0x14000f420`
- name: `?StartCbsTempCleanup@@YAPEAXPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(void *lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007228`

## callees

- `0x1400064e8`
- `0x140006d44`
- `0x14000e05c`
- `0x14000f390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f3db`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000f3be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000f3be`

## string_xrefs

- `0x14000f3ed`: `Failed to create CbsTemp cleanup thread.`

## pseudocode

```c
__int64 __fastcall StartCbsTempCleanup(void *lpParameter)
{
  HANDLE Thread; // rax
  __int64 v2; // rbx
  signed int LastError; // eax
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CbsTempDirectoryWorkerThreadProc, lpParameter, 0, 0);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &v5,
    Thread);
  v2 = v5;
  if ( v5 )
  {
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)LastError, "Failed to create CbsTemp cleanup thread.");
    v2 = 0;
  }
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v5);
  return v2;
}

```

## disassembly

```asm
0x14000f390  push    rbx
0x14000f392  sub     rsp, 30h
0x14000f396  mov     r9, rcx; lpParameter
0x14000f399  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14000f3a2  xor     ecx, ecx; lpThreadAttributes
0x14000f3a4  mov     [rsp+38h+arg_8], 0
0x14000f3ad  lea     r8, ?CbsTempDirectoryWorkerThreadProc@@YAKPEAX@Z; lpStartAddress
0x14000f3b4  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000f3bc  xor     edx, edx; dwStackSize
0x14000f3be  call    cs:__imp_CreateThread
0x14000f3c4  mov     rdx, rax
0x14000f3c7  lea     rcx, [rsp+38h+arg_8]
0x14000f3cc  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x14000f3d1  mov     rbx, [rsp+38h+arg_8]
0x14000f3d6  test    rbx, rbx
0x14000f3d9  jnz     short loc_14000F404
0x14000f3db  call    cs:__imp_GetLastError
0x14000f3e1  test    eax, eax
0x14000f3e3  jle     short loc_14000F3ED
0x14000f3e5  movzx   eax, ax
0x14000f3e8  or      eax, 80070000h
0x14000f3ed  lea     r8, aFailedToCreate_8; "Failed to create CbsTemp cleanup thread"...
0x14000f3f4  mov     edx, eax
0x14000f3f6  mov     ecx, 1
0x14000f3fb  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x14000f400  xor     ebx, ebx
0x14000f402  jmp     short loc_14000F40D
0x14000f404  mov     [rsp+38h+arg_8], 0
0x14000f40d  lea     rcx, [rsp+38h+arg_8]
0x14000f412  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14000f417  mov     rax, rbx
0x14000f41a  add     rsp, 30h
0x14000f41e  pop     rbx
0x14000f41f  retn
```
