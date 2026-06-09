# CBdeCfgConsole::ConfigureHelper(void)

- ea: `0x140001ecc`
- end: `0x140001fa4`
- name: `?ConfigureHelper@CBdeCfgConsole@@AEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001dbc`

## callees

- `0x140001ecc`
- `0x1400032b0`

## import_xrefs

- `KERNEL32!CancelWaitableTimer` at `0x140001f5e`
- `KERNEL32!CancelWaitableTimer` at `0x140001f5e`
- `KERNEL32!WaitForSingleObjectEx` at `0x140001f4d`
- `KERNEL32!WaitForSingleObjectEx` at `0x140001f4d`
- `KERNEL32!SetWaitableTimer` at `0x140001f2f`
- `KERNEL32!SetWaitableTimer` at `0x140001f2f`
- `KERNEL32!GetLastError` at `0x140001f68`
- `KERNEL32!GetLastError` at `0x140001f68`
- `BDEHDCFGLIB!?ConfigureDrive@CDriveConfiguration@@QEAAJXZ` at `0x140001ef0`
- `BDEHDCFGLIB!?ConfigureDrive@CDriveConfiguration@@QEAAJXZ` at `0x140001ef0`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::ConfigureHelper(HANDLE *this)
{
  DWORD v2; // esi
  int v3; // ebx
  signed int LastError; // eax
  LARGE_INTEGER DueTime; // [rsp+48h] [rbp+10h] BYREF

  v2 = 192;
  DueTime.QuadPart = 0;
  v3 = CDriveConfiguration::ConfigureDrive((CDriveConfiguration *)(this + 9));
  if ( v3 >= 0 )
  {
    DueTime.QuadPart = -10000000;
    SetWaitableTimer(this[181], &DueTime, 1000, CBdeCfgConsole::ProgressTimerEntry, this, 0);
    while ( v2 == 192 )
      v2 = WaitForSingleObjectEx(this[180], 0xFFFFFFFF, 1);
    CancelWaitableTimer(this[181]);
    if ( v2 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = *((_DWORD *)this + 20);
      CBdeCfgConsole::PrintConsoleMessage((CBdeCfgConsole *)this, L"\r\n\r\n");
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001ecc  mov     [rsp+arg_0], rbx
0x140001ed1  mov     [rsp+arg_10], rsi
0x140001ed6  push    rdi
0x140001ed7  sub     rsp, 30h
0x140001edb  mov     rdi, rcx
0x140001ede  mov     esi, 0C0h
0x140001ee3  mov     qword ptr [rsp+38h+DueTime], 0
0x140001eec  add     rcx, 48h ; 'H'
0x140001ef0  call    cs:__imp_?ConfigureDrive@CDriveConfiguration@@QEAAJXZ; CDriveConfiguration::ConfigureDrive(void)
0x140001ef6  mov     ebx, eax
0x140001ef8  test    eax, eax
0x140001efa  js      loc_140001F92
0x140001f00  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFFF676980h
0x140001f09  mov     [rsp+38h+fResume], 0; fResume
0x140001f11  mov     [rsp+38h+lpArgToCompletionRoutine], rdi; lpArgToCompletionRoutine
0x140001f16  lea     r9, ?ProgressTimerEntry@CBdeCfgConsole@@CAXPEAXKK@Z; pfnCompletionRoutine
0x140001f1d  mov     r8d, 3E8h; lPeriod
0x140001f23  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x140001f28  mov     rcx, [rdi+5A8h]; hTimer
0x140001f2f  call    cs:__imp_SetWaitableTimer
0x140001f35  cmp     esi, 0C0h
0x140001f3b  jnz     short loc_140001F57
0x140001f3d  mov     r8d, 1; bAlertable
0x140001f43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140001f46  mov     rcx, [rdi+5A0h]; hHandle
0x140001f4d  call    cs:__imp_WaitForSingleObjectEx
0x140001f53  mov     esi, eax
0x140001f55  jmp     short loc_140001F35
0x140001f57  mov     rcx, [rdi+5A8h]; hTimer
0x140001f5e  call    cs:__imp_CancelWaitableTimer
0x140001f64  test    esi, esi
0x140001f66  jz      short loc_140001F7F
0x140001f68  call    cs:__imp_GetLastError
0x140001f6e  mov     ebx, eax
0x140001f70  test    eax, eax
0x140001f72  jle     short loc_140001F92
0x140001f74  movzx   ebx, ax
0x140001f77  or      ebx, 80070000h
0x140001f7d  jmp     short loc_140001F92
0x140001f7f  mov     ebx, [rdi+50h]
0x140001f82  lea     rdx, asc_1400067C8; "\r\n\r\n"
0x140001f89  mov     rcx, rdi; this
0x140001f8c  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJPEBGZZ; CBdeCfgConsole::PrintConsoleMessage(ushort const *,...)
0x140001f91  nop
0x140001f92  mov     eax, ebx
0x140001f94  mov     rbx, [rsp+38h+arg_0]
0x140001f99  mov     rsi, [rsp+38h+arg_10]
0x140001f9e  add     rsp, 30h
0x140001fa2  pop     rdi
0x140001fa3  retn
0x140004650  push    rbp
0x140004652  sub     rsp, 30h
0x140004656  mov     rbp, rdx
0x140004659  add     rsp, 30h
0x14000465d  pop     rbp
0x14000465e  retn
```
