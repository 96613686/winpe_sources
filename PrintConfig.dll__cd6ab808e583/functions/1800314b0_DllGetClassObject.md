# DllGetClassObject

- ea: `0x1800314b0`
- end: `0x180031651`
- name: `DllGetClassObject`
- size: `417`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800183f8`
- `0x18001e294`
- `0x180030a88`
- `0x1800314b0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18003155b`
- `RPCRT4!NdrDllGetClassObject` at `0x18003155b`
- `ole32!StringFromCLSID` at `0x18003159e`
- `ole32!StringFromCLSID` at `0x1800315ce`
- `ole32!StringFromCLSID` at `0x18003159e`
- `ole32!StringFromCLSID` at `0x1800315ce`
- `ole32!CoTaskMemFree` at `0x1800315b1`
- `ole32!CoTaskMemFree` at `0x180031615`
- `ole32!CoTaskMemFree` at `0x18003163c`
- `ole32!CoTaskMemFree` at `0x1800315b1`
- `ole32!CoTaskMemFree` at `0x180031615`
- `ole32!CoTaskMemFree` at `0x18003163c`

## string_xrefs

- `0x1800315e7`: `DllGetClassObject`
- `0x180031600`: `DllGetClassObject`
- `0x1800315f9`: `Error converting CLSIDs to strings`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  void **v3; // r9
  ATL::CComModule *v8; // rcx
  int ClassObject; // edi
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
0x1800314b0  push    rbp
0x1800314b2  push    rbx
0x1800314b3  push    rsi
0x1800314b4  push    rdi
0x1800314b5  push    r14
0x1800314b7  push    r15
0x1800314b9  mov     rbp, rsp
0x1800314bc  sub     rsp, 68h
0x1800314c0  cmp     dword ptr [rcx], 91723892h
0x1800314c6  mov     r15, r8
0x1800314c9  mov     r14, rdx
0x1800314cc  mov     rbx, rcx
0x1800314cf  jnz     short loc_1800314FC
0x1800314d1  mov     eax, cs:dword_1801E423C
0x1800314d7  cmp     [rcx+4], eax
0x1800314da  jnz     short loc_1800314FC
0x1800314dc  mov     eax, cs:dword_1801E4240
0x1800314e2  cmp     [rcx+8], eax
0x1800314e5  jnz     short loc_1800314FC
0x1800314e7  mov     eax, cs:dword_1801E4244
0x1800314ed  cmp     [rcx+0Ch], eax
0x1800314f0  jnz     short loc_1800314FC
0x1800314f2  mov     eax, 80040111h
0x1800314f7  jmp     loc_180031644
0x1800314fc  call    ?DllGetClassObject@PrintConfig@@YAJAEBU_GUID@@0PEAPEAX@Z; PrintConfig::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180031501  mov     esi, 80040111h
0x180031506  mov     edi, eax
0x180031508  cmp     eax, esi
0x18003150a  jnz     short loc_180031563
0x18003150c  mov     r9, r15; void **
0x18003150f  mov     r8, r14; struct _GUID *
0x180031512  mov     rdx, rbx; struct _GUID *
0x180031515  call    ?DllGetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18003151a  mov     edi, eax
0x18003151c  cmp     eax, esi
0x18003151e  jnz     short loc_180031563
0x180031520  mov     rax, cs:aProxyFileList
0x180031527  mov     rcx, [rax+8]
0x18003152b  mov     rax, [rcx]
0x18003152e  test    rax, rax
0x180031531  jz      short loc_180031538
0x180031533  mov     rcx, [rax]
0x180031536  jmp     short loc_18003153A
0x180031538  xor     ecx, ecx
0x18003153a  lea     rax, gPFactory
0x180031541  mov     r8, r15; ppv
0x180031544  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180031549  lea     r9, aProxyFileList; pProxyFileList
0x180031550  mov     [rsp+68h+pclsid], rcx; pclsid
0x180031555  mov     rdx, r14; riid
0x180031558  mov     rcx, rbx; rclsid
0x18003155b  call    cs:__imp_NdrDllGetClassObject
0x180031561  mov     edi, eax
0x180031563  test    edi, edi
0x180031565  jns     loc_180031642
0x18003156b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003156f  mov     [rbp+lpsz], 0
0x180031577  lea     rdx, [rbp+lpsz]; lplpsz
0x18003157b  mov     [rbp+var_18], rsi
0x18003157f  mov     rcx, rbx; rclsid
0x180031582  mov     [rbp+var_10], rsi
0x180031586  mov     [rbp+pv], 0
0x18003158e  mov     [rbp+var_30], 0
0x180031596  mov     [rbp+var_28], 0
0x18003159e  call    cs:__imp_StringFromCLSID
0x1800315a4  test    eax, eax
0x1800315a6  js      short loc_1800315F9
0x1800315a8  mov     rcx, [rbp+pv]; pv
0x1800315ac  test    rcx, rcx
0x1800315af  jz      short loc_1800315BF
0x1800315b1  call    cs:__imp_CoTaskMemFree
0x1800315b7  mov     [rbp+pv], 0
0x1800315bf  lea     rdx, [rbp+pv]; lplpsz
0x1800315c3  mov     [rbp+var_30], rsi
0x1800315c7  mov     rcx, r14; rclsid
0x1800315ca  mov     [rbp+var_28], rsi
0x1800315ce  call    cs:__imp_StringFromCLSID
0x1800315d4  test    eax, eax
0x1800315d6  js      short loc_1800315F9
0x1800315d8  mov     r9, [rbp+pv]
0x1800315dc  lea     rdx, aCalledForClass; "Called for class=%ws interface=%ws hr=0"...
0x1800315e3  mov     r8, [rbp+lpsz]
0x1800315e7  lea     rcx, aDllgetclassobj_0; "DllGetClassObject"
0x1800315ee  mov     dword ptr [rsp+68h+pclsid], edi
0x1800315f2  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800315f7  jmp     short loc_18003160C
0x1800315f9  lea     rdx, aErrorConvertin; "Error converting CLSIDs to strings"
0x180031600  lea     rcx, aDllgetclassobj_0; "DllGetClassObject"
0x180031607  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18003160c  mov     rcx, [rbp+pv]; pv
0x180031610  test    rcx, rcx
0x180031613  jz      short loc_180031623
0x180031615  call    cs:__imp_CoTaskMemFree
0x18003161b  mov     [rbp+pv], 0
0x180031623  mov     rcx, [rbp+lpsz]; pv
0x180031627  mov     [rbp+var_30], 0
0x18003162f  mov     [rbp+var_28], 0
0x180031637  test    rcx, rcx
0x18003163a  jz      short loc_180031642
0x18003163c  call    cs:__imp_CoTaskMemFree
0x180031642  mov     eax, edi
0x180031644  add     rsp, 68h
0x180031648  pop     r15
0x18003164a  pop     r14
0x18003164c  pop     rdi
0x18003164d  pop     rsi
0x18003164e  pop     rbx
0x18003164f  pop     rbp
0x180031650  retn
```
