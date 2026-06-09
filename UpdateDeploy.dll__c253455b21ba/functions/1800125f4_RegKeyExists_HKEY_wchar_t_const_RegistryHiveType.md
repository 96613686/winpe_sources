# RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)

- ea: `0x1800125f4`
- end: `0x18001268c`
- name: `?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z`
- size: `152`
- prototype: `int __high(HKEY, const wchar_t *, enum RegistryHiveType)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013494`

## callees

- `0x180011cb8`
- `0x1800125f4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001264d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001264d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001266c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001266c`

## pseudocode

```c
__int64 __fastcall RegKeyExists(__int64 a1, const WCHAR *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 1;
  v3 = SetRegistryType(a1, &samDesired);
  if ( v3 >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( v4 )
    {
      v3 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        return (unsigned int)v4;
    }
    else
    {
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800125f4  mov     [rsp+arg_0], rbx
0x1800125f9  push    rdi
0x1800125fa  sub     rsp, 50h
0x1800125fe  mov     rax, cs:__security_cookie
0x180012605  xor     rax, rsp
0x180012608  mov     [rsp+58h+var_18], rax
0x18001260d  mov     rdi, rdx
0x180012610  mov     [rsp+58h+hKey], 0
0x180012619  lea     rdx, [rsp+58h+samDesired]
0x18001261e  mov     [rsp+58h+samDesired], 1
0x180012626  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18001262b  mov     ebx, eax
0x18001262d  test    eax, eax
0x18001262f  js      short loc_180012672
0x180012631  mov     r9d, [rsp+58h+samDesired]; samDesired
0x180012636  lea     rax, [rsp+58h+hKey]
0x18001263b  xor     r8d, r8d; ulOptions
0x18001263e  mov     [rsp+58h+phkResult], rax; phkResult
0x180012643  mov     rdx, rdi; lpSubKey
0x180012646  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001264d  call    cs:__imp_RegOpenKeyExW
0x180012653  test    eax, eax
0x180012655  jz      short loc_180012667
0x180012657  movzx   ebx, ax
0x18001265a  or      ebx, 80070000h
0x180012660  test    eax, eax
0x180012662  cmovle  ebx, eax
0x180012665  jmp     short loc_180012672
0x180012667  mov     rcx, [rsp+58h+hKey]; hKey
0x18001266c  call    cs:__imp_RegCloseKey
0x180012672  mov     eax, ebx
0x180012674  mov     rcx, [rsp+58h+var_18]
0x180012679  xor     rcx, rsp; StackCookie
0x18001267c  call    __security_check_cookie
0x180012681  mov     rbx, [rsp+58h+arg_0]
0x180012686  add     rsp, 50h
0x18001268a  pop     rdi
0x18001268b  retn
```
