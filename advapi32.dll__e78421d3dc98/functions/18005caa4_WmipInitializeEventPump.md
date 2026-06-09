# WmipInitializeEventPump

- ea: `0x18005caa4`
- end: `0x18005cb84`
- name: `WmipInitializeEventPump`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005cc64`

## callees

- `0x18005caa4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005cacf`
- `KERNEL32!GetLastError` at `0x18005cb12`
- `KERNEL32!GetLastError` at `0x18005cb37`
- `KERNEL32!GetLastError` at `0x18005cacf`
- `KERNEL32!GetLastError` at `0x18005cb12`
- `KERNEL32!GetLastError` at `0x18005cb37`
- `KERNEL32!CreateEventW` at `0x18005cabf`
- `KERNEL32!CreateEventW` at `0x18005cabf`
- `KERNEL32!CloseHandle` at `0x18005cb42`
- `KERNEL32!CloseHandle` at `0x18005cb4b`
- `KERNEL32!CloseHandle` at `0x18005cb42`
- `KERNEL32!CloseHandle` at `0x18005cb4b`
- `KERNEL32!CreateFileW` at `0x18005cb03`
- `KERNEL32!CreateFileW` at `0x18005cb03`
- `KERNEL32!CreateThreadpoolIo` at `0x18005cb2c`
- `KERNEL32!CreateThreadpoolIo` at `0x18005cb2c`

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
0x18005caa4  mov     [rsp+arg_0], rbx
0x18005caa9  mov     [rsp+arg_8], rsi
0x18005caae  push    rdi
0x18005caaf  sub     rsp, 40h
0x18005cab3  xor     r9d, r9d; lpName
0x18005cab6  xor     r8d, r8d; bInitialState
0x18005cab9  xor     ecx, ecx; lpEventAttributes
0x18005cabb  lea     edx, [r9+1]; bManualReset
0x18005cabf  call    cs:__imp_CreateEventW
0x18005cac5  xor     ebx, ebx
0x18005cac7  mov     rsi, rax
0x18005caca  test    rax, rax
0x18005cacd  jnz     short loc_18005CADC
0x18005cacf  call    cs:__imp_GetLastError
0x18005cad5  mov     ebx, eax
0x18005cad7  jmp     loc_18005CB72
0x18005cadc  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18005cae1  lea     rcx, DosName; "\\\\.\\WMIDataDevice"
0x18005cae8  mov     [rsp+48h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18005caf0  xor     r9d, r9d; lpSecurityAttributes
0x18005caf3  xor     r8d, r8d; dwShareMode
0x18005caf6  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18005cafe  mov     edx, 0C0000000h; dwDesiredAccess
0x18005cb03  call    cs:__imp_CreateFileW
0x18005cb09  mov     rdi, rax
0x18005cb0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005cb10  jnz     short loc_18005CB1C
0x18005cb12  call    cs:__imp_GetLastError
0x18005cb18  mov     ebx, eax
0x18005cb1a  jmp     short loc_18005CB48
0x18005cb1c  xor     r9d, r9d; pcbe
0x18005cb1f  lea     rdx, WmipEventPumpIoCompletion; pfnio
0x18005cb26  xor     r8d, r8d; pv
0x18005cb29  mov     rcx, rdi; fl
0x18005cb2c  call    cs:__imp_CreateThreadpoolIo
0x18005cb32  test    rax, rax
0x18005cb35  jnz     short loc_18005CB53
0x18005cb37  call    cs:__imp_GetLastError
0x18005cb3d  mov     rcx, rdi; hObject
0x18005cb40  mov     ebx, eax
0x18005cb42  call    cs:__imp_CloseHandle
0x18005cb48  mov     rcx, rsi; hObject
0x18005cb4b  call    cs:__imp_CloseHandle
0x18005cb51  jmp     short loc_18005CB72
0x18005cb53  mov     cs:WmipEventPumpOverlappedEvent, rsi
0x18005cb5a  mov     cs:WmipEventPumpTarget, rdi
0x18005cb61  mov     cs:WmipEventPumpIo, rax
0x18005cb68  mov     cs:WmipEventPumpState, 1
0x18005cb72  mov     rsi, [rsp+48h+arg_8]
0x18005cb77  mov     eax, ebx
0x18005cb79  mov     rbx, [rsp+48h+arg_0]
0x18005cb7e  add     rsp, 40h
0x18005cb82  pop     rdi
0x18005cb83  retn
```
