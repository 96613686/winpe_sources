# LocationCapabilityHandler::GetUserGlobalPolicy(ushort const *,ushort const *,CapabilityHandlerPolicyValue *)

- ea: `0x180001e10`
- end: `0x180001f01`
- name: `?GetUserGlobalPolicy@LocationCapabilityHandler@@UEAAJPEBG0PEAW4CapabilityHandlerPolicyValue@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(LocationCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, enum CapabilityHandlerPolicyValue *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ea4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ea4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001e6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001ee0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001e6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001eeb`

## pseudocode

```c
__int64 __fastcall LocationCapabilityHandler::GetUserGlobalPolicy(
        LocationCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        enum CapabilityHandlerPolicyValue *a4)
{
  __int64 result; // rax
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  *(_DWORD *)a4 = 3;
  pvData = 0;
  pcbData = 4;
  if ( a2 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20019u, &phkResult) )
    {
      RegGetValueW(
        phkResult,
        L"Software\\Policies\\Microsoft\\Windows\\LocationAndSensors",
        L"DisableLocation",
        0x18u,
        0,
        &pvData,
        &pcbData);
      RegCloseKey(phkResult);
    }
  }
  else
  {
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Policies\\Microsoft\\Windows\\LocationAndSensors",
      L"DisableLocation",
      0x18u,
      0,
      &pvData,
      &pcbData);
  }
  result = 0;
  if ( pvData == 1 )
    *(_DWORD *)a4 = 2;
  return result;
}

```

## disassembly

```asm
0x180001e10  mov     [rsp+arg_0], rbx
0x180001e15  push    rdi
0x180001e16  sub     rsp, 50h
0x180001e1a  xor     edi, edi
0x180001e1c  mov     dword ptr [r9], 3
0x180001e23  mov     [rsp+58h+arg_8], edi
0x180001e27  mov     rbx, r9
0x180001e2a  mov     [rsp+58h+arg_18], 4
0x180001e32  test    rdx, rdx
0x180001e35  jnz     short loc_180001E85
0x180001e37  lea     rax, [rsp+58h+arg_18]
0x180001e3c  mov     r9d, 18h; dwFlags
0x180001e42  mov     [rsp+58h+pcbData], rax; pcbData
0x180001e47  lea     r8, Value; "DisableLocation"
0x180001e4e  lea     rax, [rsp+58h+arg_8]
0x180001e53  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180001e5a  mov     [rsp+58h+pvData], rax; pvData
0x180001e5f  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180001e66  mov     [rsp+58h+pdwType], rdi; pdwType
0x180001e6b  call    cs:__imp_RegGetValueW
0x180001e71  xor     eax, eax
0x180001e73  cmp     [rsp+58h+arg_8], 1
0x180001e78  jz      short loc_180001EF6
0x180001e7a  mov     rbx, [rsp+58h+arg_0]
0x180001e7f  add     rsp, 50h
0x180001e83  pop     rdi
0x180001e84  retn
0x180001e85  lea     rax, [rsp+58h+phkResult]
0x180001e8a  mov     [rsp+58h+phkResult], rdi
0x180001e8f  mov     r9d, 20019h; samDesired
0x180001e95  mov     [rsp+58h+pdwType], rax; phkResult
0x180001e9a  xor     r8d, r8d; ulOptions
0x180001e9d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180001ea4  call    cs:__imp_RegOpenKeyExW
0x180001eaa  test    eax, eax
0x180001eac  jnz     short loc_180001E71
0x180001eae  mov     rcx, [rsp+58h+phkResult]; hkey
0x180001eb3  lea     rax, [rsp+58h+arg_18]
0x180001eb8  mov     [rsp+58h+pcbData], rax; pcbData
0x180001ebd  lea     r8, Value; "DisableLocation"
0x180001ec4  lea     rax, [rsp+58h+arg_8]
0x180001ec9  mov     r9d, 18h; dwFlags
0x180001ecf  mov     [rsp+58h+pvData], rax; pvData
0x180001ed4  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180001edb  mov     [rsp+58h+pdwType], rdi; pdwType
0x180001ee0  call    cs:__imp_RegGetValueW
0x180001ee6  mov     rcx, [rsp+58h+phkResult]; hKey
0x180001eeb  call    cs:__imp_RegCloseKey
0x180001ef1  jmp     loc_180001E71
0x180001ef6  mov     dword ptr [rbx], 2
0x180001efc  jmp     loc_180001E7A
```
