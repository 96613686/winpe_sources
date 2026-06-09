# DllGetClassObject

- ea: `0x180032420`
- end: `0x1800325e6`
- name: `DllGetClassObject`
- size: `454`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180018f58`
- `0x18001ebe4`
- `0x180031970`
- `0x180032420`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800324cb`
- `RPCRT4!NdrDllGetClassObject` at `0x1800324cb`
- `ole32!StringFromCLSID` at `0x180032514`
- `ole32!StringFromCLSID` at `0x180032550`
- `ole32!StringFromCLSID` at `0x180032514`
- `ole32!StringFromCLSID` at `0x180032550`
- `ole32!CoTaskMemFree` at `0x18003252d`
- `ole32!CoTaskMemFree` at `0x18003259d`
- `ole32!CoTaskMemFree` at `0x1800325ca`
- `ole32!CoTaskMemFree` at `0x18003252d`
- `ole32!CoTaskMemFree` at `0x18003259d`
- `ole32!CoTaskMemFree` at `0x1800325ca`

## string_xrefs

- `0x18003256f`: `DllGetClassObject`
- `0x180032588`: `DllGetClassObject`
- `0x180032581`: `Error converting CLSIDs to strings`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  void **v3; // r9
  ATL::CComModule *v8; // rcx
  HRESULT ClassObject; // edi
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *v11; // rcx
  CLSID *pclsid; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h]
  __int64 v15; // [rsp+40h] [rbp-28h]
  LPOLESTR lpsz[4]; // [rsp+48h] [rbp-20h] BYREF

  if ( *(_QWORD *)&rclsid->Data1 == 0x48E245D291723892LL
    && *(_DWORD *)rclsid->Data4 == 592890270
    && *(_DWORD *)&rclsid->Data4[4] == -1829119367 )
  {
    return -2147221231;
  }
  ClassObject = PrintConfig::DllGetClassObject((PrintConfig *)rclsid, riid, (const struct _GUID *)ppv, v3);
  if ( ClassObject == -2147221231 )
  {
    ClassObject = ATL::CComModule::DllGetClassObject(v8, rclsid, riid, ppv);
    if ( ClassObject == -2147221231 )
    {
      pStubVtblList = aProxyFileList->pStubVtblList;
      if ( *pStubVtblList )
        v11 = **(const CLSID ***)pStubVtblList;
      else
        v11 = 0;
      ClassObject = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, v11, &gPFactory);
    }
  }
  if ( ClassObject < 0 )
  {
    lpsz[0] = 0;
    lpsz[1] = (LPOLESTR)-1LL;
    lpsz[2] = (LPOLESTR)-1LL;
    pv = 0;
    v14 = 0;
    v15 = 0;
    if ( StringFromCLSID(rclsid, lpsz) < 0 || (v14 = -1, v15 = -1, StringFromCLSID(riid, (LPOLESTR *)&pv) < 0) )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "DllGetClassObject",
        L"Error converting CLSIDs to strings");
    }
    else
    {
      LODWORD(pclsid) = ClassObject;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "DllGetClassObject",
        L"Called for class=%ws interface=%ws hr=0x%x",
        lpsz[0],
        pv,
        pclsid);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v14 = 0;
    v15 = 0;
    if ( lpsz[0] )
      CoTaskMemFree(lpsz[0]);
  }
  return ClassObject;
}

```

## disassembly

```asm
0x180032420  push    rbp
0x180032422  push    rbx
0x180032423  push    rsi
0x180032424  push    rdi
0x180032425  push    r14
0x180032427  push    r15
0x180032429  mov     rbp, rsp
0x18003242c  sub     rsp, 68h
0x180032430  cmp     dword ptr [rcx], 91723892h
0x180032436  mov     r15, r8
0x180032439  mov     r14, rdx
0x18003243c  mov     rbx, rcx
0x18003243f  jnz     short loc_18003246C
0x180032441  mov     eax, cs:dword_1801EBFEC
0x180032447  cmp     [rcx+4], eax
0x18003244a  jnz     short loc_18003246C
0x18003244c  mov     eax, cs:dword_1801EBFF0
0x180032452  cmp     [rcx+8], eax
0x180032455  jnz     short loc_18003246C
0x180032457  mov     eax, cs:dword_1801EBFF4
0x18003245d  cmp     [rcx+0Ch], eax
0x180032460  jnz     short loc_18003246C
0x180032462  mov     eax, 80040111h
0x180032467  jmp     loc_1800325D8
0x18003246c  call    ?DllGetClassObject@PrintConfig@@YAJAEBU_GUID@@0PEAPEAX@Z; PrintConfig::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180032471  mov     esi, 80040111h
0x180032476  mov     edi, eax
0x180032478  cmp     eax, esi
0x18003247a  jnz     short loc_1800324D9
0x18003247c  mov     r9, r15; void **
0x18003247f  mov     r8, r14; struct _GUID *
0x180032482  mov     rdx, rbx; struct _GUID *
0x180032485  call    ?DllGetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18003248a  mov     edi, eax
0x18003248c  cmp     eax, esi
0x18003248e  jnz     short loc_1800324D9
0x180032490  mov     rax, cs:aProxyFileList
0x180032497  mov     rcx, [rax+8]
0x18003249b  mov     rax, [rcx]
0x18003249e  test    rax, rax
0x1800324a1  jz      short loc_1800324A8
0x1800324a3  mov     rcx, [rax]
0x1800324a6  jmp     short loc_1800324AA
0x1800324a8  xor     ecx, ecx
0x1800324aa  lea     rax, gPFactory
0x1800324b1  mov     r8, r15; ppv
0x1800324b4  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800324b9  lea     r9, aProxyFileList; pProxyFileList
0x1800324c0  mov     [rsp+68h+pclsid], rcx; pclsid
0x1800324c5  mov     rdx, r14; riid
0x1800324c8  mov     rcx, rbx; rclsid
0x1800324cb  call    cs:__imp_NdrDllGetClassObject
0x1800324d2  nop     dword ptr [rax+rax+00h]
0x1800324d7  mov     edi, eax
0x1800324d9  test    edi, edi
0x1800324db  jns     loc_1800325D6
0x1800324e1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800324e5  mov     [rbp+lpsz], 0
0x1800324ed  lea     rdx, [rbp+lpsz]; lplpsz
0x1800324f1  mov     [rbp+var_18], rsi
0x1800324f5  mov     rcx, rbx; rclsid
0x1800324f8  mov     [rbp+var_10], rsi
0x1800324fc  mov     [rbp+pv], 0
0x180032504  mov     [rbp+var_30], 0
0x18003250c  mov     [rbp+var_28], 0
0x180032514  call    cs:__imp_StringFromCLSID
0x18003251b  nop     dword ptr [rax+rax+00h]
0x180032520  test    eax, eax
0x180032522  js      short loc_180032581
0x180032524  mov     rcx, [rbp+pv]; pv
0x180032528  test    rcx, rcx
0x18003252b  jz      short loc_180032541
0x18003252d  call    cs:__imp_CoTaskMemFree
0x180032534  nop     dword ptr [rax+rax+00h]
0x180032539  mov     [rbp+pv], 0
0x180032541  lea     rdx, [rbp+pv]; lplpsz
0x180032545  mov     [rbp+var_30], rsi
0x180032549  mov     rcx, r14; rclsid
0x18003254c  mov     [rbp+var_28], rsi
0x180032550  call    cs:__imp_StringFromCLSID
0x180032557  nop     dword ptr [rax+rax+00h]
0x18003255c  test    eax, eax
0x18003255e  js      short loc_180032581
0x180032560  mov     r9, [rbp+pv]
0x180032564  lea     rdx, aCalledForClass; "Called for class=%ws interface=%ws hr=0"...
0x18003256b  mov     r8, [rbp+lpsz]
0x18003256f  lea     rcx, aDllgetclassobj_0; "DllGetClassObject"
0x180032576  mov     dword ptr [rsp+68h+pclsid], edi
0x18003257a  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18003257f  jmp     short loc_180032594
0x180032581  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180032588  lea     rcx, aDllgetclassobj_0; "DllGetClassObject"
0x18003258f  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180032594  mov     rcx, [rbp+pv]; pv
0x180032598  test    rcx, rcx
0x18003259b  jz      short loc_1800325B1
0x18003259d  call    cs:__imp_CoTaskMemFree
0x1800325a4  nop     dword ptr [rax+rax+00h]
0x1800325a9  mov     [rbp+pv], 0
0x1800325b1  mov     rcx, [rbp+lpsz]; pv
0x1800325b5  mov     [rbp+var_30], 0
0x1800325bd  mov     [rbp+var_28], 0
0x1800325c5  test    rcx, rcx
0x1800325c8  jz      short loc_1800325D6
0x1800325ca  call    cs:__imp_CoTaskMemFree
0x1800325d1  nop     dword ptr [rax+rax+00h]
0x1800325d6  mov     eax, edi
0x1800325d8  add     rsp, 68h
0x1800325dc  pop     r15
0x1800325de  pop     r14
0x1800325e0  pop     rdi
0x1800325e1  pop     rsi
0x1800325e2  pop     rbx
0x1800325e3  pop     rbp
0x1800325e4  retn
```
