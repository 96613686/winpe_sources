# WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180025d60`
- end: `0x180025f05`
- name: `?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z`
- size: `421`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18002271c`
- `0x180023180`
- `0x1800271a4`
- `0x18002d6e0`
- `0x18003a7d0`
- `0x1800693d4`

## callees

- `0x1800023dc`
- `0x18000d04c`
- `0x180025d60`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025dac`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025dac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025eea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025eea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025dfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025dfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e21`

## string_xrefs

- `0x180025e39`: `RegUtil: Error when attempting to delete registry value. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, signed int a4)
{
  REGSAM v7; // r9d
  LSTATUS v8; // eax
  signed int v9; // ebx
  __int64 v10; // rcx
  int v11; // r9d
  PHKEY phkResult; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v15; // [rsp+58h] [rbp-21h] BYREF
  const WCHAR *v16; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp-11h] BYREF
  __int64 v18; // [rsp+70h] [rbp-9h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+78h] [rbp-1h] BYREF
  signed int v20; // [rsp+F8h] [rbp+7Fh] BYREF

  v20 = a4;
  hKey = 0;
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  v7 = 2;
  if ( dword_1800A55B0 )
    v7 = 258;
  v8 = RegOpenKeyExW(a1, a2, 0, v7, &hKey);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 <= 0 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v9 = 0;
  v8 = RegDeleteValueW(hKey, a3);
  if ( v8 )
  {
    if ( v8 > 0 )
    {
LABEL_10:
      v9 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_11;
    }
    v9 = v8;
  }
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 < 0 )
  {
    LODWORD(phkResult) = v9;
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to delete registry value. Sub key: [%s] Value name: [%s]. hr=0x%08X",
      a2,
      a3,
      phkResult);
    v10 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v10 > 5u
      && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      v20 = v9;
      v17 = &gc_pszVersionString;
      v15 = a3;
      v16 = a2;
      v18 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_180092E99,
        0,
        v11,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v20);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025d60  mov     [rsp-8+arg_18], r9d
0x180025d65  push    rbp
0x180025d66  push    rbx
0x180025d67  push    rsi
0x180025d68  push    rdi
0x180025d69  lea     rbp, [rsp-3Fh]
0x180025d6e  sub     rsp, 0B8h
0x180025d75  cmp     cs:dword_1800A55AC, 0
0x180025d7c  mov     rdi, r8
0x180025d7f  mov     rsi, rdx
0x180025d82  mov     [rbp+57h+hKey], 0
0x180025d8a  mov     rbx, rcx
0x180025d8d  jnz     short loc_180025DD5
0x180025d8f  xorps   xmm0, xmm0
0x180025d92  mov     cs:dword_1800A55B0, 0
0x180025d9c  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180025da0  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180025da4  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180025da8  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180025dac  call    cs:__imp_GetNativeSystemInfo
0x180025db2  mov     eax, 6
0x180025db7  lea     ecx, [rax-5]
0x180025dba  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180025dbe  jz      short loc_180025DC9
0x180025dc0  lea     eax, [rcx+8]
0x180025dc3  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x180025dc7  jnz     short loc_180025DCF
0x180025dc9  mov     cs:dword_1800A55B0, ecx
0x180025dcf  mov     cs:dword_1800A55AC, ecx
0x180025dd5  cmp     cs:dword_1800A55B0, 0
0x180025ddc  mov     eax, 102h
0x180025de1  mov     r9d, 2
0x180025de7  cmovnz  r9d, eax; samDesired
0x180025deb  lea     rax, [rbp+57h+hKey]
0x180025def  xor     r8d, r8d; ulOptions
0x180025df2  mov     rdx, rsi; lpSubKey
0x180025df5  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180025dfa  mov     rcx, rbx; hKey
0x180025dfd  call    cs:__imp_RegOpenKeyExW
0x180025e03  mov     ebx, eax
0x180025e05  test    eax, eax
0x180025e07  jz      loc_180025EE1
0x180025e0d  jle     short loc_180025E18
0x180025e0f  movzx   ebx, ax
0x180025e12  or      ebx, 80070000h
0x180025e18  mov     rcx, [rbp+57h+hKey]; hKey
0x180025e1c  test    rcx, rcx
0x180025e1f  jz      short loc_180025E27
0x180025e21  call    cs:__imp_RegCloseKey
0x180025e27  test    ebx, ebx
0x180025e29  jns     loc_180025ED3
0x180025e2f  mov     r9, rdi
0x180025e32  mov     dword ptr [rsp+0D0h+phkResult], ebx
0x180025e36  mov     r8, rsi
0x180025e39  lea     rdx, aRegutilErrorWh; "RegUtil: Error when attempting to delet"...
0x180025e40  mov     ecx, 2; unsigned __int8
0x180025e45  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025e4a  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180025e4f  mov     rcx, [rax+8]
0x180025e53  mov     eax, [rcx]
0x180025e55  cmp     eax, 5
0x180025e58  jbe     short loc_180025ED3
0x180025e5a  mov     rdx, [rcx+18h]
0x180025e5e  mov     r8, 400000000000h
0x180025e68  mov     rax, [rcx+10h]
0x180025e6c  test    r8, rax
0x180025e6f  jz      short loc_180025ED3
0x180025e71  mov     rax, rdx
0x180025e74  and     rax, r8
0x180025e77  cmp     rax, rdx
0x180025e7a  jnz     short loc_180025ED3
0x180025e7c  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180025e83  mov     [rbp+57h+arg_18], ebx
0x180025e86  mov     [rbp+57h+var_68], rax
0x180025e8a  lea     rdx, byte_180092E99
0x180025e91  lea     rax, [rbp+57h+arg_18]
0x180025e95  mov     [rbp+57h+var_78], rdi
0x180025e99  mov     [rsp+0D0h+var_90], rax
0x180025e9e  lea     rax, [rbp+57h+var_78]
0x180025ea2  mov     [rsp+0D0h+var_98], rax
0x180025ea7  lea     rax, [rbp+57h+var_70]
0x180025eab  mov     [rsp+0D0h+var_A0], rax
0x180025eb0  lea     rax, [rbp+57h+var_68]
0x180025eb4  mov     [rsp+0D0h+var_A8], rax
0x180025eb9  lea     rax, [rbp+57h+var_60]
0x180025ebd  mov     [rsp+0D0h+phkResult], rax
0x180025ec2  mov     [rbp+57h+var_70], rsi
0x180025ec6  mov     [rbp+57h+var_60], 1000000h
0x180025ece  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180025ed3  mov     eax, ebx
0x180025ed5  add     rsp, 0B8h
0x180025edc  pop     rdi
0x180025edd  pop     rsi
0x180025ede  pop     rbx
0x180025edf  pop     rbp
0x180025ee0  retn
0x180025ee1  mov     rcx, [rbp+57h+hKey]; hKey
0x180025ee5  mov     rdx, rdi; lpValueName
0x180025ee8  xor     ebx, ebx
0x180025eea  call    cs:__imp_RegDeleteValueW
0x180025ef0  test    eax, eax
0x180025ef2  jz      loc_180025E18
0x180025ef8  jg      loc_180025E0F
0x180025efe  mov     ebx, eax
0x180025f00  jmp     loc_180025E18
```
