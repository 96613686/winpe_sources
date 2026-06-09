# RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)

- ea: `0x1400182fc`
- end: `0x14001838c`
- name: `?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003e2a4`

## callees

- `0x1400176fc`
- `0x1400182fc`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018371`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018352`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018352`

## pseudocode

```c
__int64 __fastcall RegKeyExists(int a1)
{
  int v1; // ebx
  LSTATUS v2; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 1;
  v1 = SetRegistryType(a1, &samDesired);
  if ( v1 >= 0 )
  {
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, samDesired, &hKey);
    if ( v2 )
    {
      v1 = (unsigned __int16)v2 | 0x80070000;
      if ( v2 <= 0 )
        return (unsigned int)v2;
    }
    else
    {
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400182fc  push    rbx
0x1400182fe  sub     rsp, 50h
0x140018302  mov     rax, cs:__security_cookie
0x140018309  xor     rax, rsp
0x14001830c  mov     [rsp+58h+var_18], rax
0x140018311  lea     rdx, [rsp+58h+samDesired]
0x140018316  mov     [rsp+58h+hKey], 0
0x14001831f  mov     [rsp+58h+samDesired], 1
0x140018327  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x14001832c  mov     ebx, eax
0x14001832e  test    eax, eax
0x140018330  js      short loc_140018377
0x140018332  mov     r9d, [rsp+58h+samDesired]; samDesired
0x140018337  lea     rax, [rsp+58h+hKey]
0x14001833c  xor     r8d, r8d; ulOptions
0x14001833f  mov     [rsp+58h+phkResult], rax; phkResult
0x140018344  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x14001834b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018352  call    cs:__imp_RegOpenKeyExW
0x140018358  test    eax, eax
0x14001835a  jz      short loc_14001836C
0x14001835c  movzx   ebx, ax
0x14001835f  or      ebx, 80070000h
0x140018365  test    eax, eax
0x140018367  cmovle  ebx, eax
0x14001836a  jmp     short loc_140018377
0x14001836c  mov     rcx, [rsp+58h+hKey]; hKey
0x140018371  call    cs:__imp_RegCloseKey
0x140018377  mov     eax, ebx
0x140018379  mov     rcx, [rsp+58h+var_18]
0x14001837e  xor     rcx, rsp; StackCookie
0x140018381  call    __security_check_cookie
0x140018386  add     rsp, 50h
0x14001838a  pop     rbx
0x14001838b  retn
```
