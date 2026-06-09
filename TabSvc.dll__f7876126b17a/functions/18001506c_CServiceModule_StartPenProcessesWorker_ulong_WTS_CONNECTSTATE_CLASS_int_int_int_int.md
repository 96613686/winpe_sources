# CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)

- ea: `0x18001506c`
- end: `0x18001559a`
- name: `?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z`
- size: `1326`
- prototype: `void __fastcall(PVOID Context, unsigned int, unsigned int, int, int, int)`
- caller_count: `5`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x18000f428`
- `0x180023bd0`
- `0x180023f54`
- `0x180024260`
- `0x180026fa8`

## callees

- `0x180001008`
- `0x180001bd8`
- `0x180001ec0`
- `0x180001f24`
- `0x18000ed70`
- `0x18000f0fc`
- `0x1800141d4`
- `0x180014a80`
- `0x18001506c`
- `0x180015630`
- `0x1800169d0`
- `0x180017bb0`
- `0x18001a760`
- `0x18001bbe0`
- `0x18002718c`
- `0x1800285c8`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b630`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800150e4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001515b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800151dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001536d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800150e4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001515b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800151dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18001536d`

## string_xrefs

- `0x1800150ba`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x1800150f1`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x180015233`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x180015301`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x1800153a4`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x1800154e4`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x18001555f`: `PENSERVICE_CServiceModule::_StartPenProcessesWorker`
- `0x180015520`: `Failed to create session, out of memory`

## pseudocode

```c
void __fastcall CServiceModule::_StartPenProcessesWorker(
        PVOID Context,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6)
{
  struct _GUID *v10; // rax
  char active; // al
  int v12; // r8d
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  CPenSession *v20; // rax
  CPenSession *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  bool v28; // zf
  const struct CPenProcessInfo *v29; // rdx
  const struct CPenProcessInfo *v30; // rdx
  CServiceModule *v31; // rcx
  const struct CPenProcessInfo *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  const char *v36; // [rsp+30h] [rbp-A1h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-99h] BYREF
  int v38; // [rsp+3Ch] [rbp-95h] BYREF
  __int128 v39; // [rsp+40h] [rbp-91h] BYREF
  __int64 v40; // [rsp+50h] [rbp-81h]
  int v41; // [rsp+58h] [rbp-79h] BYREF
  __m128i si128; // [rsp+5Ch] [rbp-75h]
  int v43; // [rsp+6Ch] [rbp-65h]
  __int128 v44; // [rsp+70h] [rbp-61h] BYREF
  __int64 v45; // [rsp+80h] [rbp-51h]
  _BYTE v46[32]; // [rsp+90h] [rbp-41h] BYREF
  const char **v47; // [rsp+B0h] [rbp-21h]
  __int64 v48; // [rsp+B8h] [rbp-19h]
  unsigned int *v49; // [rsp+C0h] [rbp-11h]
  __int64 v50; // [rsp+C8h] [rbp-9h]
  int *v51; // [rsp+D0h] [rbp-1h]
  __int64 v52; // [rsp+D8h] [rbp+7h]

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    {
      WPP_SF_s(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        43,
        WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        "PENSERVICE_CServiceModule::_StartPenProcessesWorker");
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != (struct _GUID *)&WPP_GLOBAL_Control && (v10[1].Data4[4] & 0x10) != 0 )
    {
      active = WTSGetActiveConsoleSessionId();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        44,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_CServiceModule::_StartPenProcessesWorker",
        active);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v38 = *((_DWORD *)Context + 17);
      v37 = a3;
      v13 = WTSGetActiveConsoleSessionId();
      v52 = 4;
      LODWORD(v36) = v13;
      v50 = 4;
      v51 = &v38;
      v48 = 4;
      v49 = &v37;
      v47 = &v36;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_1800411A8,
        (unsigned int)&byte_18003943F,
        0,
        0,
        5,
        (__int64)v46);
    }
  }
  else if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    LODWORD(v36) = WTSGetActiveConsoleSessionId();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v14,
      (int)&word_180039276,
      v15,
      v16,
      (__int64)&v36);
  }
  if ( a3 > 1 && (!a6 || a3 != 2) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_sll(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        48,
        v12,
        (unsigned int)"PENSERVICE_CServiceModule::_StartPenProcessesWorker",
        a2,
        a3);
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      LODWORD(v36) = a3;
      v37 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (int)byte_18003A571,
        v18,
        v19,
        (__int64)&v37,
        (__int64)&v36);
    }
    goto LABEL_59;
  }
  v20 = CServiceModule::EnsurePenSession((CServiceModule *)Context, a2);
  v21 = v20;
  if ( v20 )
  {
    if ( !a2 )
      goto LABEL_59;
    if ( !*((_DWORD *)Context + 17) )
    {
      if ( (a3 & 0xFFFFFFFD) != 0 )
        goto LABEL_35;
      if ( !(unsigned int)CPenSession::Initialize(v20) )
      {
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sd(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            45,
            (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            (unsigned int)"PENSERVICE_CServiceModule::_StartPenProcessesWorker",
            a2);
        if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
        {
          LODWORD(v36) = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v22,
            (int)&dword_18003A92C,
            v23,
            v24,
            (__int64)&v36);
        }
      }
    }
    if ( !a3 )
    {
LABEL_39:
      if ( !(unsigned int)CPenSession::SystemInitialize(v21) )
      {
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sd(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            46,
            (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            (unsigned int)"PENSERVICE_CServiceModule::_StartPenProcessesWorker",
            a2);
        if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
        {
          LODWORD(v36) = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v25,
            (int)&unk_18003AA58,
            v26,
            v27,
            (__int64)&v36);
        }
      }
      v28 = *((_DWORD *)Context + 17) == 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v41 = 1;
      v43 = 0;
      if ( v28 )
      {
        if ( *((_BYTE *)v21 + 9) )
        {
          CServiceModule::OnSystemTextInputProcessRequest((CServiceModule *)Context, v21);
        }
        else
        {
          v30 = (const struct CPenProcessInfo *)*((_QWORD *)Context + 73);
          v40 = 1;
          v39 = 0;
          CServiceModule::StartPenProcessAsUser(Context, v30, v21, (const struct CPenProcessStartInfo *)&v39);
          if ( !CServiceModule::_IsRailSession(v31, *((_DWORD *)v21 + 1)) )
          {
            v32 = (const struct CPenProcessInfo *)*((_QWORD *)Context + 70);
            v45 = 1;
            v44 = 0;
            CServiceModule::StartPenProcessAsUser(Context, v32, v21, (const struct CPenProcessStartInfo *)&v44);
          }
        }
      }
      else
      {
        v29 = (const struct CPenProcessInfo *)*((_QWORD *)Context + 75);
        v40 = 1;
        v39 = 0;
        CServiceModule::StartPenProcessAsSystem(
          (CServiceModule *)Context,
          v29,
          v21,
          (const struct CPenProcessStartInfo *)&v39);
        CServiceModule::StartPenProcessAsSystem(
          (CServiceModule *)Context,
          *((const struct CPenProcessInfo **)Context + 71),
          v21,
          (const struct CPenProcessStartInfo *)&v41);
      }
      CServiceModule::_ProcessSessionEvents((CServiceModule *)&_Module, v21);
      goto LABEL_59;
    }
LABEL_35:
    if ( (!a6 || a3 != 2) && a4 && a2 != WTSGetActiveConsoleSessionId() )
      goto LABEL_59;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      47,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::_StartPenProcessesWorker",
      a2);
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v36 = "Failed to create session, out of memory";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v33,
      (unsigned __int8 *)word_18003967A,
      v34,
      v35,
      (const unsigned __int16 **)&v36);
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      49,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_StartPenProcessesWorker");
}

```

## disassembly

```asm
0x18001506c  mov     [rsp-8+arg_10], rbx
0x180015071  push    rbp
0x180015072  push    rsi
0x180015073  push    rdi
0x180015074  push    r12
0x180015076  push    r14
0x180015078  lea     rbp, [rsp-1Fh]
0x18001507d  sub     rsp, 0F0h
0x180015084  mov     rax, cs:__security_cookie
0x18001508b  xor     rax, rsp
0x18001508e  mov     [rbp+3Fh+var_30], rax
0x180015092  mov     r12d, r9d
0x180015095  mov     r14d, r8d
0x180015098  mov     esi, edx
0x18001509a  mov     rdi, rcx
0x18001509d  mov     rax, cs:WPP_GLOBAL_Control
0x1800150a4  lea     rbx, WPP_GLOBAL_Control
0x1800150ab  cmp     rax, rbx
0x1800150ae  jz      short loc_180015111
0x1800150b0  test    byte ptr [rax+1Ch], 10h
0x1800150b4  jz      short loc_1800150D9
0x1800150b6  mov     rcx, [rax+10h]
0x1800150ba  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x1800150c1  mov     edx, 2Bh ; '+'
0x1800150c6  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800150cd  call    WPP_SF_s
0x1800150d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800150d9  cmp     rax, rbx
0x1800150dc  jz      short loc_180015111
0x1800150de  test    byte ptr [rax+1Ch], 10h
0x1800150e2  jz      short loc_180015111
0x1800150e4  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800150ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150f1  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x1800150f8  mov     edx, 2Ch ; ','
0x1800150fd  mov     dword ptr [rsp+110h+var_F0], eax
0x180015101  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180015108  mov     rcx, [rcx+10h]
0x18001510c  call    WPP_SF_sd
0x180015111  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch> `wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl(void)'::`2'::impl
0x180015118  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(void)
0x18001511d  test    al, al
0x18001511f  mov     ecx, 4000000h
0x180015124  mov     eax, cs:dword_1800411A8
0x18001512a  jz      loc_1800151C4
0x180015130  cmp     eax, 5
0x180015133  jbe     loc_1800151FC
0x180015139  mov     edx, ecx
0x18001513b  lea     rcx, dword_1800411A8
0x180015142  call    _tlgKeywordOn
0x180015147  test    al, al
0x180015149  jz      loc_1800151FC
0x18001514f  mov     eax, [rdi+44h]
0x180015152  mov     [rsp+110h+var_D4], eax
0x180015156  mov     [rsp+110h+var_D8], r14d
0x18001515b  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180015161  xor     r9d, r9d
0x180015164  mov     [rbp+3Fh+var_38], 4
0x18001516c  mov     dword ptr [rsp+110h+var_E0], eax
0x180015170  lea     rdx, byte_18003943F
0x180015177  lea     rax, [rsp+110h+var_D4]
0x18001517c  mov     [rbp+3Fh+var_48], 4
0x180015184  mov     [rbp+3Fh+var_40], rax
0x180015188  lea     rcx, dword_1800411A8
0x18001518f  lea     rax, [rsp+110h+var_D8]
0x180015194  mov     [rbp+3Fh+var_58], 4
0x18001519c  mov     [rbp+3Fh+var_50], rax
0x1800151a0  xor     r8d, r8d
0x1800151a3  lea     rax, [rsp+110h+var_E0]
0x1800151a8  mov     [rbp+3Fh+var_60], rax
0x1800151ac  lea     rax, [rbp+3Fh+var_80]
0x1800151b0  mov     [rsp+110h+var_E8], rax
0x1800151b5  mov     dword ptr [rsp+110h+var_F0], 5
0x1800151bd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800151c2  jmp     short loc_1800151FC
0x1800151c4  cmp     eax, 5
0x1800151c7  jbe     short loc_1800151FC
0x1800151c9  mov     rdx, rcx
0x1800151cc  lea     rcx, dword_1800411A8
0x1800151d3  call    _tlgKeywordOn
0x1800151d8  test    al, al
0x1800151da  jz      short loc_1800151FC
0x1800151dc  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800151e2  mov     dword ptr [rsp+110h+var_E0], eax
0x1800151e6  lea     rdx, word_180039276
0x1800151ed  lea     rax, [rsp+110h+var_E0]
0x1800151f2  mov     [rsp+110h+var_F0], rax
0x1800151f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800151fc  cmp     r14d, 1
0x180015200  jbe     loc_1800152A3
0x180015206  cmp     [rbp+3Fh+arg_28], 0
0x18001520a  jz      short loc_180015216
0x18001520c  cmp     r14d, 2
0x180015210  jz      loc_1800152A3
0x180015216  mov     rcx, cs:WPP_GLOBAL_Control
0x18001521d  lea     rax, WPP_GLOBAL_Control
0x180015224  cmp     rcx, rax
0x180015227  jz      short loc_18001524D
0x180015229  test    byte ptr [rcx+1Ch], 10h
0x18001522d  jz      short loc_18001524D
0x18001522f  mov     rcx, [rcx+10h]
0x180015233  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x18001523a  mov     edx, 30h ; '0'
0x18001523f  mov     dword ptr [rsp+110h+var_E8], r14d
0x180015244  mov     dword ptr [rsp+110h+var_F0], esi
0x180015248  call    WPP_SF_sll
0x18001524d  mov     eax, cs:dword_1800411A8
0x180015253  cmp     eax, 5
0x180015256  jbe     loc_180015542
0x18001525c  mov     edx, 4000000h
0x180015261  lea     rcx, dword_1800411A8
0x180015268  call    _tlgKeywordOn
0x18001526d  test    al, al
0x18001526f  jz      loc_180015542
0x180015275  lea     rax, [rsp+110h+var_E0]
0x18001527a  mov     dword ptr [rsp+110h+var_E0], r14d
0x18001527f  mov     [rsp+110h+var_E8], rax
0x180015284  lea     rdx, byte_18003A571
0x18001528b  lea     rax, [rsp+110h+var_D8]
0x180015290  mov     [rsp+110h+var_D8], esi
0x180015294  mov     [rsp+110h+var_F0], rax
0x180015299  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001529e  jmp     loc_180015542
0x1800152a3  mov     edx, esi; unsigned int
0x1800152a5  mov     rcx, rdi; this
0x1800152a8  call    ?EnsurePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z; CServiceModule::EnsurePenSession(ulong)
0x1800152ad  mov     rbx, rax
0x1800152b0  test    rax, rax
0x1800152b3  jz      loc_1800154C7
0x1800152b9  test    esi, esi
0x1800152bb  jz      loc_180015542
0x1800152c1  cmp     dword ptr [rdi+44h], 0
0x1800152c5  jnz     loc_180015357
0x1800152cb  test    r14d, 0FFFFFFFDh
0x1800152d2  jnz     loc_18001535C
0x1800152d8  mov     rcx, rax; this
0x1800152db  call    ?Initialize@CPenSession@@QEAAHXZ; CPenSession::Initialize(void)
0x1800152e0  test    eax, eax
0x1800152e2  jnz     short loc_180015357
0x1800152e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152eb  lea     rax, WPP_GLOBAL_Control
0x1800152f2  cmp     rcx, rax
0x1800152f5  jz      short loc_18001531D
0x1800152f7  test    byte ptr [rcx+1Ch], 10h
0x1800152fb  jz      short loc_18001531D
0x1800152fd  mov     rcx, [rcx+10h]
0x180015301  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x180015308  mov     edx, 2Dh ; '-'
0x18001530d  mov     dword ptr [rsp+110h+var_F0], esi
0x180015311  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180015318  call    WPP_SF_sd
0x18001531d  mov     eax, cs:dword_1800411A8
0x180015323  cmp     eax, 5
0x180015326  jbe     short loc_180015357
0x180015328  mov     edx, 4000000h
0x18001532d  lea     rcx, dword_1800411A8
0x180015334  call    _tlgKeywordOn
0x180015339  test    al, al
0x18001533b  jz      short loc_180015357
0x18001533d  lea     rax, [rsp+110h+var_E0]
0x180015342  mov     dword ptr [rsp+110h+var_E0], esi
0x180015346  lea     rdx, dword_18003A92C
0x18001534d  mov     [rsp+110h+var_F0], rax
0x180015352  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180015357  test    r14d, r14d
0x18001535a  jz      short loc_18001537B
0x18001535c  cmp     [rbp+3Fh+arg_28], 0
0x180015360  jz      short loc_180015368
0x180015362  cmp     r14d, 2
0x180015366  jz      short loc_18001537B
0x180015368  test    r12d, r12d
0x18001536b  jz      short loc_18001537B
0x18001536d  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180015373  cmp     esi, eax
0x180015375  jnz     loc_180015542
0x18001537b  mov     rcx, rbx; this
0x18001537e  call    ?SystemInitialize@CPenSession@@QEAAHXZ; CPenSession::SystemInitialize(void)
0x180015383  test    eax, eax
0x180015385  jnz     short loc_1800153FA
0x180015387  mov     rcx, cs:WPP_GLOBAL_Control
0x18001538e  lea     rax, WPP_GLOBAL_Control
0x180015395  cmp     rcx, rax
0x180015398  jz      short loc_1800153C0
0x18001539a  test    byte ptr [rcx+1Ch], 10h
0x18001539e  jz      short loc_1800153C0
0x1800153a0  mov     rcx, [rcx+10h]
0x1800153a4  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x1800153ab  mov     edx, 2Eh ; '.'
0x1800153b0  mov     dword ptr [rsp+110h+var_F0], esi
0x1800153b4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800153bb  call    WPP_SF_sd
0x1800153c0  mov     eax, cs:dword_1800411A8
0x1800153c6  cmp     eax, 5
0x1800153c9  jbe     short loc_1800153FA
0x1800153cb  mov     edx, 4000000h
0x1800153d0  lea     rcx, dword_1800411A8
0x1800153d7  call    _tlgKeywordOn
0x1800153dc  test    al, al
0x1800153de  jz      short loc_1800153FA
0x1800153e0  lea     rax, [rsp+110h+var_E0]
0x1800153e5  mov     dword ptr [rsp+110h+var_E0], esi
0x1800153e9  lea     rdx, unk_18003AA58
0x1800153f0  mov     [rsp+110h+var_F0], rax
0x1800153f5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800153fa  cmp     dword ptr [rdi+44h], 0
0x1800153fe  mov     esi, 1
0x180015403  movdqa  xmm0, cs:__xmm@00000001000000000000000000000000
0x18001540b  mov     rcx, rdi; Context
0x18001540e  movdqu  [rbp+3Fh+var_B4], xmm0
0x180015413  mov     [rbp+3Fh+var_B8], esi
0x180015416  mov     [rbp+3Fh+var_A4], 0
0x18001541d  jz      short loc_180015458
0x18001541f  mov     rdx, [rdi+258h]; struct CPenProcessInfo *
0x180015426  lea     r9, [rsp+110h+var_D0]; struct CPenProcessStartInfo *
0x18001542b  xorps   xmm0, xmm0
0x18001542e  mov     [rsp+110h+var_C0], rsi
0x180015433  mov     r8, rbx; struct CPenSession *
0x180015436  movups  [rsp+110h+var_D0], xmm0
0x18001543b  call    ?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x180015440  mov     rdx, [rdi+238h]; struct CPenProcessInfo *
0x180015447  lea     r9, [rbp+3Fh+var_B8]; struct CPenProcessStartInfo *
0x18001544b  mov     r8, rbx; struct CPenSession *
0x18001544e  mov     rcx, rdi; this
0x180015451  call    ?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x180015456  jmp     short loc_1800154B6
0x180015458  cmp     byte ptr [rbx+9], 0
0x18001545c  jz      short loc_180015468
0x18001545e  mov     rdx, rbx; struct CPenSession *
0x180015461  call    ?OnSystemTextInputProcessRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z; CServiceModule::OnSystemTextInputProcessRequest(CPenSession *)
0x180015466  jmp     short loc_1800154B6
0x180015468  mov     rdx, [rdi+248h]; struct CPenProcessInfo *
0x18001546f  lea     r9, [rsp+110h+var_D0]; struct CPenProcessStartInfo *
0x180015474  xorps   xmm0, xmm0
0x180015477  mov     [rsp+110h+var_C0], rsi
0x18001547c  mov     r8, rbx; struct CPenSession *
0x18001547f  movups  [rsp+110h+var_D0], xmm0
0x180015484  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x180015489  mov     edx, [rbx+4]; unsigned int
0x18001548c  call    ?_IsRailSession@CServiceModule@@AEAA_NK@Z; CServiceModule::_IsRailSession(ulong)
0x180015491  test    al, al
0x180015493  jnz     short loc_1800154B6
0x180015495  mov     rdx, [rdi+230h]; struct CPenProcessInfo *
0x18001549c  lea     r9, [rbp+3Fh+var_A0]; struct CPenProcessStartInfo *
0x1800154a0  xorps   xmm0, xmm0
0x1800154a3  mov     [rbp+3Fh+var_90], rsi
0x1800154a7  mov     r8, rbx; struct CPenSession *
0x1800154aa  mov     rcx, rdi; Context
0x1800154ad  movups  [rbp+3Fh+var_A0], xmm0
0x1800154b1  call    ?StartPenProcessAsUser@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsUser(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x1800154b6  mov     rdx, rbx; struct CPenSession *
0x1800154b9  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x1800154c0  call    ?_ProcessSessionEvents@CServiceModule@@AEAAXPEAVCPenSession@@@Z; CServiceModule::_ProcessSessionEvents(CPenSession *)
0x1800154c5  jmp     short loc_180015542
0x1800154c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154ce  lea     rax, WPP_GLOBAL_Control
0x1800154d5  cmp     rcx, rax
0x1800154d8  jz      short loc_180015500
0x1800154da  test    byte ptr [rcx+1Ch], 4
0x1800154de  jz      short loc_180015500
0x1800154e0  mov     rcx, [rcx+10h]
0x1800154e4  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x1800154eb  mov     edx, 2Fh ; '/'
0x1800154f0  mov     dword ptr [rsp+110h+var_F0], esi
0x1800154f4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800154fb  call    WPP_SF_sd
0x180015500  mov     eax, cs:dword_1800411A8
0x180015506  cmp     eax, 5
0x180015509  jbe     short loc_180015542
0x18001550b  mov     edx, 4000000h
0x180015510  lea     rcx, dword_1800411A8
0x180015517  call    _tlgKeywordOn
0x18001551c  test    al, al
0x18001551e  jz      short loc_180015542
0x180015520  lea     rax, aFailedToCreate; "Failed to create session, out of memory"
0x180015527  mov     [rsp+110h+var_E0], rax
0x18001552c  lea     rdx, word_18003967A
0x180015533  lea     rax, [rsp+110h+var_E0]
0x180015538  mov     [rsp+110h+var_F0], rax
0x18001553d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015542  mov     rcx, cs:WPP_GLOBAL_Control
0x180015549  lea     rax, WPP_GLOBAL_Control
0x180015550  cmp     rcx, rax
0x180015553  jz      short loc_180015577
0x180015555  test    byte ptr [rcx+1Ch], 10h
0x180015559  jz      short loc_180015577
0x18001555b  mov     rcx, [rcx+10h]
0x18001555f  lea     r9, aPenserviceCser_32; "PENSERVICE_CServiceModule::_StartPenPro"...
0x180015566  mov     edx, 31h ; '1'
0x18001556b  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180015572  call    WPP_SF_s
0x180015577  mov     rcx, [rbp+3Fh+var_30]
0x18001557b  xor     rcx, rsp; StackCookie
0x18001557e  call    __security_check_cookie
0x180015583  mov     rbx, [rsp+110h+arg_10]
0x18001558b  add     rsp, 0F0h
0x180015592  pop     r14
0x180015594  pop     r12
0x180015596  pop     rdi
0x180015597  pop     rsi
0x180015598  pop     rbp
  ... truncated ...
```
