# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x18001c220`
- end: `0x18001c47b`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `603`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001b9d8`

## callees

- `0x180001c60`
- `0x180002808`
- `0x18000516c`
- `0x180005a38`
- `0x1800075e8`
- `0x18000a2f4`
- `0x180011828`
- `0x180016c98`
- `0x18001b914`
- `0x18001b984`
- `0x18001b9b4`
- `0x18001c0ac`
- `0x18001c220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c312`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c2ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c34b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c2ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c34b`

## pseudocode

```c
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(const unsigned __int16 *a1, char *a2)
{
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  bool v5; // cc
  LSTATUS v6; // eax
  unsigned int v7; // edx
  void *v8; // rdx
  wil::details *v9; // rcx
  signed int v10; // eax
  void *v11; // rax
  char *v12; // r8
  volatile signed __int64 *v13; // rbx
  unsigned int v14; // edx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  wil::details **v22; // [rsp+58h] [rbp-A8h] BYREF
  char *v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v26[136]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  byte_180029D50 = 0;
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
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v26, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v21 = 0;
      v16 = 0;
      v22 = &v16;
      v23 = 0;
      v24 = 1;
      v4 = UnicodeToMB(v26, v7, &v23, &v21);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v22);
      v9 = v16;
      if ( v4 >= 0 && v16 )
      {
        v10 = StringCchCopyA(&byte_180029D50, 0x81u, (const char *)v16);
        v9 = v16;
        v4 = v10;
      }
      v16 = 0;
      if ( v9 )
        wil::details::FreeProcessHeap(v9, v8);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  if ( v4 < 0 )
  {
    v11 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
      v13 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v11);
    else
      v13 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v13,
      _InterlockedExchangeAdd64(v13 + 17, 0),
      v12);
    if ( v13 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v13, v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18001c220  mov     [rsp-8+arg_0], rbx
0x18001c225  push    rbp
0x18001c226  lea     rbp, [rsp-0E0h]
0x18001c22e  sub     rsp, 1E0h
0x18001c235  mov     rax, cs:__security_cookie
0x18001c23c  xor     rax, rsp
0x18001c23f  mov     [rbp+0E0h+var_10], rax
0x18001c246  xor     edx, edx
0x18001c248  mov     [rsp+1E0h+hKey], 0
0x18001c251  lea     rcx, [rsp+1E0h+hKey]
0x18001c256  mov     cs:byte_180029D50, 0
0x18001c25d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001c262  xor     ecx, ecx
0x18001c264  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18001c269  lea     rcx, [rsp+1E0h+hKey]
0x18001c26e  mov     r9d, 20019h; samDesired
0x18001c274  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x18001c279  xor     r8d, r8d; ulOptions
0x18001c27c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c283  mov     rdx, rax; lpSubKey
0x18001c286  call    cs:__imp_RegOpenKeyExW
0x18001c28d  nop     dword ptr [rax+rax+00h]
0x18001c292  mov     ebx, eax
0x18001c294  test    eax, eax
0x18001c296  jnz     loc_18001C3FA
0x18001c29c  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001c2a1  lea     rax, [rsp+1E0h+cbData]
0x18001c2a6  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18001c2ab  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18001c2b2  lea     rax, [rsp+1E0h+Data]
0x18001c2b7  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x18001c2bf  xor     r9d, r9d; lpType
0x18001c2c2  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001c2c7  xor     r8d, r8d; lpReserved
0x18001c2ca  call    cs:__imp_RegQueryValueExW
0x18001c2d1  nop     dword ptr [rax+rax+00h]
0x18001c2d6  mov     ebx, eax
0x18001c2d8  test    eax, eax
0x18001c2da  jnz     loc_18001C3FA
0x18001c2e0  xor     edx, edx
0x18001c2e2  mov     [rsp+1E0h+var_1A0], 0
0x18001c2eb  lea     rcx, [rsp+1E0h+var_1A0]
0x18001c2f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001c2f5  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001c2fa  lea     rax, [rsp+1E0h+var_1A0]
0x18001c2ff  mov     r9d, 20019h; samDesired
0x18001c305  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001c30a  xor     r8d, r8d; ulOptions
0x18001c30d  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x18001c312  call    cs:__imp_RegOpenKeyExW
0x18001c319  nop     dword ptr [rax+rax+00h]
0x18001c31e  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x18001c323  lea     rax, [rsp+1E0h+var_194]
0x18001c328  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18001c32d  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x18001c334  lea     rax, [rbp+0E0h+var_120]
0x18001c338  mov     [rsp+1E0h+var_194], 102h
0x18001c340  xor     r9d, r9d; lpType
0x18001c343  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001c348  xor     r8d, r8d; lpReserved
0x18001c34b  call    cs:__imp_RegQueryValueExW
0x18001c352  nop     dword ptr [rax+rax+00h]
0x18001c357  mov     ebx, eax
0x18001c359  test    eax, eax
0x18001c35b  jnz     loc_18001C3E3
0x18001c361  mov     [rsp+1E0h+var_190], eax
0x18001c365  lea     r9, [rsp+1E0h+var_190]; unsigned int *
0x18001c36a  lea     rax, [rsp+1E0h+var_1B0]
0x18001c36f  mov     [rsp+1E0h+var_1B0], 0
0x18001c378  lea     r8, [rsp+1E0h+var_180]; char **
0x18001c37d  mov     [rsp+1E0h+var_188], rax
0x18001c382  lea     rcx, [rbp+0E0h+var_120]; lpWideCharStr
0x18001c386  mov     [rsp+1E0h+var_180], 0
0x18001c38f  mov     [rsp+1E0h+var_178], 1
0x18001c394  call    ?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18001c399  lea     rcx, [rsp+1E0h+var_188]
0x18001c39e  mov     ebx, eax
0x18001c3a0  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x18001c3a5  mov     rcx, [rsp+1E0h+var_1B0]
0x18001c3aa  test    ebx, ebx
0x18001c3ac  js      short loc_18001C3CE
0x18001c3ae  test    rcx, rcx
0x18001c3b1  jz      short loc_18001C3CE
0x18001c3b3  mov     r8, rcx; char *
0x18001c3b6  mov     edx, 81h; unsigned __int64
0x18001c3bb  lea     rcx, byte_180029D50; char *
0x18001c3c2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001c3c7  mov     rcx, [rsp+1E0h+var_1B0]; this
0x18001c3cc  mov     ebx, eax
0x18001c3ce  mov     [rsp+1E0h+var_1B0], 0
0x18001c3d7  test    rcx, rcx
0x18001c3da  jz      short loc_18001C3EE
0x18001c3dc  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001c3e1  jmp     short loc_18001C3EE
0x18001c3e3  jle     short loc_18001C3EE
0x18001c3e5  movzx   ebx, ax
0x18001c3e8  or      ebx, 80070000h
0x18001c3ee  lea     rcx, [rsp+1E0h+var_1A0]
0x18001c3f3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c3f8  jmp     short loc_18001C405
0x18001c3fa  jle     short loc_18001C405
0x18001c3fc  movzx   ebx, ax
0x18001c3ff  or      ebx, 80070000h
0x18001c405  test    ebx, ebx
0x18001c407  jns     short loc_18001C44E
0x18001c409  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c410  mov     ecx, 90h; unsigned __int64
0x18001c415  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c41a  test    rax, rax
0x18001c41d  jz      short loc_18001C42C
0x18001c41f  mov     rcx, rax
0x18001c422  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18001c427  mov     rbx, rax
0x18001c42a  jmp     short loc_18001C42E
0x18001c42c  xor     ebx, ebx
0x18001c42e  xor     edx, edx
0x18001c430  lock xadd [rbx+88h], rdx; unsigned __int64
0x18001c439  mov     rcx, rbx; this
0x18001c43c  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001c441  test    rbx, rbx
0x18001c444  jz      short loc_18001C44E
0x18001c446  mov     rcx, rbx; this
0x18001c449  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18001c44e  lea     rcx, [rsp+1E0h+hKey]
0x18001c453  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001c458  xor     eax, eax
0x18001c45a  mov     rcx, [rbp+0E0h+var_10]
0x18001c461  xor     rcx, rsp; StackCookie
0x18001c464  call    __security_check_cookie
0x18001c469  mov     rbx, [rsp+1E0h+arg_0]
0x18001c471  add     rsp, 1E0h
0x18001c478  pop     rbp
0x18001c479  retn
```
