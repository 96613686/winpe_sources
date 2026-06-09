# CNonClusterTmInstance::PerfCounterMutexNameAndSDDL(ushort * *,ushort * *)

- ea: `0x180002200`
- end: `0x18000239d`
- name: `?PerfCounterMutexNameAndSDDL@CNonClusterTmInstance@@UEAAJPEAPEAG0@Z`
- size: `413`
- prototype: `__int64 __fastcall(CNonClusterTmInstance *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002200`
- `0x180003cf0`
- `0x180006764`
- `0x18000d5f4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000236e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000236e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002381`

## string_xrefs

- `0x180002279`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x18000232d`: `com\complus\dtc\dtc\adme\nonclustertminstance.cpp`
- `0x1800022e4`: `GetServiceSidString failed.`
- `0x180002233`: `CNonClusterTmInstance::PerfCounterMutexNameAndSDDL (com\complus\dtc\dtc\adme\nonclustertminstance.cpp@1379): NULL != ppwszMutexName`
- `0x180002245`: `CNonClusterTmInstance::PerfCounterMutexNameAndSDDL (com\complus\dtc\dtc\adme\nonclustertminstance.cpp@1380): NULL != ppwszSDDL`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::PerfCounterMutexNameAndSDDL(
        CNonClusterTmInstance *this,
        LPVOID *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  int StringW; // ebx
  const wchar_t *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v12; // [rsp+28h] [rbp-28h]
  LPVOID v13[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int16 *v15; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  pv = 0;
  v15 = 0;
  v13[0] = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"CNonClusterTmInstance::PerfCounterMutexNameAndSDDL (com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp@1379): "
       "NULL != ppwszMutexName");
  if ( !a3 )
    DtcInternalErrorW(
      L"CNonClusterTmInstance::PerfCounterMutexNameAndSDDL (com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp@1380): "
       "NULL != ppwszSDDL");
  *a2 = 0;
  *a3 = 0;
  if ( *((_DWORD *)this + 6) )
  {
    StringW = -2147168241;
    v8 = L"Request made for a RemoteProxyTmInstance - not supported.";
    v9 = 1389;
LABEL_7:
    v10 = 7;
LABEL_8:
    LODWORD(v12) = StringW;
    TraceStringInline(
      v10,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
      v9,
      L"CNonClusterTmInstance::PerfCounterMutexNameAndSDDL",
      v12,
      v8);
    goto LABEL_16;
  }
  StringW = MakeStringW((unsigned __int16 **)&pv, L"%s", L"Global\\MSDTC_STATS_EVENT");
  if ( StringW < 0 )
  {
    v8 = L"Error from MakeStringW for MutexName";
    v9 = 1396;
    goto LABEL_7;
  }
  StringW = (*(__int64 (__fastcall **)(CNonClusterTmInstance *, LPVOID *))(*(_QWORD *)this + 72LL))(this, v13);
  if ( StringW < 0 )
  {
    v8 = L"GetServiceSidString failed.";
    v9 = 1402;
    v10 = 8;
    goto LABEL_8;
  }
  StringW = MakeStringW(
              &v15,
              L"%s%s)",
              L"D:(A;OICI;0x100000;;;WD)(A;OICI;0x1f0001;;;BA)(A;OICI;0x1f0001;;;SY)(A;OICI;0x120001;;;",
              v13[0]);
  if ( StringW >= 0 )
  {
    *a2 = pv;
    *a3 = v15;
    pv = 0;
  }
  else
  {
    LODWORD(v12) = StringW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\dtc\\adme\\nonclustertminstance.cpp",
      1408,
      L"CNonClusterTmInstance::PerfCounterMutexNameAndSDDL",
      v12,
      L"Error from MakeStringW for SDDL");
    v3 = v15;
  }
LABEL_16:
  CoTaskMemFree(pv);
  CoTaskMemFree(v3);
  CoTaskMemFree(v13[0]);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180002200  mov     [rsp-28h+arg_0], rbx
0x180002205  push    rbp
0x180002206  push    rsi
0x180002207  push    rdi
0x180002208  push    r14
0x18000220a  push    r15
0x18000220c  mov     rbp, rsp
0x18000220f  sub     rsp, 50h
0x180002213  xor     esi, esi
0x180002215  mov     [rbp+pv], 0
0x18000221d  mov     [rbp+arg_18], rsi
0x180002221  mov     rdi, r8
0x180002224  mov     [rbp+var_10], rsi
0x180002228  mov     r14, rdx
0x18000222b  mov     r15, rcx
0x18000222e  test    rdx, rdx
0x180002231  jnz     short loc_180002240
0x180002233  lea     rcx, aCnonclustertmi_5; "CNonClusterTmInstance::PerfCounterMutex"...
0x18000223a  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180002240  test    rdi, rdi
0x180002243  jnz     short loc_180002252
0x180002245  lea     rcx, aCnonclustertmi_0; "CNonClusterTmInstance::PerfCounterMutex"...
0x18000224c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180002252  mov     [rdx], rsi
0x180002255  mov     [r8], rsi
0x180002258  cmp     [rcx+18h], esi
0x18000225b  jz      short loc_18000229F
0x18000225d  mov     ebx, 8004D00Fh
0x180002262  lea     rax, aRequestMadeFor; "Request made for a RemoteProxyTmInstanc"...
0x180002269  mov     r9d, 56Dh
0x18000226f  mov     ecx, 7
0x180002274  mov     [rsp+50h+var_20], rax
0x180002279  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x180002280  lea     rax, aCnonclustertmi_9; "CNonClusterTmInstance::PerfCounterMutex"...
0x180002287  mov     dword ptr [rsp+50h+var_28], ebx
0x18000228b  mov     edx, 1
0x180002290  mov     [rsp+50h+var_30], rax
0x180002295  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000229a  jmp     loc_18000236A
0x18000229f  lea     r8, aGlobalMsdtcSta_0; "Global\\MSDTC_STATS_EVENT"
0x1800022a6  lea     rdx, aS; "%s"
0x1800022ad  lea     rcx, [rbp+pv]; unsigned __int16 **
0x1800022b1  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x1800022b6  mov     ebx, eax
0x1800022b8  test    eax, eax
0x1800022ba  jns     short loc_1800022CB
0x1800022bc  lea     rax, aErrorFromMakes_1; "Error from MakeStringW for MutexName"
0x1800022c3  mov     r9d, 574h
0x1800022c9  jmp     short loc_18000226F
0x1800022cb  mov     rax, [r15]
0x1800022ce  lea     rdx, [rbp+var_10]
0x1800022d2  mov     rcx, r15
0x1800022d5  mov     rax, [rax+48h]
0x1800022d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022de  mov     ebx, eax
0x1800022e0  test    eax, eax
0x1800022e2  jns     short loc_1800022FB
0x1800022e4  lea     rax, aGetservicesids; "GetServiceSidString failed."
0x1800022eb  mov     r9d, 57Ah
0x1800022f1  mov     ecx, 8
0x1800022f6  jmp     loc_180002274
0x1800022fb  mov     r9, [rbp+var_10]
0x1800022ff  lea     r8, aDAOici0x100000; "D:(A;OICI;0x100000;;;WD)(A;OICI;0x1f000"...
0x180002306  lea     rdx, aSS_2; "%s%s)"
0x18000230d  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180002311  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180002316  mov     ebx, eax
0x180002318  test    eax, eax
0x18000231a  jns     short loc_180002358
0x18000231c  mov     edx, 1
0x180002321  lea     rax, aErrorFromMakes_0; "Error from MakeStringW for SDDL"
0x180002328  mov     [rsp+50h+var_20], rax
0x18000232d  lea     r8, aComComplusDtcD_46; "com\\complus\\dtc\\dtc\\adme\\noncluste"...
0x180002334  lea     rax, aCnonclustertmi_9; "CNonClusterTmInstance::PerfCounterMutex"...
0x18000233b  mov     dword ptr [rsp+50h+var_28], ebx
0x18000233f  mov     r9d, 580h
0x180002345  mov     [rsp+50h+var_30], rax
0x18000234a  lea     ecx, [rdx+6]
0x18000234d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002352  mov     rsi, [rbp+arg_18]
0x180002356  jmp     short loc_18000236A
0x180002358  mov     rax, [rbp+pv]
0x18000235c  mov     [r14], rax
0x18000235f  mov     rax, [rbp+arg_18]
0x180002363  mov     [rdi], rax
0x180002366  mov     [rbp+pv], rsi
0x18000236a  mov     rcx, [rbp+pv]; pv
0x18000236e  call    cs:__imp_CoTaskMemFree
0x180002374  mov     rcx, rsi; pv
0x180002377  call    cs:__imp_CoTaskMemFree
0x18000237d  mov     rcx, [rbp+var_10]; pv
0x180002381  call    cs:__imp_CoTaskMemFree
0x180002387  mov     eax, ebx
0x180002389  mov     rbx, [rsp+50h+arg_0]
0x180002391  add     rsp, 50h
0x180002395  pop     r15
0x180002397  pop     r14
0x180002399  pop     rdi
0x18000239a  pop     rsi
0x18000239b  pop     rbp
0x18000239c  retn
```
