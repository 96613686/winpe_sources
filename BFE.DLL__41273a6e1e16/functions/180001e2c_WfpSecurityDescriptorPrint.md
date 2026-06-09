# WfpSecurityDescriptorPrint

- ea: `0x180001e2c`
- end: `0x180001ed8`
- name: `WfpSecurityDescriptorPrint`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003180`

## callees

- `0x180001e2c`
- `0x1800033d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180001e5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180001e5b`

## string_xrefs

- `0x18008b380`: `<invalid access control list>`

## pseudocode

```c
HLOCAL __fastcall WfpSecurityDescriptorPrint(__int64 a1, __int64 a2, void *a3)
{
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  hMem = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(a3, 1u, 0xFu, (LPWSTR *)&hMem, 0) )
  {
    WfpSwprintf(a2, L"\n%s\n", hMem);
    return LocalFree(hMem);
  }
  v5 = GetLastError() - 87;
  if ( v5 )
  {
    v6 = v5 - 1218;
    if ( v6 )
    {
      v7 = v6 - 27;
      if ( v7 )
      {
        v8 = a2;
        if ( v7 == 4 )
          v9 = L"<invalid access control list>";
        else
          v9 = L"<invalid>";
        return (HLOCAL)WfpSwprintf(v8, v9);
      }
      v9 = L"<none mapped>";
    }
    else
    {
      v9 = L"<unknown SDDL revision>";
    }
  }
  else
  {
    v9 = L"<invalid parameter>";
  }
  v8 = a2;
  return (HLOCAL)WfpSwprintf(v8, v9);
}

```

## disassembly

```asm
0x180001e2c  mov     rax, rsp
0x180001e2f  mov     [rax+8], rcx
0x180001e33  push    rbx
0x180001e34  sub     rsp, 30h
0x180001e38  mov     rbx, rdx
0x180001e3b  mov     qword ptr [rax+8], 0
0x180001e43  mov     edx, 1; RequestedStringSDRevision
0x180001e48  mov     qword ptr [rax-18h], 0
0x180001e50  mov     rcx, r8; SecurityDescriptor
0x180001e53  lea     r9, [rax+8]; StringSecurityDescriptor
0x180001e57  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180001e5b  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180001e62  nop     dword ptr [rax+rax+00h]
0x180001e67  test    eax, eax
0x180001e69  jz      short loc_180001E97
0x180001e6b  mov     r8, [rsp+38h+hMem]
0x180001e70  lea     rdx, aS; "\n%s\n"
0x180001e77  mov     rcx, rbx
0x180001e7a  call    WfpSwprintf
0x180001e7f  mov     rcx, [rsp+38h+hMem]; hMem
0x180001e84  call    cs:__imp_LocalFree
0x180001e8b  nop     dword ptr [rax+rax+00h]
0x180001e90  add     rsp, 30h
0x180001e94  pop     rbx
0x180001e95  retn
0x180001e97  call    cs:__imp_GetLastError
0x180001e9e  nop     dword ptr [rax+rax+00h]
0x180001ea3  sub     eax, 57h ; 'W'
0x180001ea6  jz      loc_18008B39B
0x180001eac  sub     eax, 4C2h
0x180001eb1  jz      loc_18008B392
0x180001eb7  sub     eax, 1Bh
0x180001eba  jz      loc_18008B389
0x180001ec0  mov     rcx, rbx
0x180001ec3  cmp     eax, 4
0x180001ec6  jz      loc_18008B380
0x180001ecc  lea     rdx, aInvalid; "<invalid>"
0x180001ed3  jmp     loc_18008B3A5
0x18008b380  lea     rdx, aInvalidAccessC; "<invalid access control list>"
0x18008b387  jmp     short loc_18008B3A5
0x18008b389  lea     rdx, aNoneMapped; "<none mapped>"
0x18008b390  jmp     short loc_18008B3A2
0x18008b392  lea     rdx, aUnknownSddlRev; "<unknown SDDL revision>"
0x18008b399  jmp     short loc_18008B3A2
0x18008b39b  lea     rdx, aInvalidParamet; "<invalid parameter>"
0x18008b3a2  mov     rcx, rbx
0x18008b3a5  call    WfpSwprintf
0x18008b3aa  nop
0x18008b3ab  jmp     loc_180001E90
```
