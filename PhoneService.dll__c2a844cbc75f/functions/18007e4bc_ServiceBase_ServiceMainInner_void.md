# ServiceBase::_ServiceMainInner(void)

- ea: `0x18007e4bc`
- end: `0x18007e72a`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `622`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007df68`

## callees

- `0x18001db10`
- `0x18007e4bc`
- `0x18007e730`
- `0x18007e9ac`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18007e6f2`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18007e6f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e57e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e59b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e59b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e56c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e705`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e712`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e56c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e705`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e712`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  const WCHAR *v2; // rbx
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  signed int v5; // ebx
  HANDLE EventW; // rbx
  bool v7; // sf
  __int64 v8; // rcx
  __int64 *v9; // rdx
  int v10; // eax
  signed int v11; // ecx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  if ( !qword_1800B4060 )
    return -2147467263;
  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(qword_1800B3FB0 + 88LL))(&qword_1800B3FB0);
  if ( v2 )
  {
    hKey = 0;
    phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, v2, 0, 0x20019u, phkResult);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 != -2147024894 )
    {
      if ( v5 >= 0 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return -2147023781;
      }
      else if ( hKey )
      {
        RegCloseKey(hKey);
      }
      return v5;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    (*(void (__fastcall **)(void *))(qword_1800B3FB0 + 64LL))(&qword_1800B3FB0);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW == hObject )
  {
    EventW = hObject;
  }
  else
  {
    if ( hObject )
      CloseHandle(hObject);
    hObject = EventW;
  }
  if ( EventW )
    goto LABEL_46;
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
  {
LABEL_46:
    result = ServiceBase::_UpdateStatus((ServiceBase *)&qword_1800B3FB0, 2u);
    if ( result >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(void *))(qword_1800B3FB0 + 8LL))(&qword_1800B3FB0);
      if ( v5 < 0 )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
          return v5;
        v9 = ServiceBaseServiceStartingError;
LABEL_23:
        McTemplateU0zq_EventWriteTransfer(v8, v9, &ServiceName, (unsigned int)v5);
        return v5;
      }
      LODWORD(qword_1800B402C) = 1;
      result = ServiceBase::_UpdateStatus((ServiceBase *)&qword_1800B3FB0, 4u);
      if ( result < 0 )
        return result;
      v5 = (*(__int64 (__fastcall **)(void *))(qword_1800B3FB0 + 24LL))(&qword_1800B3FB0);
      if ( v5 < 0 )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
          return v5;
        v9 = ServiceBaseServiceStartedError;
        goto LABEL_23;
      }
      v10 = (*(__int64 (__fastcall **)(__int64 *, WCHAR *, HANDLE, __int64 (__fastcall *)(), void *, int))(qword_1800B4060 + 192))(
              &qword_1800B4008,
              &ServiceName,
              hObject,
              StopCallback,
              &qword_1800B3FB0,
              8);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v11 >= 0 )
        v11 = 0;
      if ( v11 >= 0 )
      {
        if ( HIDWORD(qword_1800B402C) )
          (*(void (__fastcall **)(void *, _QWORD))(qword_1800B3FB0 + 32LL))(
            &qword_1800B3FB0,
            (unsigned int)dword_1800B4034);
        CoFreeUnusedLibrariesEx(0x7530u, 0);
        return 0;
      }
      else
      {
        return v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007e4bc  mov     [rsp+arg_8], rbx
0x18007e4c1  mov     [rsp+hKey], rcx
0x18007e4c6  push    rsi
0x18007e4c7  sub     rsp, 40h
0x18007e4cb  cmp     cs:qword_1800B4060, 0
0x18007e4d3  jnz     short loc_18007E4DF
0x18007e4d5  mov     eax, 80004001h
0x18007e4da  jmp     loc_18007E71F
0x18007e4df  mov     rax, cs:qword_1800B3FB0
0x18007e4e6  lea     rsi, qword_1800B3FB0
0x18007e4ed  mov     rcx, rsi
0x18007e4f0  mov     rax, [rax+58h]
0x18007e4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e4f9  mov     rbx, rax
0x18007e4fc  test    rax, rax
0x18007e4ff  jnz     short loc_18007E516
0x18007e501  mov     rax, cs:qword_1800B3FB0
0x18007e508  mov     rcx, rsi
0x18007e50b  mov     rax, [rax+40h]
0x18007e50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e514  jmp     short loc_18007E572
0x18007e516  lea     rcx, [rsp+48h+hKey]
0x18007e51b  mov     [rsp+48h+hKey], 0
0x18007e524  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18007e529  mov     r9d, 20019h; samDesired
0x18007e52f  mov     [rsp+48h+phkResult], rax; phkResult
0x18007e534  xor     r8d, r8d; ulOptions
0x18007e537  mov     rdx, rbx; lpSubKey
0x18007e53a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007e541  call    cs:__imp_RegOpenKeyExW
0x18007e547  mov     ebx, eax
0x18007e549  test    eax, eax
0x18007e54b  jle     short loc_18007E556
0x18007e54d  movzx   ebx, ax
0x18007e550  or      ebx, 80070000h
0x18007e556  mov     rcx, [rsp+48h+hKey]; hKey
0x18007e55b  cmp     ebx, 80070002h
0x18007e561  jnz     loc_18007E6FC
0x18007e567  test    rcx, rcx
0x18007e56a  jz      short loc_18007E572
0x18007e56c  call    cs:__imp_RegCloseKey
0x18007e572  xor     r9d, r9d; lpName
0x18007e575  xor     r8d, r8d; bInitialState
0x18007e578  xor     ecx, ecx; lpEventAttributes
0x18007e57a  lea     edx, [r9+1]; bManualReset
0x18007e57e  call    cs:__imp_CreateEventW
0x18007e584  mov     rbx, rax
0x18007e587  mov     rax, cs:hObject
0x18007e58e  cmp     rbx, rax
0x18007e591  jz      short loc_18007E5AA
0x18007e593  test    rax, rax
0x18007e596  jz      short loc_18007E5A1
0x18007e598  mov     rcx, rax; hObject
0x18007e59b  call    cs:__imp_CloseHandle
0x18007e5a1  mov     cs:hObject, rbx
0x18007e5a8  jmp     short loc_18007E5AD
0x18007e5aa  mov     rbx, rax
0x18007e5ad  test    rbx, rbx
0x18007e5b0  jnz     short loc_18007E5CC
0x18007e5b2  call    cs:__imp_GetLastError
0x18007e5b8  test    eax, eax
0x18007e5ba  jle     short loc_18007E5C6
0x18007e5bc  movzx   eax, ax
0x18007e5bf  or      eax, 80070000h
0x18007e5c4  test    eax, eax
0x18007e5c6  js      loc_18007E71F
0x18007e5cc  mov     edx, 2; unsigned int
0x18007e5d1  mov     rcx, rsi; this
0x18007e5d4  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18007e5d9  test    eax, eax
0x18007e5db  js      loc_18007E71F
0x18007e5e1  mov     rax, cs:qword_1800B3FB0
0x18007e5e8  mov     rcx, rsi
0x18007e5eb  mov     rax, [rax+8]
0x18007e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e5f4  mov     ebx, eax
0x18007e5f6  test    eax, eax
0x18007e5f8  jns     short loc_18007E622
0x18007e5fa  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18007e601  jz      loc_18007E71D
0x18007e607  lea     rdx, ServiceBaseServiceStartingError
0x18007e60e  lea     r8, ServiceName
0x18007e615  mov     r9d, ebx
0x18007e618  call    McTemplateU0zq_EventWriteTransfer
0x18007e61d  jmp     loc_18007E71D
0x18007e622  mov     edx, 4; unsigned int
0x18007e627  mov     dword ptr cs:qword_1800B402C, 1
0x18007e631  mov     rcx, rsi; this
0x18007e634  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18007e639  test    eax, eax
0x18007e63b  js      loc_18007E71F
0x18007e641  mov     rax, cs:qword_1800B3FB0
0x18007e648  mov     rcx, rsi
0x18007e64b  mov     rax, [rax+18h]
0x18007e64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e654  mov     ebx, eax
0x18007e656  test    eax, eax
0x18007e658  jns     short loc_18007E670
0x18007e65a  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18007e661  jz      loc_18007E71D
0x18007e667  lea     rdx, ServiceBaseServiceStartedError
0x18007e66e  jmp     short loc_18007E60E
0x18007e670  mov     rax, cs:qword_1800B4060
0x18007e677  lea     r9, StopCallback
0x18007e67e  mov     r8, cs:hObject
0x18007e685  lea     rdx, ServiceName
0x18007e68c  mov     [rsp+48h+var_20], 8
0x18007e694  lea     rcx, qword_1800B4008
0x18007e69b  mov     [rsp+48h+phkResult], rsi
0x18007e6a0  mov     rax, [rax+0C0h]
0x18007e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6ac  mov     ecx, eax
0x18007e6ae  test    eax, eax
0x18007e6b0  jle     short loc_18007E6BB
0x18007e6b2  movzx   ecx, ax
0x18007e6b5  or      ecx, 80070000h
0x18007e6bb  xor     eax, eax
0x18007e6bd  test    ecx, ecx
0x18007e6bf  cmovns  ecx, eax
0x18007e6c2  test    ecx, ecx
0x18007e6c4  jns     short loc_18007E6CA
0x18007e6c6  mov     eax, ecx
0x18007e6c8  jmp     short loc_18007E71F
0x18007e6ca  cmp     dword ptr cs:qword_1800B402C+4, eax
0x18007e6d0  jz      short loc_18007E6EB
0x18007e6d2  mov     rax, cs:qword_1800B3FB0
0x18007e6d9  mov     rcx, rsi
0x18007e6dc  mov     edx, cs:dword_1800B4034
0x18007e6e2  mov     rax, [rax+20h]
0x18007e6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e6eb  xor     edx, edx; dwReserved
0x18007e6ed  mov     ecx, 7530h; dwUnloadDelay
0x18007e6f2  call    cs:__imp_CoFreeUnusedLibrariesEx
0x18007e6f8  xor     eax, eax
0x18007e6fa  jmp     short loc_18007E71F
0x18007e6fc  test    ebx, ebx
0x18007e6fe  jns     short loc_18007E70D
0x18007e700  test    rcx, rcx
0x18007e703  jz      short loc_18007E71D
0x18007e705  call    cs:__imp_RegCloseKey
0x18007e70b  jmp     short loc_18007E71D
0x18007e70d  test    rcx, rcx
0x18007e710  jz      short loc_18007E718
0x18007e712  call    cs:__imp_RegCloseKey
0x18007e718  mov     ebx, 8007045Bh
0x18007e71d  mov     eax, ebx
0x18007e71f  mov     rbx, [rsp+48h+arg_8]
0x18007e724  add     rsp, 40h
0x18007e728  pop     rsi
0x18007e729  retn
```
