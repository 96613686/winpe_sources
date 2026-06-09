# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18009bc4c`
- end: `0x18009bd90`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `324`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b7fc`
- `0x18009be78`
- `0x18009e96c`

## callees

- `0x180004d50`
- `0x180005280`
- `0x180015f70`
- `0x1800169b8`
- `0x180022668`
- `0x18002b664`
- `0x180037aa0`
- `0x18009bb08`
- `0x18009bc4c`
- `0x18009c1f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bcd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009bcd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bca5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v3 = (const WCHAR *)DMGetKnownRegPath(0);
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
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)cbData = v7;
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
0x18009bc4c  mov     [rsp-8+arg_0], rbx
0x18009bc51  push    rbp
0x18009bc52  lea     rbp, [rsp-57h]
0x18009bc57  sub     rsp, 0A0h
0x18009bc5e  mov     rax, cs:__security_cookie
0x18009bc65  xor     rax, rsp
0x18009bc68  mov     [rbp+57h+var_10], rax
0x18009bc6c  mov     rbx, rdx
0x18009bc6f  mov     [rbp+57h+hKey], 0
0x18009bc77  xor     edx, edx
0x18009bc79  lea     rcx, [rbp+57h+hKey]
0x18009bc7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009bc82  xor     ecx, ecx
0x18009bc84  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009bc89  lea     rcx, [rbp+57h+hKey]
0x18009bc8d  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x18009bc92  mov     r9d, 20019h; samDesired
0x18009bc98  xor     r8d, r8d; ulOptions
0x18009bc9b  mov     rdx, rax; lpSubKey
0x18009bc9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009bca5  call    cs:__imp_RegOpenKeyExW
0x18009bcab  test    eax, eax
0x18009bcad  jnz     short loc_18009BCF5
0x18009bcaf  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18009bcb6  lea     rax, [rbp+57h+cbData]
0x18009bcba  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18009bcbf  lea     rax, [rbp+57h+Data]
0x18009bcc3  mov     [rsp+0A0h+phkResult], rax; lpData
0x18009bcc8  xor     r9d, r9d; lpType
0x18009bccb  xor     r8d, r8d; lpReserved
0x18009bcce  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18009bcd5  mov     rcx, [rbp+57h+hKey]; hKey
0x18009bcd9  call    cs:__imp_RegQueryValueExW
0x18009bcdf  test    eax, eax
0x18009bce1  jnz     short loc_18009BCF5
0x18009bce3  mov     r9, [rbp+57h+hKey]; HKEY
0x18009bce7  mov     r8, rbx; char *
0x18009bcea  lea     rdx, [rbp+57h+Data]; unsigned __int16 *
0x18009bcee  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18009bcf3  jmp     short loc_18009BCFF
0x18009bcf5  jle     short loc_18009BCFF
0x18009bcf7  movzx   eax, ax
0x18009bcfa  or      eax, 80070000h
0x18009bcff  test    eax, eax
0x18009bd01  jns     short loc_18009BD4D
0x18009bd03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009bd0a  mov     ecx, 90h; unsigned __int64
0x18009bd0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009bd14  mov     qword ptr [rbp+57h+cbData], rax
0x18009bd18  test    rax, rax
0x18009bd1b  jz      short loc_18009BD77
0x18009bd1d  mov     rcx, rax
0x18009bd20  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18009bd25  mov     qword ptr [rbp+57h+cbData], rax
0x18009bd29  test    rax, rax
0x18009bd2c  jz      short loc_18009BD7F
0x18009bd2e  xor     edx, edx
0x18009bd30  lock xadd [rax+88h], rdx; unsigned __int64
0x18009bd39  mov     r8, rbx; char *
0x18009bd3c  mov     rcx, rax; this
0x18009bd3f  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18009bd44  lea     rcx, [rbp+57h+cbData]
0x18009bd48  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18009bd4d  xor     ebx, ebx
0x18009bd4f  lea     rcx, [rbp+57h+hKey]
0x18009bd53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009bd58  mov     eax, ebx
0x18009bd5a  mov     rcx, [rbp+57h+var_10]
0x18009bd5e  xor     rcx, rsp; StackCookie
0x18009bd61  call    __security_check_cookie
0x18009bd66  mov     rbx, [rsp+0A0h+arg_0]
0x18009bd6e  add     rsp, 0A0h
0x18009bd75  pop     rbp
0x18009bd76  retn
0x18009bd77  mov     qword ptr [rbp+57h+cbData], 0
0x18009bd7f  lea     rcx, [rbp+57h+cbData]
0x18009bd83  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18009bd88  mov     ebx, 8007000Eh
0x18009bd8d  jmp     short loc_18009BD4F
```
