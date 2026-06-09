# GetActiveMmsProfile(HKEY__ * *)

- ea: `0x180051fa0`
- end: `0x180052177`
- name: `?GetActiveMmsProfile@@YAJPEAPEAUHKEY__@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180052180`

## callees

- `0x180003e38`
- `0x18000b938`
- `0x1800237bc`
- `0x18004ed50`
- `0x180051f64`
- `0x180051fa0`
- `0x18005222c`
- `0x180052258`
- `0x1800c50ec`
- `0x1800c6940`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18005210e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005214f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005210e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005214f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052030`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800520e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052030`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800520e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005212d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005212d`

## pseudocode

```c
__int64 __fastcall GetActiveMmsProfile(PHKEY phkResult)
{
  HKEY *v2; // rax
  const struct RegistryIsolationKeys *v3; // rcx
  int *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  DWORD v8; // eax
  void *v9; // rax
  WCHAR *v10; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  LSTATUS v13; // eax
  LPBYTE lpData; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  DWORD Type; // [rsp+48h] [rbp-20h] BYREF

  hKey = 0;
  v2 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = RegistryOpenKey(v3, L"\\MMS\\Profiles", v2, v4, 0x20019u);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_8;
  }
  Type = 0;
  cbData = 0;
  v7 = RegQueryValueExW(hKey, L"Active", 0, &Type, 0, &cbData);
  v6 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_8;
  }
  v8 = cbData;
  if ( !cbData )
  {
    Log_AssertionEvent_25();
    v8 = cbData;
    if ( !cbData )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v8 = cbData;
    }
  }
  lpData = 0;
  cbData = v8 + 2;
  v9 = operator new[](saturated_mul((unsigned __int64)(v8 + 2) >> 1, 2u));
  tlx::auto_xxx<char *,void (*)(char *),&void tlx::_delete_array<char>(char *),0>::reset(&lpData, v9);
  v10 = (WCHAR *)lpData;
  if ( !lpData )
  {
    v6 = -2147024882;
LABEL_8:
    Log_HREvent_28(v6);
    goto LABEL_23;
  }
  v11 = RegQueryValueExW(hKey, L"Active", 0, 0, lpData, &cbData);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v13 = RegOpenKeyExW(hKey, v10, 0, 0x20019u, phkResult);
    v12 = v13;
    if ( !v13 )
    {
      operator delete[](v10);
      v6 = 0;
      goto LABEL_23;
    }
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
  }
  Log_HREvent_28(v12);
  operator delete[](v10);
  v6 = v12;
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x180051fa0  push    rbp
0x180051fa2  push    rbx
0x180051fa3  push    rsi
0x180051fa4  push    rdi
0x180051fa5  mov     rbp, rsp
0x180051fa8  sub     rsp, 68h
0x180051fac  mov     rax, cs:__security_cookie
0x180051fb3  xor     rax, rsp
0x180051fb6  mov     [rbp+var_18], rax
0x180051fba  mov     rsi, rcx
0x180051fbd  mov     [rbp+hKey], 0
0x180051fc5  lea     rcx, [rbp+hKey]
0x180051fc9  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180051fce  mov     r8, rax; HKEY *
0x180051fd1  mov     dword ptr [rsp+68h+lpData], 20019h; unsigned int
0x180051fd9  lea     rdx, aMmsProfiles; "\\MMS\\Profiles"
0x180051fe0  call    ?RegistryOpenKey@@YAJAEBURegistryIsolationKeys@@PEBGPEAPEAUHKEY__@@PEAHK@Z; RegistryOpenKey(RegistryIsolationKeys const &,ushort const *,HKEY__ * *,int *,ulong)
0x180051fe5  mov     ebx, eax
0x180051fe7  test    eax, eax
0x180051fe9  jz      short loc_180051FFE
0x180051feb  jle     short loc_180051FF6
0x180051fed  movzx   ebx, ax
0x180051ff0  or      ebx, 80070000h
0x180051ff6  mov     r9d, 21h ; '!'
0x180051ffc  jmp     short loc_18005204D
0x180051ffe  mov     rcx, [rbp+hKey]; hKey
0x180052002  lea     rax, [rbp+cbData]
0x180052006  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18005200b  lea     r9, [rbp+Type]; lpType
0x18005200f  xor     r8d, r8d; lpReserved
0x180052012  mov     [rsp+68h+lpData], 0; lpData
0x18005201b  lea     rdx, aActive; "Active"
0x180052022  mov     [rbp+Type], 0
0x180052029  mov     [rbp+cbData], 0
0x180052030  call    cs:__imp_RegQueryValueExW
0x180052036  mov     ebx, eax
0x180052038  test    eax, eax
0x18005203a  jz      short loc_18005205B
0x18005203c  jle     short loc_180052047
0x18005203e  movzx   ebx, ax
0x180052041  or      ebx, 80070000h
0x180052047  mov     r9d, 26h ; '&'
0x18005204d  xor     edx, edx
0x18005204f  mov     ecx, ebx; int
0x180052051  call    Log_HREvent_28
0x180052056  jmp     loc_180052157
0x18005205b  mov     eax, [rbp+cbData]
0x18005205e  test    eax, eax
0x180052060  jnz     short loc_180052076
0x180052062  call    Log_AssertionEvent_25
0x180052067  mov     eax, [rbp+cbData]
0x18005206a  test    eax, eax
0x18005206c  jnz     short loc_180052076
0x18005206e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180052073  mov     eax, [rbp+cbData]
0x180052076  add     eax, 2
0x180052079  mov     [rbp+var_38], 0
0x180052081  mov     ecx, eax
0x180052083  mov     [rbp+cbData], eax
0x180052086  mov     eax, 2
0x18005208b  shr     rcx, 1
0x18005208e  mul     rcx
0x180052091  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180052098  cmovb   rax, rcx
0x18005209c  mov     rcx, rax; unsigned __int64
0x18005209f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800520a4  mov     rdx, rax
0x1800520a7  lea     rcx, [rbp+var_38]
0x1800520ab  call    ?reset@?$auto_xxx@PEADP6AXPEAD@Z$1??$_delete_array@D@tlx@@YAX0@Z$0A@@tlx@@QEAAXPEAD@Z; tlx::auto_xxx<char *,void (*)(char *),&tlx::_delete_array<char>(char *),0>::reset(char *)
0x1800520b0  mov     rbx, [rbp+var_38]
0x1800520b4  test    rbx, rbx
0x1800520b7  jnz     short loc_1800520C6
0x1800520b9  mov     ebx, 8007000Eh
0x1800520be  mov     r9d, 2Ch ; ','
0x1800520c4  jmp     short loc_18005204D
0x1800520c6  mov     rcx, [rbp+hKey]; hKey
0x1800520ca  lea     rax, [rbp+cbData]
0x1800520ce  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800520d3  lea     rdx, aActive; "Active"
0x1800520da  xor     r9d, r9d; lpType
0x1800520dd  mov     [rsp+68h+lpData], rbx; lpData
0x1800520e2  xor     r8d, r8d; lpReserved
0x1800520e5  call    cs:__imp_RegQueryValueExW
0x1800520eb  mov     edi, eax
0x1800520ed  test    eax, eax
0x1800520ef  jz      short loc_180052118
0x1800520f1  jle     short loc_1800520FC
0x1800520f3  movzx   edi, ax
0x1800520f6  or      edi, 80070000h
0x1800520fc  mov     r9d, 30h ; '0'
0x180052102  xor     edx, edx
0x180052104  mov     ecx, edi; int
0x180052106  call    Log_HREvent_28
0x18005210b  mov     rcx, rbx
0x18005210e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180052114  mov     ebx, edi
0x180052116  jmp     short loc_180052157
0x180052118  mov     rcx, [rbp+hKey]; hKey
0x18005211c  mov     r9d, 20019h; samDesired
0x180052122  xor     r8d, r8d; ulOptions
0x180052125  mov     [rsp+68h+lpData], rsi; phkResult
0x18005212a  mov     rdx, rbx; lpSubKey
0x18005212d  call    cs:__imp_RegOpenKeyExW
0x180052133  mov     edi, eax
0x180052135  test    eax, eax
0x180052137  jz      short loc_18005214C
0x180052139  jle     short loc_180052144
0x18005213b  movzx   edi, ax
0x18005213e  or      edi, 80070000h
0x180052144  mov     r9d, 33h ; '3'
0x18005214a  jmp     short loc_180052102
0x18005214c  mov     rcx, rbx
0x18005214f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180052155  xor     ebx, ebx
0x180052157  lea     rcx, [rbp+hKey]
0x18005215b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052160  mov     eax, ebx
0x180052162  mov     rcx, [rbp+var_18]
0x180052166  xor     rcx, rsp; StackCookie
0x180052169  call    __security_check_cookie
0x18005216e  add     rsp, 68h
0x180052172  pop     rdi
0x180052173  pop     rsi
0x180052174  pop     rbx
0x180052175  pop     rbp
0x180052176  retn
```
