# SetUrlAclInfo

- ea: `0x180009f28`
- end: `0x180009fba`
- name: `SetUrlAclInfo`
- size: `146`
- prototype: `DWORD __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180003890`
- `0x180009f28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f67`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009fa5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009fa5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009f5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009f5d`

## pseudocode

```c
DWORD __fastcall SetUrlAclInfo(__int64 a1, int a2)
{
  int v3; // ebx
  int v4; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  hMem = 0;
  v4 = 0;
  if ( !a1 || a2 != 16 )
    return 87;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(*(LPCWSTR *)(a1 + 8), 1u, &hMem, (PULONG)&v4) )
    return GetLastError();
  v3 = AddUrlToUrlGroup(g_ServiceCommChannelHandle, 0, (__int64)hMem, v4);
  LocalFree(hMem);
  return v3;
}

```

## disassembly

```asm
0x180009f28  mov     rax, rsp
0x180009f2b  push    rbx
0x180009f2c  sub     rsp, 40h
0x180009f30  mov     qword ptr [rax+18h], 0
0x180009f38  mov     rbx, rcx
0x180009f3b  mov     dword ptr [rax+8], 0
0x180009f42  test    rcx, rcx
0x180009f45  jz      short loc_180009FAF
0x180009f47  cmp     edx, 10h
0x180009f4a  jnz     short loc_180009FAF
0x180009f4c  mov     rcx, [rcx+8]; StringSecurityDescriptor
0x180009f50  lea     r9, [rax+8]; SecurityDescriptorSize
0x180009f54  lea     r8, [rax+18h]; SecurityDescriptor
0x180009f58  mov     edx, 1; StringSDRevision
0x180009f5d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180009f63  test    eax, eax
0x180009f65  jnz     short loc_180009F6F
0x180009f67  call    cs:__imp_GetLastError
0x180009f6d  jmp     short loc_180009FB4
0x180009f6f  mov     eax, [rsp+48h+arg_0]
0x180009f73  xor     r8d, r8d
0x180009f76  mov     r9, [rbx]
0x180009f79  xor     edx, edx
0x180009f7b  mov     rcx, cs:g_ServiceCommChannelHandle; FileHandle
0x180009f82  mov     [rsp+48h+var_18], eax; int
0x180009f86  mov     rax, [rsp+48h+hMem]
0x180009f8b  mov     [rsp+48h+var_20], rax; __int64
0x180009f90  mov     [rsp+48h+var_28], 0; __int64
0x180009f99  call    AddUrlToUrlGroup
0x180009f9e  mov     rcx, [rsp+48h+hMem]; hMem
0x180009fa3  mov     ebx, eax
0x180009fa5  call    cs:__imp_LocalFree
0x180009fab  mov     eax, ebx
0x180009fad  jmp     short loc_180009FB4
0x180009faf  mov     eax, 57h ; 'W'
0x180009fb4  add     rsp, 40h
0x180009fb8  pop     rbx
0x180009fb9  retn
```
