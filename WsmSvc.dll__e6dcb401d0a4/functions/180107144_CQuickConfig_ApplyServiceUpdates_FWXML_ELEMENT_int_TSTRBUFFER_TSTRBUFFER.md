# CQuickConfig::ApplyServiceUpdates(_FWXML_ELEMENT *,int *,TSTRBUFFER *,TSTRBUFFER *)

- ea: `0x180107144`
- end: `0x180107661`
- name: `?ApplyServiceUpdates@CQuickConfig@@CAXPEAU_FWXML_ELEMENT@@PEAHPEAVTSTRBUFFER@@2@Z`
- size: `1309`
- prototype: `void __fastcall(struct _FWXML_ELEMENT *, int *, struct TSTRBUFFER *, struct TSTRBUFFER *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801af34c`
- `0x1801af9d4`

## callees

- `0x180031350`
- `0x180032f50`
- `0x1800339d0`
- `0x180033b40`
- `0x180033e10`
- `0x180035ee0`
- `0x180064250`
- `0x180084750`
- `0x180084a20`
- `0x1800a0cf0`
- `0x1800ce6a0`
- `0x180107144`
- `0x180107a60`
- `0x180112380`
- `0x1801adcec`
- `0x1801b2534`
- `0x1801b2970`
- `0x1801b2b74`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180107289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180107289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010728f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010733b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010728f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010733b`

## string_xrefs

- `0x1801071f5`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`
- `0x1801072bf`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`
- `0x18010740a`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`
- `0x1801073c2`: ` xmlns:`
- `0x1801073aa`: `ServiceSCM`
- `0x1801075df`: `ServiceSCM`
- `0x1801072ad`: `StartService`
- `0x180107540`: `StartService`
- `0x180107576`: `StartService`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CQuickConfig::ApplyServiceUpdates(
        struct _FWXML_ELEMENT *a1,
        int *a2,
        struct TSTRBUFFER *a3,
        struct TSTRBUFFER *a4)
{
  char *v5; // rdi
  wchar_t *SimpleContentEx2; // rbx
  int v7; // edx
  wchar_t *v8; // rbx
  void *v9[3]; // [rsp+50h] [rbp-B0h] BYREF
  TSTRBUFFER *v10; // [rsp+68h] [rbp-98h]
  SC_HANDLE v11[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v12[323]; // [rsp+90h] [rbp-70h] BYREF
  int v13; // [rsp+AA8h] [rbp+9A8h]

  v10 = a4;
  v9[2] = a3;
  v9[1] = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_8fa182c87f503a4a4bd64537254e78fc_Traceguids);
  CServiceManager::CServiceManager((CServiceManager *)v11, 0);
  v5 = (char *)a1 + 128;
  if ( (unsigned int)FwXmlFindChildElement(
                       (char *)a1 + 128,
                       56,
                       L"http://schemas.microsoft.com/wbem/wsman/1/config/service")
    && (unsigned int)FwXmlIsSimpleContent(0) )
  {
    SimpleContentEx2 = (wchar_t *)FwXmlGetSimpleContentEx2(0, v9, 2);
    if ( (unsigned int)StringCchEqualsCI(SimpleContentEx2, (wchar_t *)L"auto") )
    {
      v7 = 2;
    }
    else
    {
      if ( !(unsigned int)StringCchEqualsCI(SimpleContentEx2, (wchar_t *)L"delayedAuto") )
      {
        SetLastError(0x80338041);
LABEL_13:
        GetLastError();
        goto LABEL_14;
      }
      v7 = 3;
    }
    if ( (unsigned int)CServiceManager::SetStartType((__int64)v11, v7) )
      goto LABEL_14;
    goto LABEL_13;
  }
LABEL_14:
  if ( (unsigned int)FwXmlFindChildElement(v5, 56, L"http://schemas.microsoft.com/wbem/wsman/1/config/service") )
  {
    if ( (unsigned int)FwXmlIsSimpleContent(0) )
    {
      v8 = (wchar_t *)FwXmlGetSimpleContentEx2(0, v9, 2);
      if ( ((unsigned int)StringCchEqualsCI(v8, (wchar_t *)L"true")
         || (unsigned int)StringCchEqualsCI(v8, (wchar_t *)L"1"))
        && !(unsigned int)CServiceManager::StartServiceW((CServiceManager *)v11) )
      {
        GetLastError();
      }
    }
  }
  RBUFFER::RBUFFER((RBUFFER *)v12, 0);
  v13 = 0;
  v9[0] = 0;
  if ( (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"<") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"cfg") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L":") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"ServiceSCM") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L" xmlns:") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"cfg") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"=\"") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"http://schemas.microsoft.com/wbem/wsman/1/config/service") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"\"") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L">") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"</") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"cfg") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L":") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L"ServiceSCM") >= 0
    && (int)TSTRBUFFER::Append((TSTRBUFFER *)v12, L">") >= 0 )
  {
    TSTRBUFFER::Append(v10, v12[0]);
  }
  AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(v9);
  RBUFFER::~RBUFFER((RBUFFER *)v12);
  CServiceManager::~CServiceManager(v11);
}

```

## disassembly

```asm
0x180107144  push    rbp
0x180107146  push    rbx
0x180107147  push    rsi
0x180107148  push    rdi
0x180107149  push    r12
0x18010714b  push    r13
0x18010714d  push    r14
0x18010714f  lea     rbp, [rsp-9C0h]
0x180107157  sub     rsp, 0AC0h
0x18010715e  mov     rax, cs:__security_cookie
0x180107165  xor     rax, rsp
0x180107168  mov     [rbp+9F0h+var_40], rax
0x18010716f  mov     [rsp+0AF0h+var_A88], r9
0x180107174  mov     [rsp+0AF0h+var_A90], r8
0x180107179  mov     [rsp+0AF0h+var_A98], rdx
0x18010717e  mov     rbx, rcx
0x180107181  lea     rax, WPP_GLOBAL_Control
0x180107188  mov     rcx, cs:WPP_GLOBAL_Control
0x18010718f  cmp     rcx, rax
0x180107192  jz      short loc_1801071B2
0x180107194  test    dword ptr [rcx+1Ch], 200000h
0x18010719b  jz      short loc_1801071B2
0x18010719d  mov     edx, 1Fh
0x1801071a2  lea     r8, WPP_8fa182c87f503a4a4bd64537254e78fc_Traceguids
0x1801071a9  mov     rcx, [rcx+10h]
0x1801071ad  call    WPP_SF_
0x1801071b2  xor     edx, edx; bool
0x1801071b4  lea     rcx, [rsp+0AF0h+var_A80]; this
0x1801071b9  call    ??0CServiceManager@@QEAA@_N@Z; CServiceManager::CServiceManager(bool)
0x1801071be  nop
0x1801071bf  xor     r14d, r14d
0x1801071c2  xor     esi, esi
0x1801071c4  xor     r13d, r13d
0x1801071c7  mov     [rsp+0AF0h+var_AB0], esi
0x1801071cb  mov     [rsp+0AF0h+var_AA8], rsi
0x1801071d0  lea     rdi, [rbx+80h]
0x1801071d7  mov     [rsp+0AF0h+var_AC0], esi
0x1801071db  lea     rax, [rsp+0AF0h+var_AA8]
0x1801071e0  mov     [rsp+0AF0h+var_AC8], rax
0x1801071e5  lea     rax, aStarttype; "StartType"
0x1801071ec  mov     qword ptr [rsp+0AF0h+var_AD0], rax
0x1801071f1  lea     r9d, [r14+9]
0x1801071f5  lea     r8, aHttpSchemasMic_42; "http://schemas.microsoft.com/wbem/wsman"...
0x1801071fc  lea     edx, [rsi+38h]
0x1801071ff  mov     rcx, rdi
0x180107202  call    FwXmlFindChildElement
0x180107207  mov     r12, [rsp+0AF0h+var_AA8]
0x18010720c  test    eax, eax
0x18010720e  jz      loc_180107299
0x180107214  mov     rcx, r12
0x180107217  call    FwXmlIsSimpleContent
0x18010721c  test    eax, eax
0x18010721e  jnz     short loc_18010722A
0x180107220  mov     [rsp+0AF0h+var_AB0], 80338041h
0x180107228  jmp     short loc_180107299
0x18010722a  mov     r8d, 2
0x180107230  lea     rdx, [rsp+0AF0h+var_AA0]
0x180107235  mov     rcx, r12
0x180107238  call    FwXmlGetSimpleContentEx2
0x18010723d  mov     rbx, rax
0x180107240  lea     rdx, aAuto_0; "auto"
0x180107247  mov     rcx, rax; String1
0x18010724a  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x18010724f  test    eax, eax
0x180107251  jz      short loc_18010725A
0x180107253  mov     edx, 2
0x180107258  jmp     short loc_180107272
0x18010725a  lea     rdx, aDelayedauto; "delayedAuto"
0x180107261  mov     rcx, rbx; String1
0x180107264  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180107269  test    eax, eax
0x18010726b  jz      short loc_180107284
0x18010726d  mov     edx, 3
0x180107272  lea     rcx, [rsp+0AF0h+var_A80]
0x180107277  call    ?SetStartType@CServiceManager@@QEAAHW4StartType@1@@Z; CServiceManager::SetStartType(CServiceManager::StartType)
0x18010727c  mov     esi, eax
0x18010727e  test    eax, eax
0x180107280  jnz     short loc_180107299
0x180107282  jmp     short loc_18010728F
0x180107284  mov     ecx, 80338041h; dwErrCode
0x180107289  call    cs:__imp_SetLastError
0x18010728f  call    cs:__imp_GetLastError
0x180107295  mov     [rsp+0AF0h+var_AB0], eax
0x180107299  mov     [rsp+0AF0h+var_AA8], r13
0x18010729e  mov     [rsp+0AF0h+var_AC0], r13d
0x1801072a3  lea     rax, [rsp+0AF0h+var_AA8]
0x1801072a8  mov     [rsp+0AF0h+var_AC8], rax
0x1801072ad  lea     rax, aStartservice; "StartService"
0x1801072b4  mov     qword ptr [rsp+0AF0h+var_AD0], rax
0x1801072b9  mov     r9d, 0Ch
0x1801072bf  lea     r8, aHttpSchemasMic_42; "http://schemas.microsoft.com/wbem/wsman"...
0x1801072c6  lea     edx, [r9+2Ch]
0x1801072ca  mov     rcx, rdi
0x1801072cd  call    FwXmlFindChildElement
0x1801072d2  test    eax, eax
0x1801072d4  jz      short loc_180107344
0x1801072d6  mov     rcx, [rsp+0AF0h+var_AA8]
0x1801072db  call    FwXmlIsSimpleContent
0x1801072e0  test    eax, eax
0x1801072e2  jz      short loc_180107322
0x1801072e4  mov     r8d, 2
0x1801072ea  lea     rdx, [rsp+0AF0h+var_AA0]
0x1801072ef  mov     rcx, [rsp+0AF0h+var_AA8]
0x1801072f4  call    FwXmlGetSimpleContentEx2
0x1801072f9  mov     rbx, rax
0x1801072fc  lea     rdx, aTrue; "true"
0x180107303  mov     rcx, rax; String1
0x180107306  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x18010730b  test    eax, eax
0x18010730d  jnz     short loc_18010732A
0x18010730f  lea     rdx, a1; "1"
0x180107316  mov     rcx, rbx; String1
0x180107319  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x18010731e  test    eax, eax
0x180107320  jnz     short loc_18010732A
0x180107322  mov     r13d, 80338041h
0x180107328  jmp     short loc_180107344
0x18010732a  lea     rcx, [rsp+0AF0h+var_A80]; this
0x18010732f  call    ?StartServiceW@CServiceManager@@QEAAHXZ; CServiceManager::StartServiceW(void)
0x180107334  mov     r14d, eax
0x180107337  test    eax, eax
0x180107339  jnz     short loc_180107344
0x18010733b  call    cs:__imp_GetLastError
0x180107341  mov     r13d, eax
0x180107344  xor     edx, edx; unsigned int
0x180107346  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010734a  call    ??0RBUFFER@@QEAA@I@Z; RBUFFER::RBUFFER(uint)
0x18010734f  mov     [rbp+9F0h+var_48], 0
0x180107359  mov     [rsp+0AF0h+var_AA0], 0
0x180107362  lea     rdx, asc_1801D90C0; "<"
0x180107369  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010736d  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x180107372  test    eax, eax
0x180107374  js      loc_180107616
0x18010737a  lea     rdx, aCfg; "cfg"
0x180107381  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107385  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x18010738a  test    eax, eax
0x18010738c  js      loc_180107616
0x180107392  lea     rdx, asc_1801D90BC; ":"
0x180107399  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010739d  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801073a2  test    eax, eax
0x1801073a4  js      loc_180107616
0x1801073aa  lea     rdx, aServicescm; "ServiceSCM"
0x1801073b1  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801073b5  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801073ba  test    eax, eax
0x1801073bc  js      loc_180107616
0x1801073c2  lea     rdx, aXmlns; " xmlns:"
0x1801073c9  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801073cd  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801073d2  test    eax, eax
0x1801073d4  js      loc_180107616
0x1801073da  lea     rdx, aCfg; "cfg"
0x1801073e1  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801073e5  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801073ea  test    eax, eax
0x1801073ec  js      loc_180107616
0x1801073f2  lea     rdx, asc_1801D90C4; "=\""
0x1801073f9  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801073fd  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x180107402  test    eax, eax
0x180107404  js      loc_180107616
0x18010740a  lea     rdx, aHttpSchemasMic_42; "http://schemas.microsoft.com/wbem/wsman"...
0x180107411  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107415  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x18010741a  test    eax, eax
0x18010741c  js      loc_180107616
0x180107422  lea     rdx, asc_1801D90B8; "\""
0x180107429  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010742d  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x180107432  test    eax, eax
0x180107434  js      loc_180107616
0x18010743a  lea     rdx, asc_1801D2C04; ">"
0x180107441  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107445  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x18010744a  test    eax, eax
0x18010744c  js      loc_180107616
0x180107452  lea     rcx, aFailed; "failed"
0x180107459  lea     rdi, aSucceeded; "succeeded"
0x180107460  test    r12, r12
0x180107463  mov     r12, [rsp+0AF0h+var_A98]
0x180107468  jz      loc_180107656
0x18010746e  mov     rbx, rdi
0x180107471  xor     eax, eax
0x180107473  test    esi, esi
0x180107475  cmovz   rbx, rcx
0x180107479  jnz     short loc_18010747F
0x18010747b  mov     [r12], eax
0x18010747f  mov     [rsp+0AF0h+var_AC8], rax; struct _XML_ATTRIB *
0x180107484  mov     [rsp+0AF0h+var_AD0], eax; unsigned int
0x180107488  xor     r9d, r9d; int
0x18010748b  lea     r8, aCfg; "cfg"
0x180107492  lea     rdx, aStarttype; "StartType"
0x180107499  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010749d  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x1801074a2  test    eax, eax
0x1801074a4  js      short loc_1801074D0
0x1801074a6  xor     r8d, r8d; bool
0x1801074a9  mov     rdx, rbx; unsigned __int16 *
0x1801074ac  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801074b0  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x1801074b5  test    eax, eax
0x1801074b7  js      short loc_1801074D0
0x1801074b9  lea     r8, aCfg; "cfg"
0x1801074c0  lea     rdx, aStarttype; "StartType"
0x1801074c7  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801074cb  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x1801074d0  neg     esi
0x1801074d2  sbb     edx, edx
0x1801074d4  add     edx, 4033C471h; unsigned int
0x1801074da  test    eax, eax
0x1801074dc  js      loc_180107616
0x1801074e2  mov     r8d, [rsp+0AF0h+var_AB0]; unsigned int
0x1801074e7  mov     rsi, [rsp+0AF0h+var_A90]
0x1801074ec  mov     rcx, rsi; this
0x1801074ef  call    ?AppendMessage@CQuickConfig@@CAJPEAVTSTRBUFFER@@KK@Z; CQuickConfig::AppendMessage(TSTRBUFFER *,ulong,ulong)
0x1801074f4  test    eax, eax
0x1801074f6  js      loc_180107616
0x1801074fc  lea     rcx, aFailed; "failed"
0x180107503  cmp     [rsp+0AF0h+var_AA8], 0
0x180107509  jz      loc_1801075A3
0x18010750f  test    r14d, r14d
0x180107512  cmovz   rdi, rcx
0x180107516  jnz     short loc_180107520
0x180107518  mov     dword ptr [r12], 0
0x180107520  neg     r14d
0x180107523  sbb     ebx, ebx
0x180107525  mov     [rsp+0AF0h+var_AC8], 0; struct _XML_ATTRIB *
0x18010752e  mov     [rsp+0AF0h+var_AD0], 0; unsigned int
0x180107536  xor     r9d, r9d; int
0x180107539  lea     r8, aCfg; "cfg"
0x180107540  lea     rdx, aStartservice; "StartService"
0x180107547  lea     rcx, [rbp+9F0h+var_A60]; this
0x18010754b  call    ?AppendXmlStartElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0HKPEAU_XML_ATTRIB@@@Z; TSTRBUFFER::AppendXmlStartElemWithPrefix(ushort const *,ushort const *,int,ulong,_XML_ATTRIB *)
0x180107550  test    eax, eax
0x180107552  js      loc_180107616
0x180107558  xor     r8d, r8d; bool
0x18010755b  mov     rdx, rdi; unsigned __int16 *
0x18010755e  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107562  call    ?AppendEscapeXmlContent@TSTRBUFFER@@QEAAJPEBG_N@Z; TSTRBUFFER::AppendEscapeXmlContent(ushort const *,bool)
0x180107567  test    eax, eax
0x180107569  js      loc_180107616
0x18010756f  lea     r8, aCfg; "cfg"
0x180107576  lea     rdx, aStartservice; "StartService"
0x18010757d  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107581  call    ?AppendXmlEndElemWithPrefix@TSTRBUFFER@@QEAAJPEBG0@Z; TSTRBUFFER::AppendXmlEndElemWithPrefix(ushort const *,ushort const *)
0x180107586  test    eax, eax
0x180107588  js      loc_180107616
0x18010758e  mov     r8d, r13d; unsigned int
0x180107591  lea     edx, [rbx+4033C46Fh]; unsigned int
0x180107597  mov     rcx, rsi; this
0x18010759a  call    ?AppendMessage@CQuickConfig@@CAJPEAVTSTRBUFFER@@KK@Z; CQuickConfig::AppendMessage(TSTRBUFFER *,ulong,ulong)
0x18010759f  test    eax, eax
0x1801075a1  js      short loc_180107616
0x1801075a3  lea     rdx, asc_1801D90D4; "</"
0x1801075aa  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801075ae  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801075b3  test    eax, eax
0x1801075b5  js      short loc_180107616
0x1801075b7  lea     rdx, aCfg; "cfg"
0x1801075be  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801075c2  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801075c7  test    eax, eax
0x1801075c9  js      short loc_180107616
0x1801075cb  lea     rdx, asc_1801D90BC; ":"
0x1801075d2  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801075d6  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801075db  test    eax, eax
0x1801075dd  js      short loc_180107616
0x1801075df  lea     rdx, aServicescm; "ServiceSCM"
0x1801075e6  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801075ea  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x1801075ef  test    eax, eax
0x1801075f1  js      short loc_180107616
0x1801075f3  lea     rdx, asc_1801D2C04; ">"
0x1801075fa  lea     rcx, [rbp+9F0h+var_A60]; this
0x1801075fe  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x180107603  test    eax, eax
0x180107605  js      short loc_180107616
0x180107607  mov     rdx, [rbp+9F0h+var_A60]; unsigned __int16 *
0x18010760b  mov     rcx, [rsp+0AF0h+var_A88]; this
0x180107610  call    ?Append@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Append(ushort const *)
0x180107615  nop
0x180107616  lea     rcx, [rsp+0AF0h+var_AA0]; void *
0x18010761b  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180107620  nop
0x180107621  lea     rcx, [rbp+9F0h+var_A60]; this
0x180107625  call    ??1RBUFFER@@QEAA@XZ; RBUFFER::~RBUFFER(void)
0x18010762a  nop
0x18010762b  lea     rcx, [rsp+0AF0h+var_A80]; this
0x180107630  call    ??1CServiceManager@@QEAA@XZ; CServiceManager::~CServiceManager(void)
0x180107635  mov     rcx, [rbp+9F0h+var_40]
0x18010763c  xor     rcx, rsp; StackCookie
0x18010763f  call    __security_check_cookie
0x180107644  add     rsp, 0AC0h
0x18010764b  pop     r14
0x18010764d  pop     r13
0x18010764f  pop     r12
  ... truncated ...
```
