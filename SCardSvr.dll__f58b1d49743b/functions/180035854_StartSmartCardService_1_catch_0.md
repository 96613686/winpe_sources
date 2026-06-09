# _StartSmartCardService_::_1_::catch$0

- ea: `0x180035854`
- end: `0x1800358ab`
- name: `_StartSmartCardService_::_1_::catch$0`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180035854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003588d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003588d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003586a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180035883`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003586a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180035883`

## pseudocode

```c
__int64 __fastcall StartSmartCardService_::_1_::catch_0(__int64 a1, __int64 a2)
{
  SC_HANDLE v3; // rcx
  SC_HANDLE v4; // rcx

  v3 = *(SC_HANDLE *)(a2 + 32);
  if ( v3 && !CloseServiceHandle(v3) )
    GetLastError();
  v4 = *(SC_HANDLE *)(a2 + 64);
  if ( v4 && !CloseServiceHandle(v4) )
    GetLastError();
  *(_DWORD *)(a2 + 32) = 87;
  return 0;
}

```

## disassembly

```asm
0x180035854  mov     [rsp+arg_8], rdx
0x180035859  push    rbp
0x18003585a  sub     rsp, 20h
0x18003585e  mov     rbp, rdx
0x180035861  mov     rcx, [rbp+20h]; hSCObject
0x180035865  test    rcx, rcx
0x180035868  jz      short loc_18003587A
0x18003586a  call    cs:__imp_CloseServiceHandle
0x180035870  test    eax, eax
0x180035872  jnz     short loc_18003587A
0x180035874  call    cs:__imp_GetLastError
0x18003587a  mov     rcx, [rbp+40h]; hSCObject
0x18003587e  test    rcx, rcx
0x180035881  jz      short loc_180035893
0x180035883  call    cs:__imp_CloseServiceHandle
0x180035889  test    eax, eax
0x18003588b  jnz     short loc_180035893
0x18003588d  call    cs:__imp_GetLastError
0x180035893  mov     dword ptr [rbp+20h], 57h ; 'W'
0x18003589a  mov     rax, 0
0x1800358a4  add     rsp, 20h
0x1800358a8  pop     rbp
0x1800358a9  retn
```
