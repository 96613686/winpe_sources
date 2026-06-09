# CloudPrint::CloudPrintHelper::MockedCloudPrinters(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<CloudPrint::CloudPrinter,std::allocator<CloudPrint::CloudPrinter>> *)

- ea: `0x180019d74`
- end: `0x18001a3a9`
- name: `?MockedCloudPrinters@CloudPrintHelper@CloudPrint@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@4@@Z`
- size: `1589`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001b128`

## callees

- `0x180003a60`
- `0x1800067a4`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e5e8`
- `0x180010de8`
- `0x1800115c0`
- `0x180011a4c`
- `0x180012808`
- `0x180019d74`
- `0x18001c0a8`
- `0x18001dde8`
- `0x18001df80`

## string_xrefs

- `0x180019e6b`: `https://print.print-ppe.microsoft.com/printers/509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54e0`
- `0x180019f33`: `https://print.print-ppe.microsoft.com/printers/e63df6e2-7287-4a85-adbd-89163a32ac3a`
- `0x180019fec`: `https://print.print-ppe.microsoft.com/printers/e442be92-ffe2-4895-8897-f21313e80e42`
- `0x18001a0b1`: `https://print.print.microsoft.com/printers/c1357df4-a848-455a-bbb2-12c7820785de`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CloudPrint::CloudPrintHelper::MockedCloudPrinters(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v6; // r8
  __int64 v7; // rcx
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rax
  __int64 v33; // rcx
  unsigned __int64 v34; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r10
  __int64 v39; // rcx
  _BYTE *v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r10
  __int64 v43; // r10
  __int64 v44; // r10
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  int v50; // [rsp+20h] [rbp-2E8h]
  _BYTE v51[32]; // [rsp+30h] [rbp-2D8h] BYREF
  _BYTE v52[32]; // [rsp+50h] [rbp-2B8h] BYREF
  _BYTE v53[32]; // [rsp+70h] [rbp-298h] BYREF
  _BYTE v54[32]; // [rsp+90h] [rbp-278h] BYREF
  _BYTE v55[32]; // [rsp+B0h] [rbp-258h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-238h]
  _BYTE v57[32]; // [rsp+E0h] [rbp-228h] BYREF
  _BYTE v58[32]; // [rsp+100h] [rbp-208h] BYREF
  _BYTE v59[32]; // [rsp+120h] [rbp-1E8h] BYREF
  _BYTE v60[32]; // [rsp+140h] [rbp-1C8h] BYREF
  _BYTE v61[32]; // [rsp+160h] [rbp-1A8h] BYREF
  __int64 v62; // [rsp+180h] [rbp-188h]
  _BYTE v63[32]; // [rsp+190h] [rbp-178h] BYREF
  _BYTE v64[32]; // [rsp+1B0h] [rbp-158h] BYREF
  _BYTE v65[32]; // [rsp+1D0h] [rbp-138h] BYREF
  _BYTE v66[32]; // [rsp+1F0h] [rbp-118h] BYREF
  _BYTE v67[32]; // [rsp+210h] [rbp-F8h] BYREF
  __int64 v68; // [rsp+230h] [rbp-D8h]
  _BYTE v69[32]; // [rsp+240h] [rbp-C8h] BYREF
  _BYTE v70[32]; // [rsp+260h] [rbp-A8h] BYREF
  _BYTE v71[32]; // [rsp+280h] [rbp-88h] BYREF
  _BYTE v72[32]; // [rsp+2A0h] [rbp-68h] BYREF
  _BYTE v73[32]; // [rsp+2C0h] [rbp-48h] BYREF
  __int64 v74; // [rsp+2E0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27E,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)0x80004003LL,
      v50);
    return 2147500035LL;
  }
  CloudPrintHelperTelemetry::WriteDbgTraceInfo(
    "CloudPrint::CloudPrintHelper::MockedCloudPrinters",
    L"Returning Mocked Printers");
  std::vector<CloudPrint::CloudPrinter>::clear(a3);
  std::wstring::wstring((__int64)v63);
  std::wstring::wstring((__int64)v64);
  std::wstring::wstring((__int64)v65);
  std::wstring::wstring((__int64)v66);
  std::wstring::wstring((__int64)v67);
  v68 = 0;
  v6 = std::_WChar_traits<unsigned short>::length(L"509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54e0");
  std::wstring::_Assign<unsigned short>((__int64)v64, v7, v6);
  v8 = std::_WChar_traits<unsigned short>::length(L"Cloud Printer A");
  std::wstring::_Assign<unsigned short>((__int64)v63, v9, v8);
  v10 = std::_WChar_traits<unsigned short>::length(L"https://print.print-ppe.microsoft.com/printers/509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54e0");
  std::wstring::_Assign<unsigned short>((__int64)v65, v11, v10);
  v12 = std::_WChar_traits<unsigned short>::length(L"USA\\Microsoft\\Redmond,WA\\Building 27\\3\\3697");
  std::wstring::_Assign<unsigned short>((__int64)v67, v13, v12);
  std::wstring::wstring((__int64)v57);
  std::wstring::wstring((__int64)v58);
  std::wstring::wstring((__int64)v59);
  std::wstring::wstring((__int64)v60);
  std::wstring::wstring((__int64)v61);
  v62 = 0;
  v14 = std::_WChar_traits<unsigned short>::length(L"e63df6e2-7287-4a85-adbd-89163a32ac3a");
  std::wstring::_Assign<unsigned short>((__int64)v58, v15, v14);
  v16 = std::_WChar_traits<unsigned short>::length(L"Cloud Printer B");
  std::wstring::_Assign<unsigned short>((__int64)v57, v17, v16);
  v18 = std::_WChar_traits<unsigned short>::length(L"https://print.print-ppe.microsoft.com/printers/e63df6e2-7287-4a85-adbd-89163a32ac3a");
  std::wstring::_Assign<unsigned short>((__int64)v59, v19, v18);
  v20 = std::_WChar_traits<unsigned short>::length(L"USA\\Microsoft\\Redmond,WA\\Building 28\\1\\1013");
  std::wstring::_Assign<unsigned short>((__int64)v61, v21, v20);
  std::wstring::wstring((__int64)v51);
  std::wstring::wstring((__int64)v52);
  std::wstring::wstring((__int64)v53);
  std::wstring::wstring((__int64)v54);
  std::wstring::wstring((__int64)v55);
  v56 = 0;
  v22 = std::_WChar_traits<unsigned short>::length(L"e442be92-ffe2-4895-8897-f21313e80e42");
  std::wstring::_Assign<unsigned short>((__int64)v52, v23, v22);
  v24 = std::_WChar_traits<unsigned short>::length(L"Cloud Printer C");
  std::wstring::_Assign<unsigned short>((__int64)v51, v25, v24);
  v26 = std::_WChar_traits<unsigned short>::length(L"https://print.print-ppe.microsoft.com/printers/e442be92-ffe2-4895-8897-f21313e80e42");
  std::wstring::_Assign<unsigned short>((__int64)v53, v27, v26);
  v28 = std::_WChar_traits<unsigned short>::length(L"USA\\Microsoft\\Redmond,WA\\Building 28\\2\\2003");
  std::wstring::_Assign<unsigned short>((__int64)v55, v29, v28);
  std::wstring::wstring((__int64)v69);
  std::wstring::wstring((__int64)v70);
  std::wstring::wstring((__int64)v71);
  std::wstring::wstring((__int64)v72);
  std::wstring::wstring((__int64)v73);
  v74 = 0;
  v30 = std::_WChar_traits<unsigned short>::length(L"c1357df4-a848-455a-bbb2-12c7820785de");
  std::wstring::_Assign<unsigned short>((__int64)v70, v31, v30);
  v32 = std::_WChar_traits<unsigned short>::length(L"UPClientRITPPrinter");
  std::wstring::_Assign<unsigned short>((__int64)v69, v33, v32);
  v34 = std::_WChar_traits<unsigned short>::length(L"https://print.print.microsoft.com/printers/c1357df4-a848-455a-bbb2-12c7820785de");
  std::wstring::_Assign<unsigned short>((__int64)v71, v35, v34);
  v36 = std::_WChar_traits<unsigned short>::length(L"USA\\Microsoft\\Redmond,WA\\Studio G\\Test");
  std::wstring::_Assign<unsigned short>((__int64)v73, v37, v36);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_WChar_traits<unsigned short>::length(L"uuid=509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54e0");
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v38) )
  {
    LODWORD(v68) = 1;
    v40 = v63;
    goto LABEL_5;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_WChar_traits<unsigned short>::length(L"uuid=e63df6e2-7287-4a85-adbd-89163a32ac3a");
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v42) )
  {
    LODWORD(v62) = 1;
    v40 = v57;
    goto LABEL_5;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_WChar_traits<unsigned short>::length(L"uuid=e442be92-ffe2-4895-8897-f21313e80e42");
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v43) )
    goto LABEL_10;
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_WChar_traits<unsigned short>::length(L"uuid=c1357df4-a848-455a-bbb2-12c7820785de");
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v44) )
  {
    LODWORD(v74) = 1;
    v40 = v69;
    goto LABEL_5;
  }
  if ( std::wstring::find(a2, L"country=usa&organization=microsoft&site=redmond%2Cwa&building=Building%2028", 0) == -1
    || std::wstring::find(a2, L"keywords=cloud%20printer%20c", 0) == -1 )
  {
    if ( std::wstring::find(a2, L"country=usa&organization=microsoft&site=redmond%2Cwa&building=Building%2028", 0) == -1
      || std::wstring::find(a2, L"keywords=", 0) != -1 )
    {
      LODWORD(v68) = 3;
      LODWORD(v62) = 3;
      LODWORD(v56) = 3;
      v47 = *(_QWORD *)(a3 + 8);
      if ( v47 == *(_QWORD *)(a3 + 16) )
      {
        std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(a3, v47, v63);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(
          v45,
          v47,
          v63);
        *(_QWORD *)(a3 + 8) += 168LL;
      }
      v49 = *(_QWORD *)(a3 + 8);
      if ( v49 == *(_QWORD *)(a3 + 16) )
      {
        std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(a3, v49, v57);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(
          v48,
          v49,
          v57);
        *(_QWORD *)(a3 + 8) += 168LL;
      }
      v41 = *(_QWORD *)(a3 + 8);
      v40 = v51;
      if ( v41 == *(_QWORD *)(a3 + 16) )
        goto LABEL_29;
      goto LABEL_28;
    }
    LODWORD(v62) = 2;
    LODWORD(v56) = 2;
    v46 = *(_QWORD *)(a3 + 8);
    if ( v46 == *(_QWORD *)(a3 + 16) )
    {
      std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(a3, v46, v57);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(
        v45,
        v46,
        v57);
      *(_QWORD *)(a3 + 8) += 168LL;
    }
  }
  else
  {
LABEL_10:
    LODWORD(v56) = 1;
  }
  v40 = v51;
LABEL_5:
  v41 = *(_QWORD *)(a3 + 8);
  if ( v41 == *(_QWORD *)(a3 + 16) )
  {
LABEL_29:
    std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(a3, v41, v40);
    goto LABEL_30;
  }
LABEL_28:
  std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(
    v39,
    v41,
    v40);
  *(_QWORD *)(a3 + 8) += 168LL;
LABEL_30:
  CloudPrint::CloudPrinter::~CloudPrinter((CloudPrint::CloudPrinter *)v69);
  CloudPrint::CloudPrinter::~CloudPrinter((CloudPrint::CloudPrinter *)v51);
  CloudPrint::CloudPrinter::~CloudPrinter((CloudPrint::CloudPrinter *)v57);
  CloudPrint::CloudPrinter::~CloudPrinter((CloudPrint::CloudPrinter *)v63);
  return 0;
}

```

## disassembly

```asm
0x180019d74  mov     [rsp+arg_0], rbx
0x180019d79  push    rdi
0x180019d7a  sub     rsp, 300h
0x180019d81  mov     rax, cs:__security_cookie
0x180019d88  xor     rax, rsp
0x180019d8b  mov     [rsp+308h+var_18], rax
0x180019d93  mov     rbx, r8
0x180019d96  mov     rdi, rdx
0x180019d99  test    rbx, rbx
0x180019d9c  jnz     short loc_180019DC6
0x180019d9e  mov     rcx, [rsp+308h]; this
0x180019da6  mov     ebx, 80004003h
0x180019dab  mov     r9d, ebx; char *
0x180019dae  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180019db5  mov     edx, 27Eh; void *
0x180019dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dbf  mov     eax, ebx
0x180019dc1  jmp     loc_18001A387
0x180019dc6  lea     rdx, aReturningMocke; "Returning Mocked Printers"
0x180019dcd  lea     rcx, aCloudprintClou_31; "CloudPrint::CloudPrintHelper::MockedClo"...
0x180019dd4  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019dd9  mov     rcx, rbx
0x180019ddc  call    ?clear@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAAXXZ; std::vector<CloudPrint::CloudPrinter>::clear(void)
0x180019de1  lea     rcx, [rsp+308h+var_178]
0x180019de9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019dee  lea     rcx, [rsp+308h+var_158]
0x180019df6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019dfb  lea     rcx, [rsp+308h+var_138]
0x180019e03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019e08  lea     rcx, [rsp+308h+var_118]
0x180019e10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019e15  lea     rcx, [rsp+308h+var_F8]
0x180019e1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019e22  nop
0x180019e23  xor     eax, eax
0x180019e25  mov     [rsp+308h+var_D8], rax
0x180019e2d  lea     rcx, a509f1aa0Bdb046; "509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54e0"
0x180019e34  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019e39  mov     r8, rax
0x180019e3c  mov     rdx, rcx
0x180019e3f  lea     rcx, [rsp+308h+var_158]
0x180019e47  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019e4c  lea     rcx, aCloudPrinterA; "Cloud Printer A"
0x180019e53  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019e58  mov     r8, rax
0x180019e5b  mov     rdx, rcx
0x180019e5e  lea     rcx, [rsp+308h+var_178]
0x180019e66  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019e6b  lea     rcx, aHttpsPrintPrin; "https://print.print-ppe.microsoft.com/p"...
0x180019e72  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019e77  mov     r8, rax
0x180019e7a  mov     rdx, rcx
0x180019e7d  lea     rcx, [rsp+308h+var_138]
0x180019e85  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019e8a  lea     rcx, aUsaMicrosoftRe_2; "USA\\Microsoft\\Redmond,WA\\Building 27"...
0x180019e91  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019e96  mov     r8, rax
0x180019e99  mov     rdx, rcx
0x180019e9c  lea     rcx, [rsp+308h+var_F8]
0x180019ea4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019ea9  lea     rcx, [rsp+308h+var_228]
0x180019eb1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019eb6  lea     rcx, [rsp+308h+var_208]
0x180019ebe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019ec3  lea     rcx, [rsp+308h+var_1E8]
0x180019ecb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019ed0  lea     rcx, [rsp+308h+var_1C8]
0x180019ed8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019edd  lea     rcx, [rsp+308h+var_1A8]
0x180019ee5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019eea  nop
0x180019eeb  xor     eax, eax
0x180019eed  mov     [rsp+308h+var_188], rax
0x180019ef5  lea     rcx, aE63df6e272874a; "e63df6e2-7287-4a85-adbd-89163a32ac3a"
0x180019efc  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019f01  mov     r8, rax
0x180019f04  mov     rdx, rcx
0x180019f07  lea     rcx, [rsp+308h+var_208]
0x180019f0f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019f14  lea     rcx, aCloudPrinterB; "Cloud Printer B"
0x180019f1b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019f20  mov     r8, rax
0x180019f23  mov     rdx, rcx
0x180019f26  lea     rcx, [rsp+308h+var_228]
0x180019f2e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019f33  lea     rcx, aHttpsPrintPrin_1; "https://print.print-ppe.microsoft.com/p"...
0x180019f3a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019f3f  mov     r8, rax
0x180019f42  mov     rdx, rcx
0x180019f45  lea     rcx, [rsp+308h+var_1E8]
0x180019f4d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019f52  lea     rcx, aUsaMicrosoftRe_0; "USA\\Microsoft\\Redmond,WA\\Building 28"...
0x180019f59  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019f5e  mov     r8, rax
0x180019f61  mov     rdx, rcx
0x180019f64  lea     rcx, [rsp+308h+var_1A8]
0x180019f6c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019f71  lea     rcx, [rsp+308h+var_2D8]
0x180019f76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019f7b  lea     rcx, [rsp+308h+var_2B8]
0x180019f80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019f85  lea     rcx, [rsp+308h+var_298]
0x180019f8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019f8f  lea     rcx, [rsp+308h+var_278]
0x180019f97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019f9c  lea     rcx, [rsp+308h+var_258]
0x180019fa4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019fa9  nop
0x180019faa  xor     eax, eax
0x180019fac  mov     [rsp+308h+var_238], rax
0x180019fb4  lea     rcx, aE442be92Ffe248; "e442be92-ffe2-4895-8897-f21313e80e42"
0x180019fbb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019fc0  mov     r8, rax
0x180019fc3  mov     rdx, rcx
0x180019fc6  lea     rcx, [rsp+308h+var_2B8]
0x180019fcb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019fd0  lea     rcx, aCloudPrinterC; "Cloud Printer C"
0x180019fd7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019fdc  mov     r8, rax
0x180019fdf  mov     rdx, rcx
0x180019fe2  lea     rcx, [rsp+308h+var_2D8]
0x180019fe7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019fec  lea     rcx, aHttpsPrintPrin_2; "https://print.print-ppe.microsoft.com/p"...
0x180019ff3  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019ff8  mov     r8, rax
0x180019ffb  mov     rdx, rcx
0x180019ffe  lea     rcx, [rsp+308h+var_298]
0x18001a003  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a008  lea     rcx, aUsaMicrosoftRe_1; "USA\\Microsoft\\Redmond,WA\\Building 28"...
0x18001a00f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a014  mov     r8, rax
0x18001a017  mov     rdx, rcx
0x18001a01a  lea     rcx, [rsp+308h+var_258]
0x18001a022  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a027  lea     rcx, [rsp+308h+var_C8]
0x18001a02f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a034  lea     rcx, [rsp+308h+var_A8]
0x18001a03c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a041  lea     rcx, [rsp+308h+var_88]
0x18001a049  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a04e  lea     rcx, [rsp+308h+var_68]
0x18001a056  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a05b  lea     rcx, [rsp+308h+var_48]
0x18001a063  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a068  nop
0x18001a069  xor     eax, eax
0x18001a06b  mov     [rsp+308h+var_28], rax
0x18001a073  lea     rcx, aC1357df4A84845; "c1357df4-a848-455a-bbb2-12c7820785de"
0x18001a07a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a07f  mov     r8, rax
0x18001a082  mov     rdx, rcx
0x18001a085  lea     rcx, [rsp+308h+var_A8]
0x18001a08d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a092  lea     rcx, aUpclientritppr; "UPClientRITPPrinter"
0x18001a099  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a09e  mov     r8, rax
0x18001a0a1  mov     rdx, rcx
0x18001a0a4  lea     rcx, [rsp+308h+var_C8]
0x18001a0ac  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a0b1  lea     rcx, aHttpsPrintPrin_0; "https://print.print.microsoft.com/print"...
0x18001a0b8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a0bd  mov     r8, rax
0x18001a0c0  mov     rdx, rcx
0x18001a0c3  lea     rcx, [rsp+308h+var_88]
0x18001a0cb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a0d0  lea     rcx, aUsaMicrosoftRe; "USA\\Microsoft\\Redmond,WA\\Studio G\\T"...
0x18001a0d7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a0dc  mov     r8, rax
0x18001a0df  mov     rdx, rcx
0x18001a0e2  lea     rcx, [rsp+308h+var_48]
0x18001a0ea  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001a0ef  mov     rcx, rdi
0x18001a0f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a0f7  mov     r10, rax
0x18001a0fa  lea     rcx, aUuid509f1aa0Bd; "uuid=509f1aa0-bdb0-46cf-bd2d-f1ebc3fb54"...
0x18001a101  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a106  mov     r9, rax
0x18001a109  mov     r8, rcx
0x18001a10c  mov     rdx, [rdi+10h]
0x18001a110  mov     rcx, r10
0x18001a113  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001a118  test    al, al
0x18001a11a  jz      short loc_18001A14A
0x18001a11c  mov     dword ptr [rsp+308h+var_D8], 1
0x18001a127  lea     r8, [rsp+308h+var_178]
0x18001a12f  mov     rdx, [rbx+8]
0x18001a133  cmp     rdx, [rbx+10h]
0x18001a137  jnz     loc_18001A333
0x18001a13d  mov     rcx, rbx
0x18001a140  call    ??$_Emplace_reallocate@AEBUCloudPrinter@CloudPrint@@@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@AEAAPEAUCloudPrinter@CloudPrint@@QEAU23@AEBU23@@Z; std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a145  jmp     loc_18001A34B
0x18001a14a  mov     rcx, rdi
0x18001a14d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a152  mov     r10, rax
0x18001a155  lea     rcx, aUuidE63df6e272; "uuid=e63df6e2-7287-4a85-adbd-89163a32ac"...
0x18001a15c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a161  mov     r9, rax
0x18001a164  mov     r8, rcx
0x18001a167  mov     rdx, [rdi+10h]
0x18001a16b  mov     rcx, r10
0x18001a16e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001a173  test    al, al
0x18001a175  jz      short loc_18001A18C
0x18001a177  mov     dword ptr [rsp+308h+var_188], 1
0x18001a182  lea     r8, [rsp+308h+var_228]
0x18001a18a  jmp     short loc_18001A12F
0x18001a18c  mov     rcx, rdi
0x18001a18f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a194  mov     r10, rax
0x18001a197  lea     rcx, aUuidE442be92Ff; "uuid=e442be92-ffe2-4895-8897-f21313e80e"...
0x18001a19e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a1a3  mov     r9, rax
0x18001a1a6  mov     r8, rcx
0x18001a1a9  mov     rdx, [rdi+10h]
0x18001a1ad  mov     rcx, r10
0x18001a1b0  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001a1b5  test    al, al
0x18001a1b7  jz      short loc_18001A1C9
0x18001a1b9  mov     dword ptr [rsp+308h+var_238], 1
0x18001a1c4  jmp     loc_18001A2AE
0x18001a1c9  mov     rcx, rdi
0x18001a1cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a1d1  mov     r10, rax
0x18001a1d4  lea     rcx, aUuidC1357df4A8; "uuid=c1357df4-a848-455a-bbb2-12c7820785"...
0x18001a1db  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001a1e0  mov     r9, rax
0x18001a1e3  mov     r8, rcx
0x18001a1e6  mov     rdx, [rdi+10h]
0x18001a1ea  mov     rcx, r10
0x18001a1ed  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001a1f2  test    al, al
0x18001a1f4  jz      short loc_18001A20E
0x18001a1f6  mov     dword ptr [rsp+308h+var_28], 1
0x18001a201  lea     r8, [rsp+308h+var_C8]
0x18001a209  jmp     loc_18001A12F
0x18001a20e  xor     r8d, r8d
0x18001a211  lea     rdx, aCountryUsaOrga; "country=usa&organization=microsoft&site"...
0x18001a218  mov     rcx, rdi
0x18001a21b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001a220  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a224  jz      short loc_18001A242
0x18001a226  xor     r8d, r8d
0x18001a229  lea     rdx, aKeywordsCloud2; "keywords=cloud%20printer%20c"
0x18001a230  mov     rcx, rdi
0x18001a233  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001a238  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a23c  jnz     loc_18001A1B9
0x18001a242  xor     r8d, r8d
0x18001a245  lea     rdx, aCountryUsaOrga; "country=usa&organization=microsoft&site"...
0x18001a24c  mov     rcx, rdi
0x18001a24f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001a254  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a258  jz      short loc_18001A2B8
0x18001a25a  xor     r8d, r8d
0x18001a25d  lea     rdx, aKeywords_0; "keywords="
0x18001a264  mov     rcx, rdi
0x18001a267  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001a26c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a270  jnz     short loc_18001A2B8
0x18001a272  mov     eax, 2
0x18001a277  mov     dword ptr [rsp+308h+var_188], eax
0x18001a27e  mov     dword ptr [rsp+308h+var_238], eax
0x18001a285  mov     rdx, [rbx+8]
0x18001a289  lea     r8, [rsp+308h+var_228]
0x18001a291  cmp     rdx, [rbx+10h]
0x18001a295  jz      short loc_18001A2A6
0x18001a297  call    ??$construct@UCloudPrinter@CloudPrint@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@SAXAEAV?$allocator@UCloudPrinter@CloudPrint@@@1@QEAUCloudPrinter@CloudPrint@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(std::allocator<CloudPrint::CloudPrinter> &,CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a29c  add     qword ptr [rbx+8], 0A8h
0x18001a2a4  jmp     short loc_18001A2AE
0x18001a2a6  mov     rcx, rbx
0x18001a2a9  call    ??$_Emplace_reallocate@AEBUCloudPrinter@CloudPrint@@@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@AEAAPEAUCloudPrinter@CloudPrint@@QEAU23@AEBU23@@Z; std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a2ae  lea     r8, [rsp+308h+var_2D8]
0x18001a2b3  jmp     loc_18001A12F
0x18001a2b8  mov     eax, 3
0x18001a2bd  mov     dword ptr [rsp+308h+var_D8], eax
0x18001a2c4  mov     dword ptr [rsp+308h+var_188], eax
0x18001a2cb  mov     dword ptr [rsp+308h+var_238], eax
0x18001a2d2  mov     rdx, [rbx+8]
0x18001a2d6  lea     r8, [rsp+308h+var_178]
0x18001a2de  cmp     rdx, [rbx+10h]
0x18001a2e2  jz      short loc_18001A2F3
0x18001a2e4  call    ??$construct@UCloudPrinter@CloudPrint@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@SAXAEAV?$allocator@UCloudPrinter@CloudPrint@@@1@QEAUCloudPrinter@CloudPrint@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(std::allocator<CloudPrint::CloudPrinter> &,CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a2e9  add     qword ptr [rbx+8], 0A8h
0x18001a2f1  jmp     short loc_18001A2FB
0x18001a2f3  mov     rcx, rbx
0x18001a2f6  call    ??$_Emplace_reallocate@AEBUCloudPrinter@CloudPrint@@@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@AEAAPEAUCloudPrinter@CloudPrint@@QEAU23@AEBU23@@Z; std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a2fb  mov     rdx, [rbx+8]
0x18001a2ff  lea     r8, [rsp+308h+var_228]
0x18001a307  cmp     rdx, [rbx+10h]
0x18001a30b  jz      short loc_18001A31C
0x18001a30d  call    ??$construct@UCloudPrinter@CloudPrint@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@SAXAEAV?$allocator@UCloudPrinter@CloudPrint@@@1@QEAUCloudPrinter@CloudPrint@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(std::allocator<CloudPrint::CloudPrinter> &,CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a312  add     qword ptr [rbx+8], 0A8h
0x18001a31a  jmp     short loc_18001A324
0x18001a31c  mov     rcx, rbx
0x18001a31f  call    ??$_Emplace_reallocate@AEBUCloudPrinter@CloudPrint@@@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@AEAAPEAUCloudPrinter@CloudPrint@@QEAU23@AEBU23@@Z; std::vector<CloudPrint::CloudPrinter>::_Emplace_reallocate<CloudPrint::CloudPrinter const &>(CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
0x18001a324  mov     rdx, [rbx+8]
0x18001a328  lea     r8, [rsp+308h+var_2D8]
0x18001a32d  cmp     rdx, [rbx+10h]
0x18001a331  jz      short loc_18001A342
0x18001a333  call    ??$construct@UCloudPrinter@CloudPrint@@AEBU12@@?$_Default_allocator_traits@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@SAXAEAV?$allocator@UCloudPrinter@CloudPrint@@@1@QEAUCloudPrinter@CloudPrint@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<CloudPrint::CloudPrinter>>::construct<CloudPrint::CloudPrinter,CloudPrint::CloudPrinter const &>(std::allocator<CloudPrint::CloudPrinter> &,CloudPrint::CloudPrinter * const,CloudPrint::CloudPrinter const &)
  ... truncated ...
```
