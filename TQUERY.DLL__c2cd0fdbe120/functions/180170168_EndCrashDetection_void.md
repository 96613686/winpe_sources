# EndCrashDetection(void)

- ea: `0x180170168`
- end: `0x180170253`
- name: `?EndCrashDetection@@YAXXZ`
- size: `235`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801303ac`
- `0x1802ac0f9`

## callees

- `0x180170168`
- `0x180188d90`
- `0x1801b9afc`
- `0x1801b9c34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801701f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801701f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180170234`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180170234`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180170229`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180170229`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180170195`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180170195`

## pseudocode

```c
void __fastcall EndCrashDetection(__int64 a1)
{
  const wchar_t *v1; // rcx
  bool v2; // al
  wchar_t *v3; // rdx
  BYTE Data[8]; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  struct CSearchRegistryRedirectHelper *v6; // [rsp+40h] [rbp-238h] BYREF
  wchar_t v7[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  v6 = 0;
  v2 = (unsigned __int8)RtlIsStateSeparationEnabled(a1)
    && GetSearchRegistryRedirect(v1, &v6)
    && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath(
              (const wchar_t *)v6,
              L"SOFTWARE\\Microsoft\\Windows Search\\Databases\\Windows",
              v7) >= 0;
  v3 = v7;
  if ( !v2 )
    v3 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search\\Databases\\Windows";
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 3u, &hKey) )
  {
    RegSetValueExW(hKey, L"DBInitFailureCount", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180170168  push    rdi
0x18017016a  sub     rsp, 270h
0x180170171  mov     rax, cs:__security_cookie
0x180170178  xor     rax, rsp
0x18017017b  mov     [rsp+278h+var_18], rax
0x180170183  mov     [rsp+278h+hKey], 0
0x18017018c  mov     [rsp+278h+var_238], 0
0x180170195  call    cs:__imp_RtlIsStateSeparationEnabled
0x18017019b  lea     rdi, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Search\\Da"...
0x1801701a2  test    al, al
0x1801701a4  jz      short loc_1801701CE
0x1801701a6  lea     rdx, [rsp+278h+var_238]; struct CSearchRegistryRedirectHelper **
0x1801701ab  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x1801701b0  test    al, al
0x1801701b2  jz      short loc_1801701CE
0x1801701b4  mov     rcx, [rsp+278h+var_238]; this
0x1801701b9  lea     r8, [rsp+278h+var_228]; wchar_t *
0x1801701be  mov     rdx, rdi; wchar_t *
0x1801701c1  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x1801701c6  test    eax, eax
0x1801701c8  js      short loc_1801701CE
0x1801701ca  mov     al, 1
0x1801701cc  jmp     short loc_1801701D0
0x1801701ce  xor     al, al
0x1801701d0  test    al, al
0x1801701d2  lea     rdx, [rsp+278h+var_228]
0x1801701d7  lea     rax, [rsp+278h+hKey]
0x1801701dc  mov     r9d, 3; samDesired
0x1801701e2  cmovz   rdx, rdi; lpSubKey
0x1801701e6  mov     [rsp+278h+phkResult], rax; phkResult
0x1801701eb  xor     r8d, r8d; ulOptions
0x1801701ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801701f5  call    cs:__imp_RegOpenKeyExW
0x1801701fb  mov     dword ptr [rsp+278h+Data], 0
0x180170203  test    eax, eax
0x180170205  jnz     short loc_18017023A
0x180170207  mov     rcx, [rsp+278h+hKey]; hKey
0x18017020c  lea     r9d, [rax+4]; dwType
0x180170210  lea     rax, [rsp+278h+Data]
0x180170215  mov     [rsp+278h+cbData], r9d; cbData
0x18017021a  xor     r8d, r8d; Reserved
0x18017021d  mov     [rsp+278h+phkResult], rax; lpData
0x180170222  lea     rdx, aDbinitfailurec; "DBInitFailureCount"
0x180170229  call    cs:__imp_RegSetValueExW
0x18017022f  mov     rcx, [rsp+278h+hKey]; hKey
0x180170234  call    cs:__imp_RegCloseKey
0x18017023a  mov     rcx, [rsp+278h+var_18]
0x180170242  xor     rcx, rsp; StackCookie
0x180170245  call    __security_check_cookie
0x18017024a  add     rsp, 270h
0x180170251  pop     rdi
0x180170252  retn
```
