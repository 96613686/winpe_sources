# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18009ea90`
- end: `0x18009ebe1`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `337`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009e624`
- `0x18009eccc`
- `0x1800a1970`

## callees

- `0x180004eb0`
- `0x1800053e0`
- `0x180016698`
- `0x180017118`
- `0x180020cb0`
- `0x18002a028`
- `0x180036d48`
- `0x18009e934`
- `0x18009ea90`
- `0x18009f05c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009eb23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009eb23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eae9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eae9`

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
0x18009ea90  mov     [rsp-8+arg_0], rbx
0x18009ea95  push    rbp
0x18009ea96  lea     rbp, [rsp-57h]
0x18009ea9b  sub     rsp, 0A0h
0x18009eaa2  mov     rax, cs:__security_cookie
0x18009eaa9  xor     rax, rsp
0x18009eaac  mov     [rbp+57h+var_10], rax
0x18009eab0  mov     rbx, rdx
0x18009eab3  mov     [rbp+57h+hKey], 0
0x18009eabb  xor     edx, edx
0x18009eabd  lea     rcx, [rbp+57h+hKey]
0x18009eac1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009eac6  xor     ecx, ecx
0x18009eac8  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009eacd  lea     rcx, [rbp+57h+hKey]
0x18009ead1  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x18009ead6  mov     r9d, 20019h; samDesired
0x18009eadc  xor     r8d, r8d; ulOptions
0x18009eadf  mov     rdx, rax; lpSubKey
0x18009eae2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009eae9  call    cs:__imp_RegOpenKeyExW
0x18009eaf0  nop     dword ptr [rax+rax+00h]
0x18009eaf5  test    eax, eax
0x18009eaf7  jnz     short loc_18009EB45
0x18009eaf9  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18009eb00  lea     rax, [rbp+57h+cbData]
0x18009eb04  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18009eb09  lea     rax, [rbp+57h+Data]
0x18009eb0d  mov     [rsp+0A0h+phkResult], rax; lpData
0x18009eb12  xor     r9d, r9d; lpType
0x18009eb15  xor     r8d, r8d; lpReserved
0x18009eb18  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18009eb1f  mov     rcx, [rbp+57h+hKey]; hKey
0x18009eb23  call    cs:__imp_RegQueryValueExW
0x18009eb2a  nop     dword ptr [rax+rax+00h]
0x18009eb2f  test    eax, eax
0x18009eb31  jnz     short loc_18009EB45
0x18009eb33  mov     r9, [rbp+57h+hKey]; HKEY
0x18009eb37  mov     r8, rbx; char *
0x18009eb3a  lea     rdx, [rbp+57h+Data]; unsigned __int16 *
0x18009eb3e  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18009eb43  jmp     short loc_18009EB4F
0x18009eb45  jle     short loc_18009EB4F
0x18009eb47  movzx   eax, ax
0x18009eb4a  or      eax, 80070000h
0x18009eb4f  test    eax, eax
0x18009eb51  jns     short loc_18009EB9D
0x18009eb53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009eb5a  mov     ecx, 90h; unsigned __int64
0x18009eb5f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009eb64  mov     qword ptr [rbp+57h+cbData], rax
0x18009eb68  test    rax, rax
0x18009eb6b  jz      short loc_18009EBC8
0x18009eb6d  mov     rcx, rax
0x18009eb70  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18009eb75  mov     qword ptr [rbp+57h+cbData], rax
0x18009eb79  test    rax, rax
0x18009eb7c  jz      short loc_18009EBD0
0x18009eb7e  xor     edx, edx
0x18009eb80  lock xadd [rax+88h], rdx; unsigned __int64
0x18009eb89  mov     r8, rbx; char *
0x18009eb8c  mov     rcx, rax; this
0x18009eb8f  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18009eb94  lea     rcx, [rbp+57h+cbData]
0x18009eb98  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18009eb9d  xor     ebx, ebx
0x18009eb9f  lea     rcx, [rbp+57h+hKey]
0x18009eba3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009eba8  mov     eax, ebx
0x18009ebaa  mov     rcx, [rbp+57h+var_10]
0x18009ebae  xor     rcx, rsp; StackCookie
0x18009ebb1  call    __security_check_cookie
0x18009ebb6  mov     rbx, [rsp+0A0h+arg_0]
0x18009ebbe  add     rsp, 0A0h
0x18009ebc5  pop     rbp
0x18009ebc6  retn
0x18009ebc8  mov     qword ptr [rbp+57h+cbData], 0
0x18009ebd0  lea     rcx, [rbp+57h+cbData]
0x18009ebd4  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18009ebd9  mov     ebx, 8007000Eh
0x18009ebde  jmp     short loc_18009EB9F
```
