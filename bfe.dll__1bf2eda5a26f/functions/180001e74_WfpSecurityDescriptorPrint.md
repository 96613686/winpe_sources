# WfpSecurityDescriptorPrint

- ea: `0x180001e74`
- end: `0x180001f0d`
- name: `WfpSecurityDescriptorPrint`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003170`

## callees

- `0x180001e74`
- `0x1800033c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ed2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001ec6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180001ea3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180001ea3`

## string_xrefs

- `0x1800883e0`: `<invalid access control list>`

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
0x180001e74  mov     rax, rsp
0x180001e77  mov     [rax+8], rcx
0x180001e7b  push    rbx
0x180001e7c  sub     rsp, 30h
0x180001e80  mov     rbx, rdx
0x180001e83  mov     qword ptr [rax+8], 0
0x180001e8b  mov     edx, 1; RequestedStringSDRevision
0x180001e90  mov     qword ptr [rax-18h], 0
0x180001e98  mov     rcx, r8; SecurityDescriptor
0x180001e9b  lea     r9, [rax+8]; StringSecurityDescriptor
0x180001e9f  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180001ea3  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180001ea9  test    eax, eax
0x180001eab  jz      short loc_180001ED2
0x180001ead  mov     r8, [rsp+38h+hMem]
0x180001eb2  lea     rdx, aS; "\n%s\n"
0x180001eb9  mov     rcx, rbx
0x180001ebc  call    WfpSwprintf
0x180001ec1  mov     rcx, [rsp+38h+hMem]; hMem
0x180001ec6  call    cs:__imp_LocalFree
0x180001ecc  add     rsp, 30h
0x180001ed0  pop     rbx
0x180001ed1  retn
0x180001ed2  call    cs:__imp_GetLastError
0x180001ed8  sub     eax, 57h ; 'W'
0x180001edb  jz      loc_1800883FB
0x180001ee1  sub     eax, 4C2h
0x180001ee6  jz      loc_1800883F2
0x180001eec  sub     eax, 1Bh
0x180001eef  jz      loc_1800883E9
0x180001ef5  mov     rcx, rbx
0x180001ef8  cmp     eax, 4
0x180001efb  jz      loc_1800883E0
0x180001f01  lea     rdx, aInvalid; "<invalid>"
0x180001f08  jmp     loc_180088405
0x1800883e0  lea     rdx, aInvalidAccessC; "<invalid access control list>"
0x1800883e7  jmp     short loc_180088405
0x1800883e9  lea     rdx, aNoneMapped; "<none mapped>"
0x1800883f0  jmp     short loc_180088402
0x1800883f2  lea     rdx, aUnknownSddlRev; "<unknown SDDL revision>"
0x1800883f9  jmp     short loc_180088402
0x1800883fb  lea     rdx, aInvalidParamet; "<invalid parameter>"
0x180088402  mov     rcx, rbx
0x180088405  call    WfpSwprintf
0x18008840a  nop
0x18008840b  jmp     loc_180001ECC
```
