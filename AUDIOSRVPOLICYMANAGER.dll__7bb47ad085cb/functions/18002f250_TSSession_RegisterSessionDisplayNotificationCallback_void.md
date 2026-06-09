# TSSession::RegisterSessionDisplayNotificationCallback(void)

- ea: `0x18002f250`
- end: `0x18002f334`
- name: `?RegisterSessionDisplayNotificationCallback@TSSession@@QEAAXXZ`
- size: `228`
- prototype: `void __fastcall(TSSession *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180042918`

## callees

- `0x18002f250`
- `0x18003d00c`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002f25d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002f25d`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x18002f2b9`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x18002f306`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x18002f2b9`
- `POWRPROF!PowerSettingRegisterNotificationEx` at `0x18002f306`

## pseudocode

```c
void __fastcall TSSession::RegisterSessionDisplayNotificationCallback(TSSession *this)
{
  __int64 v2; // rdx
  unsigned int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v7[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( *(_DWORD *)this != (unsigned int)RtlGetCurrentServiceSessionId()
    && !*((_QWORD *)this + 128)
    && !*((_QWORD *)this + 129) )
  {
    v2 = *(unsigned int *)this;
    v6[0] = TsSessionIdDisplayNotificationCallback;
    v6[1] = *(unsigned int *)this;
    v3 = PowerSettingRegisterNotificationEx(&GUID_SESSION_DISPLAY_STATUS, v2, 2, v6);
    if ( v3 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xD8,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)v3,
        (_DWORD)this + 1024);
    v4 = *(unsigned int *)this;
    v7[0] = TsSessionConsoleLockedNotificationCallback;
    v7[1] = v4;
    v5 = PowerSettingRegisterNotificationEx(&GUID_CONSOLE_LOCKED, v4, 2, v7);
    if ( v5 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xE5,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)v5,
        (_DWORD)this + 1032);
  }
}

```

## disassembly

```asm
0x18002f250  mov     [rsp+arg_0], rbx
0x18002f255  push    rdi
0x18002f256  sub     rsp, 50h
0x18002f25a  mov     rbx, rcx
0x18002f25d  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18002f263  cmp     [rbx], eax
0x18002f265  jz      loc_18002F329
0x18002f26b  lea     rcx, [rbx+400h]
0x18002f272  cmp     qword ptr [rcx], 0
0x18002f276  jnz     loc_18002F329
0x18002f27c  lea     rdi, [rbx+408h]
0x18002f283  cmp     qword ptr [rdi], 0
0x18002f287  jnz     loc_18002F329
0x18002f28d  mov     edx, [rbx]
0x18002f28f  lea     rax, ?TsSessionIdDisplayNotificationCallback@@YAKPEAXK0@Z; TsSessionIdDisplayNotificationCallback(void *,ulong,void *)
0x18002f296  mov     [rsp+58h+var_28], rax
0x18002f29b  lea     r9, [rsp+58h+var_28]
0x18002f2a0  mov     eax, [rbx]
0x18002f2a2  mov     r8d, 2
0x18002f2a8  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x18002f2ad  lea     rcx, GUID_SESSION_DISPLAY_STATUS
0x18002f2b4  mov     [rsp+58h+var_20], rax
0x18002f2b9  call    cs:__imp_PowerSettingRegisterNotificationEx
0x18002f2bf  test    eax, eax
0x18002f2c1  jz      short loc_18002F2DC
0x18002f2c3  mov     rcx, [rsp+58h]; this
0x18002f2c8  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18002f2cf  mov     r9d, eax; char *
0x18002f2d2  mov     edx, 0D8h; void *
0x18002f2d7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002f2dc  mov     edx, [rbx]
0x18002f2de  lea     rax, ?TsSessionConsoleLockedNotificationCallback@@YAKPEAXK0@Z; TsSessionConsoleLockedNotificationCallback(void *,ulong,void *)
0x18002f2e5  lea     r9, [rsp+58h+var_18]
0x18002f2ea  mov     [rsp+58h+var_18], rax
0x18002f2ef  mov     r8d, 2
0x18002f2f5  mov     [rsp+58h+var_10], rdx
0x18002f2fa  lea     rcx, GUID_CONSOLE_LOCKED
0x18002f301  mov     qword ptr [rsp+58h+var_38], rdi; unsigned int
0x18002f306  call    cs:__imp_PowerSettingRegisterNotificationEx
0x18002f30c  test    eax, eax
0x18002f30e  jz      short loc_18002F329
0x18002f310  mov     rcx, [rsp+58h]; this
0x18002f315  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18002f31c  mov     r9d, eax; char *
0x18002f31f  mov     edx, 0E5h; void *
0x18002f324  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002f329  mov     rbx, [rsp+58h+arg_0]
0x18002f32e  add     rsp, 50h
0x18002f332  pop     rdi
0x18002f333  retn
```
