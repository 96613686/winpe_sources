# SetAdminRights

- ea: `0x18001c09c`
- end: `0x18001c0ec`
- name: `SetAdminRights`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001be2c`
- `0x18001cc8c`

## callees

- `0x18001c09c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c0ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c0ba`

## pseudocode

```c
signed int __fastcall SetAdminRights(__int64 a1)
{
  signed int result; // eax
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptorSize = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;GA;;;BA)",
         1u,
         (PSECURITY_DESCRIPTOR *)(a1 + 8),
         &SecurityDescriptorSize) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001c09c  sub     rsp, 28h
0x18001c0a0  and     [rsp+28h+SecurityDescriptorSize], 0
0x18001c0a5  lea     r8, [rcx+8]; SecurityDescriptor
0x18001c0a9  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GA;;;BA)"
0x18001c0b0  mov     edx, 1; StringSDRevision
0x18001c0b5  lea     r9, [rsp+28h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001c0ba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c0c1  nop     dword ptr [rax+rax+00h]
0x18001c0c6  test    eax, eax
0x18001c0c8  jnz     short loc_18001C0E4
0x18001c0ca  call    cs:__imp_GetLastError
0x18001c0d1  nop     dword ptr [rax+rax+00h]
0x18001c0d6  test    eax, eax
0x18001c0d8  jle     short loc_18001C0E6
0x18001c0da  movzx   eax, ax
0x18001c0dd  or      eax, 80070000h
0x18001c0e2  jmp     short loc_18001C0E6
0x18001c0e4  xor     eax, eax
0x18001c0e6  add     rsp, 28h
0x18001c0ea  retn
```
