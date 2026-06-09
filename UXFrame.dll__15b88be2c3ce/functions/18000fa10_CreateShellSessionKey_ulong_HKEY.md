# CreateShellSessionKey(ulong,HKEY__ * *)

- ea: `0x18000fa10`
- end: `0x18000fadc`
- name: `?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z`
- size: `204`
- prototype: `int(unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013174`
- `0x180040e38`

## callees

- `0x180002b20`
- `0x18000fa10`
- `0x180016414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000fab1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000fab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fa3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fa3d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fa4a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fa4a`

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
    result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 4u, 0, a2, dwDisposition);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000fa10  push    rbx
0x18000fa12  sub     rsp, 110h
0x18000fa19  mov     rax, cs:__security_cookie
0x18000fa20  xor     rax, rsp
0x18000fa23  mov     [rsp+118h+var_18], rax
0x18000fa2b  mov     rbx, rdx
0x18000fa2e  mov     qword ptr [rdx], 0
0x18000fa35  mov     [rsp+118h+pSessionId], 0
0x18000fa3d  call    cs:__imp_GetCurrentProcessId
0x18000fa43  mov     ecx, eax; dwProcessId
0x18000fa45  lea     rdx, [rsp+118h+pSessionId]; pSessionId
0x18000fa4a  call    cs:__imp_ProcessIdToSessionId
0x18000fa50  mov     r9d, [rsp+118h+pSessionId]
0x18000fa55  lea     r8, ?shellSessionKeyFormat@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000fa5c  mov     edx, 4Bh ; 'K'; unsigned __int64
0x18000fa61  lea     rcx, [rsp+118h+SubKey]; wchar_t *
0x18000fa66  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000fa6b  test    eax, eax
0x18000fa6d  js      short loc_18000FAC3
0x18000fa6f  lea     rax, [rsp+118h+dwDisposition]
0x18000fa74  mov     [rsp+118h+dwDisposition], 0
0x18000fa7c  mov     [rsp+118h+lpdwDisposition], rax; lpdwDisposition
0x18000fa81  lea     rdx, [rsp+118h+SubKey]; lpSubKey
0x18000fa86  mov     [rsp+118h+phkResult], rbx; phkResult
0x18000fa8b  xor     r9d, r9d; lpClass
0x18000fa8e  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000fa97  xor     r8d, r8d; Reserved
0x18000fa9a  mov     [rsp+118h+samDesired], 4; samDesired
0x18000faa2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000faa9  mov     [rsp+118h+dwOptions], 1; dwOptions
0x18000fab1  call    cs:__imp_RegCreateKeyExW
0x18000fab7  test    eax, eax
0x18000fab9  jle     short loc_18000FAC3
0x18000fabb  movzx   eax, ax
0x18000fabe  or      eax, 80070000h
0x18000fac3  mov     rcx, [rsp+118h+var_18]
0x18000facb  xor     rcx, rsp; StackCookie
0x18000face  call    __security_check_cookie
0x18000fad3  add     rsp, 110h
0x18000fada  pop     rbx
0x18000fadb  retn
```
