# Microsoft::Diagnostics::Tracer::StartTracingImpl(Microsoft::Diagnostics::ITraceProfileDef const &,bool,bool &)

- ea: `0x180047c48`
- end: `0x18004824e`
- name: `?StartTracingImpl@Tracer@Diagnostics@Microsoft@@AEAAJAEBVITraceProfileDef@23@_NAEA_N@Z`
- size: `1542`
- prototype: `__int64 __fastcall(OLECHAR *this, const struct Microsoft::Diagnostics::ITraceProfileDef *, char, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049288`

## callees

- `0x18001b374`
- `0x18002b7fc`
- `0x18002df00`
- `0x180047c48`
- `0x180048254`
- `0x1800482ac`
- `0x1800482dc`
- `0x180048624`
- `0x180048c54`
- `0x180064e8c`
- `0x180133e1c`
- `0x1801d19d4`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180047cfc`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180047d9c`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180047cfc`
- `WindowsPerformanceRecorderControl!WPRCCreateInstanceUnderInstanceName` at `0x180047d9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180047edd`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f07`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f17`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f22`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f65`
- `OLEAUT32!__imp_SysFreeString` at `0x180048061`
- `OLEAUT32!__imp_SysFreeString` at `0x180047edd`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f07`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f17`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f22`
- `OLEAUT32!__imp_SysFreeString` at `0x180047f65`
- `OLEAUT32!__imp_SysFreeString` at `0x180048061`

## string_xrefs

- `0x180047ec1`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180047f44`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180048016`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180048045`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x180048085`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x1800480b5`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x1800480e4`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x18004811e`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x18004816e`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x1800481b3`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`
- `0x18004820b`: `onecore\base\telemetry\utc\service\scenarios\tracing\tracer.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Tracer::StartTracingImpl(
        OLECHAR *this,
        const struct Microsoft::Diagnostics::ITraceProfileDef *a2,
        char a3,
        bool *a4)
{
  int CurrentTraceProfileCollection; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  _QWORD *v10; // r14
  char *v11; // rdi
  char *v12; // rdx
  _QWORD *bstr; // rax
  int v14; // esi
  _QWORD *v15; // rsi
  _QWORD *v16; // rax
  int v17; // edi
  OLECHAR *v18; // rax
  _QWORD *v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // edi
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  OLECHAR *v30; // rcx
  __int64 result; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // edi
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  int v43; // eax
  unsigned int v44; // edi
  __int64 v45; // rdx
  int v46; // [rsp+20h] [rbp-88h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-78h] BYREF
  BSTR v48[3]; // [rsp+40h] [rbp-68h] BYREF
  char v49; // [rsp+58h] [rbp-50h]
  _BYTE v50[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v48[2] = this;
  v49 = 1;
  *(_BYTE *)this = a3;
  *a4 = 0;
  *((_BYTE *)this + 176) = 0;
  try
  {
    CurrentTraceProfileCollection = Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(
                                      (Microsoft::Diagnostics::Tracer *)this,
                                      1);
    v9 = CurrentTraceProfileCollection;
    if ( CurrentTraceProfileCollection != -984076288 )
    {
      if ( CurrentTraceProfileCollection < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)CurrentTraceProfileCollection,
          v46);
        LOBYTE(v32) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v32);
        return v9;
      }
      *a4 = 1;
      return 0;
    }
    v10 = this + 100;
    wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(this + 100);
    wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(this + 100);
    v11 = (char *)(this + 48);
    if ( *((_QWORD *)this + 15) <= 7u )
      v12 = (char *)(this + 48);
    else
      v12 = *(char **)v11;
    bstr = (_QWORD *)wil::make_bstr(v48, v12);
    v14 = WPRCCreateInstanceUnderInstanceName(*bstr, &GUID_b98b53f3_83ba_4837_8946_e886be8d4003, 0, 1);
    if ( v48[0] )
      SysFreeString(v48[0]);
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
        (const char *)(unsigned int)v14,
        (int)&GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a);
      LOBYTE(v38) = 0;
      Microsoft::Diagnostics::Tracer::CancelTracing(this, v38);
      result = (unsigned int)v14;
    }
    else
    {
      v15 = this + 104;
      if ( *((_QWORD *)this + 26) )
      {
        wil::com_ptr_t<IProfile,wil::err_exception_policy>::query<WindowsPerformanceRecorder::IProfileElement>(
          this + 104,
          v48);
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v48[0] + 32LL))(v48[0]);
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v48);
      }
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(this + 104);
      wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(this + 104);
      if ( *((_QWORD *)this + 15) > 7u )
        v11 = *(char **)v11;
      v16 = (_QWORD *)wil::make_bstr(v48, v11);
      v17 = WPRCCreateInstanceUnderInstanceName(*v16, &GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4, 0, 1);
      if ( v48[0] )
        SysFreeString(v48[0]);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x238,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v17,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        LOBYTE(v37) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v37);
        return (unsigned int)v17;
      }
      v18 = (OLECHAR *)((char *)a2 + 32);
      if ( *((_QWORD *)a2 + 7) > 0xFu )
        v18 = *(OLECHAR **)v18;
      v48[0] = v18;
      v48[1] = *((BSTR *)a2 + 6);
      v19 = (_QWORD *)Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(v50, v48);
      if ( v19[3] > 7u )
        v19 = (_QWORD *)*v19;
      wil::make_bstr(bstrString, v19);
      std::wstring::_Tidy_deallocate(v50);
      v20 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*v15 + 208LL))(*v15, bstrString[0]);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v20,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        if ( bstrString[0] )
          SysFreeString(bstrString[0]);
        goto LABEL_46;
      }
      v22 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v15 + 152LL))(*v15, (char *)this + 160);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
          (const char *)(unsigned int)v22,
          (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(bstrString);
        LOBYTE(v39) = 0;
        Microsoft::Diagnostics::Tracer::CancelTracing(this, v39);
        result = v23;
      }
      else
      {
        v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v10 + 56LL))(*v10, *v15, 0xFFFFFFFFLL);
        v26 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
            (const char *)(unsigned int)v24,
            (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(bstrString);
          LOBYTE(v40) = 0;
          Microsoft::Diagnostics::Tracer::CancelTracing(this, v40);
          result = v26;
        }
        else
        {
          if ( !*((_BYTE *)this + 1) )
          {
            v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 23) + 72LL))(
                    *((_QWORD *)this + 23),
                    *v10);
            v21 = v27;
            if ( v27 < 0 && v27 != -984076287 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x243,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                (const char *)(unsigned int)v27,
                (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
              v30 = bstrString[0];
              if ( bstrString[0] )
                goto LABEL_28;
              goto LABEL_46;
            }
          }
          if ( !*(_BYTE *)this && !*((_BYTE *)this + 1) )
            goto LABEL_26;
          v48[0] = 0;
          if ( (unsigned __int8)wil::com_ptr_t<IControlManager,wil::err_exception_policy>::try_query_to(
                                  this + 92,
                                  v25,
                                  v48) )
          {
            v33 = *((_QWORD *)this + 25);
            v34 = *(_QWORD *)v48[0];
            if ( *(_BYTE *)this )
            {
              v35 = (*(__int64 (__fastcall **)(BSTR, __int64))(v34 + 56))(v48[0], v33);
              v36 = v35;
              if ( v35 >= 0 )
                goto LABEL_40;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x253,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                (const char *)(unsigned int)v35,
                (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v48);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(bstrString);
              LOBYTE(v42) = 0;
              Microsoft::Diagnostics::Tracer::CancelTracing(this, v42);
              result = v36;
            }
            else
            {
              v43 = (*(__int64 (__fastcall **)(BSTR, __int64))(v34 + 72))(v48[0], v33);
              v44 = v43;
              if ( v43 >= 0 )
              {
LABEL_40:
                if ( v48[0] )
                  (*(void (__fastcall **)(BSTR))(*(_QWORD *)v48[0] + 16LL))(v48[0]);
LABEL_26:
                v28 = Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(
                        (Microsoft::Diagnostics::Tracer *)this,
                        1);
                v21 = v28;
                if ( v28 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x25C,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                    (const char *)(unsigned int)v28,
                    (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
                  v30 = bstrString[0];
                  if ( bstrString[0] )
LABEL_28:
                    SysFreeString(v30);
LABEL_46:
                  LOBYTE(v29) = 0;
                  Microsoft::Diagnostics::Tracer::CancelTracing(this, v29);
                  return v21;
                }
                if ( bstrString[0] )
                  SysFreeString(bstrString[0]);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x257,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                (const char *)(unsigned int)v43,
                (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v48);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(bstrString);
              LOBYTE(v45) = 0;
              Microsoft::Diagnostics::Tracer::CancelTracing(this, v45);
              result = v44;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x250,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
              (const char *)0x80004005LL,
              (int)&GUID_c732a38e_0699_4acc_9070_a0a43f568e34);
            wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v48);
            wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(bstrString);
            LOBYTE(v41) = 0;
            Microsoft::Diagnostics::Tracer::CancelTracing(this, v41);
            result = 2147500037LL;
          }
        }
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x26B,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\tracing\\tracer.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180047c48  mov     [rsp+arg_8], rbx
0x180047c4d  mov     [rsp+arg_10], rsi
0x180047c52  push    rdi
0x180047c53  push    r14
0x180047c55  push    r15
0x180047c57  sub     rsp, 90h
0x180047c5e  mov     rax, cs:__security_cookie
0x180047c65  xor     rax, rsp
0x180047c68  mov     [rsp+0A8h+var_28], rax
0x180047c70  mov     rsi, r9
0x180047c73  mov     r15, rdx
0x180047c76  mov     rbx, rcx
0x180047c79  mov     [rsp+0A8h+var_58], rcx
0x180047c7e  mov     [rsp+0A8h+var_50], 1
0x180047c83  mov     [rcx], r8b
0x180047c86  mov     byte ptr [r9], 0
0x180047c8a  mov     byte ptr [rcx+0B0h], 0
0x180047c91  mov     dl, 1; bool
0x180047c93  call    ?QueryCurrentTraceProfileCollection@Tracer@Diagnostics@Microsoft@@AEAAJ_N@Z; Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(bool)
0x180047c98  mov     edi, eax
0x180047c9a  cmp     eax, 0C5583000h
0x180047c9f  jnz     loc_180047F35
0x180047ca5  lea     r14, [rbx+0C8h]
0x180047cac  mov     rcx, r14
0x180047caf  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180047cb4  mov     rcx, r14
0x180047cb7  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180047cbc  lea     rdi, [rbx+60h]
0x180047cc0  cmp     qword ptr [rdi+18h], 7
0x180047cc5  jbe     loc_180047F0F
0x180047ccb  mov     rdx, [rdi]
0x180047cce  lea     rcx, [rsp+0A8h+var_68]
0x180047cd3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180047cd8  mov     [rsp+0A8h+var_80], r14
0x180047cdd  lea     rcx, _GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a
0x180047ce4  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x180047ce9  mov     r9d, 1
0x180047cef  xor     r8d, r8d
0x180047cf2  lea     rdx, _GUID_b98b53f3_83ba_4837_8946_e886be8d4003
0x180047cf9  mov     rcx, [rax]
0x180047cfc  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x180047d02  mov     esi, eax
0x180047d04  mov     rcx, [rsp+0A8h+var_68]; bstrString
0x180047d09  test    rcx, rcx
0x180047d0c  jnz     loc_180047F17
0x180047d12  test    esi, esi
0x180047d14  js      loc_1800480AA
0x180047d1a  lea     rsi, [rbx+0D0h]
0x180047d21  cmp     qword ptr [rsi], 0
0x180047d25  jz      short loc_180047D51
0x180047d27  lea     rdx, [rsp+0A8h+var_68]
0x180047d2c  mov     rcx, rsi
0x180047d2f  call    ??$query@UIProfileElement@WindowsPerformanceRecorder@@@?$com_ptr_t@UIProfile@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIProfileElement@WindowsPerformanceRecorder@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IProfile,wil::err_exception_policy>::query<WindowsPerformanceRecorder::IProfileElement>(void)
0x180047d34  nop
0x180047d35  mov     rcx, [rsp+0A8h+var_68]
0x180047d3a  mov     rax, [rcx]
0x180047d3d  mov     rax, [rax+20h]
0x180047d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d46  nop
0x180047d47  lea     rcx, [rsp+0A8h+var_68]
0x180047d4c  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x180047d51  mov     rcx, rsi
0x180047d54  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180047d59  mov     rcx, rsi
0x180047d5c  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x180047d61  cmp     qword ptr [rdi+18h], 7
0x180047d66  jbe     short loc_180047D6B
0x180047d68  mov     rdi, [rdi]
0x180047d6b  mov     rdx, rdi
0x180047d6e  lea     rcx, [rsp+0A8h+var_68]
0x180047d73  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180047d78  mov     [rsp+0A8h+var_80], rsi
0x180047d7d  lea     rcx, _GUID_c732a38e_0699_4acc_9070_a0a43f568e34
0x180047d84  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x180047d89  mov     r9d, 1
0x180047d8f  xor     r8d, r8d
0x180047d92  lea     rdx, _GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4
0x180047d99  mov     rcx, [rax]
0x180047d9c  call    cs:__imp_WPRCCreateInstanceUnderInstanceName
0x180047da2  mov     edi, eax
0x180047da4  mov     rcx, [rsp+0A8h+var_68]; bstrString
0x180047da9  test    rcx, rcx
0x180047dac  jnz     loc_180047F22
0x180047db2  test    edi, edi
0x180047db4  js      loc_18004800B
0x180047dba  lea     rax, [r15+20h]
0x180047dbe  cmp     qword ptr [rax+18h], 0Fh
0x180047dc3  jbe     short loc_180047DC8
0x180047dc5  mov     rax, [rax]
0x180047dc8  mov     [rsp+0A8h+var_68], rax
0x180047dcd  mov     rax, [r15+30h]
0x180047dd1  mov     [rsp+0A8h+var_60], rax
0x180047dd6  lea     rdx, [rsp+0A8h+var_68]
0x180047ddb  lea     rcx, [rsp+0A8h+var_48]
0x180047de0  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x180047de5  nop
0x180047de6  cmp     qword ptr [rax+18h], 7
0x180047deb  ja      loc_180047F2D
0x180047df1  mov     rdx, rax
0x180047df4  lea     rcx, [rsp+0A8h+bstrString]
0x180047df9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180047dfe  nop
0x180047dff  lea     rcx, [rsp+0A8h+var_48]
0x180047e04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047e09  mov     rcx, [rsi]
0x180047e0c  mov     rax, [rcx]
0x180047e0f  mov     rdx, [rsp+0A8h+bstrString]
0x180047e14  mov     rax, [rax+0D0h]
0x180047e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e20  mov     edi, eax
0x180047e22  test    eax, eax
0x180047e24  js      loc_18004803A
0x180047e2a  mov     rcx, [rsi]
0x180047e2d  mov     rax, [rcx]
0x180047e30  lea     rdx, [rbx+0A0h]
0x180047e37  mov     rax, [rax+98h]
0x180047e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e43  mov     edi, eax
0x180047e45  test    eax, eax
0x180047e47  js      loc_1800480D9
0x180047e4d  mov     rcx, [r14]
0x180047e50  mov     rax, [rcx]
0x180047e53  or      r8d, 0FFFFFFFFh
0x180047e57  mov     rdx, [rsi]
0x180047e5a  mov     rax, [rax+38h]
0x180047e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e63  mov     edi, eax
0x180047e65  test    eax, eax
0x180047e67  js      loc_180048113
0x180047e6d  cmp     byte ptr [rbx+1], 0
0x180047e71  jnz     short loc_180047E93
0x180047e73  mov     rcx, [rbx+0B8h]
0x180047e7a  mov     rax, [rcx]
0x180047e7d  mov     rdx, [r14]
0x180047e80  mov     rax, [rax+48h]
0x180047e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e89  mov     edi, eax
0x180047e8b  test    eax, eax
0x180047e8d  js      loc_18004814D
0x180047e93  cmp     byte ptr [rbx], 0
0x180047e96  jnz     loc_180047FA2
0x180047e9c  cmp     byte ptr [rbx+1], 0
0x180047ea0  jnz     loc_180047FA2
0x180047ea6  mov     dl, 1; bool
0x180047ea8  mov     rcx, rbx; this
0x180047eab  call    ?QueryCurrentTraceProfileCollection@Tracer@Diagnostics@Microsoft@@AEAAJ_N@Z; Microsoft::Diagnostics::Tracer::QueryCurrentTraceProfileCollection(bool)
0x180047eb0  mov     edi, eax
0x180047eb2  test    eax, eax
0x180047eb4  jns     short loc_180047EFD
0x180047eb6  mov     rcx, [rsp+0A8h]; this
0x180047ebe  mov     r9d, eax; char *
0x180047ec1  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x180047ec8  mov     edx, 25Ch; void *
0x180047ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ed2  nop
0x180047ed3  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180047ed8  test    rcx, rcx
0x180047edb  jz      short loc_180047EE4
0x180047edd  call    cs:__imp_SysFreeString
0x180047ee3  nop
0x180047ee4  xor     dl, dl
0x180047ee6  mov     rcx, rbx
0x180047ee9  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180047eee  nop
0x180047eef  mov     eax, edi
0x180047ef1  jmp     loc_180047F79
0x180047ef6  mov     byte ptr [rsi], 1
0x180047ef9  xor     eax, eax
0x180047efb  jmp     short loc_180047F79
0x180047efd  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180047f02  test    rcx, rcx
0x180047f05  jz      short loc_180047EF9
0x180047f07  call    cs:__imp_SysFreeString
0x180047f0d  jmp     short loc_180047EF9
0x180047f0f  mov     rdx, rdi
0x180047f12  jmp     loc_180047CCE
0x180047f17  call    cs:__imp_SysFreeString
0x180047f1d  jmp     loc_180047D12
0x180047f22  call    cs:__imp_SysFreeString
0x180047f28  jmp     loc_180047DB2
0x180047f2d  mov     rax, [rax]
0x180047f30  jmp     loc_180047DF1
0x180047f35  test    edi, edi
0x180047f37  jns     short loc_180047EF6
0x180047f39  mov     rcx, [rsp+0A8h]; this
0x180047f41  mov     r9d, edi; char *
0x180047f44  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x180047f4b  mov     edx, 265h; void *
0x180047f50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047f55  nop
0x180047f56  xor     dl, dl
0x180047f58  mov     rcx, rbx
0x180047f5b  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180047f60  nop
0x180047f61  mov     eax, edi
0x180047f63  jmp     short loc_180047F79
0x180047f65  call    cs:__imp_SysFreeString
0x180047f6b  nop
0x180047f6c  xor     dl, dl
0x180047f6e  mov     rcx, rbx
0x180047f71  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180047f76  nop
0x180047f77  mov     eax, edi
0x180047f79  mov     rcx, [rsp+0A8h+var_28]
0x180047f81  xor     rcx, rsp; StackCookie
0x180047f84  call    __security_check_cookie
0x180047f89  lea     r11, [rsp+0A8h+var_18]
0x180047f91  mov     rbx, [r11+28h]
0x180047f95  mov     rsi, [r11+30h]
0x180047f99  mov     rsp, r11
0x180047f9c  pop     r15
0x180047f9e  pop     r14
0x180047fa0  pop     rdi
0x180047fa1  retn
0x180047fa2  mov     [rsp+0A8h+var_68], 0
0x180047fab  lea     rcx, [rbx+0B8h]
0x180047fb2  lea     r8, [rsp+0A8h+var_68]
0x180047fb7  call    ?try_query_to@?$com_ptr_t@UIControlManager@@Uerr_exception_policy@wil@@@wil@@QEBA_NAEBU_GUID@@PEAPEAX@Z; wil::com_ptr_t<IControlManager,wil::err_exception_policy>::try_query_to(_GUID const &,void * *)
0x180047fbc  test    al, al
0x180047fbe  jz      loc_18004815E
0x180047fc4  mov     rcx, [rsp+0A8h+var_68]
0x180047fc9  mov     rdx, [rbx+0C8h]
0x180047fd0  mov     rax, [rcx]
0x180047fd3  cmp     byte ptr [rbx], 0
0x180047fd6  jz      loc_1800481ED
0x180047fdc  mov     rax, [rax+38h]
0x180047fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fe5  mov     edi, eax
0x180047fe7  test    eax, eax
0x180047fe9  js      loc_1800481A8
0x180047fef  mov     rcx, [rsp+0A8h+var_68]
0x180047ff4  test    rcx, rcx
0x180047ff7  jz      short loc_180048006
0x180047ff9  mov     rax, [rcx]
0x180047ffc  mov     rax, [rax+10h]
0x180048000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048005  nop
0x180048006  jmp     loc_180047EA6
0x18004800b  mov     rcx, [rsp+0A8h]; this
0x180048013  mov     r9d, edi; char *
0x180048016  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x18004801d  mov     edx, 238h; void *
0x180048022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048027  nop
0x180048028  xor     dl, dl
0x18004802a  mov     rcx, rbx
0x18004802d  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180048032  nop
0x180048033  mov     eax, edi
0x180048035  jmp     loc_180047F79
0x18004803a  mov     rcx, [rsp+0A8h]; this
0x180048042  mov     r9d, edi; char *
0x180048045  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x18004804c  mov     edx, 23Bh; void *
0x180048051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048056  nop
0x180048057  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18004805c  test    rcx, rcx
0x18004805f  jz      short loc_180048068
0x180048061  call    cs:__imp_SysFreeString
0x180048067  nop
0x180048068  xor     dl, dl
0x18004806a  mov     rcx, rbx
0x18004806d  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x180048072  nop
0x180048073  mov     eax, edi
0x180048075  jmp     loc_180047F79
0x18004807a  mov     rcx, [rsp+0A8h]; this
0x180048082  mov     r9d, edi; char *
0x180048085  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x18004808c  mov     edx, 243h; void *
0x180048091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048096  nop
0x180048097  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18004809c  test    rcx, rcx
0x18004809f  jz      loc_180047F6C
0x1800480a5  jmp     loc_180047F65
0x1800480aa  mov     rcx, [rsp+0A8h]; this
0x1800480b2  mov     r9d, esi; char *
0x1800480b5  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x1800480bc  mov     edx, 228h; void *
0x1800480c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480c6  nop
0x1800480c7  xor     dl, dl
0x1800480c9  mov     rcx, rbx
0x1800480cc  call    ?CancelTracing@Tracer@Diagnostics@Microsoft@@QEAAJVScorchInfo@EnumDetails@23@@Z; Microsoft::Diagnostics::Tracer::CancelTracing(Microsoft::Diagnostics::EnumDetails::ScorchInfo)
0x1800480d1  nop
0x1800480d2  mov     eax, esi
0x1800480d4  jmp     loc_180047F79
0x1800480d9  mov     rcx, [rsp+0A8h]; this
0x1800480e1  mov     r9d, edi; char *
0x1800480e4  lea     r8, aOnecoreBaseTel_131; "onecore\\base\\telemetry\\utc\\service"...
0x1800480eb  mov     edx, 23Ch; void *
0x1800480f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800480f5  nop
0x1800480f6  lea     rcx, [rsp+0A8h+bstrString]
0x1800480fb  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180048100  nop
0x180048101  xor     dl, dl
0x180048103  mov     rcx, rbx
  ... truncated ...
```
