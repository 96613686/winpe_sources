# NetSetupService::OpenCurrentControlSetKey(void)

- ea: `0x18000b1d4`
- end: `0x18000b2b7`
- name: `?OpenCurrentControlSetKey@NetSetupService@@AEAA?AVRegistryKey@@XZ`
- size: `227`
- prototype: `RegistryKey *__fastcall(__int64, RegistryKey *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800088d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x18000b1d4`
- `0x180026958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b228`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b228`

## pseudocode

```c
RegistryKey *__fastcall NetSetupService::OpenCurrentControlSetKey(__int64 a1, RegistryKey *a2)
{
  unsigned int v3; // edi
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-F0h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp-20h] BYREF

  phkResult = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet", 0, 0xFu, &phkResult);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v3);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v3);
    throw (Win32Exception *)pExceptionObject;
  }
  RegistryKey::RegistryKey(a2, phkResult);
  return a2;
}

```

## disassembly

```asm
0x18000b1d4  mov     r11, rsp
0x18000b1d7  mov     [r11+8], rbx
0x18000b1db  push    rdi
0x18000b1dc  sub     rsp, 120h
0x18000b1e3  mov     rax, cs:__security_cookie
0x18000b1ea  xor     rax, rsp
0x18000b1ed  mov     [rsp+128h+var_18], rax
0x18000b1f5  mov     [rsp+128h+var_20], rdx
0x18000b1fd  lea     rax, [r11-20h]
0x18000b201  mov     rbx, rdx
0x18000b204  mov     [rsp+128h+phkResult], rax; phkResult
0x18000b209  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet"
0x18000b210  mov     qword ptr [r11-20h], 0
0x18000b218  mov     r9d, 0Fh; samDesired
0x18000b21e  xor     r8d, r8d; ulOptions
0x18000b221  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b228  call    cs:__imp_RegOpenKeyExW
0x18000b22e  mov     edi, eax
0x18000b230  test    eax, eax
0x18000b232  jz      short loc_18000B283
0x18000b234  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b23b  lea     rax, WPP_GLOBAL_Control
0x18000b242  cmp     rcx, rax
0x18000b245  jz      short loc_18000B265
0x18000b247  cmp     byte ptr [rcx+19h], 2
0x18000b24b  jb      short loc_18000B265
0x18000b24d  mov     rcx, [rcx+10h]
0x18000b251  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000b258  mov     edx, 14h
0x18000b25d  mov     r9d, edi
0x18000b260  call    WPP_SF_d
0x18000b265  mov     edx, edi; int
0x18000b267  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18000b26c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000b271  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000b278  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18000b27d  call    _CxxThrowException_0
0x18000b283  mov     rdx, [rsp+128h+var_20]; HKEY
0x18000b28b  mov     rcx, rbx; this
0x18000b28e  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000b293  mov     rax, rbx
0x18000b296  mov     rcx, [rsp+128h+var_18]
0x18000b29e  xor     rcx, rsp; StackCookie
0x18000b2a1  call    __security_check_cookie
0x18000b2a6  mov     rbx, [rsp+128h+arg_0]
0x18000b2ae  add     rsp, 120h
0x18000b2b5  pop     rdi
0x18000b2b6  retn
```
