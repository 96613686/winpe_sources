# PrintConfig::DevModeToPrintTicket(HPTPROVIDER__ *,_devicemodeW *)

- ea: `0x1800416c4`
- end: `0x180041b25`
- name: `?DevModeToPrintTicket@PrintConfig@@YA?AV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEAUHPTPROVIDER__@@PEAU_devicemodeW@@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(LPVOID *ppv, HPTPROVIDER hProvider, PDEVMODE pDevmode)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046894`
- `0x18004a7c8`

## callees

- `0x180004424`
- `0x18000f380`
- `0x1800183f8`
- `0x1800416c4`
- `0x180051150`
- `0x1801c3010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004193b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004193b`
- `OLEAUT32!__imp_VariantInit` at `0x180041797`
- `OLEAUT32!__imp_VariantInit` at `0x1800418d8`
- `OLEAUT32!__imp_VariantInit` at `0x180041797`
- `OLEAUT32!__imp_VariantInit` at `0x1800418d8`
- `OLEAUT32!__imp_VariantClear` at `0x18004192b`
- `OLEAUT32!__imp_VariantClear` at `0x180041946`
- `OLEAUT32!__imp_VariantClear` at `0x18004192b`
- `OLEAUT32!__imp_VariantClear` at `0x180041946`
- `ole32!CoCreateInstance` at `0x180041785`
- `ole32!CoCreateInstance` at `0x180041785`
- `ole32!CreateStreamOnHGlobal` at `0x180041708`
- `ole32!CreateStreamOnHGlobal` at `0x180041708`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x180041733`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x180041733`

## string_xrefs

- `0x180041ade`: `PrintConfig::DevModeToPrintTicket`
- `0x180041ad7`: `Error parsing PrintTicket XML. Line: %d Position: %d Error: %d Reason: %ws Source Text: %ws`
- `0x1800418c3`: `xmlns:psk='http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords' xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2' xmlns:ns0001 = 'http://schemas.microsoft.com/windows/2018/04/printing/printschemakeywords/Ipp' xmlns:pskv11 = 'http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11'`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
LPVOID *__fastcall PrintConfig::DevModeToPrintTicket(LPVOID *ppv, HPTPROVIDER hProvider, PDEVMODE pDevmode)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  HRESULT Instance; // eax
  LPSTREAM v10; // rax
  LPVOID v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  BSTR v21; // rax
  LPVOID v22; // rcx
  int v23; // eax
  LPSTREAM v24; // rcx
  IStream *pPrintTicket; // [rsp+28h] [rbp-79h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-59h] BYREF
  VARIANTARG pExceptionObject; // [rsp+58h] [rbp-49h] BYREF
  __int64 *v29; // [rsp+78h] [rbp-29h] BYREF
  int v30; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v31; // [rsp+84h] [rbp-1Dh] BYREF
  unsigned int v32; // [rsp+88h] [rbp-19h] BYREF
  int v33; // [rsp+8Ch] [rbp-15h]
  __int64 v34; // [rsp+90h] [rbp-11h] BYREF
  __int64 v35; // [rsp+98h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-1h] BYREF
  VARIANTARG v37; // [rsp+A8h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp+1Fh] BYREF
  __int64 v39; // [rsp+D8h] [rbp+37h]
  __int16 v40; // [rsp+120h] [rbp+7Fh] BYREF

  v39 = -2;
  v33 = 0;
  ppstm = 0;
  v6 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v6 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v6);
    throw (hr_error *)&pExceptionObject;
  }
  v7 = PTConvertDevModeToPrintTicket(
         hProvider,
         (unsigned __int16)pDevmode->dmCollate + *(unsigned __int16 *)pDevmode->dmFormName,
         pDevmode,
         kPTJobScope,
         ppstm);
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v7);
    throw (hr_error *)&pExceptionObject;
  }
  v8 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v8);
    throw (hr_error *)&pExceptionObject;
  }
  *ppv = 0;
  v33 = 1;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               ppv);
  if ( Instance < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, Instance);
    throw (hr_error *)&pExceptionObject;
  }
  VariantInit(&pvarg);
  pvarg.vt = 13;
  v10 = ppstm;
  ppstm = 0;
  pvarg.llVal = (LONGLONG)v10;
  v40 = 0;
  v11 = *ppv;
  pExceptionObject = pvarg;
  v12 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)v11 + 464LL))(
          v11,
          &pExceptionObject,
          &v40);
  if ( v12 == 1 )
  {
    v29 = 0;
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*ppv + 480LL))(*ppv, &v29);
    if ( v13 >= 0 )
    {
      v30 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v29 + 56))(v29, &v30);
      if ( v14 >= 0 )
      {
        v32 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v29 + 88))(v29, &v32);
        if ( v15 >= 0 )
        {
          v31 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v29 + 96))(v29, &v31);
          if ( v16 >= 0 )
          {
            v35 = 0;
            v17 = *v29;
            v35 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v17 + 72))(v29, &v35);
            if ( v18 >= 0 )
            {
              v34 = 0;
              v19 = *v29;
              v34 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 80))(v29, &v34);
              if ( v20 >= 0 )
              {
                LODWORD(pPrintTicket) = v30;
                Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
                  "PrintConfig::DevModeToPrintTicket",
                  L"Error parsing PrintTicket XML. Line: %d Position: %d Error: %d Reason: %ws Source Text: %ws",
                  v32,
                  v31,
                  pPrintTicket,
                  v35,
                  v34);
                hr_error::hr_error((hr_error *)&pExceptionObject, -2147418113);
                throw (hr_error *)&pExceptionObject;
              }
              hr_error::hr_error((hr_error *)&pExceptionObject, v20);
              throw (hr_error *)&pExceptionObject;
            }
            hr_error::hr_error((hr_error *)&pExceptionObject, v18);
            throw (hr_error *)&pExceptionObject;
          }
          hr_error::hr_error((hr_error *)&pExceptionObject, v16);
          throw (hr_error *)&pExceptionObject;
        }
        hr_error::hr_error((hr_error *)&pExceptionObject, v15);
        throw (hr_error *)&pExceptionObject;
      }
      hr_error::hr_error((hr_error *)&pExceptionObject, v14);
      throw (hr_error *)&pExceptionObject;
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v13);
    throw (hr_error *)&pExceptionObject;
  }
  if ( v12 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v12);
    throw (hr_error *)&pExceptionObject;
  }
  wil::make_bstr(
    &bstrString,
    L"xmlns:psk='http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords' xmlns:psf='http://schemas.micr"
     "osoft.com/windows/2003/08/printing/printschemaframework' xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/p"
     "rinting/printschemaframework2' xmlns:ns0001 = 'http://schemas.microsoft.com/windows/2018/04/printing/printschemakey"
     "words/Ipp' xmlns:pskv11 = 'http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11'");
  VariantInit(&v37);
  v37.vt = 8;
  v21 = bstrString;
  bstrString = 0;
  v37.llVal = (LONGLONG)v21;
  v22 = *ppv;
  pExceptionObject = v37;
  v23 = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v22 + 640LL))(
          v22,
          L"SelectionNamespaces",
          &pExceptionObject);
  if ( v23 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v23);
    throw (hr_error *)&pExceptionObject;
  }
  VariantClear(&v37);
  if ( bstrString )
    SysFreeString(bstrString);
  VariantClear(&pvarg);
  v24 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    ((void (__fastcall *)(LPSTREAM))v24->lpVtbl->Release)(v24);
  }
  return ppv;
}

```

## disassembly

```asm
0x1800416c4  mov     rax, rsp
0x1800416c7  mov     [rax+8], rcx
0x1800416cb  push    rbp
0x1800416cc  push    rdi
0x1800416cd  push    r14
0x1800416cf  lea     rbp, [rax-5Fh]
0x1800416d3  sub     rsp, 0E0h
0x1800416da  mov     [rbp+57h+var_20], 0FFFFFFFFFFFFFFFEh
0x1800416e2  mov     [rax+10h], rbx
0x1800416e6  mov     [rax+18h], rsi
0x1800416ea  mov     rdi, r8
0x1800416ed  mov     rsi, rdx
0x1800416f0  mov     rbx, rcx
0x1800416f3  xor     r14d, r14d
0x1800416f6  mov     [rbp+57h+var_6C], r14d
0x1800416fa  mov     [rbp+57h+ppstm], r14
0x1800416fe  lea     r8, [rbp+57h+ppstm]; ppstm
0x180041702  lea     edx, [r14+1]; fDeleteOnRelease
0x180041706  xor     ecx, ecx; hGlobal
0x180041708  call    cs:__imp_CreateStreamOnHGlobal
0x18004170e  test    eax, eax
0x180041710  js      loc_1800419BA
0x180041716  mov     rcx, [rbp+57h+ppstm]
0x18004171a  movzx   edx, word ptr [rdi+46h]
0x18004171e  movzx   eax, word ptr [rdi+44h]
0x180041722  add     edx, eax; cbDevmode
0x180041724  mov     [rsp+0F0h+pPrintTicket], rcx; pPrintTicket
0x180041729  lea     r9d, [r14+2]; scope
0x18004172d  mov     r8, rdi; pDevmode
0x180041730  mov     rcx, rsi; hProvider
0x180041733  call    cs:__imp_PTConvertDevModeToPrintTicket
0x180041739  test    eax, eax
0x18004173b  js      loc_1800419D6
0x180041741  mov     rcx, [rbp+57h+ppstm]
0x180041745  mov     edx, r14d
0x180041748  mov     rax, [rcx]
0x18004174b  xor     r9d, r9d
0x18004174e  xor     r8d, r8d
0x180041751  mov     rax, [rax+28h]
0x180041755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004175a  test    eax, eax
0x18004175c  js      loc_1800419F2
0x180041762  mov     [rbx], r14
0x180041765  mov     [rbp+57h+var_6C], 1
0x18004176c  mov     [rsp+0F0h+pPrintTicket], rbx; ppv
0x180041771  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180041778  xor     edx, edx; pUnkOuter
0x18004177a  lea     r8d, [r14+1]; dwClsContext
0x18004177e  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180041785  call    cs:__imp_CoCreateInstance
0x18004178b  test    eax, eax
0x18004178d  js      loc_180041A0E
0x180041793  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041797  call    cs:__imp_VariantInit
0x18004179d  nop
0x18004179e  lea     eax, [r14+0Dh]
0x1800417a2  mov     word ptr [rbp+57h+pvarg], ax
0x1800417a6  mov     rax, [rbp+57h+ppstm]
0x1800417aa  mov     [rbp+57h+ppstm], r14
0x1800417ae  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800417b2  mov     [rbp+57h+arg_18], r14w
0x1800417b7  mov     rcx, [rbx]
0x1800417ba  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800417be  movaps  [rbp+57h+pExceptionObject], xmm0
0x1800417c2  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800417c7  movsd   [rbp+57h+var_90], xmm1
0x1800417cc  mov     rax, [rcx]
0x1800417cf  lea     r8, [rbp+57h+arg_18]
0x1800417d3  lea     rdx, [rbp+57h+pExceptionObject]
0x1800417d7  mov     rax, [rax+1D0h]
0x1800417de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417e3  cmp     eax, 1
0x1800417e6  jnz     loc_1800418BB
0x1800417ec  mov     [rbp+57h+var_80], r14
0x1800417f0  mov     rcx, [rbx]
0x1800417f3  mov     rax, [rcx]
0x1800417f6  lea     rdx, [rbp+57h+var_80]
0x1800417fa  mov     rax, [rax+1E0h]
0x180041801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041806  test    eax, eax
0x180041808  js      loc_180041A2A
0x18004180e  mov     [rbp+57h+var_78], r14d
0x180041812  mov     rcx, [rbp+57h+var_80]
0x180041816  mov     rax, [rcx]
0x180041819  lea     rdx, [rbp+57h+var_78]
0x18004181d  mov     rax, [rax+38h]
0x180041821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041826  test    eax, eax
0x180041828  js      loc_180041A46
0x18004182e  mov     [rbp+57h+var_70], r14d
0x180041832  mov     rcx, [rbp+57h+var_80]
0x180041836  mov     rax, [rcx]
0x180041839  lea     rdx, [rbp+57h+var_70]
0x18004183d  mov     rax, [rax+58h]
0x180041841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041846  test    eax, eax
0x180041848  js      loc_180041A62
0x18004184e  mov     [rbp+57h+var_74], r14d
0x180041852  mov     rcx, [rbp+57h+var_80]
0x180041856  mov     rax, [rcx]
0x180041859  lea     rdx, [rbp+57h+var_74]
0x18004185d  mov     rax, [rax+60h]
0x180041861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041866  test    eax, eax
0x180041868  js      loc_180041A7E
0x18004186e  mov     [rbp+57h+var_60], r14
0x180041872  mov     rcx, [rbp+57h+var_80]
0x180041876  mov     rax, [rcx]
0x180041879  mov     [rbp+57h+var_60], r14
0x18004187d  lea     rdx, [rbp+57h+var_60]
0x180041881  mov     rax, [rax+48h]
0x180041885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004188a  test    eax, eax
0x18004188c  js      loc_180041A9A
0x180041892  mov     [rbp+57h+var_68], r14
0x180041896  mov     rcx, [rbp+57h+var_80]
0x18004189a  mov     rax, [rcx]
0x18004189d  mov     [rbp+57h+var_68], r14
0x1800418a1  lea     rdx, [rbp+57h+var_68]
0x1800418a5  mov     rax, [rax+50h]
0x1800418a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418ae  test    eax, eax
0x1800418b0  js      loc_18004199E
0x1800418b6  jmp     loc_180041AB6
0x1800418bb  test    eax, eax
0x1800418bd  js      loc_180041B09
0x1800418c3  lea     rdx, aXmlnsPskHttpSc_0; "xmlns:psk='http://schemas.microsoft.com"...
0x1800418ca  lea     rcx, [rbp+57h+bstrString]
0x1800418ce  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800418d3  nop
0x1800418d4  lea     rcx, [rbp+57h+var_50]; pvarg
0x1800418d8  call    cs:__imp_VariantInit
0x1800418de  nop
0x1800418df  mov     eax, 8
0x1800418e4  mov     word ptr [rbp+57h+var_50], ax
0x1800418e8  mov     rax, [rbp+57h+bstrString]
0x1800418ec  mov     [rbp+57h+bstrString], r14
0x1800418f0  mov     qword ptr [rbp+57h+var_50+8], rax
0x1800418f4  mov     rcx, [rbx]
0x1800418f7  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x1800418fb  movaps  [rbp+57h+pExceptionObject], xmm0
0x1800418ff  movsd   xmm1, qword ptr [rbp+57h+var_50+10h]
0x180041904  movsd   [rbp+57h+var_90], xmm1
0x180041909  mov     rax, [rcx]
0x18004190c  lea     r8, [rbp+57h+pExceptionObject]
0x180041910  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180041917  mov     rax, [rax+280h]
0x18004191e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041923  test    eax, eax
0x180041925  js      short loc_180041982
0x180041927  lea     rcx, [rbp+57h+var_50]; pvarg
0x18004192b  call    cs:__imp_VariantClear
0x180041931  nop
0x180041932  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180041936  test    rcx, rcx
0x180041939  jz      short loc_180041942
0x18004193b  call    cs:__imp_SysFreeString
0x180041941  nop
0x180041942  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041946  call    cs:__imp_VariantClear
0x18004194c  nop
0x18004194d  mov     rcx, [rbp+57h+ppstm]
0x180041951  test    rcx, rcx
0x180041954  jz      short loc_180041967
0x180041956  mov     [rbp+57h+ppstm], r14
0x18004195a  mov     rax, [rcx]
0x18004195d  mov     rax, [rax+10h]
0x180041961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041966  nop
0x180041967  mov     rax, rbx
0x18004196a  lea     r11, [rsp+0F0h+var_10]
0x180041972  mov     rbx, [r11+28h]
0x180041976  mov     rsi, [r11+30h]
0x18004197a  mov     rsp, r11
0x18004197d  pop     r14
0x18004197f  pop     rdi
0x180041980  pop     rbp
0x180041981  retn
0x180041982  mov     edx, eax; int
0x180041984  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041988  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004198d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041994  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041998  call    _CxxThrowException_0
0x18004199e  mov     edx, eax; int
0x1800419a0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800419a4  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800419a9  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800419b0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800419b4  call    _CxxThrowException_0
0x1800419ba  mov     edx, eax; int
0x1800419bc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800419c0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800419c5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800419cc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800419d0  call    _CxxThrowException_0
0x1800419d6  mov     edx, eax; int
0x1800419d8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800419dc  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800419e1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800419e8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800419ec  call    _CxxThrowException_0
0x1800419f2  mov     edx, eax; int
0x1800419f4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800419f8  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800419fd  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a04  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a08  call    _CxxThrowException_0
0x180041a0e  mov     edx, eax; int
0x180041a10  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041a14  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041a19  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a20  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a24  call    _CxxThrowException_0
0x180041a2a  mov     edx, eax; int
0x180041a2c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041a30  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041a35  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a3c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a40  call    _CxxThrowException_0
0x180041a46  mov     edx, eax; int
0x180041a48  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041a4c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041a51  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a58  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a5c  call    _CxxThrowException_0
0x180041a62  mov     edx, eax; int
0x180041a64  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041a68  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041a6d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a74  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a78  call    _CxxThrowException_0
0x180041a7e  mov     edx, eax; int
0x180041a80  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041a84  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041a89  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041a90  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041a94  call    _CxxThrowException_0
0x180041a9a  mov     edx, eax; int
0x180041a9c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041aa0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041aa5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041aac  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041ab0  call    _CxxThrowException_0
0x180041ab6  mov     rax, [rbp+57h+var_68]
0x180041aba  mov     [rsp+0F0h+var_C0], rax
0x180041abf  mov     rax, [rbp+57h+var_60]
0x180041ac3  mov     [rsp+0F0h+var_C8], rax
0x180041ac8  mov     eax, [rbp+57h+var_78]
0x180041acb  mov     dword ptr [rsp+0F0h+pPrintTicket], eax
0x180041acf  mov     r9d, [rbp+57h+var_74]
0x180041ad3  mov     r8d, [rbp+57h+var_70]
0x180041ad7  lea     rdx, aErrorParsingPr; "Error parsing PrintTicket XML. Line: %d"...
0x180041ade  lea     rcx, aPrintconfigDev; "PrintConfig::DevModeToPrintTicket"
0x180041ae5  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180041aea  mov     edx, 8000FFFFh; int
0x180041aef  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041af3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041af8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041aff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041b03  call    _CxxThrowException_0
0x180041b09  mov     edx, eax; int
0x180041b0b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180041b0f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180041b14  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180041b1b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180041b1f  call    _CxxThrowException_0
```
