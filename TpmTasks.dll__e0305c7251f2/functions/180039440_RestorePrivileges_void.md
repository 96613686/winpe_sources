# RestorePrivileges(void *)

- ea: `0x180039440`
- end: `0x1800394a9`
- name: `?RestorePrivileges@@YAJPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800341b0`
- `0x18003c89c`

## callees

- `0x180039440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039496`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003946b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003946b`

## pseudocode

```c
__int64 __fastcall RestorePrivileges(HANDLE hObject)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( AdjustTokenPrivileges(hObject, 0, &previousPrivilege, 0, 0, 0) )
  {
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hObject )
    CloseHandle(hObject);
  return v3;
}

```

## disassembly

```asm
0x180039440  mov     [rsp+arg_0], rbx
0x180039445  push    rdi
0x180039446  sub     rsp, 30h
0x18003944a  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180039453  lea     r8, ?previousPrivilege@@3U_TOKEN_PRIVILEGES@@A; NewState
0x18003945a  xor     r9d, r9d; BufferLength
0x18003945d  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180039466  xor     edx, edx; DisableAllPrivileges
0x180039468  mov     rdi, rcx
0x18003946b  call    cs:__imp_AdjustTokenPrivileges
0x180039471  test    eax, eax
0x180039473  jnz     short loc_18003948C
0x180039475  call    cs:__imp_GetLastError
0x18003947b  mov     ebx, eax
0x18003947d  test    eax, eax
0x18003947f  jle     short loc_18003948E
0x180039481  movzx   ebx, ax
0x180039484  or      ebx, 80070000h
0x18003948a  jmp     short loc_18003948E
0x18003948c  xor     ebx, ebx
0x18003948e  test    rdi, rdi
0x180039491  jz      short loc_18003949C
0x180039493  mov     rcx, rdi; hObject
0x180039496  call    cs:__imp_CloseHandle
0x18003949c  mov     eax, ebx
0x18003949e  mov     rbx, [rsp+38h+arg_0]
0x1800394a3  add     rsp, 30h
0x1800394a7  pop     rdi
0x1800394a8  retn
```
