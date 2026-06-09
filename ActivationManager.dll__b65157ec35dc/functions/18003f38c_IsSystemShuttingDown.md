# IsSystemShuttingDown

- ea: `0x18003f38c`
- end: `0x18003f3e7`
- name: `IsSystemShuttingDown`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180029270`

## callees

- `0x18003f38c`
- `0x18005e778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3c4`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003f3a0`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003f3a0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003f3b9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003f3b9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f3d9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f3d9`

## pseudocode

```c
bool IsSystemShuttingDown()
{
  char v0; // bl
  SC_HANDLE v1; // rax

  if ( (unsigned __int8)IsGetSystemMetricsPresent() && GetSystemMetrics(0x2000) )
    return 1;
  v1 = OpenSCManagerW(0, 0, 1u);
  if ( !v1 )
    return GetLastError() == 1115;
  v0 = 0;
  CloseServiceHandle(v1);
  return v0;
}

```

## disassembly

```asm
0x18003f38c  push    rbx
0x18003f38e  sub     rsp, 20h
0x18003f392  call    IsGetSystemMetricsPresent
0x18003f397  test    al, al
0x18003f399  jz      short loc_18003F3B1
0x18003f39b  mov     ecx, 2000h; nIndex
0x18003f3a0  call    cs:__imp_GetSystemMetrics
0x18003f3a6  test    eax, eax
0x18003f3a8  jz      short loc_18003F3B1
0x18003f3aa  mov     ebx, 1
0x18003f3af  jmp     short loc_18003F3DF
0x18003f3b1  xor     edx, edx; lpDatabaseName
0x18003f3b3  xor     ecx, ecx; lpMachineName
0x18003f3b5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003f3b9  call    cs:__imp_OpenSCManagerW
0x18003f3bf  test    rax, rax
0x18003f3c2  jnz     short loc_18003F3D4
0x18003f3c4  call    cs:__imp_GetLastError
0x18003f3ca  cmp     eax, 45Bh
0x18003f3cf  setz    bl
0x18003f3d2  jmp     short loc_18003F3DF
0x18003f3d4  xor     bl, bl
0x18003f3d6  mov     rcx, rax; hSCObject
0x18003f3d9  call    cs:__imp_CloseServiceHandle
0x18003f3df  mov     al, bl
0x18003f3e1  add     rsp, 20h
0x18003f3e5  pop     rbx
0x18003f3e6  retn
```
