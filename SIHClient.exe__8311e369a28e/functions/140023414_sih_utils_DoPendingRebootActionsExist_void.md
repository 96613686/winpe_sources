# sih::utils::DoPendingRebootActionsExist(void)

- ea: `0x140023414`
- end: `0x140023503`
- name: `?DoPendingRebootActionsExist@utils@sih@@YA_NXZ`
- size: `239`
- prototype: `bool __fastcall(sih::utils *this, __int64, __int64, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004540`
- `0x140004e10`

## callees

- `0x1400176fc`
- `0x140018394`
- `0x140023414`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400234e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400234e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002347f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002347f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400234bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400234bf`

## pseudocode

```c
bool __fastcall sih::utils::DoPendingRebootActionsExist(sih::utils *this, __int64 a2, __int64 a3, wchar_t **a4)
{
  const WCHAR *RegKeyPath; // rdi
  __int64 v5; // rcx
  signed int v6; // ebx
  LSTATUS v7; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  RegKeyPath = (const WCHAR *)GetRegKeyPath(29, a2, a3, a4);
  Type = 0;
  samDesired = 1;
  v6 = SetRegistryType(v5, &samDesired);
  if ( v6 >= 0 )
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, samDesired, &hKey);
    if ( v7 || (v7 = RegQueryValueExW(hKey, L"PendingRebootActions", 0, &Type, 0, 0)) != 0 )
    {
      v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 <= 0 )
        v6 = v7;
    }
    else if ( Type != 1 )
    {
      v6 = -2147024883;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6 == 0;
}

```

## disassembly

```asm
0x140023414  mov     [rsp+arg_0], rbx
0x140023419  push    rdi
0x14002341a  sub     rsp, 50h
0x14002341e  mov     rax, cs:__security_cookie
0x140023425  xor     rax, rsp
0x140023428  mov     [rsp+58h+var_10], rax
0x14002342d  mov     ecx, 1Dh
0x140023432  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x140023437  lea     rdx, [rsp+58h+samDesired]
0x14002343c  mov     [rsp+58h+hKey], 0
0x140023445  mov     rdi, rax
0x140023448  mov     [rsp+58h+Type], 0
0x140023450  mov     [rsp+58h+samDesired], 1
0x140023458  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x14002345d  mov     ebx, eax
0x14002345f  test    eax, eax
0x140023461  js      short loc_1400234D6
0x140023463  mov     r9d, [rsp+58h+samDesired]; samDesired
0x140023468  lea     rax, [rsp+58h+hKey]
0x14002346d  xor     r8d, r8d; ulOptions
0x140023470  mov     [rsp+58h+phkResult], rax; phkResult
0x140023475  mov     rdx, rdi; lpSubKey
0x140023478  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002347f  call    cs:__imp_RegOpenKeyExW
0x140023485  test    eax, eax
0x140023487  jz      short loc_140023499
0x140023489  movzx   ebx, ax
0x14002348c  or      ebx, 80070000h
0x140023492  test    eax, eax
0x140023494  cmovle  ebx, eax
0x140023497  jmp     short loc_1400234D6
0x140023499  mov     rcx, [rsp+58h+hKey]; hKey
0x14002349e  lea     r9, [rsp+58h+Type]; lpType
0x1400234a3  mov     [rsp+58h+lpcbData], 0; lpcbData
0x1400234ac  lea     rdx, ValueName; "PendingRebootActions"
0x1400234b3  xor     r8d, r8d; lpReserved
0x1400234b6  mov     [rsp+58h+phkResult], 0; lpData
0x1400234bf  call    cs:__imp_RegQueryValueExW
0x1400234c5  test    eax, eax
0x1400234c7  jnz     short loc_140023489
0x1400234c9  cmp     [rsp+58h+Type], 1
0x1400234ce  mov     eax, 8007000Dh
0x1400234d3  cmovnz  ebx, eax
0x1400234d6  mov     rcx, [rsp+58h+hKey]; hKey
0x1400234db  test    rcx, rcx
0x1400234de  jz      short loc_1400234E6
0x1400234e0  call    cs:__imp_RegCloseKey
0x1400234e6  test    ebx, ebx
0x1400234e8  setz    al
0x1400234eb  mov     rcx, [rsp+58h+var_10]
0x1400234f0  xor     rcx, rsp; StackCookie
0x1400234f3  call    __security_check_cookie
0x1400234f8  mov     rbx, [rsp+58h+arg_0]
0x1400234fd  add     rsp, 50h
0x140023501  pop     rdi
0x140023502  retn
```
