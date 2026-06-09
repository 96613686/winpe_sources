# AsyncPipe::WriteCompletedStatic(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x14000dee0`
- end: `0x14000dfbe`
- name: `?WriteCompletedStatic@AsyncPipe@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `222`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000dee0`
- `0x14000e1b4`
- `0x14000e4cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000df4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000df4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000deff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000deff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000df91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000df91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df5f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000df24`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14000df24`

## pseudocode

```c
void __fastcall AsyncPipe::WriteCompletedStatic(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  void *v6; // rcx
  DWORD LastError; // eax
  const char *v8; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp+10h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(Context + 208);
  NumberOfBytesTransferred = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 208));
  if ( *((_DWORD *)Context + 63) == 997 )
  {
    if ( GetOverlappedResult(*((HANDLE *)Context + 3), (LPOVERLAPPED)(Context + 136), &NumberOfBytesTransferred, 0) )
      *((_DWORD *)Context + 63) = 0;
    else
      *((_DWORD *)Context + 63) = GetLastError();
  }
  CloseThreadpoolWait(*((PTP_WAIT *)Context + 12));
  v6 = (void *)*((_QWORD *)Context + 20);
  *((_QWORD *)Context + 12) = 0;
  if ( !CloseHandle(v6) )
  {
    LastError = GetLastError();
    __FatalError(v8, 550, "CloseHandle", LastError);
  }
  *((_QWORD *)Context + 20) = 0;
  LeaveCriticalSection(v4);
  Synchronizer::EnqueueEvent(*((Synchronizer **)Context + 1), (struct SynchronizedObject *)Context, 6u, 0, 0);
}

```

## disassembly

```asm
0x14000dee0  mov     [rsp+arg_0], rbx
0x14000dee5  push    rdi
0x14000dee6  sub     rsp, 30h
0x14000deea  lea     rdi, [rdx+0D0h]
0x14000def1  mov     [rsp+38h+NumberOfBytesTransferred], 0
0x14000def9  mov     rcx, rdi; lpCriticalSection
0x14000defc  mov     rbx, rdx
0x14000deff  call    cs:__imp_EnterCriticalSection
0x14000df05  cmp     dword ptr [rbx+0FCh], 3E5h
0x14000df0f  jnz     short loc_14000DF46
0x14000df11  mov     rcx, [rbx+18h]; hFile
0x14000df15  lea     rdx, [rbx+88h]; lpOverlapped
0x14000df1c  xor     r9d, r9d; bWait
0x14000df1f  lea     r8, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14000df24  call    cs:__imp_GetOverlappedResult
0x14000df2a  test    eax, eax
0x14000df2c  jz      short loc_14000DF3A
0x14000df2e  mov     dword ptr [rbx+0FCh], 0
0x14000df38  jmp     short loc_14000DF46
0x14000df3a  call    cs:__imp_GetLastError
0x14000df40  mov     [rbx+0FCh], eax
0x14000df46  mov     rcx, [rbx+60h]; pwa
0x14000df4a  call    cs:__imp_CloseThreadpoolWait
0x14000df50  mov     rcx, [rbx+0A0h]; hObject
0x14000df57  mov     qword ptr [rbx+60h], 0
0x14000df5f  call    cs:__imp_CloseHandle
0x14000df65  test    eax, eax
0x14000df67  jnz     short loc_14000DF83
0x14000df69  call    cs:__imp_GetLastError
0x14000df6f  lea     r8, aClosehandle; "CloseHandle"
0x14000df76  mov     edx, 226h; unsigned int
0x14000df7b  mov     r9d, eax; unsigned int
0x14000df7e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000df83  mov     rcx, rdi; lpCriticalSection
0x14000df86  mov     qword ptr [rbx+0A0h], 0
0x14000df91  call    cs:__imp_LeaveCriticalSection
0x14000df97  mov     rcx, [rbx+8]; this
0x14000df9b  xor     r9d, r9d; void *
0x14000df9e  mov     rdx, rbx; struct SynchronizedObject *
0x14000dfa1  mov     [rsp+38h+var_18], 0; void *
0x14000dfaa  lea     r8d, [r9+6]; int
0x14000dfae  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x14000dfb3  mov     rbx, [rsp+38h+arg_0]
0x14000dfb8  add     rsp, 30h
0x14000dfbc  pop     rdi
0x14000dfbd  retn
```
