# IsAppPhonebookEx

- ea: `0x18008fac0`
- end: `0x18008fc0f`
- name: `IsAppPhonebookEx`
- size: `335`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008fd24`

## callees

- `0x18008f688`
- `0x18008fac0`
- `0x1800e7206`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18008fae2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18008fae2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008fb94`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008fb94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fb16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fb16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fbe6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fbe6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fbf4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fbf4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008fbb8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008fbb8`

## string_xrefs

- `0x18008fae8`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x18008faf7`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`

## pseudocode

```c
__int64 __fastcall IsAppPhonebookEx(PCNZWCH lpString2)
{
  WCHAR *v2; // rbx
  unsigned int v3; // ebp
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  WCHAR *v6; // rax
  LSTATUS v7; // edi
  DWORD v8; // esi
  LSTATUS v9; // eax
  DWORD cchValueName; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(lpString2);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey) )
  {
    v6 = (WCHAR *)DebugAlloc(0x8000);
    v2 = v6;
    if ( v6 )
    {
      v7 = 0;
      memset_0(v6, 0, 0x8000u);
      do
      {
LABEL_6:
        v8 = 0;
        if ( v7 == 259 )
          break;
        while ( 1 )
        {
          cchValueName = 0x3FFF;
          v9 = RegEnumValueW(hKey, v8, v2, &cchValueName, 0, 0, 0, 0);
          v7 = v9;
          if ( v9 )
            break;
          if ( CompareStringW(0x7Fu, 1u, v2, -1, lpString2, -1) == 2 )
          {
            v3 = 1;
            goto LABEL_6;
          }
          ++v8;
        }
      }
      while ( v9 != 259 );
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    GlobalFree(v2);
  return v3;
}

```

## disassembly

```asm
0x18008fac0  mov     [rsp+arg_0], rbx
0x18008fac5  mov     [rsp+arg_18], rbp
0x18008faca  push    rsi
0x18008facb  push    rdi
0x18008facc  push    r14
0x18008face  sub     rsp, 40h
0x18008fad2  mov     r14, rcx
0x18008fad5  mov     [rsp+58h+hKey], 0
0x18008fade  xor     ebx, ebx
0x18008fae0  xor     ebp, ebp
0x18008fae2  call    cs:__imp_RtlIsStateSeparationEnabled
0x18008fae8  lea     rcx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18008faef  mov     r9d, 20019h; samDesired
0x18008faf5  test    al, al
0x18008faf7  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18008fafe  lea     rax, [rsp+58h+hKey]
0x18008fb03  cmovz   rdx, rcx; lpSubKey
0x18008fb07  mov     [rsp+58h+phkResult], rax; phkResult
0x18008fb0c  xor     r8d, r8d; ulOptions
0x18008fb0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008fb16  call    cs:__imp_RegOpenKeyExW
0x18008fb1c  test    eax, eax
0x18008fb1e  jnz     loc_18008FBDC
0x18008fb24  mov     esi, 8000h
0x18008fb29  mov     ecx, esi
0x18008fb2b  call    DebugAlloc
0x18008fb30  mov     rbx, rax
0x18008fb33  test    rax, rax
0x18008fb36  jz      loc_18008FBDC
0x18008fb3c  xor     edi, edi
0x18008fb3e  mov     r8d, esi; Size
0x18008fb41  xor     edx, edx; Val
0x18008fb43  mov     rcx, rax; void *
0x18008fb46  call    memset_0
0x18008fb4b  xor     esi, esi
0x18008fb4d  cmp     edi, 103h
0x18008fb53  jz      loc_18008FBDC
0x18008fb59  mov     rcx, [rsp+58h+hKey]; hKey
0x18008fb5e  lea     r9, [rsp+58h+cchValueName]; lpcchValueName
0x18008fb63  mov     [rsp+58h+lpcbData], 0; lpcbData
0x18008fb6c  mov     r8, rbx; lpValueName
0x18008fb6f  mov     [rsp+58h+lpData], 0; lpData
0x18008fb78  mov     edx, esi; dwIndex
0x18008fb7a  mov     [rsp+58h+lpType], 0; lpType
0x18008fb83  mov     [rsp+58h+phkResult], 0; lpReserved
0x18008fb8c  mov     [rsp+58h+cchValueName], 3FFFh
0x18008fb94  call    cs:__imp_RegEnumValueW
0x18008fb9a  mov     edi, eax
0x18008fb9c  test    eax, eax
0x18008fb9e  jnz     short loc_18008FBD1
0x18008fba0  or      eax, 0FFFFFFFFh
0x18008fba3  lea     edx, [rdi+1]; dwCmpFlags
0x18008fba6  mov     dword ptr [rsp+58h+lpType], eax; cchCount2
0x18008fbaa  lea     ecx, [rdi+7Fh]; Locale
0x18008fbad  mov     r9d, eax; cchCount1
0x18008fbb0  mov     [rsp+58h+phkResult], r14; lpString2
0x18008fbb5  mov     r8, rbx; lpString1
0x18008fbb8  call    cs:__imp_CompareStringW
0x18008fbbe  cmp     eax, 2
0x18008fbc1  jz      short loc_18008FBC7
0x18008fbc3  inc     esi
0x18008fbc5  jmp     short loc_18008FB59
0x18008fbc7  mov     ebp, 1
0x18008fbcc  jmp     loc_18008FB4B
0x18008fbd1  cmp     eax, 103h
0x18008fbd6  jnz     loc_18008FB4B
0x18008fbdc  mov     rcx, [rsp+58h+hKey]; hKey
0x18008fbe1  test    rcx, rcx
0x18008fbe4  jz      short loc_18008FBEC
0x18008fbe6  call    cs:__imp_RegCloseKey
0x18008fbec  test    rbx, rbx
0x18008fbef  jz      short loc_18008FBFA
0x18008fbf1  mov     rcx, rbx; hMem
0x18008fbf4  call    cs:__imp_GlobalFree
0x18008fbfa  mov     rbx, [rsp+58h+arg_0]
0x18008fbff  mov     eax, ebp
0x18008fc01  mov     rbp, [rsp+58h+arg_18]
0x18008fc06  add     rsp, 40h
0x18008fc0a  pop     r14
0x18008fc0c  pop     rdi
0x18008fc0d  pop     rsi
0x18008fc0e  retn
```
