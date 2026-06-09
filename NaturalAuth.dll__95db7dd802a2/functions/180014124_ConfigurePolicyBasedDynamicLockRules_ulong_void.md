# ConfigurePolicyBasedDynamicLockRules(ulong,void *)

- ea: `0x180014124`
- end: `0x1800144a8`
- name: `?ConfigurePolicyBasedDynamicLockRules@@YAJKPEAX@Z`
- size: `900`
- prototype: `__int64 __fastcall(unsigned int, PSID Sid)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800153e8`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000a7f8`
- `0x18000ac6c`
- `0x18000bbe8`
- `0x18000c9e0`
- `0x18000e9d4`
- `0x18000edf0`
- `0x180010690`
- `0x180011a04`
- `0x180011ea8`
- `0x180011ec0`
- `0x180012850`
- `0x180014124`
- `0x1800146f4`
- `0x180015268`
- `0x1800152e4`
- `0x1800160d4`
- `0x18001a9e8`
- `0x18001c3f0`
- `0x1800219a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800141e9`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x1800141af`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x1800141af`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ConfigurePolicyBasedDynamicLockRules(unsigned int a1, PSID Sid)
{
  signed int LastError; // eax
  int v5; // ebx
  bool v6; // sf
  __int64 CorrelationVector; // rbx
  __int64 v9; // rax
  unsigned int DynamicLockPluginsPolicy; // eax
  PVOID *v11; // r10
  int v12; // r14d
  __int64 i; // rdi
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // r10
  const char *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  LPSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  char v29[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v30; // [rsp+60h] [rbp-A0h]
  __int64 *v31; // [rsp+68h] [rbp-98h]
  char v32[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v35; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v36[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v37[1040]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v37, 0, 0x408u);
  v25 = -1;
  StringSid = 0;
  v33 = 0;
  std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<GenericPlugin::Signal>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>>,0>>::_Alloc_sentinel_and_proxy(&v33);
  std::vector<_bstr_t>::vector<_bstr_t>(&v27);
  std::vector<_bstr_t>::vector<_bstr_t>(v29);
  if ( !ConvertSidToStringSidA(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError <= 0 )
      goto LABEL_5;
    v5 = (unsigned __int16)LastError;
    goto LABEL_4;
  }
  v35 = v34;
  CorrelationVector = NaturalAuthTraceLogging::GetCorrelationVector(v34);
  v9 = std::string::string(v36, StringSid);
  DynamicLockPluginsPolicy = NaturalAuthHelper::_anonymous_namespace_::GetDynamicLockPluginsPolicy(
                               v9,
                               CorrelationVector,
                               a1,
                               &v27);
  v5 = DynamicLockPluginsPolicy;
  if ( DynamicLockPluginsPolicy )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids,
        DynamicLockPluginsPolicy);
    v6 = v5 < 0;
    if ( v5 <= 0 )
      goto LABEL_6;
    v5 = (unsigned __int16)v5;
LABEL_4:
    v5 |= 0x80070000;
    goto LABEL_5;
  }
  v5 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids,
      (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 5);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = 0;
  v14 = *((_QWORD *)&v27 + 1);
  for ( i = v27; i != v14; i += 32 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    {
      v15 = std::_String_val<std::_Simple_types<char>>::_Myptr(i);
      WPP_SF_ds(*(_QWORD *)(v16 + 16), 20, (unsigned int)&WPP_a55972c0645036c47bb3e826c72e1456_Traceguids, v12, v15);
    }
    v17 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(i);
    v18 = NAPRuleRegister(v17, &stru_18005F488, a1, (struct NA_XML_PARSE_ERROR_DETAILS *)v37, &v25, 0);
    if ( v18 >= 0 )
    {
      v20 = *(_QWORD *)std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(v19, v32, &v25);
      *(_BYTE *)(v20 + 40) = 0;
      v21 = *(_QWORD *)std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(v20, &v35, &v25);
      *(_BYTE *)(v21 + 41) = 0;
      v22 = *(_QWORD *)std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(v21, v36, &v25);
      *(_BYTE *)(v22 + 42) = 0;
      *(_DWORD *)(*(_QWORD *)std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(v22, v34, &v25) + 44LL) = 0;
      if ( v30 == v31 )
        std::vector<__int64>::_Emplace_reallocate<__int64 const &>(v29, v30, &v25);
      else
        *v30++ = v25;
      goto LABEL_33;
    }
    v5 = v18;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids,
        (unsigned int)v18);
LABEL_33:
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    ++v12;
  }
  if ( qword_18005F868 )
  {
    v5 = 0;
    v23 = std::vector<__int64>::vector<__int64>(v34, v29);
    LOBYTE(v24) = 1;
    LogUserPresenceMonitoringStarted(v24, v23);
    goto LABEL_8;
  }
LABEL_5:
  v6 = v5 < 0;
LABEL_6:
  if ( v6 )
    LogUserPresenceMonitoringFailedToStart(1, v5);
LABEL_8:
  if ( StringSid )
    LocalFree(StringSid);
  std::vector<void *>::_Tidy(v29);
  if ( (_QWORD)v27 )
  {
    std::_Destroy_range<std::allocator<std::string>>(v27, *((_QWORD *)&v27 + 1));
    std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFE0uLL);
    v27 = 0;
    v28 = 0;
  }
  std::_Tree<std::_Tmap_traits<__int64,DynamicLockRuleData,std::less<__int64>,std::allocator<std::pair<__int64 const,DynamicLockRuleData>>,0>>::~_Tree<std::_Tmap_traits<__int64,DynamicLockRuleData,std::less<__int64>,std::allocator<std::pair<__int64 const,DynamicLockRuleData>>,0>>(&v33);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014124  mov     [rsp-8+arg_10], rbx
0x180014129  mov     [rsp-8+arg_18], rsi
0x18001412e  push    rbp
0x18001412f  push    rdi
0x180014130  push    r12
0x180014132  push    r14
0x180014134  push    r15
0x180014136  lea     rbp, [rsp-400h]
0x18001413e  sub     rsp, 500h
0x180014145  mov     rax, cs:__security_cookie
0x18001414c  xor     rax, rsp
0x18001414f  mov     [rbp+420h+var_30], rax
0x180014156  mov     rbx, rdx
0x180014159  mov     r12d, ecx
0x18001415c  xor     edx, edx; Val
0x18001415e  mov     r8d, 408h; Size
0x180014164  lea     rcx, [rbp+420h+var_440]; void *
0x180014168  call    memset_0
0x18001416d  mov     [rsp+520h+var_4F0], 0FFFFFFFFFFFFFFFFh
0x180014176  mov     [rsp+520h+StringSid], 0
0x18001417f  xorps   xmm0, xmm0
0x180014182  movdqu  [rbp+420h+var_4A0], xmm0
0x180014187  lea     rcx, [rbp+420h+var_4A0]
0x18001418b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<GenericPlugin::Signal>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180014190  nop
0x180014191  lea     rcx, [rsp+520h+var_4E0]
0x180014196  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18001419b  nop
0x18001419c  lea     rcx, [rsp+520h+var_4C8]
0x1800141a1  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x1800141a6  nop
0x1800141a7  lea     rdx, [rsp+520h+StringSid]; StringSid
0x1800141ac  mov     rcx, rbx; Sid
0x1800141af  call    cs:__imp_ConvertSidToStringSidA
0x1800141b5  test    eax, eax
0x1800141b7  jnz     loc_18001426D
0x1800141bd  call    cs:__imp_GetLastError
0x1800141c3  mov     ebx, eax
0x1800141c5  test    eax, eax
0x1800141c7  jle     short loc_1800141D2
0x1800141c9  movzx   ebx, ax
0x1800141cc  or      ebx, 80070000h
0x1800141d2  test    ebx, ebx
0x1800141d4  jns     short loc_1800141DF
0x1800141d6  mov     edx, ebx; int
0x1800141d8  mov     cl, 1; bool
0x1800141da  call    ?LogUserPresenceMonitoringFailedToStart@@YAX_NJ@Z; LogUserPresenceMonitoringFailedToStart(bool,long)
0x1800141df  mov     rcx, [rsp+520h+StringSid]; hMem
0x1800141e4  test    rcx, rcx
0x1800141e7  jz      short loc_1800141F0
0x1800141e9  call    cs:__imp_LocalFree
0x1800141ef  nop
0x1800141f0  lea     rcx, [rsp+520h+var_4C8]
0x1800141f5  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800141fa  nop
0x1800141fb  mov     rcx, qword ptr [rsp+520h+var_4E0]
0x180014200  test    rcx, rcx
0x180014203  jz      short loc_180014237
0x180014205  mov     rdx, qword ptr [rsp+520h+var_4E0+8]
0x18001420a  call    ??$_Destroy_range@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::string>>(std::string *,std::string * const,std::allocator<std::string> &)
0x18001420f  mov     rcx, qword ptr [rsp+520h+var_4E0]
0x180014214  mov     rdx, [rsp+520h+var_4D0]
0x180014219  sub     rdx, rcx
0x18001421c  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180014220  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014225  xorps   xmm0, xmm0
0x180014228  movdqu  [rsp+520h+var_4E0], xmm0
0x18001422e  mov     [rsp+520h+var_4D0], 0
0x180014237  lea     rcx, [rbp+420h+var_4A0]
0x18001423b  call    ??1?$_Tree@V?$_Tmap_traits@_JUDynamicLockRuleData@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,DynamicLockRuleData,std::less<__int64>,std::allocator<std::pair<__int64 const,DynamicLockRuleData>>,0>>::~_Tree<std::_Tmap_traits<__int64,DynamicLockRuleData,std::less<__int64>,std::allocator<std::pair<__int64 const,DynamicLockRuleData>>,0>>(void)
0x180014240  mov     eax, ebx
0x180014242  mov     rcx, [rbp+420h+var_30]
0x180014249  xor     rcx, rsp; StackCookie
0x18001424c  call    __security_check_cookie
0x180014251  lea     r11, [rsp+520h+var_20]
0x180014259  mov     rbx, [r11+40h]
0x18001425d  mov     rsi, [r11+48h]
0x180014261  mov     rsp, r11
0x180014264  pop     r15
0x180014266  pop     r14
0x180014268  pop     r12
0x18001426a  pop     rdi
0x18001426b  pop     rbp
0x18001426c  retn
0x18001426d  lea     rax, [rbp+420h+var_490]
0x180014271  mov     [rbp+420h+var_470], rax
0x180014275  lea     rcx, [rbp+420h+var_490]
0x180014279  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x18001427e  mov     rbx, rax
0x180014281  mov     rdx, [rsp+520h+StringSid]
0x180014286  lea     rcx, [rbp+420h+var_460]
0x18001428a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001428f  nop
0x180014290  lea     r9, [rsp+520h+var_4E0]
0x180014295  mov     r8d, r12d
0x180014298  mov     rdx, rbx
0x18001429b  mov     rcx, rax
0x18001429e  call    NaturalAuthHelper___anonymous_namespace___GetDynamicLockPluginsPolicy
0x1800142a3  mov     ebx, eax
0x1800142a5  test    eax, eax
0x1800142a7  jz      short loc_1800142EA
0x1800142a9  lea     rsi, WPP_GLOBAL_Control
0x1800142b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142b7  cmp     rcx, rsi
0x1800142ba  jz      short loc_1800142DA
0x1800142bc  test    byte ptr [rcx+1Ch], 1
0x1800142c0  jz      short loc_1800142DA
0x1800142c2  mov     edx, 12h
0x1800142c7  mov     r9d, eax
0x1800142ca  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x1800142d1  mov     rcx, [rcx+10h]
0x1800142d5  call    WPP_SF_d
0x1800142da  test    ebx, ebx
0x1800142dc  jle     loc_1800141D4
0x1800142e2  movzx   ebx, bx
0x1800142e5  jmp     loc_1800141CC
0x1800142ea  xor     ebx, ebx
0x1800142ec  lea     rsi, WPP_GLOBAL_Control
0x1800142f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800142fa  cmp     r10, rsi
0x1800142fd  jz      short loc_18001432E
0x1800142ff  test    byte ptr [r10+1Ch], 4
0x180014304  jz      short loc_18001432E
0x180014306  mov     r9, qword ptr [rsp+520h+var_4E0+8]
0x18001430b  sub     r9, qword ptr [rsp+520h+var_4E0]
0x180014310  sar     r9, 5
0x180014314  lea     edx, [rbx+13h]
0x180014317  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x18001431e  mov     rcx, [r10+10h]
0x180014322  call    WPP_SF_d
0x180014327  mov     r10, cs:WPP_GLOBAL_Control
0x18001432e  xor     r14d, r14d
0x180014331  mov     rdi, qword ptr [rsp+520h+var_4E0]
0x180014336  mov     r15, qword ptr [rsp+520h+var_4E0+8]
0x18001433b  jmp     loc_180014471
0x180014340  cmp     r10, rsi
0x180014343  jz      short loc_180014371
0x180014345  test    byte ptr [r10+1Ch], 4
0x18001434a  jz      short loc_180014371
0x18001434c  mov     rcx, rdi
0x18001434f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180014354  mov     edx, 14h
0x180014359  mov     [rsp+520h+var_500], rax
0x18001435e  mov     r9d, r14d
0x180014361  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x180014368  mov     rcx, [r10+10h]
0x18001436c  call    WPP_SF_ds
0x180014371  mov     rcx, rdi
0x180014374  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180014379  mov     [rsp+520h+var_4F8], 0; enum NA_SIGNAL_TYPE_INFO *
0x180014382  lea     rcx, [rsp+520h+var_4F0]
0x180014387  mov     [rsp+520h+var_500], rcx; __int64 *
0x18001438c  lea     r9, [rbp+420h+var_440]; struct NA_XML_PARSE_ERROR_DETAILS *
0x180014390  mov     r8d, r12d; unsigned int
0x180014393  lea     rdx, stru_18005F488; struct _WNF_STATE_NAME *
0x18001439a  mov     rcx, rax; char *
0x18001439d  call    ?NAPRuleRegister@@YAJPEBDPEAU_WNF_STATE_NAME@@KPEAUNA_XML_PARSE_ERROR_DETAILS@@PEA_JPEAW4NA_SIGNAL_TYPE_INFO@@@Z; NAPRuleRegister(char const *,_WNF_STATE_NAME *,ulong,NA_XML_PARSE_ERROR_DETAILS *,__int64 *,NA_SIGNAL_TYPE_INFO *)
0x1800143a2  test    eax, eax
0x1800143a4  jns     short loc_1800143E0
0x1800143a6  mov     ebx, eax
0x1800143a8  mov     r10, cs:WPP_GLOBAL_Control
0x1800143af  cmp     r10, rsi
0x1800143b2  jz      loc_18001446A
0x1800143b8  test    byte ptr [r10+1Ch], 1
0x1800143bd  jz      loc_18001446A
0x1800143c3  mov     edx, 15h
0x1800143c8  mov     r9d, eax
0x1800143cb  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x1800143d2  mov     rcx, [r10+10h]
0x1800143d6  call    WPP_SF_d
0x1800143db  jmp     loc_180014463
0x1800143e0  lea     r8, [rsp+520h+var_4F0]
0x1800143e5  lea     rdx, [rsp+520h+var_4B0]
0x1800143ea  call    ??$_Try_emplace@AEB_J$$V@?$map@_JUDynamicLockRuleData@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(__int64 const &)
0x1800143ef  mov     rcx, [rax]
0x1800143f2  mov     byte ptr [rcx+28h], 0
0x1800143f6  lea     r8, [rsp+520h+var_4F0]
0x1800143fb  lea     rdx, [rbp+420h+var_470]
0x1800143ff  call    ??$_Try_emplace@AEB_J$$V@?$map@_JUDynamicLockRuleData@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(__int64 const &)
0x180014404  mov     rcx, [rax]
0x180014407  mov     byte ptr [rcx+29h], 0
0x18001440b  lea     r8, [rsp+520h+var_4F0]
0x180014410  lea     rdx, [rbp+420h+var_460]
0x180014414  call    ??$_Try_emplace@AEB_J$$V@?$map@_JUDynamicLockRuleData@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(__int64 const &)
0x180014419  mov     rcx, [rax]
0x18001441c  mov     byte ptr [rcx+2Ah], 0
0x180014420  lea     r8, [rsp+520h+var_4F0]
0x180014425  lea     rdx, [rbp+420h+var_490]
0x180014429  call    ??$_Try_emplace@AEB_J$$V@?$map@_JUDynamicLockRuleData@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JUDynamicLockRuleData@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,DynamicLockRuleData>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18001442e  mov     rcx, [rax]
0x180014431  mov     dword ptr [rcx+2Ch], 0
0x180014438  mov     rdx, [rsp+520h+var_4C0]
0x18001443d  cmp     rdx, [rsp+520h+var_4B8]
0x180014442  jz      short loc_180014454
0x180014444  mov     rax, [rsp+520h+var_4F0]
0x180014449  mov     [rdx], rax
0x18001444c  add     [rsp+520h+var_4C0], 8
0x180014452  jmp     short loc_180014463
0x180014454  lea     r8, [rsp+520h+var_4F0]
0x180014459  lea     rcx, [rsp+520h+var_4C8]
0x18001445e  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x180014463  mov     r10, cs:WPP_GLOBAL_Control
0x18001446a  inc     r14d
0x18001446d  add     rdi, 20h ; ' '
0x180014471  cmp     rdi, r15
0x180014474  jnz     loc_180014340
0x18001447a  cmp     cs:qword_18005F868, 0
0x180014482  jbe     loc_1800141D2
0x180014488  xor     ebx, ebx
0x18001448a  lea     rdx, [rsp+520h+var_4C8]
0x18001448f  lea     rcx, [rbp+420h+var_490]
0x180014493  call    ??0?$vector@_JV?$allocator@_J@std@@@std@@QEAA@AEBV01@@Z; std::vector<__int64>::vector<__int64>(std::vector<__int64> const &)
0x180014498  mov     rdx, rax
0x18001449b  mov     cl, 1
0x18001449d  call    ?LogUserPresenceMonitoringStarted@@YAX_NV?$vector@_JV?$allocator@_J@std@@@std@@@Z; LogUserPresenceMonitoringStarted(bool,std::vector<__int64>)
0x1800144a2  jmp     loc_1800141DF
```
