# CloudPrint::CloudPrintHelper::GetMpsConfig(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800154fc`
- end: `0x1800157b4`
- name: `?GetMpsConfig@CloudPrintHelper@CloudPrint@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `696`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001963c`

## callees

- `0x180003a60`
- `0x1800067a4`
- `0x180007468`
- `0x18000e164`
- `0x18000e208`
- `0x18000e5e8`
- `0x180012700`
- `0x180012bc0`
- `0x1800154fc`
- `0x1800169f4`
- `0x18001a404`
- `0x18001bfe4`
- `0x18001c0a8`
- `0x18001df80`

## string_xrefs

- `0x180015730`: `https://graph.microsoft.com/v1.0`
- `0x18001553c`: `GetMpsConfig`
- `0x180015770`: `MPS configured with OAuthAuthority=%s, MSGraphResourceId=%s, MSGraphBaseUrl=%s`
- `0x180015777`: `CloudPrint::CloudPrintHelper::GetMpsConfig`

## pseudocode

```c
void __fastcall CloudPrint::CloudPrintHelper::GetMpsConfig(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r14
  __int64 v5; // r13
  __int64 v6; // r15
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 StringValue; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  const char *v21; // r9
  __int64 v22; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-D0h]
  __int64 v25; // [rsp+50h] [rbp-C8h]
  __int64 v26; // [rsp+58h] [rbp-C0h]
  _BYTE v27[80]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v28[32]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v24 = a2;
  v25 = a3;
  v26 = a4;
  CloudPrintHelperTelemetry::WatchCurrentThread(v27, "GetMpsConfig");
  try
  {
    try
    {
      v8 = CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(a1, 0, 0, 131097);
      v10 = v8;
      v23 = v8;
      if ( v8 )
      {
        v22 = v8;
        StringValue = PrintCore::RegHelpers::GetStringValue(v28, &v22, v9, L"OAuthAuthority");
        std::wstring::operator=(v6, StringValue);
        std::wstring::_Tidy_deallocate(v28);
        v22 = v10;
        v13 = PrintCore::RegHelpers::GetStringValue(v28, &v22, v12, L"MSGraphResourceId");
        std::wstring::operator=(v5, v13);
        std::wstring::_Tidy_deallocate(v28);
        v22 = v10;
        v15 = PrintCore::RegHelpers::GetStringValue(v28, &v22, v14, L"MSGraphBaseUrl");
        std::wstring::operator=(v4, v15);
        std::wstring::_Tidy_deallocate(v28);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x46C,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        v16);
      v6 = v24;
      v5 = v25;
      v4 = v26;
    }
    std::_WChar_traits<unsigned short>::length(L"organizations");
    std::wstring::_Assign<unsigned short>(v6, v17);
    std::_WChar_traits<unsigned short>::length(L"00000003-0000-0000-c000-000000000000");
    std::wstring::_Assign<unsigned short>(v5, v18);
    std::_WChar_traits<unsigned short>::length(L"https://graph.microsoft.com/v1.0");
    std::wstring::_Assign<unsigned short>(v4, v19);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    CloudPrintHelperTelemetry::WriteDbgTraceInfo(
      "CloudPrint::CloudPrintHelper::GetMpsConfig",
      L"MPS configured with OAuthAuthority=%s, MSGraphResourceId=%s, MSGraphBaseUrl=%s",
      v20);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v27);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x481,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      v21);
  }
}

```

## disassembly

```asm
0x1800154fc  push    rbx
0x1800154fe  push    rsi
0x1800154ff  push    rdi
0x180015500  push    r12
0x180015502  push    r13
0x180015504  push    r14
0x180015506  push    r15
0x180015508  sub     rsp, 0E0h
0x18001550f  mov     rax, cs:__security_cookie
0x180015516  xor     rax, rsp
0x180015519  mov     [rsp+118h+var_48], rax
0x180015521  mov     r14, r9
0x180015524  mov     r13, r8
0x180015527  mov     r15, rdx
0x18001552a  mov     rbx, rcx
0x18001552d  mov     [rsp+118h+var_D0], rdx
0x180015532  mov     [rsp+118h+var_C8], r8
0x180015537  mov     [rsp+118h+var_C0], r9
0x18001553c  lea     rdx, aGetmpsconfig; "GetMpsConfig"
0x180015543  lea     rcx, [rsp+118h+var_B8]
0x180015548  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001554d  nop
0x18001554e  xor     sil, sil
0x180015551  mov     [rsp+118h+var_E7], sil
0x180015556  xor     r12b, r12b
0x180015559  mov     [rsp+118h+var_E6], r12b
0x18001555e  xor     dil, dil
0x180015561  mov     [rsp+118h+var_E5], dil
0x180015566  mov     [rsp+118h+var_E8], dil
0x18001556b  mov     r9d, 20019h
0x180015571  xor     r8d, r8d
0x180015574  xor     edx, edx
0x180015576  mov     rcx, rbx
0x180015579  call    ?OpenCurrentUserMpsRegKey@CloudPrintHelper@CloudPrint@@IEAAPEAUHKEY__@@W4MpsRegKey@2@_NK@Z; CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(CloudPrint::MpsRegKey,bool,ulong)
0x18001557e  mov     rbx, rax
0x180015581  mov     [rsp+118h+var_D8], rax
0x180015586  test    rax, rax
0x180015589  jz      loc_1800156C2
0x18001558f  mov     [rsp+118h+var_E0], rax
0x180015594  lea     rax, [rsp+118h+var_E8]
0x180015599  mov     [rsp+118h+var_F0], rax
0x18001559e  lea     r9, aOauthauthority; "OAuthAuthority"
0x1800155a5  lea     rdx, [rsp+118h+var_E0]
0x1800155aa  lea     rcx, [rsp+118h+var_68]
0x1800155b2  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x1800155b7  mov     rdx, rax
0x1800155ba  mov     rcx, r15
0x1800155bd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800155c2  lea     rcx, [rsp+118h+var_68]
0x1800155ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800155cf  cmp     [rsp+118h+var_E8], dil
0x1800155d4  jz      short loc_1800155FD
0x1800155d6  xor     r8d, r8d
0x1800155d9  lea     rdx, aHttps; "https://"
0x1800155e0  mov     rcx, r15
0x1800155e3  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800155e8  movzx   esi, sil
0x1800155ec  mov     ecx, 1
0x1800155f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800155f5  cmovnz  esi, ecx
0x1800155f8  mov     [rsp+118h+var_E7], sil
0x1800155fd  mov     [rsp+118h+var_E0], rbx
0x180015602  lea     rax, [rsp+118h+var_E8]
0x180015607  mov     [rsp+118h+var_F0], rax
0x18001560c  lea     r9, aMsgraphresourc; "MSGraphResourceId"
0x180015613  lea     rdx, [rsp+118h+var_E0]
0x180015618  lea     rcx, [rsp+118h+var_68]
0x180015620  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x180015625  mov     rdx, rax
0x180015628  mov     rcx, r13
0x18001562b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015630  lea     rcx, [rsp+118h+var_68]
0x180015638  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001563d  movzx   r12d, r12b
0x180015641  cmp     [rsp+118h+var_E8], 0
0x180015646  mov     eax, 1
0x18001564b  cmovnz  r12d, eax
0x18001564f  mov     [rsp+118h+var_E6], r12b
0x180015654  mov     [rsp+118h+var_E0], rbx
0x180015659  lea     rax, [rsp+118h+var_E8]
0x18001565e  mov     [rsp+118h+var_F0], rax
0x180015663  lea     r9, aMsgraphbaseurl; "MSGraphBaseUrl"
0x18001566a  lea     rdx, [rsp+118h+var_E0]
0x18001566f  lea     rcx, [rsp+118h+var_68]
0x180015677  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x18001567c  mov     rdx, rax
0x18001567f  mov     rcx, r14
0x180015682  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015687  lea     rcx, [rsp+118h+var_68]
0x18001568f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015694  cmp     [rsp+118h+var_E8], 0
0x180015699  jz      short loc_1800156C2
0x18001569b  xor     r8d, r8d
0x18001569e  lea     rdx, aHttps; "https://"
0x1800156a5  mov     rcx, r14
0x1800156a8  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800156ad  movzx   edi, dil
0x1800156b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800156b5  mov     eax, 1
0x1800156ba  cmovnz  edi, eax
0x1800156bd  mov     [rsp+118h+var_E5], dil
0x1800156c2  lea     rcx, [rsp+118h+var_D8]
0x1800156c7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800156cc  nop
0x1800156cd  jmp     short loc_1800156ED
0x1800156cf  mov     sil, [rsp+118h+var_E7]
0x1800156d4  mov     r12b, [rsp+118h+var_E6]
0x1800156d9  mov     dil, [rsp+118h+var_E5]
0x1800156de  mov     r15, [rsp+118h+var_D0]
0x1800156e3  mov     r13, [rsp+118h+var_C8]
0x1800156e8  mov     r14, [rsp+118h+var_C0]
0x1800156ed  test    sil, sil
0x1800156f0  jnz     short loc_18001570C
0x1800156f2  lea     rcx, aOrganizations; "organizations"
0x1800156f9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800156fe  mov     r8, rax
0x180015701  mov     rdx, rcx
0x180015704  mov     rcx, r15
0x180015707  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001570c  test    r12b, r12b
0x18001570f  jnz     short loc_18001572B
0x180015711  lea     rcx, a00000003000000; "00000003-0000-0000-c000-000000000000"
0x180015718  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001571d  mov     r8, rax
0x180015720  mov     rdx, rcx
0x180015723  mov     rcx, r13
0x180015726  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001572b  test    dil, dil
0x18001572e  jnz     short loc_18001574A
0x180015730  lea     rcx, aHttpsGraphMicr_0; "https://graph.microsoft.com/v1.0"
0x180015737  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001573c  mov     r8, rax
0x18001573f  mov     rdx, rcx
0x180015742  mov     rcx, r14
0x180015745  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001574a  mov     rcx, r14
0x18001574d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015752  mov     rdx, rax
0x180015755  mov     rcx, r13
0x180015758  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001575d  mov     r9, rax
0x180015760  mov     rcx, r15
0x180015763  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015768  mov     [rsp+118h+var_F8], rdx
0x18001576d  mov     r8, rax
0x180015770  lea     rdx, aMpsConfiguredW; "MPS configured with OAuthAuthority=%s, "...
0x180015777  lea     rcx, aCloudprintClou_22; "CloudPrint::CloudPrintHelper::GetMpsCon"...
0x18001577e  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180015783  nop
0x180015784  lea     rcx, [rsp+118h+var_B8]; this
0x180015789  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001578e  nop
0x18001578f  jmp     short $+2
0x180015791  mov     rcx, [rsp+118h+var_48]
0x180015799  xor     rcx, rsp; StackCookie
0x18001579c  call    __security_check_cookie
0x1800157a1  add     rsp, 0E0h
0x1800157a8  pop     r15
0x1800157aa  pop     r14
0x1800157ac  pop     r13
0x1800157ae  pop     r12
0x1800157b0  pop     rdi
0x1800157b1  pop     rsi
0x1800157b2  pop     rbx
0x1800157b3  retn
```
