# _anonymous_namespace_::ServiceLifetimeManager::HostShutdownMain

- ea: `0x140005120`
- end: `0x1400051ce`
- name: `_anonymous_namespace_::ServiceLifetimeManager::HostShutdownMain`
- size: `174`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400073f0`

## callees

- `0x140005120`
- `0x14000a278`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140005148`
- `KERNEL32!OpenEventW` at `0x140005148`
- `KERNEL32!SetEvent` at `0x1400051a8`
- `KERNEL32!SetEvent` at `0x1400051a8`
- `KERNEL32!GetLastError` at `0x14000515b`
- `KERNEL32!GetLastError` at `0x14000515b`
- `KERNEL32!CloseHandle` at `0x1400051b8`
- `KERNEL32!CloseHandle` at `0x1400051b8`

## string_xrefs

- `0x14000513c`: `VisualStudio.StandardCollectorService170.StopEvent`
- `0x140005186`: `Signaling idle collector service shutdown.`
- `0x14000518d`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall anonymous_namespace_::ServiceLifetimeManager::HostShutdownMain(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  signed int v3; // ebx
  __int64 v4; // rdi
  signed int LastError; // eax

  v3 = 0;
  v4 = (__int64)OpenEventW(2u, 0, L"VisualStudio.StandardCollectorService170.StopEvent");
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v3 = LastError;
    v4 = -1;
  }
  if ( v3 >= 0 )
  {
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
      L"Signaling idle collector service shutdown.");
    SetEvent((HANDLE)v4);
  }
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
}

```

## disassembly

```asm
0x140005120  mov     rax, rsp
0x140005123  mov     [rax+8], rbx
0x140005127  mov     [rax+10h], rsi
0x14000512b  push    rdi
0x14000512c  sub     rsp, 30h
0x140005130  xorps   xmm0, xmm0
0x140005133  movups  xmmword ptr [rax-18h], xmm0
0x140005137  xor     ebx, ebx
0x140005139  mov     [rax-10h], ebx
0x14000513c  lea     r8, aVisualstudioSt; "VisualStudio.StandardCollectorService17"...
0x140005143  xor     edx, edx; bInheritHandle
0x140005145  lea     ecx, [rbx+2]; dwDesiredAccess
0x140005148  call    cs:__imp_OpenEventW
0x14000514e  mov     rdi, rax
0x140005151  mov     [rsp+38h+var_18], rax
0x140005156  test    rax, rax
0x140005159  jnz     short loc_14000517C
0x14000515b  call    cs:__imp_GetLastError
0x140005161  movzx   ebx, ax
0x140005164  or      ebx, 80070000h
0x14000516a  test    eax, eax
0x14000516c  cmovle  ebx, eax
0x14000516f  mov     [rsp+38h+var_10], ebx
0x140005173  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005177  mov     [rsp+38h+var_18], rdi
0x14000517c  test    ebx, ebx
0x14000517e  setns   sil
0x140005182  test    ebx, ebx
0x140005184  js      short loc_1400051AF
0x140005186  lea     r8, aSignalingIdleC_0; "Signaling idle collector service shutdo"...
0x14000518d  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x140005194  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x14000519b  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1400051a0  test    sil, sil
0x1400051a3  jz      short loc_1400051AF
0x1400051a5  mov     rcx, rdi; hEvent
0x1400051a8  call    cs:__imp_SetEvent
0x1400051ae  nop
0x1400051af  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400051b3  jz      short loc_1400051BE
0x1400051b5  mov     rcx, rdi; hObject
0x1400051b8  call    cs:__imp_CloseHandle
0x1400051be  mov     rbx, [rsp+38h+arg_0]
0x1400051c3  mov     rsi, [rsp+38h+arg_8]
0x1400051c8  add     rsp, 30h
0x1400051cc  pop     rdi
0x1400051cd  retn
```
