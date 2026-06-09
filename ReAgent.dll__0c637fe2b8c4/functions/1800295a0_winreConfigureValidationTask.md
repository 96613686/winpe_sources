# winreConfigureValidationTask

- ea: `0x1800295a0`
- end: `0x1800296e3`
- name: `winreConfigureValidationTask`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018870`
- `0x18001fd7c`
- `0x180024800`

## callees

- `0x1800059fc`
- `0x18001fbc0`
- `0x1800282d4`
- `0x1800295a0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002965c`
- `KERNEL32!GetLastError` at `0x18002965c`
- `KERNEL32!SetLastError` at `0x1800296c1`
- `KERNEL32!SetLastError` at `0x1800296c1`
- `ADVAPI32!RegDeleteValueW` at `0x180029604`
- `ADVAPI32!RegDeleteValueW` at `0x18002962b`
- `ADVAPI32!RegDeleteValueW` at `0x180029604`
- `ADVAPI32!RegDeleteValueW` at `0x18002962b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800295ee`
- `ADVAPI32!RegOpenKeyExW` at `0x1800295ee`
- `ADVAPI32!RegCloseKey` at `0x180029698`
- `ADVAPI32!RegCloseKey` at `0x180029698`

## string_xrefs

- `0x18002963e`: `Failed to open WinRE reg key: 0x%x`
- `0x180029680`: `Failed to publish the configuration change notification: 0x%x`
- `0x1800296ae`: `winreConfigureValidationTask failed: 0x%x, a non critical error`

## pseudocode

```c
__int64 __fastcall winreConfigureValidationTask(int a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  struct _WNF_TYPE_ID *v5; // rdx
  unsigned int v6; // r9d
  DWORD LastError; // ebx
  unsigned int v8; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v12 = 2 - (a1 != 0);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
         0,
         2u,
         &hKey);
  if ( v2 )
  {
    UnattendLogW(0, L"Failed to open WinRE reg key: 0x%x", v2);
  }
  else
  {
    v3 = RegDeleteValueW(hKey, L"WimValidated");
    if ( v3 )
      UnattendLogW(0, L"Failed to clear WIM file trusted state: 0x%x", v3);
    v4 = RegDeleteValueW(hKey, L"WimHash");
    if ( v4 )
      UnattendLogW(0, L"Failed to clear WIM file hash: 0x%x", v4);
  }
  if ( !a1 || (unsigned int)WinReValidateRecoveryWimInternal() )
  {
    v8 = winrePublishWnfStateData(WNF_SRT_WINRE_CONFIGURATION_CHANGE, v5, &v12, v6, phkResult);
    LastError = v8;
    if ( v8 )
      UnattendLogW(0, L"Failed to publish the configuration change notification: 0x%x", v8);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !LastError )
    return 1;
  UnattendLogW(2, L"winreConfigureValidationTask failed: 0x%x, a non critical error", LastError);
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800295a0  push    rbx
0x1800295a2  sub     rsp, 50h
0x1800295a6  mov     rax, cs:__security_cookie
0x1800295ad  xor     rax, rsp
0x1800295b0  mov     [rsp+58h+var_18], rax
0x1800295b5  mov     eax, ecx
0x1800295b7  mov     [rsp+58h+hKey], 0
0x1800295c0  neg     eax
0x1800295c2  mov     ebx, ecx
0x1800295c4  lea     rax, [rsp+58h+hKey]
0x1800295c9  mov     r9d, 2; samDesired
0x1800295cf  sbb     edx, edx
0x1800295d1  mov     [rsp+58h+phkResult], rax; void *
0x1800295d6  add     edx, 2
0x1800295d9  xor     r8d, r8d; ulOptions
0x1800295dc  mov     [rsp+58h+var_20], edx
0x1800295e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800295e7  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800295ee  call    cs:__imp_RegOpenKeyExW
0x1800295f4  test    eax, eax
0x1800295f6  jnz     short loc_18002963E
0x1800295f8  mov     rcx, [rsp+58h+hKey]; hKey
0x1800295fd  lea     rdx, aWimvalidated_0; "WimValidated"
0x180029604  call    cs:__imp_RegDeleteValueW
0x18002960a  test    eax, eax
0x18002960c  jz      short loc_18002961F
0x18002960e  mov     r8d, eax
0x180029611  lea     rdx, aFailedToClearW; "Failed to clear WIM file trusted state:"...
0x180029618  xor     ecx, ecx
0x18002961a  call    UnattendLogW
0x18002961f  mov     rcx, [rsp+58h+hKey]; hKey
0x180029624  lea     rdx, aWimhash_0; "WimHash"
0x18002962b  call    cs:__imp_RegDeleteValueW
0x180029631  test    eax, eax
0x180029633  jz      short loc_18002964F
0x180029635  lea     rdx, aFailedToClearW_0; "Failed to clear WIM file hash: 0x%x"
0x18002963c  jmp     short loc_180029645
0x18002963e  lea     rdx, aFailedToOpenWi_0; "Failed to open WinRE reg key: 0x%x"
0x180029645  mov     r8d, eax
0x180029648  xor     ecx, ecx
0x18002964a  call    UnattendLogW
0x18002964f  test    ebx, ebx
0x180029651  jz      short loc_180029666
0x180029653  call    WinReValidateRecoveryWimInternal
0x180029658  test    eax, eax
0x18002965a  jnz     short loc_180029666
0x18002965c  call    cs:__imp_GetLastError
0x180029662  mov     ebx, eax
0x180029664  jmp     short loc_18002968E
0x180029666  mov     rcx, qword ptr cs:WNF_SRT_WINRE_CONFIGURATION_CHANGE.Data; struct _WNF_STATE_NAME
0x18002966d  lea     r8, [rsp+58h+var_20]; void *
0x180029672  call    ?winrePublishWnfStateData@@YAKU_WNF_STATE_NAME@@PEAU_WNF_TYPE_ID@@PEBXKQEAX@Z; winrePublishWnfStateData(_WNF_STATE_NAME,_WNF_TYPE_ID *,void const *,ulong,void * const)
0x180029677  mov     ebx, eax
0x180029679  test    eax, eax
0x18002967b  jz      short loc_18002968E
0x18002967d  mov     r8d, eax
0x180029680  lea     rdx, aFailedToPublis; "Failed to publish the configuration cha"...
0x180029687  xor     ecx, ecx
0x180029689  call    UnattendLogW
0x18002968e  mov     rcx, [rsp+58h+hKey]; hKey
0x180029693  test    rcx, rcx
0x180029696  jz      short loc_1800296A7
0x180029698  call    cs:__imp_RegCloseKey
0x18002969e  mov     [rsp+58h+hKey], 0
0x1800296a7  test    ebx, ebx
0x1800296a9  jz      short loc_1800296CB
0x1800296ab  mov     r8d, ebx
0x1800296ae  lea     rdx, aWinreconfigure_2; "winreConfigureValidationTask failed: 0x"...
0x1800296b5  mov     ecx, 2
0x1800296ba  call    UnattendLogW
0x1800296bf  mov     ecx, ebx; dwErrCode
0x1800296c1  call    cs:__imp_SetLastError
0x1800296c7  xor     eax, eax
0x1800296c9  jmp     short loc_1800296D0
0x1800296cb  mov     eax, 1
0x1800296d0  mov     rcx, [rsp+58h+var_18]
0x1800296d5  xor     rcx, rsp; StackCookie
0x1800296d8  call    __security_check_cookie
0x1800296dd  add     rsp, 50h
0x1800296e1  pop     rbx
0x1800296e2  retn
```
