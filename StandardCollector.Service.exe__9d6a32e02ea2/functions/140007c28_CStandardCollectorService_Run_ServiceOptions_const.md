# CStandardCollectorService::Run(ServiceOptions const &)

- ea: `0x140007c28`
- end: `0x140007cff`
- name: `?Run@CStandardCollectorService@@QEAAHAEBUServiceOptions@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CStandardCollectorService *__hidden this, const struct ServiceOptions *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140001388`

## callees

- `0x14000356c`
- `0x140007c28`
- `0x140007da0`
- `0x1400137e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140007cbb`
- `KERNEL32!GetLastError` at `0x140007cbb`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140007cb1`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x140007cb1`

## string_xrefs

- `0x140007c82`: `VsStandardCollectorService170`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStandardCollectorService::Run(CStandardCollectorService *this, const struct ServiceOptions *a2)
{
  __int64 result; // rax
  signed int LastError; // ecx
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+20h] [rbp-38h] BYREF
  __int64 v5; // [rsp+30h] [rbp-28h]
  __int64 v6; // [rsp+38h] [rbp-20h]

  if ( *(_DWORD *)a2 == 1 || *(_DWORD *)a2 == 2 || *(_DWORD *)a2 == 3 || *(_DWORD *)a2 == 4 )
    return ServiceControl::Run(a2);
  if ( *(_DWORD *)a2 != 5 && *(_DWORD *)a2 != 6 )
  {
    if ( (unsigned int)(*(_DWORD *)a2 - 7) >= 2 )
      return 0xFFFFFFFFLL;
    return ServiceControl::Run(a2);
  }
  if ( *(_DWORD *)a2 != 5 )
  {
    CStandardCollectorService::ServiceMain(this, a2);
    return 0;
  }
  v5 = 0;
  ServiceStartTable.lpServiceName = (LPWSTR)L"VsStandardCollectorService170";
  v6 = 0;
  ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)CStandardCollectorService::ServiceMainStatic;
  if ( StartServiceCtrlDispatcherW(&ServiceStartTable) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 1056 )
    return 0;
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x140007c28  sub     rsp, 58h
0x140007c2c  mov     rax, cs:__security_cookie
0x140007c33  xor     rax, rsp
0x140007c36  mov     [rsp+58h+var_18], rax
0x140007c3b  mov     r8, rcx
0x140007c3e  mov     ecx, [rdx]
0x140007c40  sub     ecx, 1
0x140007c43  jz      loc_140007CE5
0x140007c49  sub     ecx, 1
0x140007c4c  jz      loc_140007CE5
0x140007c52  sub     ecx, 1
0x140007c55  jz      loc_140007CE5
0x140007c5b  sub     ecx, 1
0x140007c5e  jz      loc_140007CE5
0x140007c64  sub     ecx, 1
0x140007c67  jz      short loc_140007C7D
0x140007c69  sub     ecx, 1
0x140007c6c  jz      short loc_140007C7D
0x140007c6e  sub     ecx, 1
0x140007c71  jz      short loc_140007CE5
0x140007c73  cmp     ecx, 1
0x140007c76  jz      short loc_140007CE5
0x140007c78  or      eax, 0FFFFFFFFh
0x140007c7b  jmp     short loc_140007CED
0x140007c7d  cmp     dword ptr [rdx], 5
0x140007c80  jnz     short loc_140007CD9
0x140007c82  lea     rax, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x140007c89  mov     [rsp+58h+var_28], 0
0x140007c92  mov     [rsp+58h+ServiceStartTable.lpServiceName], rax
0x140007c97  lea     rcx, [rsp+58h+ServiceStartTable]; lpServiceStartTable
0x140007c9c  lea     rax, ?ServiceMainStatic@CStandardCollectorService@@CAXKQEAPEAG@Z; CStandardCollectorService::ServiceMainStatic(ulong,ushort * * const)
0x140007ca3  mov     [rsp+58h+var_20], 0
0x140007cac  mov     [rsp+58h+ServiceStartTable.lpServiceProc], rax
0x140007cb1  call    cs:__imp_StartServiceCtrlDispatcherW
0x140007cb7  test    eax, eax
0x140007cb9  jnz     short loc_140007CE1
0x140007cbb  call    cs:__imp_GetLastError
0x140007cc1  mov     ecx, eax
0x140007cc3  cmp     eax, 420h
0x140007cc8  jz      short loc_140007CE1
0x140007cca  movzx   eax, cx
0x140007ccd  or      eax, 80070000h
0x140007cd2  test    ecx, ecx
0x140007cd4  cmovle  eax, ecx
0x140007cd7  jmp     short loc_140007CED
0x140007cd9  mov     rcx, r8; this
0x140007cdc  call    ?ServiceMain@CStandardCollectorService@@AEAAXAEBUServiceOptions@@@Z; CStandardCollectorService::ServiceMain(ServiceOptions const &)
0x140007ce1  xor     eax, eax
0x140007ce3  jmp     short loc_140007CED
0x140007ce5  mov     rcx, rdx; struct ServiceOptions *
0x140007ce8  call    ?Run@ServiceControl@@SAJAEBUServiceOptions@@@Z; ServiceControl::Run(ServiceOptions const &)
0x140007ced  mov     rcx, [rsp+58h+var_18]
0x140007cf2  xor     rcx, rsp; StackCookie
0x140007cf5  call    __security_check_cookie
0x140007cfa  add     rsp, 58h
0x140007cfe  retn
```
