# CreateShellSessionKey(ulong,HKEY__ * *)

- ea: `0x1800a2ec8`
- end: `0x1800a2f91`
- name: `?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z`
- size: `201`
- prototype: `int(unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800aeacc`

## callees

- `0x180006e50`
- `0x18000f07c`
- `0x1800a2ec8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a2ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a2ef5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a2f02`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a2f02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2f66`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a2f66`

## pseudocode

```c
LSTATUS __fastcall CreateShellSessionKey(__int64 a1, HKEY *a2)
{
  DWORD CurrentProcessId; // eax
  LSTATUS result; // eax
  DWORD pSessionId; // [rsp+50h] [rbp-C8h] BYREF
  DWORD dwDisposition[3]; // [rsp+54h] [rbp-C4h] BYREF
  WCHAR SubKey[80]; // [rsp+60h] [rbp-B8h] BYREF

  *a2 = 0;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  result = StringCchPrintfW(
             SubKey,
             0x4Bu,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SessionInfo\\%d",
             pSessionId);
  if ( result >= 0 )
  {
    dwDisposition[0] = 0;
    result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 1u, 0, a2, dwDisposition);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800a2ec8  push    rbx
0x1800a2eca  sub     rsp, 110h
0x1800a2ed1  mov     rax, cs:__security_cookie
0x1800a2ed8  xor     rax, rsp
0x1800a2edb  mov     [rsp+118h+var_18], rax
0x1800a2ee3  mov     rbx, rdx
0x1800a2ee6  mov     qword ptr [rdx], 0
0x1800a2eed  mov     [rsp+118h+pSessionId], 0
0x1800a2ef5  call    cs:__imp_GetCurrentProcessId
0x1800a2efb  mov     ecx, eax; dwProcessId
0x1800a2efd  lea     rdx, [rsp+118h+pSessionId]; pSessionId
0x1800a2f02  call    cs:__imp_ProcessIdToSessionId
0x1800a2f08  mov     r9d, [rsp+118h+pSessionId]
0x1800a2f0d  lea     r8, ?shellSessionKeyFormat@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a2f14  mov     edx, 4Bh ; 'K'; unsigned __int64
0x1800a2f19  lea     rcx, [rsp+118h+SubKey]; unsigned __int16 *
0x1800a2f1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a2f23  test    eax, eax
0x1800a2f25  js      short loc_1800A2F78
0x1800a2f27  lea     rax, [rsp+118h+dwDisposition]
0x1800a2f2c  mov     [rsp+118h+dwDisposition], 0
0x1800a2f34  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x1800a2f39  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x1800a2f3e  mov     [rsp+118h+phkResult], rbx; phkResult
0x1800a2f43  mov     eax, 1
0x1800a2f48  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a2f51  xor     r9d, r9d; lpClass
0x1800a2f54  mov     [rsp+118h+samDesired], eax; samDesired
0x1800a2f58  xor     r8d, r8d; Reserved
0x1800a2f5b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800a2f62  mov     [rsp+118h+dwOptions], eax; dwOptions
0x1800a2f66  call    cs:__imp_RegCreateKeyExW
0x1800a2f6c  test    eax, eax
0x1800a2f6e  jle     short loc_1800A2F78
0x1800a2f70  movzx   eax, ax
0x1800a2f73  or      eax, 80070000h
0x1800a2f78  mov     rcx, [rsp+118h+var_18]
0x1800a2f80  xor     rcx, rsp; StackCookie
0x1800a2f83  call    __security_check_cookie
0x1800a2f88  add     rsp, 110h
0x1800a2f8f  pop     rbx
0x1800a2f90  retn
```
