# common_end_thread

- ea: `0x18033eed8`
- end: `0x18033ef4b`
- name: `common_end_thread`
- size: `115`
- prototype: `void __fastcall __noreturn(DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18033f080`

## callees

- `0x18033eed8`
- `0x1803494a8`
- `0x18034eb40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18033ef25`
- `KERNEL32!CloseHandle` at `0x18033ef25`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18033ef3b`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18033ef3b`
- `KERNEL32!ExitThread` at `0x18033eef0`
- `KERNEL32!ExitThread` at `0x18033ef05`
- `KERNEL32!ExitThread` at `0x18033ef44`
- `KERNEL32!ExitThread` at `0x18033eef0`
- `KERNEL32!ExitThread` at `0x18033ef05`
- `KERNEL32!ExitThread` at `0x18033ef44`

## pseudocode

```c
void __fastcall __noreturn common_end_thread(DWORD dwExitCode)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  char *v4; // rcx
  HMODULE v5; // rcx

  v2 = _acrt_getptd_noexit();
  if ( !v2 )
    ExitThread(dwExitCode);
  v3 = *(_QWORD *)(v2 + 960);
  if ( !v3 )
    ExitThread(dwExitCode);
  if ( *(_BYTE *)(v3 + 32) )
    _acrt_RoUninitialize();
  v4 = *(char **)(v3 + 16);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = *(HMODULE *)(v3 + 24);
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    FreeLibraryAndExitThread(v5, dwExitCode);
  ExitThread(dwExitCode);
}

```

## disassembly

```asm
0x18033eed8  mov     [rsp+arg_0], rbx
0x18033eedd  push    rdi
0x18033eede  sub     rsp, 20h
0x18033eee2  mov     ebx, ecx
0x18033eee4  call    __acrt_getptd_noexit
0x18033eee9  test    rax, rax
0x18033eeec  jnz     short loc_18033EEF7
0x18033eeee  mov     ecx, ebx; dwExitCode
0x18033eef0  call    cs:__imp_ExitThread
0x18033eef7  mov     rdi, [rax+3C0h]
0x18033eefe  test    rdi, rdi
0x18033ef01  jnz     short loc_18033EF0C
0x18033ef03  mov     ecx, ebx; dwExitCode
0x18033ef05  call    cs:__imp_ExitThread
0x18033ef0c  cmp     byte ptr [rdi+20h], 0
0x18033ef10  jz      short loc_18033EF17
0x18033ef12  call    __acrt_RoUninitialize
0x18033ef17  mov     rcx, [rdi+10h]; hObject
0x18033ef1b  lea     rax, [rcx-1]
0x18033ef1f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18033ef23  ja      short loc_18033EF2B
0x18033ef25  call    cs:__imp_CloseHandle
0x18033ef2b  mov     rcx, [rdi+18h]; hLibModule
0x18033ef2f  lea     rax, [rcx-1]
0x18033ef33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18033ef37  ja      short loc_18033EF42
0x18033ef39  mov     edx, ebx; dwExitCode
0x18033ef3b  call    cs:__imp_FreeLibraryAndExitThread
0x18033ef42  mov     ecx, ebx; dwExitCode
0x18033ef44  call    cs:__imp_ExitThread
```
