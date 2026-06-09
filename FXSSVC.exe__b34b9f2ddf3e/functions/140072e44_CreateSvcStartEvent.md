# CreateSvcStartEvent

- ea: `0x140072e44`
- end: `0x1400732c5`
- name: `CreateSvcStartEvent`
- size: `1153`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140073aa0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140066334`
- `0x140070f1c`
- `0x1400723b4`
- `0x140072518`
- `0x140072604`
- `0x140072e44`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400731ba`
- `ADVAPI32!RegCloseKey` at `0x1400731ba`
- `ADVAPI32!RegOpenKeyExW` at `0x1400730cb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400730cb`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140073167`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140073167`
- `KERNEL32!GetSystemDirectoryW` at `0x140072f47`
- `KERNEL32!GetSystemDirectoryW` at `0x140072f47`
- `KERNEL32!GetLastError` at `0x140072f51`
- `KERNEL32!GetLastError` at `0x140073063`
- `KERNEL32!GetLastError` at `0x140073121`
- `KERNEL32!GetLastError` at `0x140073216`
- `KERNEL32!GetLastError` at `0x140072f51`
- `KERNEL32!GetLastError` at `0x140073063`
- `KERNEL32!GetLastError` at `0x140073121`
- `KERNEL32!GetLastError` at `0x140073216`
- `KERNEL32!CloseHandle` at `0x1400731a6`
- `KERNEL32!CloseHandle` at `0x1400731a6`
- `KERNEL32!SetEvent` at `0x14007320c`
- `KERNEL32!SetEvent` at `0x14007320c`
- `KERNEL32!CreateEventW` at `0x140073113`
- `KERNEL32!CreateEventW` at `0x140073113`
- `KERNEL32!GetVersion` at `0x140072ef5`
- `KERNEL32!GetVersion` at `0x140072ef5`

## string_xrefs

- `0x1400730bd`: `Software\Microsoft\Fax\Client\ServiceStartup`

## pseudocode

```c
__int64 __fastcall CreateSvcStartEvent(_QWORD *a1, HKEY *a2)
{
  CMapDeviceId *v4; // rcx
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  int v7; // eax
  HANDLE SvcStartEventWithGlobalNamedEvent; // rax
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
0x140072e44  mov     [rsp-8+arg_10], rbx
0x140072e49  mov     [rsp-8+arg_18], rsi
0x140072e4e  push    rbp
0x140072e4f  push    rdi
0x140072e50  push    r13
0x140072e52  push    r14
0x140072e54  push    r15
0x140072e56  lea     rbp, [rsp-5B0h]
0x140072e5e  sub     rsp, 6B0h
0x140072e65  mov     rax, cs:__security_cookie
0x140072e6c  xor     rax, rsp
0x140072e6f  mov     [rbp+5D0h+var_30], rax
0x140072e76  mov     r14, rdx
0x140072e79  mov     [rsp+6D0h+hKey], 0
0x140072e82  mov     rsi, rcx
0x140072e85  mov     [rsp+6D0h+hSCObject], 0
0x140072e8e  mov     [rsp+6D0h+var_680], 0
0x140072e97  mov     [rsp+6D0h+var_690], 0
0x140072e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ea6  lea     r13, WPP_GLOBAL_Control
0x140072ead  lea     rdi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072eb4  mov     ebx, 5
0x140072eb9  lea     r15d, [rbx-3]
0x140072ebd  cmp     rcx, r13
0x140072ec0  jz      short loc_140072EE3
0x140072ec2  test    [rcx+1Ch], r15b
0x140072ec6  jz      short loc_140072EE3
0x140072ec8  cmp     [rcx+19h], bl
0x140072ecb  jb      short loc_140072EE3
0x140072ecd  mov     rcx, [rcx+10h]
0x140072ed1  lea     edx, [rbx+10h]
0x140072ed4  mov     r8, rdi
0x140072ed7  call    WPP_SF_
0x140072edc  mov     rcx, cs:WPP_GLOBAL_Control
0x140072ee3  test    rsi, rsi
0x140072ee6  jz      loc_140073270
0x140072eec  test    r14, r14
0x140072eef  jz      loc_140073270
0x140072ef5  call    cs:__imp_GetVersion
0x140072efb  cmp     al, bl
0x140072efd  jb      loc_1400730AA
0x140072f03  call    IsServerSku
0x140072f08  test    eax, eax
0x140072f0a  jnz     loc_1400730AA
0x140072f10  xorps   xmm0, xmm0
0x140072f13  lea     rcx, [rbp+5D0h+Buffer]; void *
0x140072f17  xor     edx, edx; Val
0x140072f19  mov     r8d, 20Ah; Size
0x140072f1f  movdqu  [rsp+6D0h+var_66C], xmm0
0x140072f25  call    memset_0
0x140072f2a  xor     edx, edx; Val
0x140072f2c  lea     rcx, [rbp+5D0h+tstrFilename]; void *
0x140072f33  mov     r8d, 410h; Size
0x140072f39  call    memset_0
0x140072f3e  mov     edx, 105h; uSize
0x140072f43  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x140072f47  call    cs:__imp_GetSystemDirectoryW
0x140072f4d  test    eax, eax
0x140072f4f  jnz     short loc_140072F87
0x140072f51  call    cs:__imp_GetLastError
0x140072f57  mov     ebx, eax
0x140072f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140072f60  cmp     rcx, r13
0x140072f63  jz      loc_140073298
0x140072f69  test    [rcx+1Ch], r15b
0x140072f6d  jz      loc_140073298
0x140072f73  cmp     [rcx+19h], r15b
0x140072f77  jb      loc_140073298
0x140072f7d  mov     edx, 17h
0x140072f82  jmp     loc_140073289
0x140072f87  lea     r9, [rbp+5D0h+Buffer]
0x140072f8b  mov     edx, 208h; unsigned __int64
0x140072f90  lea     r8, aSFxssvcExe; "%s\\FXSSVC.EXE"
0x140072f97  lea     rcx, [rbp+5D0h+tstrFilename]; unsigned __int16 *
0x140072f9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140072fa3  test    eax, eax
0x140072fa5  jns     short loc_140072FDD
0x140072fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140072fae  cmp     rcx, r13
0x140072fb1  jz      short loc_140072FD3
0x140072fb3  test    [rcx+1Ch], r15b
0x140072fb7  jz      short loc_140072FD3
0x140072fb9  cmp     [rcx+19h], r15b
0x140072fbd  jb      short loc_140072FD3
0x140072fbf  mov     rcx, [rcx+10h]
0x140072fc3  mov     edx, 18h
0x140072fc8  mov     r9d, eax
0x140072fcb  mov     r8, rdi
0x140072fce  call    WPP_SF_d
0x140072fd3  mov     eax, 10Bh
0x140072fd8  jmp     loc_14007329A
0x140072fdd  lea     rdx, [rsp+6D0h+var_670]
0x140072fe2  mov     [rsp+6D0h+var_670], 14h
0x140072fea  lea     rcx, [rbp+5D0h+tstrFilename]; lptstrFilename
0x140072ff1  call    GetFileVersion
0x140072ff6  mov     ebx, eax
0x140072ff8  test    eax, 0FFFFFFFDh
0x140072ffd  jz      short loc_14007302D
0x140072fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140073006  cmp     rcx, r13
0x140073009  jz      loc_140073298
0x14007300f  test    [rcx+1Ch], r15b
0x140073013  jz      loc_140073298
0x140073019  cmp     [rcx+19h], r15b
0x14007301d  jb      loc_140073298
0x140073023  mov     edx, 19h
0x140073028  jmp     loc_140073289
0x14007302d  mov     eax, 5
0x140073032  cmp     ax, word ptr [rsp+6D0h+var_66C+4]
0x140073037  jnz     short loc_1400730AA
0x140073039  cmp     r15w, word ptr [rsp+6D0h+var_66C+6]
0x14007303f  jnz     short loc_1400730AA
0x140073041  mov     eax, 6F0h
0x140073046  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x14007304b  jz      short loc_140073059
0x14007304d  mov     eax, 0A28h
0x140073052  cmp     ax, word ptr [rsp+6D0h+var_66C+8]
0x140073057  jnz     short loc_1400730AA
0x140073059  call    ?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ; CreateSvcStartEventWithGlobalNamedEvent(void)
0x14007305e  test    rax, rax
0x140073061  jnz     short loc_140073099
0x140073063  call    cs:__imp_GetLastError
0x140073069  mov     ebx, eax
0x14007306b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073072  cmp     rcx, r13
0x140073075  jz      loc_140073298
0x14007307b  test    [rcx+1Ch], r15b
0x14007307f  jz      loc_140073298
0x140073085  cmp     [rcx+19h], r15b
0x140073089  jb      loc_140073298
0x14007308f  mov     edx, 1Ah
0x140073094  jmp     loc_140073289
0x140073099  mov     qword ptr [r14], 0
0x1400730a0  mov     [rsi], rax
0x1400730a3  xor     eax, eax
0x1400730a5  jmp     loc_14007329A
0x1400730aa  lea     rax, [rsp+6D0h+hKey]
0x1400730af  mov     r9d, 111h; samDesired
0x1400730b5  xor     r8d, r8d; ulOptions
0x1400730b8  mov     [rsp+6D0h+phkResult], rax; phkResult
0x1400730bd  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Fax\\Client\\Servi"...
0x1400730c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400730cb  call    cs:__imp_RegOpenKeyExW
0x1400730d1  mov     ebx, eax
0x1400730d3  test    eax, eax
0x1400730d5  jz      short loc_140073105
0x1400730d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400730de  cmp     rcx, r13
0x1400730e1  jz      loc_140073298
0x1400730e7  test    [rcx+1Ch], r15b
0x1400730eb  jz      loc_140073298
0x1400730f1  cmp     [rcx+19h], r15b
0x1400730f5  jb      loc_140073298
0x1400730fb  mov     edx, 1Bh
0x140073100  jmp     loc_140073289
0x140073105  xor     r9d, r9d; lpName
0x140073108  xor     r8d, r8d; bInitialState
0x14007310b  xor     ecx, ecx; lpEventAttributes
0x14007310d  lea     ebx, [r9+1]
0x140073111  mov     edx, ebx; bManualReset
0x140073113  call    cs:__imp_CreateEventW
0x140073119  mov     rdi, rax
0x14007311c  test    rax, rax
0x14007311f  jnz     short loc_140073155
0x140073121  call    cs:__imp_GetLastError
0x140073127  mov     ebx, eax
0x140073129  mov     rcx, cs:WPP_GLOBAL_Control
0x140073130  cmp     rcx, r13
0x140073133  jz      loc_14007324E
0x140073139  test    [rcx+1Ch], r15b
0x14007313d  jz      loc_14007324E
0x140073143  cmp     [rcx+19h], r15b
0x140073147  jb      loc_14007324E
0x14007314d  lea     edx, [rdi+1Ch]
0x140073150  jmp     loc_14007323B
0x140073155  mov     rcx, [rsp+6D0h+hKey]; hKey
0x14007315a  xor     edx, edx; bWatchSubtree
0x14007315c  mov     r9, rdi; hEvent
0x14007315f  mov     dword ptr [rsp+6D0h+phkResult], ebx; unsigned int
0x140073163  lea     r8d, [rdx+4]; dwNotifyFilter
0x140073167  call    cs:__imp_RegNotifyChangeKeyValue
0x14007316d  mov     ebx, eax
0x14007316f  test    eax, eax
0x140073171  jz      short loc_1400731C5
0x140073173  mov     rcx, cs:WPP_GLOBAL_Control
0x14007317a  cmp     rcx, r13
0x14007317d  jz      short loc_1400731A3
0x14007317f  test    [rcx+1Ch], r15b
0x140073183  jz      short loc_1400731A3
0x140073185  cmp     [rcx+19h], r15b
0x140073189  jb      short loc_1400731A3
0x14007318b  mov     rcx, [rcx+10h]
0x14007318f  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073196  mov     edx, 1Dh
0x14007319b  mov     r9d, eax
0x14007319e  call    WPP_SF_d
0x1400731a3  mov     rcx, rdi; hObject
0x1400731a6  call    cs:__imp_CloseHandle
0x1400731ac  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1400731b1  test    rcx, rcx
0x1400731b4  jz      loc_140073298
0x1400731ba  call    cs:__imp_RegCloseKey
0x1400731c0  jmp     loc_140073298
0x1400731c5  lea     rax, [rsp+6D0h+var_690]
0x1400731ca  mov     [rsp+6D0h+var_6A0], rax; unsigned int *
0x1400731cf  lea     r9, [rsp+6D0h+var_680]; struct SC_HANDLE__ **
0x1400731d4  lea     r8, [rsp+6D0h+hSCObject]; struct SC_HANDLE__ **
0x1400731d9  mov     [rsp+6D0h+var_6A8], 4; unsigned int
0x1400731e1  lea     rdx, SubsystemName; "Fax"
0x1400731e8  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x1400731ed  mov     ebx, eax
0x1400731ef  test    eax, eax
0x1400731f1  jnz     short loc_1400731A3
0x1400731f3  mov     rdx, [rsp+6D0h+var_680]; SC_HANDLE
0x1400731f8  mov     rcx, [rsp+6D0h+hSCObject]; hSCObject
0x1400731fd  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x140073202  cmp     [rsp+6D0h+var_690], 4
0x140073207  jnz     short loc_140073260
0x140073209  mov     rcx, rdi; hEvent
0x14007320c  call    cs:__imp_SetEvent
0x140073212  test    eax, eax
0x140073214  jnz     short loc_140073260
0x140073216  call    cs:__imp_GetLastError
0x14007321c  mov     ebx, eax
0x14007321e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073225  cmp     rcx, r13
0x140073228  jz      short loc_14007324E
0x14007322a  test    [rcx+1Ch], r15b
0x14007322e  jz      short loc_14007324E
0x140073230  cmp     [rcx+19h], r15b
0x140073234  jb      short loc_14007324E
0x140073236  mov     edx, 1Eh
0x14007323b  mov     rcx, [rcx+10h]
0x14007323f  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073246  mov     r9d, eax
0x140073249  call    WPP_SF_d
0x14007324e  test    ebx, ebx
0x140073250  jz      short loc_140073260
0x140073252  test    rdi, rdi
0x140073255  jz      loc_1400731AC
0x14007325b  jmp     loc_1400731A3
0x140073260  mov     rax, [rsp+6D0h+hKey]
0x140073265  mov     [rsi], rdi
0x140073268  mov     [r14], rax
0x14007326b  jmp     loc_1400730A3
0x140073270  mov     ebx, 57h ; 'W'
0x140073275  cmp     rcx, r13
0x140073278  jz      short loc_140073298
0x14007327a  test    [rcx+1Ch], r15b
0x14007327e  jz      short loc_140073298
0x140073280  cmp     [rcx+19h], r15b
0x140073284  jb      short loc_140073298
0x140073286  lea     edx, [rbx-41h]
0x140073289  mov     rcx, [rcx+10h]
0x14007328d  mov     r9d, ebx
0x140073290  mov     r8, rdi
0x140073293  call    WPP_SF_d
0x140073298  mov     eax, ebx
0x14007329a  mov     rcx, [rbp+5D0h+var_30]
0x1400732a1  xor     rcx, rsp; StackCookie
0x1400732a4  call    __security_check_cookie
0x1400732a9  lea     r11, [rsp+6D0h+var_20]
0x1400732b1  mov     rbx, [r11+40h]
0x1400732b5  mov     rsi, [r11+48h]
0x1400732b9  mov     rsp, r11
0x1400732bc  pop     r15
0x1400732be  pop     r14
0x1400732c0  pop     r13
0x1400732c2  pop     rdi
0x1400732c3  pop     rbp
0x1400732c4  retn
```
