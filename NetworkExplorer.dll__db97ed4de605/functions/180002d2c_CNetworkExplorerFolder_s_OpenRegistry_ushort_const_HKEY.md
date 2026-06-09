# CNetworkExplorerFolder::s_OpenRegistry(ushort const *,HKEY__ * *)

- ea: `0x180002d2c`
- end: `0x180002db4`
- name: `?s_OpenRegistry@CNetworkExplorerFolder@@CAJPEBGPEAPEAUHKEY__@@@Z`
- size: `136`
- prototype: `static int(const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b54`
- `0x180002b48`

## callees

- `0x180002d2c`
- `0x180003570`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002d88`

## string_xrefs

- `0x180002d54`: `NetworkExplorerPlugins\%s`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::s_OpenRegistry(const unsigned __int16 *a1, HKEY *a2)
{
  __int64 result; // rax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  *a2 = 0;
  result = StringCchPrintfW(SubKey, 0x104u, L"NetworkExplorerPlugins\\%s", a1);
  if ( (int)result >= 0 )
    return RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, a2) != 0 ? 0x80004005 : 0;
  return result;
}

```

## disassembly

```asm
0x180002d2c  push    rbx
0x180002d2e  sub     rsp, 250h
0x180002d35  mov     rax, cs:__security_cookie
0x180002d3c  xor     rax, rsp
0x180002d3f  mov     [rsp+258h+var_18], rax
0x180002d47  mov     rbx, rdx
0x180002d4a  mov     qword ptr [rdx], 0
0x180002d51  mov     r9, rcx
0x180002d54  lea     r8, aNetworkexplore_2; "NetworkExplorerPlugins\\%s"
0x180002d5b  mov     edx, 104h; unsigned __int64
0x180002d60  lea     rcx, [rsp+258h+SubKey]; unsigned __int16 *
0x180002d65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d6a  test    eax, eax
0x180002d6c  js      short loc_180002D9B
0x180002d6e  mov     r9d, 20019h; samDesired
0x180002d74  mov     [rsp+258h+phkResult], rbx; phkResult
0x180002d79  xor     r8d, r8d; ulOptions
0x180002d7c  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180002d81  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002d88  call    cs:__imp_RegOpenKeyExW
0x180002d8e  xor     ecx, ecx
0x180002d90  sub     ecx, eax
0x180002d92  neg     ecx
0x180002d94  sbb     eax, eax
0x180002d96  and     eax, 80004005h
0x180002d9b  mov     rcx, [rsp+258h+var_18]
0x180002da3  xor     rcx, rsp; StackCookie
0x180002da6  call    __security_check_cookie
0x180002dab  add     rsp, 250h
0x180002db2  pop     rbx
0x180002db3  retn
```
