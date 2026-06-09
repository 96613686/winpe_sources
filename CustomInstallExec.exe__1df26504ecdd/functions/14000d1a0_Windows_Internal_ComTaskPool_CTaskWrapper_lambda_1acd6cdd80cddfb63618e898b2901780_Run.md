# Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::Run

- ea: `0x14000d1a0`
- end: `0x14000d1db`
- name: `Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::Run`
- size: `59`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000a8a8`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x14000d1d4`

## pseudocode

```c
BOOL __fastcall Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780___::Run(
        __int64 a1)
{
  OSIntegration::DEH::Internal::CustomInstallExecution::Run(
    **(const unsigned __int16 ***)(a1 + 16),
    **(_QWORD **)(a1 + 24),
    **(_BYTE **)(a1 + 32));
  return PostMessageW(g_mainWindow, 0x401u, 0, 0);
}

```

## disassembly

```asm
0x14000d1a0  sub     rsp, 28h
0x14000d1a4  mov     r8, [rcx+20h]
0x14000d1a8  mov     rdx, [rcx+18h]
0x14000d1ac  mov     rcx, [rcx+10h]
0x14000d1b0  mov     r8b, [r8]; bool
0x14000d1b3  mov     rdx, [rdx]; __int64
0x14000d1b6  mov     rcx, [rcx]; unsigned __int16 *
0x14000d1b9  call    ?Run@CustomInstallExecution@Internal@DEH@OSIntegration@@SAHQEBG_J_N@Z; OSIntegration::DEH::Internal::CustomInstallExecution::Run(ushort const * const,__int64,bool)
0x14000d1be  mov     rcx, cs:?g_mainWindow@@3PEAUHWND__@@EA; HWND__ * g_mainWindow
0x14000d1c5  xor     r9d, r9d
0x14000d1c8  xor     r8d, r8d
0x14000d1cb  mov     edx, 401h
0x14000d1d0  add     rsp, 28h
0x14000d1d4  jmp     cs:__imp_PostMessageW
```
