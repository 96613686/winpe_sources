# AsyncPipe::StartWrite(void)

- ea: `0x14000dbbc`
- end: `0x14000dcfb`
- name: `?StartWrite@AsyncPipe@@AEAAXXZ`
- size: `319`
- prototype: `void __fastcall(char *pv)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000dd04`
- `0x14000ddf0`

## callees

- `0x14000dbbc`
- `0x14000e1b4`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000dc44`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000dc44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000dc7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000dc7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000dbf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000dbf1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000dcc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000dcc3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000dc03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000dc03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000dcf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dc53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dccd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000dc93`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000dc93`

## string_xrefs

- `0x14000dc1f`: `CreateEvent`
- `0x14000dc59`: `CreateThreadpoolWait`

## pseudocode

```c
void __fastcall AsyncPipe::StartWrite(char *pv)
{
  __int64 v1; // rax
  const void *v3; // rbp
  __int64 v4; // rsi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  const char *v7; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  DWORD v9; // eax
  const char *v10; // rcx
  DWORD v11; // eax
  DWORD v12; // eax
  const char *v13; // rcx

  v1 = *((_QWORD *)pv + 183);
  v3 = *(const void **)v1;
  v4 = *(_QWORD *)(v1 + 8) - *(_QWORD *)v1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 16LL))(pv);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 208));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)pv + 20) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    __FatalError(v7, 0x202u, "CreateEvent", LastError);
  }
  ThreadpoolWait = CreateThreadpoolWait(AsyncPipe::WriteCompletedStatic, pv, (PTP_CALLBACK_ENVIRON)(pv + 1472));
  *((_QWORD *)pv + 12) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v9 = GetLastError();
    __FatalError(v10, 0x205u, "CreateThreadpoolWait", v9);
  }
  SetThreadpoolWait(*((PTP_WAIT *)pv + 12), *((HANDLE *)pv + 20), 0);
  if ( WriteFile(*((HANDLE *)pv + 3), v3, v4, 0, (LPOVERLAPPED)(pv + 136)) )
  {
    *((_DWORD *)pv + 63) = 0;
  }
  else
  {
    v11 = GetLastError();
    *((_DWORD *)pv + 63) = v11;
    if ( v11 == 997 )
      goto LABEL_10;
  }
  if ( !SetEvent(*((HANDLE *)pv + 20)) )
  {
    v12 = GetLastError();
    __FatalError(v13, 0x20Eu, "SetEvent", v12);
  }
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 208));
}

```

## disassembly

```asm
0x14000dbbc  push    rbx
0x14000dbbe  push    rbp
0x14000dbbf  push    rsi
0x14000dbc0  push    rdi
0x14000dbc1  push    r14
0x14000dbc3  sub     rsp, 30h
0x14000dbc7  mov     rax, [rcx+5B8h]
0x14000dbce  mov     rbx, rcx
0x14000dbd1  mov     rbp, [rax]
0x14000dbd4  mov     rsi, [rax+8]
0x14000dbd8  mov     rax, [rcx]
0x14000dbdb  sub     rsi, rbp
0x14000dbde  mov     rax, [rax+10h]
0x14000dbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbe7  lea     rdi, [rbx+0D0h]
0x14000dbee  mov     rcx, rdi; lpCriticalSection
0x14000dbf1  call    cs:__imp_EnterCriticalSection
0x14000dbf7  xor     r9d, r9d; lpName
0x14000dbfa  xor     r8d, r8d; bInitialState
0x14000dbfd  xor     ecx, ecx; lpEventAttributes
0x14000dbff  lea     edx, [r9+1]; bManualReset
0x14000dc03  call    cs:__imp_CreateEventW
0x14000dc09  lea     r14, [rbx+88h]
0x14000dc10  mov     [r14+18h], rax
0x14000dc14  test    rax, rax
0x14000dc17  jnz     short loc_14000DC33
0x14000dc19  call    cs:__imp_GetLastError
0x14000dc1f  lea     r8, aCreateevent; "CreateEvent"
0x14000dc26  mov     edx, 202h; unsigned int
0x14000dc2b  mov     r9d, eax; unsigned int
0x14000dc2e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000dc33  lea     r8, [rbx+5C0h]; pcbe
0x14000dc3a  mov     rdx, rbx; pv
0x14000dc3d  lea     rcx, ?WriteCompletedStatic@AsyncPipe@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14000dc44  call    cs:__imp_CreateThreadpoolWait
0x14000dc4a  mov     [rbx+60h], rax
0x14000dc4e  test    rax, rax
0x14000dc51  jnz     short loc_14000DC6D
0x14000dc53  call    cs:__imp_GetLastError
0x14000dc59  lea     r8, aCreatethreadpo; "CreateThreadpoolWait"
0x14000dc60  mov     edx, 205h; unsigned int
0x14000dc65  mov     r9d, eax; unsigned int
0x14000dc68  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000dc6d  mov     rdx, [rbx+0A0h]; h
0x14000dc74  xor     r8d, r8d; pftTimeout
0x14000dc77  mov     rcx, [rbx+60h]; pwa
0x14000dc7b  call    cs:__imp_SetThreadpoolWait
0x14000dc81  mov     rcx, [rbx+18h]; hFile
0x14000dc85  mov     r8d, esi; nNumberOfBytesToWrite
0x14000dc88  xor     r9d, r9d; lpNumberOfBytesWritten
0x14000dc8b  mov     [rsp+58h+lpOverlapped], r14; lpOverlapped
0x14000dc90  mov     rdx, rbp; lpBuffer
0x14000dc93  call    cs:__imp_WriteFile
0x14000dc99  test    eax, eax
0x14000dc9b  jz      short loc_14000DCA9
0x14000dc9d  mov     dword ptr [rbx+0FCh], 0
0x14000dca7  jmp     short loc_14000DCBC
0x14000dca9  call    cs:__imp_GetLastError
0x14000dcaf  mov     [rbx+0FCh], eax
0x14000dcb5  cmp     eax, 3E5h
0x14000dcba  jz      short loc_14000DCE7
0x14000dcbc  mov     rcx, [rbx+0A0h]; hEvent
0x14000dcc3  call    cs:__imp_SetEvent
0x14000dcc9  test    eax, eax
0x14000dccb  jnz     short loc_14000DCE7
0x14000dccd  call    cs:__imp_GetLastError
0x14000dcd3  lea     r8, aSetevent; "SetEvent"
0x14000dcda  mov     edx, 20Eh; unsigned int
0x14000dcdf  mov     r9d, eax; unsigned int
0x14000dce2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000dce7  mov     rcx, rdi
0x14000dcea  add     rsp, 30h
0x14000dcee  pop     r14
0x14000dcf0  pop     rdi
0x14000dcf1  pop     rsi
0x14000dcf2  pop     rbp
0x14000dcf3  pop     rbx
0x14000dcf4  jmp     cs:__imp_LeaveCriticalSection
```
