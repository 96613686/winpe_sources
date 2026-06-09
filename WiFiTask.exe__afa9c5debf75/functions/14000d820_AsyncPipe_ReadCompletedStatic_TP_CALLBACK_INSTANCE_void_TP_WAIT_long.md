# AsyncPipe::ReadCompletedStatic(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x14000d820`
- end: `0x14000d8ff`
- name: `?ReadCompletedStatic@AsyncPipe@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `223`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d820`
- `0x14000e1b4`
- `0x14000e4cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000d881`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000d881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d8c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d896`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000d85b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000d85b`

## pseudocode

```c
void __fastcall AsyncPipe::ReadCompletedStatic(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  void *v6; // rcx
  DWORD LastError; // eax
  const char *v8; // rcx
  unsigned int v9; // r8d

  v4 = (struct _RTL_CRITICAL_SECTION *)(Context + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 168));
  if ( *((_DWORD *)Context + 62) == 997 )
  {
    if ( GetOverlappedResult(*((HANDLE *)Context + 3), (LPOVERLAPPED)(Context + 104), (LPDWORD)Context + 64, 0) )
      *((_DWORD *)Context + 62) = 0;
    else
      *((_DWORD *)Context + 62) = GetLastError();
  }
  CloseThreadpoolWait(*((PTP_WAIT *)Context + 11));
  v6 = (void *)*((_QWORD *)Context + 16);
  *((_QWORD *)Context + 11) = 0;
  if ( !CloseHandle(v6) )
  {
    LastError = GetLastError();
    __FatalError(v8, 399, "CloseHandle", LastError);
  }
  *((_QWORD *)Context + 16) = 0;
  LeaveCriticalSection(v4);
  v9 = 4;
  if ( !*((_QWORD *)Context + 5) )
    v9 = 5;
  Synchronizer::EnqueueEvent(*((Synchronizer **)Context + 1), (struct SynchronizedObject *)Context, v9, 0, 0);
}

```

## disassembly

```asm
0x14000d820  mov     [rsp+arg_0], rbx
0x14000d825  push    rdi
0x14000d826  sub     rsp, 30h
0x14000d82a  lea     rdi, [rdx+0A8h]
0x14000d831  mov     rbx, rdx
0x14000d834  mov     rcx, rdi; lpCriticalSection
0x14000d837  call    cs:__imp_EnterCriticalSection
0x14000d83d  cmp     dword ptr [rbx+0F8h], 3E5h
0x14000d847  jnz     short loc_14000D87D
0x14000d849  mov     rcx, [rbx+18h]; hFile
0x14000d84d  lea     r8, [rbx+100h]; lpNumberOfBytesTransferred
0x14000d854  lea     rdx, [rbx+68h]; lpOverlapped
0x14000d858  xor     r9d, r9d; bWait
0x14000d85b  call    cs:__imp_GetOverlappedResult
0x14000d861  test    eax, eax
0x14000d863  jz      short loc_14000D871
0x14000d865  mov     dword ptr [rbx+0F8h], 0
0x14000d86f  jmp     short loc_14000D87D
0x14000d871  call    cs:__imp_GetLastError
0x14000d877  mov     [rbx+0F8h], eax
0x14000d87d  mov     rcx, [rbx+58h]; pwa
0x14000d881  call    cs:__imp_CloseThreadpoolWait
0x14000d887  mov     rcx, [rbx+80h]; hObject
0x14000d88e  mov     qword ptr [rbx+58h], 0
0x14000d896  call    cs:__imp_CloseHandle
0x14000d89c  test    eax, eax
0x14000d89e  jnz     short loc_14000D8BA
0x14000d8a0  call    cs:__imp_GetLastError
0x14000d8a6  lea     r8, aClosehandle; "CloseHandle"
0x14000d8ad  mov     edx, 18Fh; unsigned int
0x14000d8b2  mov     r9d, eax; unsigned int
0x14000d8b5  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d8ba  mov     rcx, rdi; lpCriticalSection
0x14000d8bd  mov     qword ptr [rbx+80h], 0
0x14000d8c8  call    cs:__imp_LeaveCriticalSection
0x14000d8ce  mov     rcx, [rbx+8]; this
0x14000d8d2  xor     r9d, r9d; void *
0x14000d8d5  mov     rdx, rbx; struct SynchronizedObject *
0x14000d8d8  mov     [rsp+38h+var_18], 0; void *
0x14000d8e1  lea     r8d, [r9+4]
0x14000d8e5  cmp     [rbx+28h], r9
0x14000d8e9  jnz     short loc_14000D8EF
0x14000d8eb  lea     r8d, [r9+5]; int
0x14000d8ef  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x14000d8f4  mov     rbx, [rsp+38h+arg_0]
0x14000d8f9  add     rsp, 30h
0x14000d8fd  pop     rdi
0x14000d8fe  retn
```
