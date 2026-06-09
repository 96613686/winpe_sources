# ServiceBase::_ServiceMainInner(void)

- ea: `0x1800062dc`
- end: `0x180006542`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `614`
- prototype: `signed int __fastcall(ServiceBase *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005d98`

## callees

- `0x1800062dc`
- `0x180006548`
- `0x1800067bc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006396`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ca`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000650a`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000650a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000651d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000652a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000651d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000652a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006359`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063b3`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  HANDLE EventW; // rbx
  bool v6; // sf
  __int64 v7; // rcx
  __int64 *v8; // rdx
  int v9; // eax
  signed int v10; // ecx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  if ( !qword_180013150 )
    return -2147467263;
  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(off_1800130A0 + 88LL))(&off_1800130A0);
  if ( v2 )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, v2, 0, 0x20019u, &hKey);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 != -2147024894 )
    {
      if ( v4 >= 0 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return -2147023781;
      }
      else if ( hKey )
      {
        RegCloseKey(hKey);
      }
      return v4;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    (*(void (__fastcall **)(void *))(off_1800130A0 + 64LL))(&off_1800130A0);
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
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 )
  {
LABEL_46:
    result = ServiceBase::_UpdateStatus((ServiceBase *)&off_1800130A0, 2u);
    if ( result >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(void *))(off_1800130A0 + 8LL))(&off_1800130A0);
      if ( v4 < 0 )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
          return v4;
        v8 = ServiceBaseServiceStartingError;
LABEL_23:
        McTemplateU0zq_EventWriteTransfer(v7, v8, &ServiceName, (unsigned int)v4);
        return v4;
      }
      LODWORD(qword_18001311C) = 1;
      result = ServiceBase::_UpdateStatus((ServiceBase *)&off_1800130A0, 4u);
      if ( result < 0 )
        return result;
      v4 = (*(__int64 (__fastcall **)(void *))(off_1800130A0 + 24LL))(&off_1800130A0);
      if ( v4 < 0 )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
          return v4;
        v8 = ServiceBaseServiceStartedError;
        goto LABEL_23;
      }
      v9 = (*(__int64 (__fastcall **)(__int64 *, WCHAR *, HANDLE, __int64 (__fastcall *)(), void *, int))(qword_180013150 + 192))(
             &qword_1800130F8,
             &ServiceName,
             hObject,
             StopCallback,
             &off_1800130A0,
             8);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v10 >= 0 )
        v10 = 0;
      if ( v10 >= 0 )
      {
        if ( HIDWORD(qword_18001311C) )
          (*(void (__fastcall **)(void *, _QWORD))(off_1800130A0 + 32LL))(&off_1800130A0, (unsigned int)dword_180013124);
        CoFreeUnusedLibrariesEx(0x7530u, 0);
        return 0;
      }
      else
      {
        return v10;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800062dc  mov     [rsp+arg_8], rbx
0x1800062e1  mov     [rsp+hKey], rcx
0x1800062e6  push    rsi
0x1800062e7  sub     rsp, 40h
0x1800062eb  cmp     cs:qword_180013150, 0
0x1800062f3  jnz     short loc_1800062FF
0x1800062f5  mov     eax, 80004001h
0x1800062fa  jmp     loc_180006537
0x1800062ff  mov     rax, cs:off_1800130A0
0x180006306  lea     rsi, off_1800130A0
0x18000630d  mov     rcx, rsi
0x180006310  mov     rax, [rax+58h]
0x180006314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006319  test    rax, rax
0x18000631c  jnz     short loc_180006333
0x18000631e  mov     rax, cs:off_1800130A0
0x180006325  mov     rcx, rsi
0x180006328  mov     rax, [rax+40h]
0x18000632c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006331  jmp     short loc_18000638A
0x180006333  lea     rcx, [rsp+48h+hKey]
0x180006338  mov     [rsp+48h+hKey], 0
0x180006341  mov     [rsp+48h+phkResult], rcx; phkResult
0x180006346  mov     r9d, 20019h; samDesired
0x18000634c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006353  xor     r8d, r8d; ulOptions
0x180006356  mov     rdx, rax; lpSubKey
0x180006359  call    cs:__imp_RegOpenKeyExW
0x18000635f  mov     ebx, eax
0x180006361  test    eax, eax
0x180006363  jle     short loc_18000636E
0x180006365  movzx   ebx, ax
0x180006368  or      ebx, 80070000h
0x18000636e  mov     rcx, [rsp+48h+hKey]; hKey
0x180006373  cmp     ebx, 80070002h
0x180006379  jnz     loc_180006514
0x18000637f  test    rcx, rcx
0x180006382  jz      short loc_18000638A
0x180006384  call    cs:__imp_RegCloseKey
0x18000638a  xor     r9d, r9d; lpName
0x18000638d  xor     r8d, r8d; bInitialState
0x180006390  xor     ecx, ecx; lpEventAttributes
0x180006392  lea     edx, [r9+1]; bManualReset
0x180006396  call    cs:__imp_CreateEventW
0x18000639c  mov     rbx, rax
0x18000639f  mov     rax, cs:hObject
0x1800063a6  cmp     rbx, rax
0x1800063a9  jz      short loc_1800063C2
0x1800063ab  test    rax, rax
0x1800063ae  jz      short loc_1800063B9
0x1800063b0  mov     rcx, rax; hObject
0x1800063b3  call    cs:__imp_CloseHandle
0x1800063b9  mov     cs:hObject, rbx
0x1800063c0  jmp     short loc_1800063C5
0x1800063c2  mov     rbx, rax
0x1800063c5  test    rbx, rbx
0x1800063c8  jnz     short loc_1800063E4
0x1800063ca  call    cs:__imp_GetLastError
0x1800063d0  test    eax, eax
0x1800063d2  jle     short loc_1800063DE
0x1800063d4  movzx   eax, ax
0x1800063d7  or      eax, 80070000h
0x1800063dc  test    eax, eax
0x1800063de  js      loc_180006537
0x1800063e4  mov     edx, 2; unsigned int
0x1800063e9  mov     rcx, rsi; this
0x1800063ec  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x1800063f1  test    eax, eax
0x1800063f3  js      loc_180006537
0x1800063f9  mov     rax, cs:off_1800130A0
0x180006400  mov     rcx, rsi
0x180006403  mov     rax, [rax+8]
0x180006407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000640c  mov     ebx, eax
0x18000640e  test    eax, eax
0x180006410  jns     short loc_18000643A
0x180006412  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x180006419  jz      loc_180006535
0x18000641f  lea     rdx, ServiceBaseServiceStartingError
0x180006426  lea     r8, ServiceName
0x18000642d  mov     r9d, ebx
0x180006430  call    McTemplateU0zq_EventWriteTransfer
0x180006435  jmp     loc_180006535
0x18000643a  mov     edx, 4; unsigned int
0x18000643f  mov     dword ptr cs:qword_18001311C, 1
0x180006449  mov     rcx, rsi; this
0x18000644c  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x180006451  test    eax, eax
0x180006453  js      loc_180006537
0x180006459  mov     rax, cs:off_1800130A0
0x180006460  mov     rcx, rsi
0x180006463  mov     rax, [rax+18h]
0x180006467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646c  mov     ebx, eax
0x18000646e  test    eax, eax
0x180006470  jns     short loc_180006488
0x180006472  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x180006479  jz      loc_180006535
0x18000647f  lea     rdx, ServiceBaseServiceStartedError
0x180006486  jmp     short loc_180006426
0x180006488  mov     rax, cs:qword_180013150
0x18000648f  lea     r9, StopCallback
0x180006496  mov     r8, cs:hObject
0x18000649d  lea     rdx, ServiceName
0x1800064a4  mov     [rsp+48h+var_20], 8
0x1800064ac  lea     rcx, qword_1800130F8
0x1800064b3  mov     [rsp+48h+phkResult], rsi
0x1800064b8  mov     rax, [rax+0C0h]
0x1800064bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c4  mov     ecx, eax
0x1800064c6  test    eax, eax
0x1800064c8  jle     short loc_1800064D3
0x1800064ca  movzx   ecx, ax
0x1800064cd  or      ecx, 80070000h
0x1800064d3  xor     eax, eax
0x1800064d5  test    ecx, ecx
0x1800064d7  cmovns  ecx, eax
0x1800064da  test    ecx, ecx
0x1800064dc  jns     short loc_1800064E2
0x1800064de  mov     eax, ecx
0x1800064e0  jmp     short loc_180006537
0x1800064e2  cmp     dword ptr cs:qword_18001311C+4, eax
0x1800064e8  jz      short loc_180006503
0x1800064ea  mov     rax, cs:off_1800130A0
0x1800064f1  mov     rcx, rsi
0x1800064f4  mov     edx, cs:dword_180013124
0x1800064fa  mov     rax, [rax+20h]
0x1800064fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006503  xor     edx, edx; dwReserved
0x180006505  mov     ecx, 7530h; dwUnloadDelay
0x18000650a  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180006510  xor     eax, eax
0x180006512  jmp     short loc_180006537
0x180006514  test    ebx, ebx
0x180006516  jns     short loc_180006525
0x180006518  test    rcx, rcx
0x18000651b  jz      short loc_180006535
0x18000651d  call    cs:__imp_RegCloseKey
0x180006523  jmp     short loc_180006535
0x180006525  test    rcx, rcx
0x180006528  jz      short loc_180006530
0x18000652a  call    cs:__imp_RegCloseKey
0x180006530  mov     ebx, 8007045Bh
0x180006535  mov     eax, ebx
0x180006537  mov     rbx, [rsp+48h+arg_8]
0x18000653c  add     rsp, 40h
0x180006540  pop     rsi
0x180006541  retn
```
