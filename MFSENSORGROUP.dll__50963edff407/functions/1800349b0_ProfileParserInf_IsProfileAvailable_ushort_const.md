# ProfileParserInf::IsProfileAvailable(ushort const *)

- ea: `0x1800349b0`
- end: `0x180034a46`
- name: `?IsProfileAvailable@ProfileParserInf@@SAHPEBG@Z`
- size: `150`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007908`

## callees

- `0x1800349b0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800349dd`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800349dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034a1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034a1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a38`

## pseudocode

```c
_BOOL8 __fastcall ProfileParserInf::IsProfileAvailable(const unsigned __int16 *a1)
{
  BOOL v1; // ebx
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  pcbData = 0;
  if ( CM_Open_Device_Interface_KeyW(a1, 0x20019u, 1u, &hkey, 0) )
  {
    return 0;
  }
  else
  {
    v1 = RegGetValueW(hkey, 0, L"OEMCameraProfiles", 2u, 0, 0, &pcbData) == 0;
    if ( hkey && hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hkey);
  }
  return v1;
}

```

## disassembly

```asm
0x1800349b0  mov     rax, rsp
0x1800349b3  push    rbx
0x1800349b4  sub     rsp, 40h
0x1800349b8  lea     r9, [rax+18h]; phkDeviceInterface
0x1800349bc  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800349c4  mov     edx, 20019h; samDesired
0x1800349c9  mov     dword ptr [rax+10h], 0
0x1800349d0  mov     r8d, 1; Disposition
0x1800349d6  mov     dword ptr [rax-28h], 0
0x1800349dd  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x1800349e3  test    eax, eax
0x1800349e5  jz      short loc_1800349EB
0x1800349e7  xor     ebx, ebx
0x1800349e9  jmp     short loc_180034A3E
0x1800349eb  mov     rcx, [rsp+48h+hkey]; hkey
0x1800349f0  lea     rax, [rsp+48h+arg_8]
0x1800349f5  mov     [rsp+48h+pcbData], rax; pcbData
0x1800349fa  lea     r8, aOemcameraprofi; "OEMCameraProfiles"
0x180034a01  mov     [rsp+48h+pvData], 0; pvData
0x180034a0a  mov     r9d, 2; dwFlags
0x180034a10  xor     edx, edx; lpSubKey
0x180034a12  mov     [rsp+48h+pdwType], 0; pdwType
0x180034a1b  call    cs:__imp_RegGetValueW
0x180034a21  mov     rcx, [rsp+48h+hkey]; hKey
0x180034a26  xor     ebx, ebx
0x180034a28  test    eax, eax
0x180034a2a  setz    bl
0x180034a2d  test    rcx, rcx
0x180034a30  jz      short loc_180034A3E
0x180034a32  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180034a36  jz      short loc_180034A3E
0x180034a38  call    cs:__imp_RegCloseKey
0x180034a3e  mov     eax, ebx
0x180034a40  add     rsp, 40h
0x180034a44  pop     rbx
0x180034a45  retn
```
