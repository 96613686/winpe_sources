# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180097434`
- end: `0x1800976a5`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `625`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180095efc`

## callees

- `0x180004eb0`
- `0x1800053e0`
- `0x180008fe4`
- `0x18000ab80`
- `0x180016698`
- `0x180017118`
- `0x180020cb0`
- `0x1800232b8`
- `0x1800285cc`
- `0x18002a028`
- `0x180036d48`
- `0x180097434`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x1800975ad`
- `DMCmnUtils!UnicodeToMB` at `0x1800975ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800974de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009755f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800974de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009755f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009749a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097526`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009749a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097526`

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
  unsigned __int16 v22[136]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  byte_1800FF760 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath(0);
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
      v17 = 0;
      v18 = &v12;
      v19 = 0;
      v20 = 1;
      v4 = UnicodeToMB(v22, 0xFDE9u, &v19, &v17);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v18);
      v7 = v12;
      if ( v4 >= 0 && v12 )
      {
        v4 = StringCchCopyA(&byte_1800FF760, 0x81u, v12);
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
    v8 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v9 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
    else
      v9 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v9,
      _InterlockedExchangeAdd64(v9 + 17, 0),
      &byte_1800FF760);
    if ( v9 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v9, v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180097434  mov     [rsp-8+arg_0], rbx
0x180097439  push    rbp
0x18009743a  lea     rbp, [rsp-0E0h]
0x180097442  sub     rsp, 1E0h
0x180097449  mov     rax, cs:__security_cookie
0x180097450  xor     rax, rsp
0x180097453  mov     [rbp+0E0h+var_10], rax
0x18009745a  mov     [rsp+1E0h+hKey], 0
0x180097463  mov     cs:byte_1800FF760, 0
0x18009746a  xor     edx, edx
0x18009746c  lea     rcx, [rsp+1E0h+hKey]
0x180097471  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180097476  xor     ecx, ecx
0x180097478  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009747d  lea     rcx, [rsp+1E0h+hKey]
0x180097482  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x180097487  mov     r9d, 20019h; samDesired
0x18009748d  xor     r8d, r8d; ulOptions
0x180097490  mov     rdx, rax; lpSubKey
0x180097493  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009749a  call    cs:__imp_RegOpenKeyExW
0x1800974a1  nop     dword ptr [rax+rax+00h]
0x1800974a6  mov     ebx, eax
0x1800974a8  test    eax, eax
0x1800974aa  jnz     loc_18009761B
0x1800974b0  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x1800974b8  lea     rax, [rsp+1E0h+cbData]
0x1800974bd  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800974c2  lea     rax, [rsp+1E0h+Data]
0x1800974c7  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800974cc  xor     r9d, r9d; lpType
0x1800974cf  xor     r8d, r8d; lpReserved
0x1800974d2  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1800974d9  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800974de  call    cs:__imp_RegQueryValueExW
0x1800974e5  nop     dword ptr [rax+rax+00h]
0x1800974ea  mov     ebx, eax
0x1800974ec  test    eax, eax
0x1800974ee  jnz     loc_18009761B
0x1800974f4  mov     [rsp+1E0h+var_1A0], 0
0x1800974fd  xor     edx, edx
0x1800974ff  lea     rcx, [rsp+1E0h+var_1A0]
0x180097504  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180097509  lea     rax, [rsp+1E0h+var_1A0]
0x18009750e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180097513  mov     r9d, 20019h; samDesired
0x180097519  xor     r8d, r8d; ulOptions
0x18009751c  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x180097521  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180097526  call    cs:__imp_RegOpenKeyExW
0x18009752d  nop     dword ptr [rax+rax+00h]
0x180097532  mov     [rsp+1E0h+var_194], 102h
0x18009753a  lea     rax, [rsp+1E0h+var_194]
0x18009753f  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180097544  lea     rax, [rbp+0E0h+var_120]
0x180097548  mov     [rsp+1E0h+phkResult], rax; lpData
0x18009754d  xor     r9d, r9d; lpType
0x180097550  xor     r8d, r8d; lpReserved
0x180097553  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x18009755a  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x18009755f  call    cs:__imp_RegQueryValueExW
0x180097566  nop     dword ptr [rax+rax+00h]
0x18009756b  mov     ebx, eax
0x18009756d  test    eax, eax
0x18009756f  jnz     loc_180097603
0x180097575  mov     [rsp+1E0h+var_1B0], 0
0x18009757e  mov     [rsp+1E0h+var_190], eax
0x180097582  lea     rax, [rsp+1E0h+var_1B0]
0x180097587  mov     [rsp+1E0h+var_188], rax
0x18009758c  mov     [rsp+1E0h+var_180], 0
0x180097595  mov     [rsp+1E0h+var_178], 1
0x18009759a  lea     r9, [rsp+1E0h+var_190]
0x18009759f  lea     r8, [rsp+1E0h+var_180]
0x1800975a4  mov     edx, 0FDE9h
0x1800975a9  lea     rcx, [rbp+0E0h+var_120]
0x1800975ad  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800975b4  nop     dword ptr [rax+rax+00h]
0x1800975b9  mov     ebx, eax
0x1800975bb  lea     rcx, [rsp+1E0h+var_188]
0x1800975c0  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800975c5  mov     rcx, [rsp+1E0h+var_1B0]
0x1800975ca  test    ebx, ebx
0x1800975cc  js      short loc_1800975EE
0x1800975ce  test    rcx, rcx
0x1800975d1  jz      short loc_1800975EE
0x1800975d3  mov     r8, rcx; char *
0x1800975d6  mov     edx, 81h; unsigned __int64
0x1800975db  lea     rcx, byte_1800FF760; char *
0x1800975e2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800975e7  mov     ebx, eax
0x1800975e9  mov     rcx, [rsp+1E0h+var_1B0]; void *
0x1800975ee  mov     [rsp+1E0h+var_1B0], 0
0x1800975f7  test    rcx, rcx
0x1800975fa  jz      short loc_18009760E
0x1800975fc  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180097601  jmp     short loc_18009760E
0x180097603  jle     short loc_18009760E
0x180097605  movzx   ebx, ax
0x180097608  or      ebx, 80070000h
0x18009760e  lea     rcx, [rsp+1E0h+var_1A0]
0x180097613  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180097618  nop
0x180097619  jmp     short loc_180097626
0x18009761b  jle     short loc_180097626
0x18009761d  movzx   ebx, ax
0x180097620  or      ebx, 80070000h
0x180097626  test    ebx, ebx
0x180097628  jns     short loc_180097677
0x18009762a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180097631  mov     ecx, 90h; unsigned __int64
0x180097636  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009763b  test    rax, rax
0x18009763e  jz      short loc_18009764D
0x180097640  mov     rcx, rax
0x180097643  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180097648  mov     rbx, rax
0x18009764b  jmp     short loc_18009764F
0x18009764d  xor     ebx, ebx
0x18009764f  xor     edx, edx
0x180097651  lock xadd [rbx+88h], rdx; unsigned __int64
0x18009765a  lea     r8, byte_1800FF760; char *
0x180097661  mov     rcx, rbx; this
0x180097664  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180097669  test    rbx, rbx
0x18009766c  jz      short loc_180097677
0x18009766e  mov     rcx, rbx; this
0x180097671  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180097676  nop
0x180097677  lea     rcx, [rsp+1E0h+hKey]
0x18009767c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180097681  nop
0x180097682  xor     eax, eax
0x180097684  mov     rcx, [rbp+0E0h+var_10]
0x18009768b  xor     rcx, rsp; StackCookie
0x18009768e  call    __security_check_cookie
0x180097693  mov     rbx, [rsp+1E0h+arg_0]
0x18009769b  add     rsp, 1E0h
0x1800976a2  pop     rbp
0x1800976a3  retn
```
