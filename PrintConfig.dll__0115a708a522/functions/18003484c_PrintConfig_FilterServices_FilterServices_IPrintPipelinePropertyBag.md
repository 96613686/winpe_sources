# PrintConfig::FilterServices::FilterServices(IPrintPipelinePropertyBag *)

- ea: `0x18003484c`
- end: `0x180034adf`
- name: `??0FilterServices@PrintConfig@@QEAA@PEAUIPrintPipelinePropertyBag@@@Z`
- size: `659`
- prototype: `PrintConfig::FilterServices *__fastcall(PrintConfig::FilterServices *this, struct IPrintPipelinePropertyBag *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b78c`

## callees

- `0x180003430`
- `0x180003c20`
- `0x180004564`
- `0x18000f830`
- `0x180018f00`
- `0x18001f25c`
- `0x18003484c`
- `0x180055608`
- `0x1801586d0`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003493b`
- `KERNEL32!GetLastError` at `0x18003493b`
- `OLEAUT32!__imp_VariantInit` at `0x1800348b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800348e5`
- `OLEAUT32!__imp_VariantInit` at `0x1800348b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800348e5`
- `OLEAUT32!__imp_VariantClear` at `0x1800349fe`
- `OLEAUT32!__imp_VariantClear` at `0x180034a0f`
- `OLEAUT32!__imp_VariantClear` at `0x1800349fe`
- `OLEAUT32!__imp_VariantClear` at `0x180034a0f`
- `ADVAPI32!SetThreadToken` at `0x18003492b`
- `ADVAPI32!SetThreadToken` at `0x18003496c`
- `ADVAPI32!SetThreadToken` at `0x18003492b`
- `ADVAPI32!SetThreadToken` at `0x18003496c`

## string_xrefs

- `0x1800349a4`: `PrintConfig::FilterServices::FilterServices`
- `0x1800348fc`: `UserSecurityToken`
- `0x18003499d`: `Populating filter services for printer %ws!`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
PrintConfig::FilterServices *__fastcall PrintConfig::FilterServices::FilterServices(
        PrintConfig::FilterServices *this,
        struct IPrintPipelinePropertyBag *a2)
{
  int v3; // eax
  int v4; // eax
  void *v5; // rsi
  signed int LastError; // eax
  bool v7; // sf
  void *v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  VARIANTARG pvarg; // [rsp+28h] [rbp-58h] BYREF
  VARIANTARG v14; // [rsp+40h] [rbp-40h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-28h] BYREF
  void *v16; // [rsp+B8h] [rbp+38h] BYREF
  struct PrintConfigData *v17; // [rsp+C0h] [rbp+40h] BYREF

  *(_QWORD *)this = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IPrintPipelinePropertyBag *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  VariantInit(&pvarg);
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)this + 32LL))(
         *(_QWORD *)this,
         L"PrinterName",
         &pvarg);
  if ( v3 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v3);
    throw (hr_error *)pExceptionObject;
  }
  VariantInit(&v14);
  v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)this + 32LL))(
         *(_QWORD *)this,
         L"UserSecurityToken",
         &v14);
  if ( v4 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v4);
    throw (hr_error *)pExceptionObject;
  }
  v5 = operator new(1u);
  v16 = v5;
  if ( !SetThreadToken(0, v14.bstrVal) )
  {
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError < 0;
    }
    if ( v7 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, LastError);
      throw (hr_error *)pExceptionObject;
    }
  }
  v8 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v5;
  if ( v8 )
  {
    SetThreadToken(0, 0);
    operator delete(v8);
  }
  v9 = PrintConfig::CPrinterQueue::Create(pvarg.bstrVal, (_QWORD *)this + 2);
  if ( v9 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v9);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::FilterServices::FilterServices",
    L"Populating filter services for printer %ws!",
    pvarg.llVal);
  v16 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), &v16);
  if ( v10 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v10);
    throw (hr_error *)pExceptionObject;
  }
  v17 = 0;
  v11 = CreatePrintConfigData(v16, &v17);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v11);
    throw (hr_error *)pExceptionObject;
  }
  std::shared_ptr<PrintConfigData>::reset<PrintConfigData,0>((_QWORD *)this + 3, (__int64)v17);
  VariantClear(&v14);
  VariantClear(&pvarg);
  return this;
}

```

## disassembly

```asm
0x18003484c  mov     rax, rsp
0x18003484f  mov     [rax+8], rcx
0x180034853  push    rbp
0x180034854  push    rsi
0x180034855  push    rdi
0x180034856  push    r14
0x180034858  push    r15
0x18003485a  mov     rbp, rsp
0x18003485d  sub     rsp, 80h
0x180034864  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFEh
0x18003486c  mov     [rax+20h], rbx
0x180034870  mov     rbx, rcx
0x180034873  mov     [rcx], rdx
0x180034876  test    rdx, rdx
0x180034879  jz      short loc_18003488B
0x18003487b  mov     rax, [rdx]
0x18003487e  mov     rcx, rdx
0x180034881  mov     rax, [rax+8]
0x180034885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003488a  nop
0x18003488b  mov     qword ptr [rbx+8], 0
0x180034893  lea     r14, [rbx+10h]
0x180034897  mov     qword ptr [r14], 0
0x18003489e  mov     qword ptr [rbx+18h], 0
0x1800348a6  mov     qword ptr [rbx+20h], 0
0x1800348ae  lea     rcx, [rbp+pvarg]; pvarg
0x1800348b2  call    cs:__imp_VariantInit
0x1800348b9  nop     dword ptr [rax+rax+00h]
0x1800348be  nop
0x1800348bf  mov     rcx, [rbx]
0x1800348c2  mov     rax, [rcx]
0x1800348c5  lea     r8, [rbp+pvarg]
0x1800348c9  lea     rdx, aPrintername; "PrinterName"
0x1800348d0  mov     rax, [rax+20h]
0x1800348d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348d9  test    eax, eax
0x1800348db  js      loc_180034A53
0x1800348e1  lea     rcx, [rbp+var_40]; pvarg
0x1800348e5  call    cs:__imp_VariantInit
0x1800348ec  nop     dword ptr [rax+rax+00h]
0x1800348f1  nop
0x1800348f2  mov     rcx, [rbx]
0x1800348f5  mov     rax, [rcx]
0x1800348f8  lea     r8, [rbp+var_40]
0x1800348fc  lea     rdx, aUsersecurityto; "UserSecurityToken"
0x180034903  mov     rax, [rax+20h]
0x180034907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003490c  test    eax, eax
0x18003490e  js      loc_180034A6F
0x180034914  mov     ecx, 1; Size
0x180034919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003491e  mov     rsi, rax
0x180034921  mov     [rbp+arg_8], rax
0x180034925  mov     rdx, qword ptr [rbp+var_40+8]; Token
0x180034929  xor     ecx, ecx; Thread
0x18003492b  call    cs:__imp_SetThreadToken
0x180034932  nop     dword ptr [rax+rax+00h]
0x180034937  test    eax, eax
0x180034939  jnz     short loc_18003495B
0x18003493b  call    cs:__imp_GetLastError
0x180034942  nop     dword ptr [rax+rax+00h]
0x180034947  test    eax, eax
0x180034949  jle     short loc_180034955
0x18003494b  movzx   eax, ax
0x18003494e  or      eax, 80070000h
0x180034953  test    eax, eax
0x180034955  js      loc_180034A8B
0x18003495b  mov     rdi, [rbx+8]
0x18003495f  mov     [rbx+8], rsi
0x180034963  test    rdi, rdi
0x180034966  jz      short loc_180034985
0x180034968  xor     edx, edx; Token
0x18003496a  xor     ecx, ecx; Thread
0x18003496c  call    cs:__imp_SetThreadToken
0x180034973  nop     dword ptr [rax+rax+00h]
0x180034978  mov     edx, 1
0x18003497d  mov     rcx, rdi; Block
0x180034980  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034985  mov     rdx, r14
0x180034988  mov     rcx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x18003498c  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x180034991  test    eax, eax
0x180034993  js      loc_180034AA7
0x180034999  mov     r8, qword ptr [rbp+pvarg+8]
0x18003499d  lea     rdx, aPopulatingFilt; "Populating filter services for printer "...
0x1800349a4  lea     rcx, aPrintconfigFil; "PrintConfig::FilterServices::FilterServ"...
0x1800349ab  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800349b0  mov     [rbp+arg_8], 0
0x1800349b8  mov     rcx, [r14]
0x1800349bb  mov     rax, [rcx]
0x1800349be  lea     rdx, [rbp+arg_8]
0x1800349c2  mov     rax, [rax+38h]
0x1800349c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349cb  test    eax, eax
0x1800349cd  js      loc_180034AC3
0x1800349d3  mov     [rbp+arg_10], 0
0x1800349db  lea     rdx, [rbp+arg_10]; struct PrintConfigData **
0x1800349df  mov     rcx, [rbp+arg_8]; void *
0x1800349e3  call    ?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z; CreatePrintConfigData(void *,PrintConfigData * *)
0x1800349e8  test    eax, eax
0x1800349ea  js      short loc_180034A37
0x1800349ec  mov     rdx, [rbp+arg_10]
0x1800349f0  lea     rcx, [rbx+18h]
0x1800349f4  call    ??$reset@VPrintConfigData@@$0A@@?$shared_ptr@VPrintConfigData@@@std@@QEAAXPEAVPrintConfigData@@@Z; std::shared_ptr<PrintConfigData>::reset<PrintConfigData,0>(PrintConfigData *)
0x1800349f9  nop
0x1800349fa  lea     rcx, [rbp+var_40]; pvarg
0x1800349fe  call    cs:__imp_VariantClear
0x180034a05  nop     dword ptr [rax+rax+00h]
0x180034a0a  nop
0x180034a0b  lea     rcx, [rbp+pvarg]; pvarg
0x180034a0f  call    cs:__imp_VariantClear
0x180034a16  nop     dword ptr [rax+rax+00h]
0x180034a1b  nop
0x180034a1c  mov     rax, rbx
0x180034a1f  mov     rbx, [rsp+80h+arg_18]
0x180034a27  add     rsp, 80h
0x180034a2e  pop     r15
0x180034a30  pop     r14
0x180034a32  pop     rdi
0x180034a33  pop     rsi
0x180034a34  pop     rbp
0x180034a35  retn
0x180034a37  mov     edx, eax; int
0x180034a39  lea     rcx, [rbp+pExceptionObject]; this
0x180034a3d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034a42  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034a49  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034a4d  call    _CxxThrowException_0
0x180034a53  mov     edx, eax; int
0x180034a55  lea     rcx, [rbp+pExceptionObject]; this
0x180034a59  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034a5e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034a65  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034a69  call    _CxxThrowException_0
0x180034a6f  mov     edx, eax; int
0x180034a71  lea     rcx, [rbp+pExceptionObject]; this
0x180034a75  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034a7a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034a81  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034a85  call    _CxxThrowException_0
0x180034a8b  mov     edx, eax; int
0x180034a8d  lea     rcx, [rbp+pExceptionObject]; this
0x180034a91  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034a96  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034a9d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034aa1  call    _CxxThrowException_0
0x180034aa7  mov     edx, eax; int
0x180034aa9  lea     rcx, [rbp+pExceptionObject]; this
0x180034aad  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034ab2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034ab9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034abd  call    _CxxThrowException_0
0x180034ac3  mov     edx, eax; int
0x180034ac5  lea     rcx, [rbp+pExceptionObject]; this
0x180034ac9  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180034ace  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180034ad5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180034ad9  call    _CxxThrowException_0
```
