# DebugSetDefaultXformModeAccordingToRegKey(void)

- ea: `0x18016c404`
- end: `0x18016c5bf`
- name: `?DebugSetDefaultXformModeAccordingToRegKey@@YAXXZ`
- size: `443`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18016d0a8`

## callees

- `0x180002170`
- `0x1800067c8`
- `0x18016c404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016c47d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18016c47d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18016c5b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18016c5b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016c448`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016c448`

## string_xrefs

- `0x18016c4d3`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c4de`: `Invalid value for registry key "Software\Microsoft\Terminal Server Client\XformMode": expecting a value between 0 and 2, got %d`
- `0x18016c569`: `Codec DWT Transform mode overriden to %d:%s by registry key "Software\Microsoft\Terminal Server Client\XformMode"`

## pseudocode

```c
void DebugSetDefaultXformModeAccordingToRegKey(void)
{
  int v0; // r8d
  int v1; // r9d
  const char *v2; // rcx
  int v3; // [rsp+50h] [rbp+17h] BYREF
  int v4; // [rsp+54h] [rbp+1Bh] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  const char *v6; // [rsp+60h] [rbp+27h] BYREF
  const char *v7; // [rsp+68h] [rbp+2Fh] BYREF
  const char *v8; // [rsp+70h] [rbp+37h] BYREF
  _QWORD v9[3]; // [rsp+78h] [rbp+3Fh]
  int Data; // [rsp+A0h] [rbp+67h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+77h] BYREF
  int v13; // [rsp+B8h] [rbp+7Fh] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Terminal Server Client", 0, 1u, &hKey) )
  {
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"XformMode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      if ( (unsigned int)(Data - 1) <= 1 )
      {
        CacNx::gDebug_DefaultXformMode = Data;
        v9[0] = L"XFORM_MODE_UNSPECIFIED";
        v9[1] = L"XFORM_MODE_ORIGINAL";
        v9[2] = L"XFORM_MODE_REDUCE_INTERPOLATE";
        if ( (unsigned int)CallbackContext > 4 )
        {
          v7 = "Codec DWT Transform mode overriden to %d:%s by registry key \"Software\\Microsoft\\Terminal Server Client\\XformMode\"";
          v2 = (const char *)v9[Data];
          v13 = Data;
          v8 = v2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v2,
            (unsigned int)qword_1802A13B0,
            v0,
            v1,
            (__int64)&v7,
            (__int64)&v13,
            (__int64)&v8);
        }
      }
      else if ( Data && (unsigned int)CallbackContext > 2 )
      {
        v13 = Data;
        v6 = "DebugSetDefaultXformModeAccordingToRegKey";
        v7 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
        v8 = "Invalid value for registry key \"Software\\Microsoft\\Terminal Server Client\\XformMode\": expecting a valu"
             "e between 0 and 2, got %d";
        v3 = 1189;
        v4 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          Data,
          (unsigned int)&dword_1802A272C,
          v0,
          v1,
          (__int64)&v8,
          (__int64)&v4,
          (__int64)&v7,
          (__int64)&v3,
          (__int64)&v6,
          (__int64)&v13);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18016c404  push    rbp
0x18016c406  lea     rbp, [rsp-57h]
0x18016c40b  sub     rsp, 90h
0x18016c412  lea     rax, [rbp+57h+hKey]
0x18016c416  mov     [rbp+57h+hKey], 0
0x18016c41e  mov     r9d, 1; samDesired
0x18016c424  mov     [rsp+90h+phkResult], rax; phkResult
0x18016c429  xor     r8d, r8d; ulOptions
0x18016c42c  mov     [rbp+57h+Data], 0
0x18016c433  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Terminal Server Cl"...
0x18016c43a  mov     [rbp+57h+cbData], 4
0x18016c441  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18016c448  call    cs:__imp_RegOpenKeyExW
0x18016c44e  test    eax, eax
0x18016c450  jnz     loc_18016C5A7
0x18016c456  mov     rcx, [rbp+57h+hKey]; hKey
0x18016c45a  lea     r9, [rbp+57h+Type]; lpType
0x18016c45e  mov     [rbp+57h+Type], eax
0x18016c461  lea     rdx, aXformmode; "XformMode"
0x18016c468  lea     rax, [rbp+57h+cbData]
0x18016c46c  xor     r8d, r8d; lpReserved
0x18016c46f  mov     [rsp+90h+lpcbData], rax; lpcbData
0x18016c474  lea     rax, [rbp+57h+Data]
0x18016c478  mov     [rsp+90h+phkResult], rax; lpData
0x18016c47d  call    cs:__imp_RegQueryValueExW
0x18016c483  test    eax, eax
0x18016c485  jnz     loc_18016C5A7
0x18016c48b  cmp     [rbp+57h+Type], 4
0x18016c48f  jnz     loc_18016C5A7
0x18016c495  mov     ecx, [rbp+57h+Data]
0x18016c498  lea     eax, [rcx-1]
0x18016c49b  cmp     eax, 1
0x18016c49e  jbe     loc_18016C534
0x18016c4a4  test    ecx, ecx
0x18016c4a6  jz      loc_18016C5A7
0x18016c4ac  mov     eax, cs:CallbackContext
0x18016c4b2  cmp     eax, 2
0x18016c4b5  jbe     loc_18016C5A7
0x18016c4bb  mov     eax, [rbp+57h+Data]
0x18016c4be  lea     rdx, dword_1802A272C
0x18016c4c5  mov     [rbp+57h+arg_18], eax
0x18016c4c8  lea     rax, aDebugsetdefaul; "DebugSetDefaultXformModeAccordingToRegK"...
0x18016c4cf  mov     [rbp+57h+var_30], rax
0x18016c4d3  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c4da  mov     [rbp+57h+var_28], rax
0x18016c4de  lea     rax, aInvalidValueFo; "Invalid value for registry key \"Softwa"...
0x18016c4e5  mov     [rbp+57h+var_20], rax
0x18016c4e9  lea     rax, [rbp+57h+arg_18]
0x18016c4ed  mov     [rsp+90h+var_48], rax
0x18016c4f2  lea     rax, [rbp+57h+var_30]
0x18016c4f6  mov     [rsp+90h+var_50], rax
0x18016c4fb  lea     rax, [rbp+57h+var_40]
0x18016c4ff  mov     [rsp+90h+var_58], rax
0x18016c504  lea     rax, [rbp+57h+var_28]
0x18016c508  mov     [rsp+90h+var_60], rax
0x18016c50d  lea     rax, [rbp+57h+var_3C]
0x18016c511  mov     [rsp+90h+lpcbData], rax
0x18016c516  lea     rax, [rbp+57h+var_20]
0x18016c51a  mov     [rsp+90h+phkResult], rax
0x18016c51f  mov     [rbp+57h+var_40], 4A5h
0x18016c526  mov     [rbp+57h+var_3C], 80004005h
0x18016c52d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016c532  jmp     short loc_18016C5A7
0x18016c534  lea     rax, aXformModeUnspe; "XFORM_MODE_UNSPECIFIED"
0x18016c53b  mov     cs:?gDebug_DefaultXformMode@CacNx@@3W4XformMode@1@A, ecx; CacNx::XformMode CacNx::gDebug_DefaultXformMode
0x18016c541  mov     [rbp+57h+var_18], rax
0x18016c545  lea     rax, aXformModeOrigi; "XFORM_MODE_ORIGINAL"
0x18016c54c  mov     [rbp+57h+var_10], rax
0x18016c550  lea     rax, aXformModeReduc; "XFORM_MODE_REDUCE_INTERPOLATE"
0x18016c557  mov     [rbp+57h+var_8], rax
0x18016c55b  mov     eax, cs:CallbackContext
0x18016c561  cmp     eax, 4
0x18016c564  jbe     short loc_18016C5A7
0x18016c566  mov     edx, [rbp+57h+Data]
0x18016c569  lea     rax, aCodecDwtTransf; "Codec DWT Transform mode overriden to %"...
0x18016c570  mov     [rbp+57h+var_28], rax
0x18016c574  lea     rax, [rbp+57h+var_20]
0x18016c578  mov     [rsp+90h+var_60], rax
0x18016c57d  lea     rax, [rbp+57h+arg_18]
0x18016c581  mov     [rsp+90h+lpcbData], rax
0x18016c586  lea     rax, [rbp+57h+var_28]
0x18016c58a  mov     rcx, [rbp+rdx*8+57h+var_18]
0x18016c58f  mov     [rbp+57h+arg_18], edx
0x18016c592  lea     rdx, qword_1802A13B0
0x18016c599  mov     [rsp+90h+phkResult], rax
0x18016c59e  mov     [rbp+57h+var_20], rcx
0x18016c5a2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18016c5a7  mov     rcx, [rbp+57h+hKey]; hKey
0x18016c5ab  test    rcx, rcx
0x18016c5ae  jz      short loc_18016C5B6
0x18016c5b0  call    cs:__imp_RegCloseKey
0x18016c5b6  add     rsp, 90h
0x18016c5bd  pop     rbp
0x18016c5be  retn
```
