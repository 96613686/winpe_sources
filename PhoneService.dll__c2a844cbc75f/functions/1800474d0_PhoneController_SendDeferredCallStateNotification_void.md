# PhoneController::_SendDeferredCallStateNotification(void)

- ea: `0x1800474d0`
- end: `0x180047a40`
- name: `?_SendDeferredCallStateNotification@PhoneController@@MEAAJXZ`
- size: `1392`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005660`
- `0x1800056a0`
- `0x180006e94`
- `0x18000e1a4`
- `0x180013cc0`
- `0x180017c84`
- `0x18001cb98`
- `0x18002c574`
- `0x18002c580`
- `0x1800474d0`
- `0x180048ed4`
- `0x18004ee7c`
- `0x18004f11c`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d942`
- `0x18008d9b0`
- `0x18008da40`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004750e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004752f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004750e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004752f`

## string_xrefs

- `0x180047993`: `onecoreuap\net\phone\phoneservice\service\lib\ControllerMessagesPriv.h`
- `0x180047523`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800475b8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004771e`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800478b9`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800479b9`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendDeferredCallStateNotification(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __m128i si128; // xmm6
  __int64 v6; // rcx
  int AllCalls; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  CallInfo **v10; // rbx
  __int64 v11; // r15
  char *v12; // rdi
  _BYTE *v13; // rsi
  CallInfo *v14; // r13
  int AssociatedDeviceIdsList; // eax
  BackTraceCollection *v16; // rcx
  unsigned int v17; // r13d
  unsigned __int64 v18; // rdx
  char v19; // al
  __int64 v20; // rcx
  char *v21; // rax
  char *v22; // rbx
  struct ATL::CAtlModule *v23; // rcx
  char **v24; // r13
  char *v25; // r9
  char *v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  unsigned int v29; // edi
  signed __int64 v30; // rcx
  signed __int64 v31; // rcx
  BackTraceCollection *v33; // rcx
  __int64 v34; // rcx
  int v35; // [rsp+30h] [rbp-D0h]
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h]
  __m128i v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h]
  _BYTE v40[6600]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+1A38h] [rbp+1938h] BYREF
  __m128i v42; // [rsp+1A40h] [rbp+1940h]
  __int64 v43; // [rsp+1A50h] [rbp+1950h]
  struct ISecurityPolicy *v44; // [rsp+1A58h] [rbp+1958h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4463);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v3 = *((_QWORD *)this + 33);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    v4 = *((_QWORD *)this + 33);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)this + 33) = 0;
    }
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v6 = *((_QWORD *)this + 12);
  v39 = -1;
  v38 = si128;
  AllCalls = PhoneCallStorage::GetAllCalls(v6, &v38, 0);
  v9 = AllCalls;
  if ( AllCalls < 0 )
  {
    BackTraceCollection::Capture(v8, AllCalls);
    Log_HREvent_7(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4474);
LABEL_39:
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v38);
    return v9;
  }
  v10 = (CallInfo **)v38.m128i_i64[0];
  v11 = -1;
  *(__m128i *)Block = si128;
  v12 = (char *)si128.m128i_i64[1];
  v13 = (_BYTE *)si128.m128i_i64[0];
  v37 = -1;
  while ( v10 != (CallInfo **)v38.m128i_i64[1] )
  {
    v41 = -1;
    v14 = *v10;
    v42 = si128;
    v43 = 0;
    v44 = 0;
    memcpy_0(v40, (char *)v14 + 24, sizeof(v40));
    LOBYTE(v43) = *((_BYTE *)v14 + 6912);
    if ( (_BYTE)v43 )
    {
      AssociatedDeviceIdsList = CallInfo::GetAssociatedDeviceIdsList(v14, &v41);
      v17 = AssociatedDeviceIdsList;
      if ( AssociatedDeviceIdsList < 0 )
      {
        BackTraceCollection::Capture(v16, AssociatedDeviceIdsList);
        Log_HREvent_7(v17, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4487);
        if ( v44 )
          (*(void (__fastcall **)(struct ISecurityPolicy *))(*(_QWORD *)v44 + 16LL))(v44);
        utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v41);
        if ( v13 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v20, v13, (v12 - v13) / 6640 + v12 - v13);
          operator delete(v13);
        }
        v9 = v17;
        goto LABEL_39;
      }
    }
    CallInfo::GetSecurityPolicy(*v10, &v44);
    if ( v12 != (char *)v11 )
      goto LABEL_18;
    v18 = 7 * ((0x87180ECE08A2DA5FuLL * ((v11 - (__int64)v13) >> 4)) >> 2) + 8;
    if ( v18 > 0x4EF583648CA55LL )
      v18 = 0x4EF583648CA55LL;
    if ( 0x87180ECE08A2DA5FuLL * ((v11 - (__int64)v13) >> 4) < v18 )
    {
      v19 = utl::vector<CallNotificationData,utl::allocator<CallNotificationData>>::_SetCapacity(Block);
      v11 = v37;
      v12 = (char *)Block[1];
      v13 = Block[0];
      if ( v19 )
      {
LABEL_18:
        CallNotificationData::CallNotificationData(v12, v40);
        v12 += 6640;
        Block[1] = v12;
      }
    }
    if ( v44 )
      (*(void (__fastcall **)(struct ISecurityPolicy *))(*(_QWORD *)v44 + 16LL))(v44);
    utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v41);
    ++v10;
  }
  v35 = *((_DWORD *)this + 20);
  v21 = (char *)operator new(0x40u);
  v22 = v21;
  if ( !v21 )
  {
    v9 = -2147024882;
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\ControllerMessagesPriv.h", 1156);
    BackTraceCollection::Capture(v33, -2147024882);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4497);
    if ( v13 != (_BYTE *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v34, v13, (v12 - v13) / 6640 + v12 - v13);
      operator delete(v13);
    }
    goto LABEL_39;
  }
  *(_QWORD *)(v21 + 12) = 0;
  *(_QWORD *)(v21 + 20) = 0;
  *((_DWORD *)v21 + 7) = 0;
  *((_QWORD *)v21 + 7) = 0;
  v23 = ATL::_pAtlModule;
  *((_DWORD *)v21 + 2) = 0;
  *((_QWORD *)v21 + 4) = -1;
  *((_QWORD *)v21 + 5) = -1;
  *((_QWORD *)v21 + 6) = -1;
  *(_QWORD *)v21 = &ATL::CComObject<SendPhoneStateMessage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v23 + 8LL))(v23);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 8LL))(v22);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 8LL))(v22);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
  *((_DWORD *)v22 + 6) = 18;
  v24 = (char **)(v22 + 40);
  v25 = (char *)*((_QWORD *)v22 + 4);
  if ( v25 != (char *)-1LL )
  {
    v26 = (char *)(*v24 - v25);
    *v24 = v25;
    utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v26, v25, &v26[(__int64)v26 / 6640]);
    operator delete(*((void **)v22 + 4));
  }
  *((_QWORD *)v22 + 4) = v13;
  *v24 = v12;
  *((_QWORD *)v22 + 6) = v11;
  *((_DWORD *)v22 + 14) = v35;
  v27 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 26) + 40LL))(*((_QWORD *)this + 26), v22);
  v29 = v27;
  if ( v27 < 0 )
  {
    BackTraceCollection::Capture(v28, v27);
    Log_HREvent_7(v29, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4498);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( si128.m128i_i64[0] != -1 )
    {
      v30 = _mm_srli_si128(si128, 8).m128i_u64[0] - si128.m128i_i64[0];
      utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v30, si128.m128i_i64[0], v30 / 6640 + v30);
      operator delete((void *)si128.m128i_i64[0]);
    }
    v9 = v29;
    goto LABEL_39;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( si128.m128i_i64[0] != -1 )
  {
    v31 = _mm_srli_si128(si128, 8).m128i_u64[0] - si128.m128i_i64[0];
    utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v31, si128.m128i_i64[0], v31 / 6640 + v31);
    operator delete((void *)si128.m128i_i64[0]);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v38);
  return 0;
}

```

## disassembly

```asm
0x1800474d0  push    rbp
0x1800474d2  push    rbx
0x1800474d3  push    rsi
0x1800474d4  push    rdi
0x1800474d5  push    r12
0x1800474d7  push    r13
0x1800474d9  push    r14
0x1800474db  push    r15
0x1800474dd  lea     rbp, [rsp-1988h]
0x1800474e5  mov     eax, 1A88h
0x1800474ea  call    _alloca_probe
0x1800474ef  sub     rsp, rax
0x1800474f2  movaps  [rsp+1AC0h+var_50], xmm6
0x1800474fa  mov     rax, cs:__security_cookie
0x180047501  xor     rax, rsp
0x180047504  mov     [rbp+19C0h+var_60], rax
0x18004750b  mov     r14, rcx
0x18004750e  call    cs:__imp_GetCurrentThreadId
0x180047514  cmp     [r14+0F0h], eax
0x18004751b  jz      short loc_180047543
0x18004751d  mov     r8d, 116Fh
0x180047523  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004752a  call    Log_AssertionEvent_3
0x18004752f  call    cs:__imp_GetCurrentThreadId
0x180047535  cmp     [r14+0F0h], eax
0x18004753c  jz      short loc_180047543
0x18004753e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047543  mov     rcx, [r14+108h]
0x18004754a  xor     r12d, r12d
0x18004754d  test    rcx, rcx
0x180047550  jz      short loc_18004757D
0x180047552  mov     rax, [rcx]
0x180047555  mov     rax, [rax+20h]
0x180047559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004755e  mov     rcx, [r14+108h]
0x180047565  test    rcx, rcx
0x180047568  jz      short loc_18004757D
0x18004756a  mov     rax, [rcx]
0x18004756d  mov     rax, [rax+10h]
0x180047571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047576  mov     [r14+108h], r12
0x18004757d  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180047585  lea     rdx, [rsp+1AC0h+var_1A70]
0x18004758a  mov     rcx, [r14+60h]
0x18004758e  or      r13, 0FFFFFFFFFFFFFFFFh
0x180047592  xor     r8d, r8d
0x180047595  mov     [rsp+1AC0h+var_1A60], r13
0x18004759a  movdqu  [rsp+1AC0h+var_1A70], xmm6
0x1800475a0  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x1800475a5  mov     ebx, eax
0x1800475a7  test    eax, eax
0x1800475a9  jns     short loc_1800475CF
0x1800475ab  mov     edx, eax; int
0x1800475ad  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800475b2  mov     r9d, 117Ah
0x1800475b8  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800475bf  lea     edx, [r13+2]
0x1800475c3  mov     ecx, ebx
0x1800475c5  call    Log_HREvent_7
0x1800475ca  jmp     loc_180047A09
0x1800475cf  mov     rbx, qword ptr [rsp+1AC0h+var_1A70]
0x1800475d4  mov     r15, r13
0x1800475d7  movdqu  xmmword ptr [rsp+1AC0h+Block], xmm6
0x1800475dd  mov     rdi, [rsp+1AC0h+Block+8]
0x1800475e2  mov     rsi, [rsp+1AC0h+Block]
0x1800475e7  mov     [rsp+1AC0h+var_1A78], r13
0x1800475ec  cmp     rbx, qword ptr [rsp+1AC0h+var_1A70+8]
0x1800475f1  jz      loc_18004779C
0x1800475f7  mov     [rbp+19C0h+var_88], r13
0x1800475fe  lea     rcx, [rsp+1AC0h+var_1A50]; void *
0x180047603  mov     r13, [rbx]
0x180047606  xor     eax, eax
0x180047608  mov     r8d, 19C8h; Size
0x18004760e  movdqa  [rbp+19C0h+var_80], xmm6
0x180047616  mov     [rbp+19C0h+var_70], rax
0x18004761d  mov     [rbp+19C0h+var_68], r12
0x180047624  lea     rdx, [r13+18h]; Src
0x180047628  call    memcpy_0
0x18004762d  mov     al, [r13+1B00h]
0x180047634  mov     byte ptr [rbp+19C0h+var_70], al
0x18004763a  test    al, al
0x18004763c  jz      short loc_180047658
0x18004763e  lea     rdx, [rbp+19C0h+var_88]
0x180047645  mov     rcx, r13
0x180047648  call    ?GetAssociatedDeviceIdsList@CallInfo@@QEBAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; CallInfo::GetAssociatedDeviceIdsList(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x18004764d  mov     r13d, eax
0x180047650  test    eax, eax
0x180047652  js      loc_180047710
0x180047658  mov     rcx, [rbx]; this
0x18004765b  lea     rdx, [rbp+19C0h+var_68]; struct ISecurityPolicy **
0x180047662  call    ?GetSecurityPolicy@CallInfo@@QEAAXPEAPEAUISecurityPolicy@@@Z; CallInfo::GetSecurityPolicy(ISecurityPolicy * *)
0x180047667  cmp     rdi, r15
0x18004766a  jnz     short loc_1800476C6
0x18004766c  mov     rax, 87180ECE08A2DA5Fh
0x180047676  mov     rcx, r15
0x180047679  sub     rcx, rsi
0x18004767c  sar     rcx, 4
0x180047680  imul    rcx, rax
0x180047684  mov     rax, rcx
0x180047687  shr     rax, 2
0x18004768b  imul    rdx, rax, 7
0x18004768f  mov     rax, 4EF583648CA55h
0x180047699  add     rdx, 8
0x18004769d  cmp     rdx, rax
0x1800476a0  cmova   rdx, rax
0x1800476a4  cmp     rcx, rdx
0x1800476a7  jnb     short loc_1800476DF
0x1800476a9  lea     rcx, [rsp+1AC0h+Block]
0x1800476ae  call    ?_SetCapacity@?$vector@UCallNotificationData@@V?$allocator@UCallNotificationData@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<CallNotificationData,utl::allocator<CallNotificationData>>::_SetCapacity(unsigned __int64)
0x1800476b3  mov     r15, [rsp+1AC0h+var_1A78]
0x1800476b8  mov     rdi, [rsp+1AC0h+Block+8]
0x1800476bd  mov     rsi, [rsp+1AC0h+Block]
0x1800476c2  test    al, al
0x1800476c4  jz      short loc_1800476DF
0x1800476c6  lea     rdx, [rsp+1AC0h+var_1A50]
0x1800476cb  mov     rcx, rdi
0x1800476ce  call    ??0CallNotificationData@@QEAA@$$QEAU0@@Z; CallNotificationData::CallNotificationData(CallNotificationData &&)
0x1800476d3  add     rdi, 19F0h
0x1800476da  mov     [rsp+1AC0h+Block+8], rdi
0x1800476df  mov     rcx, [rbp+19C0h+var_68]
0x1800476e6  test    rcx, rcx
0x1800476e9  jz      short loc_1800476F7
0x1800476eb  mov     rax, [rcx]
0x1800476ee  mov     rax, [rax+10h]
0x1800476f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476f7  lea     rcx, [rbp+19C0h+var_88]
0x1800476fe  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x180047703  add     rbx, 8
0x180047707  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004770b  jmp     loc_1800475EC
0x180047710  mov     edx, r13d; int
0x180047713  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180047718  mov     r9d, 1187h
0x18004771e  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047725  mov     edx, 1
0x18004772a  mov     ecx, r13d
0x18004772d  call    Log_HREvent_7
0x180047732  mov     rcx, [rbp+19C0h+var_68]
0x180047739  test    rcx, rcx
0x18004773c  jz      short loc_18004774A
0x18004773e  mov     rax, [rcx]
0x180047741  mov     rax, [rax+10h]
0x180047745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004774a  lea     rcx, [rbp+19C0h+var_88]
0x180047751  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x180047756  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004775a  jz      short loc_180047794
0x18004775c  sub     rdi, rsi
0x18004775f  mov     rax, 9DEB06C9194AA417h
0x180047769  imul    rdi
0x18004776c  add     rdx, rdi
0x18004776f  sar     rdx, 0Ch
0x180047773  mov     r8, rdx
0x180047776  shr     r8, 3Fh
0x18004777a  add     r8, rdx
0x18004777d  mov     rdx, rsi
0x180047780  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x180047785  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004778c  mov     rcx, rsi; Block
0x18004778f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047794  mov     ebx, r13d
0x180047797  jmp     loc_180047A09
0x18004779c  mov     eax, [r14+50h]
0x1800477a0  mov     ecx, 40h ; '@'; Size
0x1800477a5  mov     [rsp+1AC0h+var_1A90], eax
0x1800477a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800477ae  mov     rbx, rax
0x1800477b1  test    rax, rax
0x1800477b4  jz      loc_18004798E
0x1800477ba  mov     [rax+0Ch], r12
0x1800477be  mov     [rax+14h], r12
0x1800477c2  mov     [rax+1Ch], r12d
0x1800477c6  mov     [rax+38h], r12
0x1800477ca  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800477d1  mov     [rax+8], r12d
0x1800477d5  mov     [rax+20h], r13
0x1800477d9  mov     [rax+28h], r13
0x1800477dd  mov     [rax+30h], r13
0x1800477e1  lea     rax, ??_7?$CComObject@VSendPhoneStateMessage@@@ATL@@6B@; const ATL::CComObject<SendPhoneStateMessage>::`vftable'
0x1800477e8  mov     [rbx], rax
0x1800477eb  mov     rax, [rcx]
0x1800477ee  mov     rax, [rax+8]
0x1800477f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477f7  mov     rax, [rbx]
0x1800477fa  mov     rcx, rbx
0x1800477fd  mov     rax, [rax+8]
0x180047801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047806  mov     rax, [rbx]
0x180047809  mov     rcx, rbx
0x18004780c  mov     rax, [rax+8]
0x180047810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047815  mov     rax, [rbx]
0x180047818  mov     rcx, rbx
0x18004781b  mov     rax, [rax+10h]
0x18004781f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047824  mov     dword ptr [rbx+18h], 12h
0x18004782b  lea     r13, [rbx+28h]
0x18004782f  mov     r9, [rbx+20h]
0x180047833  mov     r12, 9DEB06C9194AA417h
0x18004783d  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180047841  jz      short loc_18004787D
0x180047843  mov     rcx, [r13+0]
0x180047847  mov     rax, r12
0x18004784a  sub     rcx, r9
0x18004784d  mov     [r13+0], r9
0x180047851  imul    rcx
0x180047854  add     rdx, rcx
0x180047857  sar     rdx, 0Ch
0x18004785b  mov     r8, rdx
0x18004785e  shr     r8, 3Fh
0x180047862  add     r8, rdx
0x180047865  mov     rdx, r9
0x180047868  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x18004786d  mov     rcx, [rbx+20h]; Block
0x180047871  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047878  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004787d  mov     eax, [rsp+1AC0h+var_1A90]
0x180047881  mov     rdx, rbx
0x180047884  mov     [rbx+20h], rsi
0x180047888  mov     [r13+0], rdi
0x18004788c  mov     [rbx+30h], r15
0x180047890  mov     [rbx+38h], eax
0x180047893  mov     rcx, [r14+0D0h]
0x18004789a  mov     rax, [rcx]
0x18004789d  mov     rax, [rax+28h]
0x1800478a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478a6  mov     edi, eax
0x1800478a8  test    eax, eax
0x1800478aa  jns     short loc_180047928
0x1800478ac  mov     edx, eax; int
0x1800478ae  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800478b3  mov     r9d, 1192h
0x1800478b9  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800478c0  mov     edx, 1
0x1800478c5  mov     ecx, edi
0x1800478c7  call    Log_HREvent_7
0x1800478cc  mov     rcx, [rbx]
0x1800478cf  mov     rax, [rcx+10h]
0x1800478d3  mov     rcx, rbx
0x1800478d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478db  movq    rbx, xmm6
0x1800478e0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800478e4  jz      short loc_180047921
0x1800478e6  psrldq  xmm6, 8
0x1800478eb  mov     rax, r12
0x1800478ee  movq    rcx, xmm6
0x1800478f3  sub     rcx, rbx
0x1800478f6  imul    rcx
0x1800478f9  add     rdx, rcx
0x1800478fc  sar     rdx, 0Ch
0x180047900  mov     r8, rdx
0x180047903  shr     r8, 3Fh
0x180047907  add     r8, rdx
0x18004790a  mov     rdx, rbx
0x18004790d  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x180047912  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047919  mov     rcx, rbx; Block
0x18004791c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047921  mov     ebx, edi
0x180047923  jmp     loc_180047A09
0x180047928  mov     rax, [rbx]
0x18004792b  mov     rcx, rbx
0x18004792e  mov     rax, [rax+10h]
0x180047932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047937  movq    rbx, xmm6
0x18004793c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180047940  jz      short loc_18004797D
0x180047942  psrldq  xmm6, 8
0x180047947  mov     rax, r12
0x18004794a  movq    rcx, xmm6
0x18004794f  sub     rcx, rbx
0x180047952  imul    rcx
0x180047955  add     rdx, rcx
0x180047958  sar     rdx, 0Ch
0x18004795c  mov     r8, rdx
0x18004795f  shr     r8, 3Fh
0x180047963  add     r8, rdx
0x180047966  mov     rdx, rbx
0x180047969  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x18004796e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047975  mov     rcx, rbx; Block
0x180047978  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004797d  lea     rcx, [rsp+1AC0h+var_1A70]
0x180047982  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180047987  xor     eax, eax
0x180047989  jmp     loc_180047A15
0x18004798e  mov     ebx, 8007000Eh
0x180047993  lea     r8, aOnecoreuapNetP_24; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004799a  mov     ecx, ebx
0x18004799c  mov     r9d, 484h
0x1800479a2  mov     edx, 1
0x1800479a7  call    Log_HREvent_7
0x1800479ac  mov     edx, ebx; int
0x1800479ae  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800479b3  mov     r9d, 1191h
0x1800479b9  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800479c0  mov     edx, 1
0x1800479c5  mov     ecx, ebx
0x1800479c7  call    Log_HREvent_7
0x1800479cc  cmp     rsi, r13
  ... truncated ...
```
