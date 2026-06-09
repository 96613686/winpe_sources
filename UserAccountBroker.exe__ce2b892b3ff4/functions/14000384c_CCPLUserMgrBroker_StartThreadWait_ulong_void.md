# CCPLUserMgrBroker::_StartThreadWait(ulong (*)(void *))

- ea: `0x14000384c`
- end: `0x140003b05`
- name: `?_StartThreadWait@CCPLUserMgrBroker@@AEAAJP6AKPEAX@Z@Z`
- size: `697`
- prototype: `__int64 __fastcall(char *Context, WCHAR ch)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400032c0`
- `0x1400033f0`

## callees

- `0x140002dc0`
- `0x14000384c`
- `0x140005028`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x1400038cd`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400038fd`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14000396e`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400038cd`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1400038fd`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14000396e`
- `KERNEL32!UnregisterWait` at `0x140003a06`
- `KERNEL32!UnregisterWait` at `0x140003a1d`
- `KERNEL32!UnregisterWait` at `0x140003a34`
- `KERNEL32!UnregisterWait` at `0x140003a06`
- `KERNEL32!UnregisterWait` at `0x140003a1d`
- `KERNEL32!UnregisterWait` at `0x140003a34`
- `KERNEL32!GetProcessId` at `0x140003929`
- `KERNEL32!GetProcessId` at `0x140003929`
- `KERNEL32!OpenProcess` at `0x140003945`
- `KERNEL32!OpenProcess` at `0x140003945`
- `KERNEL32!CreateEventW` at `0x14000386e`
- `KERNEL32!CreateEventW` at `0x140003a9e`
- `KERNEL32!CreateEventW` at `0x14000386e`
- `KERNEL32!CreateEventW` at `0x140003a9e`
- `KERNEL32!GetLastError` at `0x140003976`
- `KERNEL32!GetLastError` at `0x14000399c`
- `KERNEL32!GetLastError` at `0x140003976`
- `KERNEL32!GetLastError` at `0x14000399c`
- `KERNEL32!SetEvent` at `0x140003aaf`
- `KERNEL32!SetEvent` at `0x140003aaf`
- `KERNEL32!CloseHandle` at `0x14000388d`
- `KERNEL32!CloseHandle` at `0x140003ae2`
- `KERNEL32!CloseHandle` at `0x14000388d`
- `KERNEL32!CloseHandle` at `0x140003ae2`
- `KERNEL32!GetCurrentProcessId` at `0x140003a71`
- `KERNEL32!GetCurrentProcessId` at `0x140003a71`
- `USER32!GetWindowThreadProcessId` at `0x140003917`
- `USER32!GetWindowThreadProcessId` at `0x140003917`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400039f5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140003ad3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400039f5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140003ad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003af0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003af0`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x140003992`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x140003992`

## pseudocode

```c
__int64 __fastcall CCPLUserMgrBroker::_StartThreadWait(char *Context, WCHAR ch)
{
  HANDLE EventW; // rax
  char *v5; // rcx
  HANDLE v6; // rdi
  void *v7; // rdx
  HANDLE *v8; // rdi
  HWND v9; // rcx
  DWORD ProcessId; // eax
  DWORD v11; // r8d
  HANDLE v12; // rax
  HANDLE *v13; // r14
  signed int LastError; // eax
  signed int v15; // edi
  HRESULT v16; // eax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  DWORD CurrentProcessId; // eax
  int v21; // eax
  WCHAR *v22; // rsi
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE pHandles; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+38h] [rbp-30h]
  LPCWSTR lpName[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD dwProcessId; // [rsp+A0h] [rbp+38h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (char *)*((_QWORD *)Context + 4);
  v6 = EventW;
  *((_QWORD *)Context + 4) = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  *((_QWORD *)Context + 4) = v6;
  if ( v6 )
  {
    v7 = (void *)*((_QWORD *)Context + 5);
    if ( v7 )
      RegisterWaitForSingleObject(
        (PHANDLE)Context + 6,
        v7,
        CCPLUserMgrBroker::_s_TriggerFlowCancel,
        Context,
        0xFFFFFFFF,
        8u);
    v8 = (HANDLE *)(Context + 56);
    if ( (int)CallerIdentity::GetCallingProcessHandle(v5, v7, Context + 56) >= 0 )
      RegisterWaitForSingleObject(
        (PHANDLE)Context + 8,
        *v8,
        CCPLUserMgrBroker::_s_TriggerFlowCancel,
        Context,
        0xFFFFFFFF,
        8u);
    v9 = (HWND)*((_QWORD *)Context + 11);
    if ( v9 )
    {
      dwProcessId = 0;
      if ( !GetWindowThreadProcessId(v9, &dwProcessId) )
        goto LABEL_16;
      if ( *v8 )
      {
        ProcessId = GetProcessId(*v8);
        v11 = dwProcessId;
        if ( dwProcessId == ProcessId )
          goto LABEL_17;
      }
      else
      {
        v11 = dwProcessId;
      }
      v12 = OpenProcess(0x100000u, 0, v11);
      *((_QWORD *)Context + 9) = v12;
      if ( v12 )
        RegisterWaitForSingleObject(
          (PHANDLE)Context + 10,
          v12,
          CCPLUserMgrBroker::_s_TriggerFlowCancel,
          Context,
          0xFFFFFFFF,
          8u);
      else
LABEL_16:
        GetLastError();
    }
  }
LABEL_17:
  v13 = (HANDLE *)(Context + 24);
  if ( SHCreateThreadWithHandle(ch) )
  {
    pHandles = *v13;
    v27 = *((_QWORD *)Context + 4);
    dwProcessId = 0;
    v16 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, (v27 != 0) + 1, &pHandles, &dwProcessId);
    v17 = (void *)*((_QWORD *)Context + 6);
    v15 = v16;
    if ( v17 )
    {
      UnregisterWait(v17);
      *((_QWORD *)Context + 6) = 0;
    }
    v18 = (void *)*((_QWORD *)Context + 8);
    if ( v18 )
    {
      UnregisterWait(v18);
      *((_QWORD *)Context + 8) = 0;
    }
    v19 = (void *)*((_QWORD *)Context + 10);
    if ( v19 )
    {
      UnregisterWait(v19);
      *((_QWORD *)Context + 10) = 0;
    }
    if ( !v15 && dwProcessId == 1 )
    {
      v15 = -2147023673;
      memset(lpName, 0, 24);
      CurrentProcessId = GetCurrentProcessId();
      v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              lpName,
              L"Local\\UAMCloseFlow%d",
              CurrentProcessId);
      v22 = (WCHAR *)lpName[0];
      if ( v21 >= 0 )
      {
        v23 = CreateEventW(0, 1, 0, lpName[0]);
        v24 = v23;
        if ( v23 )
        {
          if ( SetEvent(v23) )
            CoWaitForMultipleHandles(8u, 0x7D0u, 1u, v13, &dwProcessId);
          if ( v24 != (void *)-1LL )
            CloseHandle(v24);
        }
      }
      if ( v22 )
        CoTaskMemFree(v22);
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( v15 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000384c  push    rbp
0x14000384e  push    rbx
0x14000384f  push    rsi
0x140003850  push    rdi
0x140003851  push    r12
0x140003853  push    r14
0x140003855  mov     rbp, rsp
0x140003858  sub     rsp, 68h
0x14000385c  xor     r9d, r9d; lpName
0x14000385f  mov     rsi, rdx
0x140003862  mov     rbx, rcx
0x140003865  xor     r8d, r8d; bInitialState
0x140003868  xor     ecx, ecx; lpEventAttributes
0x14000386a  lea     edx, [r9+1]; bManualReset
0x14000386e  call    cs:__imp_CreateEventW
0x140003874  mov     rcx, [rbx+20h]; hObject
0x140003878  mov     rdi, rax
0x14000387b  mov     qword ptr [rbx+20h], 0
0x140003883  lea     rdx, [rcx-1]
0x140003887  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000388b  ja      short loc_140003893
0x14000388d  call    cs:__imp_CloseHandle
0x140003893  mov     [rbx+20h], rdi
0x140003897  mov     r12d, 8
0x14000389d  test    rdi, rdi
0x1400038a0  jz      loc_14000397C
0x1400038a6  mov     rdx, [rbx+28h]; hObject
0x1400038aa  lea     r14, ?_s_TriggerFlowCancel@CCPLUserMgrBroker@@CAXPEAXE@Z; CCPLUserMgrBroker::_s_TriggerFlowCancel(void *,uchar)
0x1400038b1  test    rdx, rdx
0x1400038b4  jz      short loc_1400038D3
0x1400038b6  lea     rcx, [rbx+30h]; phNewWaitObject
0x1400038ba  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x1400038bf  mov     r9, rbx; Context
0x1400038c2  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400038ca  mov     r8, r14; Callback
0x1400038cd  call    cs:__imp_RegisterWaitForSingleObject
0x1400038d3  lea     rdi, [rbx+38h]
0x1400038d7  mov     r8, rdi
0x1400038da  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x1400038df  test    eax, eax
0x1400038e1  js      short loc_140003903
0x1400038e3  mov     rdx, [rdi]; hObject
0x1400038e6  lea     rcx, [rbx+40h]; phNewWaitObject
0x1400038ea  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x1400038ef  mov     r9, rbx; Context
0x1400038f2  mov     r8, r14; Callback
0x1400038f5  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400038fd  call    cs:__imp_RegisterWaitForSingleObject
0x140003903  mov     rcx, [rbx+58h]; hWnd
0x140003907  test    rcx, rcx
0x14000390a  jz      short loc_14000397C
0x14000390c  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x140003910  mov     [rbp+dwProcessId], 0
0x140003917  call    cs:__imp_GetWindowThreadProcessId
0x14000391d  test    eax, eax
0x14000391f  jz      short loc_140003976
0x140003921  mov     rcx, [rdi]; Process
0x140003924  test    rcx, rcx
0x140003927  jz      short loc_14000393A
0x140003929  call    cs:__imp_GetProcessId
0x14000392f  mov     r8d, [rbp+dwProcessId]
0x140003933  cmp     r8d, eax
0x140003936  jz      short loc_14000397C
0x140003938  jmp     short loc_14000393E
0x14000393a  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x14000393e  xor     edx, edx; bInheritHandle
0x140003940  mov     ecx, 100000h; dwDesiredAccess
0x140003945  call    cs:__imp_OpenProcess
0x14000394b  mov     [rbx+48h], rax
0x14000394f  test    rax, rax
0x140003952  jz      short loc_140003976
0x140003954  lea     rcx, [rbx+50h]; phNewWaitObject
0x140003958  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x14000395d  mov     r9, rbx; Context
0x140003960  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x140003968  mov     r8, r14; Callback
0x14000396b  mov     rdx, rax; hObject
0x14000396e  call    cs:__imp_RegisterWaitForSingleObject
0x140003974  jmp     short loc_14000397C
0x140003976  call    cs:__imp_GetLastError
0x14000397c  xor     r9d, r9d
0x14000397f  lea     r14, [rbx+18h]
0x140003983  mov     rdx, rbx
0x140003986  mov     qword ptr [rsp+68h+dwMilliseconds], r14
0x14000398b  mov     rcx, rsi; ch
0x14000398e  lea     r8d, [r9+40h]
0x140003992  call    cs:__imp_SHCreateThreadWithHandle
0x140003998  test    eax, eax
0x14000399a  jnz     short loc_1400039C0
0x14000399c  call    cs:__imp_GetLastError
0x1400039a2  mov     edi, eax
0x1400039a4  test    eax, eax
0x1400039a6  jle     short loc_1400039B1
0x1400039a8  movzx   edi, ax
0x1400039ab  or      edi, 80070000h
0x1400039b1  test    edi, edi
0x1400039b3  mov     eax, 80004005h
0x1400039b8  cmovns  edi, eax
0x1400039bb  jmp     loc_140003AF6
0x1400039c0  mov     rax, [r14]
0x1400039c3  lea     r9, [rbp+pHandles]; pHandles
0x1400039c7  mov     [rbp+pHandles], rax
0x1400039cb  mov     ecx, r12d; dwFlags
0x1400039ce  mov     rax, [rbx+20h]
0x1400039d2  mov     [rbp+var_30], rax
0x1400039d6  neg     rax
0x1400039d9  lea     rax, [rbp+dwProcessId]
0x1400039dd  mov     [rbp+dwProcessId], 0
0x1400039e4  sbb     r8d, r8d
0x1400039e7  mov     qword ptr [rsp+68h+dwMilliseconds], rax; lpdwindex
0x1400039ec  neg     r8d
0x1400039ef  or      edx, 0FFFFFFFFh; dwTimeout
0x1400039f2  inc     r8d; cHandles
0x1400039f5  call    cs:__imp_CoWaitForMultipleHandles
0x1400039fb  mov     rcx, [rbx+30h]; WaitHandle
0x1400039ff  mov     edi, eax
0x140003a01  test    rcx, rcx
0x140003a04  jz      short loc_140003A14
0x140003a06  call    cs:__imp_UnregisterWait
0x140003a0c  mov     qword ptr [rbx+30h], 0
0x140003a14  mov     rcx, [rbx+40h]; WaitHandle
0x140003a18  test    rcx, rcx
0x140003a1b  jz      short loc_140003A2B
0x140003a1d  call    cs:__imp_UnregisterWait
0x140003a23  mov     qword ptr [rbx+40h], 0
0x140003a2b  mov     rcx, [rbx+50h]; WaitHandle
0x140003a2f  test    rcx, rcx
0x140003a32  jz      short loc_140003A42
0x140003a34  call    cs:__imp_UnregisterWait
0x140003a3a  mov     qword ptr [rbx+50h], 0
0x140003a42  test    edi, edi
0x140003a44  jnz     loc_140003AF6
0x140003a4a  cmp     [rbp+dwProcessId], 1
0x140003a4e  jnz     loc_140003AF6
0x140003a54  mov     edi, 800704C7h
0x140003a59  mov     [rbp+lpName], 0
0x140003a61  mov     [rbp+var_20], 0
0x140003a69  mov     [rbp+var_18], 0
0x140003a71  call    cs:__imp_GetCurrentProcessId
0x140003a77  mov     r8d, eax
0x140003a7a  lea     rdx, aLocalUamclosef; "Local\\UAMCloseFlow%d"
0x140003a81  lea     rcx, [rbp+lpName]
0x140003a85  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x140003a8a  mov     rsi, [rbp+lpName]
0x140003a8e  test    eax, eax
0x140003a90  js      short loc_140003AE8
0x140003a92  xor     r8d, r8d; bInitialState
0x140003a95  mov     r9, rsi; lpName
0x140003a98  xor     ecx, ecx; lpEventAttributes
0x140003a9a  lea     edx, [r8+1]; bManualReset
0x140003a9e  call    cs:__imp_CreateEventW
0x140003aa4  mov     rbx, rax
0x140003aa7  test    rax, rax
0x140003aaa  jz      short loc_140003AE8
0x140003aac  mov     rcx, rax; hEvent
0x140003aaf  call    cs:__imp_SetEvent
0x140003ab5  test    eax, eax
0x140003ab7  jz      short loc_140003AD9
0x140003ab9  lea     rax, [rbp+dwProcessId]
0x140003abd  mov     r9, r14; pHandles
0x140003ac0  mov     edx, 7D0h; dwTimeout
0x140003ac5  mov     qword ptr [rsp+68h+dwMilliseconds], rax; lpdwindex
0x140003aca  mov     r8d, 1; cHandles
0x140003ad0  mov     ecx, r12d; dwFlags
0x140003ad3  call    cs:__imp_CoWaitForMultipleHandles
0x140003ad9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140003add  jz      short loc_140003AE8
0x140003adf  mov     rcx, rbx; hObject
0x140003ae2  call    cs:__imp_CloseHandle
0x140003ae8  test    rsi, rsi
0x140003aeb  jz      short loc_140003AF6
0x140003aed  mov     rcx, rsi; pv
0x140003af0  call    cs:__imp_CoTaskMemFree
0x140003af6  mov     eax, edi
0x140003af8  add     rsp, 68h
0x140003afc  pop     r14
0x140003afe  pop     r12
0x140003b00  pop     rdi
0x140003b01  pop     rsi
0x140003b02  pop     rbx
0x140003b03  pop     rbp
0x140003b04  retn
```
