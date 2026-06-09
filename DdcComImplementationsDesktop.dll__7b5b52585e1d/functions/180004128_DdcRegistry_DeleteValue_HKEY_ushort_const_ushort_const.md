# DdcRegistry::DeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180004128`
- end: `0x180004212`
- name: `?DeleteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1@Z`
- size: `234`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030a0`

## callees

- `0x1800026ac`
- `0x180004128`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800041b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800041b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800041ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004162`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004162`

## string_xrefs

- `0x18000419f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::DeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // eax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  int v9; // edx
  int v10; // ecx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
         0,
         2u,
         &hKey);
  v7 = v4;
  if ( v4 == 2 )
    goto LABEL_13;
  if ( v4 )
  {
    if ( v4 > 0 )
      v7 = (unsigned __int16)v4 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        v7,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        6,
        (__int64)"CBR(dwResult == 0L)");
    goto LABEL_14;
  }
  v8 = RegDeleteValueW(hKey, a3);
  v7 = v8;
  if ( (v8 & 0xFFFFFFFD) == 0 )
  {
LABEL_13:
    v7 = 0;
    goto LABEL_14;
  }
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
      17,
      (__int64)"CBR(dwResult == 0L)");
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180004128  mov     r11, rsp
0x18000412b  mov     [r11+8], rbx
0x18000412f  mov     [r11+10h], rdx
0x180004133  push    rdi
0x180004134  sub     rsp, 30h
0x180004138  mov     rdi, r8
0x18000413b  mov     qword ptr [r11+10h], 0
0x180004143  lea     rax, [r11+10h]
0x180004147  xor     r8d, r8d; ulOptions
0x18000414a  mov     r9d, 2; samDesired
0x180004150  mov     [r11-18h], rax
0x180004154  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000415b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004162  call    cs:__imp_RegOpenKeyExW
0x180004168  mov     ebx, eax
0x18000416a  cmp     eax, 2
0x18000416d  jz      loc_1800041F3
0x180004173  test    eax, eax
0x180004175  jz      short loc_1800041B0
0x180004177  jle     short loc_180004182
0x180004179  movzx   ebx, ax
0x18000417c  or      ebx, 80070000h
0x180004182  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004189  jz      short loc_1800041F5
0x18000418b  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x180004192  mov     [rsp+38h+var_10], rax
0x180004197  mov     [rsp+38h+var_18], 306h
0x18000419f  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800041a6  mov     r8d, ebx
0x1800041a9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800041ae  jmp     short loc_1800041F5
0x1800041b0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800041b5  mov     rdx, rdi; lpValueName
0x1800041b8  call    cs:__imp_RegDeleteValueW
0x1800041be  mov     ebx, eax
0x1800041c0  test    eax, 0FFFFFFFDh
0x1800041c5  jz      short loc_1800041F3
0x1800041c7  test    eax, eax
0x1800041c9  jle     short loc_1800041D4
0x1800041cb  movzx   ebx, ax
0x1800041ce  or      ebx, 80070000h
0x1800041d4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800041db  jz      short loc_1800041F5
0x1800041dd  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x1800041e4  mov     [rsp+38h+var_10], rax
0x1800041e9  mov     [rsp+38h+var_18], 311h
0x1800041f1  jmp     short loc_18000419F
0x1800041f3  xor     ebx, ebx
0x1800041f5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800041fa  test    rcx, rcx
0x1800041fd  jz      short loc_180004205
0x1800041ff  call    cs:__imp_RegCloseKey
0x180004205  mov     eax, ebx
0x180004207  mov     rbx, [rsp+38h+arg_0]
0x18000420c  add     rsp, 30h
0x180004210  pop     rdi
0x180004211  retn
```
