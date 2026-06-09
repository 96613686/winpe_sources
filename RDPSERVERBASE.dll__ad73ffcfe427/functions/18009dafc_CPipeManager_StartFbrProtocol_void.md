# CPipeManager::StartFbrProtocol(void)

- ea: `0x18009dafc`
- end: `0x18009df29`
- name: `?StartFbrProtocol@CPipeManager@@IEAAJXZ`
- size: `1069`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099ee0`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180079724`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f354`
- `0x18009dafc`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009dd27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009dd27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dc87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dc87`

## string_xrefs

- `0x18009de75`: `Failed to create FBR protocol`
- `0x18009db9e`: `spProtocol == NULL`
- `0x18009dbb9`: `StartFbrProtocol`
- `0x18009de90`: `StartFbrProtocol`
- `0x18009dc4c`: `IRdpPipeProtocol::GetClientUniqueId failed.`
- `0x18009de27`: `Capability: CPipeManager::StartFbrProtocol - Client and server are the same machine - opening the FBR DVC.`

## pseudocode

```c
__int64 __fastcall CPipeManager::StartFbrProtocol(CPipeManager *this)
{
  __int64 v2; // rbx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  const char *v10; // rax
  int *v11; // rdx
  LSTATUS v12; // edi
  unsigned int v13; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  char *v23; // [rsp+58h] [rbp-A8h] BYREF
  const char *v24; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  const char *v27; // [rsp+70h] [rbp-90h] BYREF
  const char *v28; // [rsp+78h] [rbp-88h] BYREF
  const char *v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  wchar_t String2[32]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Data[32]; // [rsp+E0h] [rbp-20h] BYREF

  v30 = 0;
  Type = 0;
  v23 = (char *)this + 48896;
  cbData = 64;
  hKey = 0;
  CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
  v2 = 0;
  if ( *((_QWORD *)this + 1624) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v30);
    v2 = *((_QWORD *)this + 1624);
    v30 = v2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v30);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v23);
  if ( !v2 )
  {
    v6 = -2147418113;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v22 = 9309;
      v27 = "spProtocol == NULL";
      LODWORD(v23) = -2147418113;
      v28 = "StartFbrProtocol";
      v29 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)word_1802758C2,
        v4,
        v5,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v27);
    }
    goto LABEL_48;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v2 + 264LL))(v2, String2, 32);
  if ( v6 < 0 )
  {
    v9 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_48;
    v10 = "IRdpPipeProtocol::GetClientUniqueId failed.";
    LODWORD(v23) = 9312;
    v11 = &dword_180275874;
    goto LABEL_47;
  }
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    else
      v13 = v12;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 246;
LABEL_17:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      CurrentThreadActivityIdPrefix,
      v13);
LABEL_18:
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    else
      v6 = v12;
    goto LABEL_48;
  }
  v12 = RegQueryValueExW(hKey, L"InstanceID", 0, &Type, (LPBYTE)Data, &cbData);
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    else
      v13 = v12;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 247;
    goto LABEL_17;
  }
  if ( Type != 1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 248;
LABEL_34:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v16,
      -2147418113);
LABEL_35:
    v6 = -2147418113;
    goto LABEL_48;
  }
  if ( cbData != 64 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 249;
    goto LABEL_34;
  }
  if ( !wcsnicmp(Data, String2, 0x20u) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v24 = "Capability: CPipeManager::StartFbrProtocol - Client and server are the same machine - opening the FBR DVC.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v18,
        (unsigned int)word_180275852,
        v19,
        v20,
        (__int64)&v24);
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1635) + 56LL))(*((_QWORD *)this + 1635));
    if ( v6 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v10 = "Failed to create FBR protocol";
      LODWORD(v23) = 9374;
      v11 = &dword_180275804;
LABEL_47:
      v24 = v10;
      v29 = "StartFbrProtocol";
      v28 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v27 = "Error HResult failed";
      v22 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (_DWORD)v11,
        v7,
        v8,
        (__int64)&v27,
        (__int64)&v22,
        (__int64)&v28,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v24);
    }
  }
LABEL_48:
  if ( hKey )
    RegCloseKey(hKey);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009dafc  push    rbp
0x18009dafe  push    rbx
0x18009daff  push    rsi
0x18009db00  push    rdi
0x18009db01  lea     rbp, [rsp-38h]
0x18009db06  sub     rsp, 138h
0x18009db0d  mov     rax, cs:__security_cookie
0x18009db14  xor     rax, rsp
0x18009db17  mov     [rbp+50h+var_30], rax
0x18009db1b  mov     rsi, rcx
0x18009db1e  mov     [rbp+50h+var_C8], 0
0x18009db26  add     rcx, 0BF00h; this
0x18009db2d  mov     [rsp+150h+Type], 0
0x18009db35  mov     [rsp+150h+var_F8], rcx
0x18009db3a  mov     [rsp+150h+cbData], 40h ; '@'
0x18009db42  mov     [rbp+50h+hKey], 0
0x18009db4a  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18009db4f  xor     ebx, ebx
0x18009db51  cmp     [rsi+32C0h], rbx
0x18009db58  jz      short loc_18009DB77
0x18009db5a  lea     rcx, [rbp+50h+var_C8]
0x18009db5e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009db63  mov     rbx, [rsi+32C0h]
0x18009db6a  lea     rcx, [rbp+50h+var_C8]
0x18009db6e  mov     [rbp+50h+var_C8], rbx
0x18009db72  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009db77  lea     rcx, [rsp+150h+var_F8]; this
0x18009db7c  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009db81  test    rbx, rbx
0x18009db84  jnz     loc_18009DC1B
0x18009db8a  mov     eax, cs:CallbackContext
0x18009db90  mov     ebx, 8000FFFFh
0x18009db95  cmp     eax, 2
0x18009db98  jbe     loc_18009DEF7
0x18009db9e  lea     rax, aSpprotocolNull; "spProtocol == NULL"
0x18009dba5  mov     [rsp+150h+var_100], 245Dh
0x18009dbad  mov     [rsp+150h+var_E0], rax
0x18009dbb2  lea     rdx, word_1802758C2
0x18009dbb9  lea     rax, aStartfbrprotoc; "StartFbrProtocol"
0x18009dbc0  mov     dword ptr [rsp+150h+var_F8], ebx
0x18009dbc4  mov     [rsp+150h+var_D8], rax
0x18009dbc9  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009dbd0  mov     [rbp+50h+var_D0], rax
0x18009dbd4  lea     rax, aErrorCondition; "Error condition failed"
0x18009dbdb  mov     [rsp+150h+var_F0], rax
0x18009dbe0  lea     rax, [rsp+150h+var_E0]
0x18009dbe5  mov     [rsp+150h+var_108], rax
0x18009dbea  lea     rax, [rsp+150h+var_D8]
0x18009dbef  mov     [rsp+150h+var_110], rax
0x18009dbf4  lea     rax, [rsp+150h+var_100]
0x18009dbf9  mov     [rsp+150h+var_118], rax
0x18009dbfe  lea     rax, [rbp+50h+var_D0]
0x18009dc02  mov     [rsp+150h+var_120], rax
0x18009dc07  lea     rax, [rsp+150h+var_F8]
0x18009dc0c  mov     [rsp+150h+lpcbData], rax
0x18009dc11  lea     rax, [rsp+150h+var_F0]
0x18009dc16  jmp     loc_18009DEED
0x18009dc1b  mov     rax, [rbx]
0x18009dc1e  lea     rdx, [rbp+50h+String2]
0x18009dc22  mov     r8d, 20h ; ' '
0x18009dc28  mov     rcx, rbx
0x18009dc2b  mov     rax, [rax+108h]
0x18009dc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc37  mov     ebx, eax
0x18009dc39  test    eax, eax
0x18009dc3b  jns     short loc_18009DC67
0x18009dc3d  mov     ecx, cs:CallbackContext
0x18009dc43  cmp     ecx, 2
0x18009dc46  jbe     loc_18009DEF7
0x18009dc4c  lea     rax, aIrdppipeprotoc; "IRdpPipeProtocol::GetClientUniqueId fai"...
0x18009dc53  mov     dword ptr [rsp+150h+var_F8], 2460h
0x18009dc5b  lea     rdx, dword_180275874
0x18009dc62  jmp     loc_18009DE8B
0x18009dc67  lea     rax, [rbp+50h+hKey]
0x18009dc6b  mov     r9d, 20019h; samDesired
0x18009dc71  xor     r8d, r8d; ulOptions
0x18009dc74  mov     [rsp+150h+phkResult], rax; phkResult
0x18009dc79  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18009dc80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009dc87  call    cs:__imp_RegOpenKeyExW
0x18009dc8d  mov     edi, eax
0x18009dc8f  test    eax, eax
0x18009dc91  jz      short loc_18009DD01
0x18009dc93  mov     rax, cs:WPP_GLOBAL_Control
0x18009dc9a  lea     rcx, WPP_GLOBAL_Control
0x18009dca1  mov     esi, 80070000h
0x18009dca6  cmp     rax, rcx
0x18009dca9  jz      short loc_18009DCEC
0x18009dcab  test    byte ptr [rax+1Ch], 8
0x18009dcaf  jz      short loc_18009DCEC
0x18009dcb1  cmp     byte ptr [rax+19h], 2
0x18009dcb5  jb      short loc_18009DCEC
0x18009dcb7  test    edi, edi
0x18009dcb9  jg      short loc_18009DCBF
0x18009dcbb  mov     ebx, edi
0x18009dcbd  jmp     short loc_18009DCC4
0x18009dcbf  movzx   ebx, di
0x18009dcc2  or      ebx, esi
0x18009dcc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009dcc9  mov     edx, 0F6h
0x18009dcce  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dcd5  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18009dcdc  mov     r9d, eax
0x18009dcdf  mov     dword ptr [rsp+150h+phkResult], ebx
0x18009dce3  mov     rcx, [rcx+10h]
0x18009dce7  call    WPP_SF_Dd
0x18009dcec  test    edi, edi
0x18009dcee  jg      short loc_18009DCF7
0x18009dcf0  mov     ebx, edi
0x18009dcf2  jmp     loc_18009DEF7
0x18009dcf7  movzx   ebx, di
0x18009dcfa  or      ebx, esi
0x18009dcfc  jmp     loc_18009DEF7
0x18009dd01  mov     rcx, [rbp+50h+hKey]; hKey
0x18009dd05  lea     rax, [rsp+150h+cbData]
0x18009dd0a  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18009dd0f  lea     r9, [rsp+150h+Type]; lpType
0x18009dd14  lea     rax, [rbp+50h+Data]
0x18009dd18  xor     r8d, r8d; lpReserved
0x18009dd1b  lea     rdx, aInstanceid; "InstanceID"
0x18009dd22  mov     [rsp+150h+phkResult], rax; lpData
0x18009dd27  call    cs:__imp_RegQueryValueExW
0x18009dd2d  mov     edi, eax
0x18009dd2f  test    eax, eax
0x18009dd31  jz      short loc_18009DD73
0x18009dd33  mov     rax, cs:WPP_GLOBAL_Control
0x18009dd3a  lea     rcx, WPP_GLOBAL_Control
0x18009dd41  mov     esi, 80070000h
0x18009dd46  cmp     rax, rcx
0x18009dd49  jz      short loc_18009DCEC
0x18009dd4b  test    byte ptr [rax+1Ch], 8
0x18009dd4f  jz      short loc_18009DCEC
0x18009dd51  cmp     byte ptr [rax+19h], 2
0x18009dd55  jb      short loc_18009DCEC
0x18009dd57  test    edi, edi
0x18009dd59  jg      short loc_18009DD5F
0x18009dd5b  mov     ebx, edi
0x18009dd5d  jmp     short loc_18009DD64
0x18009dd5f  movzx   ebx, di
0x18009dd62  or      ebx, esi
0x18009dd64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009dd69  mov     edx, 0F7h
0x18009dd6e  jmp     loc_18009DCCE
0x18009dd73  cmp     [rsp+150h+Type], 1
0x18009dd78  jz      short loc_18009DDCF
0x18009dd7a  mov     rax, cs:WPP_GLOBAL_Control
0x18009dd81  lea     rcx, WPP_GLOBAL_Control
0x18009dd88  cmp     rax, rcx
0x18009dd8b  jz      short loc_18009DDC5
0x18009dd8d  test    byte ptr [rax+1Ch], 8
0x18009dd91  jz      short loc_18009DDC5
0x18009dd93  cmp     byte ptr [rax+19h], 2
0x18009dd97  jb      short loc_18009DDC5
0x18009dd99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009dd9e  mov     edx, 0F8h
0x18009dda3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ddaa  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18009ddb1  mov     r9d, eax
0x18009ddb4  mov     dword ptr [rsp+150h+phkResult], 8000FFFFh
0x18009ddbc  mov     rcx, [rcx+10h]
0x18009ddc0  call    WPP_SF_Dd
0x18009ddc5  mov     ebx, 8000FFFFh
0x18009ddca  jmp     loc_18009DEF7
0x18009ddcf  cmp     [rsp+150h+cbData], 40h ; '@'
0x18009ddd4  jz      short loc_18009DE01
0x18009ddd6  mov     rax, cs:WPP_GLOBAL_Control
0x18009dddd  lea     rcx, WPP_GLOBAL_Control
0x18009dde4  cmp     rax, rcx
0x18009dde7  jz      short loc_18009DDC5
0x18009dde9  test    byte ptr [rax+1Ch], 8
0x18009dded  jz      short loc_18009DDC5
0x18009ddef  cmp     byte ptr [rax+19h], 2
0x18009ddf3  jb      short loc_18009DDC5
0x18009ddf5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009ddfa  mov     edx, 0F9h
0x18009ddff  jmp     short loc_18009DDA3
0x18009de01  mov     r8d, 20h ; ' '; MaxCount
0x18009de07  lea     rdx, [rbp+50h+String2]; String2
0x18009de0b  lea     rcx, [rbp+50h+Data]; String1
0x18009de0f  call    _wcsnicmp
0x18009de14  test    eax, eax
0x18009de16  jnz     loc_18009DEF7
0x18009de1c  mov     eax, cs:CallbackContext
0x18009de22  cmp     eax, 4
0x18009de25  jbe     short loc_18009DE49
0x18009de27  lea     rax, aCapabilityCpip; "Capability: CPipeManager::StartFbrProto"...
0x18009de2e  mov     [rsp+150h+var_F0], rax
0x18009de33  lea     rdx, word_180275852
0x18009de3a  lea     rax, [rsp+150h+var_F0]
0x18009de3f  mov     [rsp+150h+phkResult], rax
0x18009de44  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009de49  mov     rcx, [rsi+3318h]
0x18009de50  mov     rax, [rcx]
0x18009de53  mov     rax, [rax+38h]
0x18009de57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009de5c  mov     ebx, eax
0x18009de5e  test    eax, eax
0x18009de60  jns     loc_18009DEF7
0x18009de66  mov     eax, cs:CallbackContext
0x18009de6c  cmp     eax, 2
0x18009de6f  jbe     loc_18009DEF7
0x18009de75  lea     rax, aFailedToCreate_8; "Failed to create FBR protocol"
0x18009de7c  mov     dword ptr [rsp+150h+var_F8], 249Eh
0x18009de84  lea     rdx, dword_180275804
0x18009de8b  mov     [rsp+150h+var_F0], rax
0x18009de90  lea     rax, aStartfbrprotoc; "StartFbrProtocol"
0x18009de97  mov     [rbp+50h+var_D0], rax
0x18009de9b  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009dea2  mov     [rsp+150h+var_D8], rax
0x18009dea7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009deae  mov     [rsp+150h+var_E0], rax
0x18009deb3  lea     rax, [rsp+150h+var_F0]
0x18009deb8  mov     [rsp+150h+var_108], rax
0x18009debd  lea     rax, [rbp+50h+var_D0]
0x18009dec1  mov     [rsp+150h+var_110], rax
0x18009dec6  lea     rax, [rsp+150h+var_F8]
0x18009decb  mov     [rsp+150h+var_118], rax
0x18009ded0  lea     rax, [rsp+150h+var_D8]
0x18009ded5  mov     [rsp+150h+var_120], rax
0x18009deda  lea     rax, [rsp+150h+var_100]
0x18009dedf  mov     [rsp+150h+lpcbData], rax
0x18009dee4  lea     rax, [rsp+150h+var_E0]
0x18009dee9  mov     [rsp+150h+var_100], ebx
0x18009deed  mov     [rsp+150h+phkResult], rax
0x18009def2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009def7  mov     rcx, [rbp+50h+hKey]; hKey
0x18009defb  test    rcx, rcx
0x18009defe  jz      short loc_18009DF06
0x18009df00  call    cs:__imp_RegCloseKey
0x18009df06  lea     rcx, [rbp+50h+var_C8]
0x18009df0a  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009df0f  mov     eax, ebx
0x18009df11  mov     rcx, [rbp+50h+var_30]
0x18009df15  xor     rcx, rsp; StackCookie
0x18009df18  call    __security_check_cookie
0x18009df1d  add     rsp, 138h
0x18009df24  pop     rdi
0x18009df25  pop     rsi
0x18009df26  pop     rbx
0x18009df27  pop     rbp
0x18009df28  retn
```
