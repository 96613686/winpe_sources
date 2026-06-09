# HasActiveConsoleWindow(bool &)

- ea: `0x180011484`
- end: `0x1800114e4`
- name: `?HasActiveConsoleWindow@@YAKAEA_N@Z`
- size: `96`
- prototype: `unsigned int __fastcall(bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180020fa0`

## callees

- `0x180011484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011495`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011495`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800114c6`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800114c6`
- `KERNEL32!ProcessIdToSessionId` at `0x1800114a8`
- `KERNEL32!ProcessIdToSessionId` at `0x1800114a8`

## pseudocode

```c
DWORD __fastcall HasActiveConsoleWindow(bool *a1)
{
  DWORD CurrentProcessId; // eax
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF

  pSessionId = 0;
  *a1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return GetLastError();
  *a1 = WTSGetActiveConsoleSessionId() == pSessionId;
  return 0;
}

```

## disassembly

```asm
0x180011484  push    rbx
0x180011486  sub     rsp, 20h
0x18001148a  and     [rsp+28h+pSessionId], 0
0x18001148f  mov     rbx, rcx
0x180011492  mov     byte ptr [rcx], 0
0x180011495  call    cs:__imp_GetCurrentProcessId
0x18001149c  nop     dword ptr [rax+rax+00h]
0x1800114a1  mov     ecx, eax; dwProcessId
0x1800114a3  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x1800114a8  call    cs:__imp_ProcessIdToSessionId
0x1800114af  nop     dword ptr [rax+rax+00h]
0x1800114b4  test    eax, eax
0x1800114b6  jnz     short loc_1800114C6
0x1800114b8  call    cs:__imp_GetLastError
0x1800114bf  nop     dword ptr [rax+rax+00h]
0x1800114c4  jmp     short loc_1800114DD
0x1800114c6  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800114cd  nop     dword ptr [rax+rax+00h]
0x1800114d2  cmp     eax, [rsp+28h+pSessionId]
0x1800114d6  setz    al
0x1800114d9  mov     [rbx], al
0x1800114db  xor     eax, eax
0x1800114dd  add     rsp, 20h
0x1800114e1  pop     rbx
0x1800114e2  retn
```
