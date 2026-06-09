# WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180027c3c`
- end: `0x180027df0`
- name: `?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z`
- size: `436`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800214a0`
- `0x180029260`
- `0x1800575c8`

## callees

- `0x180002150`
- `0x180016c9c`
- `0x18002543c`
- `0x180027c3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027c8d`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027c8d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027dd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027dd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ce2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d06`

## string_xrefs

- `0x180027d1e`: `RegUtil: Error when attempting to delete registry value. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelValue(__int64 a1, const WCHAR *a2, const WCHAR *a3, signed int a4)
{
  REGSAM v6; // r9d
  LSTATUS v7; // eax
  signed int v8; // ebx
  const struct _tlgProvider_t *v9; // rcx
  int v10; // r9d
  PHKEY phkResult; // [rsp+28h] [rbp-39h]
  const WCHAR *v13; // [rsp+58h] [rbp-9h] BYREF
  const WCHAR *v14; // [rsp+60h] [rbp-1h] BYREF
  unsigned __int16 *v15; // [rsp+68h] [rbp+7h] BYREF
  __int64 v16; // [rsp+70h] [rbp+Fh] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+67h] BYREF
  signed int v19; // [rsp+E0h] [rbp+7Fh] BYREF

  v19 = a4;
  hKey = 0;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  v6 = 2;
  if ( dword_180098D54 )
    v6 = 258;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v6, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 <= 0 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v8 = 0;
  v7 = RegDeleteValueW(hKey, a3);
  if ( v7 )
  {
    if ( v7 > 0 )
    {
LABEL_10:
      v8 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_11;
    }
    v8 = v7;
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 < 0 )
  {
    LODWORD(phkResult) = v8;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to delete registry value. Sub key: [%s] Value name: [%s]. hr=0x%08X",
      a2,
      a3,
      phkResult);
    v9 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 5u
      && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
    {
      v19 = v8;
      v15 = &gc_pszVersionString;
      v13 = a3;
      v14 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&word_180089386,
        0,
        v10,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v19);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027c3c  mov     rax, rsp
0x180027c3f  mov     [rax+10h], rbx
0x180027c43  mov     [rax+20h], r9d
0x180027c47  mov     [rax+8], rcx
0x180027c4b  push    rbp
0x180027c4c  push    rsi
0x180027c4d  push    rdi
0x180027c4e  lea     rbp, [rax-5Fh]
0x180027c52  sub     rsp, 0A0h
0x180027c59  cmp     cs:dword_180098D58, 0
0x180027c60  mov     rdi, r8
0x180027c63  mov     rsi, rdx
0x180027c66  mov     [rbp+57h+hKey], 0
0x180027c6e  jnz     short loc_180027CB6
0x180027c70  xorps   xmm0, xmm0
0x180027c73  mov     cs:dword_180098D54, 0
0x180027c7d  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180027c81  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180027c85  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180027c89  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180027c8d  call    cs:__imp_GetNativeSystemInfo
0x180027c93  mov     eax, 6
0x180027c98  lea     ecx, [rax-5]
0x180027c9b  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180027c9f  jz      short loc_180027CAA
0x180027ca1  lea     eax, [rcx+8]
0x180027ca4  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180027ca8  jnz     short loc_180027CB0
0x180027caa  mov     cs:dword_180098D54, ecx
0x180027cb0  mov     cs:dword_180098D58, ecx
0x180027cb6  cmp     cs:dword_180098D54, 0
0x180027cbd  mov     eax, 102h
0x180027cc2  mov     r9d, 2
0x180027cc8  cmovnz  r9d, eax; samDesired
0x180027ccc  lea     rax, [rbp+57h+hKey]
0x180027cd0  xor     r8d, r8d; ulOptions
0x180027cd3  mov     rdx, rsi; lpSubKey
0x180027cd6  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180027cdb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ce2  call    cs:__imp_RegOpenKeyExW
0x180027ce8  mov     ebx, eax
0x180027cea  test    eax, eax
0x180027cec  jz      loc_180027DCC
0x180027cf2  jle     short loc_180027CFD
0x180027cf4  movzx   ebx, ax
0x180027cf7  or      ebx, 80070000h
0x180027cfd  mov     rcx, [rbp+57h+hKey]; hKey
0x180027d01  test    rcx, rcx
0x180027d04  jz      short loc_180027D0C
0x180027d06  call    cs:__imp_RegCloseKey
0x180027d0c  test    ebx, ebx
0x180027d0e  jns     loc_180027DB7
0x180027d14  mov     r9, rdi
0x180027d17  mov     dword ptr [rsp+0B0h+phkResult], ebx
0x180027d1b  mov     r8, rsi
0x180027d1e  lea     rdx, aRegutilErrorWh; "RegUtil: Error when attempting to delet"...
0x180027d25  mov     ecx, 2; unsigned __int8
0x180027d2a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027d2f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180027d34  mov     rcx, rax
0x180027d37  mov     eax, [rax]
0x180027d39  cmp     eax, 5
0x180027d3c  jbe     short loc_180027DB7
0x180027d3e  mov     rdx, [rcx+18h]
0x180027d42  mov     r8, 400000000000h
0x180027d4c  mov     rax, [rcx+10h]
0x180027d50  test    r8, rax
0x180027d53  jz      short loc_180027DB7
0x180027d55  mov     rax, rdx
0x180027d58  and     rax, r8
0x180027d5b  cmp     rax, rdx
0x180027d5e  jnz     short loc_180027DB7
0x180027d60  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180027d67  mov     [rbp+57h+arg_18], ebx
0x180027d6a  mov     [rbp+57h+var_50], rax
0x180027d6e  lea     rdx, word_180089386
0x180027d75  lea     rax, [rbp+57h+arg_18]
0x180027d79  mov     [rbp+57h+var_60], rdi
0x180027d7d  mov     [rsp+40h], rax
0x180027d82  lea     rax, [rbp+57h+var_60]
0x180027d86  mov     [rsp+0B0h+var_78], rax
0x180027d8b  lea     rax, [rbp+57h+var_58]
0x180027d8f  mov     [rsp+0B0h+var_80], rax
0x180027d94  lea     rax, [rbp+57h+var_50]
0x180027d98  mov     [rsp+0B0h+var_88], rax
0x180027d9d  lea     rax, [rbp+57h+var_48]
0x180027da1  mov     [rsp+0B0h+phkResult], rax
0x180027da6  mov     [rbp+57h+var_58], rsi
0x180027daa  mov     [rbp+57h+var_48], 1000000h
0x180027db2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180027db7  mov     eax, ebx
0x180027db9  mov     rbx, [rsp+0B0h+arg_8]
0x180027dc1  add     rsp, 0A0h
0x180027dc8  pop     rdi
0x180027dc9  pop     rsi
0x180027dca  pop     rbp
0x180027dcb  retn
0x180027dcc  mov     rcx, [rbp+57h+hKey]; hKey
0x180027dd0  mov     rdx, rdi; lpValueName
0x180027dd3  xor     ebx, ebx
0x180027dd5  call    cs:__imp_RegDeleteValueW
0x180027ddb  test    eax, eax
0x180027ddd  jz      loc_180027CFD
0x180027de3  jg      loc_180027CF4
0x180027de9  mov     ebx, eax
0x180027deb  jmp     loc_180027CFD
```
