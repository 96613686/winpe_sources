# DrvRecoveryEnumRecoveryIds(HDRIVERSTORE__ *,_DRVRECOVERY_ENUM_RECOVERY_ID_FLAG,int (*)(HDRIVERSTORE__ *,ushort const *,_DRVRECOVERY_RECOVERY_ID_FLAG,__int64),__int64)

- ea: `0x18003a9ac`
- end: `0x18003abb4`
- name: `?DrvRecoveryEnumRecoveryIds@@YAHPEAUHDRIVERSTORE__@@W4_DRVRECOVERY_ENUM_RECOVERY_ID_FLAG@@P6AH0PEBGW4_DRVRECOVERY_RECOVERY_ID_FLAG@@_J@Z4@Z`
- size: `520`
- prototype: `_BOOL8 __fastcall(struct HDRIVERSTORE__ *, __int64, unsigned int (__fastcall *)(struct HDRIVERSTORE__ *, WCHAR *, __int64, __int64), __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029a60`

## callees

- `0x18003a9ac`
- `0x18003b6ec`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003aa62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003aa62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aae5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aae5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003aa3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003aa3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ab1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ab1a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003aaaf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003aaaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall DrvRecoveryEnumRecoveryIds(
        struct HDRIVERSTORE__ *a1,
        __int64 a2,
        unsigned int (__fastcall *a3)(struct HDRIVERSTORE__ *, WCHAR *, __int64, __int64),
        __int64 a4)
{
  DWORD v4; // r14d
  HKEY RecordRoot; // rdi
  DWORD LastError; // ebx
  WCHAR *v10; // rsi
  LSTATUS v11; // eax
  BYTE Data[4]; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-5h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-1h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp+3h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+7h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+6Fh] BYREF

  v4 = 0;
  phkResult = 0;
  cbData = 0;
  Type = 0;
  cchName = 0;
  cbMaxSubKeyLen = 0;
  *(_DWORD *)Data = 0;
  RecordRoot = pDrvRecoveryGetRecordRoot(a1);
  if ( RecordRoot )
  {
    LastError = RegQueryInfoKeyW(RecordRoot, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !LastError )
    {
      ++cbMaxSubKeyLen;
      v10 = (WCHAR *)HeapAlloc(hHeap, 0, 2 * cbMaxSubKeyLen);
      if ( v10 )
      {
        while ( 1 )
        {
          cchName = cbMaxSubKeyLen;
          v11 = RegEnumKeyExW(RecordRoot, v4, v10, &cchName, 0, 0, 0, 0);
          LastError = v11;
          if ( v11 == 259 )
            break;
          if ( v11 )
            goto LABEL_18;
          *(_DWORD *)Data = 0;
          if ( !RegOpenKeyExW(RecordRoot, v10, 0, 0x20019u, &phkResult) )
          {
            cbData = 4;
            if ( RegQueryValueExW(phkResult, L"State", 0, &Type, Data, &cbData) || Type != 4 || cbData != 4 )
              *(_DWORD *)Data = 0;
            RegCloseKey(phkResult);
          }
          if ( *(_DWORD *)Data != 7 )
          {
            LastError = 0;
            if ( !a3(a1, v10, 1, a4) )
              goto LABEL_18;
          }
          ++v4;
        }
        LastError = 0;
LABEL_18:
        HeapFree(hHeap, 0, v10);
      }
      else
      {
        LastError = 8;
      }
    }
    RegCloseKey(RecordRoot);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18003a9ac  mov     [rsp-8+cbMaxSubKeyLen], edx
0x18003a9b0  push    rbp
0x18003a9b1  push    rbx
0x18003a9b2  push    rsi
0x18003a9b3  push    rdi
0x18003a9b4  push    r12
0x18003a9b6  push    r13
0x18003a9b8  push    r14
0x18003a9ba  push    r15
0x18003a9bc  lea     rbp, [rsp-1Fh]
0x18003a9c1  sub     rsp, 88h
0x18003a9c8  xor     r14d, r14d
0x18003a9cb  mov     r12, r9
0x18003a9ce  mov     [rbp+57h+phkResult], r14
0x18003a9d2  mov     r13, r8
0x18003a9d5  mov     [rbp+57h+cbData], r14d
0x18003a9d9  mov     r15, rcx
0x18003a9dc  mov     [rbp+57h+Type], r14d
0x18003a9e0  mov     [rbp+57h+cchName], r14d
0x18003a9e4  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18003a9e8  mov     dword ptr [rbp+57h+Data], r14d
0x18003a9ec  call    ?pDrvRecoveryGetRecordRoot@@YAPEAUHKEY__@@PEAUHDRIVERSTORE__@@@Z; pDrvRecoveryGetRecordRoot(HDRIVERSTORE__ *)
0x18003a9f1  mov     rdi, rax
0x18003a9f4  test    rax, rax
0x18003a9f7  jnz     short loc_18003AA06
0x18003a9f9  call    cs:__imp_GetLastError
0x18003a9ff  mov     ebx, eax
0x18003aa01  jmp     loc_18003AB90
0x18003aa06  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18003aa0b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18003aa0f  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18003aa14  xor     r9d, r9d; lpReserved
0x18003aa17  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18003aa1c  xor     r8d, r8d; lpcchClass
0x18003aa1f  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18003aa24  xor     edx, edx; lpClass
0x18003aa26  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x18003aa2b  mov     rcx, rdi; hKey
0x18003aa2e  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18003aa33  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003aa38  mov     [rsp+0C0h+lpcSubKeys], r14; lpcSubKeys
0x18003aa3d  call    cs:__imp_RegQueryInfoKeyW
0x18003aa43  mov     ebx, eax
0x18003aa45  test    eax, eax
0x18003aa47  jnz     loc_18003AB87
0x18003aa4d  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003aa50  xor     edx, edx; dwFlags
0x18003aa52  mov     rcx, cs:hHeap; hHeap
0x18003aa59  inc     eax
0x18003aa5b  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x18003aa5e  lea     r8d, [rax+rax]; dwBytes
0x18003aa62  call    cs:__imp_HeapAlloc
0x18003aa68  mov     rsi, rax
0x18003aa6b  test    rax, rax
0x18003aa6e  jnz     short loc_18003AA78
0x18003aa70  lea     ebx, [rax+8]
0x18003aa73  jmp     loc_18003AB87
0x18003aa78  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003aa7b  lea     r9, [rbp+57h+cchName]; lpcchName
0x18003aa7f  mov     [rsp+0C0h+lpcValues], 0; lpftLastWriteTime
0x18003aa88  mov     r8, rsi; lpName
0x18003aa8b  mov     [rsp+0C0h+lpcbMaxClassLen], 0; lpcchClass
0x18003aa94  mov     edx, r14d; dwIndex
0x18003aa97  mov     [rsp+0C0h+lpcbMaxSubKeyLen], 0; lpClass
0x18003aaa0  mov     rcx, rdi; hKey
0x18003aaa3  mov     [rsp+0C0h+lpcSubKeys], 0; lpReserved
0x18003aaac  mov     [rbp+57h+cchName], eax
0x18003aaaf  call    cs:__imp_RegEnumKeyExW
0x18003aab5  mov     ebx, eax
0x18003aab7  cmp     eax, 103h
0x18003aabc  jz      loc_18003AB6A
0x18003aac2  test    eax, eax
0x18003aac4  jnz     loc_18003AB72
0x18003aaca  mov     dword ptr [rbp+57h+Data], eax
0x18003aacd  mov     r9d, 20019h; samDesired
0x18003aad3  lea     rax, [rbp+57h+phkResult]
0x18003aad7  xor     r8d, r8d; ulOptions
0x18003aada  mov     rdx, rsi; lpSubKey
0x18003aadd  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x18003aae2  mov     rcx, rdi; hKey
0x18003aae5  call    cs:__imp_RegOpenKeyExW
0x18003aaeb  test    eax, eax
0x18003aaed  jnz     short loc_18003AB41
0x18003aaef  mov     rcx, [rbp+57h+phkResult]; hKey
0x18003aaf3  lea     rax, [rbp+57h+cbData]
0x18003aaf7  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003aafc  lea     r9, [rbp+57h+Type]; lpType
0x18003ab00  lea     rax, [rbp+57h+Data]
0x18003ab04  mov     [rbp+57h+cbData], 4
0x18003ab0b  xor     r8d, r8d; lpReserved
0x18003ab0e  mov     [rsp+0C0h+lpcSubKeys], rax; lpData
0x18003ab13  lea     rdx, aState; "State"
0x18003ab1a  call    cs:__imp_RegQueryValueExW
0x18003ab20  test    eax, eax
0x18003ab22  jnz     short loc_18003AB30
0x18003ab24  cmp     [rbp+57h+Type], 4
0x18003ab28  jnz     short loc_18003AB30
0x18003ab2a  cmp     [rbp+57h+cbData], 4
0x18003ab2e  jz      short loc_18003AB37
0x18003ab30  mov     dword ptr [rbp+57h+Data], 0
0x18003ab37  mov     rcx, [rbp+57h+phkResult]; hKey
0x18003ab3b  call    cs:__imp_RegCloseKey
0x18003ab41  cmp     dword ptr [rbp+57h+Data], 7
0x18003ab45  jz      short loc_18003AB62
0x18003ab47  xor     ebx, ebx
0x18003ab49  mov     r9, r12
0x18003ab4c  mov     rdx, rsi
0x18003ab4f  mov     rcx, r15
0x18003ab52  mov     rax, r13
0x18003ab55  lea     r8d, [rbx+1]
0x18003ab59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab5e  test    eax, eax
0x18003ab60  jz      short loc_18003AB72
0x18003ab62  inc     r14d
0x18003ab65  jmp     loc_18003AA78
0x18003ab6a  xor     r14d, r14d
0x18003ab6d  mov     ebx, r14d
0x18003ab70  jmp     short loc_18003AB75
0x18003ab72  xor     r14d, r14d
0x18003ab75  mov     rcx, cs:hHeap; hHeap
0x18003ab7c  mov     r8, rsi; lpMem
0x18003ab7f  xor     edx, edx; dwFlags
0x18003ab81  call    cs:__imp_HeapFree
0x18003ab87  mov     rcx, rdi; hKey
0x18003ab8a  call    cs:__imp_RegCloseKey
0x18003ab90  mov     ecx, ebx; dwErrCode
0x18003ab92  call    cs:__imp_SetLastError
0x18003ab98  test    ebx, ebx
0x18003ab9a  mov     eax, r14d
0x18003ab9d  setz    al
0x18003aba0  add     rsp, 88h
0x18003aba7  pop     r15
0x18003aba9  pop     r14
0x18003abab  pop     r13
0x18003abad  pop     r12
0x18003abaf  pop     rdi
0x18003abb0  pop     rsi
0x18003abb1  pop     rbx
0x18003abb2  pop     rbp
0x18003abb3  retn
```
