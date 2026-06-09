# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180094b3c`
- end: `0x180094d8e`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `594`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180093684`

## callees

- `0x180004d50`
- `0x180005280`
- `0x180008dac`
- `0x18000a83c`
- `0x180015f70`
- `0x1800169b8`
- `0x180022668`
- `0x180024c2c`
- `0x180029d2c`
- `0x18002b664`
- `0x180037aa0`
- `0x180094b3c`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x180094c9d`
- `DMCmnUtils!UnicodeToMB` at `0x180094c9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094be0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094c55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094be0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094c55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094ba2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094c22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094ba2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094c22`

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
  byte_1800FB910 = 0;
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
        v4 = StringCchCopyA(&byte_1800FB910, 0x81u, v12);
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
      &byte_1800FB910);
    if ( v9 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v9, v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180094b3c  mov     [rsp-8+arg_0], rbx
0x180094b41  push    rbp
0x180094b42  lea     rbp, [rsp-0E0h]
0x180094b4a  sub     rsp, 1E0h
0x180094b51  mov     rax, cs:__security_cookie
0x180094b58  xor     rax, rsp
0x180094b5b  mov     [rbp+0E0h+var_10], rax
0x180094b62  mov     [rsp+1E0h+hKey], 0
0x180094b6b  mov     cs:byte_1800FB910, 0
0x180094b72  xor     edx, edx
0x180094b74  lea     rcx, [rsp+1E0h+hKey]
0x180094b79  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180094b7e  xor     ecx, ecx
0x180094b80  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180094b85  lea     rcx, [rsp+1E0h+hKey]
0x180094b8a  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x180094b8f  mov     r9d, 20019h; samDesired
0x180094b95  xor     r8d, r8d; ulOptions
0x180094b98  mov     rdx, rax; lpSubKey
0x180094b9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180094ba2  call    cs:__imp_RegOpenKeyExW
0x180094ba8  mov     ebx, eax
0x180094baa  test    eax, eax
0x180094bac  jnz     loc_180094D05
0x180094bb2  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x180094bba  lea     rax, [rsp+1E0h+cbData]
0x180094bbf  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180094bc4  lea     rax, [rsp+1E0h+Data]
0x180094bc9  mov     [rsp+1E0h+phkResult], rax; lpData
0x180094bce  xor     r9d, r9d; lpType
0x180094bd1  xor     r8d, r8d; lpReserved
0x180094bd4  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x180094bdb  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180094be0  call    cs:__imp_RegQueryValueExW
0x180094be6  mov     ebx, eax
0x180094be8  test    eax, eax
0x180094bea  jnz     loc_180094D05
0x180094bf0  mov     [rsp+1E0h+var_1A0], 0
0x180094bf9  xor     edx, edx
0x180094bfb  lea     rcx, [rsp+1E0h+var_1A0]
0x180094c00  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180094c05  lea     rax, [rsp+1E0h+var_1A0]
0x180094c0a  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180094c0f  mov     r9d, 20019h; samDesired
0x180094c15  xor     r8d, r8d; ulOptions
0x180094c18  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x180094c1d  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180094c22  call    cs:__imp_RegOpenKeyExW
0x180094c28  mov     [rsp+1E0h+var_194], 102h
0x180094c30  lea     rax, [rsp+1E0h+var_194]
0x180094c35  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180094c3a  lea     rax, [rbp+0E0h+var_120]
0x180094c3e  mov     [rsp+1E0h+phkResult], rax; lpData
0x180094c43  xor     r9d, r9d; lpType
0x180094c46  xor     r8d, r8d; lpReserved
0x180094c49  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x180094c50  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x180094c55  call    cs:__imp_RegQueryValueExW
0x180094c5b  mov     ebx, eax
0x180094c5d  test    eax, eax
0x180094c5f  jnz     loc_180094CED
0x180094c65  mov     [rsp+1E0h+var_1B0], 0
0x180094c6e  mov     [rsp+1E0h+var_190], eax
0x180094c72  lea     rax, [rsp+1E0h+var_1B0]
0x180094c77  mov     [rsp+1E0h+var_188], rax
0x180094c7c  mov     [rsp+1E0h+var_180], 0
0x180094c85  mov     [rsp+1E0h+var_178], 1
0x180094c8a  lea     r9, [rsp+1E0h+var_190]
0x180094c8f  lea     r8, [rsp+1E0h+var_180]
0x180094c94  mov     edx, 0FDE9h
0x180094c99  lea     rcx, [rbp+0E0h+var_120]
0x180094c9d  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180094ca3  mov     ebx, eax
0x180094ca5  lea     rcx, [rsp+1E0h+var_188]
0x180094caa  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x180094caf  mov     rcx, [rsp+1E0h+var_1B0]
0x180094cb4  test    ebx, ebx
0x180094cb6  js      short loc_180094CD8
0x180094cb8  test    rcx, rcx
0x180094cbb  jz      short loc_180094CD8
0x180094cbd  mov     r8, rcx; char *
0x180094cc0  mov     edx, 81h; unsigned __int64
0x180094cc5  lea     rcx, byte_1800FB910; char *
0x180094ccc  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180094cd1  mov     ebx, eax
0x180094cd3  mov     rcx, [rsp+1E0h+var_1B0]; void *
0x180094cd8  mov     [rsp+1E0h+var_1B0], 0
0x180094ce1  test    rcx, rcx
0x180094ce4  jz      short loc_180094CF8
0x180094ce6  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180094ceb  jmp     short loc_180094CF8
0x180094ced  jle     short loc_180094CF8
0x180094cef  movzx   ebx, ax
0x180094cf2  or      ebx, 80070000h
0x180094cf8  lea     rcx, [rsp+1E0h+var_1A0]
0x180094cfd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180094d02  nop
0x180094d03  jmp     short loc_180094D10
0x180094d05  jle     short loc_180094D10
0x180094d07  movzx   ebx, ax
0x180094d0a  or      ebx, 80070000h
0x180094d10  test    ebx, ebx
0x180094d12  jns     short loc_180094D61
0x180094d14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180094d1b  mov     ecx, 90h; unsigned __int64
0x180094d20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180094d25  test    rax, rax
0x180094d28  jz      short loc_180094D37
0x180094d2a  mov     rcx, rax
0x180094d2d  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180094d32  mov     rbx, rax
0x180094d35  jmp     short loc_180094D39
0x180094d37  xor     ebx, ebx
0x180094d39  xor     edx, edx
0x180094d3b  lock xadd [rbx+88h], rdx; unsigned __int64
0x180094d44  lea     r8, byte_1800FB910; char *
0x180094d4b  mov     rcx, rbx; this
0x180094d4e  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180094d53  test    rbx, rbx
0x180094d56  jz      short loc_180094D61
0x180094d58  mov     rcx, rbx; this
0x180094d5b  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180094d60  nop
0x180094d61  lea     rcx, [rsp+1E0h+hKey]
0x180094d66  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180094d6b  nop
0x180094d6c  xor     eax, eax
0x180094d6e  mov     rcx, [rbp+0E0h+var_10]
0x180094d75  xor     rcx, rsp; StackCookie
0x180094d78  call    __security_check_cookie
0x180094d7d  mov     rbx, [rsp+1E0h+arg_0]
0x180094d85  add     rsp, 1E0h
0x180094d8c  pop     rbp
0x180094d8d  retn
```
