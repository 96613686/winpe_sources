# CrossMachineCommunicationServices::CreateSecurityDescriptor(void)

- ea: `0x180024080`
- end: `0x180024366`
- name: `?CreateSecurityDescriptor@CrossMachineCommunicationServices@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `742`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800067f8`
- `0x180012240`
- `0x180012484`
- `0x180016c74`
- `0x180024080`
- `0x1800245f0`
- `0x180024610`
- `0x180024710`
- `0x180024794`
- `0x1800249ec`
- `0x180024a40`
- `0x18002a514`
- `0x18002c958`
- `0x180031540`
- `0x180043680`
- `0x180080d98`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800240f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800240f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800242ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800242ed`

## string_xrefs

- `0x180024108`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x18002415d`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x1800241aa`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180024282`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x1800242b7`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x1800242fe`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
WCHAR *__fastcall CrossMachineCommunicationServices::CreateSecurityDescriptor(__int64 a1, WCHAR *a2)
{
  char v4; // si
  HRESULT v5; // eax
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, int *); // rdi
  int v10; // eax
  __int64 v11; // rax
  bool v12; // bl
  int v13; // eax
  int v14; // eax
  const char *v15; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v22; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v23; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid[3]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR StringSecurityDescriptor[520]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  StringSid[1] = a2;
  v4 = 0;
  *(_QWORD *)v20 = 0;
  if ( BasicUiaUtils::IsOneCore() )
  {
    v23 = 0;
    v5 = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_c0bc943b_c585_40b4_9764_105af9dc62fc, &v23);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v21 = 0;
    v6 = *(_QWORD *)v23;
    v21 = 0;
    v25[0] = *(_OWORD *)(a1 + 8);
    v7 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, __int64 *))(v6 + 24))(v23, v25, &v21);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    v8 = v21;
    if ( v21 )
    {
      v9 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v20,
        0);
      v10 = v9(v8, v20);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
          (const char *)(unsigned int)v10,
          ppv);
    }
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v21);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v23);
  }
  BasicUtils::GetUserSidString(&v22);
  BasicUtils::GetMediumILSidString(StringSid);
  std::wstring::wstring(v25, v22);
  v12 = 0;
  if ( *(_QWORD *)v20 )
  {
    v11 = std::wstring::wstring(v26, *(_QWORD *)v20);
    v4 = 1;
    if ( (unsigned __int8)std::operator!=<unsigned short>(v25, v11) )
      v12 = 1;
  }
  if ( (v4 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v26);
  if ( v12 )
  {
    ppva = v20[0];
    v13 = StringCchPrintfW(
            StringSecurityDescriptor,
            0x208u,
            L"D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;S-1-15-3-1024-3196506428-3189018336-1943045441-722120920-17"
             "1722863-3450400359-103003414-3071717473)(A;;FRFWGA;;;S-1-15-3-1024-1769051910-3479402994-26756494-266398410"
             "1-329771581-1060576799-3920267260-2648751991)S:(ML;;NW;;;%ws)",
            v22);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
        (const char *)(unsigned int)v13,
        ppva);
  }
  else
  {
    ppvb = (int)StringSid[0];
    v14 = StringCchPrintfW(
            StringSecurityDescriptor,
            0x208u,
            L"D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;S-1-15-3-1024-3196506428-3189018336-1943045441-722120920-171722863-345040035"
             "9-103003414-3071717473)(A;;FRFWGA;;;S-1-15-3-1024-1769051910-3479402994-26756494-2663984101-329771581-10605"
             "76799-3920267260-2648751991)S:(ML;;NW;;;%ws)",
            v22);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
        (const char *)(unsigned int)v14,
        ppvb);
  }
  *(_QWORD *)a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a2,
    0);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          (PSECURITY_DESCRIPTOR *)a2,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      v15);
  std::wstring::_Tidy_deallocate(v25);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(StringSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
  return a2;
}

```

## disassembly

```asm
0x180024080  mov     [rsp-8+arg_10], rbx
0x180024085  mov     [rsp-8+arg_18], rsi
0x18002408a  push    rbp
0x18002408b  push    rdi
0x18002408c  push    r14
0x18002408e  lea     rbp, [rsp-3D0h]
0x180024096  sub     rsp, 4D0h
0x18002409d  mov     rax, cs:__security_cookie
0x1800240a4  xor     rax, rsp
0x1800240a7  mov     [rbp+3E0h+var_20], rax
0x1800240ae  mov     r14, rdx
0x1800240b1  mov     rbx, rcx
0x1800240b4  mov     [rsp+4E0h+var_480], rdx
0x1800240b9  xor     esi, esi
0x1800240bb  mov     [rsp+4E0h+var_4B0], esi
0x1800240bf  mov     qword ptr [rsp+4E0h+var_4A8], rsi
0x1800240c4  call    ?IsOneCore@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsOneCore(void)
0x1800240c9  test    al, al
0x1800240cb  jz      loc_1800241D1
0x1800240d1  mov     [rsp+4E0h+var_490], rsi
0x1800240d6  lea     rax, [rsp+4E0h+var_490]
0x1800240db  mov     [rsp+4E0h+ppv], rax; int
0x1800240e0  lea     r9, _GUID_c0bc943b_c585_40b4_9764_105af9dc62fc; riid
0x1800240e7  xor     edx, edx; pUnkOuter
0x1800240e9  lea     r8d, [rsi+4]; dwClsContext
0x1800240ed  lea     rcx, CLSID_UiaManager; rclsid
0x1800240f4  call    cs:__imp_CoCreateInstance
0x1800240fa  mov     rcx, [rbp+3E8h]; this
0x180024101  test    eax, eax
0x180024103  jns     short loc_180024118
0x180024105  mov     r9d, eax; char *
0x180024108  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x18002410f  lea     edx, [rsi+7Bh]; void *
0x180024112  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024118  mov     [rsp+4E0h+var_4A0], 0
0x180024121  mov     rcx, [rsp+4E0h+var_490]
0x180024126  mov     rax, [rcx]
0x180024129  mov     [rsp+4E0h+var_4A0], 0
0x180024132  movups  xmm0, xmmword ptr [rbx+8]
0x180024136  movdqu  [rsp+4E0h+var_470], xmm0
0x18002413c  lea     r8, [rsp+4E0h+var_4A0]
0x180024141  lea     rdx, [rsp+4E0h+var_470]
0x180024146  mov     rax, [rax+18h]
0x18002414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002414f  mov     rcx, [rbp+3E8h]; this
0x180024156  test    eax, eax
0x180024158  jns     short loc_18002416F
0x18002415a  mov     r9d, eax; char *
0x18002415d  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180024164  mov     edx, 7Eh ; '~'; void *
0x180024169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002416f  mov     rbx, [rsp+4E0h+var_4A0]
0x180024174  test    rbx, rbx
0x180024177  jz      short loc_1800241BC
0x180024179  mov     rax, [rbx]
0x18002417c  mov     rdi, [rax+28h]
0x180024180  xor     edx, edx
0x180024182  lea     rcx, [rsp+4E0h+var_4A8]
0x180024187  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002418c  lea     rdx, [rsp+4E0h+var_4A8]
0x180024191  mov     rcx, rbx
0x180024194  mov     rax, rdi
0x180024197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002419c  mov     rcx, [rbp+3E8h]; this
0x1800241a3  test    eax, eax
0x1800241a5  jns     short loc_1800241BC
0x1800241a7  mov     r9d, eax; char *
0x1800241aa  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x1800241b1  mov     edx, 81h; void *
0x1800241b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800241bc  lea     rcx, [rsp+4E0h+var_4A0]
0x1800241c1  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x1800241c6  nop
0x1800241c7  lea     rcx, [rsp+4E0h+var_490]
0x1800241cc  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x1800241d1  lea     rcx, [rsp+4E0h+var_498]; StringSid
0x1800241d6  call    ?GetUserSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; BasicUtils::GetUserSidString(void)
0x1800241db  nop
0x1800241dc  lea     rcx, [rsp+4E0h+StringSid]; StringSid
0x1800241e1  call    ?GetMediumILSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; BasicUtils::GetMediumILSidString(void)
0x1800241e6  nop
0x1800241e7  mov     rdx, [rsp+4E0h+var_498]
0x1800241ec  lea     rcx, [rsp+4E0h+var_470]
0x1800241f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800241f6  nop
0x1800241f7  mov     edi, 1
0x1800241fc  mov     rdx, qword ptr [rsp+4E0h+var_4A8]
0x180024201  test    rdx, rdx
0x180024204  jz      short loc_18002422B
0x180024206  lea     rcx, [rbp+3E0h+var_450]
0x18002420a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002420f  mov     esi, edi
0x180024211  mov     [rsp+4E0h+var_4B0], edi
0x180024215  mov     rdx, rax
0x180024218  lea     rcx, [rsp+4E0h+var_470]
0x18002421d  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x180024222  test    al, al
0x180024224  jz      short loc_18002422B
0x180024226  mov     bl, dil
0x180024229  jmp     short loc_18002422D
0x18002422b  xor     bl, bl
0x18002422d  test    dil, sil
0x180024230  jz      short loc_180024242
0x180024232  and     esi, 0FFFFFFFEh
0x180024235  mov     [rsp+4E0h+var_4B0], esi
0x180024239  lea     rcx, [rbp+3E0h+var_450]
0x18002423d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024242  mov     rax, [rsp+4E0h+StringSid]
0x180024247  mov     r9, [rsp+4E0h+var_498]
0x18002424c  mov     edx, 208h; unsigned __int64
0x180024251  test    bl, bl
0x180024253  jz      short loc_180024294
0x180024255  mov     rcx, qword ptr [rsp+4E0h+var_4A8]
0x18002425a  mov     [rsp+4E0h+var_4B8], rax
0x18002425f  mov     [rsp+4E0h+ppv], rcx; int
0x180024264  lea     r8, aDAFrfwgaWsAFrf; "D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;%ws)(A;"...
0x18002426b  lea     rcx, [rbp+3E0h+StringSecurityDescriptor]; unsigned __int16 *
0x18002426f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024274  mov     rcx, [rbp+3E8h]; this
0x18002427b  test    eax, eax
0x18002427d  jns     short loc_1800242C9
0x18002427f  mov     r9d, eax; char *
0x180024282  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180024289  mov     edx, 96h; void *
0x18002428e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024294  mov     [rsp+4E0h+ppv], rax; int
0x180024299  lea     r8, aDAFrfwgaWsAFrf_0; "D:(A;;FRFWGA;;;%ws)(A;;FRFWGA;;;S-1-15-"...
0x1800242a0  lea     rcx, [rbp+3E0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800242a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800242a9  mov     rcx, [rbp+3E8h]; this
0x1800242b0  test    eax, eax
0x1800242b2  jns     short loc_1800242C9
0x1800242b4  mov     r9d, eax; char *
0x1800242b7  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x1800242be  mov     edx, 0A0h; void *
0x1800242c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800242c9  mov     qword ptr [r14], 0
0x1800242d0  or      esi, 2
0x1800242d3  mov     [rsp+4E0h+var_4B0], esi
0x1800242d7  xor     edx, edx
0x1800242d9  mov     rcx, r14
0x1800242dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800242e1  xor     r9d, r9d; SecurityDescriptorSize
0x1800242e4  mov     r8, r14; SecurityDescriptor
0x1800242e7  mov     edx, edi; StringSDRevision
0x1800242e9  lea     rcx, [rbp+3E0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800242ed  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800242f3  mov     rcx, [rbp+3E8h]; this
0x1800242fa  test    eax, eax
0x1800242fc  jnz     short loc_180024310
0x1800242fe  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180024305  mov     edx, 0A5h; void *
0x18002430a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024310  lea     rcx, [rsp+4E0h+var_470]
0x180024315  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002431a  nop
0x18002431b  lea     rcx, [rsp+4E0h+StringSid]
0x180024320  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024325  nop
0x180024326  lea     rcx, [rsp+4E0h+var_498]
0x18002432b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024330  nop
0x180024331  lea     rcx, [rsp+4E0h+var_4A8]
0x180024336  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002433b  mov     rax, r14
0x18002433e  mov     rcx, [rbp+3E0h+var_20]
0x180024345  xor     rcx, rsp; StackCookie
0x180024348  call    __security_check_cookie
0x18002434d  lea     r11, [rsp+4E0h+var_10]
0x180024355  mov     rbx, [r11+30h]
0x180024359  mov     rsi, [r11+38h]
0x18002435d  mov     rsp, r11
0x180024360  pop     r14
0x180024362  pop     rdi
0x180024363  pop     rbp
0x180024364  retn
```
