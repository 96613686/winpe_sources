# UpdateVersionString(void)

- ea: `0x180027c38`
- end: `0x180027e7b`
- name: `?UpdateVersionString@@YAXXZ`
- size: `579`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x1800016d4`
- `0x180015630`
- `0x18001a174`
- `0x180027c38`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027da1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027da1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027cdd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027cdd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027d13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027d13`

## string_xrefs

- `0x180027c7e`: `PENSERVICE_UpdateVersionString`
- `0x180027d35`: `PENSERVICE_UpdateVersionString`
- `0x180027dbf`: `PENSERVICE_UpdateVersionString`
- `0x180027e3d`: `PENSERVICE_UpdateVersionString`
- `0x180027d71`: `RegSetValueEx failed.`
- `0x180027dfb`: `RegCreateKeyEx failed.`

## pseudocode

```c
void UpdateVersionString(void)
{
  struct _GUID *v0; // rcx
  unsigned __int64 v1; // r8
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const struct _GUID *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  struct _GUID *v12; // rax
  unsigned __int64 v13; // r8
  LSTATUS v14; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF
  const char *v16; // [rsp+80h] [rbp+30h] BYREF

  v0 = WPP_GLOBAL_Control;
  v1 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v1 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x616u, v1, 1u);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != (struct _GUID *)&WPP_GLOBAL_Control && (v0[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v0[1].Data1,
      10,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_UpdateVersionString");
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Tablet PC",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        12,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_UpdateVersionString",
        v2);
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v14 = v3;
      v16 = "RegCreateKeyEx failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v9,
        (unsigned int)byte_18003A5D1,
        v10,
        v11,
        (__int64)&v14,
        (__int64)&v16);
    }
  }
  else
  {
    v4 = RegSetValueExW(hKey, L"Ident", 0, 1u, L"2.0", 8u);
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          11,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_UpdateVersionString",
          v4);
      if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
      {
        v14 = v5;
        v16 = "RegSetValueEx failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)&dword_180039F3C,
          v7,
          v8,
          (__int64)&v14,
          (__int64)&v16);
      }
    }
    RegCloseKey(hKey);
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      13,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_UpdateVersionString");
    v12 = WPP_GLOBAL_Control;
  }
  v13 = *(_QWORD *)v12[3].Data4;
  if ( v13 )
    PrivateTraceEvent(v9, 0x616u, v13, 2u);
}

```

## disassembly

```asm
0x180027c38  push    rbp
0x180027c3a  push    rbx
0x180027c3b  push    r14
0x180027c3d  mov     rbp, rsp
0x180027c40  sub     rsp, 50h
0x180027c44  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x180027c4b  mov     r8, [rcx+38h]; unsigned __int64
0x180027c4f  test    r8, r8
0x180027c52  jz      short loc_180027C68
0x180027c54  mov     r9b, 1; unsigned __int8
0x180027c57  mov     edx, 616h; unsigned int
0x180027c5c  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180027c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c68  lea     r14, WPP_GLOBAL_Control
0x180027c6f  cmp     rcx, r14
0x180027c72  jz      short loc_180027C96
0x180027c74  test    byte ptr [rcx+1Ch], 10h
0x180027c78  jz      short loc_180027C96
0x180027c7a  mov     rcx, [rcx+10h]
0x180027c7e  lea     r9, aPenserviceUpda; "PENSERVICE_UpdateVersionString"
0x180027c85  mov     edx, 0Ah
0x180027c8a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027c91  call    WPP_SF_s
0x180027c96  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180027c9f  lea     rax, [rbp+hKey]
0x180027ca3  mov     [rsp+50h+phkResult], rax; phkResult
0x180027ca8  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027caf  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027cb8  xor     r9d, r9d; lpClass
0x180027cbb  mov     [rsp+50h+samDesired], 20006h; samDesired
0x180027cc3  xor     r8d, r8d; Reserved
0x180027cc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ccd  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180027cd5  mov     [rbp+hKey], 0
0x180027cdd  call    cs:__imp_RegCreateKeyExW
0x180027ce3  mov     ebx, eax
0x180027ce5  test    eax, eax
0x180027ce7  jnz     loc_180027DA9
0x180027ced  mov     rcx, [rbp+hKey]; hKey
0x180027cf1  lea     rax, a20; "2.0"
0x180027cf8  mov     [rsp+50h+samDesired], 8; cbData
0x180027d00  lea     r9d, [rbx+1]; dwType
0x180027d04  xor     r8d, r8d; Reserved
0x180027d07  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180027d0c  lea     rdx, aIdent; "Ident"
0x180027d13  call    cs:__imp_RegSetValueExW
0x180027d19  mov     ebx, eax
0x180027d1b  test    eax, eax
0x180027d1d  jz      short loc_180027D9D
0x180027d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d26  cmp     rcx, r14
0x180027d29  jz      short loc_180027D51
0x180027d2b  test    byte ptr [rcx+1Ch], 10h
0x180027d2f  jz      short loc_180027D51
0x180027d31  mov     rcx, [rcx+10h]
0x180027d35  lea     r9, aPenserviceUpda; "PENSERVICE_UpdateVersionString"
0x180027d3c  mov     edx, 0Bh
0x180027d41  mov     [rsp+50h+dwOptions], eax
0x180027d45  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027d4c  call    WPP_SF_sd
0x180027d51  mov     eax, cs:dword_1800411A8
0x180027d57  cmp     eax, 5
0x180027d5a  jbe     short loc_180027D9D
0x180027d5c  mov     edx, 4000000h
0x180027d61  lea     rcx, dword_1800411A8
0x180027d68  call    _tlgKeywordOn
0x180027d6d  test    al, al
0x180027d6f  jz      short loc_180027D9D
0x180027d71  lea     rax, aRegsetvalueexF; "RegSetValueEx failed."
0x180027d78  mov     [rbp+arg_0], ebx
0x180027d7b  mov     [rbp+arg_10], rax
0x180027d7f  lea     rdx, dword_180039F3C
0x180027d86  lea     rax, [rbp+arg_10]
0x180027d8a  mov     qword ptr [rsp+50h+samDesired], rax
0x180027d8f  lea     rax, [rbp+arg_0]
0x180027d93  mov     qword ptr [rsp+50h+dwOptions], rax
0x180027d98  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027d9d  mov     rcx, [rbp+hKey]; hKey
0x180027da1  call    cs:__imp_RegCloseKey
0x180027da7  jmp     short loc_180027E27
0x180027da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027db0  cmp     rcx, r14
0x180027db3  jz      short loc_180027DDB
0x180027db5  test    byte ptr [rcx+1Ch], 10h
0x180027db9  jz      short loc_180027DDB
0x180027dbb  mov     rcx, [rcx+10h]
0x180027dbf  lea     r9, aPenserviceUpda; "PENSERVICE_UpdateVersionString"
0x180027dc6  mov     edx, 0Ch
0x180027dcb  mov     [rsp+50h+dwOptions], ebx
0x180027dcf  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027dd6  call    WPP_SF_sd
0x180027ddb  mov     eax, cs:dword_1800411A8
0x180027de1  cmp     eax, 5
0x180027de4  jbe     short loc_180027E27
0x180027de6  mov     edx, 4000000h
0x180027deb  lea     rcx, dword_1800411A8
0x180027df2  call    _tlgKeywordOn
0x180027df7  test    al, al
0x180027df9  jz      short loc_180027E27
0x180027dfb  lea     rax, aRegcreatekeyex; "RegCreateKeyEx failed."
0x180027e02  mov     [rbp+arg_0], ebx
0x180027e05  mov     [rbp+arg_10], rax
0x180027e09  lea     rdx, byte_18003A5D1
0x180027e10  lea     rax, [rbp+arg_10]
0x180027e14  mov     qword ptr [rsp+50h+samDesired], rax
0x180027e19  lea     rax, [rbp+arg_0]
0x180027e1d  mov     qword ptr [rsp+50h+dwOptions], rax
0x180027e22  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027e27  mov     rax, cs:WPP_GLOBAL_Control
0x180027e2e  cmp     rax, r14
0x180027e31  jz      short loc_180027E5C
0x180027e33  test    byte ptr [rax+1Ch], 10h
0x180027e37  jz      short loc_180027E5C
0x180027e39  mov     rcx, [rax+10h]
0x180027e3d  lea     r9, aPenserviceUpda; "PENSERVICE_UpdateVersionString"
0x180027e44  mov     edx, 0Dh
0x180027e49  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027e50  call    WPP_SF_s
0x180027e55  mov     rax, cs:WPP_GLOBAL_Control
0x180027e5c  mov     r8, [rax+38h]; unsigned __int64
0x180027e60  test    r8, r8
0x180027e63  jz      short loc_180027E72
0x180027e65  mov     r9b, 2; unsigned __int8
0x180027e68  mov     edx, 616h; unsigned int
0x180027e6d  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180027e72  add     rsp, 50h
0x180027e76  pop     r14
0x180027e78  pop     rbx
0x180027e79  pop     rbp
0x180027e7a  retn
```
