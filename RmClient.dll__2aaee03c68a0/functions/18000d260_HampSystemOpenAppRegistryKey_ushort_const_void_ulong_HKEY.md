# HampSystemOpenAppRegistryKey(ushort const *,void *,ulong,HKEY__ * *)

- ea: `0x18000d260`
- end: `0x18000d432`
- name: `?HampSystemOpenAppRegistryKey@@YAJPEBGPEAXKPEAPEAUHKEY__@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, __int64, HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180012240`
- `0x180019cd0`

## callees

- `0x18000d260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d413`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d341`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d427`
- `ntdll!RtlFreeHeap` at `0x18000d372`
- `ntdll!RtlFreeHeap` at `0x18000d372`
- `ntdll!RtlAllocateHeap` at `0x18000d2e0`
- `ntdll!RtlAllocateHeap` at `0x18000d2e0`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicitForUserSid` at `0x18000d28f`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicitForUserSid` at `0x18000d28f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18000d2c0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18000d305`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18000d2c0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18000d305`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18000d3b3`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18000d3b3`

## pseudocode

```c
__int64 __fastcall HampSystemOpenAppRegistryKey(const unsigned __int16 *a1, void *a2, __int64 a3, HKEY *a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  WCHAR *Heap; // rax
  WCHAR *v8; // rsi
  LSTATUS v9; // eax
  signed int LastError; // ebx
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v14; // [rsp+90h] [rbp+18h] BYREF

  v14 = 0;
  hKey = 0;
  phkResult = 0;
  v5 = OpenStateExplicitForUserSid(a2, a1);
  v6 = v5;
  if ( v5 )
  {
    v14 = 0;
    GetSystemAppDataKey(v5, 0, 0, &v14);
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v14);
    v8 = Heap;
    if ( Heap )
    {
      if ( (unsigned int)GetSystemAppDataKey(v6, &hKey, Heap, &v14) )
      {
        v9 = RegCreateKeyExW(hKey, v8, 0, 0, 0, 1u, 0, &phkResult, 0);
        LastError = v9;
        if ( v9 > 0 )
          LastError = (unsigned __int16)v9 | 0xC0070000;
        if ( LastError >= 0 )
        {
          LastError = 0;
          *a4 = phkResult;
          phkResult = 0;
        }
      }
      else if ( (int)GetLastError() > 0 )
      {
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      }
      else
      {
        LastError = GetLastError();
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    else
    {
      LastError = -1073741801;
    }
  }
  else if ( (int)GetLastError() > 0 )
  {
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    CloseState(v6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000d260  mov     r11, rsp
0x18000d263  mov     [r11+18h], r8d
0x18000d267  push    rbx
0x18000d268  push    rdi
0x18000d269  sub     rsp, 68h
0x18000d26d  mov     [r11+8], rbp
0x18000d271  mov     rax, rdx
0x18000d274  xor     ebp, ebp
0x18000d276  mov     [r11-18h], r14
0x18000d27a  mov     rdx, rcx
0x18000d27d  mov     [r11+18h], ebp
0x18000d281  mov     rcx, rax
0x18000d284  mov     [r11-20h], rbp
0x18000d288  mov     [r11-28h], rbp
0x18000d28c  mov     r14, r9
0x18000d28f  call    cs:__imp_OpenStateExplicitForUserSid
0x18000d295  mov     rdi, rax
0x18000d298  test    rax, rax
0x18000d29b  jz      loc_18000D3CD
0x18000d2a1  lea     r9, [rsp+78h+arg_10]
0x18000d2a9  mov     [rsp+78h+arg_8], rsi
0x18000d2b1  xor     r8d, r8d
0x18000d2b4  mov     [rsp+78h+arg_10], ebp
0x18000d2bb  xor     edx, edx
0x18000d2bd  mov     rcx, rax
0x18000d2c0  call    cs:__imp_GetSystemAppDataKey
0x18000d2c6  mov     rcx, gs:60h
0x18000d2cf  xor     edx, edx; Flags
0x18000d2d1  mov     r8d, [rsp+78h+arg_10]
0x18000d2d9  add     r8, r8; Size
0x18000d2dc  mov     rcx, [rcx+30h]; HeapHandle
0x18000d2e0  call    cs:__imp_RtlAllocateHeap
0x18000d2e6  mov     rsi, rax
0x18000d2e9  test    rax, rax
0x18000d2ec  jz      loc_18000D3F2
0x18000d2f2  lea     r9, [rsp+78h+arg_10]
0x18000d2fa  mov     r8, rax
0x18000d2fd  lea     rdx, [rsp+78h+hKey]
0x18000d302  mov     rcx, rdi
0x18000d305  call    cs:__imp_GetSystemAppDataKey
0x18000d30b  test    eax, eax
0x18000d30d  jz      loc_18000D3FC
0x18000d313  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d318  lea     rax, [rsp+78h+var_28]
0x18000d31d  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x18000d322  xor     r9d, r9d; lpClass
0x18000d325  mov     [rsp+78h+phkResult], rax; phkResult
0x18000d32a  xor     r8d, r8d; Reserved
0x18000d32d  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18000d332  mov     rdx, rsi; lpSubKey
0x18000d335  mov     [rsp+78h+samDesired], 1; samDesired
0x18000d33d  mov     [rsp+78h+dwOptions], ebp; dwOptions
0x18000d341  call    cs:__imp_RegCreateKeyExW
0x18000d347  mov     ebx, eax
0x18000d349  test    eax, eax
0x18000d34b  jg      short loc_18000D3C2
0x18000d34d  test    ebx, ebx
0x18000d34f  js      short loc_18000D360
0x18000d351  mov     rax, [rsp+78h+var_28]
0x18000d356  mov     ebx, ebp
0x18000d358  mov     [r14], rax
0x18000d35b  mov     [rsp+78h+var_28], rbp
0x18000d360  mov     rcx, gs:60h
0x18000d369  mov     r8, rsi; P
0x18000d36c  xor     edx, edx; Flags
0x18000d36e  mov     rcx, [rcx+30h]; HeapHandle
0x18000d372  call    cs:__imp_RtlFreeHeap
0x18000d378  mov     rsi, [rsp+78h+arg_8]
0x18000d380  mov     rcx, [rsp+78h+var_28]; hKey
0x18000d385  mov     r14, [rsp+78h+var_18]
0x18000d38a  mov     rbp, [rsp+78h+arg_0]
0x18000d392  test    rcx, rcx
0x18000d395  jnz     loc_18000D427
0x18000d39b  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d3a0  test    rcx, rcx
0x18000d3a3  jz      short loc_18000D3AB
0x18000d3a5  call    cs:__imp_RegCloseKey
0x18000d3ab  test    rdi, rdi
0x18000d3ae  jz      short loc_18000D3B9
0x18000d3b0  mov     rcx, rdi
0x18000d3b3  call    cs:__imp_CloseState
0x18000d3b9  mov     eax, ebx
0x18000d3bb  add     rsp, 68h
0x18000d3bf  pop     rdi
0x18000d3c0  pop     rbx
0x18000d3c1  retn
0x18000d3c2  movzx   ebx, ax
0x18000d3c5  or      ebx, 0C0070000h
0x18000d3cb  jmp     short loc_18000D34D
0x18000d3cd  call    cs:__imp_GetLastError
0x18000d3d3  test    eax, eax
0x18000d3d5  jg      short loc_18000D3E1
0x18000d3d7  call    cs:__imp_GetLastError
0x18000d3dd  mov     ebx, eax
0x18000d3df  jmp     short loc_18000D380
0x18000d3e1  call    cs:__imp_GetLastError
0x18000d3e7  movzx   ebx, ax
0x18000d3ea  or      ebx, 0C0070000h
0x18000d3f0  jmp     short loc_18000D380
0x18000d3f2  mov     ebx, 0C0000017h
0x18000d3f7  jmp     loc_18000D378
0x18000d3fc  call    cs:__imp_GetLastError
0x18000d402  test    eax, eax
0x18000d404  jg      short loc_18000D413
0x18000d406  call    cs:__imp_GetLastError
0x18000d40c  mov     ebx, eax
0x18000d40e  jmp     loc_18000D360
0x18000d413  call    cs:__imp_GetLastError
0x18000d419  movzx   ebx, ax
0x18000d41c  or      ebx, 0C0070000h
0x18000d422  jmp     loc_18000D360
0x18000d427  call    cs:__imp_RegCloseKey
0x18000d42d  jmp     loc_18000D39B
```
