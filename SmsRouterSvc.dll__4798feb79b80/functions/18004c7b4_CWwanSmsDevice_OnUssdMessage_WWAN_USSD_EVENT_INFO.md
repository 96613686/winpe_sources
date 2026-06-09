# CWwanSmsDevice::OnUssdMessage(WWAN_USSD_EVENT_INFO *)

- ea: `0x18004c7b4`
- end: `0x18004caed`
- name: `?OnUssdMessage@CWwanSmsDevice@@AEAAXPEAUWWAN_USSD_EVENT_INFO@@@Z`
- size: `825`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this, struct WWAN_USSD_EVENT_INFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004cb00`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180006c84`
- `0x18000cf90`
- `0x18004a7a0`
- `0x18004c7b4`
- `0x180051420`
- `0x180051628`
- `0x180058280`
- `0x18005a16c`
- `0x180065278`
- `0x18006adac`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c977`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c977`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cab9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cab9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004c9b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004c9b4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004c9e4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004c9e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CWwanSmsDevice::OnUssdMessage(CWwanSmsDevice *this, struct WWAN_USSD_EVENT_INFO *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r8
  OLECHAR *v7; // rbx
  const unsigned __int16 *v8; // rcx
  HRESULT v9; // edi
  __int64 v10; // r8
  struct _SPerIMSIConfig *PSPerIMSIConfig; // r9
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  LPVOID ppv; // [rsp+40h] [rbp-69h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-61h] BYREF
  const OLECHAR *v17; // [rsp+50h] [rbp-59h] BYREF
  struct _FILETIME FileTime[2]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v19; // [rsp+68h] [rbp-41h]
  __int128 v20; // [rsp+70h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int16 *v22[2]; // [rsp+90h] [rbp-19h] BYREF
  __m128i v23; // [rsp+A0h] [rbp-9h]
  unsigned __int16 *v24[2]; // [rsp+B0h] [rbp+7h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+D0h] [rbp+27h] BYREF

  if ( !a2 || *(_QWORD *)a2 )
    return;
  LogSmsRouterInfo("CWwanSmsDevice::OnUssdMessage", 0x49Du, "SmsRouter received Ussd Notification.");
  if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, (const EVENT_DESCRIPTOR *)UssdReceivedEvent, v5, 1u, &v26);
  *(_OWORD *)v24 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v24[0]) = 0;
  *(_QWORD *)&SystemTime.wYear = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  *(_QWORD *)&SystemTime.wHour = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  std::wstring::operator=((__int64)v24, (_QWORD *)this + 68, v6);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 8LL))((char *)this + 32);
  v7 = 0;
  bstrString = 0;
  *(_OWORD *)v22 = 0;
  v23 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  ppv = 0;
  v8 = (const unsigned __int16 *)v24;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = v24[0];
  if ( *((_BYTE *)a2 + 13) )
  {
    PSPerIMSIConfig = SmsEncodingHelper::GetPSPerIMSIConfig(v8);
    if ( *((_BYTE *)a2 + 12) == 15 )
    {
      v12 = Decode7bitDataWithCodePage(
              (char *)a2 + 14,
              (unsigned int)(8 * *((unsigned __int8 *)a2 + 13) / 7),
              0,
              *((unsigned int *)PSPerIMSIConfig + 12),
              v22,
              0);
    }
    else
    {
      if ( *((_BYTE *)a2 + 12) != 0xF8 )
      {
        v9 = -2147467263;
        goto LABEL_18;
      }
      v12 = DecodeUcs2GsmData((char *)a2 + 14, *((unsigned __int8 *)a2 + 13), v10, v22);
    }
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = (const unsigned __int16 *)v22;
      if ( v23.m128i_i64[1] > 7uLL )
        v13 = v22[0];
      ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v13);
      v9 = CoCreateInstance(&CLSID_ProvisioningEngine, 0, 0x17u, &IID_IProvisioningNotificationProcessor, &ppv);
      v7 = bstrString;
      goto LABEL_19;
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_18:
  LogSmsRouterError("CWwanSmsDevice::OnUssdMessage", 0x4B5u, v9, "Failed to decode USSD message");
LABEL_19:
  if ( v9 < 0 )
  {
    LogSmsRouterError("CWwanSmsDevice::OnUssdMessage", 0x4D2u, v9, "Failed to instantiate provisioning engine");
  }
  else
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v20 = 0;
    *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
    v19 = 0;
    v17 = &LocaleName;
    SystemTimeToFileTime(&SystemTime, FileTime);
    FileTime[1] = (struct _FILETIME)v7;
    v19 = 0x100000000LL;
    v14 = (*(__int64 (__fastcall **)(LPVOID, char *, const OLECHAR **, __int128 *))(*(_QWORD *)ppv + 24LL))(
            ppv,
            (char *)this + 152,
            &v17,
            &v20);
    if ( v14 < 0 )
    {
      LogSmsRouterError(
        "CWwanSmsDevice::OnUssdMessage",
        0x4CDu,
        v14,
        "Provisioning Engine failed to process ussd notification");
    }
    else
    {
      LogSmsRouterInfo(
        "CWwanSmsDevice::OnUssdMessage",
        0x4C7u,
        "SmsRouter successfully called ProcessNotification for Ussd");
      v26 = *(struct _EVENT_DATA_DESCRIPTOR *)((char *)this + 152);
      CSebHelper::PublishOperatorNotification(&v26, v7, 2, 0, 0, 0, 0);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  std::wstring::~wstring((char **)v22);
  SysFreeString(v7);
  std::wstring::~wstring((char **)v24);
}

```

## disassembly

```asm
0x18004c7b4  test    rdx, rdx
0x18004c7b7  jz      locret_18004CAEC
0x18004c7bd  mov     [rsp-8+arg_10], rbx
0x18004c7c2  mov     [rsp-8+arg_18], rsi
0x18004c7c7  push    rbp
0x18004c7c8  push    rdi
0x18004c7c9  push    r15
0x18004c7cb  lea     rbp, [rsp-47h]
0x18004c7d0  sub     rsp, 0F0h
0x18004c7d7  mov     rax, cs:__security_cookie
0x18004c7de  xor     rax, rsp
0x18004c7e1  mov     [rbp+57h+var_20], rax
0x18004c7e5  mov     rdi, rdx
0x18004c7e8  mov     rsi, rcx
0x18004c7eb  cmp     dword ptr [rdx], 0
0x18004c7ee  jnz     loc_18004CAC9
0x18004c7f4  cmp     dword ptr [rdx+4], 0
0x18004c7f8  jnz     loc_18004CAC9
0x18004c7fe  lea     r8, aSmsrouterRecei; "SmsRouter received Ussd Notification."
0x18004c805  mov     edx, 49Dh; unsigned int
0x18004c80a  lea     r15, aCwwansmsdevice_6; "CWwanSmsDevice::OnUssdMessage"
0x18004c811  mov     rcx, r15; char *
0x18004c814  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004c819  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 1
0x18004c820  jz      short loc_18004C83D
0x18004c822  lea     rax, [rbp+57h+var_30]
0x18004c826  mov     [rsp+100h+ppv], rax
0x18004c82b  mov     r9d, 1
0x18004c831  lea     rdx, UssdReceivedEvent
0x18004c838  call    McGenEventWrite_EventWriteTransfer
0x18004c83d  xorps   xmm0, xmm0
0x18004c840  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18004c844  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004c84c  movdqu  [rbp+57h+var_40], xmm1
0x18004c851  xor     eax, eax
0x18004c853  mov     word ptr [rbp+57h+var_50], ax
0x18004c857  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004c85e  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x18004c862  lea     rbx, [rsi+20h]
0x18004c866  mov     qword ptr [rbp+57h+SystemTime.wHour], rbx
0x18004c86a  mov     rax, [rbx]
0x18004c86d  mov     rcx, rbx
0x18004c870  mov     rax, [rax]
0x18004c873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c878  nop
0x18004c879  lea     rdx, [rsi+220h]
0x18004c880  lea     rcx, [rbp+57h+var_50]
0x18004c884  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004c889  nop
0x18004c88a  mov     rax, [rbx]
0x18004c88d  mov     rcx, rbx
0x18004c890  mov     rax, [rax+8]
0x18004c894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c899  nop
0x18004c89a  xor     ebx, ebx
0x18004c89c  mov     [rbp+57h+bstrString], rbx
0x18004c8a0  xorps   xmm0, xmm0
0x18004c8a3  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18004c8a7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004c8af  movdqu  [rbp+57h+var_60], xmm1
0x18004c8b4  xor     eax, eax
0x18004c8b6  mov     word ptr [rbp+57h+var_70], ax
0x18004c8ba  mov     [rbp+57h+var_C0], rax
0x18004c8be  lea     rcx, [rbp+57h+var_50]
0x18004c8c2  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18004c8c7  cmova   rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18004c8cc  cmp     [rdi+0Dh], al
0x18004c8cf  jnz     short loc_18004C8DB
0x18004c8d1  mov     edi, 80070057h
0x18004c8d6  jmp     loc_18004C98A
0x18004c8db  call    ?GetPSPerIMSIConfig@SmsEncodingHelper@@SAPEAU_SPerIMSIConfig@@PEBG@Z; SmsEncodingHelper::GetPSPerIMSIConfig(ushort const *)
0x18004c8e0  mov     r9, rax
0x18004c8e3  cmp     byte ptr [rdi+0Ch], 0Fh
0x18004c8e7  jnz     short loc_18004C926
0x18004c8e9  movzx   ecx, byte ptr [rdi+0Dh]
0x18004c8ed  shl     ecx, 3
0x18004c8f0  mov     eax, 92492493h
0x18004c8f5  imul    ecx
0x18004c8f7  add     edx, ecx
0x18004c8f9  sar     edx, 2
0x18004c8fc  mov     eax, edx
0x18004c8fe  shr     eax, 1Fh
0x18004c901  add     edx, eax
0x18004c903  lea     rcx, [rdi+0Eh]
0x18004c907  mov     dword ptr [rsp+100h+var_D8], 0
0x18004c90f  lea     rax, [rbp+57h+var_70]
0x18004c913  mov     [rsp+100h+ppv], rax
0x18004c918  mov     r9d, [r9+30h]
0x18004c91c  xor     r8d, r8d
0x18004c91f  call    ?Decode7bitDataWithCodePage@@YAJPEBEKKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Decode7bitDataWithCodePage(uchar const *,ulong,ulong,ulong,std::wstring &,ulong)
0x18004c924  jmp     short loc_18004C93D
0x18004c926  cmp     byte ptr [rdi+0Ch], 0F8h
0x18004c92a  jnz     short loc_18004C985
0x18004c92c  movzx   edx, byte ptr [rdi+0Dh]
0x18004c930  lea     rcx, [rdi+0Eh]
0x18004c934  lea     r9, [rbp+57h+var_70]
0x18004c938  call    ?DecodeUcs2GsmData@@YAJPEBEKPEAU_SPerIMSIConfig@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DecodeUcs2GsmData(uchar const *,ulong,_SPerIMSIConfig *,std::wstring &)
0x18004c93d  mov     edi, eax
0x18004c93f  test    eax, eax
0x18004c941  js      short loc_18004C98A
0x18004c943  lea     rdx, [rbp+57h+var_70]
0x18004c947  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18004c94c  cmova   rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18004c951  lea     rcx, [rbp+57h+bstrString]; this
0x18004c955  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18004c95a  lea     rax, [rbp+57h+var_C0]
0x18004c95e  mov     [rsp+100h+ppv], rax; ppv
0x18004c963  lea     r9, IID_IProvisioningNotificationProcessor; riid
0x18004c96a  xor     edx, edx; pUnkOuter
0x18004c96c  lea     r8d, [rdx+17h]; dwClsContext
0x18004c970  lea     rcx, CLSID_ProvisioningEngine; rclsid
0x18004c977  call    cs:__imp_CoCreateInstance
0x18004c97d  mov     edi, eax
0x18004c97f  mov     rbx, [rbp+57h+bstrString]
0x18004c983  jmp     short loc_18004C9A1
0x18004c985  mov     edi, 80004001h
0x18004c98a  lea     r9, aFailedToDecode_1; "Failed to decode USSD message"
0x18004c991  mov     r8d, edi; int
0x18004c994  mov     edx, 4B5h; unsigned int
0x18004c999  mov     rcx, r15; char *
0x18004c99c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004c9a1  test    edi, edi
0x18004c9a3  js      loc_18004CA7E
0x18004c9a9  xorps   xmm0, xmm0
0x18004c9ac  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18004c9b0  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18004c9b4  call    cs:__imp_GetLocalTime
0x18004c9ba  xorps   xmm0, xmm0
0x18004c9bd  movups  [rbp+57h+var_90], xmm0
0x18004c9c1  xorps   xmm1, xmm1
0x18004c9c4  movdqu  xmmword ptr [rbp+57h+FileTime.dwLowDateTime], xmm1
0x18004c9c9  mov     [rbp+57h+var_98], 0
0x18004c9d1  lea     rax, LocaleName
0x18004c9d8  mov     [rbp+57h+var_B0], rax
0x18004c9dc  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18004c9e0  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18004c9e4  call    cs:__imp_SystemTimeToFileTime
0x18004c9ea  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime+8], rbx
0x18004c9ee  mov     dword ptr [rbp+57h+var_98], 0
0x18004c9f5  mov     dword ptr [rbp+57h+var_98+4], 1
0x18004c9fc  mov     rcx, [rbp+57h+var_C0]
0x18004ca00  lea     rdi, [rsi+98h]
0x18004ca07  mov     rax, [rcx]
0x18004ca0a  lea     r9, [rbp+57h+var_90]
0x18004ca0e  lea     r8, [rbp+57h+var_B0]
0x18004ca12  mov     rdx, rdi
0x18004ca15  mov     rax, [rax+18h]
0x18004ca19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca1e  mov     rcx, r15; char *
0x18004ca21  test    eax, eax
0x18004ca23  js      short loc_18004CA6D
0x18004ca25  lea     r8, aSmsrouterSucce; "SmsRouter successfully called ProcessNo"...
0x18004ca2c  mov     edx, 4C7h; unsigned int
0x18004ca31  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004ca36  movups  xmm0, xmmword ptr [rdi]
0x18004ca39  movdqu  [rbp+57h+var_30], xmm0
0x18004ca3e  mov     [rsp+100h+var_D0], 0
0x18004ca46  mov     [rsp+100h+var_D8], 0
0x18004ca4f  mov     [rsp+100h+ppv], 0
0x18004ca58  xor     r9d, r9d
0x18004ca5b  lea     r8d, [r9+2]
0x18004ca5f  mov     rdx, rbx
0x18004ca62  lea     rcx, [rbp+57h+var_30]
0x18004ca66  call    ?PublishOperatorNotification@CSebHelper@@SAJU_GUID@@PEAGW4NotificationMessageType@@_N1PEBEI@Z; CSebHelper::PublishOperatorNotification(_GUID,ushort *,NotificationMessageType,bool,ushort *,uchar const *,uint)
0x18004ca6b  jmp     short loc_18004CA96
0x18004ca6d  lea     r9, aProvisioningEn; "Provisioning Engine failed to process u"...
0x18004ca74  mov     r8d, eax
0x18004ca77  mov     edx, 4CDh
0x18004ca7c  jmp     short loc_18004CA90
0x18004ca7e  lea     r9, aFailedToInstan; "Failed to instantiate provisioning engi"...
0x18004ca85  mov     r8d, edi; int
0x18004ca88  mov     edx, 4D2h; unsigned int
0x18004ca8d  mov     rcx, r15; char *
0x18004ca90  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004ca95  nop
0x18004ca96  mov     rcx, [rbp+57h+var_C0]
0x18004ca9a  test    rcx, rcx
0x18004ca9d  jz      short loc_18004CAAC
0x18004ca9f  mov     rax, [rcx]
0x18004caa2  mov     rax, [rax+10h]
0x18004caa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caab  nop
0x18004caac  lea     rcx, [rbp+57h+var_70]; void *
0x18004cab0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cab5  nop
0x18004cab6  mov     rcx, rbx; bstrString
0x18004cab9  call    cs:__imp_SysFreeString
0x18004cabf  nop
0x18004cac0  lea     rcx, [rbp+57h+var_50]; void *
0x18004cac4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cac9  mov     rcx, [rbp+57h+var_20]
0x18004cacd  xor     rcx, rsp; StackCookie
0x18004cad0  call    __security_check_cookie
0x18004cad5  lea     r11, [rsp+100h+var_10]
0x18004cadd  mov     rbx, [r11+30h]
0x18004cae1  mov     rsi, [r11+38h]
0x18004cae5  mov     rsp, r11
0x18004cae8  pop     r15
0x18004caea  pop     rdi
0x18004caeb  pop     rbp
0x18004caec  retn
```
