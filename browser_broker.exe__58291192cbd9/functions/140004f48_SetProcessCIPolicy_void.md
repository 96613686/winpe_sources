# SetProcessCIPolicy(void)

- ea: `0x140004f48`
- end: `0x140004fd1`
- name: `?SetProcessCIPolicy@@YAXXZ`
- size: `137`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400054fc`

## callees

- `0x140004a10`
- `0x140004f48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004f54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140004f54`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140004fab`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140004fab`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140004f6c`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x140004f6c`

## string_xrefs

- `0x140004f7b`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140004fba`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`

## pseudocode

```c
void SetProcessCIPolicy(void)
{
  HANDLE CurrentProcess; // rax
  const char *v1; // r9
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 8, &v4) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1AB,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      v1);
  if ( (v4 & 1) == 0 )
  {
    v4 = 1;
    if ( !(unsigned int)SetProcessMitigationPolicy(8, &v4, 4) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1B0,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
        v2);
  }
}

```

## disassembly

```asm
0x140004f48  sub     rsp, 28h
0x140004f4c  mov     [rsp+28h+arg_0], 0
0x140004f54  call    cs:__imp_GetCurrentProcess
0x140004f5a  mov     r9d, 4
0x140004f60  lea     r8, [rsp+28h+arg_0]
0x140004f65  mov     rcx, rax
0x140004f68  lea     edx, [r9+4]
0x140004f6c  call    cs:__imp_GetProcessMitigationPolicy
0x140004f72  test    eax, eax
0x140004f74  jnz     short loc_140004F8D
0x140004f76  mov     rcx, [rsp+28h]; this
0x140004f7b  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140004f82  mov     edx, 1ABh; void *
0x140004f87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004f8d  test    byte ptr [rsp+28h+arg_0], 1
0x140004f92  jnz     short loc_140004FCC
0x140004f94  mov     r8d, 4
0x140004f9a  mov     [rsp+28h+arg_0], 1
0x140004fa2  lea     rdx, [rsp+28h+arg_0]
0x140004fa7  lea     ecx, [r8+4]
0x140004fab  call    cs:__imp_SetProcessMitigationPolicy
0x140004fb1  test    eax, eax
0x140004fb3  jnz     short loc_140004FCC
0x140004fb5  mov     rcx, [rsp+28h]; this
0x140004fba  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140004fc1  mov     edx, 1B0h; void *
0x140004fc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004fcc  add     rsp, 28h
0x140004fd0  retn
```
