# CCellularSmsDevice::HandleNewMessage(ISmsMessage *,__int64)

- ea: `0x180045670`
- end: `0x180045cbf`
- name: `?HandleNewMessage@CCellularSmsDevice@@UEAAJPEAUISmsMessage@@_J@Z`
- size: `1615`
- prototype: `__int64 __fastcall(CCellularSmsDevice *__hidden this, struct ISmsMessage *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180006c84`
- `0x1800293cc`
- `0x18002aef8`
- `0x18002cd78`
- `0x18002e368`
- `0x18002f910`
- `0x18003056c`
- `0x180045670`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x180045824`: `Failed to create TextMessageXml`
- `0x1800458c1`: `Failed to create AppMessageXml`
- `0x180045a33`: `Failed to create StatusMessageXml`
- `0x18004597a`: `Failed to create WapMessageXml`
- `0x180045ba5`: `Failed to create BroadcastMessageXml`
- `0x180045aec`: `Failed to create VoicemailMessageXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CCellularSmsDevice::HandleNewMessage(CCellularSmsDevice *this, struct ISmsMessage *a2)
{
  __int64 v4; // rbx
  char *v5; // r14
  __int64 v6; // r8
  __int64 v7; // r8
  const wchar_t *v8; // r15
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rsi
  struct ISmsTextMessage *v12; // rcx
  unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r9
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  int TextMessageXml; // eax
  int v18; // esi
  struct ISmsAppMessage *v19; // rcx
  unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // rdx
  int AppMessageXml; // eax
  struct ISmsWapMessage *v25; // rcx
  unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // r9
  unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rdx
  int WapMessageXml; // eax
  struct ISmsStatusMessage *v31; // rcx
  unsigned __int16 *v32; // rax
  const unsigned __int16 *v33; // r9
  unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // rdx
  int StatusMessageXml; // eax
  struct ISmsVoicemailMessage *v37; // rcx
  const unsigned __int16 *v38; // rax
  const unsigned __int16 *v39; // r9
  const unsigned __int16 *v40; // r8
  const unsigned __int16 *v41; // rdx
  int VoicemailMessageXml; // eax
  struct ISmsBroadcastMessage *v43; // rcx
  unsigned __int16 *v44; // rax
  const unsigned __int16 *v45; // r9
  unsigned __int16 *v46; // r8
  const unsigned __int16 *v47; // rdx
  int BroadcastMessageXml; // eax
  struct ISmsStatusMessage *v50[2]; // [rsp+30h] [rbp-99h] BYREF
  struct IXMLDOMDocument *v51; // [rsp+40h] [rbp-89h] BYREF
  struct ISmsTextMessage *v52; // [rsp+48h] [rbp-81h] BYREF
  __int64 v53; // [rsp+50h] [rbp-79h]
  __int64 v54; // [rsp+58h] [rbp-71h]
  unsigned __int16 *v55[2]; // [rsp+60h] [rbp-69h] BYREF
  __m128i v56; // [rsp+70h] [rbp-59h]
  unsigned __int16 *v57[2]; // [rsp+80h] [rbp-49h] BYREF
  __m128i v58; // [rsp+90h] [rbp-39h]
  unsigned __int16 *v59[2]; // [rsp+A0h] [rbp-29h] BYREF
  __m128i v60; // [rsp+B0h] [rbp-19h]
  unsigned __int16 *v61[2]; // [rsp+C0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+D0h] [rbp+7h]

  v54 = 0;
  *(_OWORD *)v61 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v61[0]) = 0;
  *(_OWORD *)v59 = 0;
  v60 = si128;
  LOWORD(v59[0]) = 0;
  *(_OWORD *)v57 = 0;
  v58 = si128;
  LOWORD(v57[0]) = 0;
  *(_OWORD *)v55 = 0;
  v56 = si128;
  LOWORD(v55[0]) = 0;
  v4 = 0;
  v53 = 0;
  v50[0] = (struct ISmsStatusMessage *)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v5 = (char *)this + 104;
  v50[1] = (CCellularSmsDevice *)((char *)this + 104);
  (**((void (__fastcall ***)(char *))this + 13))((char *)this + 104);
  std::wstring::operator=((__int64)v59, (_QWORD *)this + 29, v6);
  std::wstring::operator=((__int64)v57, (_QWORD *)this + 33, v7);
  v8 = (const wchar_t *)((char *)this + 168);
  std::wstring::operator=((__int64)v61, (_QWORD *)this + 21, v9);
  v11 = *((_QWORD *)this + 124);
  if ( v11 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*((_QWORD *)this + 124));
    v4 = v11;
    v53 = v11;
  }
  std::wstring::operator=((__int64)v55, (_QWORD *)this + 37, v10);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
  v51 = 0;
  v12 = 0;
  v52 = 0;
  if ( a2 )
  {
    (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsTextMessage **))a2)(
      a2,
      &GUID_b70e6bba_a2d7_4d14_b9d6_86803615a141,
      &v52);
    v12 = v52;
  }
  if ( v12 )
  {
    v13 = (unsigned __int16 *)v55;
    if ( v56.m128i_i64[1] > 7uLL )
      v13 = v55[0];
    v14 = (const unsigned __int16 *)v57;
    if ( v58.m128i_i64[1] > 7uLL )
      v14 = v57[0];
    v15 = (const unsigned __int16 *)v59;
    if ( v60.m128i_i64[1] > 7uLL )
      v15 = v59[0];
    v16 = (const unsigned __int16 *)v61;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = v61[0];
    TextMessageXml = CSmsMessageXmlHelper::GetTextMessageXml(v12, v16, v15, v14, v13, &v51);
    if ( TextMessageXml >= 0 )
    {
      v18 = 1;
      goto LABEL_106;
    }
    LogSmsRouterError("CCellularSmsDevice::HandleNewMessage", 0x476u, TextMessageXml, "Failed to create TextMessageXml");
  }
  v18 = 0;
  v19 = 0;
  v50[0] = 0;
  if ( a2 )
  {
    (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsStatusMessage **))a2)(
      a2,
      &GUID_6241d6fb_6e70_48ec_a5e7_ee8d033bef3e,
      v50);
    v19 = v50[0];
  }
  if ( v19 )
  {
    v20 = (unsigned __int16 *)v55;
    if ( v56.m128i_i64[1] > 7uLL )
      v20 = v55[0];
    v21 = (const unsigned __int16 *)v57;
    if ( v58.m128i_i64[1] > 7uLL )
      v21 = v57[0];
    v22 = (const unsigned __int16 *)v59;
    if ( v60.m128i_i64[1] > 7uLL )
      v22 = v59[0];
    v23 = (const unsigned __int16 *)v61;
    if ( si128.m128i_i64[1] > 7uLL )
      v23 = v61[0];
    AppMessageXml = CSmsMessageXmlHelper::GetAppMessageXml(v19, v23, v22, v21, v20, &v51);
    if ( AppMessageXml < 0 )
      LogSmsRouterError("CCellularSmsDevice::HandleNewMessage", 0x487u, AppMessageXml, "Failed to create AppMessageXml");
    else
      v18 = 2;
    v19 = v50[0];
  }
  if ( v19 )
    (*(void (__fastcall **)(struct ISmsAppMessage *))(*(_QWORD *)v19 + 16LL))(v19);
  if ( !v18 )
  {
    v25 = 0;
    v50[0] = 0;
    if ( a2 )
    {
      (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsStatusMessage **))a2)(
        a2,
        &GUID_b0c1f204_f8fc_41c2_a4a5_c06e4f9398cc,
        v50);
      v25 = v50[0];
    }
    if ( v25 )
    {
      v26 = (unsigned __int16 *)v55;
      if ( v56.m128i_i64[1] > 7uLL )
        v26 = v55[0];
      v27 = (const unsigned __int16 *)v57;
      if ( v58.m128i_i64[1] > 7uLL )
        v27 = v57[0];
      v28 = (unsigned __int16 *)v59;
      if ( v60.m128i_i64[1] > 7uLL )
        v28 = v59[0];
      v29 = (const unsigned __int16 *)v61;
      if ( si128.m128i_i64[1] > 7uLL )
        v29 = v61[0];
      WapMessageXml = CSmsMessageXmlHelper::GetWapMessageXml(v25, v29, v28, v27, v26, &v51);
      if ( WapMessageXml < 0 )
        LogSmsRouterError(
          "CCellularSmsDevice::HandleNewMessage",
          0x499u,
          WapMessageXml,
          "Failed to create WapMessageXml");
      else
        v18 = 4;
      v25 = v50[0];
    }
    if ( v25 )
      (*(void (__fastcall **)(struct ISmsWapMessage *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( !v18 )
    {
      v31 = 0;
      v50[0] = 0;
      if ( a2 )
      {
        (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsStatusMessage **))a2)(
          a2,
          &GUID_db63de92_df17_4b59_8304_905a628451c6,
          v50);
        v31 = v50[0];
      }
      if ( v31 )
      {
        v32 = (unsigned __int16 *)v55;
        if ( v56.m128i_i64[1] > 7uLL )
          v32 = v55[0];
        v33 = (const unsigned __int16 *)v57;
        if ( v58.m128i_i64[1] > 7uLL )
          v33 = v57[0];
        v34 = (unsigned __int16 *)v59;
        if ( v60.m128i_i64[1] > 7uLL )
          v34 = v59[0];
        v35 = (const unsigned __int16 *)v61;
        if ( si128.m128i_i64[1] > 7uLL )
          v35 = v61[0];
        StatusMessageXml = CSmsMessageXmlHelper::GetStatusMessageXml(v31, v35, v34, v33, v32, &v51);
        if ( StatusMessageXml < 0 )
          LogSmsRouterError(
            "CCellularSmsDevice::HandleNewMessage",
            0x4ABu,
            StatusMessageXml,
            "Failed to create StatusMessageXml");
        else
          v18 = 5;
        v31 = v50[0];
      }
      if ( v31 )
        (*(void (__fastcall **)(struct ISmsStatusMessage *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( !v18 )
      {
        v37 = 0;
        v50[0] = 0;
        if ( a2 )
        {
          (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsStatusMessage **))a2)(
            a2,
            &GUID_588e24c6_8f80_42bc_ae61_4a834343bf0a,
            v50);
          v37 = v50[0];
        }
        if ( v37 )
        {
          v38 = (const unsigned __int16 *)v55;
          if ( v56.m128i_i64[1] > 7uLL )
            v38 = v55[0];
          v39 = (const unsigned __int16 *)v57;
          if ( v58.m128i_i64[1] > 7uLL )
            v39 = v57[0];
          v40 = (const unsigned __int16 *)v59;
          if ( v60.m128i_i64[1] > 7uLL )
            v40 = v59[0];
          v41 = (const unsigned __int16 *)v61;
          if ( si128.m128i_i64[1] > 7uLL )
            v41 = v61[0];
          VoicemailMessageXml = CSmsMessageXmlHelper::GetVoicemailMessageXml(v37, v41, v40, v39, v38, &v51);
          if ( VoicemailMessageXml < 0 )
            LogSmsRouterError(
              "CCellularSmsDevice::HandleNewMessage",
              0x4BDu,
              VoicemailMessageXml,
              "Failed to create VoicemailMessageXml");
          else
            v18 = 3;
          v37 = v50[0];
        }
        if ( v37 )
          (*(void (__fastcall **)(struct ISmsVoicemailMessage *))(*(_QWORD *)v37 + 16LL))(v37);
        if ( !v18 )
        {
          v43 = 0;
          v50[0] = 0;
          if ( a2 )
          {
            (**(void (__fastcall ***)(struct ISmsMessage *, GUID *, struct ISmsStatusMessage **))a2)(
              a2,
              &GUID_c60a7d3a_934c_4270_a37b_3453419cbbbb,
              v50);
            v43 = v50[0];
          }
          if ( v43 )
          {
            v44 = (unsigned __int16 *)v55;
            if ( v56.m128i_i64[1] > 7uLL )
              v44 = v55[0];
            v45 = (const unsigned __int16 *)v57;
            if ( v58.m128i_i64[1] > 7uLL )
              v45 = v57[0];
            v46 = (unsigned __int16 *)v59;
            if ( v60.m128i_i64[1] > 7uLL )
              v46 = v59[0];
            v47 = (const unsigned __int16 *)v61;
            if ( si128.m128i_i64[1] > 7uLL )
              v47 = v61[0];
            BroadcastMessageXml = CSmsMessageXmlHelper::GetBroadcastMessageXml(v43, v47, v46, v45, v44, &v51);
            if ( BroadcastMessageXml < 0 )
              LogSmsRouterError(
                "CCellularSmsDevice::HandleNewMessage",
                0x4CFu,
                BroadcastMessageXml,
                "Failed to create BroadcastMessageXml");
            else
              v18 = 6;
            v43 = v50[0];
          }
          if ( v43 )
            (*(void (__fastcall **)(struct ISmsBroadcastMessage *))(*(_QWORD *)v43 + 16LL))(v43);
        }
      }
    }
  }
LABEL_106:
  if ( *((_QWORD *)this + 24) > 7u )
    v8 = *(const wchar_t **)v8;
  LogSmsRouterInfo("CCellularSmsDevice::HandleNewMessage", 0x4D4u, "SmsDevice %S received message of type %d", v8, v18);
  if ( v18 && v4 )
    (*(void (__fastcall **)(__int64, struct IXMLDOMDocument *, _QWORD))(*(_QWORD *)v4 + 24LL))(
      v4,
      v51,
      *((unsigned int *)this + 250));
  (*(void (__fastcall **)(struct ISmsMessage *))(*(_QWORD *)a2 + 40LL))(a2);
  if ( v52 )
    (*(void (__fastcall **)(struct ISmsTextMessage *))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v51 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v51->lpVtbl->Release)(v51);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  std::wstring::~wstring((char **)v55);
  std::wstring::~wstring((char **)v57);
  std::wstring::~wstring((char **)v59);
  std::wstring::~wstring((char **)v61);
  return 0;
}

```

## disassembly

```asm
0x180045670  mov     [rsp-8+arg_10], rbx
0x180045675  push    rbp
0x180045676  push    rsi
0x180045677  push    rdi
0x180045678  push    r12
0x18004567a  push    r13
0x18004567c  push    r14
0x18004567e  push    r15
0x180045680  lea     rbp, [rsp-27h]
0x180045685  sub     rsp, 0F0h
0x18004568c  mov     rax, cs:__security_cookie
0x180045693  xor     rax, rsp
0x180045696  mov     [rbp+57h+var_40], rax
0x18004569a  mov     rdi, rdx
0x18004569d  mov     r13, rcx
0x1800456a0  mov     [rbp+57h+var_C8], 0
0x1800456a8  xorps   xmm0, xmm0
0x1800456ab  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800456af  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800456b7  movdqu  [rbp+57h+var_50], xmm1
0x1800456bc  xor     eax, eax
0x1800456be  mov     word ptr [rbp+57h+var_60], ax
0x1800456c2  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800456c6  movdqu  [rbp+57h+var_70], xmm1
0x1800456cb  mov     word ptr [rbp+57h+var_80], ax
0x1800456cf  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800456d3  movdqu  [rbp+57h+var_90], xmm1
0x1800456d8  mov     word ptr [rbp+57h+var_A0], ax
0x1800456dc  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800456e0  movdqu  [rbp+57h+var_B0], xmm1
0x1800456e5  mov     word ptr [rbp+57h+var_C0], ax
0x1800456e9  xor     ebx, ebx
0x1800456eb  mov     [rbp+57h+var_D0], rbx
0x1800456ef  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800456f6  mov     [rsp+120h+var_F0], rax
0x1800456fb  lea     r14, [rcx+68h]
0x1800456ff  mov     [rsp+120h+var_E8], r14
0x180045704  mov     rax, [r14]
0x180045707  mov     rcx, r14
0x18004570a  mov     rax, [rax]
0x18004570d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045712  nop
0x180045713  lea     rdx, [r13+0E8h]
0x18004571a  lea     rcx, [rbp+57h+var_80]
0x18004571e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180045723  lea     rdx, [r13+108h]
0x18004572a  lea     rcx, [rbp+57h+var_A0]
0x18004572e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180045733  lea     r15, [r13+0A8h]
0x18004573a  mov     rdx, r15
0x18004573d  lea     rcx, [rbp+57h+var_60]
0x180045741  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180045746  mov     rsi, [r13+3E0h]
0x18004574d  test    rsi, rsi
0x180045750  jz      short loc_180045768
0x180045752  mov     rax, [rsi]
0x180045755  mov     rcx, rsi
0x180045758  mov     rax, [rax+8]
0x18004575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045761  mov     rbx, rsi
0x180045764  mov     [rbp+57h+var_D0], rbx
0x180045768  lea     rdx, [r13+128h]
0x18004576f  lea     rcx, [rbp+57h+var_C0]
0x180045773  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180045778  nop
0x180045779  mov     rax, [r14]
0x18004577c  mov     rcx, r14
0x18004577f  mov     rax, [rax+8]
0x180045783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045788  nop
0x180045789  mov     [rsp+120h+var_E0], 0
0x180045792  xor     ecx, ecx
0x180045794  mov     [rsp+120h+var_D8], rcx
0x180045799  test    rdi, rdi
0x18004579c  jz      short loc_1800457BD
0x18004579e  mov     rax, [rdi]
0x1800457a1  lea     r8, [rsp+120h+var_D8]
0x1800457a6  lea     rdx, _GUID_b70e6bba_a2d7_4d14_b9d6_86803615a141
0x1800457ad  mov     rcx, rdi
0x1800457b0  mov     rax, [rax]
0x1800457b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457b8  mov     rcx, [rsp+120h+var_D8]; struct ISmsTextMessage *
0x1800457bd  lea     r12, aCcellularsmsde_7; "CCellularSmsDevice::HandleNewMessage"
0x1800457c4  mov     r14d, 7
0x1800457ca  test    rcx, rcx
0x1800457cd  jz      short loc_18004583C
0x1800457cf  lea     rax, [rbp+57h+var_C0]
0x1800457d3  cmp     qword ptr [rbp+57h+var_B0+8], r14
0x1800457d7  cmova   rax, [rbp+57h+var_C0]
0x1800457dc  lea     r9, [rbp+57h+var_A0]
0x1800457e0  cmp     qword ptr [rbp+57h+var_90+8], r14
0x1800457e4  cmova   r9, [rbp+57h+var_A0]; unsigned __int16 *
0x1800457e9  lea     r8, [rbp+57h+var_80]
0x1800457ed  cmp     qword ptr [rbp+57h+var_70+8], r14
0x1800457f1  cmova   r8, [rbp+57h+var_80]; unsigned __int16 *
0x1800457f6  lea     rdx, [rbp+57h+var_60]
0x1800457fa  cmp     qword ptr [rbp+57h+var_50+8], r14
0x1800457fe  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180045803  lea     r10, [rsp+120h+var_E0]
0x180045808  mov     [rsp+120h+var_F8], r10; struct IXMLDOMDocument **
0x18004580d  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180045812  call    ?GetTextMessageXml@CSmsMessageXmlHelper@@SAJPEAUISmsTextMessage@@PEBG111PEAPEAUIXMLDOMDocument@@@Z; CSmsMessageXmlHelper::GetTextMessageXml(ISmsTextMessage *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x180045817  test    eax, eax
0x180045819  js      short loc_180045824
0x18004581b  lea     esi, [r14-6]
0x18004581f  jmp     loc_180045BD3
0x180045824  lea     r9, aFailedToCreate_2; "Failed to create TextMessageXml"
0x18004582b  mov     r8d, eax; int
0x18004582e  mov     edx, 476h; unsigned int
0x180045833  mov     rcx, r12; char *
0x180045836  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004583b  nop
0x18004583c  xor     esi, esi
0x18004583e  xor     ecx, ecx
0x180045840  mov     [rsp+120h+var_F0], rcx
0x180045845  test    rdi, rdi
0x180045848  jz      short loc_180045869
0x18004584a  mov     rax, [rdi]
0x18004584d  lea     r8, [rsp+120h+var_F0]
0x180045852  lea     rdx, _GUID_6241d6fb_6e70_48ec_a5e7_ee8d033bef3e
0x180045859  mov     rcx, rdi
0x18004585c  mov     rax, [rax]
0x18004585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045864  mov     rcx, [rsp+120h+var_F0]; struct ISmsAppMessage *
0x180045869  test    rcx, rcx
0x18004586c  jz      short loc_1800458DD
0x18004586e  lea     rax, [rbp+57h+var_C0]
0x180045872  cmp     qword ptr [rbp+57h+var_B0+8], r14
0x180045876  cmova   rax, [rbp+57h+var_C0]
0x18004587b  lea     r9, [rbp+57h+var_A0]
0x18004587f  cmp     qword ptr [rbp+57h+var_90+8], r14
0x180045883  cmova   r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180045888  lea     r8, [rbp+57h+var_80]
0x18004588c  cmp     qword ptr [rbp+57h+var_70+8], r14
0x180045890  cmova   r8, [rbp+57h+var_80]; unsigned __int16 *
0x180045895  lea     rdx, [rbp+57h+var_60]
0x180045899  cmp     qword ptr [rbp+57h+var_50+8], r14
0x18004589d  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800458a2  lea     r10, [rsp+120h+var_E0]
0x1800458a7  mov     [rsp+120h+var_F8], r10; struct IXMLDOMDocument **
0x1800458ac  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1800458b1  call    ?GetAppMessageXml@CSmsMessageXmlHelper@@SAJPEAUISmsAppMessage@@PEBG111PEAPEAUIXMLDOMDocument@@@Z; CSmsMessageXmlHelper::GetAppMessageXml(ISmsAppMessage *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x1800458b6  test    eax, eax
0x1800458b8  js      short loc_1800458C1
0x1800458ba  mov     esi, 2
0x1800458bf  jmp     short loc_1800458D8
0x1800458c1  lea     r9, aFailedToCreate_13; "Failed to create AppMessageXml"
0x1800458c8  mov     r8d, eax; int
0x1800458cb  mov     edx, 487h; unsigned int
0x1800458d0  mov     rcx, r12; char *
0x1800458d3  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800458d8  mov     rcx, [rsp+120h+var_F0]
0x1800458dd  test    rcx, rcx
0x1800458e0  jz      short loc_1800458EF
0x1800458e2  mov     rax, [rcx]
0x1800458e5  mov     rax, [rax+10h]
0x1800458e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458ee  nop
0x1800458ef  test    esi, esi
0x1800458f1  jnz     loc_180045BD3
0x1800458f7  xor     ecx, ecx
0x1800458f9  mov     [rsp+120h+var_F0], rcx
0x1800458fe  test    rdi, rdi
0x180045901  jz      short loc_180045922
0x180045903  mov     rax, [rdi]
0x180045906  lea     r8, [rsp+120h+var_F0]
0x18004590b  lea     rdx, _GUID_b0c1f204_f8fc_41c2_a4a5_c06e4f9398cc
0x180045912  mov     rcx, rdi
0x180045915  mov     rax, [rax]
0x180045918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004591d  mov     rcx, [rsp+120h+var_F0]; struct ISmsWapMessage *
0x180045922  test    rcx, rcx
0x180045925  jz      short loc_180045996
0x180045927  lea     rax, [rbp+57h+var_C0]
0x18004592b  cmp     qword ptr [rbp+57h+var_B0+8], r14
0x18004592f  cmova   rax, [rbp+57h+var_C0]
0x180045934  lea     r9, [rbp+57h+var_A0]
0x180045938  cmp     qword ptr [rbp+57h+var_90+8], r14
0x18004593c  cmova   r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180045941  lea     r8, [rbp+57h+var_80]
0x180045945  cmp     qword ptr [rbp+57h+var_70+8], r14
0x180045949  cmova   r8, [rbp+57h+var_80]; unsigned __int16 *
0x18004594e  lea     rdx, [rbp+57h+var_60]
0x180045952  cmp     qword ptr [rbp+57h+var_50+8], r14
0x180045956  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x18004595b  lea     r10, [rsp+120h+var_E0]
0x180045960  mov     [rsp+120h+var_F8], r10; struct IXMLDOMDocument **
0x180045965  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x18004596a  call    ?GetWapMessageXml@CSmsMessageXmlHelper@@SAJPEAUISmsWapMessage@@PEBG111PEAPEAUIXMLDOMDocument@@@Z; CSmsMessageXmlHelper::GetWapMessageXml(ISmsWapMessage *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x18004596f  test    eax, eax
0x180045971  js      short loc_18004597A
0x180045973  mov     esi, 4
0x180045978  jmp     short loc_180045991
0x18004597a  lea     r9, aFailedToCreate_4; "Failed to create WapMessageXml"
0x180045981  mov     r8d, eax; int
0x180045984  mov     edx, 499h; unsigned int
0x180045989  mov     rcx, r12; char *
0x18004598c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180045991  mov     rcx, [rsp+120h+var_F0]
0x180045996  test    rcx, rcx
0x180045999  jz      short loc_1800459A8
0x18004599b  mov     rax, [rcx]
0x18004599e  mov     rax, [rax+10h]
0x1800459a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459a7  nop
0x1800459a8  test    esi, esi
0x1800459aa  jnz     loc_180045BD3
0x1800459b0  xor     ecx, ecx
0x1800459b2  mov     [rsp+120h+var_F0], rcx
0x1800459b7  test    rdi, rdi
0x1800459ba  jz      short loc_1800459DB
0x1800459bc  mov     rax, [rdi]
0x1800459bf  lea     r8, [rsp+120h+var_F0]
0x1800459c4  lea     rdx, _GUID_db63de92_df17_4b59_8304_905a628451c6
0x1800459cb  mov     rcx, rdi
0x1800459ce  mov     rax, [rax]
0x1800459d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459d6  mov     rcx, [rsp+120h+var_F0]; struct ISmsStatusMessage *
0x1800459db  test    rcx, rcx
0x1800459de  jz      short loc_180045A4F
0x1800459e0  lea     rax, [rbp+57h+var_C0]
0x1800459e4  cmp     qword ptr [rbp+57h+var_B0+8], r14
0x1800459e8  cmova   rax, [rbp+57h+var_C0]
0x1800459ed  lea     r9, [rbp+57h+var_A0]
0x1800459f1  cmp     qword ptr [rbp+57h+var_90+8], r14
0x1800459f5  cmova   r9, [rbp+57h+var_A0]; unsigned __int16 *
0x1800459fa  lea     r8, [rbp+57h+var_80]
0x1800459fe  cmp     qword ptr [rbp+57h+var_70+8], r14
0x180045a02  cmova   r8, [rbp+57h+var_80]; unsigned __int16 *
0x180045a07  lea     rdx, [rbp+57h+var_60]
0x180045a0b  cmp     qword ptr [rbp+57h+var_50+8], r14
0x180045a0f  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180045a14  lea     r10, [rsp+120h+var_E0]
0x180045a19  mov     [rsp+120h+var_F8], r10; struct IXMLDOMDocument **
0x180045a1e  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180045a23  call    ?GetStatusMessageXml@CSmsMessageXmlHelper@@SAJPEAUISmsStatusMessage@@PEBG111PEAPEAUIXMLDOMDocument@@@Z; CSmsMessageXmlHelper::GetStatusMessageXml(ISmsStatusMessage *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x180045a28  test    eax, eax
0x180045a2a  js      short loc_180045A33
0x180045a2c  mov     esi, 5
0x180045a31  jmp     short loc_180045A4A
0x180045a33  lea     r9, aFailedToCreate_5; "Failed to create StatusMessageXml"
0x180045a3a  mov     r8d, eax; int
0x180045a3d  mov     edx, 4ABh; unsigned int
0x180045a42  mov     rcx, r12; char *
0x180045a45  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180045a4a  mov     rcx, [rsp+120h+var_F0]
0x180045a4f  test    rcx, rcx
0x180045a52  jz      short loc_180045A61
0x180045a54  mov     rax, [rcx]
0x180045a57  mov     rax, [rax+10h]
0x180045a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a60  nop
0x180045a61  test    esi, esi
0x180045a63  jnz     loc_180045BD3
0x180045a69  xor     ecx, ecx
0x180045a6b  mov     [rsp+120h+var_F0], rcx
0x180045a70  test    rdi, rdi
0x180045a73  jz      short loc_180045A94
0x180045a75  mov     rax, [rdi]
0x180045a78  lea     r8, [rsp+120h+var_F0]
0x180045a7d  lea     rdx, _GUID_588e24c6_8f80_42bc_ae61_4a834343bf0a
0x180045a84  mov     rcx, rdi
0x180045a87  mov     rax, [rax]
0x180045a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a8f  mov     rcx, [rsp+120h+var_F0]; struct ISmsVoicemailMessage *
0x180045a94  test    rcx, rcx
0x180045a97  jz      short loc_180045B08
0x180045a99  lea     rax, [rbp+57h+var_C0]
0x180045a9d  cmp     qword ptr [rbp+57h+var_B0+8], r14
0x180045aa1  cmova   rax, [rbp+57h+var_C0]
0x180045aa6  lea     r9, [rbp+57h+var_A0]
0x180045aaa  cmp     qword ptr [rbp+57h+var_90+8], r14
0x180045aae  cmova   r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180045ab3  lea     r8, [rbp+57h+var_80]
0x180045ab7  cmp     qword ptr [rbp+57h+var_70+8], r14
0x180045abb  cmova   r8, [rbp+57h+var_80]; unsigned __int16 *
0x180045ac0  lea     rdx, [rbp+57h+var_60]
0x180045ac4  cmp     qword ptr [rbp+57h+var_50+8], r14
0x180045ac8  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180045acd  lea     r10, [rsp+120h+var_E0]
0x180045ad2  mov     [rsp+120h+var_F8], r10; struct IXMLDOMDocument **
0x180045ad7  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180045adc  call    ?GetVoicemailMessageXml@CSmsMessageXmlHelper@@SAJPEAUISmsVoicemailMessage@@PEBG111PEAPEAUIXMLDOMDocument@@@Z; CSmsMessageXmlHelper::GetVoicemailMessageXml(ISmsVoicemailMessage *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMDocument * *)
0x180045ae1  test    eax, eax
0x180045ae3  js      short loc_180045AEC
0x180045ae5  mov     esi, 3
0x180045aea  jmp     short loc_180045B03
0x180045aec  lea     r9, aFailedToCreate_11; "Failed to create VoicemailMessageXml"
0x180045af3  mov     r8d, eax; int
0x180045af6  mov     edx, 4BDh; unsigned int
0x180045afb  mov     rcx, r12; char *
0x180045afe  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180045b03  mov     rcx, [rsp+120h+var_F0]
0x180045b08  test    rcx, rcx
0x180045b0b  jz      short loc_180045B1A
0x180045b0d  mov     rax, [rcx]
0x180045b10  mov     rax, [rax+10h]
0x180045b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b19  nop
0x180045b1a  test    esi, esi
  ... truncated ...
```
