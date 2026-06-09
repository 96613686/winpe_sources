# WaasMedic::RegDelAllValuesInKey(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180027808`
- end: `0x180027a79`
- name: `?RegDelAllValuesInKey@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z`
- size: `625`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180021060`

## callees

- `0x1800023b0`
- `0x180003bb0`
- `0x180016c9c`
- `0x18002543c`
- `0x180027808`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027873`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180027873`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800279e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027a3e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800279e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027a3e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027a08`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027a08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800278c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800278c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278ed`

## string_xrefs

- `0x1800278fe`: `RegUtil: Error when attempting to delete all values under registry key. Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelAllValuesInKey(__int64 a1, const WCHAR *a2)
{
  REGSAM v3; // ebx
  LSTATUS v4; // eax
  int v5; // ebx
  unsigned int v6; // edi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  DWORD v10; // edi
  DWORD v11; // eax
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v15; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF

  cchValueName = 260;
  hKey = 0;
  v3 = 131097;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  if ( dword_180098D54 )
    v3 = 131353;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v3, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_11;
  }
  v10 = 0;
  if ( RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, 0, 0) )
    goto LABEL_11;
  do
  {
    if ( v5 )
      break;
    cchValueName = 260;
    v5 = RegDeleteValueW(hKey, ValueName);
    v11 = v10 + 1;
    if ( !v5 )
      v11 = v10;
    v10 = v11;
  }
  while ( !RegEnumValueW(hKey, v11, ValueName, &cchValueName, 0, 0, 0, 0) );
  v6 = 0;
  if ( v5 != 234 && v5 != 259 )
  {
    if ( v5 > 0 )
    {
      v6 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_12;
    }
LABEL_11:
    v6 = v5;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (v6 & 0x80000000) != 0 )
  {
    LogLevelW(
      2u,
      L"RegUtil: Error when attempting to delete all values under registry key. Sub key: [%s]. hr=0x%08X",
      a2,
      v6);
    v7 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v7 > 5u
      && (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v7 + 3) & 0x400000000000LL) == *((_QWORD *)v7 + 3) )
    {
      v14 = v6;
      v16 = &gc_pszVersionString;
      v15 = a2;
      v17 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)&byte_18008925F,
        0,
        v8,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180027808  mov     [rsp-8+arg_0], rbx
0x18002780d  mov     [rsp-8+arg_10], rsi
0x180027812  push    rbp
0x180027813  push    rdi
0x180027814  push    r14
0x180027816  lea     rbp, [rsp-1C0h]
0x18002781e  sub     rsp, 2C0h
0x180027825  mov     rax, cs:__security_cookie
0x18002782c  xor     rax, rsp
0x18002782f  mov     [rbp+1D0h+var_20], rax
0x180027836  xor     r14d, r14d
0x180027839  mov     [rsp+2D0h+cchValueName], 104h
0x180027841  cmp     cs:dword_180098D58, r14d
0x180027848  mov     rsi, rdx
0x18002784b  mov     [rsp+2D0h+hKey], r14
0x180027850  mov     ebx, 20019h
0x180027855  jnz     short loc_18002789D
0x180027857  xorps   xmm0, xmm0
0x18002785a  mov     cs:dword_180098D54, r14d
0x180027861  lea     rcx, [rsp+2D0h+SystemInfo]; lpSystemInfo
0x180027866  movups  xmmword ptr [rsp+2D0h+SystemInfo], xmm0
0x18002786b  movups  xmmword ptr [rbp+1D0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002786f  movups  xmmword ptr [rbp+1D0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180027873  call    cs:__imp_GetNativeSystemInfo
0x180027879  lea     eax, [r14+6]
0x18002787d  lea     ecx, [rax-5]
0x180027880  cmp     ax, word ptr [rsp+2D0h+SystemInfo]
0x180027885  jz      short loc_180027891
0x180027887  lea     eax, [rcx+8]
0x18002788a  cmp     ax, word ptr [rsp+2D0h+SystemInfo]
0x18002788f  jnz     short loc_180027897
0x180027891  mov     cs:dword_180098D54, ecx
0x180027897  mov     cs:dword_180098D58, ecx
0x18002789d  cmp     cs:dword_180098D54, r14d
0x1800278a4  mov     eax, 20119h
0x1800278a9  cmovnz  ebx, eax
0x1800278ac  lea     rax, [rsp+2D0h+hKey]
0x1800278b1  mov     r9d, ebx; samDesired
0x1800278b4  xor     r8d, r8d; ulOptions
0x1800278b7  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800278bc  mov     rdx, rsi; lpSubKey
0x1800278bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800278c6  call    cs:__imp_RegOpenKeyExW
0x1800278cc  mov     ebx, eax
0x1800278ce  test    eax, eax
0x1800278d0  jz      loc_1800279BE
0x1800278d6  jle     short loc_1800278E1
0x1800278d8  movzx   ebx, ax
0x1800278db  or      ebx, 80070000h
0x1800278e1  mov     edi, ebx
0x1800278e3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800278e8  test    rcx, rcx
0x1800278eb  jz      short loc_1800278F3
0x1800278ed  call    cs:__imp_RegCloseKey
0x1800278f3  test    edi, edi
0x1800278f5  jns     loc_180027995
0x1800278fb  mov     r9d, edi
0x1800278fe  lea     rdx, aRegutilErrorWh_3; "RegUtil: Error when attempting to delet"...
0x180027905  mov     r8, rsi
0x180027908  mov     ecx, 2; unsigned __int8
0x18002790d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027912  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180027917  mov     ecx, [rax]
0x180027919  cmp     ecx, 5
0x18002791c  jbe     short loc_180027995
0x18002791e  mov     rdx, [rax+18h]
0x180027922  mov     r8, 400000000000h
0x18002792c  mov     rcx, [rax+10h]
0x180027930  test    r8, rcx
0x180027933  jz      short loc_180027995
0x180027935  mov     rcx, rdx
0x180027938  and     rcx, r8
0x18002793b  cmp     rcx, rdx
0x18002793e  jnz     short loc_180027995
0x180027940  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180027947  mov     [rsp+2D0h+var_280], edi
0x18002794b  mov     [rsp+2D0h+var_270], rcx
0x180027950  lea     rdx, byte_18008925F
0x180027957  lea     rcx, [rsp+2D0h+var_280]
0x18002795c  mov     [rsp+2D0h+var_278], rsi
0x180027961  mov     [rsp+2D0h+lpcbData], rcx
0x180027966  lea     rcx, [rsp+2D0h+var_278]
0x18002796b  mov     [rsp+2D0h+lpData], rcx
0x180027970  lea     rcx, [rsp+2D0h+var_270]
0x180027975  mov     [rsp+2D0h+lpType], rcx
0x18002797a  lea     rcx, [rsp+2D0h+var_268]
0x18002797f  mov     [rsp+2D0h+phkResult], rcx
0x180027984  mov     rcx, rax
0x180027987  mov     [rsp+2D0h+var_268], 1000000h
0x180027990  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180027995  mov     eax, edi
0x180027997  mov     rcx, [rbp+1D0h+var_20]
0x18002799e  xor     rcx, rsp; StackCookie
0x1800279a1  call    __security_check_cookie
0x1800279a6  lea     r11, [rsp+2D0h+var_10]
0x1800279ae  mov     rbx, [r11+20h]
0x1800279b2  mov     rsi, [r11+30h]
0x1800279b6  mov     rsp, r11
0x1800279b9  pop     r14
0x1800279bb  pop     rdi
0x1800279bc  pop     rbp
0x1800279bd  retn
0x1800279be  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800279c3  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x1800279c8  mov     [rsp+2D0h+lpcbData], r14; lpcbData
0x1800279cd  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x1800279d1  mov     [rsp+2D0h+lpData], r14; lpData
0x1800279d6  xor     edx, edx; dwIndex
0x1800279d8  mov     [rsp+2D0h+lpType], r14; lpType
0x1800279dd  mov     edi, r14d
0x1800279e0  mov     [rsp+2D0h+phkResult], r14; lpReserved
0x1800279e5  call    cs:__imp_RegEnumValueW
0x1800279eb  test    eax, eax
0x1800279ed  jnz     loc_1800278E1
0x1800279f3  test    ebx, ebx
0x1800279f5  jnz     short loc_180027A48
0x1800279f7  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800279fc  lea     rdx, [rbp+1D0h+ValueName]; lpValueName
0x180027a00  mov     [rsp+2D0h+cchValueName], 104h
0x180027a08  call    cs:__imp_RegDeleteValueW
0x180027a0e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180027a13  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x180027a18  mov     ebx, eax
0x180027a1a  mov     [rsp+2D0h+lpcbData], r14; lpcbData
0x180027a1f  lea     eax, [rdi+1]
0x180027a22  mov     [rsp+2D0h+lpData], r14; lpData
0x180027a27  test    ebx, ebx
0x180027a29  mov     [rsp+2D0h+lpType], r14; lpType
0x180027a2e  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x180027a32  mov     [rsp+2D0h+phkResult], r14; lpReserved
0x180027a37  cmovz   eax, edi
0x180027a3a  mov     edx, eax; dwIndex
0x180027a3c  mov     edi, eax
0x180027a3e  call    cs:__imp_RegEnumValueW
0x180027a44  test    eax, eax
0x180027a46  jz      short loc_1800279F3
0x180027a48  mov     edi, r14d
0x180027a4b  cmp     ebx, 0EAh
0x180027a51  jz      loc_1800278E3
0x180027a57  cmp     ebx, 103h
0x180027a5d  jz      loc_1800278E3
0x180027a63  test    ebx, ebx
0x180027a65  jle     loc_1800278E1
0x180027a6b  movzx   edi, bx
0x180027a6e  or      edi, 80070000h
0x180027a74  jmp     loc_1800278E3
```
