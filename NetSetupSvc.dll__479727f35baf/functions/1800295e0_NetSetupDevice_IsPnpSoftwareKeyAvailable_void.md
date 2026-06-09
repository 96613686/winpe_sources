# NetSetupDevice::IsPnpSoftwareKeyAvailable(void)

- ea: `0x1800295e0`
- end: `0x18002965c`
- name: `?IsPnpSoftwareKeyAvailable@NetSetupDevice@@QEAA_NXZ`
- size: `124`
- prototype: `char __fastcall(NetSetupDevice *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001e828`
- `0x18001eb14`

## callees

- `0x1800027c0`
- `0x18002900c`
- `0x1800295e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029636`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180029627`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180029627`

## pseudocode

```c
char __fastcall NetSetupDevice::IsPnpSoftwareKeyAvailable(NetSetupDevice *this)
{
  char v2; // di
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  NetSetupDevice::EnsureDeviceInstance(this);
  v2 = 1;
  if ( CM_Open_DevNode_Key(*(_DWORD *)this, 1u, 0, 1u, &hKey, 1u) )
    return 0;
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800295e0  mov     [rsp+arg_8], rbx
0x1800295e5  push    rdi
0x1800295e6  sub     rsp, 40h
0x1800295ea  mov     rax, cs:__security_cookie
0x1800295f1  xor     rax, rsp
0x1800295f4  mov     [rsp+48h+var_10], rax
0x1800295f9  mov     rbx, rcx
0x1800295fc  mov     [rsp+48h+hKey], 0
0x180029605  call    ?EnsureDeviceInstance@NetSetupDevice@@AEAAXXZ; NetSetupDevice::EnsureDeviceInstance(void)
0x18002960a  mov     ecx, [rbx]; dnDevNode
0x18002960c  lea     rax, [rsp+48h+hKey]
0x180029611  mov     edi, 1
0x180029616  xor     r8d, r8d; ulHardwareProfile
0x180029619  mov     [rsp+48h+ulFlags], edi; ulFlags
0x18002961d  mov     r9d, edi; Disposition
0x180029620  mov     edx, edi; samDesired
0x180029622  mov     [rsp+48h+phkDevice], rax; phkDevice
0x180029627  call    cs:__imp_CM_Open_DevNode_Key
0x18002962d  test    eax, eax
0x18002962f  jnz     short loc_18002963E
0x180029631  mov     rcx, [rsp+48h+hKey]; hKey
0x180029636  call    cs:__imp_RegCloseKey
0x18002963c  jmp     short loc_180029641
0x18002963e  xor     dil, dil
0x180029641  mov     al, dil
0x180029644  mov     rcx, [rsp+48h+var_10]
0x180029649  xor     rcx, rsp; StackCookie
0x18002964c  call    __security_check_cookie
0x180029651  mov     rbx, [rsp+48h+arg_8]
0x180029656  add     rsp, 40h
0x18002965a  pop     rdi
0x18002965b  retn
```
