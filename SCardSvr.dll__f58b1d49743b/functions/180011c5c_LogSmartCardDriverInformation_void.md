# LogSmartCardDriverInformation(void)

- ea: `0x180011c5c`
- end: `0x180012188`
- name: `?LogSmartCardDriverInformation@@YAXXZ`
- size: `1324`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f50`

## callees

- `0x180001008`
- `0x180001158`
- `0x1800012a8`
- `0x18000139c`
- `0x180011c5c`
- `0x18001a15c`
- `0x180023282`
- `0x1800326a2`
- `0x1800326d0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180011e7f`
- `msvcrt!wcsrchr` at `0x180011e7f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cc9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011da4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001201f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011da4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001201f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011dea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001205f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011dea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001205f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011fd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011d5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011fd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e6d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011edd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011e6d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011edd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f2a`

## string_xrefs

- `0x180011fc9`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void LogSmartCardDriverInformation(void)
{
  DWORD i; // edi
  wchar_t *v1; // rax
  wchar_t *v2; // rbx
  __int64 v3; // r9
  DWORD j; // ebx
  __int64 v5; // rax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v7; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD v10; // [rsp+78h] [rbp-88h] BYREF
  DWORD v11; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v13; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v14; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v15; // [rsp+98h] [rbp-68h] BYREF
  WCHAR *v16; // [rsp+A0h] [rbp-60h] BYREF
  int v17; // [rsp+A8h] [rbp-58h] BYREF
  char v18; // [rsp+ACh] [rbp-54h]
  GUID ActivityId; // [rsp+B0h] [rbp-50h] BYREF
  DWORD *v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]
  DWORD *v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  wchar_t Name[256]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t pvData[264]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v26[528]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v27[528]; // [rsp+730h] [rbp+630h] BYREF

  cchName = 0;
  cSubKeys = 0;
  v7 = 0;
  v17 = 0;
  v18 = 0;
  if ( (unsigned int)dword_18004B048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v17 = 1;
  if ( (unsigned int)dword_18004B048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18004B048,
      (__int64)byte_180042951);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards", 0, 0x20019u, &hKey) )
  {
    RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( cSubKeys )
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 255;
        if ( !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0)
          && wcscmp_0(L"Identity Device (Microsoft Generic Profile)", Name)
          && wcscmp_0(L"Identity Device (NIST SP 800-73 [PIV])", Name) )
        {
          memset_0(pvData, 0, 0x208u);
          pcbData = 520;
          RegGetValueW(hKey, Name, L"80000001", 2u, 0, pvData, &pcbData);
          v1 = wcsrchr(pvData, 0x5Cu);
          v2 = v1;
          if ( v1 && *v1 )
            v2 = v1 + 1;
          memset_0(v27, 0, 0x208u);
          v10 = 520;
          RegGetValueW(hKey, Name, L"Crypto Provider", 2u, 0, v27, &v10);
          memset_0(v26, 0, 0x208u);
          v11 = 520;
          RegGetValueW(hKey, Name, L"Smart Card Key Storage Provider", 2u, 0, v26, &v11);
          if ( (unsigned int)dword_18004B048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
          {
            v15 = v2;
            v13 = v26;
            v14 = v27;
            v16 = Name;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (__int64)&dword_18004B048,
              (__int64)&byte_1800429BF,
              (__int64)&ActivityId,
              v3,
              &v16,
              &v15,
              &v14,
              &v13);
          }
        }
      }
    }
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers", 0, 0x20019u, &hKey) )
  {
    RegQueryInfoKeyW(hKey, 0, 0, 0, &v7, 0, 0, 0, 0, 0, 0, 0);
    if ( v7 )
    {
      for ( j = 0; j < v7; ++j )
      {
        cchName = 255;
        if ( !RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0)
          && (unsigned int)dword_18004B048 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
        {
          v5 = -1;
          do
            ++v5;
          while ( Name[v5] );
          v21 = (unsigned int)(2 * v5 + 2);
          v20 = (DWORD *)Name;
          tlgWriteTransfer_EventWriteTransfer(&dword_18004B048, &dword_180042A24);
        }
      }
    }
  }
  v17 = 2;
  if ( (unsigned int)dword_18004B048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
  {
    v11 = v7;
    v23 = 4;
    v10 = cSubKeys - 2;
    v21 = 4;
    v22 = &v11;
    v20 = &v10;
    tlgWriteTransfer_EventWriteTransfer(&dword_18004B048, &byte_180042977);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v17);
}

```

## disassembly

```asm
0x180011c5c  push    rbp
0x180011c5e  push    rbx
0x180011c5f  push    rsi
0x180011c60  push    rdi
0x180011c61  push    r12
0x180011c63  push    r14
0x180011c65  lea     rbp, [rsp-858h]
0x180011c6d  sub     rsp, 958h
0x180011c74  mov     rax, cs:__security_cookie
0x180011c7b  xor     rax, rsp
0x180011c7e  mov     [rbp+880h+var_40], rax
0x180011c85  mov     eax, cs:dword_18004B048
0x180011c8b  lea     r14, dword_18004B048
0x180011c92  xor     esi, esi
0x180011c94  mov     [rsp+980h+cchName], esi
0x180011c98  mov     [rsp+980h+cSubKeys], esi
0x180011c9c  mov     [rsp+980h+var_91C], esi
0x180011ca0  mov     [rbp+880h+var_8D8], esi
0x180011ca3  mov     [rbp+880h+var_8D4], sil
0x180011ca7  cmp     eax, 5
0x180011caa  jbe     short loc_180011CD1
0x180011cac  mov     rdx, 400000000000h
0x180011cb6  mov     rcx, r14
0x180011cb9  call    _tlgKeywordOn
0x180011cbe  test    al, al
0x180011cc0  jz      short loc_180011CD1
0x180011cc2  lea     rdx, [rbp+880h+ActivityId]; ActivityId
0x180011cc6  lea     ecx, [rsi+3]; ControlCode
0x180011cc9  call    cs:__imp_EventActivityIdControl
0x180011ccf  jmp     short loc_180011CD8
0x180011cd1  xorps   xmm0, xmm0
0x180011cd4  movups  xmmword ptr [rbp+880h+ActivityId.Data1], xmm0
0x180011cd8  mov     eax, cs:dword_18004B048
0x180011cde  mov     [rbp+880h+var_8D8], 1
0x180011ce5  cmp     eax, 5
0x180011ce8  jbe     short loc_180011D36
0x180011cea  mov     rdx, 400000000000h
0x180011cf4  mov     rcx, r14
0x180011cf7  call    _tlgKeywordOn
0x180011cfc  test    al, al
0x180011cfe  jz      short loc_180011D36
0x180011d00  cmp     [rbp+880h+var_8D4], sil
0x180011d04  jz      short loc_180011D20
0x180011d06  cmp     [rbp+880h+var_8C0], esi
0x180011d09  jnz     short loc_180011D1A
0x180011d0b  cmp     [rbp+880h+var_8BC], esi
0x180011d0e  jnz     short loc_180011D1A
0x180011d10  cmp     [rbp+880h+var_8B8], esi
0x180011d13  jnz     short loc_180011D1A
0x180011d15  cmp     [rbp+880h+var_8B4], esi
0x180011d18  jz      short loc_180011D20
0x180011d1a  lea     r9, [rbp+880h+var_8C0]
0x180011d1e  jmp     short loc_180011D23
0x180011d20  mov     r9, rsi
0x180011d23  lea     r8, [rbp+880h+ActivityId]
0x180011d27  mov     rcx, r14
0x180011d2a  lea     rdx, byte_180042951
0x180011d31  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180011d36  lea     rax, [rsp+980h+hKey]
0x180011d3b  mov     [rsp+980h+hKey], rsi
0x180011d40  mov     r9d, 20019h; samDesired
0x180011d46  mov     [rsp+980h+phkResult], rax; phkResult
0x180011d4b  xor     r8d, r8d; ulOptions
0x180011d4e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180011d55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011d5c  call    cs:__imp_RegOpenKeyExW
0x180011d62  test    eax, eax
0x180011d64  jnz     loc_180011FB6
0x180011d6a  mov     rcx, [rsp+980h+hKey]; hKey
0x180011d6f  lea     rax, [rsp+980h+cSubKeys]
0x180011d74  mov     [rsp+980h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180011d79  xor     r9d, r9d; lpReserved
0x180011d7c  mov     [rsp+980h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180011d81  xor     r8d, r8d; lpcchClass
0x180011d84  mov     [rsp+980h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180011d89  xor     edx, edx; lpClass
0x180011d8b  mov     [rsp+980h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180011d90  mov     [rsp+980h+lpcValues], rsi; lpcValues
0x180011d95  mov     [rsp+980h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180011d9a  mov     [rsp+980h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180011d9f  mov     [rsp+980h+phkResult], rax; lpcSubKeys
0x180011da4  call    cs:__imp_RegQueryInfoKeyW
0x180011daa  mov     eax, [rsp+980h+cSubKeys]
0x180011dae  test    eax, eax
0x180011db0  jz      loc_180011FB6
0x180011db6  mov     edi, esi
0x180011db8  mov     r12d, 208h
0x180011dbe  mov     rcx, [rsp+980h+hKey]; hKey
0x180011dc3  lea     r9, [rsp+980h+cchName]; lpcchName
0x180011dc8  mov     [rsp+980h+lpcValues], rsi; lpftLastWriteTime
0x180011dcd  lea     r8, [rbp+880h+Name]; lpName
0x180011dd1  mov     [rsp+980h+lpcbMaxClassLen], rsi; lpcchClass
0x180011dd6  mov     edx, edi; dwIndex
0x180011dd8  mov     [rsp+980h+lpcbMaxSubKeyLen], rsi; lpClass
0x180011ddd  mov     [rsp+980h+phkResult], rsi; lpReserved
0x180011de2  mov     [rsp+980h+cchName], 0FFh
0x180011dea  call    cs:__imp_RegEnumKeyExW
0x180011df0  test    eax, eax
0x180011df2  jnz     loc_180011FAA
0x180011df8  lea     rdx, [rbp+880h+Name]; String2
0x180011dfc  lea     rcx, aIdentityDevice; "Identity Device (Microsoft Generic Prof"...
0x180011e03  call    wcscmp_0
0x180011e08  test    eax, eax
0x180011e0a  jz      loc_180011FAA
0x180011e10  lea     rdx, [rbp+880h+Name]; String2
0x180011e14  lea     rcx, aIdentityDevice_0; "Identity Device (NIST SP 800-73 [PIV])"
0x180011e1b  call    wcscmp_0
0x180011e20  test    eax, eax
0x180011e22  jz      loc_180011FAA
0x180011e28  mov     r8, r12; Size
0x180011e2b  lea     rcx, [rbp+880h+pvData]; void *
0x180011e32  xor     edx, edx; Val
0x180011e34  call    memset_0
0x180011e39  mov     rcx, [rsp+980h+hKey]; hkey
0x180011e3e  lea     rax, [rbp+880h+pcbData]
0x180011e42  mov     [rsp+980h+lpcbMaxClassLen], rax; pcbData
0x180011e47  lea     r8, Value; "80000001"
0x180011e4e  lea     rax, [rbp+880h+pvData]
0x180011e55  mov     [rbp+880h+pcbData], r12d
0x180011e59  mov     [rsp+980h+lpcbMaxSubKeyLen], rax; pvData
0x180011e5e  lea     rdx, [rbp+880h+Name]; lpSubKey
0x180011e62  mov     r9d, 2; dwFlags
0x180011e68  mov     [rsp+980h+phkResult], rsi; pdwType
0x180011e6d  call    cs:__imp_RegGetValueW
0x180011e73  mov     edx, 5Ch ; '\'; Ch
0x180011e78  lea     rcx, [rbp+880h+pvData]; Str
0x180011e7f  call    cs:__imp_wcsrchr
0x180011e85  mov     rbx, rax
0x180011e88  test    rax, rax
0x180011e8b  jz      short loc_180011E96
0x180011e8d  cmp     [rax], si
0x180011e90  jz      short loc_180011E96
0x180011e92  add     rbx, 2
0x180011e96  mov     r8, r12; Size
0x180011e99  lea     rcx, [rbp+880h+var_250]; void *
0x180011ea0  xor     edx, edx; Val
0x180011ea2  call    memset_0
0x180011ea7  mov     rcx, [rsp+980h+hKey]; hkey
0x180011eac  lea     rax, [rsp+980h+var_908]
0x180011eb1  mov     [rsp+980h+lpcbMaxClassLen], rax; pcbData
0x180011eb6  lea     r8, aCryptoProvider; "Crypto Provider"
0x180011ebd  lea     rax, [rbp+880h+var_250]
0x180011ec4  mov     [rsp+980h+var_908], r12d
0x180011ec9  mov     [rsp+980h+lpcbMaxSubKeyLen], rax; pvData
0x180011ece  lea     rdx, [rbp+880h+Name]; lpSubKey
0x180011ed2  mov     r9d, 2; dwFlags
0x180011ed8  mov     [rsp+980h+phkResult], rsi; pdwType
0x180011edd  call    cs:__imp_RegGetValueW
0x180011ee3  mov     r8, r12; Size
0x180011ee6  lea     rcx, [rbp+880h+var_460]; void *
0x180011eed  xor     edx, edx; Val
0x180011eef  call    memset_0
0x180011ef4  mov     rcx, [rsp+980h+hKey]; hkey
0x180011ef9  lea     rax, [rsp+980h+var_904]
0x180011efe  mov     [rsp+980h+lpcbMaxClassLen], rax; pcbData
0x180011f03  lea     r8, aSmartCardKeySt; "Smart Card Key Storage Provider"
0x180011f0a  lea     rax, [rbp+880h+var_460]
0x180011f11  mov     [rsp+980h+var_904], r12d
0x180011f16  mov     [rsp+980h+lpcbMaxSubKeyLen], rax; pvData
0x180011f1b  lea     rdx, [rbp+880h+Name]; lpSubKey
0x180011f1f  mov     r9d, 2; dwFlags
0x180011f25  mov     [rsp+980h+phkResult], rsi; pdwType
0x180011f2a  call    cs:__imp_RegGetValueW
0x180011f30  mov     eax, cs:dword_18004B048
0x180011f36  cmp     eax, 5
0x180011f39  jbe     short loc_180011FAA
0x180011f3b  mov     rdx, 400000000000h
0x180011f45  mov     rcx, r14
0x180011f48  call    _tlgKeywordOn
0x180011f4d  test    al, al
0x180011f4f  jz      short loc_180011FAA
0x180011f51  lea     rax, [rbp+880h+var_460]
0x180011f58  mov     [rbp+880h+var_8E8], rbx
0x180011f5c  mov     [rbp+880h+var_8F8], rax
0x180011f60  lea     r8, [rbp+880h+ActivityId]
0x180011f64  lea     rax, [rbp+880h+var_250]
0x180011f6b  mov     rcx, r14
0x180011f6e  mov     [rbp+880h+var_8F0], rax
0x180011f72  lea     rdx, byte_1800429BF
0x180011f79  lea     rax, [rbp+880h+Name]
0x180011f7d  mov     [rbp+880h+var_8E0], rax
0x180011f81  lea     rax, [rbp+880h+var_8F8]
0x180011f85  mov     [rsp+980h+lpcValues], rax
0x180011f8a  lea     rax, [rbp+880h+var_8F0]
0x180011f8e  mov     [rsp+980h+lpcbMaxClassLen], rax
0x180011f93  lea     rax, [rbp+880h+var_8E8]
0x180011f97  mov     [rsp+980h+lpcbMaxSubKeyLen], rax
0x180011f9c  lea     rax, [rbp+880h+var_8E0]
0x180011fa0  mov     [rsp+980h+phkResult], rax
0x180011fa5  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180011faa  inc     edi
0x180011fac  cmp     edi, [rsp+980h+cSubKeys]
0x180011fb0  jb      loc_180011DBE
0x180011fb6  lea     rax, [rsp+980h+hKey]
0x180011fbb  mov     r9d, 20019h; samDesired
0x180011fc1  xor     r8d, r8d; ulOptions
0x180011fc4  mov     [rsp+980h+phkResult], rax; phkResult
0x180011fc9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180011fd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011fd7  call    cs:__imp_RegOpenKeyExW
0x180011fdd  test    eax, eax
0x180011fdf  jnz     loc_1800120E3
0x180011fe5  mov     rcx, [rsp+980h+hKey]; hKey
0x180011fea  lea     rax, [rsp+980h+var_91C]
0x180011fef  mov     [rsp+980h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180011ff4  xor     r9d, r9d; lpReserved
0x180011ff7  mov     [rsp+980h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180011ffc  xor     r8d, r8d; lpcchClass
0x180011fff  mov     [rsp+980h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180012004  xor     edx, edx; lpClass
0x180012006  mov     [rsp+980h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18001200b  mov     [rsp+980h+lpcValues], rsi; lpcValues
0x180012010  mov     [rsp+980h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180012015  mov     [rsp+980h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18001201a  mov     [rsp+980h+phkResult], rax; lpcSubKeys
0x18001201f  call    cs:__imp_RegQueryInfoKeyW
0x180012025  mov     eax, [rsp+980h+var_91C]
0x180012029  test    eax, eax
0x18001202b  jz      loc_1800120E3
0x180012031  mov     ebx, esi
0x180012033  mov     rcx, [rsp+980h+hKey]; hKey
0x180012038  lea     r9, [rsp+980h+cchName]; lpcchName
0x18001203d  mov     [rsp+980h+lpcValues], rsi; lpftLastWriteTime
0x180012042  lea     r8, [rbp+880h+Name]; lpName
0x180012046  mov     [rsp+980h+lpcbMaxClassLen], rsi; lpcchClass
0x18001204b  mov     edx, ebx; dwIndex
0x18001204d  mov     [rsp+980h+lpcbMaxSubKeyLen], rsi; lpClass
0x180012052  mov     [rsp+980h+phkResult], rsi; lpReserved
0x180012057  mov     [rsp+980h+cchName], 0FFh
0x18001205f  call    cs:__imp_RegEnumKeyExW
0x180012065  test    eax, eax
0x180012067  jnz     short loc_1800120D7
0x180012069  mov     eax, cs:dword_18004B048
0x18001206f  cmp     eax, 5
0x180012072  jbe     short loc_1800120D7
0x180012074  mov     rdx, 400000000000h
0x18001207e  mov     rcx, r14
0x180012081  call    _tlgKeywordOn
0x180012086  test    al, al
0x180012088  jz      short loc_1800120D7
0x18001208a  lea     rcx, [rbp+880h+Name]
0x18001208e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012092  inc     rax
0x180012095  cmp     [rcx+rax*2], si
0x180012099  jnz     short loc_180012092
0x18001209b  lea     eax, ds:2[rax*2]
0x1800120a2  mov     dword ptr [rbp+880h+var_888+4], esi
0x1800120a5  mov     dword ptr [rbp+880h+var_888], eax
0x1800120a8  lea     rcx, [rbp+880h+Name]
0x1800120ac  lea     rax, [rbp+880h+var_8B0]
0x1800120b0  mov     [rbp+880h+var_890], rcx
0x1800120b4  mov     [rsp+980h+lpcbMaxSubKeyLen], rax
0x1800120b9  lea     r8, [rbp+880h+ActivityId]
0x1800120bd  xor     r9d, r9d
0x1800120c0  mov     dword ptr [rsp+980h+phkResult], 3
0x1800120c8  lea     rdx, dword_180042A24
0x1800120cf  mov     rcx, r14
0x1800120d2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800120d7  inc     ebx
0x1800120d9  cmp     ebx, [rsp+980h+var_91C]
0x1800120dd  jb      loc_180012033
0x1800120e3  mov     eax, cs:dword_18004B048
0x1800120e9  mov     [rbp+880h+var_8D8], 2
0x1800120f0  cmp     eax, 5
0x1800120f3  jbe     short loc_180012160
0x1800120f5  mov     rdx, 400000000000h
0x1800120ff  mov     rcx, r14
0x180012102  call    _tlgKeywordOn
0x180012107  test    al, al
0x180012109  jz      short loc_180012160
0x18001210b  mov     eax, [rsp+980h+var_91C]
0x18001210f  lea     r8, [rbp+880h+ActivityId]
0x180012113  mov     [rsp+980h+var_904], eax
0x180012117  mov     edx, 4
0x18001211c  mov     eax, [rsp+980h+cSubKeys]
0x180012120  xor     r9d, r9d
0x180012123  add     eax, 0FFFFFFFEh
0x180012126  mov     [rbp+880h+var_878], rdx
0x18001212a  mov     [rsp+980h+var_908], eax
0x18001212e  mov     rcx, r14
0x180012131  lea     rax, [rsp+980h+var_904]
0x180012136  mov     [rbp+880h+var_888], rdx
0x18001213a  mov     [rbp+880h+var_880], rax
0x18001213e  lea     rax, [rsp+980h+var_908]
0x180012143  mov     [rbp+880h+var_890], rax
0x180012147  lea     rax, [rbp+880h+var_8B0]
0x18001214b  mov     [rsp+980h+lpcbMaxSubKeyLen], rax
0x180012150  mov     dword ptr [rsp+980h+phkResult], edx
0x180012154  lea     rdx, byte_180042977
0x18001215b  call    _tlgWriteTransfer_EventWriteTransfer
0x180012160  lea     rcx, [rbp+880h+var_8D8]
0x180012164  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180012169  mov     rcx, [rbp+880h+var_40]
0x180012170  xor     rcx, rsp; StackCookie
0x180012173  call    __security_check_cookie
0x180012178  add     rsp, 958h
0x18001217f  pop     r14
0x180012181  pop     r12
0x180012183  pop     rdi
0x180012184  pop     rsi
  ... truncated ...
```
