# IsAppInstalled(ushort const *)

- ea: `0x18002a628`
- end: `0x18002a6bd`
- name: `?IsAppInstalled@@YAHPEBG@Z`
- size: `149`
- prototype: `_BOOL8 __fastcall(PCWSTR packageFamilyName)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180029d00`

## callees

- `0x18002a628`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6ad`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a662`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002a662`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002a691`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18002a691`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002a653`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002a653`

## pseudocode

```c
_BOOL8 __fastcall IsAppInstalled(PCWSTR packageFamilyName)
{
  BOOL v2; // ebx
  UINT32 count; // [rsp+68h] [rbp+10h] BYREF
  UINT32 bufferLength; // [rsp+70h] [rbp+18h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp+20h] BYREF

  count = 0;
  bufferLength = 0;
  hToken = 0;
  v2 = 0;
  if ( (unsigned int)QueryUserToken(0, &hToken)
    && ImpersonateLoggedOnUser(hToken)
    && FindPackagesByPackageFamily(packageFamilyName, 0x10u, &count, 0, &bufferLength, 0, 0) == 122 )
  {
    v2 = count != 0;
  }
  if ( hToken )
    CloseHandle(hToken);
  return v2;
}

```

## disassembly

```asm
0x18002a628  mov     rax, rsp
0x18002a62b  push    rbx
0x18002a62c  push    rbp
0x18002a62d  push    rdi
0x18002a62e  sub     rsp, 40h
0x18002a632  mov     rdi, rcx
0x18002a635  mov     dword ptr [rax+10h], 0
0x18002a63c  xor     ecx, ecx
0x18002a63e  mov     dword ptr [rax+18h], 0
0x18002a645  lea     rdx, [rax+20h]
0x18002a649  mov     qword ptr [rax+20h], 0
0x18002a651  xor     ebx, ebx
0x18002a653  call    cs:__imp_QueryUserToken
0x18002a659  test    eax, eax
0x18002a65b  jz      short loc_18002A6A3
0x18002a65d  mov     rcx, [rsp+58h+hToken]; hToken
0x18002a662  call    cs:__imp_ImpersonateLoggedOnUser
0x18002a668  lea     ebp, [rbx+1]
0x18002a66b  cmp     eax, ebp
0x18002a66d  jnz     short loc_18002A6A3
0x18002a66f  mov     [rsp+58h+packageProperties], rbx; packageProperties
0x18002a674  lea     rax, [rsp+58h+arg_10]
0x18002a679  mov     [rsp+58h+buffer], rbx; buffer
0x18002a67e  lea     r8, [rsp+58h+count]; count
0x18002a683  xor     r9d, r9d; packageFullNames
0x18002a686  mov     [rsp+58h+bufferLength], rax; bufferLength
0x18002a68b  lea     edx, [rbx+10h]; packageFilters
0x18002a68e  mov     rcx, rdi; packageFamilyName
0x18002a691  call    cs:__imp_FindPackagesByPackageFamily
0x18002a697  cmp     eax, 7Ah ; 'z'
0x18002a69a  jnz     short loc_18002A6A3
0x18002a69c  cmp     [rsp+58h+count], ebx
0x18002a6a0  cmova   ebx, ebp
0x18002a6a3  mov     rcx, [rsp+58h+hToken]; hObject
0x18002a6a8  test    rcx, rcx
0x18002a6ab  jz      short loc_18002A6B3
0x18002a6ad  call    cs:__imp_CloseHandle
0x18002a6b3  mov     eax, ebx
0x18002a6b5  add     rsp, 40h
0x18002a6b9  pop     rdi
0x18002a6ba  pop     rbp
0x18002a6bb  pop     rbx
0x18002a6bc  retn
```
