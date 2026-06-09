# UddpGetServiceRegStringValue

- ea: `0x180038e34`
- end: `0x180039032`
- name: `UddpGetServiceRegStringValue`
- size: `510`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, DWORD dwFlags)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18004d604`
- `0x1800b0e88`
- `0x1800b10e8`

## callees

- `0x180012920`
- `0x180038e34`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180039004`
- `ntdll!RtlFreeHeap` at `0x180039004`
- `ntdll!RtlAllocateHeap` at `0x180038f5f`
- `ntdll!RtlAllocateHeap` at `0x180038f5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039016`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039016`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038ece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038fad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038ece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038fad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038e7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038e7a`

## string_xrefs

- `0x180038e6c`: `SYSTEM\CurrentControlSet\Services`
- `0x180038e88`: `Failed to open services key [%d]`
- `0x180038e95`: `UddpGetServiceRegStringValue`
- `0x180038ef1`: `UddpGetServiceRegStringValue`
- `0x180038f31`: `UddpGetServiceRegStringValue`
- `0x180038fd8`: `UddpGetServiceRegStringValue`
- `0x180038fcc`: `Failed to get Service: '%ls' Value: '%ls' [%d]`
- `0x180038ee5`: `Failed to get size for Service: '%ls' Value: '%ls' [%d]`
- `0x180038f1f`: `Empty string for Service: '%ls' Value: '%ls'`

## pseudocode

```c
_WORD *__fastcall UddpGetServiceRegStringValue(LPCWSTR lpSubKey, LPCWSTR lpValue, DWORD dwFlags)
{
  _WORD *pvData; // rbx
  LSTATUS v7; // eax
  LSTATUS ValueW; // eax
  LSTATUS v9; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  LPDWORD pcbData; // [rsp+30h] [rbp-38h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-38h]
  HKEY hkey; // [rsp+40h] [rbp-28h] BYREF
  DWORD v15; // [rsp+88h] [rbp+20h] BYREF

  pvData = 0;
  hkey = 0;
  v15 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services", 0, 1u, &hkey);
  if ( v7 )
  {
    LODWORD(phkResult) = v7;
    AslLogCallPrintf(
      1,
      (unsigned int)"UddpGetServiceRegStringValue",
      425,
      (unsigned int)"Failed to open services key [%d]",
      phkResult);
  }
  else
  {
    ValueW = RegGetValueW(hkey, lpSubKey, lpValue, dwFlags, 0, 0, &v15);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        LODWORD(pcbData) = ValueW;
        AslLogCallPrintf(
          1,
          (unsigned int)"UddpGetServiceRegStringValue",
          439,
          (unsigned int)"Failed to get size for Service: '%ls' Value: '%ls' [%d]",
          lpSubKey,
          lpValue,
          pcbData);
      }
    }
    else if ( v15 >= 4 )
    {
      pvData = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
      if ( pvData )
      {
        v9 = RegGetValueW(hkey, lpSubKey, lpValue, dwFlags, 0, pvData, &v15);
        if ( v9 || v15 < 4 || !*pvData )
        {
          LODWORD(pcbDataa) = v9;
          AslLogCallPrintf(
            1,
            (unsigned int)"UddpGetServiceRegStringValue",
            466,
            (unsigned int)"Failed to get Service: '%ls' Value: '%ls' [%d]",
            lpSubKey,
            lpValue,
            pcbDataa);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvData);
          pvData = 0;
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"UddpGetServiceRegStringValue",
          452,
          (unsigned int)"Failed to allocate memory for '%ls'",
          lpValue);
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"UddpGetServiceRegStringValue",
        446,
        (unsigned int)"Empty string for Service: '%ls' Value: '%ls'",
        lpSubKey,
        lpValue);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return pvData;
}

```

## disassembly

```asm
0x180038e34  mov     rax, rsp
0x180038e37  mov     [rax+8], rbx
0x180038e3b  mov     [rax+10h], rbp
0x180038e3f  push    rsi
0x180038e40  push    rdi
0x180038e41  push    r15
0x180038e43  sub     rsp, 50h
0x180038e47  xor     ebx, ebx
0x180038e49  mov     ebp, r8d
0x180038e4c  mov     [rax-28h], rbx
0x180038e50  mov     rdi, rdx
0x180038e53  mov     [rax+20h], ebx
0x180038e56  lea     rax, [rax-28h]
0x180038e5a  mov     rsi, rcx
0x180038e5d  mov     [rsp+68h+phkResult], rax; phkResult
0x180038e62  lea     r15d, [rbx+1]
0x180038e66  xor     r8d, r8d; ulOptions
0x180038e69  mov     r9d, r15d; samDesired
0x180038e6c  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services"
0x180038e73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038e7a  call    cs:__imp_RegOpenKeyExW
0x180038e80  test    eax, eax
0x180038e82  jz      short loc_180038EA9
0x180038e84  mov     dword ptr [rsp+68h+phkResult], eax
0x180038e88  lea     r9, aFailedToOpenSe; "Failed to open services key [%d]"
0x180038e8f  mov     r8d, 1A9h
0x180038e95  lea     rdx, aUddpgetservice; "UddpGetServiceRegStringValue"
0x180038e9c  mov     ecx, r15d
0x180038e9f  call    AslLogCallPrintf
0x180038ea4  jmp     loc_18003900C
0x180038ea9  mov     rcx, [rsp+68h+hkey]; hkey
0x180038eae  lea     rax, [rsp+68h+arg_18]
0x180038eb6  mov     [rsp+68h+pcbData], rax; pcbData
0x180038ebb  mov     r9d, ebp; dwFlags
0x180038ebe  mov     [rsp+68h+pvData], rbx; pvData
0x180038ec3  mov     r8, rdi; lpValue
0x180038ec6  mov     rdx, rsi; lpSubKey
0x180038ec9  mov     [rsp+68h+phkResult], rbx; pdwType
0x180038ece  call    cs:__imp_RegGetValueW
0x180038ed4  test    eax, eax
0x180038ed6  jz      short loc_180038F10
0x180038ed8  cmp     eax, 2
0x180038edb  jz      loc_18003900C
0x180038ee1  mov     dword ptr [rsp+68h+pcbData], eax
0x180038ee5  lea     r9, aFailedToGetSiz; "Failed to get size for Service: '%ls' V"...
0x180038eec  mov     [rsp+68h+pvData], rdi
0x180038ef1  lea     rdx, aUddpgetservice; "UddpGetServiceRegStringValue"
0x180038ef8  mov     r8d, 1B7h
0x180038efe  mov     [rsp+68h+phkResult], rsi
0x180038f03  mov     ecx, r15d
0x180038f06  call    AslLogCallPrintf
0x180038f0b  jmp     loc_18003900C
0x180038f10  cmp     [rsp+68h+arg_18], 4
0x180038f18  jnb     short loc_180038F45
0x180038f1a  mov     [rsp+68h+pvData], rdi
0x180038f1f  lea     r9, aEmptyStringFor; "Empty string for Service: '%ls' Value: "...
0x180038f26  mov     r8d, 1BEh
0x180038f2c  mov     [rsp+68h+phkResult], rsi
0x180038f31  lea     rdx, aUddpgetservice; "UddpGetServiceRegStringValue"
0x180038f38  mov     ecx, r15d
0x180038f3b  call    AslLogCallPrintf
0x180038f40  jmp     loc_18003900C
0x180038f45  mov     rcx, gs:60h
0x180038f4e  mov     edx, 8; Flags
0x180038f53  mov     r8d, [rsp+68h+arg_18]; Size
0x180038f5b  mov     rcx, [rcx+30h]; HeapHandle
0x180038f5f  call    cs:__imp_RtlAllocateHeap
0x180038f65  mov     rbx, rax
0x180038f68  test    rax, rax
0x180038f6b  jnz     short loc_180038F84
0x180038f6d  mov     [rsp+68h+phkResult], rdi
0x180038f72  lea     r9, aFailedToAlloca_1; "Failed to allocate memory for '%ls'"
0x180038f79  mov     r8d, 1C4h
0x180038f7f  jmp     loc_180038E95
0x180038f84  mov     rcx, [rsp+68h+hkey]; hkey
0x180038f89  lea     rax, [rsp+68h+arg_18]
0x180038f91  mov     [rsp+68h+pcbData], rax; pcbData
0x180038f96  mov     r9d, ebp; dwFlags
0x180038f99  mov     [rsp+68h+pvData], rbx; pvData
0x180038f9e  mov     r8, rdi; lpValue
0x180038fa1  mov     rdx, rsi; lpSubKey
0x180038fa4  mov     [rsp+68h+phkResult], 0; pdwType
0x180038fad  call    cs:__imp_RegGetValueW
0x180038fb3  test    eax, eax
0x180038fb5  jnz     short loc_180038FC8
0x180038fb7  cmp     [rsp+68h+arg_18], 4
0x180038fbf  jb      short loc_180038FC8
0x180038fc1  xor     ecx, ecx
0x180038fc3  cmp     cx, [rbx]
0x180038fc6  jnz     short loc_18003900C
0x180038fc8  mov     dword ptr [rsp+68h+pcbData], eax
0x180038fcc  lea     r9, aFailedToGetSer; "Failed to get Service: '%ls' Value: '%l"...
0x180038fd3  mov     [rsp+68h+pvData], rdi
0x180038fd8  lea     rdx, aUddpgetservice; "UddpGetServiceRegStringValue"
0x180038fdf  mov     r8d, 1D2h
0x180038fe5  mov     [rsp+68h+phkResult], rsi
0x180038fea  mov     ecx, r15d
0x180038fed  call    AslLogCallPrintf
0x180038ff2  mov     rcx, gs:60h
0x180038ffb  mov     r8, rbx; P
0x180038ffe  xor     edx, edx; Flags
0x180039000  mov     rcx, [rcx+30h]; HeapHandle
0x180039004  call    cs:__imp_RtlFreeHeap
0x18003900a  xor     ebx, ebx
0x18003900c  mov     rcx, [rsp+68h+hkey]; hKey
0x180039011  test    rcx, rcx
0x180039014  jz      short loc_18003901C
0x180039016  call    cs:__imp_RegCloseKey
0x18003901c  mov     rbp, [rsp+68h+arg_8]
0x180039021  mov     rax, rbx
0x180039024  mov     rbx, [rsp+68h+arg_0]
0x180039029  add     rsp, 50h
0x18003902d  pop     r15
0x18003902f  pop     rdi
0x180039030  pop     rsi
0x180039031  retn
```
