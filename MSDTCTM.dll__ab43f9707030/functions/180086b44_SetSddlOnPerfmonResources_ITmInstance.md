# SetSddlOnPerfmonResources(ITmInstance *)

- ea: `0x180086b44`
- end: `0x180086d50`
- name: `?SetSddlOnPerfmonResources@@YAJPEAUITmInstance@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000db80`

## callees

- `0x1800063b0`
- `0x180023d98`
- `0x180086b44`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086d10`

## string_xrefs

- `0x180086b75`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`

## pseudocode

```c
__int64 __fastcall SetSddlOnPerfmonResources(struct ITmInstance *a1)
{
  int v2; // ebx
  const wchar_t *v3; // rax
  __int64 v4; // r9
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+28h] [rbp-20h]
  LPVOID pv; // [rsp+80h] [rbp+38h] BYREF
  LPWSTR pObjectName; // [rsp+88h] [rbp+40h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+90h] [rbp+48h] BYREF
  LPCWSTR v12; // [rsp+98h] [rbp+50h] BYREF

  pv = 0;
  pObjectName = 0;
  StringSecurityDescriptor = 0;
  v12 = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    879,
    L"SetSddlOnPerfmonResources",
    0,
    L"In");
  v2 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *, LPCWSTR *))(*(_QWORD *)a1 + 432LL))(
         a1,
         &pv,
         &StringSecurityDescriptor);
  if ( v2 < 0 )
  {
    v3 = L"Error from pTmInstance->PerfCounterFileMappingName";
    v4 = 884;
LABEL_13:
    LODWORD(v8) = v2;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      v4,
      L"SetSddlOnPerfmonResources",
      v8,
      v3);
    goto LABEL_14;
  }
  v2 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPWSTR *, LPCWSTR *))(*(_QWORD *)a1 + 440LL))(
         a1,
         &pObjectName,
         &v12);
  if ( v2 < 0 )
  {
    v3 = L"Error from pTmInstance->PerfCounterMutexName";
    v4 = 891;
    goto LABEL_13;
  }
  v5 = SetObjectSddl((LPWSTR)pv, SE_KERNEL_OBJECT, StringSecurityDescriptor);
  v2 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147024894 )
    {
      v3 = L"SetObjectSddl(wszMappedFileName) failed";
      v4 = 905;
      goto LABEL_13;
    }
    LODWORD(v8) = -2147024894;
    TraceStringInline(
      7,
      4,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      900,
      L"SetSddlOnPerfmonResources",
      v8,
      L"SetObjectSddl(wszMappedFileName) failed, deliberately ignoring failure");
  }
  v6 = SetObjectSddl(pObjectName, SE_KERNEL_OBJECT, v12);
  v2 = v6;
  if ( v6 < 0 )
  {
    if ( v6 != -2147024894 )
    {
      v3 = L"SetObjectSddl(wszMutexName) failed";
      v4 = 919;
      goto LABEL_13;
    }
    LODWORD(v8) = -2147024894;
    TraceStringInline(
      7,
      4,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      914,
      L"SetSddlOnPerfmonResources",
      v8,
      L"SetObjectSddl(wszMutexName) failed, deliberately ignoring failure");
    v2 = 0;
  }
LABEL_14:
  CoTaskMemFree(pv);
  CoTaskMemFree(pObjectName);
  CoTaskMemFree((LPVOID)StringSecurityDescriptor);
  CoTaskMemFree((LPVOID)v12);
  LODWORD(v8) = v2;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    930,
    L"SetSddlOnPerfmonResources",
    v8,
    L"Out");
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180086b44  push    rbp
0x180086b46  push    rbx
0x180086b47  push    rsi
0x180086b48  push    rdi
0x180086b49  push    r14
0x180086b4b  push    r15
0x180086b4d  mov     rbp, rsp
0x180086b50  sub     rsp, 48h
0x180086b54  mov     edx, 6
0x180086b59  mov     [rbp+pv], 0
0x180086b61  lea     rax, aIn_0; "In"
0x180086b68  mov     [rbp+pObjectName], 0
0x180086b70  mov     [rsp+48h+var_18], rax
0x180086b75  lea     rsi, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180086b7c  mov     rdi, rcx
0x180086b7f  mov     [rsp+48h+var_20], 0
0x180086b88  lea     r14d, [rdx+1]
0x180086b8c  mov     [rbp+StringSecurityDescriptor], 0
0x180086b94  lea     r15, aSetsddlonperfm; "SetSddlOnPerfmonResources"
0x180086b9b  mov     [rbp+arg_18], 0
0x180086ba3  mov     ecx, r14d
0x180086ba6  mov     [rsp+48h+var_28], r15
0x180086bab  mov     r9d, 36Fh
0x180086bb1  mov     r8, rsi
0x180086bb4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180086bb9  mov     rax, [rdi]
0x180086bbc  lea     r8, [rbp+StringSecurityDescriptor]
0x180086bc0  lea     rdx, [rbp+pv]
0x180086bc4  mov     rcx, rdi
0x180086bc7  mov     rax, [rax+1B0h]
0x180086bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086bd3  mov     ebx, eax
0x180086bd5  test    eax, eax
0x180086bd7  jns     short loc_180086BEB
0x180086bd9  lea     rax, aErrorFromPtmin_0; "Error from pTmInstance->PerfCounterFile"...
0x180086be0  mov     r9d, 374h
0x180086be6  jmp     loc_180086CD0
0x180086beb  mov     rax, [rdi]
0x180086bee  lea     r8, [rbp+arg_18]
0x180086bf2  lea     rdx, [rbp+pObjectName]
0x180086bf6  mov     rcx, rdi
0x180086bf9  mov     rax, [rax+1B8h]
0x180086c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c05  mov     ebx, eax
0x180086c07  test    eax, eax
0x180086c09  jns     short loc_180086C1D
0x180086c0b  lea     rax, aErrorFromPtmin_1; "Error from pTmInstance->PerfCounterMute"...
0x180086c12  mov     r9d, 37Bh
0x180086c18  jmp     loc_180086CD0
0x180086c1d  mov     r8, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180086c21  mov     edx, 6; ObjectType
0x180086c26  mov     rcx, [rbp+pv]; pObjectName
0x180086c2a  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180086c2f  mov     ebx, eax
0x180086c31  mov     edi, 80070002h
0x180086c36  test    eax, eax
0x180086c38  jns     short loc_180086C69
0x180086c3a  mov     r8, rsi
0x180086c3d  mov     ecx, r14d
0x180086c40  cmp     eax, edi
0x180086c42  jnz     short loc_180086CB4
0x180086c44  lea     rax, aSetobjectsddlW; "SetObjectSddl(wszMappedFileName) failed"...
0x180086c4b  mov     r9d, 384h
0x180086c51  mov     [rsp+48h+var_18], rax
0x180086c56  mov     edx, 4
0x180086c5b  mov     dword ptr [rsp+48h+var_20], edi
0x180086c5f  mov     [rsp+48h+var_28], r15
0x180086c64  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180086c69  mov     r8, [rbp+arg_18]; StringSecurityDescriptor
0x180086c6d  mov     edx, 6; ObjectType
0x180086c72  mov     rcx, [rbp+pObjectName]; pObjectName
0x180086c76  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180086c7b  mov     ebx, eax
0x180086c7d  test    eax, eax
0x180086c7f  jns     short loc_180086CEE
0x180086c81  cmp     eax, edi
0x180086c83  jnz     short loc_180086CC3
0x180086c85  lea     rax, aSetobjectsddlW_1; "SetObjectSddl(wszMutexName) failed, del"...
0x180086c8c  mov     r9d, 392h
0x180086c92  mov     [rsp+48h+var_18], rax
0x180086c97  mov     r8, rsi
0x180086c9a  mov     dword ptr [rsp+48h+var_20], edi
0x180086c9e  mov     edx, 4
0x180086ca3  mov     ecx, r14d
0x180086ca6  mov     [rsp+48h+var_28], r15
0x180086cab  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180086cb0  xor     ebx, ebx
0x180086cb2  jmp     short loc_180086CEE
0x180086cb4  lea     rax, aSetobjectsddlW_3; "SetObjectSddl(wszMappedFileName) failed"
0x180086cbb  mov     r9d, 389h
0x180086cc1  jmp     short loc_180086CD6
0x180086cc3  lea     rax, aSetobjectsddlW_0; "SetObjectSddl(wszMutexName) failed"
0x180086cca  mov     r9d, 397h
0x180086cd0  mov     r8, rsi
0x180086cd3  mov     ecx, r14d
0x180086cd6  mov     [rsp+48h+var_18], rax
0x180086cdb  mov     edx, 1
0x180086ce0  mov     dword ptr [rsp+48h+var_20], ebx
0x180086ce4  mov     [rsp+48h+var_28], r15
0x180086ce9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180086cee  mov     rcx, [rbp+pv]; pv
0x180086cf2  call    cs:__imp_CoTaskMemFree
0x180086cf8  mov     rcx, [rbp+pObjectName]; pv
0x180086cfc  call    cs:__imp_CoTaskMemFree
0x180086d02  mov     rcx, [rbp+StringSecurityDescriptor]; pv
0x180086d06  call    cs:__imp_CoTaskMemFree
0x180086d0c  mov     rcx, [rbp+arg_18]; pv
0x180086d10  call    cs:__imp_CoTaskMemFree
0x180086d16  lea     rax, aOut; "Out"
0x180086d1d  mov     r9d, 3A2h
0x180086d23  mov     [rsp+48h+var_18], rax
0x180086d28  mov     r8, rsi
0x180086d2b  mov     dword ptr [rsp+48h+var_20], ebx
0x180086d2f  mov     edx, 6
0x180086d34  mov     ecx, r14d
0x180086d37  mov     [rsp+48h+var_28], r15
0x180086d3c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180086d41  mov     eax, ebx
0x180086d43  add     rsp, 48h
0x180086d47  pop     r15
0x180086d49  pop     r14
0x180086d4b  pop     rdi
0x180086d4c  pop     rsi
0x180086d4d  pop     rbx
0x180086d4e  pop     rbp
0x180086d4f  retn
```
