# McpService::SearchCloudPrinters(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_McpPrinterSearchResult * *)

- ea: `0x1800268a0`
- end: `0x180026f05`
- name: `?SearchCloudPrinters@McpService@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU_McpPrinterSearchResult@@@Z`
- size: `1637`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800267f0`
- `0x180026f10`

## callees

- `0x1800045d8`
- `0x180006804`
- `0x18000c4cc`
- `0x18000df30`
- `0x18000e164`
- `0x180010dac`
- `0x180011f68`
- `0x18001b128`
- `0x180022000`
- `0x180025484`
- `0x1800255f4`
- `0x180025a80`
- `0x1800268a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800269d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800269d8`

## string_xrefs

- `0x1800268d2`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180026e8e`: `Failed to create McpPrinterSearchResult, out of memory.`
- `0x180026903`: `McpService::SearchCloudPrinters`
- `0x180026b91`: `McpService::SearchCloudPrinters`
- `0x180026c52`: `McpService::SearchCloudPrinters`
- `0x180026d0f`: `McpService::SearchCloudPrinters`
- `0x180026d73`: `McpService::SearchCloudPrinters`
- `0x180026dd7`: `McpService::SearchCloudPrinters`
- `0x180026d6c`: `Failed to create McpPrinter PrinterUuid, out of memory.`
- `0x180026b8a`: `Failed to create McpPrinter PrinterUrl, out of memory.`
- `0x1800269ea`: `Failed to create McpPrinters array, out of memory.`
- `0x180026dd0`: `Failed to create McpPrinter PrinterName, out of memory.`
- `0x180026c4b`: `Failed to create McpPrinter PrinterDesc, out of memory.`
- `0x180026d08`: `Failed to create McpPrinter OrgLocation, out of memory.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall McpService::SearchCloudPrinters(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  _OWORD *v9; // rax
  _OWORD *v10; // rbx
  CloudPrint::CloudPrinter *v11; // rcx
  char *v12; // r12
  unsigned __int64 i; // r15
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // [rsp+20h] [rbp-58h] BYREF
  __int64 v27; // [rsp+28h] [rbp-50h] BYREF
  __int64 v28; // [rsp+30h] [rbp-48h] BYREF
  CloudPrint::CloudPrinter *v29; // [rsp+38h] [rbp-40h] BYREF
  CloudPrint::CloudPrinter *v30; // [rsp+40h] [rbp-38h]
  __int64 v31; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v33; // [rsp+90h] [rbp+18h] BYREF
  __int64 v34; // [rsp+98h] [rbp+20h] BYREF

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  *a3 = 0;
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  McpManagementTelemetry::WriteDbgTraceInfo("McpService::SearchCloudPrinters", L"Query Params: %s", v6);
  std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(&v29);
  v7 = CloudPrint::CloudPrintHelper::SearchCloudPrinters(*(CloudPrint::CloudPrintHelper **)(a1 + 24));
  v8 = v7;
  if ( v7 < 0 )
  {
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpService::SearchCloudPrinters",
      L"Failed to SearchCloudPrinters. hr=%#x",
      (unsigned int)v7);
    if ( v29 )
    {
      std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
      std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
    }
    return v8;
  }
  v9 = CoTaskMemAlloc(0x10u);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v11 = v29;
    if ( v29 != v30 )
    {
      v12 = (char *)CoTaskMemAlloc(0x6186186186186188LL * ((v30 - v29) >> 3));
      *((_QWORD *)v10 + 1) = v12;
      if ( !v12 )
      {
        McpManagementTelemetry::WriteDbgTraceWarning(
          "McpService::SearchCloudPrinters",
          L"Failed to create McpPrinters array, out of memory.");
        McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
        if ( v29 )
        {
          std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
          std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
        }
        return 2147942414LL;
      }
      memset_0(v12, 0, 0x6186186186186188LL * ((v30 - v29) >> 3));
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xCF3CF3CF3CF3CF3DuLL * ((v30 - v29) >> 3) )
        {
          *(_DWORD *)v10 = *((_DWORD *)v29 + 40);
          *((_DWORD *)v10 + 1) = 1022611261 * ((v30 - v29) >> 3);
          v11 = v29;
          break;
        }
        v14 = 168 * i;
        if ( *((_QWORD *)v29 + 21 * i + 2) )
        {
          v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v29 + v14);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v28,
            v16);
          v17 = v28;
          if ( !v28 )
          {
            McpManagementTelemetry::WriteDbgTraceWarning(
              "McpService::SearchCloudPrinters",
              L"Failed to create McpPrinter PrinterName, out of memory.");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
            McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
            if ( v29 )
            {
              std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
              std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
            }
            return 2147942414LL;
          }
          v28 = 0;
          v15 = 40 * i;
          *(_QWORD *)&v12[40 * i] = v17;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        }
        else
        {
          v15 = 40 * i;
        }
        if ( *(_QWORD *)((char *)v29 + v14 + 48) )
        {
          v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v29 + v14 + 32);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v27,
            v18);
          v19 = v27;
          if ( !v27 )
          {
            McpManagementTelemetry::WriteDbgTraceWarning(
              "McpService::SearchCloudPrinters",
              L"Failed to create McpPrinter PrinterUuid, out of memory.");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
            McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
            if ( v29 )
            {
              std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
              std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
            }
            return 2147942414LL;
          }
          v27 = 0;
          *(_QWORD *)&v12[v15 + 8] = v19;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        }
        if ( *(_QWORD *)((char *)v29 + v14 + 80) )
        {
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v29 + v14 + 64);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v33,
            v20);
          v21 = v33;
          if ( !v33 )
          {
            McpManagementTelemetry::WriteDbgTraceWarning(
              "McpService::SearchCloudPrinters",
              L"Failed to create McpPrinter PrinterUrl, out of memory.");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
            McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
            if ( v29 )
            {
              std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
              std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
            }
            return 2147942414LL;
          }
          v33 = 0;
          *(_QWORD *)&v12[v15 + 16] = v21;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        }
        if ( *(_QWORD *)((char *)v29 + v14 + 112) )
        {
          v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v29 + v14 + 96);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v34,
            v22);
          v23 = v34;
          if ( !v34 )
          {
            McpManagementTelemetry::WriteDbgTraceWarning(
              "McpService::SearchCloudPrinters",
              L"Failed to create McpPrinter PrinterDesc, out of memory.");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
            McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
            if ( v29 )
            {
              std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
              std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
            }
            return 2147942414LL;
          }
          v34 = 0;
          *(_QWORD *)&v12[v15 + 24] = v23;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        }
        if ( *(_QWORD *)((char *)v29 + v14 + 144) )
        {
          v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v29 + v14 + 128);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v26,
            v24);
          v25 = v26;
          if ( !v26 )
          {
            McpManagementTelemetry::WriteDbgTraceWarning(
              "McpService::SearchCloudPrinters",
              L"Failed to create McpPrinter OrgLocation, out of memory.");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
            McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult((struct _McpPrinterSearchResult *)v10);
            if ( v29 )
            {
              std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
              std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
            }
            return 2147942414LL;
          }
          v26 = 0;
          *(_QWORD *)&v12[v15 + 32] = v25;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
        }
      }
    }
    *a3 = v10;
    if ( v11 )
    {
      std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v11);
      std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
    }
    return 0;
  }
  else
  {
    McpManagementTelemetry::WriteDbgTraceWarning(
      "McpService::SearchCloudPrinters",
      L"Failed to create McpPrinterSearchResult, out of memory.");
    if ( v29 )
    {
      std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(v29);
      std::_Deallocate<16>(v29, 8 * ((v31 - (__int64)v29) >> 3));
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800268a0  mov     [rsp+arg_0], rbx
0x1800268a5  mov     [rsp+arg_8], rsi
0x1800268aa  push    rdi
0x1800268ab  push    r12
0x1800268ad  push    r13
0x1800268af  push    r14
0x1800268b1  push    r15
0x1800268b3  sub     rsp, 50h
0x1800268b7  mov     r13, r8
0x1800268ba  mov     rbx, rdx
0x1800268bd  mov     rdi, rcx
0x1800268c0  test    r8, r8
0x1800268c3  jnz     short loc_1800268EA
0x1800268c5  mov     rcx, [rsp+78h]; this
0x1800268ca  mov     ebx, 80004003h
0x1800268cf  mov     r9d, ebx; char *
0x1800268d2  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800268d9  mov     edx, 160h; void *
0x1800268de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268e3  mov     eax, ebx
0x1800268e5  jmp     loc_180026EEA
0x1800268ea  mov     qword ptr [r8], 0
0x1800268f1  mov     rcx, rbx
0x1800268f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800268f9  mov     r8, rax
0x1800268fc  lea     rdx, aQueryParamsS; "Query Params: %s"
0x180026903  lea     r14, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x18002690a  mov     rcx, r14; char *
0x18002690d  call    ?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180026912  lea     rcx, [rsp+78h+var_40]
0x180026917  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x18002691c  lea     r8, [rsp+78h+var_40]
0x180026921  mov     rdx, rbx
0x180026924  mov     rcx, [rdi+18h]; this
0x180026928  call    ?SearchCloudPrinters@CloudPrintHelper@CloudPrint@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@4@@Z; CloudPrint::CloudPrintHelper::SearchCloudPrinters(std::wstring const &,std::vector<CloudPrint::CloudPrinter> *)
0x18002692d  mov     ebx, eax
0x18002692f  test    eax, eax
0x180026931  jns     short loc_18002698B
0x180026933  mov     r8d, eax
0x180026936  lea     rdx, aFailedToSearch; "Failed to SearchCloudPrinters. hr=%#x"
0x18002693d  mov     rcx, r14; char *
0x180026940  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026945  mov     rcx, [rsp+78h+var_40]; this
0x18002694a  test    rcx, rcx
0x18002694d  jz      short loc_180026984
0x18002694f  mov     rdx, [rsp+78h+var_38]
0x180026954  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026959  mov     rcx, [rsp+78h+var_40]
0x18002695e  mov     rax, [rsp+78h+var_30]
0x180026963  sub     rax, rcx
0x180026966  sar     rax, 3
0x18002696a  mov     rdi, 0CF3CF3CF3CF3CF3Dh
0x180026974  imul    rax, rdi
0x180026978  imul    rdx, rax, 0A8h
0x18002697f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026984  mov     eax, ebx
0x180026986  jmp     loc_180026EEA
0x18002698b  mov     ecx, 10h; cb
0x180026990  call    cs:__imp_CoTaskMemAlloc
0x180026996  mov     rbx, rax
0x180026999  test    rax, rax
0x18002699c  jz      loc_180026E8E
0x1800269a2  xorps   xmm0, xmm0
0x1800269a5  movups  xmmword ptr [rax], xmm0
0x1800269a8  mov     rdx, [rsp+78h+var_38]
0x1800269ad  mov     rcx, [rsp+78h+var_40]
0x1800269b2  mov     rdi, 0CF3CF3CF3CF3CF3Dh
0x1800269bc  cmp     rcx, rdx
0x1800269bf  jz      loc_180026E5B
0x1800269c5  sub     rdx, rcx
0x1800269c8  sar     rdx, 3
0x1800269cc  imul    rdx, rdi
0x1800269d0  lea     rcx, [rdx+rdx*4]
0x1800269d4  shl     rcx, 3; cb
0x1800269d8  call    cs:__imp_CoTaskMemAlloc
0x1800269de  mov     r12, rax
0x1800269e1  mov     [rbx+8], rax
0x1800269e5  test    rax, rax
0x1800269e8  jnz     short loc_180026A40
0x1800269ea  lea     rdx, aFailedToCreate_3; "Failed to create McpPrinters array, out"...
0x1800269f1  mov     rcx, r14; char *
0x1800269f4  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800269f9  mov     rcx, rbx; pv
0x1800269fc  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026a01  mov     rcx, [rsp+78h+var_40]; this
0x180026a06  test    rcx, rcx
0x180026a09  jz      short loc_180026A36
0x180026a0b  mov     rdx, [rsp+78h+var_38]
0x180026a10  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026a15  mov     rcx, [rsp+78h+var_40]
0x180026a1a  mov     rax, [rsp+78h+var_30]
0x180026a1f  sub     rax, rcx
0x180026a22  sar     rax, 3
0x180026a26  imul    rax, rdi
0x180026a2a  imul    rdx, rax, 0A8h
0x180026a31  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026a36  mov     eax, 8007000Eh
0x180026a3b  jmp     loc_180026EEA
0x180026a40  mov     rax, [rsp+78h+var_38]
0x180026a45  sub     rax, [rsp+78h+var_40]
0x180026a4a  sar     rax, 3
0x180026a4e  imul    rax, rdi
0x180026a52  lea     r8, [rax+rax*4]
0x180026a56  shl     r8, 3; Size
0x180026a5a  xor     edx, edx; Val
0x180026a5c  mov     rcx, r12; void *
0x180026a5f  call    memset_0
0x180026a64  xor     r15d, r15d
0x180026a67  mov     rcx, [rsp+78h+var_40]
0x180026a6c  mov     rax, [rsp+78h+var_38]
0x180026a71  sub     rax, rcx
0x180026a74  sar     rax, 3
0x180026a78  imul    rax, rdi
0x180026a7c  cmp     r15, rax
0x180026a7f  jnb     loc_180026E34
0x180026a85  imul    rsi, r15, 0A8h
0x180026a8c  cmp     qword ptr [rcx+rsi+10h], 0
0x180026a92  jnz     short loc_180026A9E
0x180026a94  lea     r14, [r15+r15*4]
0x180026a98  shl     r14, 3
0x180026a9c  jmp     short loc_180026AE4
0x180026a9e  add     rcx, rsi
0x180026aa1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026aa6  mov     rdx, rax
0x180026aa9  lea     rcx, [rsp+78h+var_48]
0x180026aae  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026ab3  mov     rcx, [rsp+78h+var_48]
0x180026ab8  test    rcx, rcx
0x180026abb  jz      loc_180026DD0
0x180026ac1  mov     [rsp+78h+var_48], 0
0x180026aca  lea     rax, [r15+r15*4]
0x180026ace  lea     r14, ds:0[rax*8]
0x180026ad6  mov     [r14+r12], rcx
0x180026ada  lea     rcx, [rsp+78h+var_48]
0x180026adf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026ae4  mov     rax, [rsp+78h+var_40]
0x180026ae9  cmp     qword ptr [rax+rsi+30h], 0
0x180026aef  jz      short loc_180026B30
0x180026af1  lea     rcx, [rax+20h]
0x180026af5  add     rcx, rsi
0x180026af8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026afd  mov     rdx, rax
0x180026b00  lea     rcx, [rsp+78h+var_50]
0x180026b05  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026b0a  mov     rax, [rsp+78h+var_50]
0x180026b0f  test    rax, rax
0x180026b12  jz      loc_180026D6C
0x180026b18  mov     [rsp+78h+var_50], 0
0x180026b21  mov     [r14+r12+8], rax
0x180026b26  lea     rcx, [rsp+78h+var_50]
0x180026b2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026b30  mov     rax, [rsp+78h+var_40]
0x180026b35  cmp     qword ptr [rax+rsi+50h], 0
0x180026b3b  jz      loc_180026BF1
0x180026b41  lea     rcx, [rax+40h]
0x180026b45  add     rcx, rsi
0x180026b48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026b4d  mov     rdx, rax
0x180026b50  lea     rcx, [rsp+78h+arg_10]
0x180026b58  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026b5d  mov     rax, [rsp+78h+arg_10]
0x180026b65  test    rax, rax
0x180026b68  jz      short loc_180026B8A
0x180026b6a  mov     [rsp+78h+arg_10], 0
0x180026b76  mov     [r14+r12+10h], rax
0x180026b7b  lea     rcx, [rsp+78h+arg_10]
0x180026b83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026b88  jmp     short loc_180026BF1
0x180026b8a  lea     rdx, aFailedToCreate_7; "Failed to create McpPrinter PrinterUrl,"...
0x180026b91  lea     rcx, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x180026b98  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026b9d  lea     rcx, [rsp+78h+arg_10]
0x180026ba5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026baa  mov     rcx, rbx; pv
0x180026bad  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026bb2  mov     rcx, [rsp+78h+var_40]; this
0x180026bb7  test    rcx, rcx
0x180026bba  jz      short loc_180026BE7
0x180026bbc  mov     rdx, [rsp+78h+var_38]
0x180026bc1  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026bc6  mov     rcx, [rsp+78h+var_40]
0x180026bcb  mov     rax, [rsp+78h+var_30]
0x180026bd0  sub     rax, rcx
0x180026bd3  sar     rax, 3
0x180026bd7  imul    rax, rdi
0x180026bdb  imul    rdx, rax, 0A8h
0x180026be2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026be7  mov     eax, 8007000Eh
0x180026bec  jmp     loc_180026EEA
0x180026bf1  mov     rax, [rsp+78h+var_40]
0x180026bf6  cmp     qword ptr [rax+rsi+70h], 0
0x180026bfc  jz      loc_180026CB2
0x180026c02  lea     rcx, [rax+60h]
0x180026c06  add     rcx, rsi
0x180026c09  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026c0e  mov     rdx, rax
0x180026c11  lea     rcx, [rsp+78h+arg_18]
0x180026c19  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026c1e  mov     rax, [rsp+78h+arg_18]
0x180026c26  test    rax, rax
0x180026c29  jz      short loc_180026C4B
0x180026c2b  mov     [rsp+78h+arg_18], 0
0x180026c37  mov     [r14+r12+18h], rax
0x180026c3c  lea     rcx, [rsp+78h+arg_18]
0x180026c44  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026c49  jmp     short loc_180026CB2
0x180026c4b  lea     rdx, aFailedToCreate_1; "Failed to create McpPrinter PrinterDesc"...
0x180026c52  lea     rcx, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x180026c59  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026c5e  lea     rcx, [rsp+78h+arg_18]
0x180026c66  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026c6b  mov     rcx, rbx; pv
0x180026c6e  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026c73  mov     rcx, [rsp+78h+var_40]; this
0x180026c78  test    rcx, rcx
0x180026c7b  jz      short loc_180026CA8
0x180026c7d  mov     rdx, [rsp+78h+var_38]
0x180026c82  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026c87  mov     rcx, [rsp+78h+var_40]
0x180026c8c  mov     rax, [rsp+78h+var_30]
0x180026c91  sub     rax, rcx
0x180026c94  sar     rax, 3
0x180026c98  imul    rax, rdi
0x180026c9c  imul    rdx, rax, 0A8h
0x180026ca3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026ca8  mov     eax, 8007000Eh
0x180026cad  jmp     loc_180026EEA
0x180026cb2  mov     rax, [rsp+78h+var_40]
0x180026cb7  cmp     qword ptr [rax+rsi+90h], 0
0x180026cc0  jz      short loc_180026D00
0x180026cc2  lea     rcx, [rax+80h]
0x180026cc9  add     rcx, rsi
0x180026ccc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026cd1  mov     rdx, rax
0x180026cd4  lea     rcx, [rsp+78h+var_58]
0x180026cd9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026cde  mov     rax, [rsp+78h+var_58]
0x180026ce3  test    rax, rax
0x180026ce6  jz      short loc_180026D08
0x180026ce8  mov     [rsp+78h+var_58], 0
0x180026cf1  mov     [r14+r12+20h], rax
0x180026cf6  lea     rcx, [rsp+78h+var_58]
0x180026cfb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026d00  inc     r15
0x180026d03  jmp     loc_180026A67
0x180026d08  lea     rdx, aFailedToCreate_5; "Failed to create McpPrinter OrgLocation"...
0x180026d0f  lea     rcx, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x180026d16  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026d1b  lea     rcx, [rsp+78h+var_58]
0x180026d20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026d25  mov     rcx, rbx; pv
0x180026d28  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026d2d  mov     rcx, [rsp+78h+var_40]; this
0x180026d32  test    rcx, rcx
0x180026d35  jz      short loc_180026D62
0x180026d37  mov     rdx, [rsp+78h+var_38]
0x180026d3c  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026d41  mov     rcx, [rsp+78h+var_40]
0x180026d46  mov     rax, [rsp+78h+var_30]
0x180026d4b  sub     rax, rcx
0x180026d4e  sar     rax, 3
0x180026d52  imul    rax, rdi
0x180026d56  imul    rdx, rax, 0A8h
0x180026d5d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026d62  mov     eax, 8007000Eh
0x180026d67  jmp     loc_180026EEA
0x180026d6c  lea     rdx, aFailedToCreate_4; "Failed to create McpPrinter PrinterUuid"...
0x180026d73  lea     rcx, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x180026d7a  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026d7f  lea     rcx, [rsp+78h+var_50]
0x180026d84  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026d89  mov     rcx, rbx; pv
0x180026d8c  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026d91  mov     rcx, [rsp+78h+var_40]; this
0x180026d96  test    rcx, rcx
0x180026d99  jz      short loc_180026DC6
0x180026d9b  mov     rdx, [rsp+78h+var_38]
0x180026da0  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026da5  mov     rcx, [rsp+78h+var_40]
0x180026daa  mov     rax, [rsp+78h+var_30]
0x180026daf  sub     rax, rcx
0x180026db2  sar     rax, 3
0x180026db6  imul    rax, rdi
0x180026dba  imul    rdx, rax, 0A8h
0x180026dc1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026dc6  mov     eax, 8007000Eh
0x180026dcb  jmp     loc_180026EEA
0x180026dd0  lea     rdx, aFailedToCreate_2; "Failed to create McpPrinter PrinterName"...
0x180026dd7  lea     rcx, aMcpserviceSear; "McpService::SearchCloudPrinters"
0x180026dde  call    ?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ; McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180026de3  lea     rcx, [rsp+78h+var_48]
0x180026de8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180026ded  mov     rcx, rbx; pv
0x180026df0  call    ?FreeMcpPrinterSearchResult@McpManagementHelpers@McpManagement@@SAXPEAU_McpPrinterSearchResult@@@Z; McpManagement::McpManagementHelpers::FreeMcpPrinterSearchResult(_McpPrinterSearchResult *)
0x180026df5  mov     rcx, [rsp+78h+var_40]; this
0x180026dfa  test    rcx, rcx
0x180026dfd  jz      short loc_180026E2A
0x180026dff  mov     rdx, [rsp+78h+var_38]
0x180026e04  call    ??$_Destroy_range@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@YAXPEAUCloudPrinter@CloudPrint@@QEAU12@AEAV?$allocator@UCloudPrinter@CloudPrint@@@0@@Z; std::_Destroy_range<std::allocator<CloudPrint::CloudPrinter>>(CloudPrint::CloudPrinter *,CloudPrint::CloudPrinter * const,std::allocator<CloudPrint::CloudPrinter> &)
0x180026e09  mov     rcx, [rsp+78h+var_40]
  ... truncated ...
```
