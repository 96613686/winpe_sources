# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18005d1d4`
- end: `0x18005d31e`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `330`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c118`
- `0x18005d324`
- `0x180095590`

## callees

- `0x180007270`
- `0x1800520f0`
- `0x18005cf3c`
- `0x18005d010`
- `0x18005d058`
- `0x18005d088`
- `0x18005d1d4`
- `0x18005d5a0`
- `0x18005d6b8`
- `0x18005d6e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d22b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d22b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005d265`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005d265`

## pseudocode

```c
__int64 __fastcall GetCorrelationVectorForDmSession(const unsigned __int16 *a1, char *a2)
{
  const WCHAR *v3; // rax
  int ComponentCVForEnrollmentId; // eax
  bool v5; // cc
  const unsigned __int16 *v6; // rcx
  void *v7; // rax
  volatile signed __int64 *v8; // rax
  unsigned int v9; // ebx
  DWORD cbData[2]; // [rsp+30h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int16 Data[40]; // [rsp+40h] [rbp-9h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = (const WCHAR *)DMGetKnownRegPath();
  ComponentCVForEnrollmentId = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = ComponentCVForEnrollmentId <= 0;
  if ( ComponentCVForEnrollmentId
    || (cbData[0] = 78,
        ComponentCVForEnrollmentId = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, cbData),
        v5 = ComponentCVForEnrollmentId <= 0,
        ComponentCVForEnrollmentId) )
  {
    if ( !v5 )
      ComponentCVForEnrollmentId = (unsigned __int16)ComponentCVForEnrollmentId | 0x80070000;
  }
  else
  {
    ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(v6, Data, a2, hKey);
  }
  if ( ComponentCVForEnrollmentId >= 0 )
    goto LABEL_10;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7 )
  {
    *(_QWORD *)cbData = 0;
    goto LABEL_13;
  }
  v8 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v7);
  *(_QWORD *)cbData = v8;
  if ( !v8 )
  {
LABEL_13:
    wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(cbData);
    v9 = -2147024882;
    goto LABEL_11;
  }
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v8,
    _InterlockedExchangeAdd64(v8 + 17, 0),
    a2);
  wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(cbData);
LABEL_10:
  v9 = 0;
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x18005d1d4  mov     [rsp-8+arg_0], rbx
0x18005d1d9  push    rbp
0x18005d1da  lea     rbp, [rsp-57h]
0x18005d1df  sub     rsp, 0A0h
0x18005d1e6  mov     rax, cs:__security_cookie
0x18005d1ed  xor     rax, rsp
0x18005d1f0  mov     [rbp+57h+var_10], rax
0x18005d1f4  mov     rbx, rdx
0x18005d1f7  mov     [rbp+57h+hKey], 0
0x18005d1ff  xor     edx, edx
0x18005d201  lea     rcx, [rbp+57h+hKey]
0x18005d205  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005d20a  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18005d20f  lea     rcx, [rbp+57h+hKey]
0x18005d213  mov     r9d, 20019h; samDesired
0x18005d219  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x18005d21e  xor     r8d, r8d; ulOptions
0x18005d221  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005d228  mov     rdx, rax; lpSubKey
0x18005d22b  call    cs:__imp_RegOpenKeyExW
0x18005d232  nop     dword ptr [rax+rax+00h]
0x18005d237  test    eax, eax
0x18005d239  jnz     short loc_18005D287
0x18005d23b  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d23f  lea     rax, [rbp+57h+cbData]
0x18005d243  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18005d248  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18005d24f  lea     rax, [rbp+57h+Data]
0x18005d253  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18005d25a  xor     r9d, r9d; lpType
0x18005d25d  mov     [rsp+0A0h+phkResult], rax; lpData
0x18005d262  xor     r8d, r8d; lpReserved
0x18005d265  call    cs:__imp_RegQueryValueExW
0x18005d26c  nop     dword ptr [rax+rax+00h]
0x18005d271  test    eax, eax
0x18005d273  jnz     short loc_18005D287
0x18005d275  mov     r9, [rbp+57h+hKey]; HKEY
0x18005d279  lea     rdx, [rbp+57h+Data]; unsigned __int16 *
0x18005d27d  mov     r8, rbx; char *
0x18005d280  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18005d285  jmp     short loc_18005D291
0x18005d287  jle     short loc_18005D291
0x18005d289  movzx   eax, ax
0x18005d28c  or      eax, 80070000h
0x18005d291  test    eax, eax
0x18005d293  jns     short loc_18005D2DB
0x18005d295  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d29c  mov     ecx, 90h; unsigned __int64
0x18005d2a1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d2a6  test    rax, rax
0x18005d2a9  jz      short loc_18005D306
0x18005d2ab  mov     rcx, rax
0x18005d2ae  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18005d2b3  mov     qword ptr [rbp+57h+cbData], rax
0x18005d2b7  test    rax, rax
0x18005d2ba  jz      short loc_18005D30E
0x18005d2bc  xor     edx, edx
0x18005d2be  lock xadd [rax+88h], rdx; unsigned __int64
0x18005d2c7  mov     r8, rbx; char *
0x18005d2ca  mov     rcx, rax; this
0x18005d2cd  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18005d2d2  lea     rcx, [rbp+57h+cbData]
0x18005d2d6  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18005d2db  xor     ebx, ebx
0x18005d2dd  lea     rcx, [rbp+57h+hKey]
0x18005d2e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005d2e6  mov     eax, ebx
0x18005d2e8  mov     rcx, [rbp+57h+var_10]
0x18005d2ec  xor     rcx, rsp; StackCookie
0x18005d2ef  call    __security_check_cookie
0x18005d2f4  mov     rbx, [rsp+0A0h+arg_0]
0x18005d2fc  add     rsp, 0A0h
0x18005d303  pop     rbp
0x18005d304  retn
0x18005d306  mov     qword ptr [rbp+57h+cbData], 0
0x18005d30e  lea     rcx, [rbp+57h+cbData]
0x18005d312  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18005d317  mov     ebx, 8007000Eh
0x18005d31c  jmp     short loc_18005D2DD
```
