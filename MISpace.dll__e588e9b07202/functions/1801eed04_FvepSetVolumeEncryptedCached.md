# FvepSetVolumeEncryptedCached

- ea: `0x1801eed04`
- end: `0x1801eee58`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801eeaf8`

## callees

- `0x1801ee368`
- `0x1801ee970`
- `0x1801eed04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801eee25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801eee25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801eee17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801eee17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801eee34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801eee4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801eee34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801eee4b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801eee0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801eee0c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801eeda0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801eede6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801eeda0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801eede6`

## string_xrefs

- `0x1801eedbb`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(STRSAFE_PCNZWCH pszSrc, int a2)
{
  int result; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp+30h]

  hKey = 0;
  phkResult = 0;
  lpValueName = 0;
  result = a2 != 0;
  Data = result;
  if ( pszSrc )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(pszSrc);
      v4 = (WCHAR *)lpValueName;
      if ( result >= 0 )
      {
        result = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FveDetect",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &hKey,
                   0);
        if ( !result )
        {
          result = RegCreateKeyExW(hKey, L"Cache", 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
          if ( !result )
            result = RegSetValueExW(phkResult, v4, 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, v4);
      }
    }
    if ( phkResult )
    {
      result = RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x1801eed04  push    rbp
0x1801eed06  push    rbx
0x1801eed07  mov     rbp, rsp
0x1801eed0a  sub     rsp, 58h
0x1801eed0e  xor     eax, eax
0x1801eed10  mov     [rbp+hKey], 0
0x1801eed18  test    edx, edx
0x1801eed1a  mov     [rbp+arg_0], 0
0x1801eed22  mov     rbx, rcx
0x1801eed25  mov     [rbp+lpValueName], 0
0x1801eed2d  setnz   al
0x1801eed30  mov     [rbp+Data], eax
0x1801eed33  test    rcx, rcx
0x1801eed36  jz      loc_1801EEE51
0x1801eed3c  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x1801eed41  test    eax, eax
0x1801eed43  jz      loc_1801EEE2B
0x1801eed49  lea     rdx, [rbp+lpValueName]
0x1801eed4d  mov     rcx, rbx; pszSrc
0x1801eed50  call    FvepConvertVolumeNameToCacheValueName
0x1801eed55  mov     rbx, [rbp+lpValueName]
0x1801eed59  test    eax, eax
0x1801eed5b  js      loc_1801EEE12
0x1801eed61  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1801eed6a  lea     rax, [rbp+hKey]
0x1801eed6e  mov     [rsp+58h+phkResult], rax; phkResult
0x1801eed73  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1801eed7a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801eed83  xor     r9d, r9d; lpClass
0x1801eed86  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801eed8e  xor     r8d, r8d; Reserved
0x1801eed91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801eed98  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1801eeda0  call    cs:__imp_RegCreateKeyExW
0x1801eeda6  test    eax, eax
0x1801eeda8  jnz     short loc_1801EEE12
0x1801eedaa  mov     rcx, [rbp+hKey]; hKey
0x1801eedae  lea     rax, [rbp+arg_0]
0x1801eedb2  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1801eedbb  lea     rdx, aCache; "Cache"
0x1801eedc2  mov     [rsp+58h+phkResult], rax; phkResult
0x1801eedc7  xor     r9d, r9d; lpClass
0x1801eedca  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801eedd3  xor     r8d, r8d; Reserved
0x1801eedd6  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1801eedde  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1801eede6  call    cs:__imp_RegCreateKeyExW
0x1801eedec  test    eax, eax
0x1801eedee  jnz     short loc_1801EEE12
0x1801eedf0  mov     rcx, [rbp+arg_0]; hKey
0x1801eedf4  lea     r9d, [rax+4]; dwType
0x1801eedf8  lea     rax, [rbp+Data]
0x1801eedfc  mov     [rsp+58h+samDesired], r9d; cbData
0x1801eee01  xor     r8d, r8d; Reserved
0x1801eee04  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1801eee09  mov     rdx, rbx; lpValueName
0x1801eee0c  call    cs:__imp_RegSetValueExW
0x1801eee12  test    rbx, rbx
0x1801eee15  jz      short loc_1801EEE2B
0x1801eee17  call    cs:__imp_GetProcessHeap
0x1801eee1d  mov     r8, rbx; lpMem
0x1801eee20  xor     edx, edx; dwFlags
0x1801eee22  mov     rcx, rax; hHeap
0x1801eee25  call    cs:__imp_HeapFree
0x1801eee2b  mov     rcx, [rbp+arg_0]; hKey
0x1801eee2f  test    rcx, rcx
0x1801eee32  jz      short loc_1801EEE42
0x1801eee34  call    cs:__imp_RegCloseKey
0x1801eee3a  mov     [rbp+arg_0], 0
0x1801eee42  mov     rcx, [rbp+hKey]; hKey
0x1801eee46  test    rcx, rcx
0x1801eee49  jz      short loc_1801EEE51
0x1801eee4b  call    cs:__imp_RegCloseKey
0x1801eee51  add     rsp, 58h
0x1801eee55  pop     rbx
0x1801eee56  pop     rbp
0x1801eee57  retn
```
