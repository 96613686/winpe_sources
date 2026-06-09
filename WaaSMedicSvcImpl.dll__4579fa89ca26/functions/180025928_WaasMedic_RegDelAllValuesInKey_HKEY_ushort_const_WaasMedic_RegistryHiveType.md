# WaasMedic::RegDelAllValuesInKey(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)

- ea: `0x180025928`
- end: `0x180025b9a`
- name: `?RegDelAllValuesInKey@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z`
- size: `626`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum WaasMedic::RegistryHiveType)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180022d30`

## callees

- `0x18000263c`
- `0x1800050a0`
- `0x18000d04c`
- `0x180025928`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025993`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180025993`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025b29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025b29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800259e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a0d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025b06`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025b5f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025b06`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025b5f`

## string_xrefs

- `0x180025a1e`: `RegUtil: Error when attempting to delete all values under registry key. Sub key: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegDelAllValuesInKey(__int64 a1, const WCHAR *a2)
{
  REGSAM v3; // ebx
  LSTATUS v4; // eax
  int v5; // ebx
  unsigned int v6; // edi
  __int64 v7; // rcx
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
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  if ( dword_1800A55B0 )
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
    v7 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v14 = v6;
      v16 = &gc_pszVersionString;
      v15 = a2;
      v17 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)word_180092D72,
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
0x180025928  mov     [rsp-8+arg_0], rbx
0x18002592d  mov     [rsp-8+arg_10], rsi
0x180025932  push    rbp
0x180025933  push    rdi
0x180025934  push    r14
0x180025936  lea     rbp, [rsp-1C0h]
0x18002593e  sub     rsp, 2C0h
0x180025945  mov     rax, cs:__security_cookie
0x18002594c  xor     rax, rsp
0x18002594f  mov     [rbp+1D0h+var_20], rax
0x180025956  xor     r14d, r14d
0x180025959  mov     [rsp+2D0h+cchValueName], 104h
0x180025961  cmp     cs:dword_1800A55AC, r14d
0x180025968  mov     rsi, rdx
0x18002596b  mov     [rsp+2D0h+hKey], r14
0x180025970  mov     ebx, 20019h
0x180025975  jnz     short loc_1800259BD
0x180025977  xorps   xmm0, xmm0
0x18002597a  mov     cs:dword_1800A55B0, r14d
0x180025981  lea     rcx, [rsp+2D0h+SystemInfo]; lpSystemInfo
0x180025986  movups  xmmword ptr [rsp+2D0h+SystemInfo], xmm0
0x18002598b  movups  xmmword ptr [rbp+1D0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002598f  movups  xmmword ptr [rbp+1D0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180025993  call    cs:__imp_GetNativeSystemInfo
0x180025999  lea     eax, [r14+6]
0x18002599d  lea     ecx, [rax-5]
0x1800259a0  cmp     ax, word ptr [rsp+2D0h+SystemInfo]
0x1800259a5  jz      short loc_1800259B1
0x1800259a7  lea     eax, [rcx+8]
0x1800259aa  cmp     ax, word ptr [rsp+2D0h+SystemInfo]
0x1800259af  jnz     short loc_1800259B7
0x1800259b1  mov     cs:dword_1800A55B0, ecx
0x1800259b7  mov     cs:dword_1800A55AC, ecx
0x1800259bd  cmp     cs:dword_1800A55B0, r14d
0x1800259c4  mov     eax, 20119h
0x1800259c9  cmovnz  ebx, eax
0x1800259cc  lea     rax, [rsp+2D0h+hKey]
0x1800259d1  mov     r9d, ebx; samDesired
0x1800259d4  xor     r8d, r8d; ulOptions
0x1800259d7  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800259dc  mov     rdx, rsi; lpSubKey
0x1800259df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800259e6  call    cs:__imp_RegOpenKeyExW
0x1800259ec  mov     ebx, eax
0x1800259ee  test    eax, eax
0x1800259f0  jz      loc_180025ADF
0x1800259f6  jle     short loc_180025A01
0x1800259f8  movzx   ebx, ax
0x1800259fb  or      ebx, 80070000h
0x180025a01  mov     edi, ebx
0x180025a03  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180025a08  test    rcx, rcx
0x180025a0b  jz      short loc_180025A13
0x180025a0d  call    cs:__imp_RegCloseKey
0x180025a13  test    edi, edi
0x180025a15  jns     loc_180025AB6
0x180025a1b  mov     r9d, edi
0x180025a1e  lea     rdx, aRegutilErrorWh_3; "RegUtil: Error when attempting to delet"...
0x180025a25  mov     r8, rsi
0x180025a28  mov     ecx, 2; unsigned __int8
0x180025a2d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025a32  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180025a37  mov     rcx, [rax+8]
0x180025a3b  mov     eax, [rcx]
0x180025a3d  cmp     eax, 5
0x180025a40  jbe     short loc_180025AB6
0x180025a42  mov     rdx, [rcx+18h]
0x180025a46  mov     r8, 400000000000h
0x180025a50  mov     rax, [rcx+10h]
0x180025a54  test    r8, rax
0x180025a57  jz      short loc_180025AB6
0x180025a59  mov     rax, rdx
0x180025a5c  and     rax, r8
0x180025a5f  cmp     rax, rdx
0x180025a62  jnz     short loc_180025AB6
0x180025a64  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180025a6b  mov     [rsp+2D0h+var_280], edi
0x180025a6f  mov     [rsp+2D0h+var_270], rax
0x180025a74  lea     rdx, word_180092D72
0x180025a7b  lea     rax, [rsp+2D0h+var_280]
0x180025a80  mov     [rsp+2D0h+var_278], rsi
0x180025a85  mov     [rsp+2D0h+lpcbData], rax
0x180025a8a  lea     rax, [rsp+2D0h+var_278]
0x180025a8f  mov     [rsp+2D0h+lpData], rax
0x180025a94  lea     rax, [rsp+2D0h+var_270]
0x180025a99  mov     [rsp+2D0h+lpType], rax
0x180025a9e  lea     rax, [rsp+2D0h+var_268]
0x180025aa3  mov     [rsp+2D0h+phkResult], rax
0x180025aa8  mov     [rsp+2D0h+var_268], 1000000h
0x180025ab1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180025ab6  mov     eax, edi
0x180025ab8  mov     rcx, [rbp+1D0h+var_20]
0x180025abf  xor     rcx, rsp; StackCookie
0x180025ac2  call    __security_check_cookie
0x180025ac7  lea     r11, [rsp+2D0h+var_10]
0x180025acf  mov     rbx, [r11+20h]
0x180025ad3  mov     rsi, [r11+30h]
0x180025ad7  mov     rsp, r11
0x180025ada  pop     r14
0x180025adc  pop     rdi
0x180025add  pop     rbp
0x180025ade  retn
0x180025adf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180025ae4  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x180025ae9  mov     [rsp+2D0h+lpcbData], r14; lpcbData
0x180025aee  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x180025af2  mov     [rsp+2D0h+lpData], r14; lpData
0x180025af7  xor     edx, edx; dwIndex
0x180025af9  mov     [rsp+2D0h+lpType], r14; lpType
0x180025afe  mov     edi, r14d
0x180025b01  mov     [rsp+2D0h+phkResult], r14; lpReserved
0x180025b06  call    cs:__imp_RegEnumValueW
0x180025b0c  test    eax, eax
0x180025b0e  jnz     loc_180025A01
0x180025b14  test    ebx, ebx
0x180025b16  jnz     short loc_180025B69
0x180025b18  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180025b1d  lea     rdx, [rbp+1D0h+ValueName]; lpValueName
0x180025b21  mov     [rsp+2D0h+cchValueName], 104h
0x180025b29  call    cs:__imp_RegDeleteValueW
0x180025b2f  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180025b34  lea     r9, [rsp+2D0h+cchValueName]; lpcchValueName
0x180025b39  mov     ebx, eax
0x180025b3b  mov     [rsp+2D0h+lpcbData], r14; lpcbData
0x180025b40  lea     eax, [rdi+1]
0x180025b43  mov     [rsp+2D0h+lpData], r14; lpData
0x180025b48  test    ebx, ebx
0x180025b4a  mov     [rsp+2D0h+lpType], r14; lpType
0x180025b4f  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x180025b53  mov     [rsp+2D0h+phkResult], r14; lpReserved
0x180025b58  cmovz   eax, edi
0x180025b5b  mov     edx, eax; dwIndex
0x180025b5d  mov     edi, eax
0x180025b5f  call    cs:__imp_RegEnumValueW
0x180025b65  test    eax, eax
0x180025b67  jz      short loc_180025B14
0x180025b69  mov     edi, r14d
0x180025b6c  cmp     ebx, 0EAh
0x180025b72  jz      loc_180025A03
0x180025b78  cmp     ebx, 103h
0x180025b7e  jz      loc_180025A03
0x180025b84  test    ebx, ebx
0x180025b86  jle     loc_180025A01
0x180025b8c  movzx   edi, bx
0x180025b8f  or      edi, 80070000h
0x180025b95  jmp     loc_180025A03
```
