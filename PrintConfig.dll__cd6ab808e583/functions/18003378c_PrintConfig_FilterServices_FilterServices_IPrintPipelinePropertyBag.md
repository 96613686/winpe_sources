# PrintConfig::FilterServices::FilterServices(IPrintPipelinePropertyBag *)

- ea: `0x18003378c`
- end: `0x1800339f4`
- name: `??0FilterServices@PrintConfig@@QEAA@PEAUIPrintPipelinePropertyBag@@@Z`
- size: `616`
- prototype: `PrintConfig::FilterServices *__fastcall(PrintConfig::FilterServices *this, struct IPrintPipelinePropertyBag *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ab40`

## callees

- `0x180003310`
- `0x180003b00`
- `0x180004424`
- `0x18000f380`
- `0x1800183a0`
- `0x18001e8e4`
- `0x18003378c`
- `0x180053468`
- `0x180151610`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180033869`
- `KERNEL32!GetLastError` at `0x180033869`
- `OLEAUT32!__imp_VariantInit` at `0x1800337f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003381f`
- `OLEAUT32!__imp_VariantInit` at `0x1800337f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003381f`
- `OLEAUT32!__imp_VariantClear` at `0x180033920`
- `OLEAUT32!__imp_VariantClear` at `0x18003392b`
- `OLEAUT32!__imp_VariantClear` at `0x180033920`
- `OLEAUT32!__imp_VariantClear` at `0x18003392b`
- `ADVAPI32!SetThreadToken` at `0x18003385f`
- `ADVAPI32!SetThreadToken` at `0x180033894`
- `ADVAPI32!SetThreadToken` at `0x18003385f`
- `ADVAPI32!SetThreadToken` at `0x180033894`

## string_xrefs

- `0x180033830`: `UserSecurityToken`
- `0x1800338bf`: `Populating filter services for printer %ws!`
- `0x1800338c6`: `PrintConfig::FilterServices::FilterServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
  v9 = PrintConfig::CPrinterQueue::Create(pvarg.bstrVal);
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
0x18003378c  mov     rax, rsp
0x18003378f  mov     [rax+8], rcx
0x180033793  push    rbp
0x180033794  push    rsi
0x180033795  push    rdi
0x180033796  push    r14
0x180033798  push    r15
0x18003379a  mov     rbp, rsp
0x18003379d  sub     rsp, 80h
0x1800337a4  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFEh
0x1800337ac  mov     [rax+20h], rbx
0x1800337b0  mov     rbx, rcx
0x1800337b3  mov     [rcx], rdx
0x1800337b6  test    rdx, rdx
0x1800337b9  jz      short loc_1800337CB
0x1800337bb  mov     rax, [rdx]
0x1800337be  mov     rcx, rdx
0x1800337c1  mov     rax, [rax+8]
0x1800337c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337ca  nop
0x1800337cb  mov     qword ptr [rbx+8], 0
0x1800337d3  lea     r14, [rbx+10h]
0x1800337d7  mov     qword ptr [r14], 0
0x1800337de  mov     qword ptr [rbx+18h], 0
0x1800337e6  mov     qword ptr [rbx+20h], 0
0x1800337ee  lea     rcx, [rbp+pvarg]; pvarg
0x1800337f2  call    cs:__imp_VariantInit
0x1800337f8  nop
0x1800337f9  mov     rcx, [rbx]
0x1800337fc  mov     rax, [rcx]
0x1800337ff  lea     r8, [rbp+pvarg]
0x180033803  lea     rdx, aPrintername; "PrinterName"
0x18003380a  mov     rax, [rax+20h]
0x18003380e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033813  test    eax, eax
0x180033815  js      loc_180033968
0x18003381b  lea     rcx, [rbp+var_40]; pvarg
0x18003381f  call    cs:__imp_VariantInit
0x180033825  nop
0x180033826  mov     rcx, [rbx]
0x180033829  mov     rax, [rcx]
0x18003382c  lea     r8, [rbp+var_40]
0x180033830  lea     rdx, aUsersecurityto; "UserSecurityToken"
0x180033837  mov     rax, [rax+20h]
0x18003383b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033840  test    eax, eax
0x180033842  js      loc_180033984
0x180033848  mov     ecx, 1; Size
0x18003384d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033852  mov     rsi, rax
0x180033855  mov     [rbp+arg_8], rax
0x180033859  mov     rdx, qword ptr [rbp+var_40+8]; Token
0x18003385d  xor     ecx, ecx; Thread
0x18003385f  call    cs:__imp_SetThreadToken
0x180033865  test    eax, eax
0x180033867  jnz     short loc_180033883
0x180033869  call    cs:__imp_GetLastError
0x18003386f  test    eax, eax
0x180033871  jle     short loc_18003387D
0x180033873  movzx   eax, ax
0x180033876  or      eax, 80070000h
0x18003387b  test    eax, eax
0x18003387d  js      loc_1800339A0
0x180033883  mov     rdi, [rbx+8]
0x180033887  mov     [rbx+8], rsi
0x18003388b  test    rdi, rdi
0x18003388e  jz      short loc_1800338A7
0x180033890  xor     edx, edx; Token
0x180033892  xor     ecx, ecx; Thread
0x180033894  call    cs:__imp_SetThreadToken
0x18003389a  mov     edx, 1
0x18003389f  mov     rcx, rdi; Block
0x1800338a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800338a7  mov     rdx, r14
0x1800338aa  mov     rcx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x1800338ae  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x1800338b3  test    eax, eax
0x1800338b5  js      loc_1800339BC
0x1800338bb  mov     r8, qword ptr [rbp+pvarg+8]
0x1800338bf  lea     rdx, aPopulatingFilt; "Populating filter services for printer "...
0x1800338c6  lea     rcx, aPrintconfigFil; "PrintConfig::FilterServices::FilterServ"...
0x1800338cd  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800338d2  mov     [rbp+arg_8], 0
0x1800338da  mov     rcx, [r14]
0x1800338dd  mov     rax, [rcx]
0x1800338e0  lea     rdx, [rbp+arg_8]
0x1800338e4  mov     rax, [rax+38h]
0x1800338e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338ed  test    eax, eax
0x1800338ef  js      loc_1800339D8
0x1800338f5  mov     [rbp+arg_10], 0
0x1800338fd  lea     rdx, [rbp+arg_10]; struct PrintConfigData **
0x180033901  mov     rcx, [rbp+arg_8]; void *
0x180033905  call    ?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z; CreatePrintConfigData(void *,PrintConfigData * *)
0x18003390a  test    eax, eax
0x18003390c  js      short loc_18003394C
0x18003390e  mov     rdx, [rbp+arg_10]
0x180033912  lea     rcx, [rbx+18h]
0x180033916  call    ??$reset@VPrintConfigData@@$0A@@?$shared_ptr@VPrintConfigData@@@std@@QEAAXPEAVPrintConfigData@@@Z; std::shared_ptr<PrintConfigData>::reset<PrintConfigData,0>(PrintConfigData *)
0x18003391b  nop
0x18003391c  lea     rcx, [rbp+var_40]; pvarg
0x180033920  call    cs:__imp_VariantClear
0x180033926  nop
0x180033927  lea     rcx, [rbp+pvarg]; pvarg
0x18003392b  call    cs:__imp_VariantClear
0x180033931  nop
0x180033932  mov     rax, rbx
0x180033935  mov     rbx, [rsp+80h+arg_18]
0x18003393d  add     rsp, 80h
0x180033944  pop     r15
0x180033946  pop     r14
0x180033948  pop     rdi
0x180033949  pop     rsi
0x18003394a  pop     rbp
0x18003394b  retn
0x18003394c  mov     edx, eax; int
0x18003394e  lea     rcx, [rbp+pExceptionObject]; this
0x180033952  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180033957  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18003395e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180033962  call    _CxxThrowException_0
0x180033968  mov     edx, eax; int
0x18003396a  lea     rcx, [rbp+pExceptionObject]; this
0x18003396e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180033973  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18003397a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003397e  call    _CxxThrowException_0
0x180033984  mov     edx, eax; int
0x180033986  lea     rcx, [rbp+pExceptionObject]; this
0x18003398a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18003398f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180033996  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003399a  call    _CxxThrowException_0
0x1800339a0  mov     edx, eax; int
0x1800339a2  lea     rcx, [rbp+pExceptionObject]; this
0x1800339a6  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800339ab  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800339b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800339b6  call    _CxxThrowException_0
0x1800339bc  mov     edx, eax; int
0x1800339be  lea     rcx, [rbp+pExceptionObject]; this
0x1800339c2  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800339c7  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800339ce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800339d2  call    _CxxThrowException_0
0x1800339d8  mov     edx, eax; int
0x1800339da  lea     rcx, [rbp+pExceptionObject]; this
0x1800339de  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800339e3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800339ea  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800339ee  call    _CxxThrowException_0
```
