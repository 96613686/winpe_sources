# NAPRuleRegister(char const *,_WNF_STATE_NAME *,ulong,NA_XML_PARSE_ERROR_DETAILS *,__int64 *,NA_SIGNAL_TYPE_INFO *)

- ea: `0x18000bbe8`
- end: `0x18000bf6e`
- name: `?NAPRuleRegister@@YAJPEBDPEAU_WNF_STATE_NAME@@KPEAUNA_XML_PARSE_ERROR_DETAILS@@PEA_JPEAW4NA_SIGNAL_TYPE_INFO@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(const char *, struct _WNF_STATE_NAME *, unsigned int, struct NA_XML_PARSE_ERROR_DETAILS *, __int64 *, enum NA_SIGNAL_TYPE_INFO *)`
- caller_count: `4`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x18000d1c0`
- `0x180013f30`
- `0x180014124`
- `0x18001c8b4`

## callees

- `0x1800010b0`
- `0x1800010f4`
- `0x1800011c0`
- `0x180004170`
- `0x18000b0d0`
- `0x18000b3dc`
- `0x18000b578`
- `0x18000b594`
- `0x18000b5b0`
- `0x18000b794`
- `0x18000b7e4`
- `0x18000b814`
- `0x18000bbe8`
- `0x18000c9e0`
- `0x18000cab8`
- `0x18000cb10`
- `0x18000d37c`
- `0x180020370`
- `0x180021980`
- `0x1800219a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bde1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bde1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bc97`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bcca`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bc97`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bcca`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NAPRuleRegister(
        const char *a1,
        struct _WNF_STATE_NAME *a2,
        unsigned int a3,
        struct NA_XML_PARSE_ERROR_DETAILS *a4,
        __int64 *a5,
        enum NA_SIGNAL_TYPE_INFO *a6)
{
  NaturalAuthTraceLogging **v8; // r14
  enum NA_SIGNAL_TYPE_INFO *v10; // rsi
  GUID *v11; // r9
  int v12; // edi
  signed __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 CorrelationVector; // rax
  NaturalAuthTraceLogging *v19; // rcx
  int v20; // eax
  unsigned int v21; // eax
  int v22; // ecx
  __int64 v24; // rax
  __int64 v25; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-C8h] BYREF
  struct _WNF_STATE_NAME *v28; // [rsp+68h] [rbp-C0h] BYREF
  enum NA_SIGNAL_TYPE_INFO *v29; // [rsp+70h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v30; // [rsp+78h] [rbp-B0h] BYREF
  int *v31; // [rsp+80h] [rbp-A8h] BYREF
  __int16 v32; // [rsp+88h] [rbp-A0h]
  std::exception *v33; // [rsp+90h] [rbp-98h] BYREF
  int v34; // [rsp+98h] [rbp-90h] BYREF
  char v35; // [rsp+9Ch] [rbp-8Ch]
  GUID ActivityId; // [rsp+A0h] [rbp-88h] BYREF
  GUID v37; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v38[32]; // [rsp+C0h] [rbp-68h] BYREF

  v8 = (NaturalAuthTraceLogging **)a2;
  v28 = a2;
  v10 = a6;
  v29 = a6;
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids, a1);
  v34 = 0;
  v35 = 0;
  if ( (unsigned int)dword_18005C570 <= 5 )
  {
    ActivityId = 0;
  }
  else
  {
    EventActivityIdControl(3u, &ActivityId);
    v37 = ActivityId;
    EventActivityIdControl(4u, &v37);
    v35 = 1;
  }
  v34 = 1;
  if ( (unsigned int)dword_18005C570 > 5 )
  {
    if ( !v35 || _tlgGuidIsZero(&v37) )
      v11 = 0;
    else
      v11 = &v37;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18005C570,
      byte_18004F829,
      &ActivityId,
      v11);
  }
  try
  {
    v31 = &v34;
    v32 = 256;
    v25 = 0;
    v12 = NAParseRule(a1, &v25, a4);
    if ( v12 >= 0 )
    {
      v13 = _InterlockedIncrement64(&qword_18005FA38);
      v27 = v13;
      if ( a6 )
      {
        *(_DWORD *)a6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
        v13 = v27;
      }
      v26 = 0;
      v12 = SignalInfo::Create(v13, &v25, v8, a3, &v26);
      if ( v12 >= 0 )
      {
        AcquireSRWLockExclusive(&SRWLock);
        v30 = &SRWLock;
        v15 = *(_QWORD *)std::map<__int64,std::unique_ptr<SignalInfo>>::_Try_emplace<__int64 const &,>(v14, v38, &v27);
        v16 = v26;
        v26 = 0;
        v17 = *(_QWORD *)(v15 + 40);
        *(_QWORD *)(v15 + 40) = v16;
        if ( v17 )
          std::default_delete<SignalInfo>::operator()();
        *a5 = v27;
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
      }
      std::unique_ptr<SignalInfo>::~unique_ptr<SignalInfo>(&v26);
    }
    std::unique_ptr<TimeSignal::Factory>::~unique_ptr<TimeSignal::Factory>(&v25);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v25) = -2147024882;
    v10 = v29;
    v8 = (NaturalAuthTraceLogging **)v28;
    v12 = -2147024882;
  }
  catch ( std::exception *v33 )
  {
    LODWORD(v25) = -2147220987;
    v24 = (*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v33 + 8LL))(v33);
    LogUnhandledException(v24);
    v10 = v29;
    v8 = (NaturalAuthTraceLogging **)v28;
    v12 = v25;
  }
  v31 = &v34;
  v32 = 256;
  v25 = 0;
  v12 = NAParseRule(a1, &v25, a4);
}

```

## disassembly

```asm
0x18000bbe8  push    rsi
0x18000bbea  push    rdi
0x18000bbeb  push    r12
0x18000bbed  push    r13
0x18000bbef  push    r14
0x18000bbf1  push    r15
0x18000bbf3  sub     rsp, 0F8h
0x18000bbfa  mov     rax, cs:__security_cookie
0x18000bc01  xor     rax, rsp
0x18000bc04  mov     [rsp+128h+var_48], rax
0x18000bc0c  mov     r15, r9
0x18000bc0f  mov     r12d, r8d
0x18000bc12  mov     r14, rdx
0x18000bc15  mov     rdi, rcx
0x18000bc18  mov     [rsp+128h+var_C0], rdx
0x18000bc1d  mov     r13, [rsp+128h+arg_20]
0x18000bc25  mov     rsi, [rsp+128h+arg_28]
0x18000bc2d  mov     [rsp+128h+var_B8], rsi
0x18000bc32  mov     [rsp+128h+var_C8], 0
0x18000bc3b  lea     rax, WPP_GLOBAL_Control
0x18000bc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc49  cmp     rcx, rax
0x18000bc4c  jz      short loc_18000BC6C
0x18000bc4e  test    byte ptr [rcx+1Ch], 4
0x18000bc52  jz      short loc_18000BC6C
0x18000bc54  mov     edx, 11h
0x18000bc59  mov     r9, rdi
0x18000bc5c  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000bc63  mov     rcx, [rcx+10h]
0x18000bc67  call    WPP_SF_s
0x18000bc6c  mov     [rsp+128h+var_90], 0
0x18000bc77  mov     [rsp+128h+var_8C], 0
0x18000bc7f  mov     eax, cs:dword_18005C570
0x18000bc85  cmp     eax, 5
0x18000bc88  jbe     short loc_18000BCDA
0x18000bc8a  lea     rdx, [rsp+128h+ActivityId]; ActivityId
0x18000bc92  mov     ecx, 3; ControlCode
0x18000bc97  call    cs:__imp_EventActivityIdControl
0x18000bc9d  mov     rax, qword ptr [rsp+128h+ActivityId.Data1]
0x18000bca5  mov     qword ptr [rsp+128h+var_78.Data1], rax
0x18000bcad  mov     rax, qword ptr [rsp+128h+ActivityId.Data4]
0x18000bcb5  mov     qword ptr [rsp+128h+var_78.Data4], rax
0x18000bcbd  lea     rdx, [rsp+128h+var_78]; ActivityId
0x18000bcc5  mov     ecx, 4; ControlCode
0x18000bcca  call    cs:__imp_EventActivityIdControl
0x18000bcd0  mov     [rsp+128h+var_8C], 1
0x18000bcd8  jmp     short loc_18000BCE5
0x18000bcda  xorps   xmm0, xmm0
0x18000bcdd  movups  xmmword ptr [rsp+128h+ActivityId.Data1], xmm0
0x18000bce5  mov     [rsp+128h+var_90], 1
0x18000bcf0  mov     eax, cs:dword_18005C570
0x18000bcf6  cmp     eax, 5
0x18000bcf9  jbe     short loc_18000BD3E
0x18000bcfb  cmp     [rsp+128h+var_8C], 0
0x18000bd03  jz      short loc_18000BD20
0x18000bd05  lea     rcx, [rsp+128h+var_78]; struct _GUID *
0x18000bd0d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18000bd12  test    al, al
0x18000bd14  jnz     short loc_18000BD20
0x18000bd16  lea     r9, [rsp+128h+var_78]
0x18000bd1e  jmp     short loc_18000BD23
0x18000bd20  xor     r9d, r9d
0x18000bd23  lea     r8, [rsp+128h+ActivityId]
0x18000bd2b  lea     rdx, byte_18004F829
0x18000bd32  lea     rcx, dword_18005C570
0x18000bd39  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000bd3e  lea     rax, [rsp+128h+var_90]
0x18000bd46  mov     [rsp+128h+var_A8], rax
0x18000bd4e  mov     [rsp+128h+var_A0], 100h
0x18000bd58  mov     [rsp+128h+var_D8], 0
0x18000bd61  mov     r8, r15
0x18000bd64  lea     rdx, [rsp+128h+var_D8]
0x18000bd69  mov     rcx, rdi; lpMultiByteStr
0x18000bd6c  call    ?NAParseRule@@YAJPEBDPEAV?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z; NAParseRule(char const *,std::unique_ptr<NASignal> *,NA_XML_PARSE_ERROR_DETAILS *)
0x18000bd71  mov     edi, eax
0x18000bd73  test    eax, eax
0x18000bd75  js      loc_18000BE40
0x18000bd7b  mov     ecx, 1
0x18000bd80  lock xadd cs:qword_18005FA38, rcx
0x18000bd89  inc     rcx
0x18000bd8c  mov     [rsp+128h+var_C8], rcx
0x18000bd91  test    rsi, rsi
0x18000bd94  jz      short loc_18000BDAE
0x18000bd96  mov     rcx, [rsp+128h+var_D8]
0x18000bd9b  mov     rax, [rcx]
0x18000bd9e  mov     rax, [rax+20h]
0x18000bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda7  mov     [rsi], eax
0x18000bda9  mov     rcx, [rsp+128h+var_C8]
0x18000bdae  mov     [rsp+128h+var_D0], 0
0x18000bdb7  lea     rax, [rsp+128h+var_D0]
0x18000bdbc  mov     [rsp+128h+var_108], rax
0x18000bdc1  mov     r9d, r12d
0x18000bdc4  mov     r8, r14
0x18000bdc7  lea     rdx, [rsp+128h+var_D8]
0x18000bdcc  call    ?Create@SignalInfo@@SAJ_J$$QEAV?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@PEAU_WNF_STATE_NAME@@KPEAV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@3@@Z; SignalInfo::Create(__int64,std::unique_ptr<NASignal> &&,_WNF_STATE_NAME *,ulong,std::unique_ptr<SignalInfo> *)
0x18000bdd1  mov     edi, eax
0x18000bdd3  test    eax, eax
0x18000bdd5  js      short loc_18000BE35
0x18000bdd7  lea     r15, SRWLock
0x18000bdde  mov     rcx, r15; SRWLock
0x18000bde1  call    cs:__imp_AcquireSRWLockExclusive
0x18000bde7  mov     [rsp+128h+var_B0], r15
0x18000bdec  lea     r8, [rsp+128h+var_C8]
0x18000bdf1  lea     rdx, [rsp+128h+var_68]
0x18000bdf9  call    ??$_Try_emplace@AEB_J$$V@?$map@_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,std::unique_ptr<SignalInfo>>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18000bdfe  mov     rcx, [rax]
0x18000be01  mov     rax, [rsp+128h+var_D0]
0x18000be06  mov     [rsp+128h+var_D0], 0
0x18000be0f  mov     rdx, [rcx+28h]
0x18000be13  mov     [rcx+28h], rax
0x18000be17  test    rdx, rdx
0x18000be1a  jz      short loc_18000BE21
0x18000be1c  call    ??R?$default_delete@VSignalInfo@@@std@@QEBAXPEAVSignalInfo@@@Z; std::default_delete<SignalInfo>::operator()(SignalInfo *)
0x18000be21  mov     rax, [rsp+128h+var_C8]
0x18000be26  mov     [r13+0], rax
0x18000be2a  lea     rcx, [rsp+128h+var_B0]
0x18000be2f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000be34  nop
0x18000be35  lea     rcx, [rsp+128h+var_D0]
0x18000be3a  call    ??1?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<SignalInfo>::~unique_ptr<SignalInfo>(void)
0x18000be3f  nop
0x18000be40  lea     rcx, [rsp+128h+var_D8]
0x18000be45  call    ??1?$unique_ptr@VFactory@TimeSignal@@U?$default_delete@VFactory@TimeSignal@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimeSignal::Factory>::~unique_ptr<TimeSignal::Factory>(void)
0x18000be4a  nop
0x18000be4b  jmp     short loc_18000BE5B
0x18000be4d  mov     rsi, [rsp+128h+var_B8]
0x18000be52  mov     r14, [rsp+128h+var_C0]
0x18000be57  mov     edi, dword ptr [rsp+128h+var_D8]
0x18000be5b  mov     eax, cs:dword_18005C570
0x18000be61  cmp     eax, 5
0x18000be64  jbe     loc_18000BF2F
0x18000be6a  mov     rdx, 400000000000h
0x18000be74  lea     rcx, dword_18005C570
0x18000be7b  call    _tlgKeywordOn
0x18000be80  test    al, al
0x18000be82  jz      loc_18000BF2F
0x18000be88  lea     rcx, [rsp+128h+var_68]
0x18000be90  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x18000be95  mov     rcx, rax
0x18000be98  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18000be9d  mov     [rsp+128h+var_B0], rax
0x18000bea2  mov     ecx, [r14+4]
0x18000bea6  shl     rcx, 20h
0x18000beaa  mov     eax, [r14]
0x18000bead  or      rcx, rax; this
0x18000beb0  mov     [rsp+128h+var_B8], rcx
0x18000beb5  test    rsi, rsi
0x18000beb8  jz      short loc_18000BEBE
0x18000beba  mov     eax, [rsi]
0x18000bebc  jmp     short loc_18000BEC1
0x18000bebe  or      eax, 0FFFFFFFFh
0x18000bec1  mov     dword ptr [rsp+128h+var_D8], eax
0x18000bec5  mov     rax, [rsp+128h+var_C8]
0x18000beca  mov     [rsp+128h+var_C0], rax
0x18000becf  mov     dword ptr [rsp+128h+var_D0], edi
0x18000bed3  call    ?GetActivityId@NaturalAuthTraceLogging@@YAPEBU_GUID@@XZ; NaturalAuthTraceLogging::GetActivityId(void)
0x18000bed8  mov     r9, rax
0x18000bedb  lea     rax, [rsp+128h+var_B0]
0x18000bee0  mov     [rsp+128h+var_E8], rax
0x18000bee5  lea     rax, [rsp+128h+var_B8]
0x18000beea  mov     [rsp+128h+var_F0], rax
0x18000beef  lea     rax, [rsp+128h+var_D8]
0x18000bef4  mov     [rsp+128h+var_F8], rax
0x18000bef9  lea     rax, [rsp+128h+var_C0]
0x18000befe  mov     [rsp+128h+var_100], rax
0x18000bf03  lea     rax, [rsp+128h+var_D0]
0x18000bf08  mov     [rsp+128h+var_108], rax
0x18000bf0d  lea     r8, [rsp+128h+ActivityId]
0x18000bf15  lea     rdx, word_18004F856
0x18000bf1c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@34AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18000bf21  lea     rcx, [rsp+128h+var_68]
0x18000bf29  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000bf2e  nop
0x18000bf2f  lea     rcx, [rsp+128h+var_A8]
0x18000bf37  call    wil__details__ScopeExitFnGuard__lambda_d63af430316b8bd6ee45747296341a04_____operator__
0x18000bf3c  nop
0x18000bf3d  lea     rcx, [rsp+128h+var_90]
0x18000bf45  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000bf4a  mov     eax, edi
0x18000bf4c  mov     rcx, [rsp+128h+var_48]
0x18000bf54  xor     rcx, rsp; StackCookie
0x18000bf57  call    __security_check_cookie
0x18000bf5c  add     rsp, 0F8h
0x18000bf63  pop     r15
0x18000bf65  pop     r14
0x18000bf67  pop     r13
0x18000bf69  pop     r12
0x18000bf6b  pop     rdi
0x18000bf6c  pop     rsi
0x18000bf6d  retn
```
