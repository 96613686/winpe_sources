# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x140018d74`
- end: `0x140018fde`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `618`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14001848c`

## callees

- `0x1400029c0`
- `0x14000360c`
- `0x140004b94`
- `0x140005344`
- `0x140007578`
- `0x140007e3c`
- `0x14000b784`
- `0x1400183c8`
- `0x140018438`
- `0x140018468`
- `0x140018c00`
- `0x140018d74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018e1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018e9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018e1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018e9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018dda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018e66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018dda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018e66`
- `DMCmnUtils!UnicodeToMB` at `0x140018eed`
- `DMCmnUtils!UnicodeToMB` at `0x140018eed`

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
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rax
  char *v10; // r8
  volatile signed __int64 *v11; // rbx
  unsigned int v12; // edx
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  wil::details **v20; // [rsp+58h] [rbp-A8h] BYREF
  char *v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[136]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  byte_1400258D0 = 0;
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
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v24, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v14 = 0;
      v19 = 0;
      v20 = &v14;
      v21 = 0;
      v22 = 1;
      v4 = UnicodeToMB(v24, 0xFDE9u, &v21, &v19);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v20);
      v8 = v14;
      if ( v4 >= 0 && v14 )
      {
        v4 = StringCchCopyA(&byte_1400258D0, 0x81u, (const char *)v14);
        v8 = v14;
      }
      v14 = 0;
      if ( v8 )
        wil::details::FreeProcessHeap(v8, v7);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  if ( v4 < 0 )
  {
    v9 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
      v11 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v9);
    else
      v11 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v11,
      _InterlockedExchangeAdd64(v11 + 17, 0),
      v10);
    if ( v11 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v11, v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x140018d74  mov     [rsp-8+arg_0], rbx
0x140018d79  push    rbp
0x140018d7a  lea     rbp, [rsp-0E0h]
0x140018d82  sub     rsp, 1E0h
0x140018d89  mov     rax, cs:__security_cookie
0x140018d90  xor     rax, rsp
0x140018d93  mov     [rbp+0E0h+var_10], rax
0x140018d9a  mov     [rsp+1E0h+hKey], 0
0x140018da3  mov     cs:byte_1400258D0, 0
0x140018daa  xor     edx, edx
0x140018dac  lea     rcx, [rsp+1E0h+hKey]
0x140018db1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140018db6  xor     ecx, ecx
0x140018db8  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x140018dbd  lea     rcx, [rsp+1E0h+hKey]
0x140018dc2  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x140018dc7  mov     r9d, 20019h; samDesired
0x140018dcd  xor     r8d, r8d; ulOptions
0x140018dd0  mov     rdx, rax; lpSubKey
0x140018dd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018dda  call    cs:__imp_RegOpenKeyExW
0x140018de1  nop     dword ptr [rax+rax+00h]
0x140018de6  mov     ebx, eax
0x140018de8  test    eax, eax
0x140018dea  jnz     loc_140018F5B
0x140018df0  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x140018df8  lea     rax, [rsp+1E0h+cbData]
0x140018dfd  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x140018e02  lea     rax, [rsp+1E0h+Data]
0x140018e07  mov     [rsp+1E0h+phkResult], rax; lpData
0x140018e0c  xor     r9d, r9d; lpType
0x140018e0f  xor     r8d, r8d; lpReserved
0x140018e12  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x140018e19  mov     rcx, [rsp+1E0h+hKey]; hKey
0x140018e1e  call    cs:__imp_RegQueryValueExW
0x140018e25  nop     dword ptr [rax+rax+00h]
0x140018e2a  mov     ebx, eax
0x140018e2c  test    eax, eax
0x140018e2e  jnz     loc_140018F5B
0x140018e34  mov     [rsp+1E0h+var_1A0], 0
0x140018e3d  xor     edx, edx
0x140018e3f  lea     rcx, [rsp+1E0h+var_1A0]
0x140018e44  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140018e49  lea     rax, [rsp+1E0h+var_1A0]
0x140018e4e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x140018e53  mov     r9d, 20019h; samDesired
0x140018e59  xor     r8d, r8d; ulOptions
0x140018e5c  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x140018e61  mov     rcx, [rsp+1E0h+hKey]; hKey
0x140018e66  call    cs:__imp_RegOpenKeyExW
0x140018e6d  nop     dword ptr [rax+rax+00h]
0x140018e72  mov     [rsp+1E0h+var_194], 102h
0x140018e7a  lea     rax, [rsp+1E0h+var_194]
0x140018e7f  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x140018e84  lea     rax, [rbp+0E0h+var_120]
0x140018e88  mov     [rsp+1E0h+phkResult], rax; lpData
0x140018e8d  xor     r9d, r9d; lpType
0x140018e90  xor     r8d, r8d; lpReserved
0x140018e93  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x140018e9a  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x140018e9f  call    cs:__imp_RegQueryValueExW
0x140018ea6  nop     dword ptr [rax+rax+00h]
0x140018eab  mov     ebx, eax
0x140018ead  test    eax, eax
0x140018eaf  jnz     loc_140018F43
0x140018eb5  mov     [rsp+1E0h+var_1B0], 0
0x140018ebe  mov     [rsp+1E0h+var_190], eax
0x140018ec2  lea     rax, [rsp+1E0h+var_1B0]
0x140018ec7  mov     [rsp+1E0h+var_188], rax
0x140018ecc  mov     [rsp+1E0h+var_180], 0
0x140018ed5  mov     [rsp+1E0h+var_178], 1
0x140018eda  lea     r9, [rsp+1E0h+var_190]
0x140018edf  lea     r8, [rsp+1E0h+var_180]
0x140018ee4  mov     edx, 0FDE9h
0x140018ee9  lea     rcx, [rbp+0E0h+var_120]
0x140018eed  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x140018ef4  nop     dword ptr [rax+rax+00h]
0x140018ef9  mov     ebx, eax
0x140018efb  lea     rcx, [rsp+1E0h+var_188]
0x140018f00  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x140018f05  mov     rcx, [rsp+1E0h+var_1B0]
0x140018f0a  test    ebx, ebx
0x140018f0c  js      short loc_140018F2E
0x140018f0e  test    rcx, rcx
0x140018f11  jz      short loc_140018F2E
0x140018f13  mov     r8, rcx; char *
0x140018f16  mov     edx, 81h; unsigned __int64
0x140018f1b  lea     rcx, byte_1400258D0; char *
0x140018f22  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x140018f27  mov     ebx, eax
0x140018f29  mov     rcx, [rsp+1E0h+var_1B0]; this
0x140018f2e  mov     [rsp+1E0h+var_1B0], 0
0x140018f37  test    rcx, rcx
0x140018f3a  jz      short loc_140018F4E
0x140018f3c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140018f41  jmp     short loc_140018F4E
0x140018f43  jle     short loc_140018F4E
0x140018f45  movzx   ebx, ax
0x140018f48  or      ebx, 80070000h
0x140018f4e  lea     rcx, [rsp+1E0h+var_1A0]
0x140018f53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140018f58  nop
0x140018f59  jmp     short loc_140018F66
0x140018f5b  jle     short loc_140018F66
0x140018f5d  movzx   ebx, ax
0x140018f60  or      ebx, 80070000h
0x140018f66  test    ebx, ebx
0x140018f68  jns     short loc_140018FB0
0x140018f6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018f71  mov     ecx, 90h; unsigned __int64
0x140018f76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140018f7b  test    rax, rax
0x140018f7e  jz      short loc_140018F8D
0x140018f80  mov     rcx, rax
0x140018f83  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x140018f88  mov     rbx, rax
0x140018f8b  jmp     short loc_140018F8F
0x140018f8d  xor     ebx, ebx
0x140018f8f  xor     edx, edx
0x140018f91  lock xadd [rbx+88h], rdx; unsigned __int64
0x140018f9a  mov     rcx, rbx; this
0x140018f9d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x140018fa2  test    rbx, rbx
0x140018fa5  jz      short loc_140018FB0
0x140018fa7  mov     rcx, rbx; this
0x140018faa  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x140018faf  nop
0x140018fb0  lea     rcx, [rsp+1E0h+hKey]
0x140018fb5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140018fba  nop
0x140018fbb  xor     eax, eax
0x140018fbd  mov     rcx, [rbp+0E0h+var_10]
0x140018fc4  xor     rcx, rsp; StackCookie
0x140018fc7  call    __security_check_cookie
0x140018fcc  mov     rbx, [rsp+1E0h+arg_0]
0x140018fd4  add     rsp, 1E0h
0x140018fdb  pop     rbp
0x140018fdc  retn
```
