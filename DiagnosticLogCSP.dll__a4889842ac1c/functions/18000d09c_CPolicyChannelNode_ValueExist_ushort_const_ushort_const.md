# CPolicyChannelNode::ValueExist(ushort const *,ushort const *)

- ea: `0x18000d09c`
- end: `0x18000d288`
- name: `?ValueExist@CPolicyChannelNode@@CA_NPEBG0@Z`
- size: `492`
- prototype: `bool __fastcall(LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x1800011a4`
- `0x180001b60`
- `0x180006518`
- `0x18000d09c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000d0fa`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d0fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d1f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d1f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d25a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d25a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1bf`

## pseudocode

```c
char __fastcall CPolicyChannelNode::ValueExist(LPCWSTR lpValueName, const unsigned __int16 *a2)
{
  DWORD v4; // edi
  __int64 v5; // r9
  HKEY v6; // rbx
  const wchar_t *v7; // r8
  __int64 v8; // rcx
  _WORD *v9; // rax
  __int64 v10; // rdx
  _WORD *v11; // rcx
  LSTATUS v12; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  const WCHAR *v16; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[1024]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[512]; // [rsp+460h] [rbp+360h] BYREF

  v4 = 0;
  if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v17, 1024, 0) < 0 )
  {
    v6 = 0;
    v7 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v8 = 2147483646;
    v9 = v17;
    v10 = 512;
    do
    {
      if ( !v8 )
        break;
      v5 = *v7;
      if ( !(_WORD)v5 )
        break;
      *v9 = v5;
      ++v7;
      ++v9;
      --v8;
      --v10;
    }
    while ( v10 );
    v11 = v9 - 1;
    if ( v10 )
      v11 = v9;
    *v11 = 0;
    v4 = v10 == 0 ? 0x8007007A : 0;
    if ( !v10 )
      goto LABEL_16;
  }
  StringCchPrintfW(SubKey, 0x200u, L"%s\\%s\\%s", v17, L"Policies", a2);
  hKey = 0;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
  if ( v12 )
  {
    v6 = 0;
    if ( v12 < 0 )
      goto LABEL_16;
  }
  else
  {
    v6 = hKey;
  }
  Type = 0;
  if ( !RegQueryValueExW(v6, lpValueName, 0, &Type, 0, 0) )
  {
    if ( v6 )
      RegCloseKey(v6);
    return 1;
  }
LABEL_16:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    Type = v4;
    if ( !a2 )
      a2 = &String2;
    v16 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v11,
      (__int64)byte_18003F093,
      (__int64)v7,
      v5,
      &v16,
      (__int64)&Type);
  }
  if ( v6 )
    RegCloseKey(v6);
  return 0;
}

```

## disassembly

```asm
0x18000d09c  mov     [rsp-8+arg_10], rbx
0x18000d0a1  push    rbp
0x18000d0a2  push    rsi
0x18000d0a3  push    rdi
0x18000d0a4  push    r14
0x18000d0a6  push    r15
0x18000d0a8  lea     rbp, [rsp-770h]
0x18000d0b0  sub     rsp, 870h
0x18000d0b7  mov     rax, cs:__security_cookie
0x18000d0be  xor     rax, rsp
0x18000d0c1  mov     [rbp+790h+var_30], rax
0x18000d0c8  xor     r15d, r15d
0x18000d0cb  lea     rax, [rsp+890h+var_830]
0x18000d0d0  mov     [rsp+890h+var_860], r15
0x18000d0d5  mov     rsi, rdx
0x18000d0d8  mov     r14, rcx
0x18000d0db  mov     dword ptr [rsp+890h+lpcbData], 400h
0x18000d0e3  xor     r9d, r9d
0x18000d0e6  mov     [rsp+890h+phkResult], rax
0x18000d0eb  xor     r8d, r8d
0x18000d0ee  lea     rcx, aWinevt; "WINEVT"
0x18000d0f5  xor     edx, edx
0x18000d0f7  mov     edi, r15d
0x18000d0fa  call    cs:__imp_RtlGetPersistedStateLocation
0x18000d100  mov     r10d, 200h
0x18000d106  test    eax, eax
0x18000d108  jns     short loc_18000D16D
0x18000d10a  mov     ebx, r15d
0x18000d10d  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d114  mov     ecx, 7FFFFFFEh
0x18000d119  lea     rax, [rsp+890h+var_830]
0x18000d11e  mov     edx, r10d
0x18000d121  test    rcx, rcx
0x18000d124  jz      short loc_18000D145
0x18000d126  movzx   r9d, word ptr [r8]
0x18000d12a  test    r9w, r9w
0x18000d12e  jz      short loc_18000D145
0x18000d130  mov     [rax], r9w
0x18000d134  add     r8, 2
0x18000d138  add     rax, 2
0x18000d13c  dec     rcx
0x18000d13f  sub     rdx, 1
0x18000d143  jnz     short loc_18000D121
0x18000d145  test    rdx, rdx
0x18000d148  lea     rcx, [rax-2]
0x18000d14c  cmovnz  rcx, rax
0x18000d150  mov     rax, rdx
0x18000d153  neg     rax
0x18000d156  sbb     edi, edi
0x18000d158  not     edi
0x18000d15a  mov     [rcx], r15w
0x18000d15e  and     edi, 8007007Ah
0x18000d164  test    rdx, rdx
0x18000d167  jz      loc_18000D210
0x18000d16d  lea     rax, aPolicies; "Policies"
0x18000d174  mov     [rsp+890h+lpcbData], rsi
0x18000d179  lea     r9, [rsp+890h+var_830]
0x18000d17e  mov     [rsp+890h+phkResult], rax
0x18000d183  lea     r8, aSSS; "%s\\%s\\%s"
0x18000d18a  mov     rdx, r10; unsigned __int64
0x18000d18d  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000d194  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d199  lea     rax, [rsp+890h+hKey]
0x18000d19e  mov     [rsp+890h+hKey], r15
0x18000d1a3  mov     r9d, 20119h; samDesired
0x18000d1a9  mov     [rsp+890h+phkResult], rax; phkResult
0x18000d1ae  xor     r8d, r8d; ulOptions
0x18000d1b1  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000d1b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d1bf  call    cs:__imp_RegOpenKeyExW
0x18000d1c5  test    eax, eax
0x18000d1c7  jnz     short loc_18000D1D0
0x18000d1c9  mov     rbx, [rsp+890h+hKey]
0x18000d1ce  jmp     short loc_18000D1D7
0x18000d1d0  mov     rbx, r15
0x18000d1d3  test    eax, eax
0x18000d1d5  js      short loc_18000D210
0x18000d1d7  mov     [rsp+890h+lpcbData], r15; lpcbData
0x18000d1dc  lea     r9, [rsp+890h+Type]; lpType
0x18000d1e1  xor     r8d, r8d; lpReserved
0x18000d1e4  mov     [rsp+890h+phkResult], r15; lpData
0x18000d1e9  mov     rdx, r14; lpValueName
0x18000d1ec  mov     [rsp+890h+Type], r15d
0x18000d1f1  mov     rcx, rbx; hKey
0x18000d1f4  call    cs:__imp_RegQueryValueExW
0x18000d1fa  test    eax, eax
0x18000d1fc  jnz     short loc_18000D210
0x18000d1fe  test    rbx, rbx
0x18000d201  jz      short loc_18000D20C
0x18000d203  mov     rcx, rbx; hKey
0x18000d206  call    cs:__imp_RegCloseKey
0x18000d20c  mov     al, 1
0x18000d20e  jmp     short loc_18000D262
0x18000d210  mov     eax, cs:dword_180048E90
0x18000d216  cmp     eax, 5
0x18000d219  jbe     short loc_18000D252
0x18000d21b  test    rsi, rsi
0x18000d21e  mov     [rsp+890h+Type], edi
0x18000d222  lea     rax, String2
0x18000d229  cmovz   rsi, rax
0x18000d22d  lea     rdx, byte_18003F093
0x18000d234  lea     rax, [rsp+890h+Type]
0x18000d239  mov     [rsp+890h+var_840], rsi
0x18000d23e  mov     [rsp+890h+lpcbData], rax
0x18000d243  lea     rax, [rsp+890h+var_840]
0x18000d248  mov     [rsp+890h+phkResult], rax
0x18000d24d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000d252  test    rbx, rbx
0x18000d255  jz      short loc_18000D260
0x18000d257  mov     rcx, rbx; hKey
0x18000d25a  call    cs:__imp_RegCloseKey
0x18000d260  xor     al, al
0x18000d262  mov     rcx, [rbp+790h+var_30]
0x18000d269  xor     rcx, rsp; StackCookie
0x18000d26c  call    __security_check_cookie
0x18000d271  mov     rbx, [rsp+890h+arg_10]
0x18000d279  add     rsp, 870h
0x18000d280  pop     r15
0x18000d282  pop     r14
0x18000d284  pop     rdi
0x18000d285  pop     rsi
0x18000d286  pop     rbp
0x18000d287  retn
```
