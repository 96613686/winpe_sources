# PhoneController::_EndCall(CallInfo *,int,int)

- ea: `0x180038688`
- end: `0x180038d26`
- name: `?_EndCall@PhoneController@@IEAAJPEAVCallInfo@@HH@Z`
- size: `1694`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct CallInfo *, int, int)`
- caller_count: `10`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800233e0`
- `0x180023670`
- `0x180024ef0`
- `0x180025b90`
- `0x180034b10`
- `0x180038264`
- `0x180039008`
- `0x18003d070`
- `0x18003de48`
- `0x180042c34`

## callees

- `0x1800011fc`
- `0x180005654`
- `0x180005660`
- `0x1800056a0`
- `0x180006e94`
- `0x180009094`
- `0x18000e1a4`
- `0x18001d890`
- `0x18001f080`
- `0x1800208b4`
- `0x1800239bc`
- `0x18002c574`
- `0x18002c580`
- `0x180036b60`
- `0x180038688`
- `0x18003a048`
- `0x180048a68`
- `0x18004ef10`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800386c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800386ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800386c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800386ea`

## string_xrefs

- `0x1800386cd`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038bfe`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180038cba`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_EndCall(PhoneController *this, struct CallInfo *a2, int a3, unsigned int a4)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rsi
  int AllCalls; // eax
  void *v10; // rcx
  __int64 i; // rbx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  bool v18; // zf
  unsigned int *v19; // r12
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // ecx
  int v24; // edx
  int v25; // r15d
  struct PhoneLine *v26; // rbx
  const unsigned __int16 *v27; // rcx
  __int128 v28; // xmm0
  struct PhoneLine *v30; // rbx
  struct CallInfo *v31; // r13
  const unsigned __int16 *v32; // rcx
  __m128i v33; // xmm0
  int v34; // esi
  VerbParameters *v35; // rax
  VerbParameters *v36; // rsi
  VerbParameters *v37; // rsi
  unsigned int *v38; // r12
  unsigned int v39; // eax
  PhoneController *v40; // r15
  int v41; // eax
  BackTraceCollection *v42; // rcx
  unsigned int v43; // r14d
  unsigned int v44; // eax
  unsigned int v45; // [rsp+30h] [rbp-D0h] BYREF
  struct PhoneLine *v46; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v47[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v48; // [rsp+48h] [rbp-B8h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  PhoneController *v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v51; // [rsp+68h] [rbp-98h] BYREF
  __int128 v52; // [rsp+78h] [rbp-88h]
  __int128 v53; // [rsp+88h] [rbp-78h]
  __m128i si128; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-58h]
  void *v56[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C2h] [rbp-3Eh]
  int v59; // [rsp+CAh] [rbp-36h]
  __int16 v60; // [rsp+CEh] [rbp-32h]
  void *Block[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v62; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v63; // [rsp+E2h] [rbp-1Eh]
  int v64; // [rsp+EAh] [rbp-16h]
  __int16 v65; // [rsp+EEh] [rbp-12h]
  struct _EVENT_DATA_DESCRIPTOR v66; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int *v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]
  PhoneController **p_si128; // [rsp+120h] [rbp+20h]
  __int64 v70; // [rsp+128h] [rbp+28h]
  struct PhoneLine **v71; // [rsp+130h] [rbp+30h]
  __int64 v72; // [rsp+138h] [rbp+38h]
  struct PhoneLine **v73; // [rsp+140h] [rbp+40h]
  __int64 v74; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v75; // [rsp+150h] [rbp+50h]
  int v76; // [rsp+158h] [rbp+58h]
  int v77; // [rsp+15Ch] [rbp+5Ch]
  const char *v78; // [rsp+160h] [rbp+60h]
  __int64 v79; // [rsp+168h] [rbp+68h]

  v47[0] = a4;
  v48 = a3;
  v50[0] = this;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8701);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v51 = 0;
  v52 = 0;
  v53 = 0;
  PhoneController::_ComputeCallCounts(this, 0, (struct PH_PHONE_CALL_COUNTS *)&v51, 0);
  v46 = 0;
  CallInfo::GetPhoneLine(a2, &v46);
  v7 = *((_QWORD *)this + 12);
  v56[0] = &v57;
  v8 = -1;
  v58 = 0;
  v56[1] = &v57;
  v59 = 0;
  v60 = 0;
  v57 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v55 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v7, &si128, 0);
  if ( AllCalls < 0 )
    Log_HREvent_7((unsigned int)AllCalls, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8680);
  for ( i = si128.m128i_i64[0]; i != si128.m128i_i64[1]; i += 8 )
  {
    v12 = *(unsigned int *)(*(_QWORD *)i + 3040LL);
    if ( (_DWORD)v12 != 5 )
    {
      v63 = 0;
      Block[0] = &v62;
      Block[1] = &v62;
      v64 = 0;
      v65 = 0;
      v62 = 0;
      v13 = PhoneController::ConvertCallStateToString(v10, v12);
      v15 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              Block,
              L"%u-%s,",
              *(unsigned int *)(v14 + 3068),
              v13);
      if ( v15 < 0 )
        Log_HREvent_7((unsigned int)v15, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8689);
      if ( Block[0] )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)Block[0] + v16) );
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v56,
                               Block[0]) )
        Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8690);
      v10 = Block[0];
      if ( Block[0] != &v62 )
        operator delete(Block[0]);
    }
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  v17 = (unsigned int)(HIDWORD(v52) + v52 + HIDWORD(v51));
  v18 = *((_DWORD *)a2 + 766) == 4;
  v45 = HIDWORD(v52) + v52 + HIDWORD(v51);
  if ( !v18 )
  {
    v19 = (unsigned int *)((char *)a2 + 3040);
LABEL_46:
    v30 = v46;
    v31 = a2;
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v32 = (const unsigned __int16 *)v56[0];
      LODWORD(v46) = *v19;
      v45 = *((_DWORD *)a2 + 767);
      v33 = *(__m128i *)((char *)v30 + 88);
      v49 = (unsigned int)v17;
      si128 = v33;
      if ( v56[0] )
      {
        do
          ++v8;
        while ( *((_WORD *)v56[0] + v8) );
        v34 = 2 * v8 + 2;
      }
      else
      {
        v32 = &qword_18009A460;
        v34 = 2;
      }
      v75 = v32;
      v73 = &v46;
      v76 = v34;
      v71 = (struct PhoneLine **)&v45;
      v77 = 0;
      p_si128 = (PhoneController **)&si128;
      v74 = 4;
      v67 = (unsigned int *)&v49;
      v72 = 4;
      v70 = 16;
      v68 = 8;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&unk_1800A77A0, 0, 0, 7u, &v66);
    }
    v35 = (VerbParameters *)operator new(0x118u);
    v36 = v35;
    if ( v35 && (memset_0(v35, 0, 0x118u), (v37 = VerbParameters::VerbParameters(v36)) != 0) )
    {
      v18 = v47[0] == 0;
      v38 = (unsigned int *)((char *)a2 + 3072);
      *((_DWORD *)v37 + 58) = v48;
      if ( v18 || (v39 = *v38) == 0 )
        v39 = *((_DWORD *)a2 + 767);
      v40 = v50[0];
      v47[0] = v39;
      v41 = PhoneController::_ExecuteVerb(v50[0], a2, v47, 2, v37);
      v43 = v41;
      if ( v41 >= 0 )
      {
        v44 = *v38;
        if ( !*v38 )
          v44 = *((_DWORD *)v31 + 767);
        v47[0] = v44;
        PhoneController::_SetAttemptedLocalEnd(v40, v47);
        VerbParameters::~VerbParameters(v37);
        operator delete(v37);
        if ( v56[0] != &v57 )
          operator delete(v56[0]);
        if ( v30 )
          (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v30 + 16LL))(v30);
        return 0;
      }
      else
      {
        BackTraceCollection::Capture(v42, v41);
        Log_HREvent_7(v43, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8747);
        VerbParameters::~VerbParameters(v37);
        operator delete(v37);
        if ( v56[0] != &v57 )
          operator delete(v56[0]);
        if ( v30 )
          (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v30 + 16LL))(v30);
        return v43;
      }
    }
    else
    {
      Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8742);
      if ( v56[0] != &v57 )
        operator delete(v56[0]);
      if ( v30 )
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v30 + 16LL))(v30);
      return 2147942414LL;
    }
  }
  if ( (_DWORD)v17 != 3 || (v19 = (unsigned int *)((char *)a2 + 3040), *((_DWORD *)a2 + 760) != 1) && *v19 != 4 )
  {
    v20 = *((_QWORD *)this + 12);
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v55 = -1;
    v21 = PhoneCallStorage::GetAllCalls(v20, &si128, 0);
    if ( v21 < 0 )
      Log_HREvent_7((unsigned int)v21, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8611);
    v22 = si128.m128i_i64[0];
    v19 = (unsigned int *)((char *)a2 + 3040);
    while ( v22 != si128.m128i_i64[1] )
    {
      if ( *((_DWORD *)a2 + 767) != *(_DWORD *)(*(_QWORD *)v22 + 3068LL) && *v19 == 4 )
      {
        v23 = *(_DWORD *)(*(_QWORD *)v22 + 3040LL);
        if ( v23 <= 6 )
        {
          v24 = 77;
          if ( _bittest(&v24, v23) )
          {
            utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
            v17 = v45;
            goto LABEL_34;
          }
        }
      }
      v22 += 8;
    }
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    LODWORD(v17) = v45;
    goto LABEL_46;
  }
LABEL_34:
  v25 = 2;
  v26 = v46;
  if ( (unsigned int)dword_1800B3200 > 2 )
  {
    v27 = (const unsigned __int16 *)v56[0];
    v45 = *v19;
    LODWORD(v46) = *((_DWORD *)a2 + 767);
    v79 = 113;
    v28 = *(_OWORD *)((char *)v26 + 88);
    *(_QWORD *)v47 = (unsigned int)v17;
    v78 = "Ending the given call Id in the current callstate is not supported in multi-call scenario on Bluetooth HFP line.";
    *(_OWORD *)v50 = v28;
    if ( v56[0] )
    {
      do
        ++v8;
      while ( *((_WORD *)v56[0] + v8) );
      v25 = 2 * v8 + 2;
    }
    else
    {
      v27 = &qword_18009A460;
    }
    v75 = v27;
    v73 = (struct PhoneLine **)&v45;
    v76 = v25;
    v71 = &v46;
    v77 = 0;
    p_si128 = v50;
    v74 = 4;
    v67 = v47;
    v72 = 4;
    v70 = 16;
    v68 = 8;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&byte_1800A782D, 0, 0, 8u, &v66);
  }
  if ( v56[0] != &v57 )
    operator delete(v56[0]);
  if ( v26 )
    (*(void (__fastcall **)(struct PhoneLine *, __int64))(*(_QWORD *)v26 + 16LL))(v26, v17);
  return 2147942450LL;
}

```

## disassembly

```asm
0x180038688  mov     [rsp-8+arg_10], rbx
0x18003868d  push    rbp
0x18003868e  push    rsi
0x18003868f  push    rdi
0x180038690  push    r12
0x180038692  push    r13
0x180038694  push    r14
0x180038696  push    r15
0x180038698  lea     rbp, [rsp-80h]
0x18003869d  sub     rsp, 180h
0x1800386a4  mov     rax, cs:__security_cookie
0x1800386ab  xor     rax, rsp
0x1800386ae  mov     [rbp+0B0h+var_40], rax
0x1800386b2  mov     [rsp+1B0h+var_170], r9d
0x1800386b7  mov     r14, rdx
0x1800386ba  mov     [rsp+1B0h+var_168], r8d
0x1800386bf  mov     rdi, rcx
0x1800386c2  mov     [rsp+1B0h+var_158], rcx
0x1800386c7  call    cs:__imp_GetCurrentThreadId
0x1800386cd  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800386d4  cmp     [rdi+0F0h], eax
0x1800386da  jz      short loc_1800386FD
0x1800386dc  mov     r8d, 21FDh
0x1800386e2  mov     rdx, r15
0x1800386e5  call    Log_AssertionEvent_3
0x1800386ea  call    cs:__imp_GetCurrentThreadId
0x1800386f0  cmp     [rdi+0F0h], eax
0x1800386f6  jz      short loc_1800386FD
0x1800386f8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800386fd  xorps   xmm0, xmm0
0x180038700  lea     r8, [rsp+1B0h+var_148]; struct PH_PHONE_CALL_COUNTS *
0x180038705  xor     r9d, r9d; struct ISecurityToken *
0x180038708  xor     edx, edx; int
0x18003870a  mov     rcx, rdi; this
0x18003870d  movups  [rsp+1B0h+var_148], xmm0
0x180038712  movups  [rsp+1B0h+var_138], xmm0
0x180038717  movups  [rbp+0B0h+var_128], xmm0
0x18003871b  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x180038720  xor     r13d, r13d
0x180038723  lea     rdx, [rsp+1B0h+var_178]; struct PhoneLine **
0x180038728  mov     rcx, r14; this
0x18003872b  mov     [rsp+1B0h+var_178], r13
0x180038730  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180038735  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003873d  lea     rax, [rbp+0B0h+var_F0]
0x180038741  mov     rcx, [rdi+60h]
0x180038745  lea     rdx, [rbp+0B0h+var_118]
0x180038749  mov     [rbp+0B0h+var_100], rax
0x18003874d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038751  lea     rax, [rbp+0B0h+var_F0]
0x180038755  mov     [rbp+0B0h+var_EE], r13
0x180038759  xor     r8d, r8d
0x18003875c  mov     [rbp+0B0h+var_F8], rax
0x180038760  mov     [rbp+0B0h+var_E6], r13d
0x180038764  mov     [rbp+0B0h+var_E2], r13w
0x180038769  mov     [rbp+0B0h+var_F0], r13w
0x18003876e  movdqu  [rbp+0B0h+var_118], xmm0
0x180038773  mov     [rbp+0B0h+var_108], rsi
0x180038777  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x18003877c  test    eax, eax
0x18003877e  jns     short loc_180038792
0x180038780  mov     r9d, 21E8h
0x180038786  mov     r8, r15
0x180038789  xor     edx, edx
0x18003878b  mov     ecx, eax
0x18003878d  call    Log_HREvent_7
0x180038792  mov     rbx, qword ptr [rbp+0B0h+var_118]
0x180038796  cmp     rbx, qword ptr [rbp+0B0h+var_118+8]
0x18003879a  jz      loc_180038869
0x1800387a0  mov     r8, [rbx]
0x1800387a3  mov     edx, [r8+0BE0h]
0x1800387aa  cmp     edx, 5
0x1800387ad  jz      loc_180038860
0x1800387b3  lea     rax, [rbp+0B0h+var_D0]
0x1800387b7  mov     [rbp+0B0h+var_CE], r13
0x1800387bb  mov     [rbp+0B0h+Block], rax
0x1800387bf  lea     rax, [rbp+0B0h+var_D0]
0x1800387c3  mov     [rbp+0B0h+var_D8], rax
0x1800387c7  mov     [rbp+0B0h+var_C6], r13d
0x1800387cb  mov     [rbp+0B0h+var_C2], r13w
0x1800387d0  mov     [rbp+0B0h+var_D0], r13w
0x1800387d5  call    ?ConvertCallStateToString@PhoneController@@AEAAPEBGW4PH_CALLSTATE@@@Z; PhoneController::ConvertCallStateToString(PH_CALLSTATE)
0x1800387da  mov     r8d, [r8+0BFCh]
0x1800387e1  lea     rdx, aUS; "%u-%s,"
0x1800387e8  mov     r9, rax
0x1800387eb  lea     rcx, [rbp+0B0h+Block]
0x1800387ef  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800387f4  test    eax, eax
0x1800387f6  jns     short loc_18003880A
0x1800387f8  mov     r9d, 21F1h
0x1800387fe  mov     r8, r15
0x180038801  xor     edx, edx
0x180038803  mov     ecx, eax
0x180038805  call    Log_HREvent_7
0x18003880a  mov     rdx, [rbp+0B0h+Block]
0x18003880e  test    rdx, rdx
0x180038811  jz      short loc_180038822
0x180038813  mov     r8, rsi
0x180038816  inc     r8
0x180038819  cmp     [rdx+r8*2], r13w
0x18003881e  jnz     short loc_180038816
0x180038820  jmp     short loc_180038825
0x180038822  mov     r8, r13
0x180038825  lea     rcx, [rbp+0B0h+var_100]
0x180038829  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18003882e  test    al, al
0x180038830  jnz     short loc_180038847
0x180038832  mov     r9d, 21F2h
0x180038838  mov     r8, r15
0x18003883b  xor     edx, edx
0x18003883d  mov     ecx, 8007000Eh
0x180038842  call    Log_HREvent_7
0x180038847  mov     rcx, [rbp+0B0h+Block]; Block
0x18003884b  lea     rax, [rbp+0B0h+var_D0]
0x18003884f  cmp     rcx, rax
0x180038852  jz      short loc_180038860
0x180038854  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003885b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038860  add     rbx, 8
0x180038864  jmp     loc_180038796
0x180038869  lea     rcx, [rbp+0B0h+var_118]
0x18003886d  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180038872  mov     edx, dword ptr [rsp+1B0h+var_148+0Ch]
0x180038876  add     edx, dword ptr [rsp+1B0h+var_138]
0x18003887a  add     edx, dword ptr [rbp+0B0h+var_138+0Ch]
0x18003887d  cmp     dword ptr [r14+0BF8h], 4
0x180038885  mov     [rsp+1B0h+var_180], edx
0x180038889  jz      short loc_180038897
0x18003888b  lea     r12, [r14+0BE0h]
0x180038892  jmp     loc_180038A7B
0x180038897  cmp     edx, 3
0x18003889a  jnz     short loc_1800388B9
0x18003889c  lea     r12, [r14+0BE0h]
0x1800388a3  cmp     dword ptr [r12], 1
0x1800388a8  jz      loc_180038946
0x1800388ae  cmp     dword ptr [r12], 4
0x1800388b3  jz      loc_180038946
0x1800388b9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800388c1  lea     rdx, [rbp+0B0h+var_118]
0x1800388c5  mov     rcx, [rdi+60h]
0x1800388c9  xor     r8d, r8d
0x1800388cc  movdqu  [rbp+0B0h+var_118], xmm0
0x1800388d1  mov     [rbp+0B0h+var_108], rsi
0x1800388d5  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x1800388da  test    eax, eax
0x1800388dc  jns     short loc_1800388F0
0x1800388de  mov     r9d, 21A3h
0x1800388e4  mov     r8, r15
0x1800388e7  xor     edx, edx
0x1800388e9  mov     ecx, eax
0x1800388eb  call    Log_HREvent_7
0x1800388f0  mov     rax, qword ptr [rbp+0B0h+var_118]
0x1800388f4  lea     r12, [r14+0BE0h]
0x1800388fb  cmp     rax, qword ptr [rbp+0B0h+var_118+8]
0x1800388ff  jz      loc_180038A6E
0x180038905  mov     rdx, [rax]
0x180038908  mov     ecx, [rdx+0BFCh]
0x18003890e  cmp     [r14+0BFCh], ecx
0x180038915  jz      short loc_180038933
0x180038917  cmp     dword ptr [r12], 4
0x18003891c  jnz     short loc_180038933
0x18003891e  mov     ecx, [rdx+0BE0h]
0x180038924  cmp     ecx, 6
0x180038927  ja      short loc_180038933
0x180038929  mov     edx, 4Dh ; 'M'
0x18003892e  bt      edx, ecx
0x180038931  jb      short loc_180038939
0x180038933  add     rax, 8
0x180038937  jmp     short loc_1800388FB
0x180038939  lea     rcx, [rbp+0B0h+var_118]
0x18003893d  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180038942  mov     edx, [rsp+1B0h+var_180]
0x180038946  mov     eax, cs:dword_1800B3200
0x18003894c  mov     r15d, 2
0x180038952  mov     rbx, [rsp+1B0h+var_178]
0x180038957  mov     edi, 0BFCh
0x18003895c  cmp     eax, r15d
0x18003895f  jbe     loc_180038A37
0x180038965  mov     eax, [r12]
0x180038969  mov     rcx, [rbp+0B0h+var_100]
0x18003896d  mov     [rsp+1B0h+var_180], eax
0x180038971  mov     eax, [r14+rdi]
0x180038975  mov     dword ptr [rsp+1B0h+var_178], eax
0x180038979  mov     eax, edx
0x18003897b  mov     [rbp+0B0h+var_48], 71h ; 'q'
0x180038983  movups  xmm0, xmmword ptr [rbx+58h]
0x180038987  mov     qword ptr [rsp+1B0h+var_170], rax
0x18003898c  lea     rax, aEndingTheGiven; "Ending the given call Id in the current"...
0x180038993  mov     [rbp+0B0h+var_50], rax
0x180038997  movdqu  xmmword ptr [rsp+1B0h+var_158], xmm0
0x18003899d  test    rcx, rcx
0x1800389a0  jz      short loc_1800389B6
0x1800389a2  inc     rsi
0x1800389a5  cmp     [rcx+rsi*2], r13w
0x1800389aa  jnz     short loc_1800389A2
0x1800389ac  lea     r15d, ds:2[rsi*2]
0x1800389b4  jmp     short loc_1800389BD
0x1800389b6  lea     rcx, qword_18009A460
0x1800389bd  lea     rax, [rsp+1B0h+var_180]
0x1800389c2  mov     [rbp+0B0h+var_60], rcx
0x1800389c6  mov     [rbp+0B0h+var_70], rax
0x1800389ca  lea     rdx, byte_1800A782D; int
0x1800389d1  lea     rax, [rsp+1B0h+var_178]
0x1800389d6  mov     [rbp+0B0h+var_58], r15d
0x1800389da  mov     [rbp+0B0h+var_80], rax
0x1800389de  lea     rcx, dword_1800B3200; int
0x1800389e5  lea     rax, [rsp+1B0h+var_158]
0x1800389ea  mov     [rbp+0B0h+var_54], r13d
0x1800389ee  mov     [rbp+0B0h+var_90], rax
0x1800389f2  xor     r9d, r9d; int
0x1800389f5  lea     rax, [rsp+1B0h+var_170]
0x1800389fa  mov     [rbp+0B0h+var_68], 4
0x180038a02  mov     [rbp+0B0h+var_A0], rax
0x180038a06  xor     r8d, r8d; int
0x180038a09  lea     rax, [rbp+0B0h+var_C0]
0x180038a0d  mov     [rbp+0B0h+var_78], 4
0x180038a15  mov     [rsp+1B0h+var_188], rax; PEVENT_DATA_DESCRIPTOR
0x180038a1a  mov     [rsp+1B0h+var_190], 8; ULONG
0x180038a22  mov     [rbp+0B0h+var_88], 10h
0x180038a2a  mov     [rbp+0B0h+var_98], 8
0x180038a32  call    _tlgWriteTransfer_EventWriteTransfer
0x180038a37  mov     rcx, [rbp+0B0h+var_100]; Block
0x180038a3b  lea     rax, [rbp+0B0h+var_F0]
0x180038a3f  cmp     rcx, rax
0x180038a42  jz      short loc_180038A50
0x180038a44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180038a4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038a50  test    rbx, rbx
0x180038a53  jz      short loc_180038A64
0x180038a55  mov     rax, [rbx]
0x180038a58  mov     rcx, rbx
0x180038a5b  mov     rax, [rax+10h]
0x180038a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a64  mov     eax, 80070032h
0x180038a69  jmp     loc_180038CFF
0x180038a6e  lea     rcx, [rbp+0B0h+var_118]
0x180038a72  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180038a77  mov     edx, [rsp+1B0h+var_180]
0x180038a7b  mov     eax, cs:dword_1800B3200
0x180038a81  mov     edi, 0BFCh
0x180038a86  mov     rbx, [rsp+1B0h+var_178]
0x180038a8b  mov     r13, r14
0x180038a8e  mov     r15d, 2
0x180038a94  cmp     eax, 4
0x180038a97  jbe     loc_180038B60
0x180038a9d  mov     eax, [r12]
0x180038aa1  xor     r12d, r12d
0x180038aa4  mov     rcx, [rbp+0B0h+var_100]
0x180038aa8  mov     dword ptr [rsp+1B0h+var_178], eax
0x180038aac  mov     eax, [rdi+r14]
0x180038ab0  mov     [rsp+1B0h+var_180], eax
0x180038ab4  mov     eax, edx
0x180038ab6  movups  xmm0, xmmword ptr [rbx+58h]
0x180038aba  mov     [rsp+1B0h+var_160], rax
0x180038abf  movdqu  [rbp+0B0h+var_118], xmm0
0x180038ac4  test    rcx, rcx
0x180038ac7  jz      short loc_180038ADC
0x180038ac9  inc     rsi
0x180038acc  cmp     [rcx+rsi*2], r12w
0x180038ad1  jnz     short loc_180038AC9
0x180038ad3  lea     esi, ds:2[rsi*2]
0x180038ada  jmp     short loc_180038AE6
0x180038adc  lea     rcx, qword_18009A460
0x180038ae3  mov     esi, r15d
0x180038ae6  lea     rax, [rsp+1B0h+var_178]
0x180038aeb  mov     [rbp+0B0h+var_60], rcx
0x180038aef  mov     [rbp+0B0h+var_70], rax
0x180038af3  lea     rdx, unk_1800A77A0; int
0x180038afa  lea     rax, [rsp+1B0h+var_180]
0x180038aff  mov     [rbp+0B0h+var_58], esi
0x180038b02  mov     [rbp+0B0h+var_80], rax
0x180038b06  lea     rcx, dword_1800B3200; int
0x180038b0d  lea     rax, [rbp+0B0h+var_118]
0x180038b11  mov     [rbp+0B0h+var_54], r12d
0x180038b15  mov     [rbp+0B0h+var_90], rax
0x180038b19  xor     r9d, r9d; int
0x180038b1c  lea     rax, [rsp+1B0h+var_160]
0x180038b21  mov     [rbp+0B0h+var_68], 4
0x180038b29  mov     [rbp+0B0h+var_A0], rax
0x180038b2d  xor     r8d, r8d; int
0x180038b30  lea     rax, [rbp+0B0h+var_C0]
0x180038b34  mov     [rbp+0B0h+var_78], 4
0x180038b3c  mov     [rsp+1B0h+var_188], rax; PEVENT_DATA_DESCRIPTOR
0x180038b41  mov     [rsp+1B0h+var_190], 7; ULONG
0x180038b49  mov     [rbp+0B0h+var_88], 10h
0x180038b51  mov     [rbp+0B0h+var_98], 8
0x180038b59  call    _tlgWriteTransfer_EventWriteTransfer
0x180038b5e  jmp     short loc_180038B63
0x180038b60  xor     r12d, r12d
0x180038b63  mov     ecx, 118h; Size
0x180038b68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038b6d  mov     rsi, rax
0x180038b70  test    rax, rax
0x180038b73  jz      loc_180038CB5
0x180038b79  xor     edx, edx; Val
0x180038b7b  mov     r8d, 118h; Size
0x180038b81  mov     rcx, rax; void *
0x180038b84  call    memset_0
0x180038b89  mov     rcx, rsi; this
0x180038b8c  call    ??0VerbParameters@@QEAA@XZ; VerbParameters::VerbParameters(void)
  ... truncated ...
```
