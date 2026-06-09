# CreateSvcStartEvent

- ea: `0x18002e5ac`
- end: `0x18002ea6f`
- name: `CreateSvcStartEvent`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f0f0`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002cd9c`
- `0x18002d9ac`
- `0x18002db3c`
- `0x18002dc40`
- `0x18002e5ac`
- `0x180031f94`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetVersion` at `0x18002e65d`
- `KERNEL32!GetVersion` at `0x18002e65d`
- `KERNEL32!CreateEventW` at `0x18002e899`
- `KERNEL32!CreateEventW` at `0x18002e899`
- `KERNEL32!SetEvent` at `0x18002e9a9`
- `KERNEL32!SetEvent` at `0x18002e9a9`
- `KERNEL32!CloseHandle` at `0x18002e93e`
- `KERNEL32!CloseHandle` at `0x18002e93e`
- `KERNEL32!GetLastError` at `0x18002e6c5`
- `KERNEL32!GetLastError` at `0x18002e7dd`
- `KERNEL32!GetLastError` at `0x18002e8ad`
- `KERNEL32!GetLastError` at `0x18002e9b9`
- `KERNEL32!GetLastError` at `0x18002e6c5`
- `KERNEL32!GetLastError` at `0x18002e7dd`
- `KERNEL32!GetLastError` at `0x18002e8ad`
- `KERNEL32!GetLastError` at `0x18002e9b9`
- `KERNEL32!GetSystemDirectoryW` at `0x18002e6b5`
- `KERNEL32!GetSystemDirectoryW` at `0x18002e6b5`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18002e8f9`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18002e8f9`
- `ADVAPI32!RegCloseKey` at `0x18002e958`
- `ADVAPI32!RegCloseKey` at `0x18002e958`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e84b`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e84b`

## string_xrefs

- `0x18002e83d`: `Software\Microsoft\Fax\Client\ServiceStartup`

## pseudocode

```c
__int64 __fastcall CreateSvcStartEvent(_QWORD *a1, HKEY *a2)
{
  _BYTE *v4; // rcx
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  int v7; // eax
  void *SvcStartEventWithGlobalNamedEvent; // rax
  HANDLE EventW; // rax
  void *v11; // rdi
  DWORD v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rcx
  HKEY v18; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  SC_HANDLE v22; // [rsp+50h] [rbp-B0h] BYREF
  SC_HANDLE hSCObject; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+64h] [rbp-9Ch]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR tstrFilename[520]; // [rsp+290h] [rbp+190h] BYREF

  hKey = 0;
  hSCObject = 0;
  v22 = 0;
  v20 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_db036311db36307996a98c23702218b2_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 )
  {
    LastError = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 2) == 0 || v4[25] < 2u )
      return LastError;
    v6 = 22;
    goto LABEL_69;
  }
  if ( (unsigned __int8)GetVersion() < 5u || (unsigned int)IsServerSku() )
    goto LABEL_35;
  v25 = 0;
  memset_0(Buffer, 0, 0x20Au);
  memset_0(tstrFilename, 0, sizeof(tstrFilename));
  if ( !GetSystemDirectoryW(Buffer, 0x105u) )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v6 = 23;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    return LastError;
  }
  v7 = StringCchPrintfW(tstrFilename, 0x208u, L"%s\\FXSSVC.EXE", Buffer);
  if ( v7 >= 0 )
  {
    v24 = 20;
    LastError = GetFileVersion(tstrFilename);
    if ( (LastError & 0xFFFFFFFD) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return LastError;
      }
      v6 = 25;
      goto LABEL_69;
    }
    if ( DWORD1(v25) == 131077 && (WORD4(v25) == 1776 || WORD4(v25) == 2600) )
    {
      SvcStartEventWithGlobalNamedEvent = CreateSvcStartEventWithGlobalNamedEvent();
      if ( !SvcStartEventWithGlobalNamedEvent )
      {
        LastError = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return LastError;
        }
        v6 = 26;
        goto LABEL_69;
      }
      *a2 = 0;
      *a1 = SvcStartEventWithGlobalNamedEvent;
      return 0;
    }
LABEL_35:
    LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client\\ServiceStartup", 0, 0x111u, &hKey);
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return LastError;
      }
      v6 = 27;
      goto LABEL_69;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    v11 = EventW;
    if ( EventW )
    {
      v15 = RegNotifyChangeKeyValue(hKey, 0, 4u, EventW, 1);
      LastError = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_db036311db36307996a98c23702218b2_Traceguids, v15);
        }
        goto LABEL_50;
      }
      LastError = FaxOpenService(v17, v16, &hSCObject, &v22, phkResult, 4u, &v20);
      if ( LastError )
      {
LABEL_50:
        CloseHandle(v11);
        goto LABEL_51;
      }
      FaxCloseService(hSCObject, v22);
      if ( v20 != 4 || SetEvent(v11) )
      {
LABEL_64:
        v18 = hKey;
        *a1 = v11;
        *a2 = v18;
        return 0;
      }
      v12 = GetLastError();
      LastError = v12;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 30;
        goto LABEL_60;
      }
    }
    else
    {
      v12 = GetLastError();
      LastError = v12;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 28;
LABEL_60:
        WPP_SF_d(v13[2], v14, WPP_db036311db36307996a98c23702218b2_Traceguids, v12);
      }
    }
    if ( LastError )
    {
      if ( !v11 )
      {
LABEL_51:
        if ( hKey )
          RegCloseKey(hKey);
        return LastError;
      }
      goto LABEL_50;
    }
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_db036311db36307996a98c23702218b2_Traceguids, (unsigned int)v7);
  }
  return 267;
}

```

## disassembly

```asm
0x18002e5ac  mov     [rsp-8+arg_10], rbx
0x18002e5b1  mov     [rsp-8+arg_18], rsi
0x18002e5b6  push    rbp
0x18002e5b7  push    rdi
0x18002e5b8  push    r13
0x18002e5ba  push    r14
0x18002e5bc  push    r15
0x18002e5be  lea     rbp, [rsp-5B0h]
0x18002e5c6  sub     rsp, 6B0h
0x18002e5cd  mov     rax, cs:__security_cookie
0x18002e5d4  xor     rax, rsp
0x18002e5d7  mov     [rbp+5D0h+var_30], rax
0x18002e5de  mov     r14, rdx
0x18002e5e1  mov     [rsp+6D0h+hKey], 0
0x18002e5ea  mov     rsi, rcx
0x18002e5ed  mov     [rsp+6D0h+hSCObject], 0
0x18002e5f6  mov     [rsp+6D0h+var_680], 0
0x18002e5ff  mov     [rsp+6D0h+var_690], 0
0x18002e607  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e60e  lea     r13, WPP_GLOBAL_Control
0x18002e615  lea     rdi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e61c  mov     ebx, 5
0x18002e621  lea     r15d, [rbx-3]
0x18002e625  cmp     rcx, r13
0x18002e628  jz      short loc_18002E64B
0x18002e62a  test    [rcx+1Ch], r15b
0x18002e62e  jz      short loc_18002E64B
0x18002e630  cmp     [rcx+19h], bl
0x18002e633  jb      short loc_18002E64B
0x18002e635  mov     rcx, [rcx+10h]
0x18002e639  lea     edx, [rbx+10h]
0x18002e63c  mov     r8, rdi
0x18002e63f  call    WPP_SF_
0x18002e644  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e64b  test    rsi, rsi
0x18002e64e  jz      loc_18002EA19
0x18002e654  test    r14, r14
0x18002e657  jz      loc_18002EA19
0x18002e65d  call    cs:__imp_GetVersion
0x18002e664  nop     dword ptr [rax+rax+00h]
0x18002e669  cmp     al, bl
0x18002e66b  jb      loc_18002E82A
0x18002e671  call    IsServerSku
0x18002e676  test    eax, eax
0x18002e678  jnz     loc_18002E82A
0x18002e67e  xorps   xmm0, xmm0
0x18002e681  lea     rcx, [rbp+5D0h+Buffer]; void *
0x18002e685  xor     edx, edx; Val
0x18002e687  mov     r8d, 20Ah; Size
0x18002e68d  movdqu  [rsp+6D0h+var_66C], xmm0
0x18002e693  call    memset_0
0x18002e698  xor     edx, edx; Val
0x18002e69a  lea     rcx, [rbp+5D0h+tstrFilename]; void *
0x18002e6a1  mov     r8d, 410h; Size
0x18002e6a7  call    memset_0
0x18002e6ac  mov     edx, 105h; uSize
0x18002e6b1  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x18002e6b5  call    cs:__imp_GetSystemDirectoryW
0x18002e6bc  nop     dword ptr [rax+rax+00h]
0x18002e6c1  test    eax, eax
0x18002e6c3  jnz     short loc_18002E701
0x18002e6c5  call    cs:__imp_GetLastError
0x18002e6cc  nop     dword ptr [rax+rax+00h]
0x18002e6d1  mov     ebx, eax
0x18002e6d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6da  cmp     rcx, r13
0x18002e6dd  jz      loc_18002EA41
0x18002e6e3  test    [rcx+1Ch], r15b
0x18002e6e7  jz      loc_18002EA41
0x18002e6ed  cmp     [rcx+19h], r15b
0x18002e6f1  jb      loc_18002EA41
0x18002e6f7  mov     edx, 17h
0x18002e6fc  jmp     loc_18002EA32
0x18002e701  lea     r9, [rbp+5D0h+Buffer]
0x18002e705  mov     edx, 208h; unsigned __int64
0x18002e70a  lea     r8, aSFxssvcExe; "%s\\FXSSVC.EXE"
0x18002e711  lea     rcx, [rbp+5D0h+tstrFilename]; unsigned __int16 *
0x18002e718  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e71d  test    eax, eax
0x18002e71f  jns     short loc_18002E757
0x18002e721  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e728  cmp     rcx, r13
0x18002e72b  jz      short loc_18002E74D
0x18002e72d  test    [rcx+1Ch], r15b
0x18002e731  jz      short loc_18002E74D
0x18002e733  cmp     [rcx+19h], r15b
0x18002e737  jb      short loc_18002E74D
0x18002e739  mov     rcx, [rcx+10h]
0x18002e73d  mov     edx, 18h
0x18002e742  mov     r9d, eax
0x18002e745  mov     r8, rdi
0x18002e748  call    WPP_SF_d
0x18002e74d  mov     eax, 10Bh
0x18002e752  jmp     loc_18002EA43
0x18002e757  lea     rdx, [rsp+6D0h+var_670]
0x18002e75c  mov     [rsp+6D0h+var_670], 14h
0x18002e764  lea     rcx, [rbp+5D0h+tstrFilename]; lptstrFilename
0x18002e76b  call    GetFileVersion
0x18002e770  mov     ebx, eax
0x18002e772  test    eax, 0FFFFFFFDh
0x18002e777  jz      short loc_18002E7A7
0x18002e779  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e780  cmp     rcx, r13
0x18002e783  jz      loc_18002EA41
0x18002e789  test    [rcx+1Ch], r15b
0x18002e78d  jz      loc_18002EA41
0x18002e793  cmp     [rcx+19h], r15b
0x18002e797  jb      loc_18002EA41
0x18002e79d  mov     edx, 19h
0x18002e7a2  jmp     loc_18002EA32
0x18002e7a7  mov     eax, 5
0x18002e7ac  cmp     ax, word ptr [rsp+6D0h+var_66C+4]
0x18002e7b1  jnz     short loc_18002E82A
0x18002e7b3  cmp     r15w, word ptr [rsp+6D0h+var_66C+6]
0x18002e7b9  jnz     short loc_18002E82A
0x18002e7bb  mov     eax, 6F0h
0x18002e7c0  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x18002e7c5  jz      short loc_18002E7D3
0x18002e7c7  mov     eax, 0A28h
0x18002e7cc  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x18002e7d1  jnz     short loc_18002E82A
0x18002e7d3  call    ?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ; CreateSvcStartEventWithGlobalNamedEvent(void)
0x18002e7d8  test    rax, rax
0x18002e7db  jnz     short loc_18002E819
0x18002e7dd  call    cs:__imp_GetLastError
0x18002e7e4  nop     dword ptr [rax+rax+00h]
0x18002e7e9  mov     ebx, eax
0x18002e7eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7f2  cmp     rcx, r13
0x18002e7f5  jz      loc_18002EA41
0x18002e7fb  test    [rcx+1Ch], r15b
0x18002e7ff  jz      loc_18002EA41
0x18002e805  cmp     [rcx+19h], r15b
0x18002e809  jb      loc_18002EA41
0x18002e80f  mov     edx, 1Ah
0x18002e814  jmp     loc_18002EA32
0x18002e819  mov     qword ptr [r14], 0
0x18002e820  mov     [rsi], rax
0x18002e823  xor     eax, eax
0x18002e825  jmp     loc_18002EA43
0x18002e82a  lea     rax, [rsp+6D0h+hKey]
0x18002e82f  mov     r9d, 111h; samDesired
0x18002e835  xor     r8d, r8d; ulOptions
0x18002e838  mov     [rsp+6D0h+phkResult], rax; phkResult
0x18002e83d  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Fax\\Client\\Servi"...
0x18002e844  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e84b  call    cs:__imp_RegOpenKeyExW
0x18002e852  nop     dword ptr [rax+rax+00h]
0x18002e857  mov     ebx, eax
0x18002e859  test    eax, eax
0x18002e85b  jz      short loc_18002E88B
0x18002e85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e864  cmp     rcx, r13
0x18002e867  jz      loc_18002EA41
0x18002e86d  test    [rcx+1Ch], r15b
0x18002e871  jz      loc_18002EA41
0x18002e877  cmp     [rcx+19h], r15b
0x18002e87b  jb      loc_18002EA41
0x18002e881  mov     edx, 1Bh
0x18002e886  jmp     loc_18002EA32
0x18002e88b  xor     r9d, r9d; lpName
0x18002e88e  xor     r8d, r8d; bInitialState
0x18002e891  xor     ecx, ecx; lpEventAttributes
0x18002e893  lea     ebx, [r9+1]
0x18002e897  mov     edx, ebx; bManualReset
0x18002e899  call    cs:__imp_CreateEventW
0x18002e8a0  nop     dword ptr [rax+rax+00h]
0x18002e8a5  mov     rdi, rax
0x18002e8a8  test    rax, rax
0x18002e8ab  jnz     short loc_18002E8E7
0x18002e8ad  call    cs:__imp_GetLastError
0x18002e8b4  nop     dword ptr [rax+rax+00h]
0x18002e8b9  mov     ebx, eax
0x18002e8bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8c2  cmp     rcx, r13
0x18002e8c5  jz      loc_18002E9F7
0x18002e8cb  test    [rcx+1Ch], r15b
0x18002e8cf  jz      loc_18002E9F7
0x18002e8d5  cmp     [rcx+19h], r15b
0x18002e8d9  jb      loc_18002E9F7
0x18002e8df  lea     edx, [rdi+1Ch]
0x18002e8e2  jmp     loc_18002E9E4
0x18002e8e7  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18002e8ec  xor     edx, edx; bWatchSubtree
0x18002e8ee  mov     r9, rdi; hEvent
0x18002e8f1  mov     dword ptr [rsp+6D0h+phkResult], ebx; unsigned int
0x18002e8f5  lea     r8d, [rdx+4]; dwNotifyFilter
0x18002e8f9  call    cs:__imp_RegNotifyChangeKeyValue
0x18002e900  nop     dword ptr [rax+rax+00h]
0x18002e905  mov     ebx, eax
0x18002e907  test    eax, eax
0x18002e909  jz      short loc_18002E969
0x18002e90b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e912  cmp     rcx, r13
0x18002e915  jz      short loc_18002E93B
0x18002e917  test    [rcx+1Ch], r15b
0x18002e91b  jz      short loc_18002E93B
0x18002e91d  cmp     [rcx+19h], r15b
0x18002e921  jb      short loc_18002E93B
0x18002e923  mov     rcx, [rcx+10h]
0x18002e927  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e92e  mov     edx, 1Dh
0x18002e933  mov     r9d, eax
0x18002e936  call    WPP_SF_d
0x18002e93b  mov     rcx, rdi; hObject
0x18002e93e  call    cs:__imp_CloseHandle
0x18002e945  nop     dword ptr [rax+rax+00h]
0x18002e94a  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18002e94f  test    rcx, rcx
0x18002e952  jz      loc_18002EA41
0x18002e958  call    cs:__imp_RegCloseKey
0x18002e95f  nop     dword ptr [rax+rax+00h]
0x18002e964  jmp     loc_18002EA41
0x18002e969  lea     rax, [rsp+6D0h+var_690]
0x18002e96e  mov     [rsp+6D0h+var_6A0], rax; unsigned int *
0x18002e973  lea     r9, [rsp+6D0h+var_680]; struct SC_HANDLE__ **
0x18002e978  lea     r8, [rsp+6D0h+hSCObject]; struct SC_HANDLE__ **
0x18002e97d  mov     [rsp+6D0h+dwDesiredAccess], 4; dwDesiredAccess
0x18002e985  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x18002e98a  mov     ebx, eax
0x18002e98c  test    eax, eax
0x18002e98e  jnz     short loc_18002E93B
0x18002e990  mov     rdx, [rsp+6D0h+var_680]; SC_HANDLE
0x18002e995  mov     rcx, [rsp+6D0h+hSCObject]; hSCObject
0x18002e99a  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x18002e99f  cmp     [rsp+6D0h+var_690], 4
0x18002e9a4  jnz     short loc_18002EA09
0x18002e9a6  mov     rcx, rdi; hEvent
0x18002e9a9  call    cs:__imp_SetEvent
0x18002e9b0  nop     dword ptr [rax+rax+00h]
0x18002e9b5  test    eax, eax
0x18002e9b7  jnz     short loc_18002EA09
0x18002e9b9  call    cs:__imp_GetLastError
0x18002e9c0  nop     dword ptr [rax+rax+00h]
0x18002e9c5  mov     ebx, eax
0x18002e9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9ce  cmp     rcx, r13
0x18002e9d1  jz      short loc_18002E9F7
0x18002e9d3  test    [rcx+1Ch], r15b
0x18002e9d7  jz      short loc_18002E9F7
0x18002e9d9  cmp     [rcx+19h], r15b
0x18002e9dd  jb      short loc_18002E9F7
0x18002e9df  mov     edx, 1Eh
0x18002e9e4  mov     rcx, [rcx+10h]
0x18002e9e8  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002e9ef  mov     r9d, eax
0x18002e9f2  call    WPP_SF_d
0x18002e9f7  test    ebx, ebx
0x18002e9f9  jz      short loc_18002EA09
0x18002e9fb  test    rdi, rdi
0x18002e9fe  jz      loc_18002E94A
0x18002ea04  jmp     loc_18002E93B
0x18002ea09  mov     rax, [rsp+6D0h+hKey]
0x18002ea0e  mov     [rsi], rdi
0x18002ea11  mov     [r14], rax
0x18002ea14  jmp     loc_18002E823
0x18002ea19  mov     ebx, 57h ; 'W'
0x18002ea1e  cmp     rcx, r13
0x18002ea21  jz      short loc_18002EA41
0x18002ea23  test    [rcx+1Ch], r15b
0x18002ea27  jz      short loc_18002EA41
0x18002ea29  cmp     [rcx+19h], r15b
0x18002ea2d  jb      short loc_18002EA41
0x18002ea2f  lea     edx, [rbx-41h]
0x18002ea32  mov     rcx, [rcx+10h]
0x18002ea36  mov     r9d, ebx
0x18002ea39  mov     r8, rdi
0x18002ea3c  call    WPP_SF_d
0x18002ea41  mov     eax, ebx
0x18002ea43  mov     rcx, [rbp+5D0h+var_30]
0x18002ea4a  xor     rcx, rsp; StackCookie
0x18002ea4d  call    __security_check_cookie
0x18002ea52  lea     r11, [rsp+6D0h+var_20]
0x18002ea5a  mov     rbx, [r11+40h]
0x18002ea5e  mov     rsi, [r11+48h]
0x18002ea62  mov     rsp, r11
0x18002ea65  pop     r15
0x18002ea67  pop     r14
0x18002ea69  pop     r13
0x18002ea6b  pop     rdi
0x18002ea6c  pop     rbp
0x18002ea6d  retn
```
