# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x1800b16c8`
- end: `0x1800b192c`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `612`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800b1594`

## callees

- `0x180007270`
- `0x1800520f0`
- `0x180054ec0`
- `0x1800583bc`
- `0x18005cf3c`
- `0x18005cfac`
- `0x18005d010`
- `0x18005d034`
- `0x18005d058`
- `0x18005d5a0`
- `0x18005d6e0`
- `0x18006e950`
- `0x1800b16c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b172c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b17b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b172c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b17b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1770`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b17f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b1770`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b17f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(const unsigned __int16 *a1, char *a2)
{
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  bool v5; // cc
  LSTATUS v6; // eax
  char *v7; // rcx
  void *v8; // rax
  volatile signed __int64 *v9; // rbx
  unsigned int v10; // edx
  char *v12; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  char **v18; // [rsp+58h] [rbp-A8h] BYREF
  char *v19; // [rsp+60h] [rbp-A0h] BYREF
  char v20; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v22[136]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  byte_18010E3B0 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath();
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3
    || (cbData = 78,
        v3 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData),
        v4 = v3,
        v5 = v3 <= 0,
        v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v22, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v12 = 0;
      v18 = &v12;
      v19 = 0;
      v20 = 1;
      v4 = UnicodeToMB(v22, 0xFDE9u, &v19, &v17);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v18);
      v7 = v12;
      if ( v4 >= 0 && v12 )
      {
        v4 = StringCchCopyA(&byte_18010E3B0, 0x81u, v12);
        v7 = v12;
      }
      v12 = 0;
      if ( v7 )
        MemoryFree(v7);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  if ( v4 < 0 )
  {
    v8 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    if ( v8 )
      v9 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
    else
      v9 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v9,
      _InterlockedExchangeAdd64(v9 + 17, 0),
      &byte_18010E3B0);
    if ( v9 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v9, v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800b16c8  mov     [rsp-8+arg_0], rbx
0x1800b16cd  push    rbp
0x1800b16ce  lea     rbp, [rsp-0E0h]
0x1800b16d6  sub     rsp, 1E0h
0x1800b16dd  mov     rax, cs:__security_cookie
0x1800b16e4  xor     rax, rsp
0x1800b16e7  mov     [rbp+0E0h+var_10], rax
0x1800b16ee  mov     [rsp+1E0h+hKey], 0
0x1800b16f7  mov     cs:byte_18010E3B0, 0
0x1800b16fe  xor     edx, edx
0x1800b1700  lea     rcx, [rsp+1E0h+hKey]
0x1800b1705  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b170a  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800b170f  lea     rcx, [rsp+1E0h+hKey]
0x1800b1714  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x1800b1719  mov     r9d, 20019h; samDesired
0x1800b171f  xor     r8d, r8d; ulOptions
0x1800b1722  mov     rdx, rax; lpSubKey
0x1800b1725  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b172c  call    cs:__imp_RegOpenKeyExW
0x1800b1733  nop     dword ptr [rax+rax+00h]
0x1800b1738  mov     ebx, eax
0x1800b173a  test    eax, eax
0x1800b173c  jnz     loc_1800B18A2
0x1800b1742  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x1800b174a  lea     rax, [rsp+1E0h+cbData]
0x1800b174f  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800b1754  lea     rax, [rsp+1E0h+Data]
0x1800b1759  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800b175e  xor     r9d, r9d; lpType
0x1800b1761  xor     r8d, r8d; lpReserved
0x1800b1764  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1800b176b  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800b1770  call    cs:__imp_RegQueryValueExW
0x1800b1777  nop     dword ptr [rax+rax+00h]
0x1800b177c  mov     ebx, eax
0x1800b177e  test    eax, eax
0x1800b1780  jnz     loc_1800B18A2
0x1800b1786  mov     [rsp+1E0h+var_1A0], 0
0x1800b178f  xor     edx, edx
0x1800b1791  lea     rcx, [rsp+1E0h+var_1A0]
0x1800b1796  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b179b  lea     rax, [rsp+1E0h+var_1A0]
0x1800b17a0  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800b17a5  mov     r9d, 20019h; samDesired
0x1800b17ab  xor     r8d, r8d; ulOptions
0x1800b17ae  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x1800b17b3  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800b17b8  call    cs:__imp_RegOpenKeyExW
0x1800b17bf  nop     dword ptr [rax+rax+00h]
0x1800b17c4  mov     [rsp+1E0h+var_194], 102h
0x1800b17cc  lea     rax, [rsp+1E0h+var_194]
0x1800b17d1  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800b17d6  lea     rax, [rbp+0E0h+var_120]
0x1800b17da  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800b17df  xor     r9d, r9d; lpType
0x1800b17e2  xor     r8d, r8d; lpReserved
0x1800b17e5  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x1800b17ec  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x1800b17f1  call    cs:__imp_RegQueryValueExW
0x1800b17f8  nop     dword ptr [rax+rax+00h]
0x1800b17fd  mov     ebx, eax
0x1800b17ff  test    eax, eax
0x1800b1801  jnz     loc_1800B188A
0x1800b1807  mov     [rsp+1E0h+var_1B0], 0
0x1800b1810  lea     rax, [rsp+1E0h+var_1B0]
0x1800b1815  mov     [rsp+1E0h+var_188], rax
0x1800b181a  mov     [rsp+1E0h+var_180], 0
0x1800b1823  mov     [rsp+1E0h+var_178], 1
0x1800b1828  lea     r9, [rsp+1E0h+var_190]; unsigned int *
0x1800b182d  lea     r8, [rsp+1E0h+var_180]; char **
0x1800b1832  mov     edx, 0FDE9h; CodePage
0x1800b1837  lea     rcx, [rbp+0E0h+var_120]; lpWideCharStr
0x1800b183b  call    ?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800b1840  mov     ebx, eax
0x1800b1842  lea     rcx, [rsp+1E0h+var_188]
0x1800b1847  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800b184c  mov     rcx, [rsp+1E0h+var_1B0]
0x1800b1851  test    ebx, ebx
0x1800b1853  js      short loc_1800B1875
0x1800b1855  test    rcx, rcx
0x1800b1858  jz      short loc_1800B1875
0x1800b185a  mov     r8, rcx; char *
0x1800b185d  mov     edx, 81h; unsigned __int64
0x1800b1862  lea     rcx, byte_18010E3B0; char *
0x1800b1869  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800b186e  mov     ebx, eax
0x1800b1870  mov     rcx, [rsp+1E0h+var_1B0]; void *
0x1800b1875  mov     [rsp+1E0h+var_1B0], 0
0x1800b187e  test    rcx, rcx
0x1800b1881  jz      short loc_1800B1895
0x1800b1883  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800b1888  jmp     short loc_1800B1895
0x1800b188a  jle     short loc_1800B1895
0x1800b188c  movzx   ebx, ax
0x1800b188f  or      ebx, 80070000h
0x1800b1895  lea     rcx, [rsp+1E0h+var_1A0]
0x1800b189a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b189f  nop
0x1800b18a0  jmp     short loc_1800B18AD
0x1800b18a2  jle     short loc_1800B18AD
0x1800b18a4  movzx   ebx, ax
0x1800b18a7  or      ebx, 80070000h
0x1800b18ad  test    ebx, ebx
0x1800b18af  jns     short loc_1800B18FE
0x1800b18b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b18b8  mov     ecx, 90h; unsigned __int64
0x1800b18bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b18c2  test    rax, rax
0x1800b18c5  jz      short loc_1800B18D4
0x1800b18c7  mov     rcx, rax
0x1800b18ca  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1800b18cf  mov     rbx, rax
0x1800b18d2  jmp     short loc_1800B18D6
0x1800b18d4  xor     ebx, ebx
0x1800b18d6  xor     edx, edx
0x1800b18d8  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800b18e1  lea     r8, byte_18010E3B0; char *
0x1800b18e8  mov     rcx, rbx; this
0x1800b18eb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800b18f0  test    rbx, rbx
0x1800b18f3  jz      short loc_1800B18FE
0x1800b18f5  mov     rcx, rbx; this
0x1800b18f8  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800b18fd  nop
0x1800b18fe  lea     rcx, [rsp+1E0h+hKey]
0x1800b1903  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b1908  nop
0x1800b1909  xor     eax, eax
0x1800b190b  mov     rcx, [rbp+0E0h+var_10]
0x1800b1912  xor     rcx, rsp; StackCookie
0x1800b1915  call    __security_check_cookie
0x1800b191a  mov     rbx, [rsp+1E0h+arg_0]
0x1800b1922  add     rsp, 1E0h
0x1800b1929  pop     rbp
0x1800b192a  retn
```
