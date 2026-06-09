# RegSetValueW

- ea: `0x180034960`
- end: `0x180034a98`
- name: `RegSetValueW`
- size: `312`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, DWORD dwType, LPCWSTR lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180034960`

## import_xrefs

- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800349ba`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800349ba`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180034a7c`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180034a7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034a26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034a26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034a55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034a55`

## pseudocode

```c
LSTATUS __stdcall RegSetValueW(HKEY hKey, LPCWSTR lpSubKey, DWORD dwType, LPCWSTR lpData, DWORD cbData)
{
  LSTATUS v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  HKEY v11; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+B0h] [rbp+38h] BYREF

  hKeya = hKey;
  phkResult = 0;
  v14[0] = 0;
  v13 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  if ( dwType == 1 && lpData )
  {
    v8 = MapPredefinedHandleInternal(hKey, &hKeya, v14, &v13);
    if ( !v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpData[v9] );
      v10 = 2 * v9 + 2;
      if ( v10 > 0xFFFFFFFF )
      {
        v8 = 87;
      }
      else
      {
        if ( !lpSubKey || !*lpSubKey )
        {
          v11 = hKeya;
          phkResult = hKeya;
LABEL_14:
          v8 = RegSetValueExW(v11, 0, 0, 1u, (const BYTE *)lpData, v10);
          if ( phkResult != hKeya )
            RegCloseKey(phkResult);
          goto LABEL_17;
        }
        v8 = RegCreateKeyExW(hKeya, lpSubKey, 0, 0, 0, 2u, 0, &phkResult, 0);
        if ( !v8 )
        {
          v11 = phkResult;
          goto LABEL_14;
        }
      }
    }
LABEL_17:
    CLOSE_LOCAL_HANDLE_INTERNAL(v14[0], v13);
    return v8;
  }
  return 87;
}

```

## disassembly

```asm
0x180034960  mov     [rsp-30h+hKey], rcx
0x180034965  push    rbp
0x180034966  push    rbx
0x180034967  push    rsi
0x180034968  push    rdi
0x180034969  push    r14
0x18003496b  push    r15
0x18003496d  mov     rbp, rsp
0x180034970  sub     rsp, 78h
0x180034974  xor     r15d, r15d
0x180034977  mov     rsi, r9
0x18003497a  mov     [rbp+var_28], r15
0x18003497e  mov     rdi, rdx
0x180034981  mov     [rbp+var_18], r15
0x180034985  mov     [rbp+var_20], r15
0x180034989  cmp     rcx, 0FFFFFFFF80000004h
0x180034990  jnz     short loc_18003499B
0x180034992  lea     eax, [r15+6]
0x180034996  jmp     loc_180034A8B
0x18003499b  cmp     r8d, 1
0x18003499f  jnz     loc_180034A86
0x1800349a5  test    rsi, rsi
0x1800349a8  jz      loc_180034A86
0x1800349ae  lea     r9, [rbp+var_20]
0x1800349b2  lea     r8, [rbp+var_18]
0x1800349b6  lea     rdx, [rbp+hKey]
0x1800349ba  call    cs:__imp_MapPredefinedHandleInternal
0x1800349c0  mov     ebx, eax
0x1800349c2  test    eax, eax
0x1800349c4  jnz     loc_180034A74
0x1800349ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800349ce  inc     rax
0x1800349d1  cmp     [rsi+rax*2], r15w
0x1800349d6  jnz     short loc_1800349CE
0x1800349d8  lea     r14, ds:2[rax*2]
0x1800349e0  mov     eax, 0FFFFFFFFh
0x1800349e5  cmp     r14, rax
0x1800349e8  ja      loc_180034A6F
0x1800349ee  test    rdi, rdi
0x1800349f1  jz      short loc_180034A38
0x1800349f3  cmp     [rdi], r15w
0x1800349f7  jz      short loc_180034A38
0x1800349f9  mov     rcx, [rbp+hKey]; hKey
0x1800349fd  lea     rax, [rbp+var_28]
0x180034a01  mov     [rsp+78h+lpdwDisposition], r15; lpdwDisposition
0x180034a06  xor     r9d, r9d; lpClass
0x180034a09  mov     [rsp+78h+phkResult], rax; phkResult
0x180034a0e  xor     r8d, r8d; Reserved
0x180034a11  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180034a16  mov     rdx, rdi; lpSubKey
0x180034a19  mov     [rsp+78h+samDesired], 2; samDesired
0x180034a21  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x180034a26  call    cs:__imp_RegCreateKeyExW
0x180034a2c  mov     ebx, eax
0x180034a2e  test    eax, eax
0x180034a30  jnz     short loc_180034A74
0x180034a32  mov     rcx, [rbp+var_28]
0x180034a36  jmp     short loc_180034A40
0x180034a38  mov     rcx, [rbp+hKey]; hKey
0x180034a3c  mov     [rbp+var_28], rcx
0x180034a40  mov     [rsp+78h+samDesired], r14d; cbData
0x180034a45  mov     r9d, 1; dwType
0x180034a4b  xor     r8d, r8d; Reserved
0x180034a4e  mov     qword ptr [rsp+78h+dwOptions], rsi; lpData
0x180034a53  xor     edx, edx; lpValueName
0x180034a55  call    cs:__imp_RegSetValueExW
0x180034a5b  mov     rcx, [rbp+var_28]; hKey
0x180034a5f  mov     ebx, eax
0x180034a61  cmp     rcx, [rbp+hKey]
0x180034a65  jz      short loc_180034A74
0x180034a67  call    cs:__imp_RegCloseKey
0x180034a6d  jmp     short loc_180034A74
0x180034a6f  mov     ebx, 57h ; 'W'
0x180034a74  mov     rdx, [rbp+var_20]
0x180034a78  mov     rcx, [rbp+var_18]
0x180034a7c  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x180034a82  mov     eax, ebx
0x180034a84  jmp     short loc_180034A8B
0x180034a86  mov     eax, 57h ; 'W'
0x180034a8b  add     rsp, 78h
0x180034a8f  pop     r15
0x180034a91  pop     r14
0x180034a93  pop     rdi
0x180034a94  pop     rsi
0x180034a95  pop     rbx
0x180034a96  pop     rbp
0x180034a97  retn
```
