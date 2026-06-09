# WaasMedic::ResetRepairPlugin::PerformAction(void)

- ea: `0x180047580`
- end: `0x180047821`
- name: `?PerformAction@ResetRepairPlugin@WaasMedic@@UEAAJXZ`
- size: `673`
- prototype: `__int64 __fastcall(WaasMedic::ResetRepairPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f1c`
- `0x180001fac`
- `0x180003bb0`
- `0x180004708`
- `0x180016c9c`
- `0x18002543c`
- `0x180046ecc`
- `0x180047178`
- `0x180047580`
- `0x180047ea4`
- `0x18004815c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800475de`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800475de`

## string_xrefs

- `0x1800475ff`: `Failed to get host system Windows directory, Err=0x%08x`
- `0x1800475b1`: `ResetRepairPlugin: Perform Action`
- `0x1800477e4`: `ResetRepairPlugin: Action Completes. hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::ResetRepairPlugin::PerformAction(WaasMedic::ResetRepairPlugin *this)
{
  WaasMedic::ResetRepairPlugin *v2; // rcx
  signed int LastError; // eax
  signed int v4; // ebx
  const unsigned __int16 *v5; // rdx
  unsigned __int8 v6; // cl
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  int *v12; // rdx
  WaasMedic::ResetRepairPlugin *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // rdx
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  LogLevelW(4u, L"ResetRepairPlugin: Perform Action");
  memset_0(Buffer, 0, 0x20Au);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"Failed to get host system Windows directory, Err=0x%08x";
    goto LABEL_5;
  }
  v20 = 0;
  v4 = WaasMedic::ResetRepairPlugin::NeedRemediation(v2, Buffer, &v20);
  if ( v4 >= 0 )
  {
    if ( v20 )
    {
      v7 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v7 > 5u
        && (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v7 + 3) & 0x400000000000LL) == *((_QWORD *)v7 + 3) )
      {
        v21 = L"Remediation1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&dword_180089EB4,
          (_DWORD)v7,
          v8,
          (__int64)&v21);
      }
      v4 = WaasMedic::ResetRepairPlugin::RunRemediation(this, Buffer);
      v9 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v9 <= 5u
        || (*((_QWORD *)v9 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v9 + 3) & 0x400000000000LL) != *((_QWORD *)v9 + 3) )
      {
        goto LABEL_29;
      }
      v22[0] = L"Remediation1";
      v12 = &dword_180089EFC;
    }
    else
    {
      LogLevelW(5u, L"No need to run Remediation based on detection, checking Remediation2");
      v4 = WaasMedic::ResetRepairPlugin::NeedRemediation2(v13, Buffer, &v20);
      if ( v4 < 0 )
      {
        v5 = L"NeedRemediation2 failed. Err=0x%08x";
        goto LABEL_5;
      }
      if ( !v20 )
        goto LABEL_29;
      v14 = WaasMedic::TelemetryProvider::Provider();
      v17 = *(unsigned int *)v14;
      if ( (unsigned int)v17 > 5 )
      {
        v18 = *((_QWORD *)v14 + 3);
        v17 = *((_QWORD *)v14 + 2);
        if ( (v17 & 0x400000000000LL) != 0 )
        {
          v17 = v18 & 0x400000000000LL;
          if ( (v18 & 0x400000000000LL) == v18 )
          {
            v22[0] = L"Remediation2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v14,
              (unsigned int)&unk_180089E18,
              v15,
              v16,
              (__int64)v22);
          }
        }
      }
      v4 = WaasMedic::ResetRepairPlugin::RunRemediation2((WaasMedic::ResetRepairPlugin *)v17, Buffer);
      v9 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v9 <= 5u
        || (*((_QWORD *)v9 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v9 + 3) & 0x400000000000LL) != *((_QWORD *)v9 + 3) )
      {
LABEL_29:
        v5 = L"ResetRepairPlugin: Action Completes. hr = 0x%08x";
        v6 = 4;
        goto LABEL_30;
      }
      v22[0] = L"Remediation2";
      v12 = (int *)&unk_180089E60;
    }
    LODWORD(v21) = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (_DWORD)v12,
      v10,
      v11,
      (__int64)v22,
      (__int64)&v21);
    goto LABEL_29;
  }
  v5 = L"NeedRemediation failed. Err=0x%08x";
LABEL_5:
  v6 = 2;
LABEL_30:
  LogLevelW(v6, v5, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047580  mov     [rsp-8+arg_8], rbx
0x180047585  mov     [rsp-8+arg_10], rsi
0x18004758a  push    rbp
0x18004758b  push    rdi
0x18004758c  push    r14
0x18004758e  lea     rbp, [rsp-170h]
0x180047596  sub     rsp, 270h
0x18004759d  mov     rax, cs:__security_cookie
0x1800475a4  xor     rax, rsp
0x1800475a7  mov     [rbp+180h+var_20], rax
0x1800475ae  mov     rsi, rcx
0x1800475b1  lea     rdx, aResetrepairplu_1; "ResetRepairPlugin: Perform Action"
0x1800475b8  mov     ecx, 4; unsigned __int8
0x1800475bd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800475c2  xor     edx, edx; Val
0x1800475c4  lea     rcx, [rsp+280h+Buffer]; void *
0x1800475c9  mov     r8d, 20Ah; Size
0x1800475cf  call    memset_0
0x1800475d4  mov     edx, 104h; uSize
0x1800475d9  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x1800475de  call    cs:__imp_GetWindowsDirectoryW
0x1800475e4  xor     edi, edi
0x1800475e6  test    eax, eax
0x1800475e8  jnz     short loc_180047610
0x1800475ea  call    cs:__imp_GetLastError
0x1800475f0  mov     ebx, eax
0x1800475f2  test    eax, eax
0x1800475f4  jle     short loc_1800475FF
0x1800475f6  movzx   ebx, ax
0x1800475f9  or      ebx, 80070000h
0x1800475ff  lea     rdx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180047606  mov     ecx, 2
0x18004760b  jmp     loc_1800477F0
0x180047610  lea     r8, [rsp+280h+var_250]; bool *
0x180047615  mov     [rsp+280h+var_250], dil
0x18004761a  lea     rdx, [rsp+280h+Buffer]; unsigned __int16 *
0x18004761f  call    ?NeedRemediation@ResetRepairPlugin@WaasMedic@@AEAAJPEBGPEA_N@Z; WaasMedic::ResetRepairPlugin::NeedRemediation(ushort const *,bool *)
0x180047624  mov     ebx, eax
0x180047626  test    eax, eax
0x180047628  jns     short loc_180047633
0x18004762a  lea     rdx, aNeedremediatio; "NeedRemediation failed. Err=0x%08x"
0x180047631  jmp     short loc_180047606
0x180047633  cmp     [rsp+280h+var_250], dil
0x180047638  jz      loc_1800476F8
0x18004763e  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180047643  mov     r8, rax
0x180047646  lea     r14, aRemediation1; "Remediation1"
0x18004764d  mov     rdi, 400000000000h
0x180047657  mov     ecx, [rax]
0x180047659  cmp     ecx, 5
0x18004765c  jbe     short loc_180047694
0x18004765e  mov     rdx, [rax+18h]
0x180047662  mov     rcx, [rax+10h]
0x180047666  test    rdi, rcx
0x180047669  jz      short loc_180047694
0x18004766b  mov     rax, rdx
0x18004766e  and     rax, rdi
0x180047671  cmp     rax, rdx
0x180047674  jnz     short loc_180047694
0x180047676  lea     rax, [rsp+280h+var_248]
0x18004767b  mov     [rsp+280h+var_248], r14
0x180047680  lea     rdx, dword_180089EB4
0x180047687  mov     [rsp+280h+var_260], rax
0x18004768c  mov     rcx, r8
0x18004768f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047694  lea     rdx, [rsp+280h+Buffer]; unsigned __int16 *
0x180047699  mov     rcx, rsi; this
0x18004769c  call    ?RunRemediation@ResetRepairPlugin@WaasMedic@@AEAAJPEBG@Z; WaasMedic::ResetRepairPlugin::RunRemediation(ushort const *)
0x1800476a1  mov     ebx, eax
0x1800476a3  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800476a8  mov     ecx, [rax]
0x1800476aa  cmp     ecx, 5
0x1800476ad  jbe     loc_1800477E4
0x1800476b3  mov     rdx, [rax+18h]
0x1800476b7  mov     rcx, [rax+10h]
0x1800476bb  test    rdi, rcx
0x1800476be  jz      loc_1800477E4
0x1800476c4  mov     rcx, rdx
0x1800476c7  and     rcx, rdi
0x1800476ca  cmp     rcx, rdx
0x1800476cd  jnz     loc_1800477E4
0x1800476d3  lea     rcx, [rsp+280h+var_248]
0x1800476d8  mov     [rsp+280h+var_240], r14
0x1800476dd  mov     [rsp+280h+var_258], rcx
0x1800476e2  lea     rdx, dword_180089EFC
0x1800476e9  lea     rcx, [rsp+280h+var_240]
0x1800476ee  mov     [rsp+280h+var_260], rcx
0x1800476f3  jmp     loc_1800477D8
0x1800476f8  lea     rdx, aNoNeedToRunRem; "No need to run Remediation based on det"...
0x1800476ff  mov     ecx, 5; unsigned __int8
0x180047704  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047709  lea     r8, [rsp+280h+var_250]; bool *
0x18004770e  lea     rdx, [rsp+280h+Buffer]; unsigned __int16 *
0x180047713  call    ?NeedRemediation2@ResetRepairPlugin@WaasMedic@@AEAAJPEBGPEA_N@Z; WaasMedic::ResetRepairPlugin::NeedRemediation2(ushort const *,bool *)
0x180047718  mov     ebx, eax
0x18004771a  test    eax, eax
0x18004771c  jns     short loc_18004772A
0x18004771e  lea     rdx, aNeedremediatio_0; "NeedRemediation2 failed. Err=0x%08x"
0x180047725  jmp     loc_180047606
0x18004772a  cmp     [rsp+280h+var_250], dil
0x18004772f  jz      loc_1800477E4
0x180047735  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004773a  mov     rdi, 400000000000h
0x180047744  lea     rsi, aRemediation2; "Remediation2"
0x18004774b  mov     ecx, [rax]
0x18004774d  cmp     ecx, 5
0x180047750  jbe     short loc_180047788
0x180047752  mov     rdx, [rax+18h]
0x180047756  mov     rcx, [rax+10h]
0x18004775a  test    rdi, rcx
0x18004775d  jz      short loc_180047788
0x18004775f  mov     rcx, rdx
0x180047762  and     rcx, rdi
0x180047765  cmp     rcx, rdx
0x180047768  jnz     short loc_180047788
0x18004776a  lea     rcx, [rsp+280h+var_240]
0x18004776f  mov     [rsp+280h+var_240], rsi
0x180047774  mov     [rsp+280h+var_260], rcx
0x180047779  lea     rdx, unk_180089E18
0x180047780  mov     rcx, rax
0x180047783  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047788  lea     rdx, [rsp+280h+Buffer]; unsigned __int16 *
0x18004778d  call    ?RunRemediation2@ResetRepairPlugin@WaasMedic@@AEAAJPEBG@Z; WaasMedic::ResetRepairPlugin::RunRemediation2(ushort const *)
0x180047792  mov     ebx, eax
0x180047794  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180047799  mov     ecx, [rax]
0x18004779b  cmp     ecx, 5
0x18004779e  jbe     short loc_1800477E4
0x1800477a0  mov     rdx, [rax+18h]
0x1800477a4  mov     rcx, [rax+10h]
0x1800477a8  test    rdi, rcx
0x1800477ab  jz      short loc_1800477E4
0x1800477ad  mov     rcx, rdx
0x1800477b0  and     rcx, rdi
0x1800477b3  cmp     rcx, rdx
0x1800477b6  jnz     short loc_1800477E4
0x1800477b8  lea     rdx, [rsp+280h+var_248]
0x1800477bd  mov     [rsp+280h+var_240], rsi
0x1800477c2  mov     [rsp+280h+var_258], rdx
0x1800477c7  lea     rdx, [rsp+280h+var_240]
0x1800477cc  mov     [rsp+280h+var_260], rdx
0x1800477d1  lea     rdx, unk_180089E60
0x1800477d8  mov     rcx, rax
0x1800477db  mov     dword ptr [rsp+280h+var_248], ebx
0x1800477df  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800477e4  lea     rdx, aResetrepairplu_2; "ResetRepairPlugin: Action Completes. hr"...
0x1800477eb  mov     ecx, 4; unsigned __int8
0x1800477f0  mov     r8d, ebx
0x1800477f3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800477f8  mov     eax, ebx
0x1800477fa  mov     rcx, [rbp+180h+var_20]
0x180047801  xor     rcx, rsp; StackCookie
0x180047804  call    __security_check_cookie
0x180047809  lea     r11, [rsp+280h+var_10]
0x180047811  mov     rbx, [r11+28h]
0x180047815  mov     rsi, [r11+30h]
0x180047819  mov     rsp, r11
0x18004781c  pop     r14
0x18004781e  pop     rdi
0x18004781f  pop     rbp
0x180047820  retn
```
