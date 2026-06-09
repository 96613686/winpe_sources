# KillProcess(ulong)

- ea: `0x18002e238`
- end: `0x18002e2cc`
- name: `?KillProcess@@YAJK@Z`
- size: `148`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002e2d4`

## callees

- `0x18002e238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e29d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e288`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2b9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002e24a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002e24a`

## pseudocode

```c
__int64 __fastcall KillProcess(DWORD dwProcessId)
{
  HANDLE v1; // rdi
  signed int LastError; // eax
  signed int v4; // ebx
  signed int v5; // eax

  v1 = OpenProcess(1u, 0, dwProcessId);
  if ( v1 )
    goto LABEL_8;
  if ( GetLastError() == 87 )
    return 0;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_8:
    if ( TerminateProcess(v1, 1u) || GetLastError() == 5 )
    {
      v4 = 0;
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
    }
    CloseHandle(v1);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002e238  mov     [rsp+arg_0], rbx
0x18002e23d  push    rdi
0x18002e23e  sub     rsp, 20h
0x18002e242  xor     edx, edx; bInheritHandle
0x18002e244  mov     r8d, ecx; dwProcessId
0x18002e247  lea     ecx, [rdx+1]; dwDesiredAccess
0x18002e24a  call    cs:__imp_OpenProcess
0x18002e250  mov     rdi, rax
0x18002e253  test    rax, rax
0x18002e256  jnz     short loc_18002E280
0x18002e258  call    cs:__imp_GetLastError
0x18002e25e  cmp     eax, 57h ; 'W'
0x18002e261  jnz     short loc_18002E267
0x18002e263  xor     eax, eax
0x18002e265  jmp     short loc_18002E2C1
0x18002e267  call    cs:__imp_GetLastError
0x18002e26d  mov     ebx, eax
0x18002e26f  test    eax, eax
0x18002e271  jle     short loc_18002E27C
0x18002e273  movzx   ebx, ax
0x18002e276  or      ebx, 80070000h
0x18002e27c  test    ebx, ebx
0x18002e27e  js      short loc_18002E2BF
0x18002e280  mov     edx, 1; uExitCode
0x18002e285  mov     rcx, rdi; hProcess
0x18002e288  call    cs:__imp_TerminateProcess
0x18002e28e  test    eax, eax
0x18002e290  jnz     short loc_18002E2B4
0x18002e292  call    cs:__imp_GetLastError
0x18002e298  cmp     eax, 5
0x18002e29b  jz      short loc_18002E2B4
0x18002e29d  call    cs:__imp_GetLastError
0x18002e2a3  mov     ebx, eax
0x18002e2a5  test    eax, eax
0x18002e2a7  jle     short loc_18002E2B6
0x18002e2a9  movzx   ebx, ax
0x18002e2ac  or      ebx, 80070000h
0x18002e2b2  jmp     short loc_18002E2B6
0x18002e2b4  xor     ebx, ebx
0x18002e2b6  mov     rcx, rdi; hObject
0x18002e2b9  call    cs:__imp_CloseHandle
0x18002e2bf  mov     eax, ebx
0x18002e2c1  mov     rbx, [rsp+28h+arg_0]
0x18002e2c6  add     rsp, 20h
0x18002e2ca  pop     rdi
0x18002e2cb  retn
```
