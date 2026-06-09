# getEaphostProcessId(void)

- ea: `0x14000238c`
- end: `0x140002429`
- name: `?getEaphostProcessId@@YAKXZ`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x140002430`

## callees

- `0x140001330`
- `0x14000238c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400023ca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400023ca`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002404`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000240c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140002404`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000240c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400023f7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400023f7`

## pseudocode

```c
__int64 getEaphostProcessId(void)
{
  SC_HANDLE v0; // rbx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v4; // [rsp+48h] [rbp-30h]
  int v5; // [rsp+58h] [rbp-20h]

  *(_OWORD *)Buffer = 0;
  v5 = 0;
  v4 = 0;
  pcbBytesNeeded = 0;
  v0 = OpenServiceW(schSCManager, L"EapHost", 4u);
  if ( !v0 )
    return 0xFFFFFFFFLL;
  if ( !QueryServiceStatusEx(v0, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    CloseServiceHandle(v0);
    return 0xFFFFFFFFLL;
  }
  CloseServiceHandle(v0);
  return HIDWORD(v4);
}

```

## disassembly

```asm
0x14000238c  push    rbx
0x14000238e  sub     rsp, 70h
0x140002392  mov     rax, cs:__security_cookie
0x140002399  xor     rax, rsp
0x14000239c  mov     [rsp+78h+var_18], rax
0x1400023a1  mov     rcx, cs:?schSCManager@@3PEAUSC_HANDLE__@@EA; hSCManager
0x1400023a8  lea     rdx, ServiceName; "EapHost"
0x1400023af  xor     eax, eax
0x1400023b1  xorps   xmm0, xmm0
0x1400023b4  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x1400023b9  mov     [rsp+78h+var_20], eax
0x1400023bd  movups  [rsp+78h+var_30], xmm0
0x1400023c2  lea     r8d, [rax+4]; dwDesiredAccess
0x1400023c6  mov     [rsp+78h+var_48], eax
0x1400023ca  call    cs:__imp_OpenServiceW
0x1400023d0  mov     rbx, rax
0x1400023d3  test    rax, rax
0x1400023d6  jnz     short loc_1400023DD
0x1400023d8  or      eax, 0FFFFFFFFh
0x1400023db  jmp     short loc_140002416
0x1400023dd  lea     rax, [rsp+78h+var_48]
0x1400023e2  mov     r9d, 24h ; '$'; cbBufSize
0x1400023e8  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x1400023ed  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1400023f2  xor     edx, edx; InfoLevel
0x1400023f4  mov     rcx, rbx; hService
0x1400023f7  call    cs:__imp_QueryServiceStatusEx
0x1400023fd  mov     rcx, rbx; hSCObject
0x140002400  test    eax, eax
0x140002402  jnz     short loc_14000240C
0x140002404  call    cs:__imp_CloseServiceHandle
0x14000240a  jmp     short loc_1400023D8
0x14000240c  call    cs:__imp_CloseServiceHandle
0x140002412  mov     eax, dword ptr [rsp+78h+var_30+0Ch]
0x140002416  mov     rcx, [rsp+78h+var_18]
0x14000241b  xor     rcx, rsp; StackCookie
0x14000241e  call    __security_check_cookie
0x140002423  add     rsp, 70h
0x140002427  pop     rbx
0x140002428  retn
```
