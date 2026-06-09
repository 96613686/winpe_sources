# PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::InitializeRootNode(void)

- ea: `0x1800fca5c`
- end: `0x1800fcf02`
- name: `?InitializeRootNode@PrintDeviceResourcesSerializer@Serializer@PrintDeviceCapabilitiesOM@@AEAA?AV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@XZ`
- size: `1190`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800ee0b4`

## callees

- `0x180004564`
- `0x18001f36c`
- `0x18006a14c`
- `0x18006c72c`
- `0x1800fca5c`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fcb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcc1c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fccab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcd3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcc1c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fccab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fcd3a`
- `OLEAUT32!__imp_VariantInit` at `0x1800fcae3`
- `OLEAUT32!__imp_VariantInit` at `0x1800fcae3`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcb3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcc32`
- `OLEAUT32!__imp_VariantClear` at `0x1800fccc1`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcd50`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcb3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcc32`
- `OLEAUT32!__imp_VariantClear` at `0x1800fccc1`
- `OLEAUT32!__imp_VariantClear` at `0x1800fcd50`

## string_xrefs

- `0x1800fccdb`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x1800fcc4c`: `http://www.w3.org/2001/XMLSchema`
- `0x1800fccf5`: `xmlns:xsi`
- `0x1800fcc66`: `xmlns:xsd`
- `0x1800fcdde`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fce10`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fce42`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fce74`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fcea6`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fced8`: `onecoreuap\internal\printscan\inc\private\print\platform\config\Serializer.hxx`
- `0x1800fcbd7`: `xmlns:xml`
- `0x1800fcbbd`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Serializer::PrintDeviceResourcesSerializer::InitializeRootNode(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // r14
  __int64 (__fastcall *v5)(__int64, __int128 *, __int64, __int64, _QWORD *); // rsi
  __int64 v6; // rdi
  __int64 v7; // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int128 *); // rbx
  VARIANTARG *v12; // rax
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  PrintCore::BStrRAII *v15; // rax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int128 *); // rbx
  VARIANTARG *v19; // rax
  __int128 v20; // xmm6
  IRecordInfo *v21; // xmm7_8
  PrintCore::BStrRAII *v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int128 *); // rbx
  VARIANTARG *v26; // rax
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  PrintCore::BStrRAII *v29; // rax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  void **v35; // [rsp+38h] [rbp-99h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-91h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-89h] BYREF
  IRecordInfo *v38; // [rsp+60h] [rbp-71h]
  __int128 v39; // [rsp+68h] [rbp-69h] BYREF
  IRecordInfo *v40; // [rsp+78h] [rbp-59h]
  _BYTE pExceptionObject[56]; // [rsp+88h] [rbp-49h] BYREF
  void **v42; // [rsp+C0h] [rbp-11h] BYREF
  BSTR v43; // [rsp+C8h] [rbp-9h]
  __int64 v44; // [rsp+D0h] [rbp-1h]
  __int64 v45; // [rsp+138h] [rbp+67h] BYREF
  _QWORD *v46; // [rsp+140h] [rbp+6Fh]
  __int64 v47; // [rsp+148h] [rbp+77h] BYREF

  v46 = a2;
  v44 = -2;
  *a2 = 0;
  *(_DWORD *)&pvarg.vt = 1;
  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64, _QWORD *))(*(_QWORD *)v4 + 448LL);
  v6 = *((_QWORD *)PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v42, &Filename) + 1);
  v7 = *((_QWORD *)PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v35, L"root") + 1);
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  *((_DWORD *)&pvarg.decVal + 4) = 1;
  pvarg.iVal = 22;
  v39 = *(_OWORD *)&pvarg.decVal.Lo32;
  v40 = v38;
  v8 = v5(v4, &v39, v7, v6, a2);
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
  v35 = &PrintCore::BStrRAII::`vftable';
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v42 = &PrintCore::BStrRAII::`vftable';
  if ( v43 )
    SysFreeString(v43);
  v45 = 0;
  v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(
         *a2,
         &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
         &v45);
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
  v10 = v45;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v45 + 360LL);
  v12 = PrintCore::VariantRAII::VariantRAII((VARIANTARG *)&pvarg.decVal.8, L"http://www.w3.org/XML/1998/namespace");
  v13 = *(_OWORD *)&v12->vt;
  pRecInfo = v12->pRecInfo;
  v15 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v35, L"xmlns:xml");
  v39 = v13;
  v40 = pRecInfo;
  v16 = v11(v10, *((_QWORD *)v15 + 1), &v39);
  if ( v16 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v16,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5F8u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v35 = &PrintCore::BStrRAII::`vftable';
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v17 = v45;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v45 + 360LL);
  v19 = PrintCore::VariantRAII::VariantRAII((VARIANTARG *)&pvarg.decVal.8, L"http://www.w3.org/2001/XMLSchema");
  v20 = *(_OWORD *)&v19->vt;
  v21 = v19->pRecInfo;
  v22 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v35, L"xmlns:xsd");
  v39 = v20;
  v40 = v21;
  v23 = v18(v17, *((_QWORD *)v22 + 1), &v39);
  if ( v23 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v23,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x5FEu);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v35 = &PrintCore::BStrRAII::`vftable';
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v24 = v45;
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v45 + 360LL);
  v26 = PrintCore::VariantRAII::VariantRAII((VARIANTARG *)&pvarg.decVal.8, L"http://www.w3.org/2001/XMLSchema-instance");
  v27 = *(_OWORD *)&v26->vt;
  v28 = v26->pRecInfo;
  v29 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v35, L"xmlns:xsi");
  v39 = v27;
  v40 = v28;
  v30 = v25(v24, *((_QWORD *)v29 + 1), &v39);
  if ( v30 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v30,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x604u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v35 = &PrintCore::BStrRAII::`vftable';
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  v47 = 0;
  v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 168LL))(
          *(_QWORD *)(a1 + 24),
          *a2,
          &v47);
  if ( v31 < 0 )
  {
    PrintCore::WindowsError::WindowsError(
      (PrintCore::WindowsError *)pExceptionObject,
      v31,
      "Internal error",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\Serializer.hxx",
      0x608u);
    throw (PrintCore::WindowsError *)pExceptionObject;
  }
  v32 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return a2;
}

```

## disassembly

```asm
0x1800fca5c  mov     rax, rsp
0x1800fca5f  mov     [rax+10h], rdx
0x1800fca63  push    rbp
0x1800fca64  push    rbx
0x1800fca65  push    rsi
0x1800fca66  push    rdi
0x1800fca67  push    r13
0x1800fca69  push    r14
0x1800fca6b  push    r15
0x1800fca6d  lea     rbp, [rax-5Fh]
0x1800fca71  sub     rsp, 0F0h
0x1800fca78  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800fca80  movaps  xmmword ptr [rax-48h], xmm6
0x1800fca84  movaps  xmmword ptr [rax-58h], xmm7
0x1800fca88  mov     r15, rdx
0x1800fca8b  mov     r13, rcx
0x1800fca8e  mov     dword ptr [rsp+120h+pvarg], 0
0x1800fca96  mov     qword ptr [rdx], 0
0x1800fca9d  mov     dword ptr [rsp+120h+pvarg], 1
0x1800fcaa5  mov     r14, [rcx+18h]
0x1800fcaa9  mov     rax, [r14]
0x1800fcaac  mov     rsi, [rax+1C0h]
0x1800fcab3  lea     rdx, Filename; unsigned __int16 *
0x1800fcaba  lea     rcx, [rbp+57h+var_68]; this
0x1800fcabe  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800fcac3  nop
0x1800fcac4  mov     rdi, [rax+8]
0x1800fcac8  lea     rdx, aRoot_0; "root"
0x1800fcacf  lea     rcx, [rsp+120h+var_F0]; this
0x1800fcad4  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800fcad9  nop
0x1800fcada  mov     rbx, [rax+8]
0x1800fcade  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800fcae3  call    cs:__imp_VariantInit
0x1800fcaea  nop     dword ptr [rax+rax+00h]
0x1800fcaef  mov     dword ptr [rbp+57h+pvarg+10h], 1
0x1800fcaf6  mov     eax, 16h
0x1800fcafb  mov     word ptr [rsp+120h+pvarg+8], ax
0x1800fcb00  movups  xmm0, xmmword ptr [rsp+120h+pvarg+8]
0x1800fcb05  movaps  [rbp+57h+var_C0], xmm0
0x1800fcb09  movsd   xmm1, [rbp+57h+var_C8]
0x1800fcb0e  movsd   [rbp+57h+var_B0], xmm1
0x1800fcb13  mov     qword ptr [rsp+120h+var_100], r15
0x1800fcb18  mov     r9, rdi
0x1800fcb1b  mov     r8, rbx
0x1800fcb1e  lea     rdx, [rbp+57h+var_C0]
0x1800fcb22  mov     rcx, r14
0x1800fcb25  mov     rax, rsi
0x1800fcb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcb2d  xor     esi, esi
0x1800fcb2f  test    eax, eax
0x1800fcb31  js      loc_1800FCE08
0x1800fcb37  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800fcb3c  call    cs:__imp_VariantClear
0x1800fcb43  nop     dword ptr [rax+rax+00h]
0x1800fcb48  nop
0x1800fcb49  lea     r14, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x1800fcb50  mov     [rsp+120h+var_F0], r14
0x1800fcb55  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1800fcb5a  test    rcx, rcx
0x1800fcb5d  jz      short loc_1800FCB70
0x1800fcb5f  call    cs:__imp_SysFreeString
0x1800fcb66  nop     dword ptr [rax+rax+00h]
0x1800fcb6b  mov     [rsp+120h+bstrString], rsi
0x1800fcb70  mov     [rbp+57h+var_68], r14
0x1800fcb74  mov     rcx, [rbp+57h+var_60]; bstrString
0x1800fcb78  test    rcx, rcx
0x1800fcb7b  jz      short loc_1800FCB89
0x1800fcb7d  call    cs:__imp_SysFreeString
0x1800fcb84  nop     dword ptr [rax+rax+00h]
0x1800fcb89  mov     [rbp+57h+arg_0], rsi
0x1800fcb8d  mov     rcx, [r15]
0x1800fcb90  mov     rax, [rcx]
0x1800fcb93  lea     r8, [rbp+57h+arg_0]
0x1800fcb97  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800fcb9e  mov     rax, [rax]
0x1800fcba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcba6  nop
0x1800fcba7  test    eax, eax
0x1800fcba9  js      loc_1800FCE3A
0x1800fcbaf  mov     rdi, [rbp+57h+arg_0]
0x1800fcbb3  mov     rax, [rdi]
0x1800fcbb6  mov     rbx, [rax+168h]
0x1800fcbbd  lea     rdx, aHttpWwwW3OrgXm; "http://www.w3.org/XML/1998/namespace"
0x1800fcbc4  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800fcbc9  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800fcbce  nop
0x1800fcbcf  movups  xmm6, xmmword ptr [rax]
0x1800fcbd2  movsd   xmm7, qword ptr [rax+10h]
0x1800fcbd7  lea     rdx, aXmlnsXml; "xmlns:xml"
0x1800fcbde  lea     rcx, [rsp+120h+var_F0]; this
0x1800fcbe3  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800fcbe8  nop
0x1800fcbe9  movaps  [rbp+57h+var_C0], xmm6
0x1800fcbed  movsd   [rbp+57h+var_B0], xmm7
0x1800fcbf2  lea     r8, [rbp+57h+var_C0]
0x1800fcbf6  mov     rdx, [rax+8]
0x1800fcbfa  mov     rcx, rdi
0x1800fcbfd  mov     rax, rbx
0x1800fcc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcc05  test    eax, eax
0x1800fcc07  js      loc_1800FCE6C
0x1800fcc0d  mov     [rsp+120h+var_F0], r14
0x1800fcc12  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1800fcc17  test    rcx, rcx
0x1800fcc1a  jz      short loc_1800FCC2D
0x1800fcc1c  call    cs:__imp_SysFreeString
0x1800fcc23  nop     dword ptr [rax+rax+00h]
0x1800fcc28  mov     [rsp+120h+bstrString], rsi
0x1800fcc2d  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800fcc32  call    cs:__imp_VariantClear
0x1800fcc39  nop     dword ptr [rax+rax+00h]
0x1800fcc3e  mov     rdi, [rbp+57h+arg_0]
0x1800fcc42  mov     rax, [rdi]
0x1800fcc45  mov     rbx, [rax+168h]
0x1800fcc4c  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x1800fcc53  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800fcc58  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800fcc5d  nop
0x1800fcc5e  movups  xmm6, xmmword ptr [rax]
0x1800fcc61  movsd   xmm7, qword ptr [rax+10h]
0x1800fcc66  lea     rdx, aXmlnsXsd; "xmlns:xsd"
0x1800fcc6d  lea     rcx, [rsp+120h+var_F0]; this
0x1800fcc72  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800fcc77  nop
0x1800fcc78  movaps  [rbp+57h+var_C0], xmm6
0x1800fcc7c  movsd   [rbp+57h+var_B0], xmm7
0x1800fcc81  lea     r8, [rbp+57h+var_C0]
0x1800fcc85  mov     rdx, [rax+8]
0x1800fcc89  mov     rcx, rdi
0x1800fcc8c  mov     rax, rbx
0x1800fcc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcc94  test    eax, eax
0x1800fcc96  js      loc_1800FCE9E
0x1800fcc9c  mov     [rsp+120h+var_F0], r14
0x1800fcca1  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1800fcca6  test    rcx, rcx
0x1800fcca9  jz      short loc_1800FCCBC
0x1800fccab  call    cs:__imp_SysFreeString
0x1800fccb2  nop     dword ptr [rax+rax+00h]
0x1800fccb7  mov     [rsp+120h+bstrString], rsi
0x1800fccbc  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800fccc1  call    cs:__imp_VariantClear
0x1800fccc8  nop     dword ptr [rax+rax+00h]
0x1800fcccd  mov     rdi, [rbp+57h+arg_0]
0x1800fccd1  mov     rax, [rdi]
0x1800fccd4  mov     rbx, [rax+168h]
0x1800fccdb  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x1800fcce2  lea     rcx, [rsp+120h+pvarg+8]; this
0x1800fcce7  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x1800fccec  nop
0x1800fcced  movups  xmm6, xmmword ptr [rax]
0x1800fccf0  movsd   xmm7, qword ptr [rax+10h]
0x1800fccf5  lea     rdx, aXmlnsXsi; "xmlns:xsi"
0x1800fccfc  lea     rcx, [rsp+120h+var_F0]; this
0x1800fcd01  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x1800fcd06  nop
0x1800fcd07  movaps  [rbp+57h+var_C0], xmm6
0x1800fcd0b  movsd   [rbp+57h+var_B0], xmm7
0x1800fcd10  lea     r8, [rbp+57h+var_C0]
0x1800fcd14  mov     rdx, [rax+8]
0x1800fcd18  mov     rcx, rdi
0x1800fcd1b  mov     rax, rbx
0x1800fcd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcd23  test    eax, eax
0x1800fcd25  js      loc_1800FCED0
0x1800fcd2b  mov     [rsp+120h+var_F0], r14
0x1800fcd30  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1800fcd35  test    rcx, rcx
0x1800fcd38  jz      short loc_1800FCD4B
0x1800fcd3a  call    cs:__imp_SysFreeString
0x1800fcd41  nop     dword ptr [rax+rax+00h]
0x1800fcd46  mov     [rsp+120h+bstrString], rsi
0x1800fcd4b  lea     rcx, [rsp+120h+pvarg+8]; pvarg
0x1800fcd50  call    cs:__imp_VariantClear
0x1800fcd57  nop     dword ptr [rax+rax+00h]
0x1800fcd5c  mov     [rbp+57h+arg_10], rsi
0x1800fcd60  mov     rcx, [r13+18h]
0x1800fcd64  mov     rax, [rcx]
0x1800fcd67  lea     r8, [rbp+57h+arg_10]
0x1800fcd6b  mov     rdx, [r15]
0x1800fcd6e  mov     rax, [rax+0A8h]
0x1800fcd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcd7a  test    eax, eax
0x1800fcd7c  js      short loc_1800FCDD6
0x1800fcd7e  mov     rcx, [rbp+57h+arg_10]
0x1800fcd82  test    rcx, rcx
0x1800fcd85  jz      short loc_1800FCD98
0x1800fcd87  mov     [rbp+57h+arg_10], rsi
0x1800fcd8b  mov     rax, [rcx]
0x1800fcd8e  mov     rax, [rax+10h]
0x1800fcd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcd97  nop
0x1800fcd98  mov     rcx, [rbp+57h+arg_0]
0x1800fcd9c  test    rcx, rcx
0x1800fcd9f  jz      short loc_1800FCDB2
0x1800fcda1  mov     [rbp+57h+arg_0], rsi
0x1800fcda5  mov     rax, [rcx]
0x1800fcda8  mov     rax, [rax+10h]
0x1800fcdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcdb1  nop
0x1800fcdb2  mov     rax, r15
0x1800fcdb5  lea     r11, [rsp+120h+var_30]
0x1800fcdbd  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fcdc2  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fcdc7  mov     rsp, r11
0x1800fcdca  pop     r15
0x1800fcdcc  pop     r14
0x1800fcdce  pop     r13
0x1800fcdd0  pop     rdi
0x1800fcdd1  pop     rsi
0x1800fcdd2  pop     rbx
0x1800fcdd3  pop     rbp
0x1800fcdd4  retn
0x1800fcdd6  mov     [rsp+120h+var_100], 608h; unsigned int
0x1800fcdde  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fcde5  lea     r8, aInternalError; "Internal error"
0x1800fcdec  mov     edx, eax; int
0x1800fcdee  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fcdf2  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fcdf7  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fcdfe  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fce02  call    _CxxThrowException_0
0x1800fce08  mov     [rsp+120h+var_100], 5EEh; unsigned int
0x1800fce10  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fce17  lea     r8, aInternalError; "Internal error"
0x1800fce1e  mov     edx, eax; int
0x1800fce20  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fce24  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fce29  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fce30  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fce34  call    _CxxThrowException_0
0x1800fce3a  mov     [rsp+120h+var_100], 5F2h; unsigned int
0x1800fce42  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fce49  lea     r8, aInternalError; "Internal error"
0x1800fce50  mov     edx, eax; int
0x1800fce52  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fce56  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fce5b  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fce62  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fce66  call    _CxxThrowException_0
0x1800fce6c  mov     [rsp+120h+var_100], 5F8h; unsigned int
0x1800fce74  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fce7b  lea     r8, aInternalError; "Internal error"
0x1800fce82  mov     edx, eax; int
0x1800fce84  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fce88  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fce8d  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fce94  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fce98  call    _CxxThrowException_0
0x1800fce9e  mov     [rsp+120h+var_100], 5FEh; unsigned int
0x1800fcea6  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fcead  lea     r8, aInternalError; "Internal error"
0x1800fceb4  mov     edx, eax; int
0x1800fceb6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fceba  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fcebf  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fcec6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fceca  call    _CxxThrowException_0
0x1800fced0  mov     [rsp+120h+var_100], 604h; unsigned int
0x1800fced8  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800fcedf  lea     r8, aInternalError; "Internal error"
0x1800fcee6  mov     edx, eax; int
0x1800fcee8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800fceec  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x1800fcef1  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x1800fcef8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800fcefc  call    _CxxThrowException_0
```
