# UpdateBitLockerStatusReg(BITLOCKER_CSP_STATUS,ulong)

- ea: `0x18006f774`
- end: `0x18006fa58`
- name: `?UpdateBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@K@Z`
- size: `740`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004aaec`
- `0x18004d7f0`
- `0x18004e620`

## callees

- `0x1800016a4`
- `0x180001fe8`
- `0x180009f30`
- `0x180009f60`
- `0x18001c6c8`
- `0x180025ed4`
- `0x18002f28c`
- `0x18006e530`
- `0x18006f774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f829`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f829`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f996`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f996`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006f91e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006f91e`

## pseudocode

```c
__int64 __fastcall UpdateBitLockerStatusReg(unsigned int a1, int a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  int BitLockerCSPRegValueName; // eax
  LSTATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v12; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  __int64 v14; // [rsp+60h] [rbp-20h] BYREF
  PSRWLOCK v15[3]; // [rsp+68h] [rbp-18h] BYREF
  int Data; // [rsp+B8h] [rbp+38h] BYREF
  LPCWSTR lpValueName; // [rsp+C0h] [rbp+40h] BYREF
  int v18; // [rsp+C8h] [rbp+48h] BYREF

  Data = a2;
  hKey = 0;
  lpValueName = 0;
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v15,
    &g_hBitLockerCSPStateUpdateProvider,
    &g_bitLockerCSPStateUpdateProviderInitLock,
    &g_bitLockerCSPStateUpdateProviderRefCount);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\BitLockerCsp\\EncryptionFailure",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    BitLockerCSPRegValueName = GetBitLockerCSPRegValueName(a1, &lpValueName);
    v4 = BitLockerCSPRegValueName;
    if ( BitLockerCSPRegValueName >= 0 )
    {
      v8 = RegSetKeyValueW(hKey, 0, lpValueName, 4u, &Data, 4u);
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, a1, v4);
            v5 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
          {
            v6 = 87;
            goto LABEL_29;
          }
        }
      }
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
            a1,
            BitLockerCSPRegValueName);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
        {
          v6 = 85;
          goto LABEL_29;
        }
      }
    }
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, a1, v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
      {
        v6 = 83;
LABEL_29:
        WPP_SF_d(v5[2], v6, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, (unsigned int)v4);
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (unsigned int)dword_18009A4A0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A4A0, 0x400000000000LL) )
  {
    v18 = Data;
    v14 = 0x1000000;
    LODWORD(lpValueName) = v4;
    v12 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (int)&dword_18009A4A0,
      (int)&word_18008E47E,
      v9,
      v10,
      (__int64)&v12,
      (__int64)&v18,
      (__int64)&lpValueName,
      (__int64)&v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006f774  mov     [rsp-28h+Data], edx
0x18006f778  push    rbp
0x18006f779  push    rbx
0x18006f77a  push    rdi
0x18006f77b  push    r14
0x18006f77d  push    r15
0x18006f77f  mov     rbp, rsp
0x18006f782  sub     rsp, 80h
0x18006f789  mov     edi, ecx
0x18006f78b  mov     [rbp+hKey], 0
0x18006f793  lea     rcx, [rbp+var_18]; this
0x18006f797  mov     [rbp+lpValueName], 0
0x18006f79f  lea     r9, ?g_bitLockerCSPStateUpdateProviderRefCount@@3JC; volatile int *
0x18006f7a6  lea     r8, ?g_bitLockerCSPStateUpdateProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x18006f7ad  lea     rdx, g_hBitLockerCSPStateUpdateProvider; struct _tlgProvider_t **
0x18006f7b4  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x18006f7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7c0  lea     r14, WPP_GLOBAL_Control
0x18006f7c7  lea     r15, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006f7ce  cmp     rcx, r14
0x18006f7d1  jz      short loc_18006F7EA
0x18006f7d3  test    byte ptr [rcx+1Ch], 20h
0x18006f7d7  jz      short loc_18006F7EA
0x18006f7d9  mov     rcx, [rcx+10h]
0x18006f7dd  mov     edx, 51h ; 'Q'
0x18006f7e2  mov     r8, r15
0x18006f7e5  call    WPP_SF_
0x18006f7ea  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x18006f7f3  lea     rax, [rbp+hKey]
0x18006f7f7  mov     [rsp+80h+phkResult], rax; phkResult
0x18006f7fc  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\BitLockerCsp\\Encr"...
0x18006f803  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006f80c  xor     r9d, r9d; lpClass
0x18006f80f  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18006f817  xor     r8d, r8d; Reserved
0x18006f81a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f821  mov     [rsp+80h+dwOptions], 0; dwOptions
0x18006f829  call    cs:__imp_RegCreateKeyExW
0x18006f830  nop     dword ptr [rax+rax+00h]
0x18006f835  mov     ebx, eax
0x18006f837  test    eax, eax
0x18006f839  jle     short loc_18006F844
0x18006f83b  movzx   ebx, ax
0x18006f83e  or      ebx, 80070000h
0x18006f844  test    ebx, ebx
0x18006f846  jns     short loc_18006F89A
0x18006f848  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f84f  cmp     rcx, r14
0x18006f852  jz      loc_18006F98D
0x18006f858  test    byte ptr [rcx+1Ch], 2
0x18006f85c  jz      short loc_18006F87D
0x18006f85e  mov     rcx, [rcx+10h]
0x18006f862  mov     edx, 52h ; 'R'
0x18006f867  mov     r9d, edi
0x18006f86a  mov     [rsp+80h+dwOptions], ebx
0x18006f86e  mov     r8, r15
0x18006f871  call    WPP_SF_DD
0x18006f876  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f87d  cmp     rcx, r14
0x18006f880  jz      loc_18006F98D
0x18006f886  test    byte ptr [rcx+1Ch], 40h
0x18006f88a  jz      loc_18006F98D
0x18006f890  mov     edx, 53h ; 'S'
0x18006f895  jmp     loc_18006F97E
0x18006f89a  lea     rdx, [rbp+lpValueName]
0x18006f89e  mov     ecx, edi
0x18006f8a0  call    ?GetBitLockerCSPRegValueName@@YAJW4BITLOCKER_CSP_STATUS@@PEAPEBG@Z; GetBitLockerCSPRegValueName(BITLOCKER_CSP_STATUS,ushort const * *)
0x18006f8a5  mov     ebx, eax
0x18006f8a7  test    eax, eax
0x18006f8a9  jns     short loc_18006F8FD
0x18006f8ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f8b2  cmp     rcx, r14
0x18006f8b5  jz      loc_18006F98D
0x18006f8bb  test    byte ptr [rcx+1Ch], 2
0x18006f8bf  jz      short loc_18006F8E0
0x18006f8c1  mov     rcx, [rcx+10h]
0x18006f8c5  mov     edx, 54h ; 'T'
0x18006f8ca  mov     r9d, edi
0x18006f8cd  mov     [rsp+80h+dwOptions], eax
0x18006f8d1  mov     r8, r15
0x18006f8d4  call    WPP_SF_DD
0x18006f8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f8e0  cmp     rcx, r14
0x18006f8e3  jz      loc_18006F98D
0x18006f8e9  test    byte ptr [rcx+1Ch], 40h
0x18006f8ed  jz      loc_18006F98D
0x18006f8f3  mov     edx, 55h ; 'U'
0x18006f8f8  jmp     loc_18006F97E
0x18006f8fd  mov     r8, [rbp+lpValueName]; lpValueName
0x18006f901  lea     rax, [rbp+Data]
0x18006f905  mov     rcx, [rbp+hKey]; hKey
0x18006f909  mov     r9d, 4; dwType
0x18006f90f  mov     [rsp+80h+samDesired], 4; cbData
0x18006f917  xor     edx, edx; lpSubKey
0x18006f919  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18006f91e  call    cs:__imp_RegSetKeyValueW
0x18006f925  nop     dword ptr [rax+rax+00h]
0x18006f92a  mov     ebx, eax
0x18006f92c  test    eax, eax
0x18006f92e  jle     short loc_18006F939
0x18006f930  movzx   ebx, ax
0x18006f933  or      ebx, 80070000h
0x18006f939  test    ebx, ebx
0x18006f93b  jns     short loc_18006F98D
0x18006f93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f944  cmp     rcx, r14
0x18006f947  jz      short loc_18006F98D
0x18006f949  test    byte ptr [rcx+1Ch], 2
0x18006f94d  jz      short loc_18006F96E
0x18006f94f  mov     rcx, [rcx+10h]
0x18006f953  mov     edx, 56h ; 'V'
0x18006f958  mov     r9d, edi
0x18006f95b  mov     [rsp+80h+dwOptions], ebx
0x18006f95f  mov     r8, r15
0x18006f962  call    WPP_SF_DD
0x18006f967  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f96e  cmp     rcx, r14
0x18006f971  jz      short loc_18006F98D
0x18006f973  test    byte ptr [rcx+1Ch], 40h
0x18006f977  jz      short loc_18006F98D
0x18006f979  mov     edx, 57h ; 'W'
0x18006f97e  mov     rcx, [rcx+10h]
0x18006f982  mov     r9d, ebx
0x18006f985  mov     r8, r15
0x18006f988  call    WPP_SF_d
0x18006f98d  mov     rcx, [rbp+hKey]; hKey
0x18006f991  test    rcx, rcx
0x18006f994  jz      short loc_18006F9AA
0x18006f996  call    cs:__imp_RegCloseKey
0x18006f99d  nop     dword ptr [rax+rax+00h]
0x18006f9a2  mov     [rbp+hKey], 0
0x18006f9aa  mov     eax, cs:dword_18009A4A0
0x18006f9b0  cmp     eax, 4
0x18006f9b3  jbe     short loc_18006FA1A
0x18006f9b5  mov     rdx, 400000000000h
0x18006f9bf  lea     rcx, dword_18009A4A0
0x18006f9c6  call    _tlgKeywordOn
0x18006f9cb  test    al, al
0x18006f9cd  jz      short loc_18006FA1A
0x18006f9cf  mov     eax, [rbp+Data]
0x18006f9d2  lea     rdx, word_18008E47E
0x18006f9d9  mov     [rbp+arg_18], eax
0x18006f9dc  lea     rcx, dword_18009A4A0
0x18006f9e3  lea     rax, [rbp+var_20]
0x18006f9e7  mov     [rbp+var_20], 1000000h
0x18006f9ef  mov     [rsp+80h+phkResult], rax
0x18006f9f4  lea     rax, [rbp+lpValueName]
0x18006f9f8  mov     [rsp+80h+lpSecurityAttributes], rax
0x18006f9fd  lea     rax, [rbp+arg_18]
0x18006fa01  mov     qword ptr [rsp+80h+samDesired], rax
0x18006fa06  lea     rax, [rbp+var_30]
0x18006fa0a  mov     qword ptr [rsp+80h+dwOptions], rax
0x18006fa0f  mov     dword ptr [rbp+lpValueName], ebx
0x18006fa12  mov     [rbp+var_30], edi
0x18006fa15  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006fa1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa21  cmp     rcx, r14
0x18006fa24  jz      short loc_18006FA3D
0x18006fa26  test    byte ptr [rcx+1Ch], 20h
0x18006fa2a  jz      short loc_18006FA3D
0x18006fa2c  mov     rcx, [rcx+10h]
0x18006fa30  mov     edx, 58h ; 'X'
0x18006fa35  mov     r8, r15
0x18006fa38  call    WPP_SF_
0x18006fa3d  lea     rcx, [rbp+var_18]; this
0x18006fa41  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x18006fa46  mov     eax, ebx
0x18006fa48  add     rsp, 80h
0x18006fa4f  pop     r15
0x18006fa51  pop     r14
0x18006fa53  pop     rdi
0x18006fa54  pop     rbx
0x18006fa55  pop     rbp
0x18006fa56  retn
```
