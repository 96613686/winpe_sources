# TiCoreWinlogonNotificationsInitialize

- ea: `0x1400168ac`
- end: `0x140016941`
- name: `TiCoreWinlogonNotificationsInitialize`
- size: `149`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009438`

## callees

- `0x1400168ac`
- `0x140017658`
- `0x14001c0f4`
- `0x14001c11c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400168dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400168dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168ee`

## string_xrefs

- `0x140016908`: `Failed to create startup processing event.`

## pseudocode

```c
__int64 TiCoreWinlogonNotificationsInitialize()
{
  int v0; // edi
  signed int LastError; // eax
  unsigned int v2; // ebx
  struct MonitoredCritSec *v3; // rcx
  __int64 result; // rax

  CBS_InitializeCriticalSection(L"WinlogonNotifyLock", 8u, &stru_1400406F8);
  v0 = 1;
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    v2 = 0;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) == 0 )
      v2 = -2147467259;
    CBSWdsLogLight(0x4000000u, v2, (size_t *)1, "Failed to create startup processing event.");
    CBS_DeleteCriticalSection(v3);
    v0 = 0;
  }
  result = v2;
  dword_140040870 = v0;
  return result;
}

```

## disassembly

```asm
0x1400168ac  mov     [rsp+arg_0], rbx
0x1400168b1  push    rdi
0x1400168b2  sub     rsp, 20h
0x1400168b6  lea     r8, stru_1400406F8; struct _RTL_CRITICAL_SECTION *
0x1400168bd  mov     edx, 8; unsigned int
0x1400168c2  lea     rcx, aWinlogonnotify; "WinlogonNotifyLock"
0x1400168c9  call    ?CBS_InitializeCriticalSection@@YAXPEB_WIPEAUMonitoredCritSec@@@Z; CBS_InitializeCriticalSection(wchar_t const *,uint,MonitoredCritSec *)
0x1400168ce  xor     r9d, r9d; lpName
0x1400168d1  xor     r8d, r8d; bInitialState
0x1400168d4  xor     ecx, ecx; lpEventAttributes
0x1400168d6  lea     edi, [r9+1]
0x1400168da  mov     edx, edi; bManualReset
0x1400168dc  call    cs:__imp_CreateEventW
0x1400168e2  mov     cs:hObject, rax
0x1400168e9  test    rax, rax
0x1400168ec  jnz     short loc_14001692C
0x1400168ee  call    cs:__imp_GetLastError
0x1400168f4  mov     ebx, eax
0x1400168f6  test    eax, eax
0x1400168f8  jle     short loc_140016903
0x1400168fa  movzx   ebx, ax
0x1400168fd  or      ebx, 80070000h
0x140016903  mov     eax, 80004005h
0x140016908  lea     r9, aFailedToCreate_16; "Failed to create startup processing eve"...
0x14001690f  test    ebx, ebx
0x140016911  mov     r8d, edi
0x140016914  mov     ecx, 4000000h
0x140016919  cmovns  ebx, eax
0x14001691c  mov     edx, ebx
0x14001691e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140016923  call    ?CBS_DeleteCriticalSection@@YAXPEAUMonitoredCritSec@@@Z; CBS_DeleteCriticalSection(MonitoredCritSec *)
0x140016928  xor     edi, edi
0x14001692a  jmp     short loc_14001692E
0x14001692c  xor     ebx, ebx
0x14001692e  mov     eax, ebx
0x140016930  mov     cs:dword_140040870, edi
0x140016936  mov     rbx, [rsp+28h+arg_0]
0x14001693b  add     rsp, 20h
0x14001693f  pop     rdi
0x140016940  retn
```
