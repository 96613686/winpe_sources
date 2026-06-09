# HNS::Service::Util::ServiceHelpers::IsServiceEnabled(wil::basic_zstring_view<ushort>)

- ea: `0x1800889f8`
- end: `0x180088aee`
- name: `?IsServiceEnabled@ServiceHelpers@Util@Service@HNS@@SA_NV?$basic_zstring_view@G@wil@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800c6e00`

## callees

- `0x180088744`
- `0x180088908`
- `0x1800889f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a66`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180088a2f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180088a2f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180088a0b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180088a0b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ab2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088abc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ad4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ade`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ab2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088abc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ad4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088ade`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180088a5c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180088a94`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180088a5c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180088a94`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall HNS::Service::Util::ServiceHelpers::IsServiceEnabled(LPCWSTR *a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  LPQUERY_SERVICE_CONFIGW v6; // rsi
  LPQUERY_SERVICE_CONFIGW lpServiceConfig[7]; // [rsp+20h] [rbp-38h] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp+10h] BYREF
  SC_HANDLE v10; // [rsp+70h] [rbp+18h]
  SC_HANDLE v11; // [rsp+78h] [rbp+20h]

  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, *a1, 5u);
    v5 = v4;
    v11 = v4;
    if ( v4 )
    {
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(v4, 0, 0, &pcbBytesNeeded) || GetLastError() == 122 )
      {
        std::vector<unsigned char>::vector<unsigned char>(lpServiceConfig, pcbBytesNeeded);
        v6 = lpServiceConfig[0];
        if ( QueryServiceConfigW(v5, lpServiceConfig[0], pcbBytesNeeded, &pcbBytesNeeded) && v6->dwStartType != 4 )
        {
          std::vector<enum std::byte>::~vector<enum std::byte>(lpServiceConfig);
          CloseServiceHandle(v5);
          CloseServiceHandle(v3);
          return 1;
        }
        std::vector<enum std::byte>::~vector<enum std::byte>(lpServiceConfig);
      }
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800889f8  push    rbx
0x1800889fa  push    rsi
0x1800889fb  push    rdi
0x1800889fc  sub     rsp, 40h
0x180088a00  mov     rdi, rcx
0x180088a03  xor     edx, edx; lpDatabaseName
0x180088a05  xor     ecx, ecx; lpMachineName
0x180088a07  lea     r8d, [rdx+1]; dwDesiredAccess
0x180088a0b  call    cs:__imp_OpenSCManagerW
0x180088a11  mov     rbx, rax
0x180088a14  mov     [rsp+58h+arg_10], rax
0x180088a19  test    rax, rax
0x180088a1c  jnz     short loc_180088A23
0x180088a1e  jmp     loc_180088AE4
0x180088a23  mov     r8d, 5; dwDesiredAccess
0x180088a29  mov     rdx, [rdi]; lpServiceName
0x180088a2c  mov     rcx, rbx; hSCManager
0x180088a2f  call    cs:__imp_OpenServiceW
0x180088a35  mov     rdi, rax
0x180088a38  mov     [rsp+58h+arg_18], rax
0x180088a3d  test    rax, rax
0x180088a40  jnz     short loc_180088A47
0x180088a42  jmp     loc_180088ADB
0x180088a47  mov     [rsp+58h+pcbBytesNeeded], 0
0x180088a4f  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180088a54  xor     r8d, r8d; cbBufSize
0x180088a57  xor     edx, edx; lpServiceConfig
0x180088a59  mov     rcx, rdi; hService
0x180088a5c  call    cs:__imp_QueryServiceConfigW
0x180088a62  test    eax, eax
0x180088a64  jnz     short loc_180088A71
0x180088a66  call    cs:__imp_GetLastError
0x180088a6c  cmp     eax, 7Ah ; 'z'
0x180088a6f  jnz     short loc_180088AD1
0x180088a71  mov     edx, [rsp+58h+pcbBytesNeeded]
0x180088a75  lea     rcx, [rsp+58h+lpServiceConfig]
0x180088a7a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180088a7f  mov     rsi, [rsp+58h+lpServiceConfig]
0x180088a84  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180088a89  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180088a8e  mov     rdx, rsi; lpServiceConfig
0x180088a91  mov     rcx, rdi; hService
0x180088a94  call    cs:__imp_QueryServiceConfigW
0x180088a9a  test    eax, eax
0x180088a9c  jz      short loc_180088AC6
0x180088a9e  cmp     dword ptr [rsi+4], 4
0x180088aa2  jz      short loc_180088AC6
0x180088aa4  lea     rcx, [rsp+58h+lpServiceConfig]
0x180088aa9  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180088aae  nop
0x180088aaf  mov     rcx, rdi; hSCObject
0x180088ab2  call    cs:__imp_CloseServiceHandle
0x180088ab8  nop
0x180088ab9  mov     rcx, rbx; hSCObject
0x180088abc  call    cs:__imp_CloseServiceHandle
0x180088ac2  mov     al, 1
0x180088ac4  jmp     short loc_180088AE6
0x180088ac6  lea     rcx, [rsp+58h+lpServiceConfig]
0x180088acb  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180088ad0  nop
0x180088ad1  mov     rcx, rdi; hSCObject
0x180088ad4  call    cs:__imp_CloseServiceHandle
0x180088ada  nop
0x180088adb  mov     rcx, rbx; hSCObject
0x180088ade  call    cs:__imp_CloseServiceHandle
0x180088ae4  xor     al, al
0x180088ae6  add     rsp, 40h
0x180088aea  pop     rdi
0x180088aeb  pop     rsi
0x180088aec  pop     rbx
0x180088aed  retn
```
