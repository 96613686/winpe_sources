# RegSetValueW

- ea: `0x180038510`
- end: `0x180038667`
- name: `RegSetValueW`
- size: `343`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, DWORD dwType, LPCWSTR lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180038510`

## import_xrefs

- `KERNELBASE!MapPredefinedHandleInternal` at `0x18003856a`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18003856a`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180038644`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180038644`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800385dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800385dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038629`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038629`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038611`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038611`

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
0x180038510  mov     [rsp-30h+hKey], rcx
0x180038515  push    rbp
0x180038516  push    rbx
0x180038517  push    rsi
0x180038518  push    rdi
0x180038519  push    r14
0x18003851b  push    r15
0x18003851d  mov     rbp, rsp
0x180038520  sub     rsp, 78h
0x180038524  xor     r15d, r15d
0x180038527  mov     rsi, r9
0x18003852a  mov     [rbp+var_28], r15
0x18003852e  mov     rdi, rdx
0x180038531  mov     [rbp+var_18], r15
0x180038535  mov     [rbp+var_20], r15
0x180038539  cmp     rcx, 0FFFFFFFF80000004h
0x180038540  jnz     short loc_18003854B
0x180038542  lea     eax, [r15+6]
0x180038546  jmp     loc_180038659
0x18003854b  cmp     r8d, 1
0x18003854f  jnz     loc_180038654
0x180038555  test    rsi, rsi
0x180038558  jz      loc_180038654
0x18003855e  lea     r9, [rbp+var_20]
0x180038562  lea     r8, [rbp+var_18]
0x180038566  lea     rdx, [rbp+hKey]
0x18003856a  call    cs:__imp_MapPredefinedHandleInternal
0x180038571  nop     dword ptr [rax+rax+00h]
0x180038576  mov     ebx, eax
0x180038578  test    eax, eax
0x18003857a  jnz     loc_18003863C
0x180038580  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038584  inc     rax
0x180038587  cmp     [rsi+rax*2], r15w
0x18003858c  jnz     short loc_180038584
0x18003858e  lea     r14, ds:2[rax*2]
0x180038596  mov     eax, 0FFFFFFFFh
0x18003859b  cmp     r14, rax
0x18003859e  ja      loc_180038637
0x1800385a4  test    rdi, rdi
0x1800385a7  jz      short loc_1800385F4
0x1800385a9  cmp     [rdi], r15w
0x1800385ad  jz      short loc_1800385F4
0x1800385af  mov     rcx, [rbp+hKey]; hKey
0x1800385b3  lea     rax, [rbp+var_28]
0x1800385b7  mov     [rsp+78h+lpdwDisposition], r15; lpdwDisposition
0x1800385bc  xor     r9d, r9d; lpClass
0x1800385bf  mov     [rsp+78h+phkResult], rax; phkResult
0x1800385c4  xor     r8d, r8d; Reserved
0x1800385c7  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800385cc  mov     rdx, rdi; lpSubKey
0x1800385cf  mov     [rsp+78h+samDesired], 2; samDesired
0x1800385d7  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x1800385dc  call    cs:__imp_RegCreateKeyExW
0x1800385e3  nop     dword ptr [rax+rax+00h]
0x1800385e8  mov     ebx, eax
0x1800385ea  test    eax, eax
0x1800385ec  jnz     short loc_18003863C
0x1800385ee  mov     rcx, [rbp+var_28]
0x1800385f2  jmp     short loc_1800385FC
0x1800385f4  mov     rcx, [rbp+hKey]; hKey
0x1800385f8  mov     [rbp+var_28], rcx
0x1800385fc  mov     [rsp+78h+samDesired], r14d; cbData
0x180038601  mov     r9d, 1; dwType
0x180038607  xor     r8d, r8d; Reserved
0x18003860a  mov     qword ptr [rsp+78h+dwOptions], rsi; lpData
0x18003860f  xor     edx, edx; lpValueName
0x180038611  call    cs:__imp_RegSetValueExW
0x180038618  nop     dword ptr [rax+rax+00h]
0x18003861d  mov     rcx, [rbp+var_28]; hKey
0x180038621  mov     ebx, eax
0x180038623  cmp     rcx, [rbp+hKey]
0x180038627  jz      short loc_18003863C
0x180038629  call    cs:__imp_RegCloseKey
0x180038630  nop     dword ptr [rax+rax+00h]
0x180038635  jmp     short loc_18003863C
0x180038637  mov     ebx, 57h ; 'W'
0x18003863c  mov     rdx, [rbp+var_20]
0x180038640  mov     rcx, [rbp+var_18]
0x180038644  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x18003864b  nop     dword ptr [rax+rax+00h]
0x180038650  mov     eax, ebx
0x180038652  jmp     short loc_180038659
0x180038654  mov     eax, 57h ; 'W'
0x180038659  add     rsp, 78h
0x18003865d  pop     r15
0x18003865f  pop     r14
0x180038661  pop     rdi
0x180038662  pop     rsi
0x180038663  pop     rbx
0x180038664  pop     rbp
0x180038665  retn
```
