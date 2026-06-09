# FvepSetVolumeEncryptedCached

- ea: `0x18005186c`
- end: `0x1800519c0`
- name: `FvepSetVolumeEncryptedCached`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051660`

## callees

- `0x180050ea4`
- `0x1800514d8`
- `0x18005186c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005198d`
- `KERNEL32!HeapFree` at `0x18005198d`
- `KERNEL32!GetProcessHeap` at `0x18005197f`
- `KERNEL32!GetProcessHeap` at `0x18005197f`
- `ADVAPI32!RegSetValueExW` at `0x180051974`
- `ADVAPI32!RegSetValueExW` at `0x180051974`
- `ADVAPI32!RegCreateKeyExW` at `0x180051908`
- `ADVAPI32!RegCreateKeyExW` at `0x18005194e`
- `ADVAPI32!RegCreateKeyExW` at `0x180051908`
- `ADVAPI32!RegCreateKeyExW` at `0x18005194e`
- `ADVAPI32!RegCloseKey` at `0x18005199c`
- `ADVAPI32!RegCloseKey` at `0x1800519b3`
- `ADVAPI32!RegCloseKey` at `0x18005199c`
- `ADVAPI32!RegCloseKey` at `0x1800519b3`

## string_xrefs

- `0x180051923`: `Cache`

## pseudocode

```c
int __fastcall FvepSetVolumeEncryptedCached(STRSAFE_PCNZWCH psz, int a2)
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
  if ( psz )
  {
    result = FvepIsNonDriverEncryptionStatusCachingAllowed();
    if ( result )
    {
      result = FvepConvertVolumeNameToCacheValueName(psz);
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
0x18005186c  push    rbp
0x18005186e  push    rbx
0x18005186f  mov     rbp, rsp
0x180051872  sub     rsp, 58h
0x180051876  xor     eax, eax
0x180051878  mov     [rbp+hKey], 0
0x180051880  test    edx, edx
0x180051882  mov     [rbp+arg_0], 0
0x18005188a  mov     rbx, rcx
0x18005188d  mov     [rbp+lpValueName], 0
0x180051895  setnz   al
0x180051898  mov     [rbp+Data], eax
0x18005189b  test    rcx, rcx
0x18005189e  jz      loc_1800519B9
0x1800518a4  call    FvepIsNonDriverEncryptionStatusCachingAllowed
0x1800518a9  test    eax, eax
0x1800518ab  jz      loc_180051993
0x1800518b1  lea     rdx, [rbp+lpValueName]
0x1800518b5  mov     rcx, rbx; psz
0x1800518b8  call    FvepConvertVolumeNameToCacheValueName
0x1800518bd  mov     rbx, [rbp+lpValueName]
0x1800518c1  test    eax, eax
0x1800518c3  js      loc_18005197A
0x1800518c9  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800518d2  lea     rax, [rbp+hKey]
0x1800518d6  mov     [rsp+58h+phkResult], rax; phkResult
0x1800518db  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800518e2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800518eb  xor     r9d, r9d; lpClass
0x1800518ee  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800518f6  xor     r8d, r8d; Reserved
0x1800518f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051900  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180051908  call    cs:__imp_RegCreateKeyExW
0x18005190e  test    eax, eax
0x180051910  jnz     short loc_18005197A
0x180051912  mov     rcx, [rbp+hKey]; hKey
0x180051916  lea     rax, [rbp+arg_0]
0x18005191a  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180051923  lea     rdx, aCache; "Cache"
0x18005192a  mov     [rsp+58h+phkResult], rax; phkResult
0x18005192f  xor     r9d, r9d; lpClass
0x180051932  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005193b  xor     r8d, r8d; Reserved
0x18005193e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180051946  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18005194e  call    cs:__imp_RegCreateKeyExW
0x180051954  test    eax, eax
0x180051956  jnz     short loc_18005197A
0x180051958  mov     rcx, [rbp+arg_0]; hKey
0x18005195c  lea     r9d, [rax+4]; dwType
0x180051960  lea     rax, [rbp+Data]
0x180051964  mov     [rsp+58h+samDesired], r9d; cbData
0x180051969  xor     r8d, r8d; Reserved
0x18005196c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180051971  mov     rdx, rbx; lpValueName
0x180051974  call    cs:__imp_RegSetValueExW
0x18005197a  test    rbx, rbx
0x18005197d  jz      short loc_180051993
0x18005197f  call    cs:__imp_GetProcessHeap
0x180051985  mov     r8, rbx; lpMem
0x180051988  xor     edx, edx; dwFlags
0x18005198a  mov     rcx, rax; hHeap
0x18005198d  call    cs:__imp_HeapFree
0x180051993  mov     rcx, [rbp+arg_0]; hKey
0x180051997  test    rcx, rcx
0x18005199a  jz      short loc_1800519AA
0x18005199c  call    cs:__imp_RegCloseKey
0x1800519a2  mov     [rbp+arg_0], 0
0x1800519aa  mov     rcx, [rbp+hKey]; hKey
0x1800519ae  test    rcx, rcx
0x1800519b1  jz      short loc_1800519B9
0x1800519b3  call    cs:__imp_RegCloseKey
0x1800519b9  add     rsp, 58h
0x1800519bd  pop     rbx
0x1800519be  pop     rbp
0x1800519bf  retn
```
