# SwitchHelper::SwitchPortConfigureIov(ushort const *,uint,uint,uint)

- ea: `0x18023cbe0`
- end: `0x18023d27a`
- name: `?SwitchPortConfigureIov@SwitchHelper@@QEAAXPEBGIII@Z`
- size: `1690`
- prototype: `void __usercall(SwitchHelper *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801fc9a0`

## callees

- `0x180002474`
- `0x1800056d0`
- `0x1800057cc`
- `0x180005928`
- `0x18005f0c0`
- `0x18005ffa0`
- `0x18005ffac`
- `0x180061240`
- `0x1800653f0`
- `0x1800666b4`
- `0x1800759d8`
- `0x180075aac`
- `0x180077910`
- `0x18007dc48`
- `0x1800887c4`
- `0x1800887dc`
- `0x18023ba88`
- `0x18023cbe0`

## import_xrefs

- `NetMgmtIF!NetMgmtPortPropertyFree` at `0x18023cfcb`
- `NetMgmtIF!NetMgmtPortPropertyFree` at `0x18023cfcb`
- `NetMgmtIF!NetMgmtUpdateVirtualSwitchPortProperty` at `0x18023ce98`
- `NetMgmtIF!NetMgmtUpdateVirtualSwitchPortProperty` at `0x18023ce98`
- `NetMgmtIF!NetMgmtGetVirtualSwitchPortProperty` at `0x18023cd3e`
- `NetMgmtIF!NetMgmtGetVirtualSwitchPortProperty` at `0x18023cd3e`
- `NetMgmtIF!NetMgmtAddVirtualSwitchPortProperty` at `0x18023cfa4`
- `NetMgmtIF!NetMgmtAddVirtualSwitchPortProperty` at `0x18023cfa4`
- `RPCRT4!UuidCreate` at `0x18023ceb8`
- `RPCRT4!UuidCreate` at `0x18023ceb8`

## string_xrefs

- `0x18023d04e`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`
- `0x18023d0bd`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`
- `0x18023d12c`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`
- `0x18023d19b`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`
- `0x18023d268`: `onecore\vm\dv\net\hns\service\common\helperlib\src\switchhelper.cpp`
- `0x18023cc1b`: `SwitchHelper::SwitchPortConfigureIov`
- `0x18023cfb5`: `SwitchHelper::SwitchPortConfigureIov`
- `0x18023cf2e`: `SwitchHelper::ConfigureDefaultOffloadValues`
- `0x18023cf56`: `SwitchHelper::ConfigureDefaultOffloadValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SwitchHelper::SwitchPortConfigureIov(
        SwitchHelper *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5)
{
  const struct _GUID *v9; // r8
  int v10; // r9d
  char **v11; // rbx
  char *v12; // rax
  int SwitchPortPropertyInstanceId; // eax
  unsigned int v14; // esi
  char *v15; // rcx
  int VirtualSwitchPortProperty; // eax
  unsigned int v17; // esi
  _DWORD *v18; // rsi
  const struct _tlgProvider_t *v19; // rax
  int v20; // r9d
  int v21; // r8d
  char *v22; // rax
  char *v23; // rcx
  int updated; // eax
  unsigned int v25; // esi
  const struct _tlgProvider_t *v26; // rax
  int v27; // r8d
  int v28; // r9d
  char *v29; // rcx
  char *v30; // rcx
  int v31; // eax
  unsigned int v32; // esi
  const unsigned __int16 *v33; // rax
  unsigned int v34; // eax
  const unsigned __int16 *v35; // rax
  unsigned int v36; // eax
  const unsigned __int16 *v37; // rax
  unsigned int v38; // eax
  const unsigned __int16 *v39; // rax
  unsigned int v40; // eax
  const struct _tlgProvider_t *v41; // rax
  int v42; // r8d
  int v43; // r9d
  char *v44; // rcx
  const unsigned __int16 *v45; // rax
  unsigned int v46; // eax
  int v47; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v48; // [rsp+74h] [rbp-8Ch] BYREF
  int v49; // [rsp+78h] [rbp-88h] BYREF
  char *v50; // [rsp+80h] [rbp-80h] BYREF
  char *v51; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v52; // [rsp+90h] [rbp-70h] BYREF
  int v53; // [rsp+98h] [rbp-68h] BYREF
  int v54; // [rsp+9Ch] [rbp-64h] BYREF
  char *v55; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v57; // [rsp+B8h] [rbp-48h]
  UUID v58; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v59; // [rsp+D0h] [rbp-30h]
  _BYTE v60[20]; // [rsp+E0h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v62[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v63[24]; // [rsp+128h] [rbp+28h] BYREF
  GUID Buf1; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v65[2]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  HNSTraceProvider::TraceEnter("SwitchHelper::SwitchPortConfigureIov", 0x4FFu);
  Buf1 = GUID_NULL;
  memset(v65, 0, 28);
  v58 = 0;
  v59 = 0;
  memset(v60, 0, sizeof(v60));
  v50 = 0;
  v9 = (const struct _GUID *)HNSTraceProvider::Provider();
  v11 = (char **)((char *)this + 56);
  if ( v9->Data1 > 5 )
  {
    v48 = a5;
    v49 = a4;
    v47 = a3;
    v52 = a2;
    if ( *((_QWORD *)this + 10) <= 7u )
      v12 = (char *)this + 56;
    else
      v12 = *v11;
    v51 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)byte_1803438D9,
      (_DWORD)v9,
      v10,
      (__int64)&v51,
      (__int64)&v52,
      (__int64)&v47,
      (__int64)&v49,
      (__int64)&v48);
  }
  v56[1] = &v50;
  v57 = 1;
  SwitchPortPropertyInstanceId = SwitchHelper::GetSwitchPortPropertyInstanceId(this, a2, v9, &Buf1);
  v14 = SwitchPortPropertyInstanceId;
  if ( SwitchPortPropertyInstanceId < 0 )
  {
    HNSEventType::HNSEventType((HNSEventType *)v63, SwitchPortPropertyInstanceId);
    v37 = (const unsigned __int16 *)std::wstring::c_str((char *)this + 56);
    HNSEventType::HNSEventType((HNSEventType *)v62, v37);
    HNSEventType::HNSEventType((HNSEventType *)&Uuid, a2);
    EventWrite(&VMSWITCH_PORT_CONFIGURE_IOV_FAILED, (struct HNSEventType *)v63, v62, &Uuid);
    v38 = wil::verify_hresult<long>(v14);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x526,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
      (const char *)v38,
      0);
  }
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    Uuid = 0;
    UuidCreate(&Uuid);
    v58 = Uuid;
    v26 = HNSTraceProvider::Provider();
    if ( *(_DWORD *)v26 > 5u )
    {
      *(_QWORD *)&Uuid.Data1 = &v58;
      v56[0] = a2;
      if ( *((_QWORD *)this + 10) <= 7u )
        v29 = (char *)this + 56;
      else
        v29 = *v11;
      v55 = v29;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (_DWORD)v26,
        (unsigned int)byte_180343893,
        v27,
        v28,
        (__int64)&v55,
        (__int64)v56,
        (__int64)&Uuid);
    }
    LOWORD(v59) = 0;
    DWORD1(v59) = 20;
    HNSTraceProvider::TraceEnter("SwitchHelper::ConfigureDefaultOffloadValues", 0x4D5u);
    *(_DWORD *)v60 = 512;
    *(_QWORD *)&v60[4] = 100;
    *(_QWORD *)&v60[12] = 1;
    HNSTraceProvider::TraceSuccess("SwitchHelper::ConfigureDefaultOffloadValues", 0x4EEu);
    *(_DWORD *)&v60[8] = a3;
    *(_DWORD *)&v60[12] = a4;
    *(_DWORD *)&v60[16] = a5;
    *((_QWORD *)&v59 + 1) = v60;
    if ( *((_QWORD *)this + 10) <= 7u )
      v30 = (char *)this + 56;
    else
      v30 = *v11;
    v31 = NetMgmtAddVirtualSwitchPortProperty(
            v30,
            a2,
            VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID,
            &v58,
            *((_DWORD *)this + 22),
            v65);
    v32 = v31;
    if ( v31 < 0 )
    {
      HNSEventType::HNSEventType((HNSEventType *)&Uuid, v31);
      v33 = (const unsigned __int16 *)std::wstring::c_str((char *)this + 56);
      HNSEventType::HNSEventType((HNSEventType *)v62, v33);
      HNSEventType::HNSEventType((HNSEventType *)v63, a2);
      EventWrite(&VMSWITCH_PORT_CONFIGURE_IOV_FAILED, (struct HNSEventType *)&Uuid, v62, v63);
      v34 = wil::verify_hresult<long>(v32);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A4,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
        (const char *)v34,
        0);
    }
  }
  else
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v15 = (char *)this + 56;
    else
      v15 = *v11;
    VirtualSwitchPortProperty = NetMgmtGetVirtualSwitchPortProperty(
                                  v15,
                                  a2,
                                  VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID,
                                  &Buf1,
                                  &v50);
    v17 = VirtualSwitchPortProperty;
    if ( VirtualSwitchPortProperty < 0 )
    {
      HNSEventType::HNSEventType((HNSEventType *)&Uuid, VirtualSwitchPortProperty);
      v39 = (const unsigned __int16 *)std::wstring::c_str((char *)this + 56);
      HNSEventType::HNSEventType((HNSEventType *)v62, v39);
      HNSEventType::HNSEventType((HNSEventType *)v63, a2);
      EventWrite(&VMSWITCH_PORT_CONFIGURE_IOV_FAILED, (struct HNSEventType *)&Uuid, v62, v63);
      v40 = wil::verify_hresult<long>(v17);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x535,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
        (const char *)v40,
        0);
    }
    if ( *((_DWORD *)v50 + 5) < 0x14u )
    {
      v41 = HNSTraceProvider::Provider();
      if ( *(_DWORD *)v41 > 5u )
      {
        v47 = *((_DWORD *)v50 + 5);
        v52 = a2;
        if ( *((_QWORD *)this + 10) <= 7u )
          v44 = (char *)this + 56;
        else
          v44 = *v11;
        v51 = v44;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v41,
          (unsigned int)&byte_18034394F,
          v42,
          v43,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v47);
      }
      HNSEventType::HNSEventType((HNSEventType *)&Uuid, -2147467259);
      v45 = (const unsigned __int16 *)std::wstring::c_str((char *)this + 56);
      HNSEventType::HNSEventType((HNSEventType *)v62, v45);
      HNSEventType::HNSEventType((HNSEventType *)v63, a2);
      EventWrite(&VMSWITCH_PORT_CONFIGURE_IOV_FAILED, (struct HNSEventType *)&Uuid, v62, v63);
      v46 = wil::verify_hresult<long>(2147500037LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
        (const char *)v46,
        0);
    }
    v18 = (_DWORD *)*((_QWORD *)v50 + 3);
    v19 = HNSTraceProvider::Provider();
    v21 = (int)v19;
    if ( *(_DWORD *)v19 > 5u )
    {
      v47 = v18[4];
      v49 = v18[3];
      v53 = v18[2];
      v54 = v18[1];
      LODWORD(v51) = *v18;
      LOWORD(v48) = *((_WORD *)v50 + 8);
      LODWORD(v52) = *((_DWORD *)v50 + 5);
      v55 = v50;
      v56[0] = a2;
      if ( *((_QWORD *)this + 10) <= 7u )
        v22 = (char *)this + 56;
      else
        v22 = *v11;
      *(_QWORD *)&Uuid.Data1 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_1803437D8,
        v21,
        v20,
        (__int64)&Uuid,
        (__int64)v56,
        (__int64)&v55,
        (__int64)&v52,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v49,
        (__int64)&v47);
    }
    v58 = *(UUID *)v50;
    DWORD1(v59) = *((_DWORD *)v50 + 5);
    LOWORD(v59) = *((_WORD *)v50 + 8);
    memcpy_0(v60, v18, *((unsigned int *)v50 + 5));
    *(_DWORD *)&v60[8] = a3;
    *(_DWORD *)&v60[12] = a4;
    *(_DWORD *)&v60[16] = a5;
    *((_QWORD *)&v59 + 1) = v60;
    if ( *((_QWORD *)this + 10) <= 7u )
      v23 = (char *)this + 56;
    else
      v23 = *v11;
    updated = NetMgmtUpdateVirtualSwitchPortProperty(
                v23,
                a2,
                VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID,
                &v58,
                *((_DWORD *)this + 22),
                v65);
    v25 = updated;
    if ( updated < 0 )
    {
      HNSEventType::HNSEventType((HNSEventType *)&Uuid, updated);
      v35 = (const unsigned __int16 *)std::wstring::c_str((char *)this + 56);
      HNSEventType::HNSEventType((HNSEventType *)v62, v35);
      HNSEventType::HNSEventType((HNSEventType *)v63, a2);
      EventWrite(&VMSWITCH_PORT_CONFIGURE_IOV_FAILED, (struct HNSEventType *)&Uuid, v62, v63);
      v36 = wil::verify_hresult<long>(v25);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x578,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\switchhelper.cpp",
        (const char *)v36,
        0);
    }
  }
  HNSTraceProvider::TraceSuccess("SwitchHelper::SwitchPortConfigureIov", 0x5A8u);
  if ( v50 )
    NetMgmtPortPropertyFree();
}

```

## disassembly

```asm
0x18023cbe0  push    rbp
0x18023cbe2  push    rbx
0x18023cbe3  push    rsi
0x18023cbe4  push    rdi
0x18023cbe5  push    r12
0x18023cbe7  push    r13
0x18023cbe9  push    r14
0x18023cbeb  push    r15
0x18023cbed  lea     rbp, [rsp-88h]
0x18023cbf5  sub     rsp, 188h
0x18023cbfc  mov     rax, cs:__security_cookie
0x18023cc03  xor     rax, rsp
0x18023cc06  mov     [rbp+0C0h+var_50], rax
0x18023cc0a  mov     r15d, r9d
0x18023cc0d  mov     r14d, r8d
0x18023cc10  mov     rdi, rdx
0x18023cc13  mov     r13, rcx
0x18023cc16  mov     edx, 4FFh; unsigned int
0x18023cc1b  lea     rcx, aSwitchhelperSw_0; "SwitchHelper::SwitchPortConfigureIov"
0x18023cc22  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18023cc27  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18023cc2e  movdqu  [rbp+0C0h+Buf1], xmm0
0x18023cc33  xorps   xmm1, xmm1
0x18023cc36  xor     eax, eax
0x18023cc38  movups  [rbp+0C0h+var_70], xmm1
0x18023cc3c  movups  [rbp+0C0h+var_70+0Ch], xmm1
0x18023cc40  xorps   xmm0, xmm0
0x18023cc43  movups  [rbp+0C0h+var_100], xmm0
0x18023cc47  movups  [rbp+0C0h+var_F0], xmm0
0x18023cc4b  movups  [rbp+0C0h+var_E0], xmm1
0x18023cc4f  mov     [rbp+0C0h+var_D0], eax
0x18023cc52  mov     [rbp+0C0h+var_140], rax
0x18023cc56  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x18023cc5b  mov     r8, rax
0x18023cc5e  mov     ecx, [rax]
0x18023cc60  lea     rbx, [r13+38h]
0x18023cc64  mov     r12d, [rbp+0C0h+arg_20]
0x18023cc6b  cmp     ecx, 5
0x18023cc6e  jbe     short loc_18023CCD5
0x18023cc70  mov     [rsp+1C0h+var_14C], r12d
0x18023cc75  mov     [rsp+1C0h+var_148], r15d
0x18023cc7a  mov     [rsp+1C0h+var_150], r14d
0x18023cc7f  mov     [rbp+0C0h+var_130], rdi
0x18023cc83  cmp     qword ptr [rbx+18h], 7
0x18023cc88  jbe     short loc_18023CC8F
0x18023cc8a  mov     rax, [rbx]
0x18023cc8d  jmp     short loc_18023CC92
0x18023cc8f  mov     rax, rbx
0x18023cc92  mov     [rbp+0C0h+var_138], rax
0x18023cc96  lea     rax, [rsp+1C0h+var_14C]
0x18023cc9b  mov     [rsp+1C0h+var_180], rax
0x18023cca0  lea     rax, [rsp+1C0h+var_148]
0x18023cca5  mov     [rsp+1C0h+var_188], rax
0x18023ccaa  lea     rax, [rsp+1C0h+var_150]
0x18023ccaf  mov     [rsp+1C0h+var_190], rax
0x18023ccb4  lea     rax, [rbp+0C0h+var_130]
0x18023ccb8  mov     [rsp+1C0h+var_198], rax
0x18023ccbd  lea     rax, [rbp+0C0h+var_138]
0x18023ccc1  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18023ccc6  lea     rdx, byte_1803438D9
0x18023cccd  mov     rcx, r8
0x18023ccd0  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18023ccd5  lea     rax, [rbp+0C0h+var_140]
0x18023ccd9  mov     [rbp+0C0h+var_110], rax
0x18023ccdd  mov     [rbp+0C0h+var_108], 1
0x18023cce1  lea     r9, [rbp+0C0h+Buf1]; struct _GUID *
0x18023cce5  mov     rdx, rdi; unsigned __int16 *
0x18023cce8  mov     rcx, r13; this
0x18023cceb  call    ?GetSwitchPortPropertyInstanceId@SwitchHelper@@QEAAJPEBGPEBU_GUID@@PEAU2@@Z; SwitchHelper::GetSwitchPortPropertyInstanceId(ushort const *,_GUID const *,_GUID *)
0x18023ccf0  mov     esi, eax
0x18023ccf2  test    eax, eax
0x18023ccf4  js      loc_18023D0CF
0x18023ccfa  mov     r8d, 10h; Size
0x18023cd00  lea     rdx, GUID_NULL; Buf2
0x18023cd07  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x18023cd0b  call    memcmp_0
0x18023cd10  test    eax, eax
0x18023cd12  jz      loc_18023CEAD
0x18023cd18  cmp     qword ptr [rbx+18h], 7
0x18023cd1d  jbe     short loc_18023CD24
0x18023cd1f  mov     rcx, [rbx]
0x18023cd22  jmp     short loc_18023CD27
0x18023cd24  mov     rcx, rbx
0x18023cd27  lea     rax, [rbp+0C0h+var_140]
0x18023cd2b  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18023cd30  lea     r9, [rbp+0C0h+Buf1]
0x18023cd34  lea     r8, VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID
0x18023cd3b  mov     rdx, rdi
0x18023cd3e  call    cs:__imp_NetMgmtGetVirtualSwitchPortProperty
0x18023cd44  mov     esi, eax
0x18023cd46  test    eax, eax
0x18023cd48  js      loc_18023D13E
0x18023cd4e  mov     rsi, [rbp+0C0h+var_140]
0x18023cd52  cmp     dword ptr [rsi+14h], 14h
0x18023cd56  jb      loc_18023D1AD
0x18023cd5c  mov     rsi, [rsi+18h]
0x18023cd60  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x18023cd65  mov     r8, rax
0x18023cd68  mov     ecx, [rax]
0x18023cd6a  cmp     ecx, 5
0x18023cd6d  jbe     loc_18023CE2C
0x18023cd73  mov     ecx, [rsi+10h]
0x18023cd76  mov     [rsp+1C0h+var_150], ecx
0x18023cd7a  mov     ecx, [rsi+0Ch]
0x18023cd7d  mov     [rsp+1C0h+var_148], ecx
0x18023cd81  mov     ecx, [rsi+8]
0x18023cd84  mov     [rbp+0C0h+var_128], ecx
0x18023cd87  mov     ecx, [rsi+4]
0x18023cd8a  mov     [rbp+0C0h+var_124], ecx
0x18023cd8d  mov     ecx, [rsi]
0x18023cd8f  mov     dword ptr [rbp+0C0h+var_138], ecx
0x18023cd92  mov     rcx, [rbp+0C0h+var_140]
0x18023cd96  movzx   eax, word ptr [rcx+10h]
0x18023cd9a  mov     word ptr [rsp+1C0h+var_14C], ax
0x18023cd9f  mov     eax, [rcx+14h]
0x18023cda2  mov     dword ptr [rbp+0C0h+var_130], eax
0x18023cda5  mov     [rbp+0C0h+var_120], rcx
0x18023cda9  mov     [rbp+0C0h+var_118], rdi
0x18023cdad  cmp     qword ptr [rbx+18h], 7
0x18023cdb2  jbe     short loc_18023CDB9
0x18023cdb4  mov     rax, [rbx]
0x18023cdb7  jmp     short loc_18023CDBC
0x18023cdb9  mov     rax, rbx
0x18023cdbc  mov     qword ptr [rbp+0C0h+Uuid.Data1], rax
0x18023cdc0  lea     rax, [rsp+1C0h+var_150]
0x18023cdc5  mov     [rsp+1C0h+var_158], rax
0x18023cdca  lea     rax, [rsp+1C0h+var_148]
0x18023cdcf  mov     [rsp+1C0h+var_160], rax
0x18023cdd4  lea     rax, [rbp+0C0h+var_128]
0x18023cdd8  mov     [rsp+1C0h+var_168], rax
0x18023cddd  lea     rax, [rbp+0C0h+var_124]
0x18023cde1  mov     [rsp+1C0h+var_170], rax
0x18023cde6  lea     rax, [rbp+0C0h+var_138]
0x18023cdea  mov     [rsp+1C0h+var_178], rax
0x18023cdef  lea     rax, [rsp+1C0h+var_14C]
0x18023cdf4  mov     [rsp+1C0h+var_180], rax
0x18023cdf9  lea     rax, [rbp+0C0h+var_130]
0x18023cdfd  mov     [rsp+1C0h+var_188], rax
0x18023ce02  lea     rax, [rbp+0C0h+var_120]
0x18023ce06  mov     [rsp+1C0h+var_190], rax
0x18023ce0b  lea     rax, [rbp+0C0h+var_118]
0x18023ce0f  mov     [rsp+1C0h+var_198], rax
0x18023ce14  lea     rax, [rbp+0C0h+Uuid]
0x18023ce18  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18023ce1d  lea     rdx, unk_1803437D8
0x18023ce24  mov     rcx, r8
0x18023ce27  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18023ce2c  mov     rcx, [rbp+0C0h+var_140]
0x18023ce30  movups  xmm0, xmmword ptr [rcx]
0x18023ce33  movdqu  [rbp+0C0h+var_100], xmm0
0x18023ce38  mov     eax, [rcx+14h]
0x18023ce3b  mov     dword ptr [rbp+0C0h+var_F0+4], eax
0x18023ce3e  movzx   eax, word ptr [rcx+10h]
0x18023ce42  mov     word ptr [rbp+0C0h+var_F0], ax
0x18023ce46  mov     r8d, [rcx+14h]; Size
0x18023ce4a  mov     rdx, rsi; Src
0x18023ce4d  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18023ce51  call    memcpy_0
0x18023ce56  mov     dword ptr [rbp+0C0h+var_E0+8], r14d
0x18023ce5a  mov     dword ptr [rbp+0C0h+var_E0+0Ch], r15d
0x18023ce5e  mov     [rbp+0C0h+var_D0], r12d
0x18023ce62  lea     rax, [rbp+0C0h+var_E0]
0x18023ce66  mov     qword ptr [rbp+0C0h+var_F0+8], rax
0x18023ce6a  mov     eax, [r13+58h]
0x18023ce6e  cmp     qword ptr [rbx+18h], 7
0x18023ce73  jbe     short loc_18023CE7A
0x18023ce75  mov     rcx, [rbx]
0x18023ce78  jmp     short loc_18023CE7D
0x18023ce7a  mov     rcx, rbx
0x18023ce7d  lea     rdx, [rbp+0C0h+var_70]
0x18023ce81  mov     [rsp+1C0h+var_198], rdx
0x18023ce86  mov     [rsp+1C0h+var_1A0], eax
0x18023ce8a  lea     r9, [rbp+0C0h+var_100]
0x18023ce8e  lea     r8, VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID
0x18023ce95  mov     rdx, rdi
0x18023ce98  call    cs:__imp_NetMgmtUpdateVirtualSwitchPortProperty
0x18023ce9e  mov     esi, eax
0x18023cea0  test    eax, eax
0x18023cea2  js      loc_18023D060
0x18023cea8  jmp     loc_18023CFB0
0x18023cead  xorps   xmm0, xmm0
0x18023ceb0  movups  xmmword ptr [rbp+0C0h+Uuid.Data1], xmm0
0x18023ceb4  lea     rcx, [rbp+0C0h+Uuid]; Uuid
0x18023ceb8  call    cs:__imp_UuidCreate
0x18023cebe  movups  xmm0, xmmword ptr [rbp+0C0h+Uuid.Data1]
0x18023cec2  movdqu  [rbp+0C0h+var_100], xmm0
0x18023cec7  call    ?Provider@HNSTraceProvider@@SAPEBU_tlgProvider_t@@XZ; HNSTraceProvider::Provider(void)
0x18023cecc  mov     ecx, [rax]
0x18023cece  cmp     ecx, 5
0x18023ced1  jbe     short loc_18023CF1C
0x18023ced3  lea     rcx, [rbp+0C0h+var_100]
0x18023ced7  mov     qword ptr [rbp+0C0h+Uuid.Data1], rcx
0x18023cedb  mov     [rbp+0C0h+var_118], rdi
0x18023cedf  cmp     qword ptr [rbx+18h], 7
0x18023cee4  jbe     short loc_18023CEEB
0x18023cee6  mov     rcx, [rbx]
0x18023cee9  jmp     short loc_18023CEEE
0x18023ceeb  mov     rcx, rbx
0x18023ceee  mov     [rbp+0C0h+var_120], rcx
0x18023cef2  lea     rcx, [rbp+0C0h+Uuid]
0x18023cef6  mov     [rsp+1C0h+var_190], rcx
0x18023cefb  lea     rcx, [rbp+0C0h+var_118]
0x18023ceff  mov     [rsp+1C0h+var_198], rcx
0x18023cf04  lea     rcx, [rbp+0C0h+var_120]
0x18023cf08  mov     qword ptr [rsp+1C0h+var_1A0], rcx
0x18023cf0d  lea     rdx, byte_180343893
0x18023cf14  mov     rcx, rax
0x18023cf17  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x18023cf1c  xor     eax, eax
0x18023cf1e  mov     word ptr [rbp+0C0h+var_F0], ax
0x18023cf22  mov     dword ptr [rbp+0C0h+var_F0+4], 14h
0x18023cf29  mov     edx, 4D5h; unsigned int
0x18023cf2e  lea     rcx, aSwitchhelperCo; "SwitchHelper::ConfigureDefaultOffloadVa"...
0x18023cf35  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18023cf3a  mov     dword ptr [rbp+0C0h+var_E0], 200h
0x18023cf41  mov     qword ptr [rbp+0C0h+var_E0+4], 64h ; 'd'
0x18023cf49  mov     qword ptr [rbp+0C0h+var_E0+0Ch], 1
0x18023cf51  mov     edx, 4EEh; unsigned int
0x18023cf56  lea     rcx, aSwitchhelperCo; "SwitchHelper::ConfigureDefaultOffloadVa"...
0x18023cf5d  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x18023cf62  mov     dword ptr [rbp+0C0h+var_E0+8], r14d
0x18023cf66  mov     dword ptr [rbp+0C0h+var_E0+0Ch], r15d
0x18023cf6a  mov     [rbp+0C0h+var_D0], r12d
0x18023cf6e  lea     rax, [rbp+0C0h+var_E0]
0x18023cf72  mov     qword ptr [rbp+0C0h+var_F0+8], rax
0x18023cf76  mov     eax, [r13+58h]
0x18023cf7a  cmp     qword ptr [rbx+18h], 7
0x18023cf7f  jbe     short loc_18023CF86
0x18023cf81  mov     rcx, [rbx]
0x18023cf84  jmp     short loc_18023CF89
0x18023cf86  mov     rcx, rbx
0x18023cf89  lea     rdx, [rbp+0C0h+var_70]
0x18023cf8d  mov     [rsp+1C0h+var_198], rdx
0x18023cf92  mov     [rsp+1C0h+var_1A0], eax
0x18023cf96  lea     r9, [rbp+0C0h+var_100]
0x18023cf9a  lea     r8, VMS_PORT_POLICY_OFFLOAD_SETTINGS_GUID
0x18023cfa1  mov     rdx, rdi
0x18023cfa4  call    cs:__imp_NetMgmtAddVirtualSwitchPortProperty
0x18023cfaa  mov     esi, eax
0x18023cfac  test    eax, eax
0x18023cfae  js      short loc_18023CFF1
0x18023cfb0  mov     edx, 5A8h; unsigned int
0x18023cfb5  lea     rcx, aSwitchhelperSw_0; "SwitchHelper::SwitchPortConfigureIov"
0x18023cfbc  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x18023cfc1  nop
0x18023cfc2  mov     rcx, [rbp+0C0h+var_140]
0x18023cfc6  test    rcx, rcx
0x18023cfc9  jz      short loc_18023CFD1
0x18023cfcb  call    cs:__imp_NetMgmtPortPropertyFree
0x18023cfd1  mov     rcx, [rbp+0C0h+var_50]
0x18023cfd5  xor     rcx, rsp; StackCookie
0x18023cfd8  call    __security_check_cookie
0x18023cfdd  add     rsp, 188h
0x18023cfe4  pop     r15
0x18023cfe6  pop     r14
0x18023cfe8  pop     r13
0x18023cfea  pop     r12
0x18023cfec  pop     rdi
0x18023cfed  pop     rsi
0x18023cfee  pop     rbx
0x18023cfef  pop     rbp
0x18023cff0  retn
0x18023cff1  mov     edx, esi; int
0x18023cff3  lea     rcx, [rbp+0C0h+Uuid]; this
0x18023cff7  call    ??0HNSEventType@@QEAA@J@Z; HNSEventType::HNSEventType(long)
0x18023cffc  mov     rcx, rbx
0x18023cfff  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18023d004  mov     rdx, rax; unsigned __int16 *
0x18023d007  lea     rcx, [rbp+0C0h+var_B0]; this
0x18023d00b  call    ??0HNSEventType@@QEAA@PEBG@Z; HNSEventType::HNSEventType(ushort const *)
0x18023d010  mov     rdx, rdi; unsigned __int16 *
0x18023d013  lea     rcx, [rbp+0C0h+var_98]; this
0x18023d017  call    ??0HNSEventType@@QEAA@PEBG@Z; HNSEventType::HNSEventType(ushort const *)
0x18023d01c  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x18023d025  lea     r9, [rbp+0C0h+var_98]
0x18023d029  lea     r8, [rbp+0C0h+var_B0]
0x18023d02d  lea     rdx, [rbp+0C0h+Uuid]; this
0x18023d031  lea     rcx, VMSWITCH_PORT_CONFIGURE_IOV_FAILED; EventDescriptor
0x18023d038  call    ?EventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVHNSEventType@@ZZ; EventWrite(_EVENT_DESCRIPTOR const *,HNSEventType *,...)
0x18023d03d  mov     ecx, esi
0x18023d03f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18023d044  mov     r9d, eax; char *
0x18023d047  mov     rcx, [rbp+0C8h]; this
0x18023d04e  lea     r8, aOnecoreVmDvNet_71; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18023d055  mov     edx, 5A4h; void *
0x18023d05a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18023d060  mov     edx, esi; int
0x18023d062  lea     rcx, [rbp+0C0h+Uuid]; this
0x18023d066  call    ??0HNSEventType@@QEAA@J@Z; HNSEventType::HNSEventType(long)
0x18023d06b  mov     rcx, rbx
0x18023d06e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18023d073  mov     rdx, rax; unsigned __int16 *
0x18023d076  lea     rcx, [rbp+0C0h+var_B0]; this
0x18023d07a  call    ??0HNSEventType@@QEAA@PEBG@Z; HNSEventType::HNSEventType(ushort const *)
0x18023d07f  mov     rdx, rdi; unsigned __int16 *
0x18023d082  lea     rcx, [rbp+0C0h+var_98]; this
0x18023d086  call    ??0HNSEventType@@QEAA@PEBG@Z; HNSEventType::HNSEventType(ushort const *)
0x18023d08b  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x18023d094  lea     r9, [rbp+0C0h+var_98]
0x18023d098  lea     r8, [rbp+0C0h+var_B0]
  ... truncated ...
```
