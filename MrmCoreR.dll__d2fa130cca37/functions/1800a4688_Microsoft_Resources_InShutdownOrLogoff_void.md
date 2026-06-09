# Microsoft::Resources::InShutdownOrLogoff(void)

- ea: `0x1800a4688`
- end: `0x1800a46e3`
- name: `?InShutdownOrLogoff@Resources@Microsoft@@YA_NXZ`
- size: `91`
- prototype: `bool __fastcall(Microsoft::Resources *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014284`
- `0x18001916c`
- `0x180035680`
- `0x1800a45f0`

## callees

- `0x180087178`
- `0x1800a4688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a46c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a46c0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800a469c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800a469c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a46b5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a46b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a46d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a46d5`

## pseudocode

```c
char __fastcall Microsoft::Resources::InShutdownOrLogoff(Microsoft::Resources *this)
{
  char v1; // bl
  SC_HANDLE v2; // rax

  if ( (unsigned __int8)IsGetSystemMetricsPresent(this) && GetSystemMetrics(0x2000) )
    return 1;
  v2 = OpenSCManagerW(0, 0, 1u);
  if ( !v2 )
    return GetLastError() == 1115;
  v1 = 0;
  CloseServiceHandle(v2);
  return v1;
}

```

## disassembly

```asm
0x1800a4688  push    rbx
0x1800a468a  sub     rsp, 20h
0x1800a468e  call    IsGetSystemMetricsPresent
0x1800a4693  test    al, al
0x1800a4695  jz      short loc_1800A46AD
0x1800a4697  mov     ecx, 2000h; nIndex
0x1800a469c  call    cs:__imp_GetSystemMetrics
0x1800a46a2  test    eax, eax
0x1800a46a4  jz      short loc_1800A46AD
0x1800a46a6  mov     ebx, 1
0x1800a46ab  jmp     short loc_1800A46DB
0x1800a46ad  xor     edx, edx; lpDatabaseName
0x1800a46af  xor     ecx, ecx; lpMachineName
0x1800a46b1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800a46b5  call    cs:__imp_OpenSCManagerW
0x1800a46bb  test    rax, rax
0x1800a46be  jnz     short loc_1800A46D0
0x1800a46c0  call    cs:__imp_GetLastError
0x1800a46c6  cmp     eax, 45Bh
0x1800a46cb  setz    bl
0x1800a46ce  jmp     short loc_1800A46DB
0x1800a46d0  xor     bl, bl
0x1800a46d2  mov     rcx, rax; hSCObject
0x1800a46d5  call    cs:__imp_CloseServiceHandle
0x1800a46db  mov     al, bl
0x1800a46dd  add     rsp, 20h
0x1800a46e1  pop     rbx
0x1800a46e2  retn
```
