# WmipInitializeEventPump

- ea: `0x1800690fc`
- end: `0x18006920d`
- name: `WmipInitializeEventPump`
- size: `273`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180069300`

## callees

- `0x1800690fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006912d`
- `KERNEL32!GetLastError` at `0x18006917c`
- `KERNEL32!GetLastError` at `0x1800691ad`
- `KERNEL32!GetLastError` at `0x18006912d`
- `KERNEL32!GetLastError` at `0x18006917c`
- `KERNEL32!GetLastError` at `0x1800691ad`
- `KERNEL32!CreateEventW` at `0x180069117`
- `KERNEL32!CreateEventW` at `0x180069117`
- `KERNEL32!CloseHandle` at `0x1800691be`
- `KERNEL32!CloseHandle` at `0x1800691cd`
- `KERNEL32!CloseHandle` at `0x1800691be`
- `KERNEL32!CloseHandle` at `0x1800691cd`
- `KERNEL32!CreateFileW` at `0x180069167`
- `KERNEL32!CreateFileW` at `0x180069167`
- `KERNEL32!CreateThreadpoolIo` at `0x18006919c`
- `KERNEL32!CreateThreadpoolIo` at `0x18006919c`

## pseudocode

```c
__int64 WmipInitializeEventPump()
{
  DWORD LastError; // ebx
  HANDLE EventW; // rsi
  HANDLE FileW; // rax
  void *v3; // rdi
  struct _TP_IO *ThreadpoolIo; // rax

  LastError = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    FileW = CreateFileW(L"\\\\.\\WMIDataDevice", 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
    v3 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      ThreadpoolIo = CreateThreadpoolIo(FileW, WmipEventPumpIoCompletion, 0, 0);
      if ( ThreadpoolIo )
      {
        WmipEventPumpOverlappedEvent = (__int64)EventW;
        WmipEventPumpTarget = v3;
        WmipEventPumpIo = ThreadpoolIo;
        WmipEventPumpState = 1;
        return LastError;
      }
      LastError = GetLastError();
      CloseHandle(v3);
    }
    CloseHandle(EventW);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800690fc  mov     [rsp+arg_0], rbx
0x180069101  mov     [rsp+arg_8], rsi
0x180069106  push    rdi
0x180069107  sub     rsp, 40h
0x18006910b  xor     r9d, r9d; lpName
0x18006910e  xor     r8d, r8d; bInitialState
0x180069111  xor     ecx, ecx; lpEventAttributes
0x180069113  lea     edx, [r9+1]; bManualReset
0x180069117  call    cs:__imp_CreateEventW
0x18006911e  nop     dword ptr [rax+rax+00h]
0x180069123  xor     ebx, ebx
0x180069125  mov     rsi, rax
0x180069128  test    rax, rax
0x18006912b  jnz     short loc_180069140
0x18006912d  call    cs:__imp_GetLastError
0x180069134  nop     dword ptr [rax+rax+00h]
0x180069139  mov     ebx, eax
0x18006913b  jmp     loc_1800691FA
0x180069140  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180069145  lea     rcx, DosName; "\\\\.\\WMIDataDevice"
0x18006914c  mov     [rsp+48h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180069154  xor     r9d, r9d; lpSecurityAttributes
0x180069157  xor     r8d, r8d; dwShareMode
0x18006915a  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180069162  mov     edx, 0C0000000h; dwDesiredAccess
0x180069167  call    cs:__imp_CreateFileW
0x18006916e  nop     dword ptr [rax+rax+00h]
0x180069173  mov     rdi, rax
0x180069176  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006917a  jnz     short loc_18006918C
0x18006917c  call    cs:__imp_GetLastError
0x180069183  nop     dword ptr [rax+rax+00h]
0x180069188  mov     ebx, eax
0x18006918a  jmp     short loc_1800691CA
0x18006918c  xor     r9d, r9d; pcbe
0x18006918f  lea     rdx, WmipEventPumpIoCompletion; pfnio
0x180069196  xor     r8d, r8d; pv
0x180069199  mov     rcx, rdi; fl
0x18006919c  call    cs:__imp_CreateThreadpoolIo
0x1800691a3  nop     dword ptr [rax+rax+00h]
0x1800691a8  test    rax, rax
0x1800691ab  jnz     short loc_1800691DB
0x1800691ad  call    cs:__imp_GetLastError
0x1800691b4  nop     dword ptr [rax+rax+00h]
0x1800691b9  mov     rcx, rdi; hObject
0x1800691bc  mov     ebx, eax
0x1800691be  call    cs:__imp_CloseHandle
0x1800691c5  nop     dword ptr [rax+rax+00h]
0x1800691ca  mov     rcx, rsi; hObject
0x1800691cd  call    cs:__imp_CloseHandle
0x1800691d4  nop     dword ptr [rax+rax+00h]
0x1800691d9  jmp     short loc_1800691FA
0x1800691db  mov     cs:WmipEventPumpOverlappedEvent, rsi
0x1800691e2  mov     cs:WmipEventPumpTarget, rdi
0x1800691e9  mov     cs:WmipEventPumpIo, rax
0x1800691f0  mov     cs:WmipEventPumpState, 1
0x1800691fa  mov     rsi, [rsp+48h+arg_8]
0x1800691ff  mov     eax, ebx
0x180069201  mov     rbx, [rsp+48h+arg_0]
0x180069206  add     rsp, 40h
0x18006920a  pop     rdi
0x18006920b  retn
```
