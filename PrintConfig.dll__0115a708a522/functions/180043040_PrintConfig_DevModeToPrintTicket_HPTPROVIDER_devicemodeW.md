# PrintConfig::DevModeToPrintTicket(HPTPROVIDER__ *,_devicemodeW *)

- ea: `0x180043040`
- end: `0x1800434d2`
- name: `?DevModeToPrintTicket@PrintConfig@@YA?AV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEAUHPTPROVIDER__@@PEAU_devicemodeW@@@Z`
- size: `1170`
- prototype: `LPVOID *__fastcall(LPVOID *ppv, HPTPROVIDER hProvider, PDEVMODE pDevmode)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004862c`
- `0x18004c6b8`

## callees

- `0x180004564`
- `0x18000f830`
- `0x180018f58`
- `0x180043040`
- `0x180053124`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800432db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800432db`
- `OLEAUT32!__imp_VariantInit` at `0x180043125`
- `OLEAUT32!__imp_VariantInit` at `0x18004326c`
- `OLEAUT32!__imp_VariantInit` at `0x180043125`
- `OLEAUT32!__imp_VariantInit` at `0x18004326c`
- `OLEAUT32!__imp_VariantClear` at `0x1800432c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800432ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800432c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800432ec`
- `ole32!CoCreateInstance` at `0x18004310d`
- `ole32!CoCreateInstance` at `0x18004310d`
- `ole32!CreateStreamOnHGlobal` at `0x180043084`
- `ole32!CreateStreamOnHGlobal` at `0x180043084`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800430b5`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x1800430b5`

## string_xrefs

- `0x18004348b`: `PrintConfig::DevModeToPrintTicket`
- `0x180043484`: `Error parsing PrintTicket XML. Line: %d Position: %d Error: %d Reason: %ws Source Text: %ws`
- `0x180043257`: `xmlns:psk='http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords' xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2' xmlns:ns0001 = 'http://schemas.microsoft.com/windows/2018/04/printing/printschemakeywords/Ipp' xmlns:pskv11 = 'http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11'`

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
0x180043040  mov     rax, rsp
0x180043043  mov     [rax+8], rcx
0x180043047  push    rbp
0x180043048  push    rdi
0x180043049  push    r14
0x18004304b  lea     rbp, [rax-5Fh]
0x18004304f  sub     rsp, 0E0h
0x180043056  mov     [rbp+57h+var_20], 0FFFFFFFFFFFFFFFEh
0x18004305e  mov     [rax+10h], rbx
0x180043062  mov     [rax+18h], rsi
0x180043066  mov     rdi, r8
0x180043069  mov     rsi, rdx
0x18004306c  mov     rbx, rcx
0x18004306f  xor     r14d, r14d
0x180043072  mov     [rbp+57h+var_6C], r14d
0x180043076  mov     [rbp+57h+ppstm], r14
0x18004307a  lea     r8, [rbp+57h+ppstm]; ppstm
0x18004307e  lea     edx, [r14+1]; fDeleteOnRelease
0x180043082  xor     ecx, ecx; hGlobal
0x180043084  call    cs:__imp_CreateStreamOnHGlobal
0x18004308b  nop     dword ptr [rax+rax+00h]
0x180043090  test    eax, eax
0x180043092  js      loc_180043367
0x180043098  mov     rcx, [rbp+57h+ppstm]
0x18004309c  movzx   edx, word ptr [rdi+46h]
0x1800430a0  movzx   eax, word ptr [rdi+44h]
0x1800430a4  add     edx, eax; cbDevmode
0x1800430a6  mov     [rsp+0F0h+pPrintTicket], rcx; pPrintTicket
0x1800430ab  lea     r9d, [r14+2]; scope
0x1800430af  mov     r8, rdi; pDevmode
0x1800430b2  mov     rcx, rsi; hProvider
0x1800430b5  call    cs:__imp_PTConvertDevModeToPrintTicket
0x1800430bc  nop     dword ptr [rax+rax+00h]
0x1800430c1  test    eax, eax
0x1800430c3  js      loc_180043383
0x1800430c9  mov     rcx, [rbp+57h+ppstm]
0x1800430cd  mov     edx, r14d
0x1800430d0  mov     rax, [rcx]
0x1800430d3  xor     r9d, r9d
0x1800430d6  xor     r8d, r8d
0x1800430d9  mov     rax, [rax+28h]
0x1800430dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430e2  test    eax, eax
0x1800430e4  js      loc_18004339F
0x1800430ea  mov     [rbx], r14
0x1800430ed  mov     [rbp+57h+var_6C], 1
0x1800430f4  mov     [rsp+0F0h+pPrintTicket], rbx; ppv
0x1800430f9  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180043100  xor     edx, edx; pUnkOuter
0x180043102  lea     r8d, [r14+1]; dwClsContext
0x180043106  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18004310d  call    cs:__imp_CoCreateInstance
0x180043114  nop     dword ptr [rax+rax+00h]
0x180043119  test    eax, eax
0x18004311b  js      loc_1800433BB
0x180043121  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043125  call    cs:__imp_VariantInit
0x18004312c  nop     dword ptr [rax+rax+00h]
0x180043131  nop
0x180043132  lea     eax, [r14+0Dh]
0x180043136  mov     word ptr [rbp+57h+pvarg], ax
0x18004313a  mov     rax, [rbp+57h+ppstm]
0x18004313e  mov     [rbp+57h+ppstm], r14
0x180043142  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180043146  mov     [rbp+57h+arg_18], r14w
0x18004314b  mov     rcx, [rbx]
0x18004314e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180043152  movaps  [rbp+57h+pExceptionObject], xmm0
0x180043156  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18004315b  movsd   [rbp+57h+var_90], xmm1
0x180043160  mov     rax, [rcx]
0x180043163  lea     r8, [rbp+57h+arg_18]
0x180043167  lea     rdx, [rbp+57h+pExceptionObject]
0x18004316b  mov     rax, [rax+1D0h]
0x180043172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043177  cmp     eax, 1
0x18004317a  jnz     loc_18004324F
0x180043180  mov     [rbp+57h+var_80], r14
0x180043184  mov     rcx, [rbx]
0x180043187  mov     rax, [rcx]
0x18004318a  lea     rdx, [rbp+57h+var_80]
0x18004318e  mov     rax, [rax+1E0h]
0x180043195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004319a  test    eax, eax
0x18004319c  js      loc_1800433D7
0x1800431a2  mov     [rbp+57h+var_78], r14d
0x1800431a6  mov     rcx, [rbp+57h+var_80]
0x1800431aa  mov     rax, [rcx]
0x1800431ad  lea     rdx, [rbp+57h+var_78]
0x1800431b1  mov     rax, [rax+38h]
0x1800431b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431ba  test    eax, eax
0x1800431bc  js      loc_1800433F3
0x1800431c2  mov     [rbp+57h+var_70], r14d
0x1800431c6  mov     rcx, [rbp+57h+var_80]
0x1800431ca  mov     rax, [rcx]
0x1800431cd  lea     rdx, [rbp+57h+var_70]
0x1800431d1  mov     rax, [rax+58h]
0x1800431d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431da  test    eax, eax
0x1800431dc  js      loc_18004340F
0x1800431e2  mov     [rbp+57h+var_74], r14d
0x1800431e6  mov     rcx, [rbp+57h+var_80]
0x1800431ea  mov     rax, [rcx]
0x1800431ed  lea     rdx, [rbp+57h+var_74]
0x1800431f1  mov     rax, [rax+60h]
0x1800431f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431fa  test    eax, eax
0x1800431fc  js      loc_18004342B
0x180043202  mov     [rbp+57h+var_60], r14
0x180043206  mov     rcx, [rbp+57h+var_80]
0x18004320a  mov     rax, [rcx]
0x18004320d  mov     [rbp+57h+var_60], r14
0x180043211  lea     rdx, [rbp+57h+var_60]
0x180043215  mov     rax, [rax+48h]
0x180043219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004321e  test    eax, eax
0x180043220  js      loc_180043447
0x180043226  mov     [rbp+57h+var_68], r14
0x18004322a  mov     rcx, [rbp+57h+var_80]
0x18004322e  mov     rax, [rcx]
0x180043231  mov     [rbp+57h+var_68], r14
0x180043235  lea     rdx, [rbp+57h+var_68]
0x180043239  mov     rax, [rax+50h]
0x18004323d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043242  test    eax, eax
0x180043244  js      loc_18004334B
0x18004324a  jmp     loc_180043463
0x18004324f  test    eax, eax
0x180043251  js      loc_1800434B6
0x180043257  lea     rdx, aXmlnsPskHttpSc_0; "xmlns:psk='http://schemas.microsoft.com"...
0x18004325e  lea     rcx, [rbp+57h+bstrString]
0x180043262  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180043267  nop
0x180043268  lea     rcx, [rbp+57h+var_50]; pvarg
0x18004326c  call    cs:__imp_VariantInit
0x180043273  nop     dword ptr [rax+rax+00h]
0x180043278  nop
0x180043279  mov     eax, 8
0x18004327e  mov     word ptr [rbp+57h+var_50], ax
0x180043282  mov     rax, [rbp+57h+bstrString]
0x180043286  mov     [rbp+57h+bstrString], r14
0x18004328a  mov     qword ptr [rbp+57h+var_50+8], rax
0x18004328e  mov     rcx, [rbx]
0x180043291  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x180043295  movaps  [rbp+57h+pExceptionObject], xmm0
0x180043299  movsd   xmm1, qword ptr [rbp+57h+var_50+10h]
0x18004329e  movsd   [rbp+57h+var_90], xmm1
0x1800432a3  mov     rax, [rcx]
0x1800432a6  lea     r8, [rbp+57h+pExceptionObject]
0x1800432aa  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800432b1  mov     rax, [rax+280h]
0x1800432b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432bd  test    eax, eax
0x1800432bf  js      short loc_18004332F
0x1800432c1  lea     rcx, [rbp+57h+var_50]; pvarg
0x1800432c5  call    cs:__imp_VariantClear
0x1800432cc  nop     dword ptr [rax+rax+00h]
0x1800432d1  nop
0x1800432d2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800432d6  test    rcx, rcx
0x1800432d9  jz      short loc_1800432E8
0x1800432db  call    cs:__imp_SysFreeString
0x1800432e2  nop     dword ptr [rax+rax+00h]
0x1800432e7  nop
0x1800432e8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800432ec  call    cs:__imp_VariantClear
0x1800432f3  nop     dword ptr [rax+rax+00h]
0x1800432f8  nop
0x1800432f9  mov     rcx, [rbp+57h+ppstm]
0x1800432fd  test    rcx, rcx
0x180043300  jz      short loc_180043313
0x180043302  mov     [rbp+57h+ppstm], r14
0x180043306  mov     rax, [rcx]
0x180043309  mov     rax, [rax+10h]
0x18004330d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043312  nop
0x180043313  mov     rax, rbx
0x180043316  lea     r11, [rsp+0F0h+var_10]
0x18004331e  mov     rbx, [r11+28h]
0x180043322  mov     rsi, [r11+30h]
0x180043326  mov     rsp, r11
0x180043329  pop     r14
0x18004332b  pop     rdi
0x18004332c  pop     rbp
0x18004332d  retn
0x18004332f  mov     edx, eax; int
0x180043331  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043335  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004333a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043341  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043345  call    _CxxThrowException_0
0x18004334b  mov     edx, eax; int
0x18004334d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043351  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043356  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004335d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043361  call    _CxxThrowException_0
0x180043367  mov     edx, eax; int
0x180043369  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004336d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043372  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043379  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004337d  call    _CxxThrowException_0
0x180043383  mov     edx, eax; int
0x180043385  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043389  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004338e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043395  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043399  call    _CxxThrowException_0
0x18004339f  mov     edx, eax; int
0x1800433a1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800433a5  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800433aa  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800433b1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800433b5  call    _CxxThrowException_0
0x1800433bb  mov     edx, eax; int
0x1800433bd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800433c1  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800433c6  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800433cd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800433d1  call    _CxxThrowException_0
0x1800433d7  mov     edx, eax; int
0x1800433d9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800433dd  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800433e2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800433e9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800433ed  call    _CxxThrowException_0
0x1800433f3  mov     edx, eax; int
0x1800433f5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800433f9  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800433fe  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043405  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043409  call    _CxxThrowException_0
0x18004340f  mov     edx, eax; int
0x180043411  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043415  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004341a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043421  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043425  call    _CxxThrowException_0
0x18004342b  mov     edx, eax; int
0x18004342d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043431  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043436  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004343d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043441  call    _CxxThrowException_0
0x180043447  mov     edx, eax; int
0x180043449  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004344d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043452  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043459  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004345d  call    _CxxThrowException_0
0x180043463  mov     rax, [rbp+57h+var_68]
0x180043467  mov     [rsp+0F0h+var_C0], rax
0x18004346c  mov     rax, [rbp+57h+var_60]
0x180043470  mov     [rsp+0F0h+var_C8], rax
0x180043475  mov     eax, [rbp+57h+var_78]
0x180043478  mov     dword ptr [rsp+0F0h+pPrintTicket], eax
0x18004347c  mov     r9d, [rbp+57h+var_74]
0x180043480  mov     r8d, [rbp+57h+var_70]
0x180043484  lea     rdx, aErrorParsingPr; "Error parsing PrintTicket XML. Line: %d"...
0x18004348b  lea     rcx, aPrintconfigDev; "PrintConfig::DevModeToPrintTicket"
0x180043492  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180043497  mov     edx, 8000FFFFh; int
0x18004349c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800434a0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800434a5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800434ac  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800434b0  call    _CxxThrowException_0
0x1800434b6  mov     edx, eax; int
0x1800434b8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800434bc  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800434c1  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800434c8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800434cc  call    _CxxThrowException_0
```
