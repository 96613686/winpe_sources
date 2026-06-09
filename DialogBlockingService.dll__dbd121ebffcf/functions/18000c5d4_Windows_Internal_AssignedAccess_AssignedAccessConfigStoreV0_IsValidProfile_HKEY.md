# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(HKEY__ *)

- ea: `0x18000c5d4`
- end: `0x18000c67d`
- name: `?IsValidProfile@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@AEAA_NPEAUHKEY__@@@Z`
- size: `169`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *this, HKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c1b0`

## callees

- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c643`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c643`

## string_xrefs

- `0x18000c601`: `ConfigLevel`

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
  while ( !RegQueryValueExW(a2, *v2, 0, &Type, 0, &cbData) && Type == *((_DWORD *)v2 + 2) && cbData )
  {
    v2 += 2;
    if ( v2 == (const wchar_t **)&vars0 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c5d4  mov     [rsp-8+arg_8], rbx
0x18000c5d9  mov     [rsp-8+arg_18], rdi
0x18000c5de  mov     qword ptr [rsp-8+Type], rcx
0x18000c5e3  push    rbp
0x18000c5e4  mov     rbp, rsp
0x18000c5e7  sub     rsp, 50h
0x18000c5eb  lea     rax, aAppusermodelid; "AppUserModelId"
0x18000c5f2  mov     [rbp+var_18], 1
0x18000c5f9  mov     [rbp+var_20], rax
0x18000c5fd  lea     rbx, [rbp+var_20]
0x18000c601  lea     rax, aConfiglevel; "ConfigLevel"
0x18000c608  mov     [rbp+var_8], 4
0x18000c60f  mov     [rbp+var_10], rax
0x18000c613  mov     rdi, rdx
0x18000c616  mov     [rbp+Type], 0
0x18000c61d  mov     [rbp+cbData], 0
0x18000c624  mov     rdx, [rbx]; lpValueName
0x18000c627  lea     rax, [rbp+cbData]
0x18000c62b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000c630  lea     r9, [rbp+Type]; lpType
0x18000c634  xor     r8d, r8d; lpReserved
0x18000c637  mov     [rsp+50h+lpData], 0; lpData
0x18000c640  mov     rcx, rdi; hKey
0x18000c643  call    cs:__imp_RegQueryValueExW
0x18000c649  test    eax, eax
0x18000c64b  jnz     short loc_18000C66B
0x18000c64d  mov     ecx, [rbx+8]
0x18000c650  cmp     [rbp+Type], ecx
0x18000c653  jnz     short loc_18000C66B
0x18000c655  cmp     [rbp+cbData], eax
0x18000c658  jz      short loc_18000C66B
0x18000c65a  add     rbx, 10h
0x18000c65e  lea     rcx, [rbp+var_s0]
0x18000c662  cmp     rbx, rcx
0x18000c665  jnz     short loc_18000C624
0x18000c667  mov     al, 1
0x18000c669  jmp     short loc_18000C66D
0x18000c66b  xor     al, al
0x18000c66d  mov     rbx, [rsp+50h+arg_8]
0x18000c672  mov     rdi, [rsp+50h+arg_18]
0x18000c677  add     rsp, 50h
0x18000c67b  pop     rbp
0x18000c67c  retn
```
