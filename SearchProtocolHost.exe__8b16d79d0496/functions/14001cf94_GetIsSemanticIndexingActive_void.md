# GetIsSemanticIndexingActive(void)

- ea: `0x14001cf94`
- end: `0x14001d043`
- name: `?GetIsSemanticIndexingActive@@YAHXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014c94`

## callees

- `0x140005240`
- `0x14001cf94`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001d01e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001d01e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001d003`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001d003`

## pseudocode

```c
__int64 __fastcall GetIsSemanticIndexingActive(const wchar_t *a1)
{
  bool v1; // al
  wchar_t *v2; // rdx
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // sf
  unsigned int phkResult; // [rsp+20h] [rbp-248h]
  HKEY hKey[2]; // [rsp+30h] [rbp-238h] BYREF
  wchar_t v9[264]; // [rsp+40h] [rbp-228h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  v1 = MapRegistryKeyPath(
         a1,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer\\IsSemanticIndexingActive",
         v9,
         phkResult);
  v2 = v9;
  if ( !v1 )
    v2 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search\\SemanticIndexer\\IsSemanticIndexingActive";
  v3 = 1;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 1u, hKey);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( v5 )
    return 0;
  else
    RegCloseKey(hKey[0]);
  return v3;
}

```

## disassembly

```asm
0x14001cf94  push    rbx
0x14001cf96  sub     rsp, 260h
0x14001cf9d  mov     [rsp+268h+var_230], 0FFFFFFFFFFFFFFFEh
0x14001cfa6  mov     rax, cs:__security_cookie
0x14001cfad  xor     rax, rsp
0x14001cfb0  mov     [rsp+268h+var_18], rax
0x14001cfb8  mov     [rsp+268h+hKey], 0
0x14001cfc1  lea     r9, [rsp+268h+var_228]; wchar_t *
0x14001cfc6  lea     rbx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows Search\\Se"...
0x14001cfcd  mov     r8, rbx; wchar_t *
0x14001cfd0  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14001cfd7  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x14001cfdc  lea     rdx, [rsp+268h+var_228]
0x14001cfe1  test    al, al
0x14001cfe3  cmovz   rdx, rbx; lpSubKey
0x14001cfe7  lea     rax, [rsp+268h+hKey]
0x14001cfec  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x14001cff1  mov     ebx, 1
0x14001cff6  mov     r9d, ebx; samDesired
0x14001cff9  xor     r8d, r8d; ulOptions
0x14001cffc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001d003  call    cs:__imp_RegOpenKeyExW
0x14001d009  test    eax, eax
0x14001d00b  jle     short loc_14001D017
0x14001d00d  movzx   eax, ax
0x14001d010  or      eax, 80070000h
0x14001d015  test    eax, eax
0x14001d017  js      short loc_14001D026
0x14001d019  mov     rcx, [rsp+268h+hKey]; hKey
0x14001d01e  call    cs:__imp_RegCloseKey
0x14001d024  jmp     short loc_14001D028
0x14001d026  xor     ebx, ebx
0x14001d028  mov     eax, ebx
0x14001d02a  mov     rcx, [rsp+268h+var_18]
0x14001d032  xor     rcx, rsp; StackCookie
0x14001d035  call    __security_check_cookie
0x14001d03a  add     rsp, 260h
0x14001d041  pop     rbx
0x14001d042  retn
```
