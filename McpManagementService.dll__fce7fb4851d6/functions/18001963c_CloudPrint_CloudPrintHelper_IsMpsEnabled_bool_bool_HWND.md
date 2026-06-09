# CloudPrint::CloudPrintHelper::IsMpsEnabled(bool,bool,HWND__ *)

- ea: `0x18001963c`
- end: `0x1800199c2`
- name: `?IsMpsEnabled@CloudPrintHelper@CloudPrint@@IEAAJ_N0PEAUHWND__@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper *this, char, char, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18001892c`

## callees

- `0x180003a60`
- `0x1800067a4`
- `0x180006b70`
- `0x18000e208`
- `0x18000e5e8`
- `0x180011de0`
- `0x180012bfc`
- `0x180013948`
- `0x180014de4`
- `0x1800154fc`
- `0x1800157bc`
- `0x18001963c`
- `0x18001ac7c`
- `0x18001bc2c`
- `0x18001c0a8`

## string_xrefs

- `0x180019705`: `Using cached state. State: %s`
- `0x180019722`: `Using cached state. State: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall CloudPrint::CloudPrintHelper::IsMpsEnabled(
        CloudPrint::CloudPrintHelper *this,
        char a2,
        char a3,
        __int64 a4)
{
  const wchar_t *v8; // rbx
  const wchar_t *v9; // r8
  char v10; // si
  int MpsDiscoveryEndpointFromGraph; // ebx
  int v12; // edx
  char v14[4]; // [rsp+60h] [rbp-118h] BYREF
  _BYTE v15[32]; // [rsp+68h] [rbp-110h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp-F0h] BYREF
  _BYTE v17[32]; // [rsp+A8h] [rbp-D0h] BYREF
  _BYTE v18[32]; // [rsp+C8h] [rbp-B0h] BYREF
  _BYTE v19[32]; // [rsp+E8h] [rbp-90h] BYREF
  _BYTE v20[32]; // [rsp+108h] [rbp-70h] BYREF
  _BYTE v21[32]; // [rsp+128h] [rbp-50h] BYREF

  v14[0] = 0;
  std::wstring::wstring(v15);
  std::wstring::wstring(v17);
  std::wstring::wstring(v16);
  CloudPrint::CloudPrintHelper::GetMpsConfig((__int64)this, (__int64)v15, (__int64)v17, (__int64)v16);
  if ( (int)CloudPrint::CloudPrintHelper::GetMpsCachedState(
              (__int64)this,
              (__int64)v15,
              (__int64)v17,
              (__int64)v16,
              v14) < 0 )
  {
    CloudPrint::CloudPrintHelper::UpdateMpsCachedState((__int64)this, 1, (__int64)v15, (__int64)v17, (__int64)v16);
    std::wstring::wstring(v18, L"dae89220-69ba-4957-a77a-47b78695e883");
    MpsDiscoveryEndpointFromGraph = CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph(
                                      this,
                                      (__int64)v16,
                                      a2,
                                      a3,
                                      a4);
    std::wstring::_Tidy_deallocate(v18);
    if ( MpsDiscoveryEndpointFromGraph < 0 )
    {
      v12 = 2;
    }
    else
    {
      if ( !MpsDiscoveryEndpointFromGraph )
      {
        v10 = 1;
        v12 = 4;
        goto LABEL_13;
      }
      v12 = 3;
    }
    v10 = v14[0];
LABEL_13:
    CloudPrint::CloudPrintHelper::UpdateMpsCachedState((__int64)this, v12, (__int64)v15, (__int64)v17, (__int64)v16);
    if ( MpsDiscoveryEndpointFromGraph < 0 )
      goto LABEL_19;
    goto LABEL_14;
  }
  v8 = L"Enabled";
  v9 = L"Enabled";
  v10 = v14[0];
  if ( !v14[0] )
    v9 = L"Disabled";
  CloudPrintHelperTelemetry::WriteDbgTraceInfo(
    "CloudPrint::CloudPrintHelper::IsMpsEnabled",
    L"Using cached state. State: %s",
    v9);
  if ( !v10 )
    v8 = L"Disabled";
  PrintCore::McpEvtSrc::ReportInfoEvent(L"Using cached state. State: %s", v8);
LABEL_14:
  if ( v10 )
  {
    std::wstring::wstring(v21);
    std::wstring::wstring(v18);
    std::wstring::wstring(v20, L"dae89220-69ba-4957-a77a-47b78695e883");
    std::wstring::wstring(v19, L"da9b70f6-5323-4ce6-ae5c-88dcc5082966");
    MpsDiscoveryEndpointFromGraph = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternal(
                                      (_DWORD)this,
                                      (unsigned int)v19,
                                      (unsigned int)v20,
                                      (unsigned int)v15,
                                      a2,
                                      a3,
                                      a4,
                                      (__int64)v21);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v20);
    if ( MpsDiscoveryEndpointFromGraph >= 0 )
    {
      *((_BYTE *)this + 9) = 1;
      *((_DWORD *)this + 3) = 1;
      std::wstring::operator=((char *)this + 144, v15);
      std::_WChar_traits<unsigned short>::length(L"dae89220-69ba-4957-a77a-47b78695e883");
      std::wstring::_Assign<unsigned short>((char *)this + 176, L"dae89220-69ba-4957-a77a-47b78695e883");
      std::wstring::operator=((char *)this + 208, v18);
      std::_WChar_traits<unsigned short>::length(L"da9b70f6-5323-4ce6-ae5c-88dcc5082966");
      std::wstring::_Assign<unsigned short>((char *)this + 240, L"da9b70f6-5323-4ce6-ae5c-88dcc5082966");
      std::_WChar_traits<unsigned short>::length(L"da9b70f6-5323-4ce6-ae5c-88dcc5082966");
      std::wstring::_Assign<unsigned short>((char *)this + 272, L"da9b70f6-5323-4ce6-ae5c-88dcc5082966");
    }
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v21);
  }
  else
  {
    MpsDiscoveryEndpointFromGraph = 1;
  }
LABEL_19:
  std::wstring::_Tidy_deallocate(v16);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v15);
  return (unsigned int)MpsDiscoveryEndpointFromGraph;
}

```

## disassembly

```asm
0x18001963c  mov     [rsp+arg_8], rbx
0x180019641  mov     [rsp+arg_10], rsi
0x180019646  push    rdi
0x180019647  push    r12
0x180019649  push    r13
0x18001964b  push    r14
0x18001964d  push    r15
0x18001964f  sub     rsp, 150h
0x180019656  mov     rax, cs:__security_cookie
0x18001965d  xor     rax, rsp
0x180019660  mov     [rsp+178h+var_30], rax
0x180019668  mov     r12, r9
0x18001966b  mov     r14b, r8b
0x18001966e  mov     r15b, dl
0x180019671  mov     rdi, rcx
0x180019674  mov     [rsp+178h+var_118], 0
0x180019679  lea     rcx, [rsp+178h+var_110]
0x18001967e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019683  nop
0x180019684  lea     rcx, [rsp+178h+var_D0]
0x18001968c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019691  nop
0x180019692  lea     rcx, [rsp+178h+var_F0]
0x18001969a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001969f  nop
0x1800196a0  lea     r9, [rsp+178h+var_F0]
0x1800196a8  lea     r8, [rsp+178h+var_D0]
0x1800196b0  lea     rdx, [rsp+178h+var_110]
0x1800196b5  mov     rcx, rdi
0x1800196b8  call    ?GetMpsConfig@CloudPrintHelper@CloudPrint@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; CloudPrint::CloudPrintHelper::GetMpsConfig(std::wstring *,std::wstring *,std::wstring *)
0x1800196bd  lea     rax, [rsp+178h+var_118]
0x1800196c2  mov     [rsp+178h+var_158], rax
0x1800196c7  lea     r9, [rsp+178h+var_F0]
0x1800196cf  lea     r8, [rsp+178h+var_D0]
0x1800196d7  lea     rdx, [rsp+178h+var_110]
0x1800196dc  mov     rcx, rdi
0x1800196df  call    ?GetMpsCachedState@CloudPrintHelper@CloudPrint@@IEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEA_N@Z; CloudPrint::CloudPrintHelper::GetMpsCachedState(std::wstring &,std::wstring &,std::wstring &,bool *)
0x1800196e4  test    eax, eax
0x1800196e6  js      short loc_180019733
0x1800196e8  lea     rbx, aEnabled; "Enabled"
0x1800196ef  mov     r8, rbx
0x1800196f2  lea     r13, aDisabled; "Disabled"
0x1800196f9  mov     sil, [rsp+178h+var_118]
0x1800196fe  test    sil, sil
0x180019701  cmovz   r8, r13
0x180019705  lea     rdx, aUsingCachedSta; "Using cached state. State: %s"
0x18001970c  lea     rcx, aCloudprintClou_11; "CloudPrint::CloudPrintHelper::IsMpsEnab"...
0x180019713  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019718  test    sil, sil
0x18001971b  cmovz   rbx, r13
0x18001971f  mov     rdx, rbx
0x180019722  lea     rcx, aUsingCachedSta; "Using cached state. State: %s"
0x180019729  call    ?ReportInfoEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportInfoEvent(ushort const *,...)
0x18001972e  jmp     loc_180019801
0x180019733  lea     rax, [rsp+178h+var_F0]
0x18001973b  mov     [rsp+178h+var_158], rax
0x180019740  lea     r9, [rsp+178h+var_D0]
0x180019748  lea     r8, [rsp+178h+var_110]
0x18001974d  mov     edx, 1
0x180019752  mov     rcx, rdi
0x180019755  call    ?UpdateMpsCachedState@CloudPrintHelper@CloudPrint@@IEAAXW4MpsCacheState@2@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; CloudPrint::CloudPrintHelper::UpdateMpsCachedState(CloudPrint::MpsCacheState,std::wstring &,std::wstring &,std::wstring &)
0x18001975a  lea     rdx, aDae8922069ba49; "dae89220-69ba-4957-a77a-47b78695e883"
0x180019761  lea     rcx, [rsp+178h+var_B0]
0x180019769  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001976e  mov     [rsp+178h+var_140], r12
0x180019773  mov     byte ptr [rsp+178h+var_148], r14b
0x180019778  mov     [rsp+178h+var_150], r15b
0x18001977d  lea     rax, [rsp+178h+var_F0]
0x180019785  mov     [rsp+178h+var_158], rax
0x18001978a  lea     r9, [rsp+178h+var_110]
0x18001978f  lea     r8, [rsp+178h+var_B0]
0x180019797  lea     rdx, [rsp+178h+var_D0]
0x18001979f  mov     rcx, rdi
0x1800197a2  call    ?GetMpsDiscoveryEndpointFromGraph@CloudPrintHelper@CloudPrint@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@1_N2PEAUHWND__@@@Z; CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph(std::wstring const &,std::wstring const &,std::wstring &,std::wstring &,bool,bool,HWND__ *)
0x1800197a7  mov     ebx, eax
0x1800197a9  lea     rcx, [rsp+178h+var_B0]
0x1800197b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800197b6  test    ebx, ebx
0x1800197b8  js      short loc_1800197CD
0x1800197ba  jnz     short loc_1800197C6
0x1800197bc  mov     sil, 1
0x1800197bf  mov     edx, 4
0x1800197c4  jmp     short loc_1800197D7
0x1800197c6  mov     edx, 3
0x1800197cb  jmp     short loc_1800197D2
0x1800197cd  mov     edx, 2
0x1800197d2  mov     sil, [rsp+178h+var_118]
0x1800197d7  lea     rax, [rsp+178h+var_F0]
0x1800197df  mov     [rsp+178h+var_158], rax
0x1800197e4  lea     r9, [rsp+178h+var_D0]
0x1800197ec  lea     r8, [rsp+178h+var_110]
0x1800197f1  mov     rcx, rdi
0x1800197f4  call    ?UpdateMpsCachedState@CloudPrintHelper@CloudPrint@@IEAAXW4MpsCacheState@2@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; CloudPrint::CloudPrintHelper::UpdateMpsCachedState(CloudPrint::MpsCacheState,std::wstring &,std::wstring &,std::wstring &)
0x1800197f9  test    ebx, ebx
0x1800197fb  js      loc_180019966
0x180019801  test    sil, sil
0x180019804  jz      loc_180019961
0x18001980a  lea     rcx, [rsp+178h+var_50]
0x180019812  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019817  nop
0x180019818  lea     rcx, [rsp+178h+var_B0]
0x180019820  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019825  nop
0x180019826  lea     rdx, aDae8922069ba49; "dae89220-69ba-4957-a77a-47b78695e883"
0x18001982d  lea     rcx, [rsp+178h+var_70]
0x180019835  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001983a  nop
0x18001983b  lea     rsi, aDa9b70f653234c; "da9b70f6-5323-4ce6-ae5c-88dcc5082966"
0x180019842  mov     rdx, rsi
0x180019845  lea     rcx, [rsp+178h+var_90]
0x18001984d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019852  lea     rax, [rsp+178h+var_B0]
0x18001985a  mov     [rsp+178h+var_128], rax
0x18001985f  lea     rax, [rsp+178h+var_50]
0x180019867  mov     [rsp+178h+var_140], rax
0x18001986c  mov     [rsp+178h+var_148], r12
0x180019871  mov     [rsp+178h+var_150], r14b
0x180019876  mov     byte ptr [rsp+178h+var_158], r15b
0x18001987b  lea     r9, [rsp+178h+var_110]
0x180019880  lea     r8, [rsp+178h+var_70]
0x180019888  lea     rdx, [rsp+178h+var_90]
0x180019890  mov     rcx, rdi
0x180019893  call    ?GetAuthorizationHeaderInternal@CloudPrintHelper@CloudPrint@@IEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@_N2PEAUHWND__@@PEAV34@444@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternal(std::wstring const &,std::wstring const &,std::wstring &,bool,bool,HWND__ *,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x180019898  mov     ebx, eax
0x18001989a  lea     rcx, [rsp+178h+var_90]
0x1800198a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198a7  nop
0x1800198a8  lea     rcx, [rsp+178h+var_70]
0x1800198b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198b5  test    ebx, ebx
0x1800198b7  js      loc_180019944
0x1800198bd  mov     byte ptr [rdi+9], 1
0x1800198c1  mov     dword ptr [rdi+0Ch], 1
0x1800198c8  lea     rcx, [rdi+90h]
0x1800198cf  lea     rdx, [rsp+178h+var_110]
0x1800198d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800198d9  lea     rcx, aDae8922069ba49; "dae89220-69ba-4957-a77a-47b78695e883"
0x1800198e0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800198e5  mov     r8, rax
0x1800198e8  lea     rcx, [rdi+0B0h]
0x1800198ef  lea     rdx, aDae8922069ba49; "dae89220-69ba-4957-a77a-47b78695e883"
0x1800198f6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800198fb  lea     rcx, [rdi+0D0h]
0x180019902  lea     rdx, [rsp+178h+var_B0]
0x18001990a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001990f  mov     rcx, rsi
0x180019912  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019917  mov     r8, rax
0x18001991a  lea     rcx, [rdi+0F0h]
0x180019921  mov     rdx, rsi
0x180019924  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019929  mov     rcx, rsi
0x18001992c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180019931  mov     r8, rax
0x180019934  lea     rcx, [rdi+110h]
0x18001993b  mov     rdx, rsi
0x18001993e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180019943  nop
0x180019944  lea     rcx, [rsp+178h+var_B0]
0x18001994c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019951  nop
0x180019952  lea     rcx, [rsp+178h+var_50]
0x18001995a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001995f  jmp     short loc_180019966
0x180019961  mov     ebx, 1
0x180019966  lea     rcx, [rsp+178h+var_F0]
0x18001996e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019973  nop
0x180019974  lea     rcx, [rsp+178h+var_D0]
0x18001997c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019981  nop
0x180019982  lea     rcx, [rsp+178h+var_110]
0x180019987  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001998c  mov     eax, ebx
0x18001998e  jmp     short loc_180019994
0x180019990  mov     eax, [rsp+178h+var_114]
0x180019994  mov     rcx, [rsp+178h+var_30]
0x18001999c  xor     rcx, rsp; StackCookie
0x18001999f  call    __security_check_cookie
0x1800199a4  lea     r11, [rsp+178h+var_28]
0x1800199ac  mov     rbx, [r11+38h]
0x1800199b0  mov     rsi, [r11+40h]
0x1800199b4  mov     rsp, r11
0x1800199b7  pop     r15
0x1800199b9  pop     r14
0x1800199bb  pop     r13
0x1800199bd  pop     r12
0x1800199bf  pop     rdi
0x1800199c0  retn
```
