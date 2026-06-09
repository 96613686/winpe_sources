# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(HKEY__ *)

- ea: `0x18002baa8`
- end: `0x18002bb54`
- name: `?IsValidProfile@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@AEAA_NPEAUHKEY__@@@Z`
- size: `172`
- prototype: `bool(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002207c`

## callees

- `0x18002baa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb20`

## string_xrefs

- `0x18002bad5`: `ConfigLevel`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *this,
        HKEY a2)
{
  const wchar_t **v2; // rbx
  const wchar_t *v5; // [rsp+30h] [rbp-20h] BYREF
  int v6; // [rsp+38h] [rbp-18h]
  const wchar_t *v7; // [rsp+40h] [rbp-10h]
  int v8; // [rsp+48h] [rbp-8h]
  char vars0; // [rsp+50h] [rbp+0h] BYREF
  DWORD Type; // [rsp+60h] [rbp+10h] BYREF
  int v11; // [rsp+64h] [rbp+14h]
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF

  v11 = HIDWORD(this);
  v6 = 1;
  v5 = L"AppUserModelId";
  v2 = &v5;
  v8 = 4;
  v7 = L"ConfigLevel";
  Type = 0;
  cbData = 0;
  while ( v2 != (const wchar_t **)&vars0 )
  {
    if ( RegQueryValueExW(a2, *v2, 0, &Type, 0, &cbData) || Type != *((_DWORD *)v2 + 2) || !cbData )
      return 0;
    v2 += 2;
  }
  return 1;
}

```

## disassembly

```asm
0x18002baa8  mov     [rsp-8+arg_8], rbx
0x18002baad  mov     [rsp-8+arg_18], rdi
0x18002bab2  mov     qword ptr [rsp-8+Type], rcx
0x18002bab7  push    rbp
0x18002bab8  mov     rbp, rsp
0x18002babb  sub     rsp, 50h
0x18002babf  lea     rax, aAppusermodelid; "AppUserModelId"
0x18002bac6  mov     [rbp+var_18], 1
0x18002bacd  mov     [rbp+var_20], rax
0x18002bad1  lea     rbx, [rbp+var_20]
0x18002bad5  lea     rax, aConfiglevel; "ConfigLevel"
0x18002badc  mov     [rbp+var_8], 4
0x18002bae3  mov     [rbp+var_10], rax
0x18002bae7  mov     rdi, rdx
0x18002baea  mov     [rbp+Type], 0
0x18002baf1  mov     [rbp+cbData], 0
0x18002baf8  lea     rax, [rbp+var_s0]
0x18002bafc  cmp     rbx, rax
0x18002baff  jz      short loc_18002BB42
0x18002bb01  mov     rdx, [rbx]; lpValueName
0x18002bb04  lea     rax, [rbp+cbData]
0x18002bb08  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002bb0d  lea     r9, [rbp+Type]; lpType
0x18002bb11  xor     r8d, r8d; lpReserved
0x18002bb14  mov     [rsp+50h+lpData], 0; lpData
0x18002bb1d  mov     rcx, rdi; hKey
0x18002bb20  call    cs:__imp_RegQueryValueExW
0x18002bb26  test    eax, eax
0x18002bb28  jnz     short loc_18002BB3E
0x18002bb2a  mov     eax, [rbx+8]
0x18002bb2d  cmp     [rbp+Type], eax
0x18002bb30  jnz     short loc_18002BB3E
0x18002bb32  cmp     [rbp+cbData], 0
0x18002bb36  jz      short loc_18002BB3E
0x18002bb38  add     rbx, 10h
0x18002bb3c  jmp     short loc_18002BAF8
0x18002bb3e  xor     al, al
0x18002bb40  jmp     short loc_18002BB44
0x18002bb42  mov     al, 1
0x18002bb44  mov     rbx, [rsp+50h+arg_8]
0x18002bb49  mov     rdi, [rsp+50h+arg_18]
0x18002bb4e  add     rsp, 50h
0x18002bb52  pop     rbp
0x18002bb53  retn
```
