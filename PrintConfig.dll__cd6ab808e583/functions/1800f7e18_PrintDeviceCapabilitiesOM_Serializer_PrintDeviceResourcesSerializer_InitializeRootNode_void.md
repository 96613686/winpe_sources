# PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::InitializeRootNode(void)

- ea: `0x1800f7e18`
- end: `0x1800f8392`
- name: `?InitializeRootNode@PrintDeviceResourcesSerializer@Serializer@PrintDeviceCapabilitiesOM@@AEAA?AV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@XZ`
- size: `1402`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800e9848`

## callees

- `0x180004424`
- `0x18001e9f0`
- `0x18006a064`
- `0x1800f7e18`
- `0x1801c3010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f7e7a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7e9c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7f85`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8005`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8085`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7e7a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7e9c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f7f85`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8005`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f8085`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7f17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7f21`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7fc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8046`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f80c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7f17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7f21`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f7fc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f8046`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f80c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800f7eb8`
- `OLEAUT32!__imp_VariantInit` at `0x1800f7eb8`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7f0d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7fd2`
- `OLEAUT32!__imp_VariantClear` at `0x1800f8052`
- `OLEAUT32!__imp_VariantClear` at `0x1800f80d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7f0d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f7fd2`
- `OLEAUT32!__imp_VariantClear` at `0x1800f8052`
- `OLEAUT32!__imp_VariantClear` at `0x1800f80d2`

## string_xrefs

- `0x1800f805f`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x1800f7fdf`: `http://www.w3.org/2001/XMLSchema`
- `0x1800f7ffe`: `xmlns:xsd`
- `0x1800f807e`: `xmlns:xsi`
- `0x1800f8165`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f8201`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f8233`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f829a`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f8301`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f8368`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800f7f7e`: `xmlns:xml`
- `0x1800f7f58`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::InitializeRootNode(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v4; // r14
  __int64 v5; // r13
  OLECHAR *v6; // rsi
  OLECHAR *v7; // rdi
  int v8; // eax
  int v9; // eax
  _QWORD *v10; // rsi
  __int64 v11; // r14
  __int128 *v12; // rax
  __int128 v13; // xmm6
  __int64 v14; // xmm7_8
  BSTR v15; // rax
  OLECHAR *v16; // rdi
  int v17; // eax
  _QWORD *v18; // rsi
  __int64 v19; // r14
  __int128 *v20; // rax
  __int128 v21; // xmm6
  __int64 v22; // xmm7_8
  BSTR v23; // rax
  OLECHAR *v24; // rdi
  int v25; // eax
  _QWORD *v26; // rsi
  __int64 v27; // r14
  __int128 *v28; // rax
  __int128 v29; // xmm6
  __int64 v30; // xmm7_8
  BSTR v31; // rax
  OLECHAR *v32; // rdi
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  VARIANTARG pvarg; // [rsp+48h] [rbp-89h] BYREF
  __int64 v39; // [rsp+60h] [rbp-71h]
  __int128 v40; // [rsp+68h] [rbp-69h] BYREF
  __int64 v41; // [rsp+78h] [rbp-59h]
  _BYTE pExceptionObject[56]; // [rsp+88h] [rbp-49h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-11h]
  void **v44; // [rsp+C8h] [rbp-9h]
  OLECHAR *v45; // [rsp+D0h] [rbp-1h]
  _QWORD *v46; // [rsp+138h] [rbp+67h] BYREF
  _QWORD *v47; // [rsp+140h] [rbp+6Fh]
  __int64 v48; // [rsp+148h] [rbp+77h] BYREF

  v47 = a2;
  v43 = -2;
  *a2 = 0;
  v4 = *(__int64 **)(a1 + 24);
  v5 = *v4;
  v44 = &PrintCore::BStrRAII::`vftable';
  v6 = SysAllocString(&Filename);
  v45 = v6;
  if ( !v6 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147024882,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
      0x12u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v7 = SysAllocString(L"root");
  if ( !v7 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147024882,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
      0x12u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  *((_DWORD *)&pvarg.decVal + 4) = 1;
  pvarg.iVal = 22;
  v40 = *(_OWORD *)&pvarg.decVal.Lo32;
  v41 = v39;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, OLECHAR *, OLECHAR *, _QWORD *))(v5 + 448))(
         v4,
         &v40,
         v7,
         v6,
         a2);
  if ( v8 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v8,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5EEu);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  SysFreeString(v7);
  SysFreeString(v6);
  v46 = 0;
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))*a2)(
         *a2,
         &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
         &v46);
  if ( v9 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v9,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5F2u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v10 = v46;
  v11 = *v46;
  v12 = (__int128 *)PrintCore::VariantRAII::VariantRAII(
                      (PrintCore::VariantRAII *)&pvarg.decVal.8,
                      L"http://www.w3.org/XML/1998/namespace");
  v13 = *v12;
  v14 = *((_QWORD *)v12 + 2);
  v15 = SysAllocString(L"xmlns:xml");
  v16 = v15;
  if ( !v15 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147024882,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
      0x12u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v40 = v13;
  v41 = v14;
  v17 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int128 *))(v11 + 360))(v10, v15, &v40);
  if ( v17 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v17,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5F8u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  SysFreeString(v16);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v18 = v46;
  v19 = *v46;
  v20 = (__int128 *)PrintCore::VariantRAII::VariantRAII(
                      (PrintCore::VariantRAII *)&pvarg.decVal.8,
                      L"http://www.w3.org/2001/XMLSchema");
  v21 = *v20;
  v22 = *((_QWORD *)v20 + 2);
  v23 = SysAllocString(L"xmlns:xsd");
  v24 = v23;
  if ( !v23 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147024882,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
      0x12u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v40 = v21;
  v41 = v22;
  v25 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int128 *))(v19 + 360))(v18, v23, &v40);
  if ( v25 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v25,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5FEu);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  SysFreeString(v24);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v26 = v46;
  v27 = *v46;
  v28 = (__int128 *)PrintCore::VariantRAII::VariantRAII(
                      (PrintCore::VariantRAII *)&pvarg.decVal.8,
                      L"http://www.w3.org/2001/XMLSchema-instance");
  v29 = *v28;
  v30 = *((_QWORD *)v28 + 2);
  v31 = SysAllocString(L"xmlns:xsi");
  v32 = v31;
  if ( !v31 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      -2147024882,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
      0x12u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v40 = v29;
  v41 = v30;
  v33 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int128 *))(v27 + 360))(v26, v31, &v40);
  if ( v33 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v33,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x604u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  SysFreeString(v32);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v48 = 0;
  v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 168LL))(
          *(_QWORD *)(a1 + 24),
          *a2,
          &v48);
  if ( v34 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v34,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x608u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v35 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
  }
  return a2;
}

```

## disassembly

```asm
0x1800f7e18  mov     rax, rsp
0x1800f7e1b  mov     [rax+10h], rdx
0x1800f7e1f  push    rbp
0x1800f7e20  push    rbx
0x1800f7e21  push    rsi
0x1800f7e22  push    rdi
0x1800f7e23  push    r13
0x1800f7e25  push    r14
0x1800f7e27  push    r15
0x1800f7e29  lea     rbp, [rax-5Fh]
0x1800f7e2d  sub     rsp, 0F0h
0x1800f7e34  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800f7e3c  movaps  xmmword ptr [rax-48h], xmm6
0x1800f7e40  movaps  xmmword ptr [rax-58h], xmm7
0x1800f7e44  mov     rbx, rdx
0x1800f7e47  mov     r15, rcx
0x1800f7e4a  mov     dword ptr [rsp+120h+var_F0], 0
0x1800f7e52  mov     qword ptr [rdx], 0
0x1800f7e59  mov     dword ptr [rsp+120h+var_F0], 1
0x1800f7e61  mov     r14, [rcx+18h]
0x1800f7e65  mov     r13, [r14]
0x1800f7e68  lea     rdi, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x1800f7e6f  mov     [rbp+57h+var_60], rdi
0x1800f7e73  lea     rcx, Filename; psz
0x1800f7e7a  call    cs:__imp_SysAllocString
0x1800f7e80  mov     rsi, rax
0x1800f7e83  mov     [rbp+57h+var_58], rax
0x1800f7e87  test    rax, rax
0x1800f7e8a  jz      loc_1800F818F
0x1800f7e90  mov     [rsp+120h+var_E8], rdi
0x1800f7e95  lea     rcx, aRoot_0; "root"
0x1800f7e9c  call    cs:__imp_SysAllocString
0x1800f7ea2  mov     rdi, rax
0x1800f7ea5  mov     qword ptr [rsp+120h+pvarg], rax
0x1800f7eaa  test    rax, rax
0x1800f7ead  jz      loc_1800F81C4
0x1800f7eb3  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800f7eb8  call    cs:__imp_VariantInit
0x1800f7ebe  mov     dword ptr [rbp+57h+pvarg+10h], 1
0x1800f7ec5  mov     eax, 16h
0x1800f7eca  mov     word ptr [rsp+120h+pvarg+8], ax
0x1800f7ecf  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x1800f7ed4  movaps  [rbp+57h+var_C0], xmm0
0x1800f7ed8  movsd   xmm1, [rbp+57h+var_C8]
0x1800f7edd  movsd   [rbp+57h+var_B0], xmm1
0x1800f7ee2  mov     qword ptr [rsp+120h+var_100], rbx
0x1800f7ee7  mov     r9, rsi
0x1800f7eea  mov     r8, rdi
0x1800f7eed  lea     rdx, [rbp+57h+var_C0]
0x1800f7ef1  mov     rcx, r14
0x1800f7ef4  mov     rax, [r13+1C0h]
0x1800f7efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f00  test    eax, eax
0x1800f7f02  js      loc_1800F81F9
0x1800f7f08  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800f7f0d  call    cs:__imp_VariantClear
0x1800f7f13  nop
0x1800f7f14  mov     rcx, rdi; bstrString
0x1800f7f17  call    cs:__imp_SysFreeString
0x1800f7f1d  nop
0x1800f7f1e  mov     rcx, rsi; bstrString
0x1800f7f21  call    cs:__imp_SysFreeString
0x1800f7f27  mov     [rbp+57h+arg_0], 0
0x1800f7f2f  mov     rcx, [rbx]
0x1800f7f32  mov     rax, [rcx]
0x1800f7f35  lea     r8, [rbp+57h+arg_0]
0x1800f7f39  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800f7f40  mov     rax, [rax]
0x1800f7f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f48  nop
0x1800f7f49  test    eax, eax
0x1800f7f4b  js      loc_1800F822B
0x1800f7f51  mov     rsi, [rbp+57h+arg_0]
0x1800f7f55  mov     r14, [rsi]
0x1800f7f58  lea     rdx, aHttpWwwW3OrgXm; "http://www.w3.org/XML/1998/namespace"
0x1800f7f5f  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800f7f64  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800f7f69  nop
0x1800f7f6a  movups  xmm6, xmmword ptr [rax]
0x1800f7f6d  movsd   xmm7, qword ptr [rax+10h]
0x1800f7f72  lea     r13, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x1800f7f79  mov     [rsp+120h+var_E8], r13
0x1800f7f7e  lea     rcx, aXmlnsXml; "xmlns:xml"
0x1800f7f85  call    cs:__imp_SysAllocString
0x1800f7f8b  mov     rdi, rax
0x1800f7f8e  mov     qword ptr [rsp+120h+pvarg], rax
0x1800f7f93  test    rax, rax
0x1800f7f96  jz      loc_1800F825D
0x1800f7f9c  movaps  [rbp+57h+var_C0], xmm6
0x1800f7fa0  movsd   [rbp+57h+var_B0], xmm7
0x1800f7fa5  lea     r8, [rbp+57h+var_C0]
0x1800f7fa9  mov     rdx, rax
0x1800f7fac  mov     rcx, rsi
0x1800f7faf  mov     rax, [r14+168h]
0x1800f7fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7fbb  test    eax, eax
0x1800f7fbd  js      loc_1800F8292
0x1800f7fc3  mov     rcx, rdi; bstrString
0x1800f7fc6  call    cs:__imp_SysFreeString
0x1800f7fcc  nop
0x1800f7fcd  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800f7fd2  call    cs:__imp_VariantClear
0x1800f7fd8  mov     rsi, [rbp+57h+arg_0]
0x1800f7fdc  mov     r14, [rsi]
0x1800f7fdf  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x1800f7fe6  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800f7feb  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800f7ff0  nop
0x1800f7ff1  movups  xmm6, xmmword ptr [rax]
0x1800f7ff4  movsd   xmm7, qword ptr [rax+10h]
0x1800f7ff9  mov     [rsp+120h+var_E8], r13
0x1800f7ffe  lea     rcx, aXmlnsXsd; "xmlns:xsd"
0x1800f8005  call    cs:__imp_SysAllocString
0x1800f800b  mov     rdi, rax
0x1800f800e  mov     qword ptr [rsp+120h+pvarg], rax
0x1800f8013  test    rax, rax
0x1800f8016  jz      loc_1800F82C4
0x1800f801c  movaps  [rbp+57h+var_C0], xmm6
0x1800f8020  movsd   [rbp+57h+var_B0], xmm7
0x1800f8025  lea     r8, [rbp+57h+var_C0]
0x1800f8029  mov     rdx, rax
0x1800f802c  mov     rcx, rsi
0x1800f802f  mov     rax, [r14+168h]
0x1800f8036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f803b  test    eax, eax
0x1800f803d  js      loc_1800F82F9
0x1800f8043  mov     rcx, rdi; bstrString
0x1800f8046  call    cs:__imp_SysFreeString
0x1800f804c  nop
0x1800f804d  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800f8052  call    cs:__imp_VariantClear
0x1800f8058  mov     rsi, [rbp+57h+arg_0]
0x1800f805c  mov     r14, [rsi]
0x1800f805f  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x1800f8066  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800f806b  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800f8070  nop
0x1800f8071  movups  xmm6, xmmword ptr [rax]
0x1800f8074  movsd   xmm7, qword ptr [rax+10h]
0x1800f8079  mov     [rsp+120h+var_E8], r13
0x1800f807e  lea     rcx, aXmlnsXsi; "xmlns:xsi"
0x1800f8085  call    cs:__imp_SysAllocString
0x1800f808b  mov     rdi, rax
0x1800f808e  mov     qword ptr [rsp+120h+pvarg], rax
0x1800f8093  test    rax, rax
0x1800f8096  jz      loc_1800F832B
0x1800f809c  movaps  [rbp+57h+var_C0], xmm6
0x1800f80a0  movsd   [rbp+57h+var_B0], xmm7
0x1800f80a5  lea     r8, [rbp+57h+var_C0]
0x1800f80a9  mov     rdx, rax
0x1800f80ac  mov     rcx, rsi
0x1800f80af  mov     rax, [r14+168h]
0x1800f80b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80bb  test    eax, eax
0x1800f80bd  js      loc_1800F8360
0x1800f80c3  mov     rcx, rdi; bstrString
0x1800f80c6  call    cs:__imp_SysFreeString
0x1800f80cc  nop
0x1800f80cd  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800f80d2  call    cs:__imp_VariantClear
0x1800f80d8  mov     [rbp+57h+arg_10], 0
0x1800f80e0  mov     rcx, [r15+18h]
0x1800f80e4  mov     rax, [rcx]
0x1800f80e7  lea     r8, [rbp+57h+arg_10]
0x1800f80eb  mov     rdx, [rbx]
0x1800f80ee  mov     rax, [rax+0A8h]
0x1800f80f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80fa  test    eax, eax
0x1800f80fc  js      short loc_1800F815D
0x1800f80fe  mov     rcx, [rbp+57h+arg_10]
0x1800f8102  test    rcx, rcx
0x1800f8105  jz      short loc_1800F811C
0x1800f8107  mov     [rbp+57h+arg_10], 0
0x1800f810f  mov     rax, [rcx]
0x1800f8112  mov     rax, [rax+10h]
0x1800f8116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f811b  nop
0x1800f811c  mov     rcx, [rbp+57h+arg_0]
0x1800f8120  test    rcx, rcx
0x1800f8123  jz      short loc_1800F813A
0x1800f8125  mov     [rbp+57h+arg_0], 0
0x1800f812d  mov     rax, [rcx]
0x1800f8130  mov     rax, [rax+10h]
0x1800f8134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8139  nop
0x1800f813a  mov     rax, rbx
0x1800f813d  lea     r11, [rsp+120h+var_30]
0x1800f8145  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f814a  movaps  xmm7, xmmword ptr [r11-20h]
0x1800f814f  mov     rsp, r11
0x1800f8152  pop     r15
0x1800f8154  pop     r14
0x1800f8156  pop     r13
0x1800f8158  pop     rdi
0x1800f8159  pop     rsi
0x1800f815a  pop     rbx
0x1800f815b  pop     rbp
0x1800f815c  retn
0x1800f815d  mov     [rsp+120h+var_100], 608h; unsigned int
0x1800f8165  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f816c  lea     r8, aInternalError; "Internal error"
0x1800f8173  mov     edx, eax; int
0x1800f8175  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f8179  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f817e  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8185  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f8189  call    _CxxThrowException_0
0x1800f818f  mov     [rsp+120h+var_100], 12h; unsigned int
0x1800f8197  lea     r9, aOnecoreuapInte_12; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f819e  lea     r8, aUnspecified; "Unspecified."
0x1800f81a5  mov     edx, 8007000Eh; int
0x1800f81aa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f81ae  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f81b3  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f81ba  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f81be  call    _CxxThrowException_0
0x1800f81c4  mov     [rsp+120h+var_100], 12h; unsigned int
0x1800f81cc  lea     r9, aOnecoreuapInte_12; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f81d3  lea     r8, aUnspecified; "Unspecified."
0x1800f81da  mov     edx, 8007000Eh; int
0x1800f81df  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f81e3  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f81e8  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f81ef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f81f3  call    _CxxThrowException_0
0x1800f81f9  mov     [rsp+120h+var_100], 5EEh; unsigned int
0x1800f8201  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f8208  lea     r8, aInternalError; "Internal error"
0x1800f820f  mov     edx, eax; int
0x1800f8211  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f8215  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f821a  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8221  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f8225  call    _CxxThrowException_0
0x1800f822b  mov     [rsp+120h+var_100], 5F2h; unsigned int
0x1800f8233  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f823a  lea     r8, aInternalError; "Internal error"
0x1800f8241  mov     edx, eax; int
0x1800f8243  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f8247  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f824c  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8253  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f8257  call    _CxxThrowException_0
0x1800f825d  mov     [rsp+120h+var_100], 12h; unsigned int
0x1800f8265  lea     r9, aOnecoreuapInte_12; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f826c  lea     r8, aUnspecified; "Unspecified."
0x1800f8273  mov     edx, 8007000Eh; int
0x1800f8278  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f827c  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f8281  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8288  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f828c  call    _CxxThrowException_0
0x1800f8292  mov     [rsp+120h+var_100], 5F8h; unsigned int
0x1800f829a  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f82a1  lea     r8, aInternalError; "Internal error"
0x1800f82a8  mov     edx, eax; int
0x1800f82aa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f82ae  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f82b3  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f82ba  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f82be  call    _CxxThrowException_0
0x1800f82c4  mov     [rsp+120h+var_100], 12h; unsigned int
0x1800f82cc  lea     r9, aOnecoreuapInte_12; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f82d3  lea     r8, aUnspecified; "Unspecified."
0x1800f82da  mov     edx, 8007000Eh; int
0x1800f82df  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f82e3  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f82e8  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f82ef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f82f3  call    _CxxThrowException_0
0x1800f82f9  mov     [rsp+120h+var_100], 5FEh; unsigned int
0x1800f8301  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f8308  lea     r8, aInternalError; "Internal error"
0x1800f830f  mov     edx, eax; int
0x1800f8311  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f8315  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f831a  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8321  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f8325  call    _CxxThrowException_0
0x1800f832b  mov     [rsp+120h+var_100], 12h; unsigned int
0x1800f8333  lea     r9, aOnecoreuapInte_12; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f833a  lea     r8, aUnspecified; "Unspecified."
0x1800f8341  mov     edx, 8007000Eh; int
0x1800f8346  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f834a  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f834f  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8356  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f835a  call    _CxxThrowException_0
0x1800f8360  mov     [rsp+120h+var_100], 604h; unsigned int
0x1800f8368  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800f836f  lea     r8, aInternalError; "Internal error"
0x1800f8376  mov     edx, eax; int
0x1800f8378  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800f837c  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800f8381  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800f8388  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800f838c  call    _CxxThrowException_0
```
