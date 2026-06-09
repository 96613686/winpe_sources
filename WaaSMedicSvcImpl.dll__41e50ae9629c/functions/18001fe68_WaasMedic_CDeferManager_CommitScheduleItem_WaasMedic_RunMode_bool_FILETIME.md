# WaasMedic::CDeferManager::CommitScheduleItem(WaasMedic::RunMode,bool,_FILETIME *)

- ea: `0x18001fe68`
- end: `0x1800202d1`
- name: `?CommitScheduleItem@CDeferManager@WaasMedic@@AEAAJW4RunMode@2@_NPEAU_FILETIME@@@Z`
- size: `1129`
- prototype: `int __high(enum WaasMedic::RunMode, bool, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020718`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18001fe68`
- `0x180021190`
- `0x180029a30`
- `0x18002e81c`
- `0x18002ff7c`
- `0x1800301e0`
- `0x180030554`
- `0x180032984`
- `0x180032c94`
- `0x180032f6c`
- `0x18003300c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ffcc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002000f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020098`
- `OLEAUT32!__imp_SysFreeString` at `0x180020159`
- `OLEAUT32!__imp_SysFreeString` at `0x1800201a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002024e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffcc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002000f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020098`
- `OLEAUT32!__imp_SysFreeString` at `0x180020159`
- `OLEAUT32!__imp_SysFreeString` at `0x1800201a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002024e`

## string_xrefs

- `0x1800201de`: `Performs remediation work outside of normal runs.`
- `0x18001feeb`: `Attempted the schedule unknown run mode!`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::CDeferManager::CommitScheduleItem(
        __int64 a1,
        int a2,
        char a3,
        const struct _FILETIME *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // edi
  unsigned __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned __int16 **v13; // rcx
  int v14; // eax
  int updated; // eax
  __int64 v16; // rdx
  int XmlForScheduledTask; // edi
  __int64 v18; // rdx
  unsigned __int16 **v19; // rcx
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  unsigned __int16 **v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  const unsigned __int16 *v27; // rdx
  WaasMedic::CDeferManager *v28; // rcx
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // rdx
  int v32; // [rsp+20h] [rbp-89h]
  bool v33; // [rsp+40h] [rbp-69h] BYREF
  BSTR v34; // [rsp+48h] [rbp-61h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-59h] BYREF
  LPVOID ppv[2]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v37; // [rsp+68h] [rbp-41h]
  unsigned __int16 *v38[2]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v39; // [rsp+80h] [rbp-29h]
  unsigned __int16 *v40[2]; // [rsp+90h] [rbp-19h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-9h]
  unsigned __int16 v42[8]; // [rsp+B0h] [rbp+7h] BYREF
  _BYTE v43[26]; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v37 = 0;
  *(_OWORD *)ppv = 0;
  v7 = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\WaaSMedic");
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = a2 - 3;
    if ( v9 )
    {
      if ( v9 != 1 )
      {
        LogLevelW(2u, L"Attempted the schedule unknown run mode!");
        v8 = -2147418113;
        goto LABEL_70;
      }
      *(_OWORD *)v38 = 0;
      v39 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v38, L"DeferredWork", 12);
      if ( a3 )
      {
        *(_OWORD *)v42 = 0;
        memset(v43, 0, sizeof(v43));
        if ( !a4 )
        {
          v8 = -2147467261;
          v11 = 2147500035LL;
          v12 = 284;
LABEL_9:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
            (const char *)v11,
            v32);
LABEL_10:
          v13 = v38;
LABEL_44:
          std::wstring::~wstring(v13);
          goto LABEL_70;
        }
        v14 = WaasMedic::TimeHelper::FileTimeToString(v42, v10, a4);
        v8 = v14;
        if ( v14 < 0 )
        {
          v11 = (unsigned int)v14;
          v12 = 285;
          goto LABEL_9;
        }
        bstrString = 0;
        updated = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\WaaSMedic");
        v8 = updated;
        if ( updated < 0 )
        {
          v16 = 288;
          goto LABEL_15;
        }
        XmlForScheduledTask = WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(
                                (WaasMedic::TasksHelper *)ppv,
                                L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)");
        if ( XmlForScheduledTask < 0 )
        {
          v18 = 289;
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
            (const char *)(unsigned int)XmlForScheduledTask,
            v32);
          if ( bstrString )
            SysFreeString(bstrString);
          v19 = v38;
LABEL_50:
          std::wstring::~wstring(v19);
          v8 = XmlForScheduledTask;
          goto LABEL_70;
        }
        XmlForScheduledTask = WaasMedic::TasksHelper::CreateXmlForScheduledTask(
                                (__int64 *)ppv,
                                L"\\Microsoft\\Windows\\WaaSMedic\\DeferredWork",
                                (__int64)L"Performs deferred remediation  work.",
                                L"DeferralWork",
                                v42,
                                (__int64 *)L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)",
                                (__int64)&bstrString);
        if ( XmlForScheduledTask < 0 )
        {
          v18 = 296;
          goto LABEL_19;
        }
        v20 = (const unsigned __int16 *)v38;
        if ( *((_QWORD *)&v39 + 1) > 7u )
          v20 = v38[0];
        updated = WaasMedic::TasksHelper::CreateOrUpdateTask(
                    (WaasMedic::TasksHelper *)ppv,
                    v20,
                    bstrString,
                    L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)");
        v8 = updated;
        if ( updated < 0 )
        {
          v16 = 297;
LABEL_15:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
            (const char *)(unsigned int)updated,
            v32);
          if ( bstrString )
            SysFreeString(bstrString);
          goto LABEL_10;
        }
        if ( bstrString )
          SysFreeString(bstrString);
      }
      else
      {
        v33 = 0;
        v21 = (const unsigned __int16 *)v38;
        if ( *((_QWORD *)&v39 + 1) > 7u )
          v21 = v38[0];
        if ( (int)WaasMedic::TasksHelper::TaskExists((WaasMedic::TasksHelper *)ppv, v21, &v33) >= 0 && v33 )
        {
          v22 = (const unsigned __int16 *)v38;
          if ( *((_QWORD *)&v39 + 1) > 7u )
            v22 = v38[0];
          WaasMedic::TasksHelper::DisableTask((WaasMedic::TasksHelper *)ppv, v22);
        }
      }
      v23 = v38;
LABEL_69:
      std::wstring::~wstring(v23);
      v8 = 0;
      goto LABEL_70;
    }
    *(_OWORD *)v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v40, L"MaintenanceWork", 15);
    if ( a3 )
    {
      v34 = 0;
      v24 = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\WaaSMedic");
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = 255;
LABEL_41:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
          (const char *)(unsigned int)v24,
          v32);
        if ( v34 )
          SysFreeString(v34);
        v13 = v40;
        goto LABEL_44;
      }
      XmlForScheduledTask = WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(
                              (WaasMedic::TasksHelper *)ppv,
                              L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)");
      if ( XmlForScheduledTask < 0 )
      {
        v26 = 256;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
          (const char *)(unsigned int)XmlForScheduledTask,
          v32);
        if ( v34 )
          SysFreeString(v34);
        v19 = v40;
        goto LABEL_50;
      }
      XmlForScheduledTask = WaasMedic::TasksHelper::CreateXmlForScheduledTask(
                              (__int64 *)ppv,
                              L"\\Microsoft\\Windows\\WaaSMedic\\MaintenanceWork",
                              (__int64)L"Performs remediation work outside of normal runs.",
                              L"MaintenanceWork",
                              0,
                              (__int64 *)L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)",
                              (__int64)&v34);
      if ( XmlForScheduledTask < 0 )
      {
        v26 = 263;
        goto LABEL_47;
      }
      v27 = (const unsigned __int16 *)v40;
      if ( *((_QWORD *)&v41 + 1) > 7u )
        v27 = v40[0];
      v24 = WaasMedic::TasksHelper::CreateOrUpdateTask(
              (WaasMedic::TasksHelper *)ppv,
              v27,
              v34,
              L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)(A;;FRFX;;;BU)(A;;FRFX;;;AU)");
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = 264;
        goto LABEL_41;
      }
      v24 = WaasMedic::CDeferManager::SignalMaintenanceScheduled(v28);
      v8 = v24;
      if ( v24 < 0 )
      {
        v25 = 265;
        goto LABEL_41;
      }
      if ( v34 )
        SysFreeString(v34);
    }
    else
    {
      v33 = 0;
      v29 = (const unsigned __int16 *)v40;
      if ( *((_QWORD *)&v41 + 1) > 7u )
        v29 = v40[0];
      if ( (int)WaasMedic::TasksHelper::TaskExists((WaasMedic::TasksHelper *)ppv, v29, &v33) >= 0 && v33 )
      {
        v30 = (const unsigned __int16 *)v40;
        if ( *((_QWORD *)&v41 + 1) > 7u )
          v30 = v40[0];
        WaasMedic::TasksHelper::DisableTask((WaasMedic::TasksHelper *)ppv, v30);
      }
    }
    v23 = v40;
    goto LABEL_69;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF5,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\defermanager.cpp",
    (const char *)(unsigned int)v7,
    v32);
LABEL_70:
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  return v8;
}

```

## disassembly

```asm
0x18001fe68  mov     [rsp-8+arg_0], rbx
0x18001fe6d  mov     [rsp-8+arg_8], rsi
0x18001fe72  push    rbp
0x18001fe73  push    rdi
0x18001fe74  push    r14
0x18001fe76  lea     rbp, [rsp-47h]
0x18001fe7b  sub     rsp, 0F0h
0x18001fe82  mov     rax, cs:__security_cookie
0x18001fe89  xor     rax, rsp
0x18001fe8c  mov     [rbp+57h+var_20], rax
0x18001fe90  mov     rsi, r9
0x18001fe93  mov     r14b, r8b
0x18001fe96  mov     edi, edx
0x18001fe98  xor     eax, eax
0x18001fe9a  mov     [rbp+57h+var_98], rax
0x18001fe9e  xorps   xmm1, xmm1
0x18001fea1  movdqu  xmmword ptr [rbp+57h+ppv], xmm1
0x18001fea6  mov     word ptr [rbp+57h+var_98], ax
0x18001feaa  lea     rdx, aMicrosoftWindo_4; "Microsoft\\Windows\\WaaSMedic"
0x18001feb1  lea     rcx, [rbp+57h+ppv]; ppv
0x18001feb5  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x18001feba  mov     ebx, eax
0x18001febc  test    eax, eax
0x18001febe  jns     short loc_18001FEDD
0x18001fec0  mov     rcx, [rbp+5Fh]; this
0x18001fec4  mov     r9d, eax; char *
0x18001fec7  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x18001fece  mov     edx, 0F5h; void *
0x18001fed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fed8  jmp     loc_1800202A2
0x18001fedd  sub     edi, 3
0x18001fee0  jz      loc_1800200EA
0x18001fee6  cmp     edi, 1
0x18001fee9  jz      short loc_18001FF06
0x18001feeb  lea     rdx, aAttemptedTheSc; "Attempted the schedule unknown run mode"...
0x18001fef2  mov     ecx, 2; unsigned __int8
0x18001fef7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001fefc  mov     ebx, 8000FFFFh
0x18001ff01  jmp     loc_1800202A2
0x18001ff06  xorps   xmm0, xmm0
0x18001ff09  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18001ff0d  xorps   xmm1, xmm1
0x18001ff10  movdqu  [rbp+57h+var_80], xmm1
0x18001ff15  mov     r8d, 0Ch
0x18001ff1b  lea     rdx, aDeferredwork; "DeferredWork"
0x18001ff22  lea     rcx, [rbp+57h+var_90]
0x18001ff26  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ff2b  nop
0x18001ff2c  test    r14b, r14b
0x18001ff2f  jz      loc_1800200A0
0x18001ff35  xorps   xmm0, xmm0
0x18001ff38  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001ff3c  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18001ff40  movups  xmmword ptr [rbp+57h+var_40+0Ah], xmm0
0x18001ff44  test    rsi, rsi
0x18001ff47  jnz     short loc_18001FF70
0x18001ff49  mov     ebx, 80004003h
0x18001ff4e  mov     r9d, ebx; char *
0x18001ff51  mov     edx, 11Ch; void *
0x18001ff56  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x18001ff5d  mov     rcx, [rbp+5Fh]; this
0x18001ff61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff66  nop
0x18001ff67  lea     rcx, [rbp+57h+var_90]
0x18001ff6b  jmp     loc_180020164
0x18001ff70  mov     r8, rsi; struct _FILETIME *
0x18001ff73  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18001ff77  call    ?FileTimeToString@TimeHelper@WaasMedic@@SAJPEAG_KAEBU_FILETIME@@@Z; WaasMedic::TimeHelper::FileTimeToString(ushort *,unsigned __int64,_FILETIME const &)
0x18001ff7c  mov     ebx, eax
0x18001ff7e  test    eax, eax
0x18001ff80  jns     short loc_18001FF8C
0x18001ff82  mov     r9d, eax
0x18001ff85  mov     edx, 11Dh
0x18001ff8a  jmp     short loc_18001FF56
0x18001ff8c  mov     [rbp+57h+bstrString], 0
0x18001ff94  lea     rdx, aMicrosoftWindo_4; "Microsoft\\Windows\\WaaSMedic"
0x18001ff9b  lea     rcx, [rbp+57h+ppv]; ppv
0x18001ff9f  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x18001ffa4  mov     ebx, eax
0x18001ffa6  test    eax, eax
0x18001ffa8  jns     short loc_18001FFD4
0x18001ffaa  mov     edx, 120h; void *
0x18001ffaf  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x18001ffb6  mov     r9d, eax; char *
0x18001ffb9  mov     rcx, [rbp+5Fh]; this
0x18001ffbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffc2  nop
0x18001ffc3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001ffc7  test    rcx, rcx
0x18001ffca  jz      short loc_18001FF67
0x18001ffcc  call    cs:__imp_SysFreeString
0x18001ffd2  jmp     short loc_18001FF67
0x18001ffd4  lea     rbx, aDPAFaSyAFrfxLs; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x18001ffdb  mov     rdx, rbx; unsigned __int16 *
0x18001ffde  lea     rcx, [rbp+57h+ppv]; this
0x18001ffe2  call    ?SetTaskFolderSecurityDescriptor@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(ushort const *)
0x18001ffe7  mov     edi, eax
0x18001ffe9  test    eax, eax
0x18001ffeb  jns     short loc_18002001F
0x18001ffed  mov     edx, 121h; void *
0x18001fff2  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x18001fff9  mov     r9d, edi; char *
0x18001fffc  mov     rcx, [rbp+5Fh]; this
0x180020000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020005  nop
0x180020006  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002000a  test    rcx, rcx
0x18002000d  jz      short loc_180020016
0x18002000f  call    cs:__imp_SysFreeString
0x180020015  nop
0x180020016  lea     rcx, [rbp+57h+var_90]
0x18002001a  jmp     loc_1800201B4
0x18002001f  lea     rax, [rbp+57h+bstrString]
0x180020023  mov     [rsp+100h+var_D0], rax
0x180020028  mov     [rsp+100h+var_D8], rbx
0x18002002d  lea     rax, [rbp+57h+var_50]
0x180020031  mov     [rsp+100h+var_E0], rax
0x180020036  lea     r9, aDeferralwork; "DeferralWork"
0x18002003d  lea     r8, aPerformsDeferr; "Performs deferred remediation  work."
0x180020044  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\WaaSMedic\\Deferr"...
0x18002004b  lea     rcx, [rbp+57h+ppv]
0x18002004f  call    ?CreateXmlForScheduledTask@TasksHelper@WaasMedic@@QEAAJPEBG0000AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WaasMedic::TasksHelper::CreateXmlForScheduledTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180020054  mov     edi, eax
0x180020056  test    eax, eax
0x180020058  jns     short loc_180020061
0x18002005a  mov     edx, 128h
0x18002005f  jmp     short loc_18001FFF2
0x180020061  lea     rdx, [rbp+57h+var_90]
0x180020065  cmp     qword ptr [rbp+57h+var_80+8], 7
0x18002006a  cmova   rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18002006f  mov     r9, rbx; unsigned __int16 *
0x180020072  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x180020076  lea     rcx, [rbp+57h+ppv]; this
0x18002007a  call    ?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z; WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)
0x18002007f  mov     ebx, eax
0x180020081  test    eax, eax
0x180020083  jns     short loc_18002008F
0x180020085  mov     edx, 129h
0x18002008a  jmp     loc_18001FFAF
0x18002008f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180020093  test    rcx, rcx
0x180020096  jz      short loc_1800200E1
0x180020098  call    cs:__imp_SysFreeString
0x18002009e  jmp     short loc_1800200E1
0x1800200a0  mov     [rbp+57h+var_C0], 0
0x1800200a4  lea     rdx, [rbp+57h+var_90]
0x1800200a8  cmp     qword ptr [rbp+57h+var_80+8], 7
0x1800200ad  cmova   rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1800200b2  lea     r8, [rbp+57h+var_C0]; bool *
0x1800200b6  lea     rcx, [rbp+57h+ppv]; this
0x1800200ba  call    ?TaskExists@TasksHelper@WaasMedic@@QEAAJPEBGPEA_N@Z; WaasMedic::TasksHelper::TaskExists(ushort const *,bool *)
0x1800200bf  test    eax, eax
0x1800200c1  js      short loc_1800200E1
0x1800200c3  cmp     [rbp+57h+var_C0], 0
0x1800200c7  jz      short loc_1800200E1
0x1800200c9  lea     rdx, [rbp+57h+var_90]
0x1800200cd  cmp     qword ptr [rbp+57h+var_80+8], 7
0x1800200d2  cmova   rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1800200d7  lea     rcx, [rbp+57h+ppv]; this
0x1800200db  call    ?DisableTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::DisableTask(ushort const *)
0x1800200e0  nop
0x1800200e1  lea     rcx, [rbp+57h+var_90]
0x1800200e5  jmp     loc_18002029B
0x1800200ea  xorps   xmm0, xmm0
0x1800200ed  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800200f1  xorps   xmm1, xmm1
0x1800200f4  movdqu  [rbp+57h+var_60], xmm1
0x1800200f9  mov     r8d, 0Fh
0x1800200ff  lea     rdx, aMaintenancewor; "MaintenanceWork"
0x180020106  lea     rcx, [rbp+57h+var_70]
0x18002010a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002010f  nop
0x180020110  test    r14b, r14b
0x180020113  jz      loc_180020256
0x180020119  mov     [rbp+57h+var_B8], 0
0x180020121  lea     rdx, aMicrosoftWindo_4; "Microsoft\\Windows\\WaaSMedic"
0x180020128  lea     rcx, [rbp+57h+ppv]; ppv
0x18002012c  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x180020131  mov     ebx, eax
0x180020133  test    eax, eax
0x180020135  jns     short loc_18002016E
0x180020137  mov     edx, 0FFh; void *
0x18002013c  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x180020143  mov     r9d, eax; char *
0x180020146  mov     rcx, [rbp+5Fh]; this
0x18002014a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002014f  nop
0x180020150  mov     rcx, [rbp+57h+var_B8]; bstrString
0x180020154  test    rcx, rcx
0x180020157  jz      short loc_180020160
0x180020159  call    cs:__imp_SysFreeString
0x18002015f  nop
0x180020160  lea     rcx, [rbp+57h+var_70]; void *
0x180020164  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020169  jmp     loc_1800202A2
0x18002016e  lea     rbx, aDPAFaSyAFrfxLs; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x180020175  mov     rdx, rbx; unsigned __int16 *
0x180020178  lea     rcx, [rbp+57h+ppv]; this
0x18002017c  call    ?SetTaskFolderSecurityDescriptor@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(ushort const *)
0x180020181  mov     edi, eax
0x180020183  test    eax, eax
0x180020185  jns     short loc_1800201C0
0x180020187  mov     edx, 100h; void *
0x18002018c  mov     r9d, edi; char *
0x18002018f  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\waasmedic\\lib\\engin"...
0x180020196  mov     rcx, [rbp+5Fh]; this
0x18002019a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002019f  nop
0x1800201a0  mov     rcx, [rbp+57h+var_B8]; bstrString
0x1800201a4  test    rcx, rcx
0x1800201a7  jz      short loc_1800201B0
0x1800201a9  call    cs:__imp_SysFreeString
0x1800201af  nop
0x1800201b0  lea     rcx, [rbp+57h+var_70]; void *
0x1800201b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800201b9  mov     ebx, edi
0x1800201bb  jmp     loc_1800202A2
0x1800201c0  lea     rax, [rbp+57h+var_B8]
0x1800201c4  mov     [rsp+100h+var_D0], rax
0x1800201c9  mov     [rsp+100h+var_D8], rbx
0x1800201ce  mov     [rsp+100h+var_E0], 0
0x1800201d7  lea     r9, aMaintenancewor; "MaintenanceWork"
0x1800201de  lea     r8, aPerformsRemedi; "Performs remediation work outside of no"...
0x1800201e5  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\WaaSMedic\\Mainte"...
0x1800201ec  lea     rcx, [rbp+57h+ppv]
0x1800201f0  call    ?CreateXmlForScheduledTask@TasksHelper@WaasMedic@@QEAAJPEBG0000AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WaasMedic::TasksHelper::CreateXmlForScheduledTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800201f5  mov     edi, eax
0x1800201f7  test    eax, eax
0x1800201f9  jns     short loc_180020202
0x1800201fb  mov     edx, 107h
0x180020200  jmp     short loc_18002018C
0x180020202  lea     rdx, [rbp+57h+var_70]
0x180020206  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18002020b  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180020210  mov     r9, rbx; unsigned __int16 *
0x180020213  mov     r8, [rbp+57h+var_B8]; unsigned __int16 *
0x180020217  lea     rcx, [rbp+57h+ppv]; this
0x18002021b  call    ?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z; WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)
0x180020220  mov     ebx, eax
0x180020222  test    eax, eax
0x180020224  jns     short loc_180020230
0x180020226  mov     edx, 108h
0x18002022b  jmp     loc_18002013C
0x180020230  call    ?SignalMaintenanceScheduled@CDeferManager@WaasMedic@@QEAAJXZ; WaasMedic::CDeferManager::SignalMaintenanceScheduled(void)
0x180020235  mov     ebx, eax
0x180020237  test    eax, eax
0x180020239  jns     short loc_180020245
0x18002023b  mov     edx, 109h
0x180020240  jmp     loc_18002013C
0x180020245  mov     rcx, [rbp+57h+var_B8]; bstrString
0x180020249  test    rcx, rcx
0x18002024c  jz      short loc_180020297
0x18002024e  call    cs:__imp_SysFreeString
0x180020254  jmp     short loc_180020297
0x180020256  mov     [rbp+57h+var_C0], 0
0x18002025a  lea     rdx, [rbp+57h+var_70]
0x18002025e  cmp     qword ptr [rbp+57h+var_60+8], 7
0x180020263  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180020268  lea     r8, [rbp+57h+var_C0]; bool *
0x18002026c  lea     rcx, [rbp+57h+ppv]; this
0x180020270  call    ?TaskExists@TasksHelper@WaasMedic@@QEAAJPEBGPEA_N@Z; WaasMedic::TasksHelper::TaskExists(ushort const *,bool *)
0x180020275  test    eax, eax
0x180020277  js      short loc_180020297
0x180020279  cmp     [rbp+57h+var_C0], 0
0x18002027d  jz      short loc_180020297
0x18002027f  lea     rdx, [rbp+57h+var_70]
0x180020283  cmp     qword ptr [rbp+57h+var_60+8], 7
0x180020288  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18002028d  lea     rcx, [rbp+57h+ppv]; this
0x180020291  call    ?DisableTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::DisableTask(ushort const *)
0x180020296  nop
0x180020297  lea     rcx, [rbp+57h+var_70]; void *
0x18002029b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800202a0  xor     ebx, ebx
0x1800202a2  lea     rcx, [rbp+57h+ppv]; this
0x1800202a6  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x1800202ab  mov     eax, ebx
0x1800202ad  mov     rcx, [rbp+57h+var_20]
0x1800202b1  xor     rcx, rsp; StackCookie
0x1800202b4  call    __security_check_cookie
0x1800202b9  lea     r11, [rsp+100h+var_10]
0x1800202c1  mov     rbx, [r11+20h]
0x1800202c5  mov     rsi, [r11+28h]
0x1800202c9  mov     rsp, r11
0x1800202cc  pop     r14
0x1800202ce  pop     rdi
0x1800202cf  pop     rbp
0x1800202d0  retn
```
