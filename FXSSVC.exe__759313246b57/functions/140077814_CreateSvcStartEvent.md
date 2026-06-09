# CreateSvcStartEvent

- ea: `0x140077814`
- end: `0x140077cde`
- name: `CreateSvcStartEvent`
- size: `1226`
- prototype: `__int64 __fastcall(_QWORD *, HKEY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140078570`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140069f50`
- `0x14007566c`
- `0x140076c74`
- `0x140076e04`
- `0x140076f08`
- `0x140077814`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140077bc0`
- `ADVAPI32!RegCloseKey` at `0x140077bc0`
- `ADVAPI32!RegOpenKeyExW` at `0x140077ab3`
- `ADVAPI32!RegOpenKeyExW` at `0x140077ab3`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140077b61`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140077b61`
- `KERNEL32!GetSystemDirectoryW` at `0x14007791d`
- `KERNEL32!GetSystemDirectoryW` at `0x14007791d`
- `KERNEL32!GetLastError` at `0x14007792d`
- `KERNEL32!GetLastError` at `0x140077a45`
- `KERNEL32!GetLastError` at `0x140077b15`
- `KERNEL32!GetLastError` at `0x140077c28`
- `KERNEL32!GetLastError` at `0x14007792d`
- `KERNEL32!GetLastError` at `0x140077a45`
- `KERNEL32!GetLastError` at `0x140077b15`
- `KERNEL32!GetLastError` at `0x140077c28`
- `KERNEL32!CloseHandle` at `0x140077ba6`
- `KERNEL32!CloseHandle` at `0x140077ba6`
- `KERNEL32!SetEvent` at `0x140077c18`
- `KERNEL32!SetEvent` at `0x140077c18`
- `KERNEL32!CreateEventW` at `0x140077b01`
- `KERNEL32!CreateEventW` at `0x140077b01`
- `KERNEL32!GetVersion` at `0x1400778c5`
- `KERNEL32!GetVersion` at `0x1400778c5`

## string_xrefs

- `0x140077aa5`: `Software\Microsoft\Fax\Client\ServiceStartup`

## pseudocode

```c
__int64 __fastcall CreateSvcStartEvent(_QWORD *a1, HKEY *a2)
{
  CMapDeviceId *v4; // rcx
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  int v7; // eax
  void *SvcStartEventWithGlobalNamedEvent; // rax
  HANDLE EventW; // rax
  void *v11; // rdi
  DWORD v12; // eax
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rcx
  HKEY v17; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  SC_HANDLE v21; // [rsp+50h] [rbp-B0h] BYREF
  SC_HANDLE hSCObject; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  __int128 v24; // [rsp+64h] [rbp-9Ch]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR tstrFilename[520]; // [rsp+290h] [rbp+190h] BYREF

  hKey = 0;
  hSCObject = 0;
  v21 = 0;
  v19 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_db036311db36307996a98c23702218b2_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 )
  {
    LastError = 87;
    if ( v4 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 2) == 0 || *((_BYTE *)v4 + 25) < 2u )
      return LastError;
    v6 = 22;
    goto LABEL_69;
  }
  if ( (unsigned __int8)GetVersion() < 5u || (unsigned int)IsServerSku() )
    goto LABEL_35;
  v24 = 0;
  memset_0(Buffer, 0, 0x20Au);
  memset_0(tstrFilename, 0, sizeof(tstrFilename));
  if ( !GetSystemDirectoryW(Buffer, 0x105u) )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
    v23 = 20;
    LastError = GetFileVersion(tstrFilename);
    if ( (LastError & 0xFFFFFFFD) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return LastError;
      }
      v6 = 25;
      goto LABEL_69;
    }
    if ( DWORD1(v24) == 131077 && (WORD4(v24) == 1776 || WORD4(v24) == 2600) )
    {
      SvcStartEventWithGlobalNamedEvent = CreateSvcStartEventWithGlobalNamedEvent();
      if ( !SvcStartEventWithGlobalNamedEvent )
      {
        LastError = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_db036311db36307996a98c23702218b2_Traceguids, v15);
        }
        goto LABEL_50;
      }
      LastError = FaxOpenService(v16, L"Fax", &hSCObject, &v21, phkResult, 4u, &v19);
      if ( LastError )
      {
LABEL_50:
        CloseHandle(v11);
        goto LABEL_51;
      }
      FaxCloseService(hSCObject, v21);
      if ( v19 != 4 || SetEvent(v11) )
      {
LABEL_64:
        v17 = hKey;
        *a1 = v11;
        *a2 = v17;
        return 0;
      }
      v12 = GetLastError();
      LastError = v12;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 28;
LABEL_60:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_db036311db36307996a98c23702218b2_Traceguids, v12);
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
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
0x140077814  mov     [rsp-8+arg_10], rbx
0x140077819  mov     [rsp-8+arg_18], rsi
0x14007781e  push    rbp
0x14007781f  push    rdi
0x140077820  push    r13
0x140077822  push    r14
0x140077824  push    r15
0x140077826  lea     rbp, [rsp-5B0h]
0x14007782e  sub     rsp, 6B0h
0x140077835  mov     rax, cs:__security_cookie
0x14007783c  xor     rax, rsp
0x14007783f  mov     [rbp+5D0h+var_30], rax
0x140077846  mov     r14, rdx
0x140077849  mov     [rsp+6D0h+hKey], 0
0x140077852  mov     rsi, rcx
0x140077855  mov     [rsp+6D0h+hSCObject], 0
0x14007785e  mov     [rsp+6D0h+var_680], 0
0x140077867  mov     [rsp+6D0h+var_690], 0
0x14007786f  mov     rcx, cs:WPP_GLOBAL_Control
0x140077876  lea     r13, WPP_GLOBAL_Control
0x14007787d  lea     rdi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077884  mov     ebx, 5
0x140077889  lea     r15d, [rbx-3]
0x14007788d  cmp     rcx, r13
0x140077890  jz      short loc_1400778B3
0x140077892  test    [rcx+1Ch], r15b
0x140077896  jz      short loc_1400778B3
0x140077898  cmp     [rcx+19h], bl
0x14007789b  jb      short loc_1400778B3
0x14007789d  mov     rcx, [rcx+10h]
0x1400778a1  lea     edx, [rbx+10h]
0x1400778a4  mov     r8, rdi
0x1400778a7  call    WPP_SF_
0x1400778ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400778b3  test    rsi, rsi
0x1400778b6  jz      loc_140077C88
0x1400778bc  test    r14, r14
0x1400778bf  jz      loc_140077C88
0x1400778c5  call    cs:__imp_GetVersion
0x1400778cc  nop     dword ptr [rax+rax+00h]
0x1400778d1  cmp     al, bl
0x1400778d3  jb      loc_140077A92
0x1400778d9  call    IsServerSku
0x1400778de  test    eax, eax
0x1400778e0  jnz     loc_140077A92
0x1400778e6  xorps   xmm0, xmm0
0x1400778e9  lea     rcx, [rbp+5D0h+Buffer]; void *
0x1400778ed  xor     edx, edx; Val
0x1400778ef  mov     r8d, 20Ah; Size
0x1400778f5  movdqu  [rsp+6D0h+var_66C], xmm0
0x1400778fb  call    memset_0
0x140077900  xor     edx, edx; Val
0x140077902  lea     rcx, [rbp+5D0h+tstrFilename]; void *
0x140077909  mov     r8d, 410h; Size
0x14007790f  call    memset_0
0x140077914  mov     edx, 105h; uSize
0x140077919  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x14007791d  call    cs:__imp_GetSystemDirectoryW
0x140077924  nop     dword ptr [rax+rax+00h]
0x140077929  test    eax, eax
0x14007792b  jnz     short loc_140077969
0x14007792d  call    cs:__imp_GetLastError
0x140077934  nop     dword ptr [rax+rax+00h]
0x140077939  mov     ebx, eax
0x14007793b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077942  cmp     rcx, r13
0x140077945  jz      loc_140077CB0
0x14007794b  test    [rcx+1Ch], r15b
0x14007794f  jz      loc_140077CB0
0x140077955  cmp     [rcx+19h], r15b
0x140077959  jb      loc_140077CB0
0x14007795f  mov     edx, 17h
0x140077964  jmp     loc_140077CA1
0x140077969  lea     r9, [rbp+5D0h+Buffer]
0x14007796d  mov     edx, 208h; unsigned __int64
0x140077972  lea     r8, aSFxssvcExe; "%s\\FXSSVC.EXE"
0x140077979  lea     rcx, [rbp+5D0h+tstrFilename]; unsigned __int16 *
0x140077980  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140077985  test    eax, eax
0x140077987  jns     short loc_1400779BF
0x140077989  mov     rcx, cs:WPP_GLOBAL_Control
0x140077990  cmp     rcx, r13
0x140077993  jz      short loc_1400779B5
0x140077995  test    [rcx+1Ch], r15b
0x140077999  jz      short loc_1400779B5
0x14007799b  cmp     [rcx+19h], r15b
0x14007799f  jb      short loc_1400779B5
0x1400779a1  mov     rcx, [rcx+10h]
0x1400779a5  mov     edx, 18h
0x1400779aa  mov     r9d, eax
0x1400779ad  mov     r8, rdi
0x1400779b0  call    WPP_SF_d
0x1400779b5  mov     eax, 10Bh
0x1400779ba  jmp     loc_140077CB2
0x1400779bf  lea     rdx, [rsp+6D0h+var_670]
0x1400779c4  mov     [rsp+6D0h+var_670], 14h
0x1400779cc  lea     rcx, [rbp+5D0h+tstrFilename]; lptstrFilename
0x1400779d3  call    GetFileVersion
0x1400779d8  mov     ebx, eax
0x1400779da  test    eax, 0FFFFFFFDh
0x1400779df  jz      short loc_140077A0F
0x1400779e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400779e8  cmp     rcx, r13
0x1400779eb  jz      loc_140077CB0
0x1400779f1  test    [rcx+1Ch], r15b
0x1400779f5  jz      loc_140077CB0
0x1400779fb  cmp     [rcx+19h], r15b
0x1400779ff  jb      loc_140077CB0
0x140077a05  mov     edx, 19h
0x140077a0a  jmp     loc_140077CA1
0x140077a0f  mov     eax, 5
0x140077a14  cmp     ax, word ptr [rsp+6D0h+var_66C+4]
0x140077a19  jnz     short loc_140077A92
0x140077a1b  cmp     r15w, word ptr [rsp+6D0h+var_66C+6]
0x140077a21  jnz     short loc_140077A92
0x140077a23  mov     eax, 6F0h
0x140077a28  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x140077a2d  jz      short loc_140077A3B
0x140077a2f  mov     eax, 0A28h
0x140077a34  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x140077a39  jnz     short loc_140077A92
0x140077a3b  call    ?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ; CreateSvcStartEventWithGlobalNamedEvent(void)
0x140077a40  test    rax, rax
0x140077a43  jnz     short loc_140077A81
0x140077a45  call    cs:__imp_GetLastError
0x140077a4c  nop     dword ptr [rax+rax+00h]
0x140077a51  mov     ebx, eax
0x140077a53  mov     rcx, cs:WPP_GLOBAL_Control
0x140077a5a  cmp     rcx, r13
0x140077a5d  jz      loc_140077CB0
0x140077a63  test    [rcx+1Ch], r15b
0x140077a67  jz      loc_140077CB0
0x140077a6d  cmp     [rcx+19h], r15b
0x140077a71  jb      loc_140077CB0
0x140077a77  mov     edx, 1Ah
0x140077a7c  jmp     loc_140077CA1
0x140077a81  mov     qword ptr [r14], 0
0x140077a88  mov     [rsi], rax
0x140077a8b  xor     eax, eax
0x140077a8d  jmp     loc_140077CB2
0x140077a92  lea     rax, [rsp+6D0h+hKey]
0x140077a97  mov     r9d, 111h; samDesired
0x140077a9d  xor     r8d, r8d; ulOptions
0x140077aa0  mov     [rsp+6D0h+phkResult], rax; phkResult
0x140077aa5  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Fax\\Client\\Servi"...
0x140077aac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140077ab3  call    cs:__imp_RegOpenKeyExW
0x140077aba  nop     dword ptr [rax+rax+00h]
0x140077abf  mov     ebx, eax
0x140077ac1  test    eax, eax
0x140077ac3  jz      short loc_140077AF3
0x140077ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140077acc  cmp     rcx, r13
0x140077acf  jz      loc_140077CB0
0x140077ad5  test    [rcx+1Ch], r15b
0x140077ad9  jz      loc_140077CB0
0x140077adf  cmp     [rcx+19h], r15b
0x140077ae3  jb      loc_140077CB0
0x140077ae9  mov     edx, 1Bh
0x140077aee  jmp     loc_140077CA1
0x140077af3  xor     r9d, r9d; lpName
0x140077af6  xor     r8d, r8d; bInitialState
0x140077af9  xor     ecx, ecx; lpEventAttributes
0x140077afb  lea     ebx, [r9+1]
0x140077aff  mov     edx, ebx; bManualReset
0x140077b01  call    cs:__imp_CreateEventW
0x140077b08  nop     dword ptr [rax+rax+00h]
0x140077b0d  mov     rdi, rax
0x140077b10  test    rax, rax
0x140077b13  jnz     short loc_140077B4F
0x140077b15  call    cs:__imp_GetLastError
0x140077b1c  nop     dword ptr [rax+rax+00h]
0x140077b21  mov     ebx, eax
0x140077b23  mov     rcx, cs:WPP_GLOBAL_Control
0x140077b2a  cmp     rcx, r13
0x140077b2d  jz      loc_140077C66
0x140077b33  test    [rcx+1Ch], r15b
0x140077b37  jz      loc_140077C66
0x140077b3d  cmp     [rcx+19h], r15b
0x140077b41  jb      loc_140077C66
0x140077b47  lea     edx, [rdi+1Ch]
0x140077b4a  jmp     loc_140077C53
0x140077b4f  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140077b54  xor     edx, edx; bWatchSubtree
0x140077b56  mov     r9, rdi; hEvent
0x140077b59  mov     dword ptr [rsp+6D0h+phkResult], ebx; unsigned int
0x140077b5d  lea     r8d, [rdx+4]; dwNotifyFilter
0x140077b61  call    cs:__imp_RegNotifyChangeKeyValue
0x140077b68  nop     dword ptr [rax+rax+00h]
0x140077b6d  mov     ebx, eax
0x140077b6f  test    eax, eax
0x140077b71  jz      short loc_140077BD1
0x140077b73  mov     rcx, cs:WPP_GLOBAL_Control
0x140077b7a  cmp     rcx, r13
0x140077b7d  jz      short loc_140077BA3
0x140077b7f  test    [rcx+1Ch], r15b
0x140077b83  jz      short loc_140077BA3
0x140077b85  cmp     [rcx+19h], r15b
0x140077b89  jb      short loc_140077BA3
0x140077b8b  mov     rcx, [rcx+10h]
0x140077b8f  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077b96  mov     edx, 1Dh
0x140077b9b  mov     r9d, eax
0x140077b9e  call    WPP_SF_d
0x140077ba3  mov     rcx, rdi; hObject
0x140077ba6  call    cs:__imp_CloseHandle
0x140077bad  nop     dword ptr [rax+rax+00h]
0x140077bb2  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140077bb7  test    rcx, rcx
0x140077bba  jz      loc_140077CB0
0x140077bc0  call    cs:__imp_RegCloseKey
0x140077bc7  nop     dword ptr [rax+rax+00h]
0x140077bcc  jmp     loc_140077CB0
0x140077bd1  lea     rax, [rsp+6D0h+var_690]
0x140077bd6  mov     [rsp+6D0h+var_6A0], rax; unsigned int *
0x140077bdb  lea     r9, [rsp+6D0h+var_680]; struct SC_HANDLE__ **
0x140077be0  lea     r8, [rsp+6D0h+hSCObject]; struct SC_HANDLE__ **
0x140077be5  mov     [rsp+6D0h+var_6A8], 4; unsigned int
0x140077bed  lea     rdx, SubsystemName; "Fax"
0x140077bf4  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x140077bf9  mov     ebx, eax
0x140077bfb  test    eax, eax
0x140077bfd  jnz     short loc_140077BA3
0x140077bff  mov     rdx, [rsp+6D0h+var_680]; SC_HANDLE
0x140077c04  mov     rcx, [rsp+6D0h+hSCObject]; hSCObject
0x140077c09  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x140077c0e  cmp     [rsp+6D0h+var_690], 4
0x140077c13  jnz     short loc_140077C78
0x140077c15  mov     rcx, rdi; hEvent
0x140077c18  call    cs:__imp_SetEvent
0x140077c1f  nop     dword ptr [rax+rax+00h]
0x140077c24  test    eax, eax
0x140077c26  jnz     short loc_140077C78
0x140077c28  call    cs:__imp_GetLastError
0x140077c2f  nop     dword ptr [rax+rax+00h]
0x140077c34  mov     ebx, eax
0x140077c36  mov     rcx, cs:WPP_GLOBAL_Control
0x140077c3d  cmp     rcx, r13
0x140077c40  jz      short loc_140077C66
0x140077c42  test    [rcx+1Ch], r15b
0x140077c46  jz      short loc_140077C66
0x140077c48  cmp     [rcx+19h], r15b
0x140077c4c  jb      short loc_140077C66
0x140077c4e  mov     edx, 1Eh
0x140077c53  mov     rcx, [rcx+10h]
0x140077c57  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077c5e  mov     r9d, eax
0x140077c61  call    WPP_SF_d
0x140077c66  test    ebx, ebx
0x140077c68  jz      short loc_140077C78
0x140077c6a  test    rdi, rdi
0x140077c6d  jz      loc_140077BB2
0x140077c73  jmp     loc_140077BA3
0x140077c78  mov     rax, [rsp+6D0h+hKey]
0x140077c7d  mov     [rsi], rdi
0x140077c80  mov     [r14], rax
0x140077c83  jmp     loc_140077A8B
0x140077c88  mov     ebx, 57h ; 'W'
0x140077c8d  cmp     rcx, r13
0x140077c90  jz      short loc_140077CB0
0x140077c92  test    [rcx+1Ch], r15b
0x140077c96  jz      short loc_140077CB0
0x140077c98  cmp     [rcx+19h], r15b
0x140077c9c  jb      short loc_140077CB0
0x140077c9e  lea     edx, [rbx-41h]
0x140077ca1  mov     rcx, [rcx+10h]
0x140077ca5  mov     r9d, ebx
0x140077ca8  mov     r8, rdi
0x140077cab  call    WPP_SF_d
0x140077cb0  mov     eax, ebx
0x140077cb2  mov     rcx, [rbp+5D0h+var_30]
0x140077cb9  xor     rcx, rsp; StackCookie
0x140077cbc  call    __security_check_cookie
0x140077cc1  lea     r11, [rsp+6D0h+var_20]
0x140077cc9  mov     rbx, [r11+40h]
0x140077ccd  mov     rsi, [r11+48h]
0x140077cd1  mov     rsp, r11
0x140077cd4  pop     r15
0x140077cd6  pop     r14
0x140077cd8  pop     r13
0x140077cda  pop     rdi
0x140077cdb  pop     rbp
0x140077cdc  retn
```
