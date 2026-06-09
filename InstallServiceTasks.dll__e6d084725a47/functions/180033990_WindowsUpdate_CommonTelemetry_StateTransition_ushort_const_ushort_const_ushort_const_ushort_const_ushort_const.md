# WindowsUpdate::CommonTelemetry::StateTransition(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,char const *,char const *,uchar,long,char const *)

- ea: `0x180033990`
- end: `0x180033c1e`
- name: `?StateTransition@CommonTelemetry@WindowsUpdate@@YAXPEBG0000PEBD1EJ1@Z`
- size: `654`
- prototype: `void __fastcall(WindowsUpdate::CommonTelemetry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const char *, const char *, unsigned __int8, int, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180020a1c`

## callees

- `0x180001b88`
- `0x180001cfc`
- `0x180003450`
- `0x18000c520`
- `0x18001aac4`
- `0x18003236c`
- `0x180033990`

## string_xrefs

- `0x1800339ba`: `AutoUpdateState_Disabled`
- `0x180033b47`: `onecoreuap\enduser\winstore\installservice\libqueue2\commontelemetry.cpp`
- `0x180033ae7`: `FulfillmentPluginId`
- `0x180033ad8`: `PluginTelemetryData`
- `0x180033aab`: `PluginLastStage`
- `0x180033b36`: `WindowsUpdate::CommonTelemetry::StateTransition`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WindowsUpdate::CommonTelemetry::StateTransition(
        WindowsUpdate::CommonTelemetry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const char *a7)
{
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r9
  _BYTE v12[4]; // [rsp+80h] [rbp-80h] BYREF
  int v13; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD v14[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v15[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v16[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v17[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v18[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v19[2]; // [rsp+D8h] [rbp-28h] BYREF
  const char *v20; // [rsp+E8h] [rbp-18h] BYREF
  char v21; // [rsp+F0h] [rbp-10h]
  const char *v22; // [rsp+F8h] [rbp-8h] BYREF
  int v23; // [rsp+100h] [rbp+0h]
  _QWORD v24[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v25[2]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v26[2]; // [rsp+128h] [rbp+28h] BYREF
  void *v27[2]; // [rsp+138h] [rbp+38h] BYREF
  __m128i si128; // [rsp+148h] [rbp+48h]
  void *v29[3]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v30; // [rsp+170h] [rbp+70h]

  if ( (unsigned int)dword_1800630D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800630D8, 0x800000000000LL, a3, a4) )
  {
    v14[0] = 0;
    v13 = 0;
    v12[0] = 0;
    v15[0] = a7;
    v16[0] = "AutoUpdateState_Disabled";
    v17[0] = 0;
    v18[0] = 0;
    v19[0] = 0;
    v20 = 0;
    v22 = 0;
    v24[0] = 0x80000000LL;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v7,
      (__int64)&dword_1800581A4,
      (__int64)a3,
      (__int64)a4,
      (__int64)v24,
      &v22,
      &v20,
      v19,
      v18,
      v17,
      v16,
      v15,
      (__int64)v12,
      (__int64)&v13,
      v14);
  }
  v24[0] = "__TlgCV__";
  v24[1] = 0;
  v22 = "HResult";
  v23 = 0;
  v20 = "PluginLastStage";
  v21 = 0;
  v19[0] = "NewState";
  v19[1] = a7;
  v18[0] = "PrevState";
  v18[1] = "AutoUpdateState_Disabled";
  v17[0] = "PluginTelemetryData";
  v17[1] = 0;
  v16[0] = "FulfillmentPluginId";
  v16[1] = 0;
  v15[0] = "CatalogId";
  v15[1] = 0;
  v14[0] = "PFN";
  v14[1] = 0;
  v25[0] = "ProductId";
  v25[1] = 0;
  v26[0] = "StateTransition";
  v26[1] = 15;
  std::string::string(v29, "WindowsUpdate::CommonTelemetry::StateTransition", a3, a4);
  std::string::string(v27, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\commontelemetry.cpp", v8, v9);
  Logging::StoreLoggingWrite<std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,char const *>,std::pair<char const *,char const *>,std::pair<char const *,unsigned char>,std::pair<char const *,long>,std::pair<char const *,char const *>>(
    (__int64)v27,
    v10,
    (__int64)v29,
    v11,
    (__int64)v26,
    (__int64)v25,
    (__int64)v14,
    (__int64)v15,
    (__int64)v16,
    (__int64)v17,
    (__int64)v18,
    (__int64)v19,
    (__int64)&v20,
    (__int64)&v22,
    (__int64)v24);
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>(v27[0], (struct std::nothrow_t *)(si128.m128i_i64[1] + 1));
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v27[0]) = 0;
  if ( v30 > 0xF )
    std::_Deallocate<16>(v29[0], (struct std::nothrow_t *)(v30 + 1));
}

```

## disassembly

```asm
0x180033990  push    rbp
0x180033992  push    rbx
0x180033993  push    rsi
0x180033994  push    rdi
0x180033995  lea     rbp, [rsp-88h]
0x18003399d  sub     rsp, 188h
0x1800339a4  mov     rax, cs:__security_cookie
0x1800339ab  xor     rax, rsp
0x1800339ae  mov     [rbp+0A0h+var_28], rax
0x1800339b2  mov     eax, cs:dword_1800630D8
0x1800339b8  xor     edi, edi
0x1800339ba  lea     rsi, aAutoupdatestat_0; "AutoUpdateState_Disabled"
0x1800339c1  mov     rbx, [rbp+0A0h+arg_30]
0x1800339c8  cmp     eax, 5
0x1800339cb  jbe     loc_180033A8E
0x1800339d1  mov     rdx, 800000000000h
0x1800339db  lea     rcx, dword_1800630D8
0x1800339e2  call    _tlgKeywordOn
0x1800339e7  test    al, al
0x1800339e9  jz      loc_180033A8E
0x1800339ef  mov     [rbp+0A0h+var_118], rdi
0x1800339f3  mov     [rbp+0A0h+var_11C], edi
0x1800339f6  mov     [rbp+0A0h+var_120], dil
0x1800339fa  mov     [rbp+0A0h+var_108], rbx
0x1800339fe  mov     [rbp+0A0h+var_F8], rsi
0x180033a02  mov     [rbp+0A0h+var_E8], rdi
0x180033a06  mov     [rbp+0A0h+var_D8], rdi
0x180033a0a  mov     [rbp+0A0h+var_C8], rdi
0x180033a0e  mov     [rbp+0A0h+var_B8], rdi
0x180033a12  mov     [rbp+0A0h+var_A8], rdi
0x180033a16  mov     eax, 80000000h
0x180033a1b  mov     [rbp+0A0h+var_98], rax
0x180033a1f  lea     rax, [rbp+0A0h+var_118]
0x180033a23  mov     [rsp+1A0h+var_130], rax
0x180033a28  lea     rax, [rbp+0A0h+var_11C]
0x180033a2c  mov     [rsp+1A0h+var_138], rax
0x180033a31  lea     rax, [rbp+0A0h+var_120]
0x180033a35  mov     [rsp+1A0h+var_140], rax
0x180033a3a  lea     rax, [rbp+0A0h+var_108]
0x180033a3e  mov     [rsp+1A0h+var_148], rax
0x180033a43  lea     rax, [rbp+0A0h+var_F8]
0x180033a47  mov     [rsp+1A0h+var_150], rax
0x180033a4c  lea     rax, [rbp+0A0h+var_E8]
0x180033a50  mov     [rsp+1A0h+var_158], rax
0x180033a55  lea     rax, [rbp+0A0h+var_D8]
0x180033a59  mov     [rsp+1A0h+var_160], rax
0x180033a5e  lea     rax, [rbp+0A0h+var_C8]
0x180033a62  mov     [rsp+1A0h+var_168], rax
0x180033a67  lea     rax, [rbp+0A0h+var_B8]
0x180033a6b  mov     [rsp+1A0h+var_170], rax
0x180033a70  lea     rax, [rbp+0A0h+var_A8]
0x180033a74  mov     [rsp+1A0h+var_178], rax
0x180033a79  lea     rax, [rbp+0A0h+var_98]
0x180033a7d  mov     [rsp+1A0h+var_180], rax
0x180033a82  lea     rdx, dword_1800581A4
0x180033a89  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U?$_tlgWrapSz@D@@U3@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4444AEBU?$_tlgWrapSz@D@@5AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033a8e  lea     rax, aTlgcv; "__TlgCV__"
0x180033a95  mov     [rbp+0A0h+var_98], rax
0x180033a99  mov     [rbp+0A0h+var_90], rdi
0x180033a9d  lea     rax, aHresult; "HResult"
0x180033aa4  mov     [rbp+0A0h+var_A8], rax
0x180033aa8  mov     [rbp+0A0h+var_A0], edi
0x180033aab  lea     rax, aPluginlaststag; "PluginLastStage"
0x180033ab2  mov     [rbp+0A0h+var_B8], rax
0x180033ab6  mov     [rbp+0A0h+var_B0], dil
0x180033aba  lea     rax, aNewstate; "NewState"
0x180033ac1  mov     [rbp+0A0h+var_C8], rax
0x180033ac5  mov     [rbp+0A0h+var_C0], rbx
0x180033ac9  lea     rax, aPrevstate; "PrevState"
0x180033ad0  mov     [rbp+0A0h+var_D8], rax
0x180033ad4  mov     [rbp+0A0h+var_D0], rsi
0x180033ad8  lea     rax, aPlugintelemetr; "PluginTelemetryData"
0x180033adf  mov     [rbp+0A0h+var_E8], rax
0x180033ae3  mov     [rbp+0A0h+var_E0], rdi
0x180033ae7  lea     rax, aFulfillmentplu; "FulfillmentPluginId"
0x180033aee  mov     [rbp+0A0h+var_F8], rax
0x180033af2  mov     [rbp+0A0h+var_F0], rdi
0x180033af6  lea     rax, aCatalogid; "CatalogId"
0x180033afd  mov     [rbp+0A0h+var_108], rax
0x180033b01  mov     [rbp+0A0h+var_100], rdi
0x180033b05  lea     rax, aPfn; "PFN"
0x180033b0c  mov     [rbp+0A0h+var_118], rax
0x180033b10  mov     [rbp+0A0h+var_110], rdi
0x180033b14  lea     rax, aProductid; "ProductId"
0x180033b1b  mov     [rbp+0A0h+var_88], rax
0x180033b1f  mov     [rbp+0A0h+var_80], rdi
0x180033b23  lea     rax, aStatetransitio; "StateTransition"
0x180033b2a  mov     [rbp+0A0h+var_78], rax
0x180033b2e  mov     [rbp+0A0h+var_70], 0Fh
0x180033b36  lea     rdx, aWindowsupdateC_2; "WindowsUpdate::CommonTelemetry::StateTr"...
0x180033b3d  lea     rcx, [rbp+0A0h+var_48]
0x180033b41  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180033b46  nop
0x180033b47  lea     rdx, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\installs"...
0x180033b4e  lea     rcx, [rbp+0A0h+var_68]
0x180033b52  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180033b57  nop
0x180033b58  lea     rax, [rbp+0A0h+var_98]
0x180033b5c  mov     [rsp+1A0h+var_130], rax
0x180033b61  lea     rax, [rbp+0A0h+var_A8]
0x180033b65  mov     [rsp+1A0h+var_138], rax
0x180033b6a  lea     rax, [rbp+0A0h+var_B8]
0x180033b6e  mov     [rsp+1A0h+var_140], rax
0x180033b73  lea     rax, [rbp+0A0h+var_C8]
0x180033b77  mov     [rsp+1A0h+var_148], rax
0x180033b7c  lea     rax, [rbp+0A0h+var_D8]
0x180033b80  mov     [rsp+1A0h+var_150], rax
0x180033b85  lea     rax, [rbp+0A0h+var_E8]
0x180033b89  mov     [rsp+1A0h+var_158], rax
0x180033b8e  lea     rax, [rbp+0A0h+var_F8]
0x180033b92  mov     [rsp+1A0h+var_160], rax
0x180033b97  lea     rax, [rbp+0A0h+var_108]
0x180033b9b  mov     [rsp+1A0h+var_168], rax
0x180033ba0  lea     rax, [rbp+0A0h+var_118]
0x180033ba4  mov     [rsp+1A0h+var_170], rax
0x180033ba9  lea     rax, [rbp+0A0h+var_88]
0x180033bad  mov     [rsp+1A0h+var_178], rax
0x180033bb2  lea     rax, [rbp+0A0h+var_78]
0x180033bb6  mov     [rsp+1A0h+var_180], rax
0x180033bbb  lea     r8, [rbp+0A0h+var_48]
0x180033bbf  lea     rcx, [rbp+0A0h+var_68]
0x180033bc3  call    ??$StoreLoggingWrite@U?$pair@PEBDPEBG@std@@U12@U12@U12@U12@U?$pair@PEBDPEBD@2@U32@U?$pair@PEBDE@2@U?$pair@PEBDJ@2@U32@@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@DU?$char_traits@D@std@@@2@$$QEAU?$pair@PEBDPEBG@2@3333$$QEAU?$pair@PEBDPEBD@2@4$$QEAU?$pair@PEBDE@2@$$QEAU?$pair@PEBDJ@2@4@Z; Logging::StoreLoggingWrite<std::pair<char const *,ushort const *>,std::pair<char const *,ushort const *>,std::pair<char const *,ushort const *>,std::pair<char const *,ushort const *>,std::pair<char const *,ushort const *>,std::pair<char const *,char const *>,std::pair<char const *,char const *>,std::pair<char const *,uchar>,std::pair<char const *,long>,std::pair<char const *,char const *>>(std::string const &,uint,std::string const &,Logging::Level,std::string_view const &,std::pair<char const *,ushort const *> &&,std::pair<char const *,ushort const *> &&,std::pair<char const *,ushort const *> &&,std::pair<char const *,ushort const *> &&,std::pair<char const *,ushort const *> &&,std::pair<char const *,char const *> &&,std::pair<char const *,char const *> &&,std::pair<char const *,uchar> &&,std::pair<char const *,long> &&,std::pair<char const *,char const *> &&)
0x180033bc8  nop
0x180033bc9  mov     rdx, [rbp+0A0h+var_50]
0x180033bcd  cmp     rdx, 0Fh
0x180033bd1  jbe     short loc_180033BDF
0x180033bd3  inc     rdx
0x180033bd6  mov     rcx, [rbp+0A0h+var_68]
0x180033bda  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033bdf  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180033be7  movdqu  xmmword ptr [rbp+48h], xmm0
0x180033bec  mov     byte ptr [rbp+0A0h+var_68], dil
0x180033bf0  mov     rdx, [rbp+0A0h+var_30]
0x180033bf4  cmp     rdx, 0Fh
0x180033bf8  jbe     short loc_180033C06
0x180033bfa  inc     rdx
0x180033bfd  mov     rcx, [rbp+0A0h+var_48]
0x180033c01  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033c06  mov     rcx, [rbp+0A0h+var_28]
0x180033c0a  xor     rcx, rsp; StackCookie
0x180033c0d  call    __security_check_cookie
0x180033c12  add     rsp, 188h
0x180033c19  pop     rdi
0x180033c1a  pop     rsi
0x180033c1b  pop     rbx
0x180033c1c  pop     rbp
0x180033c1d  retn
```
