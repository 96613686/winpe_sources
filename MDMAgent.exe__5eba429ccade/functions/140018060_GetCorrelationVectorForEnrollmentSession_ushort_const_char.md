# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x140018060`
- end: `0x1400182ab`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `587`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400177b0`

## callees

- `0x140002930`
- `0x14000356c`
- `0x140004b0c`
- `0x1400051cc`
- `0x1400072bc`
- `0x140007b34`
- `0x14000b288`
- `0x1400176f4`
- `0x14001775c`
- `0x14001778c`
- `0x140017efc`
- `0x140018060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018104`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018179`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018104`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018179`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400180c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400180c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018146`
- `DMCmnUtils!UnicodeToMB` at `0x1400181c1`
- `DMCmnUtils!UnicodeToMB` at `0x1400181c1`

## pseudocode

```c
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
  byte_1400248D0 = 0;
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
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>((__int64)&v20);
      v8 = v14;
      if ( v4 >= 0 && v14 )
      {
        v4 = StringCchCopyA(&byte_1400248D0, 0x81u, (const char *)v14);
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
      v11 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v9);
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
0x140018060  mov     [rsp-8+arg_0], rbx
0x140018065  push    rbp
0x140018066  lea     rbp, [rsp-0E0h]
0x14001806e  sub     rsp, 1E0h
0x140018075  mov     rax, cs:__security_cookie
0x14001807c  xor     rax, rsp
0x14001807f  mov     [rbp+0E0h+var_10], rax
0x140018086  mov     [rsp+1E0h+hKey], 0
0x14001808f  mov     cs:byte_1400248D0, 0
0x140018096  xor     edx, edx
0x140018098  lea     rcx, [rsp+1E0h+hKey]
0x14001809d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1400180a2  xor     ecx, ecx
0x1400180a4  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1400180a9  lea     rcx, [rsp+1E0h+hKey]
0x1400180ae  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x1400180b3  mov     r9d, 20019h; samDesired
0x1400180b9  xor     r8d, r8d; ulOptions
0x1400180bc  mov     rdx, rax; lpSubKey
0x1400180bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400180c6  call    cs:__imp_RegOpenKeyExW
0x1400180cc  mov     ebx, eax
0x1400180ce  test    eax, eax
0x1400180d0  jnz     loc_140018229
0x1400180d6  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x1400180de  lea     rax, [rsp+1E0h+cbData]
0x1400180e3  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1400180e8  lea     rax, [rsp+1E0h+Data]
0x1400180ed  mov     [rsp+1E0h+phkResult], rax; lpData
0x1400180f2  xor     r9d, r9d; lpType
0x1400180f5  xor     r8d, r8d; lpReserved
0x1400180f8  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1400180ff  mov     rcx, [rsp+1E0h+hKey]; hKey
0x140018104  call    cs:__imp_RegQueryValueExW
0x14001810a  mov     ebx, eax
0x14001810c  test    eax, eax
0x14001810e  jnz     loc_140018229
0x140018114  mov     [rsp+1E0h+var_1A0], 0
0x14001811d  xor     edx, edx
0x14001811f  lea     rcx, [rsp+1E0h+var_1A0]
0x140018124  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140018129  lea     rax, [rsp+1E0h+var_1A0]
0x14001812e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x140018133  mov     r9d, 20019h; samDesired
0x140018139  xor     r8d, r8d; ulOptions
0x14001813c  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x140018141  mov     rcx, [rsp+1E0h+hKey]; hKey
0x140018146  call    cs:__imp_RegOpenKeyExW
0x14001814c  mov     [rsp+1E0h+var_194], 102h
0x140018154  lea     rax, [rsp+1E0h+var_194]
0x140018159  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x14001815e  lea     rax, [rbp+0E0h+var_120]
0x140018162  mov     [rsp+1E0h+phkResult], rax; lpData
0x140018167  xor     r9d, r9d; lpType
0x14001816a  xor     r8d, r8d; lpReserved
0x14001816d  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x140018174  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x140018179  call    cs:__imp_RegQueryValueExW
0x14001817f  mov     ebx, eax
0x140018181  test    eax, eax
0x140018183  jnz     loc_140018211
0x140018189  mov     [rsp+1E0h+var_1B0], 0
0x140018192  mov     [rsp+1E0h+var_190], eax
0x140018196  lea     rax, [rsp+1E0h+var_1B0]
0x14001819b  mov     [rsp+1E0h+var_188], rax
0x1400181a0  mov     [rsp+1E0h+var_180], 0
0x1400181a9  mov     [rsp+1E0h+var_178], 1
0x1400181ae  lea     r9, [rsp+1E0h+var_190]
0x1400181b3  lea     r8, [rsp+1E0h+var_180]
0x1400181b8  mov     edx, 0FDE9h
0x1400181bd  lea     rcx, [rbp+0E0h+var_120]
0x1400181c1  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1400181c7  mov     ebx, eax
0x1400181c9  lea     rcx, [rsp+1E0h+var_188]
0x1400181ce  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x1400181d3  mov     rcx, [rsp+1E0h+var_1B0]
0x1400181d8  test    ebx, ebx
0x1400181da  js      short loc_1400181FC
0x1400181dc  test    rcx, rcx
0x1400181df  jz      short loc_1400181FC
0x1400181e1  mov     r8, rcx; char *
0x1400181e4  mov     edx, 81h; unsigned __int64
0x1400181e9  lea     rcx, byte_1400248D0; char *
0x1400181f0  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1400181f5  mov     ebx, eax
0x1400181f7  mov     rcx, [rsp+1E0h+var_1B0]; this
0x1400181fc  mov     [rsp+1E0h+var_1B0], 0
0x140018205  test    rcx, rcx
0x140018208  jz      short loc_14001821C
0x14001820a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14001820f  jmp     short loc_14001821C
0x140018211  jle     short loc_14001821C
0x140018213  movzx   ebx, ax
0x140018216  or      ebx, 80070000h
0x14001821c  lea     rcx, [rsp+1E0h+var_1A0]
0x140018221  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140018226  nop
0x140018227  jmp     short loc_140018234
0x140018229  jle     short loc_140018234
0x14001822b  movzx   ebx, ax
0x14001822e  or      ebx, 80070000h
0x140018234  test    ebx, ebx
0x140018236  jns     short loc_14001827E
0x140018238  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001823f  mov     ecx, 90h; unsigned __int64
0x140018244  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140018249  test    rax, rax
0x14001824c  jz      short loc_14001825B
0x14001824e  mov     rcx, rax
0x140018251  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x140018256  mov     rbx, rax
0x140018259  jmp     short loc_14001825D
0x14001825b  xor     ebx, ebx
0x14001825d  xor     edx, edx
0x14001825f  lock xadd [rbx+88h], rdx; unsigned __int64
0x140018268  mov     rcx, rbx; this
0x14001826b  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x140018270  test    rbx, rbx
0x140018273  jz      short loc_14001827E
0x140018275  mov     rcx, rbx; this
0x140018278  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x14001827d  nop
0x14001827e  lea     rcx, [rsp+1E0h+hKey]
0x140018283  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140018288  nop
0x140018289  xor     eax, eax
0x14001828b  mov     rcx, [rbp+0E0h+var_10]
0x140018292  xor     rcx, rsp; StackCookie
0x140018295  call    __security_check_cookie
0x14001829a  mov     rbx, [rsp+1E0h+arg_0]
0x1400182a2  add     rsp, 1E0h
0x1400182a9  pop     rbp
0x1400182aa  retn
```
