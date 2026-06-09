# WfpSecurityDescriptorPrint

- ea: `0x180116f58`
- end: `0x18011701e`
- name: `WfpSecurityDescriptorPrint`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801134e4`

## callees

- `0x180116f58`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116fbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116fb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180116f8d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180116f8d`

## string_xrefs

- `0x180116fe6`: `<invalid access control list>`

## pseudocode

```c
HLOCAL __fastcall WfpSecurityDescriptorPrint(void (*a1)(__int64, const wchar_t *, ...), __int64 a2, void *a3)
{
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  bool v9; // zf
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64, const wchar_t *); // rax
  const wchar_t *v12; // rdx
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  hMem = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(a3, 1u, 0xFu, (LPWSTR *)&hMem, 0) )
  {
    a1(a2, L"\n%s\n", hMem);
    return LocalFree(hMem);
  }
  v6 = GetLastError() - 87;
  if ( v6 )
  {
    v7 = v6 - 1218;
    if ( v7 )
    {
      v8 = v7 - 27;
      if ( v8 )
      {
        v9 = v8 == 4;
        v10 = a2;
        v11 = (__int64 (__fastcall *)(__int64, const wchar_t *))a1;
        if ( v9 )
          v12 = L"<invalid access control list>";
        else
          v12 = L"<invalid>";
        return (HLOCAL)v11(v10, v12);
      }
      v12 = L"<none mapped>";
    }
    else
    {
      v12 = L"<unknown SDDL revision>";
    }
  }
  else
  {
    v12 = L"<invalid parameter>";
  }
  v10 = a2;
  v11 = (__int64 (__fastcall *)(__int64, const wchar_t *))a1;
  return (HLOCAL)v11(v10, v12);
}

```

## disassembly

```asm
0x180116f58  mov     r11, rsp
0x180116f5b  mov     [r11+8], rbx
0x180116f5f  push    rdi
0x180116f60  sub     rsp, 30h
0x180116f64  mov     rax, r8
0x180116f67  mov     qword ptr [r11+20h], 0
0x180116f6f  mov     rbx, rdx
0x180116f72  mov     qword ptr [r11-18h], 0
0x180116f7a  mov     edx, 1; RequestedStringSDRevision
0x180116f7f  lea     r9, [r11+20h]; StringSecurityDescriptor
0x180116f83  mov     rdi, rcx
0x180116f86  mov     rcx, rax; SecurityDescriptor
0x180116f89  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180116f8d  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180116f93  test    eax, eax
0x180116f95  jz      short loc_180116FBB
0x180116f97  mov     r8, [rsp+38h+hMem]
0x180116f9c  lea     rdx, aS; "\n%s\n"
0x180116fa3  mov     rcx, rbx
0x180116fa6  mov     rax, rdi
0x180116fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116fae  mov     rcx, [rsp+38h+hMem]; hMem
0x180116fb3  call    cs:__imp_LocalFree
0x180116fb9  jmp     short loc_180117013
0x180116fbb  call    cs:__imp_GetLastError
0x180116fc1  sub     eax, 57h ; 'W'
0x180116fc4  jz      short loc_180117001
0x180116fc6  sub     eax, 4C2h
0x180116fcb  jz      short loc_180116FF8
0x180116fcd  sub     eax, 1Bh
0x180116fd0  jz      short loc_180116FEF
0x180116fd2  cmp     eax, 4
0x180116fd5  mov     rcx, rbx
0x180116fd8  mov     rax, rdi
0x180116fdb  jz      short loc_180116FE6
0x180116fdd  lea     rdx, aInvalid; "<invalid>"
0x180116fe4  jmp     short loc_18011700E
0x180116fe6  lea     rdx, aInvalidAccessC; "<invalid access control list>"
0x180116fed  jmp     short loc_18011700E
0x180116fef  lea     rdx, aNoneMapped; "<none mapped>"
0x180116ff6  jmp     short loc_180117008
0x180116ff8  lea     rdx, aUnknownSddlRev; "<unknown SDDL revision>"
0x180116fff  jmp     short loc_180117008
0x180117001  lea     rdx, aInvalidParamet; "<invalid parameter>"
0x180117008  mov     rcx, rbx
0x18011700b  mov     rax, rdi
0x18011700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117013  mov     rbx, [rsp+38h+arg_0]
0x180117018  add     rsp, 30h
0x18011701c  pop     rdi
0x18011701d  retn
```
