# WaasMedic::RegCreateKeyHelperPrivate

- ea: `0x180027644`
- end: `0x180027801`
- name: `WaasMedic::RegCreateKeyHelperPrivate`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180029500`

## callees

- `0x180002150`
- `0x180016c9c`
- `0x18002543c`
- `0x180027644`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027695`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027695`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027703`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027703`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002773d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002773d`

## string_xrefs

- `0x180027755`: `RegUtil: Error when attempting to create registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegCreateKeyHelperPrivate(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        HKEY *a4,
        signed int a5)
{
  HKEY v5; // rcx
  bool v7; // zf
  REGSAM samDesired; // esi
  signed int v10; // ebx
  LSTATUS v11; // eax
  const struct _tlgProvider_t *v12; // rcx
  int v13; // r9d
  unsigned __int16 *v15; // [rsp+50h] [rbp-11h] BYREF
  __int64 v16; // [rsp+58h] [rbp-9h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+60h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+5Fh] BYREF
  HKEY hKey; // [rsp+D0h] [rbp+6Fh] BYREF
  const WCHAR *v20; // [rsp+D8h] [rbp+77h] BYREF

  v18 = a1;
  v5 = 0;
  v7 = dword_180098D58 == 0;
  hKey = 0;
  samDesired = 131078;
  *a4 = 0;
  if ( v7 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
    v5 = hKey;
  }
  if ( dword_180098D54 )
    samDesired = 131334;
  v10 = 0;
  if ( a2 )
  {
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, samDesired, 0, &hKey, 0);
    if ( v11 )
    {
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      else
        v10 = v11;
      v5 = hKey;
    }
    else
    {
      v5 = 0;
      *a4 = hKey;
      hKey = 0;
    }
  }
  else
  {
    *a4 = HKEY_LOCAL_MACHINE;
  }
  if ( v5 )
    RegCloseKey(v5);
  if ( v10 < 0 )
  {
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to create registry key. Parent key: [%s] Sub key: [%s]. hr=0x%08X",
      a2);
    v12 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v12 > 5u
      && (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v12 + 3) & 0x400000000000LL) == *((_QWORD *)v12 + 3) )
    {
      a5 = v10;
      v15 = &gc_pszVersionString;
      v18 = 0;
      v20 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)word_18008945A,
        0,
        v13,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v20,
        (__int64)&v18,
        (__int64)&a5);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180027644  mov     [rsp-8+hKey], r8
0x180027649  mov     [rsp-8+arg_0], rcx
0x18002764e  push    rbp
0x18002764f  push    rbx
0x180027650  push    rsi
0x180027651  push    rdi
0x180027652  push    r14
0x180027654  lea     rbp, [rsp-2Fh]
0x180027659  sub     rsp, 90h
0x180027660  xor     ecx, ecx
0x180027662  mov     rdi, r9
0x180027665  cmp     cs:dword_180098D58, ecx
0x18002766b  mov     r14, rdx
0x18002766e  mov     [rbp+4Fh+hKey], rcx
0x180027672  mov     esi, 20006h
0x180027677  mov     [r9], rcx
0x18002767a  jnz     short loc_1800276C2
0x18002767c  xorps   xmm0, xmm0
0x18002767f  mov     cs:dword_180098D54, ecx
0x180027685  lea     rcx, [rbp+4Fh+SystemInfo]; lpSystemInfo
0x180027689  movups  xmmword ptr [rbp+4Fh+SystemInfo], xmm0
0x18002768d  movups  xmmword ptr [rbp+4Fh+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180027691  movups  xmmword ptr [rbp+4Fh+SystemInfo.dwNumberOfProcessors], xmm0
0x180027695  call    cs:__imp_GetNativeSystemInfo
0x18002769b  mov     eax, 6
0x1800276a0  lea     ecx, [rax-5]
0x1800276a3  cmp     ax, word ptr [rbp+4Fh+SystemInfo]
0x1800276a7  jz      short loc_1800276B2
0x1800276a9  lea     eax, [rcx+8]
0x1800276ac  cmp     ax, word ptr [rbp+4Fh+SystemInfo]
0x1800276b0  jnz     short loc_1800276B8
0x1800276b2  mov     cs:dword_180098D54, ecx
0x1800276b8  mov     cs:dword_180098D58, ecx
0x1800276be  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800276c2  cmp     cs:dword_180098D54, 0
0x1800276c9  mov     eax, 20106h
0x1800276ce  cmovnz  esi, eax
0x1800276d1  xor     ebx, ebx
0x1800276d3  test    r14, r14
0x1800276d6  jz      short loc_180027731
0x1800276d8  mov     [rsp+0B0h+lpdwDisposition], rbx; lpdwDisposition
0x1800276dd  lea     rax, [rbp+4Fh+hKey]
0x1800276e1  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800276e6  xor     r9d, r9d; lpClass
0x1800276e9  mov     [rsp+0B0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800276ee  xor     r8d, r8d; Reserved
0x1800276f1  mov     [rsp+0B0h+samDesired], esi; samDesired
0x1800276f5  mov     rdx, r14; lpSubKey
0x1800276f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800276ff  mov     [rsp+0B0h+dwOptions], ebx; dwOptions
0x180027703  call    cs:__imp_RegCreateKeyExW
0x180027709  test    eax, eax
0x18002770b  jz      short loc_180027722
0x18002770d  jg      short loc_180027713
0x18002770f  mov     ebx, eax
0x180027711  jmp     short loc_18002771C
0x180027713  movzx   ebx, ax
0x180027716  or      ebx, 80070000h
0x18002771c  mov     rcx, [rbp+4Fh+hKey]
0x180027720  jmp     short loc_180027738
0x180027722  mov     rax, [rbp+4Fh+hKey]
0x180027726  xor     ecx, ecx
0x180027728  mov     [rdi], rax
0x18002772b  mov     [rbp+4Fh+hKey], rcx
0x18002772f  jmp     short loc_180027738
0x180027731  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x180027738  test    rcx, rcx
0x18002773b  jz      short loc_180027743
0x18002773d  call    cs:__imp_RegCloseKey
0x180027743  test    ebx, ebx
0x180027745  jns     loc_1800277F1
0x18002774b  xor     r9d, r9d
0x18002774e  mov     [rsp+0B0h+dwOptions], ebx
0x180027752  mov     r8, r14
0x180027755  lea     rdx, aRegutilErrorWh_5; "RegUtil: Error when attempting to creat"...
0x18002775c  lea     ecx, [r9+2]; unsigned __int8
0x180027760  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027765  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18002776a  mov     rcx, rax
0x18002776d  mov     eax, [rax]
0x18002776f  cmp     eax, 5
0x180027772  jbe     short loc_1800277F1
0x180027774  mov     rdx, [rcx+18h]
0x180027778  mov     r8, 400000000000h
0x180027782  mov     rax, [rcx+10h]
0x180027786  test    r8, rax
0x180027789  jz      short loc_1800277F1
0x18002778b  mov     rax, rdx
0x18002778e  and     rax, r8
0x180027791  cmp     rax, rdx
0x180027794  jnz     short loc_1800277F1
0x180027796  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18002779d  mov     [rbp+4Fh+arg_20], ebx
0x1800277a0  mov     [rbp+4Fh+var_60], rax
0x1800277a4  lea     rdx, word_18008945A
0x1800277ab  lea     rax, [rbp+4Fh+arg_20]
0x1800277af  mov     [rbp+4Fh+arg_0], 0
0x1800277b7  mov     [rsp+0B0h+lpdwDisposition], rax
0x1800277bc  lea     rax, [rbp+4Fh+arg_0]
0x1800277c0  mov     [rsp+0B0h+phkResult], rax
0x1800277c5  lea     rax, [rbp+4Fh+arg_18]
0x1800277c9  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x1800277ce  lea     rax, [rbp+4Fh+var_60]
0x1800277d2  mov     qword ptr [rsp+0B0h+samDesired], rax
0x1800277d7  lea     rax, [rbp+4Fh+var_58]
0x1800277db  mov     qword ptr [rsp+0B0h+dwOptions], rax
0x1800277e0  mov     [rbp+4Fh+arg_18], r14
0x1800277e4  mov     [rbp+4Fh+var_58], 1000000h
0x1800277ec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800277f1  mov     eax, ebx
0x1800277f3  add     rsp, 90h
0x1800277fa  pop     r14
0x1800277fc  pop     rdi
0x1800277fd  pop     rsi
0x1800277fe  pop     rbx
0x1800277ff  pop     rbp
0x180027800  retn
```
