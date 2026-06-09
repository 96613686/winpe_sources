# WinMain_CompileHealth

- ea: `0x140002868`
- end: `0x14000299c`
- name: `WinMain_CompileHealth`
- size: `308`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002ce8`

## callees

- `0x140001eb0`
- `0x140001f80`
- `0x1400020b8`
- `0x140002868`
- `0x1400029a4`
- `0x140002ab4`
- `0x140003234`
- `0x1400032dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140002946`
- `KERNEL32!CloseHandle` at `0x140002962`
- `KERNEL32!CloseHandle` at `0x140002946`
- `KERNEL32!CloseHandle` at `0x140002962`
- `KERNEL32!CreateMutexExW` at `0x1400028a4`
- `KERNEL32!CreateMutexExW` at `0x1400028a4`
- `KERNEL32!SetLastError` at `0x140002978`
- `KERNEL32!SetLastError` at `0x140002978`
- `KERNEL32!GetLastError` at `0x140002935`
- `KERNEL32!GetLastError` at `0x140002952`
- `KERNEL32!GetLastError` at `0x14000296e`
- `KERNEL32!GetLastError` at `0x140002935`
- `KERNEL32!GetLastError` at `0x140002952`
- `KERNEL32!GetLastError` at `0x14000296e`

## pseudocode

```c
__int64 WinMain_CompileHealth()
{
  HANDLE Mutex; // rax
  void *v1; // rsi
  unsigned int EventIfPrimary; // ebx
  __int16 v3; // ax
  DWORD LastError; // edi
  BOOL v5; // eax
  DWORD ThreadId[24]; // [rsp+20h] [rbp-60h] BYREF

  PoolNotify::PoolNotify((PoolNotify *)ThreadId);
  Mutex = CreateMutexExW(0, L"Global\\SpaceWorker_Mutex", 0, 0x1F0001u);
  v1 = Mutex;
  if ( Mutex )
    EventIfPrimary = WinMain_CompileHealth_CreateEventIfPrimary(Mutex);
  else
    EventIfPrimary = 0;
  if ( guiStorageSpacesState )
    v3 = -1;
  else
    v3 = 0;
  EnableTaskBootTrigger(v3);
  LastError = GetLastError();
  if ( v1 )
  {
    v5 = CloseHandle(v1);
    if ( EventIfPrimary )
    {
      EventIfPrimary = v5;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  PoolNotify::~PoolNotify((PoolNotify *)ThreadId);
  return EventIfPrimary;
}

```

## disassembly

```asm
0x140002868  mov     [rsp-18h+arg_10], rbx
0x14000286d  push    rbp
0x14000286e  push    rsi
0x14000286f  push    rdi
0x140002870  mov     rbp, rsp
0x140002873  sub     rsp, 80h
0x14000287a  lea     rcx, [rbp+ThreadId]; this
0x14000287e  mov     [rbp+hObject], 0
0x140002886  mov     [rbp+arg_0], 0
0x14000288d  call    ??0PoolNotify@@QEAA@XZ; PoolNotify::PoolNotify(void)
0x140002892  mov     r9d, 1F0001h; dwDesiredAccess
0x140002898  lea     rdx, Name; "Global\\SpaceWorker_Mutex"
0x14000289f  xor     r8d, r8d; dwFlags
0x1400028a2  xor     ecx, ecx; lpMutexAttributes
0x1400028a4  call    cs:__imp_CreateMutexExW
0x1400028aa  mov     rsi, rax
0x1400028ad  test    rax, rax
0x1400028b0  jnz     short loc_1400028B6
0x1400028b2  xor     ebx, ebx
0x1400028b4  jmp     short loc_14000291D
0x1400028b6  lea     r9, [rbp+arg_0]
0x1400028ba  mov     rcx, rsi; hMutex
0x1400028bd  lea     r8, [rbp+hObject]
0x1400028c1  call    WinMain_CompileHealth_CreateEventIfPrimary
0x1400028c6  cmp     [rbp+arg_0], 0
0x1400028ca  mov     ebx, eax
0x1400028cc  jz      short loc_14000291D
0x1400028ce  lea     rcx, [rbp+ThreadId]; lpThreadId
0x1400028d2  call    ?Start@PoolNotify@@QEAAKK@Z; PoolNotify::Start(ulong)
0x1400028d7  test    eax, eax
0x1400028d9  jnz     short loc_1400028B2
0x1400028db  mov     edx, 1; int
0x1400028e0  lea     rcx, [rbp+ThreadId]; this
0x1400028e4  call    ?Run@PoolNotify@@QEAAHH@Z; PoolNotify::Run(int)
0x1400028e9  mov     ebx, eax
0x1400028eb  test    eax, eax
0x1400028ed  jz      short loc_14000291D
0x1400028ef  xor     edx, edx; int
0x1400028f1  lea     rcx, [rbp+ThreadId]; this
0x1400028f5  call    ?Run@PoolNotify@@QEAAHH@Z; PoolNotify::Run(int)
0x1400028fa  test    eax, eax
0x1400028fc  jnz     short loc_1400028EF
0x1400028fe  lea     r8, [rbp+arg_0]
0x140002902  mov     [rbp+arg_0], eax
0x140002905  lea     rdx, [rbp+hObject]
0x140002909  mov     rcx, rsi; hMutex
0x14000290c  call    WinMain_CompileHealth_DestroyEventIfOkay
0x140002911  mov     ebx, eax
0x140002913  test    eax, eax
0x140002915  jz      short loc_14000291D
0x140002917  cmp     [rbp+arg_0], 1
0x14000291b  jz      short loc_1400028DB
0x14000291d  cmp     cs:?guiStorageSpacesState@@3IA, 0; uint guiStorageSpacesState
0x140002924  jz      short loc_14000292B
0x140002926  or      eax, 0FFFFFFFFh
0x140002929  jmp     short loc_14000292D
0x14000292b  xor     eax, eax
0x14000292d  movzx   ecx, ax; __int16
0x140002930  call    ?EnableTaskBootTrigger@@YAXF@Z; EnableTaskBootTrigger(short)
0x140002935  call    cs:__imp_GetLastError
0x14000293b  mov     rcx, [rbp+hObject]; hObject
0x14000293f  mov     edi, eax
0x140002941  test    rcx, rcx
0x140002944  jz      short loc_14000295A
0x140002946  call    cs:__imp_CloseHandle
0x14000294c  test    ebx, ebx
0x14000294e  jz      short loc_14000295A
0x140002950  mov     ebx, eax
0x140002952  call    cs:__imp_GetLastError
0x140002958  mov     edi, eax
0x14000295a  test    rsi, rsi
0x14000295d  jz      short loc_140002976
0x14000295f  mov     rcx, rsi; hObject
0x140002962  call    cs:__imp_CloseHandle
0x140002968  test    ebx, ebx
0x14000296a  jz      short loc_140002976
0x14000296c  mov     ebx, eax
0x14000296e  call    cs:__imp_GetLastError
0x140002974  mov     edi, eax
0x140002976  mov     ecx, edi; dwErrCode
0x140002978  call    cs:__imp_SetLastError
0x14000297e  lea     rcx, [rbp+ThreadId]; this
0x140002982  call    ??1PoolNotify@@QEAA@XZ; PoolNotify::~PoolNotify(void)
0x140002987  mov     eax, ebx
0x140002989  mov     rbx, [rsp+80h+arg_10]
0x140002991  add     rsp, 80h
0x140002998  pop     rdi
0x140002999  pop     rsi
0x14000299a  pop     rbp
0x14000299b  retn
```
