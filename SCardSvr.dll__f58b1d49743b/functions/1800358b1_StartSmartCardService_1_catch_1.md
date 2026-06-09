# _StartSmartCardService_::_1_::catch$1

- ea: `0x1800358b1`
- end: `0x180035907`
- name: `_StartSmartCardService_::_1_::catch$1`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800358b1`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800358ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800358c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800358e0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800358c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800358e0`

## pseudocode

```c
__int64 __fastcall StartSmartCardService_::_1_::catch_1(__int64 a1, __int64 a2)
{
  SC_HANDLE v3; // rcx
  SC_HANDLE v4; // rcx

  v3 = *(SC_HANDLE *)(a2 + 32);
  if ( v3 && !CloseServiceHandle(v3) )
    GetLastError();
  v4 = *(SC_HANDLE *)(a2 + 64);
  if ( v4 && !CloseServiceHandle(v4) )
    GetLastError();
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a2 + 72);
  return 0;
}

```

## disassembly

```asm
0x1800358b1  mov     [rsp+arg_8], rdx
0x1800358b6  push    rbp
0x1800358b7  sub     rsp, 20h
0x1800358bb  mov     rbp, rdx
0x1800358be  mov     rcx, [rbp+20h]; hSCObject
0x1800358c2  test    rcx, rcx
0x1800358c5  jz      short loc_1800358D7
0x1800358c7  call    cs:__imp_CloseServiceHandle
0x1800358cd  test    eax, eax
0x1800358cf  jnz     short loc_1800358D7
0x1800358d1  call    cs:__imp_GetLastError
0x1800358d7  mov     rcx, [rbp+40h]; hSCObject
0x1800358db  test    rcx, rcx
0x1800358de  jz      short loc_1800358F0
0x1800358e0  call    cs:__imp_CloseServiceHandle
0x1800358e6  test    eax, eax
0x1800358e8  jnz     short loc_1800358F0
0x1800358ea  call    cs:__imp_GetLastError
0x1800358f0  mov     eax, [rbp+48h]
0x1800358f3  mov     [rbp+20h], eax
0x1800358f6  mov     rax, 0
0x180035900  add     rsp, 20h
0x180035904  pop     rbp
0x180035905  retn
```
