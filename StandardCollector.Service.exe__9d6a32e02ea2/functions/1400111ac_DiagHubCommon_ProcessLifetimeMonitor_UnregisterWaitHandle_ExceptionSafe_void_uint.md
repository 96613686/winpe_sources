# DiagHubCommon::ProcessLifetimeMonitor::UnregisterWaitHandle_ExceptionSafe(void *,uint)

- ea: `0x1400111ac`
- end: `0x14001121f`
- name: `?UnregisterWaitHandle_ExceptionSafe@ProcessLifetimeMonitor@DiagHubCommon@@AEAAXPEAXI@Z`
- size: `115`
- prototype: `void __fastcall(DiagHubCommon::ProcessLifetimeMonitor *this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010d8c`

## callees

- `0x14000a278`
- `0x1400111ac`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x1400111ca`
- `KERNEL32!UnregisterWaitEx` at `0x1400111ca`
- `KERNEL32!GetLastError` at `0x1400111ef`
- `KERNEL32!GetLastError` at `0x1400111ef`

## string_xrefs

- `0x1400111de`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`
- `0x140011203`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`

## pseudocode

```c
void __fastcall DiagHubCommon::ProcessLifetimeMonitor::UnregisterWaitHandle_ExceptionSafe(
        DiagHubCommon::ProcessLifetimeMonitor *this,
        void *a2,
        unsigned int a3)
{
  DiagHubCommon::LogStream *v4; // rdi
  DWORD LastError; // [rsp+20h] [rbp-18h]

  v4 = (DiagHubCommon::ProcessLifetimeMonitor *)((char *)this + 224);
  if ( UnregisterWaitEx(a2, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    DiagHubCommon::LogStream::Write(
      v4,
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Unregistered process exit handler for process ID: %d",
      a3);
  }
  else
  {
    LastError = GetLastError();
    DiagHubCommon::LogStream::Write(
      v4,
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Failed to unregister process exit handler for process ID: %d. Error code: %#08x",
      a3,
      LastError);
  }
}

```

## disassembly

```asm
0x1400111ac  mov     [rsp+arg_0], rbx
0x1400111b1  push    rdi
0x1400111b2  sub     rsp, 30h
0x1400111b6  mov     ebx, r8d
0x1400111b9  mov     rax, rdx
0x1400111bc  lea     rdi, [rcx+0E0h]
0x1400111c3  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400111c7  mov     rcx, rax; WaitHandle
0x1400111ca  call    cs:__imp_UnregisterWaitEx
0x1400111d0  test    eax, eax
0x1400111d2  jz      short loc_1400111EF
0x1400111d4  mov     r9d, ebx
0x1400111d7  lea     r8, aUnregisteredPr; "Unregistered process exit handler for p"...
0x1400111de  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x1400111e5  mov     rcx, rdi; this
0x1400111e8  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1400111ed  jmp     short loc_140011212
0x1400111ef  call    cs:__imp_GetLastError
0x1400111f5  mov     [rsp+38h+var_18], eax
0x1400111f9  mov     r9d, ebx
0x1400111fc  lea     r8, aFailedToUnregi; "Failed to unregister process exit handl"...
0x140011203  lea     rdx, aDAWork1SSource_1; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x14001120a  mov     rcx, rdi; this
0x14001120d  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140011212  jmp     short $+2
0x140011214  mov     rbx, [rsp+38h+arg_0]
0x140011219  add     rsp, 30h
0x14001121d  pop     rdi
0x14001121e  retn
```
