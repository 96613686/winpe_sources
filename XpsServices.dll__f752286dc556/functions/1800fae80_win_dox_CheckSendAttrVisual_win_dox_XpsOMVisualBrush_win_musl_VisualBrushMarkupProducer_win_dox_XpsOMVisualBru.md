# win_dox::CheckSendAttrVisual<win_dox::XpsOMVisualBrush,win_musl::VisualBrushMarkupProducer>(win_dox::XpsOMVisualBrush const &,win_scope::scope<wchar_t *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> (win_dox::XpsOMVisualBrush::*)(void),win_dox::XpsOMVisual (win_dox::XpsOMVisualBrush::*)(void),win_musl::VisualBrushMarkupProducer *,void (win_musl::VisualBrushMarkupProducer::*)(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &))

- ea: `0x1800fae80`
- end: `0x1800faf6d`
- name: `??$CheckSendAttrVisual@VXpsOMVisualBrush@win_dox@@VVisualBrushMarkupProducer@win_musl@@@win_dox@@YA_NAEBVXpsOMVisualBrush@0@P810@EBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZP810@EBA?AVXpsOMVisual@0@XZPEAVVisualBrushMarkupProducer@win_musl@@P856@EAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@Z`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce310`
- `0x1800cef24`

## callees

- `0x1800c1178`
- `0x1800c1454`
- `0x1800cc4e8`
- `0x1800cd1bc`
- `0x1800cf450`
- `0x1800fae80`
- `0x1800fb058`
- `0x1800fb070`
- `0x180134b70`
- `0x1801a5cfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faf24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faf37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faf24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faf37`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall win_dox::CheckSendAttrVisual<win_dox::XpsOMVisualBrush,win_musl::VisualBrushMarkupProducer>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdx
  int v7; // eax
  char v8; // bl
  __int64 StaticResource; // rax
  LPVOID pv; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v12[16]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp-28h] BYREF

  win_dox::XpsOMVisualBrush::GetVisual(a1, v12);
  win_dox::XpsOMVisualBrush::GetVisualLookup(a1, &pv);
  v7 = -1;
  v8 = 0;
  if ( pv )
    v7 = dword_180229818;
  if ( v7 == -1 )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
  else
  {
    std::wstring::wstring(v13, v6);
    StaticResource = win_dox::MakeStaticResource(v14);
    std::wstring::operator=(v13, StaticResource);
    std::wstring::_Tidy_deallocate(v14);
    win_musl::VisualBrushMarkupProducer::SetVisual(a4, v13);
    std::wstring::_Tidy_deallocate(v13);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v8 = 1;
  }
  win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence((win_dox::XpsOMDocumentSequence *)v12);
  return v8;
}

```

## disassembly

```asm
0x1800fae80  mov     [rsp-8+arg_8], rbx
0x1800fae85  mov     [rsp-8+arg_10], rdi
0x1800fae8a  push    rbp
0x1800fae8b  mov     rbp, rsp
0x1800fae8e  sub     rsp, 80h
0x1800fae95  mov     rax, cs:__security_cookie
0x1800fae9c  xor     rax, rsp
0x1800fae9f  mov     [rbp+var_8], rax
0x1800faea3  mov     rdi, r9
0x1800faea6  mov     rbx, rcx
0x1800faea9  lea     rdx, [rbp+var_58]
0x1800faead  call    ?GetVisual@XpsOMVisualBrush@win_dox@@QEBA?AVXpsOMVisual@2@XZ; win_dox::XpsOMVisualBrush::GetVisual(void)
0x1800faeb2  nop
0x1800faeb3  lea     rdx, [rbp+pv]
0x1800faeb7  mov     rcx, rbx
0x1800faeba  call    ?GetVisualLookup@XpsOMVisualBrush@win_dox@@QEBA?AV?$scope@PEA_WU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::XpsOMVisualBrush::GetVisualLookup(void)
0x1800faebf  nop
0x1800faec0  or      eax, 0FFFFFFFFh
0x1800faec3  mov     rcx, [rbp+pv]; pv
0x1800faec7  xor     ebx, ebx
0x1800faec9  test    rcx, rcx
0x1800faecc  cmovnz  eax, cs:dword_180229818
0x1800faed3  cmp     eax, 0FFFFFFFFh
0x1800faed6  jz      short loc_1800FAF32
0x1800faed8  lea     rcx, [rbp+var_48]
0x1800faedc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800faee1  nop
0x1800faee2  mov     rdx, [rbp+pv]
0x1800faee6  lea     rcx, [rbp+var_28]
0x1800faeea  call    ?MakeStaticResource@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; win_dox::MakeStaticResource(wchar_t const *)
0x1800faeef  mov     rdx, rax
0x1800faef2  lea     rcx, [rbp+var_48]
0x1800faef6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800faefb  lea     rcx, [rbp+var_28]
0x1800faeff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800faf04  lea     rdx, [rbp+var_48]
0x1800faf08  mov     rcx, rdi
0x1800faf0b  call    ?SetVisual@VisualBrushMarkupProducer@win_musl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; win_musl::VisualBrushMarkupProducer::SetVisual(std::wstring const &)
0x1800faf10  nop
0x1800faf11  lea     rcx, [rbp+var_48]
0x1800faf15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800faf1a  nop
0x1800faf1b  mov     rcx, [rbp+pv]; pv
0x1800faf1f  test    rcx, rcx
0x1800faf22  jz      short loc_1800FAF2E
0x1800faf24  call    cs:__imp_CoTaskMemFree
0x1800faf2a  mov     [rbp+pv], rbx
0x1800faf2e  mov     bl, 1
0x1800faf30  jmp     short loc_1800FAF41
0x1800faf32  test    rcx, rcx
0x1800faf35  jz      short loc_1800FAF41
0x1800faf37  call    cs:__imp_CoTaskMemFree
0x1800faf3d  mov     [rbp+pv], rbx
0x1800faf41  lea     rcx, [rbp+var_58]; this
0x1800faf45  call    ??1XpsOMDocumentSequence@win_dox@@QEAA@XZ; win_dox::XpsOMDocumentSequence::~XpsOMDocumentSequence(void)
0x1800faf4a  mov     al, bl
0x1800faf4c  mov     rcx, [rbp+var_8]
0x1800faf50  xor     rcx, rsp; StackCookie
0x1800faf53  call    __security_check_cookie
0x1800faf58  lea     r11, [rsp+80h+var_s0]
0x1800faf60  mov     rbx, [r11+18h]
0x1800faf64  mov     rdi, [r11+20h]
0x1800faf68  mov     rsp, r11
0x1800faf6b  pop     rbp
0x1800faf6c  retn
```
