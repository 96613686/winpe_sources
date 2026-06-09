# PhoneController::_SendDeferredAssociatedDevicesChangeNotification(void)

- ea: `0x180046e70`
- end: `0x1800473b1`
- name: `?_SendDeferredAssociatedDevicesChangeNotification@PhoneController@@MEAAJXZ`
- size: `1345`
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
- `0x180046e70`
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

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046ed9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046eb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046ed9`

## string_xrefs

- `0x1800472fe`: `onecoreuap\net\phone\phoneservice\service\lib\ControllerMessagesPriv.h`
- `0x180046ecd`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180046f2b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047093`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047224`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047324`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendDeferredAssociatedDevicesChangeNotification(PhoneController *this)
{
  __int64 v2; // rcx
  __m128i si128; // xmm6
  __int64 v4; // rcx
  int AllCalls; // eax
  BackTraceCollection *v6; // rcx
  unsigned int v7; // ebx
  CallInfo **v8; // rbx
  __int64 v9; // r15
  _BYTE *v10; // rsi
  char *v11; // rdi
  CallInfo *v12; // r13
  int AssociatedDeviceIdsList; // eax
  BackTraceCollection *v14; // rcx
  unsigned int v15; // r13d
  unsigned __int64 v16; // rdx
  char v17; // al
  __int64 v18; // rcx
  char *v19; // rax
  char *v20; // rbx
  struct ATL::CAtlModule *v21; // rcx
  char *v22; // r9
  char **v23; // r13
  char *v24; // rcx
  int v25; // eax
  BackTraceCollection *v26; // rcx
  unsigned int v27; // edi
  signed __int64 v28; // rcx
  signed __int64 v29; // rcx
  BackTraceCollection *v31; // rcx
  __int64 v32; // rcx
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __m128i v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h]
  _BYTE v38[6600]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+1A38h] [rbp+1938h] BYREF
  __m128i v40; // [rsp+1A40h] [rbp+1940h]
  __int64 v41; // [rsp+1A50h] [rbp+1950h]
  struct ISecurityPolicy *v42; // [rsp+1A58h] [rbp+1958h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4505);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v4 = *((_QWORD *)this + 12);
  v37 = -1;
  v36 = si128;
  AllCalls = PhoneCallStorage::GetAllCalls(v4, &v36, 0);
  v7 = AllCalls;
  if ( AllCalls < 0 )
  {
    BackTraceCollection::Capture(v6, AllCalls);
    Log_HREvent_7(v7, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4509);
LABEL_37:
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v36);
    return v7;
  }
  v8 = (CallInfo **)v36.m128i_i64[0];
  v9 = -1;
  *(__m128i *)Block = si128;
  v10 = (_BYTE *)si128.m128i_i64[0];
  v35 = -1;
  v11 = (char *)si128.m128i_i64[1];
  while ( v8 != (CallInfo **)v36.m128i_i64[1] )
  {
    v12 = *v8;
    if ( *((_BYTE *)*v8 + 6912) )
    {
      v39 = -1;
      v41 = 0;
      v40 = si128;
      v42 = 0;
      memcpy_0(v38, (char *)v12 + 24, sizeof(v38));
      LOBYTE(v41) = 1;
      AssociatedDeviceIdsList = CallInfo::GetAssociatedDeviceIdsList(v12, &v39);
      v15 = AssociatedDeviceIdsList;
      if ( AssociatedDeviceIdsList < 0 )
      {
        BackTraceCollection::Capture(v14, AssociatedDeviceIdsList);
        Log_HREvent_7(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4523);
        if ( v42 )
          (*(void (__fastcall **)(struct ISecurityPolicy *))(*(_QWORD *)v42 + 16LL))(v42);
        utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v39);
        if ( v10 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v18, v10, (v11 - v10) / 6640 + v11 - v10);
          operator delete(v10);
        }
        v7 = v15;
        goto LABEL_37;
      }
      CallInfo::GetSecurityPolicy(*v8, &v42);
      if ( v11 != (char *)v9 )
        goto LABEL_15;
      v16 = 7 * ((0x87180ECE08A2DA5FuLL * ((v9 - (__int64)v10) >> 4)) >> 2) + 8;
      if ( v16 > 0x4EF583648CA55LL )
        v16 = 0x4EF583648CA55LL;
      if ( 0x87180ECE08A2DA5FuLL * ((v9 - (__int64)v10) >> 4) < v16 )
      {
        v17 = utl::vector<CallNotificationData,utl::allocator<CallNotificationData>>::_SetCapacity(Block);
        v9 = v35;
        v11 = (char *)Block[1];
        v10 = Block[0];
        if ( v17 )
        {
LABEL_15:
          CallNotificationData::CallNotificationData(v11, v38);
          v11 += 6640;
          Block[1] = v11;
        }
      }
      if ( v42 )
        (*(void (__fastcall **)(struct ISecurityPolicy *))(*(_QWORD *)v42 + 16LL))(v42);
      utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_Uninit(&v39);
    }
    ++v8;
  }
  v19 = (char *)operator new(0x38u);
  v20 = v19;
  if ( !v19 )
  {
    v7 = -2147024882;
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\ControllerMessagesPriv.h", 1197);
    BackTraceCollection::Capture(v31, -2147024882);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4533);
    if ( v10 != (_BYTE *)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v32, v10, (v11 - v10) / 6640 + v11 - v10);
      operator delete(v10);
    }
    goto LABEL_37;
  }
  *(_QWORD *)(v19 + 12) = 0;
  *(_QWORD *)(v19 + 20) = 0;
  *((_DWORD *)v19 + 7) = 0;
  v21 = ATL::_pAtlModule;
  *((_DWORD *)v19 + 2) = 0;
  *((_QWORD *)v19 + 4) = -1;
  *((_QWORD *)v19 + 5) = -1;
  *((_QWORD *)v19 + 6) = -1;
  *(_QWORD *)v19 = &ATL::CComObject<SendAssociatedDevicesChangedMessage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v21 + 8LL))(v21);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 8LL))(v20);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 8LL))(v20);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
  v22 = (char *)*((_QWORD *)v20 + 4);
  v23 = (char **)(v20 + 40);
  if ( v22 != (char *)-1LL )
  {
    v24 = (char *)(*v23 - v22);
    *v23 = v22;
    utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v24, v22, &v24[(__int64)v24 / 6640]);
    operator delete(*((void **)v20 + 4));
  }
  *((_QWORD *)v20 + 4) = v10;
  *v23 = v11;
  *((_QWORD *)v20 + 6) = v9;
  *((_DWORD *)v20 + 6) = 39;
  v25 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 26) + 40LL))(*((_QWORD *)this + 26), v20);
  v27 = v25;
  if ( v25 < 0 )
  {
    BackTraceCollection::Capture(v26, v25);
    Log_HREvent_7(v27, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4534);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
    if ( si128.m128i_i64[0] != -1 )
    {
      v28 = _mm_srli_si128(si128, 8).m128i_u64[0] - si128.m128i_i64[0];
      utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v28, si128.m128i_i64[0], v28 / 6640 + v28);
      operator delete((void *)si128.m128i_i64[0]);
    }
    v7 = v27;
    goto LABEL_37;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
  if ( si128.m128i_i64[0] != -1 )
  {
    v29 = _mm_srli_si128(si128, 8).m128i_u64[0] - si128.m128i_i64[0];
    utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(v29, si128.m128i_i64[0], v29 / 6640 + v29);
    operator delete((void *)si128.m128i_i64[0]);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v36);
  return 0;
}

```

## disassembly

```asm
0x180046e70  mov     [rsp-8+arg_8], rbx
0x180046e75  mov     [rsp-8+arg_10], rsi
0x180046e7a  push    rbp
0x180046e7b  push    rdi
0x180046e7c  push    r12
0x180046e7e  push    r13
0x180046e80  push    r15
0x180046e82  lea     rbp, [rsp-1980h]
0x180046e8a  mov     eax, 1A80h
0x180046e8f  call    _alloca_probe
0x180046e94  sub     rsp, rax
0x180046e97  movaps  [rsp+1AA0h+var_30], xmm6
0x180046e9f  mov     rax, cs:__security_cookie
0x180046ea6  xor     rax, rsp
0x180046ea9  mov     [rbp+19A0h+var_40], rax
0x180046eb0  mov     r13, rcx
0x180046eb3  mov     [rsp+1AA0h+var_1A70], rcx
0x180046eb8  call    cs:__imp_GetCurrentThreadId
0x180046ebe  cmp     [r13+0F0h], eax
0x180046ec5  jz      short loc_180046EED
0x180046ec7  mov     r8d, 1199h
0x180046ecd  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180046ed4  call    Log_AssertionEvent_3
0x180046ed9  call    cs:__imp_GetCurrentThreadId
0x180046edf  cmp     [r13+0F0h], eax
0x180046ee6  jz      short loc_180046EED
0x180046ee8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046eed  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180046ef5  lea     rdx, [rsp+1AA0h+var_1A50]
0x180046efa  mov     rcx, [r13+60h]
0x180046efe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046f02  xor     r8d, r8d
0x180046f05  mov     [rsp+1AA0h+var_1A40], rdi
0x180046f0a  movdqu  [rsp+1AA0h+var_1A50], xmm6
0x180046f10  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x180046f15  xor     r12d, r12d
0x180046f18  mov     ebx, eax
0x180046f1a  test    eax, eax
0x180046f1c  jns     short loc_180046F41
0x180046f1e  mov     edx, eax; int
0x180046f20  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180046f25  mov     r9d, 119Dh
0x180046f2b  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180046f32  lea     edx, [rdi+2]
0x180046f35  mov     ecx, ebx
0x180046f37  call    Log_HREvent_7
0x180046f3c  jmp     loc_180047375
0x180046f41  mov     rbx, qword ptr [rsp+1AA0h+var_1A50]
0x180046f46  mov     r15, rdi
0x180046f49  movdqu  xmmword ptr [rsp+1AA0h+Block], xmm6
0x180046f4f  mov     rsi, [rsp+1AA0h+Block]
0x180046f54  mov     [rsp+1AA0h+var_1A58], rdi
0x180046f59  mov     rdi, [rsp+1AA0h+Block+8]
0x180046f5e  cmp     rbx, qword ptr [rsp+1AA0h+var_1A50+8]
0x180046f63  jz      loc_180047111
0x180046f69  mov     r13, [rbx]
0x180046f6c  cmp     [r13+1B00h], r12b
0x180046f73  jz      loc_18004707C
0x180046f79  xor     eax, eax
0x180046f7b  mov     [rbp+19A0h+var_68], 0FFFFFFFFFFFFFFFFh
0x180046f86  lea     rdx, [r13+18h]; Src
0x180046f8a  mov     [rbp+19A0h+var_50], rax
0x180046f91  mov     r8d, 19C8h; Size
0x180046f97  movdqa  [rbp+19A0h+var_60], xmm6
0x180046f9f  lea     rcx, [rsp+1AA0h+var_1A30]; void *
0x180046fa4  mov     [rbp+19A0h+var_48], r12
0x180046fab  call    memcpy_0
0x180046fb0  lea     rdx, [rbp+19A0h+var_68]
0x180046fb7  mov     byte ptr [rbp+19A0h+var_50], 1
0x180046fbe  mov     rcx, r13
0x180046fc1  call    ?GetAssociatedDeviceIdsList@CallInfo@@QEBAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; CallInfo::GetAssociatedDeviceIdsList(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x180046fc6  mov     r13d, eax
0x180046fc9  test    eax, eax
0x180046fcb  js      loc_180047085
0x180046fd1  mov     rcx, [rbx]; this
0x180046fd4  lea     rdx, [rbp+19A0h+var_48]; struct ISecurityPolicy **
0x180046fdb  call    ?GetSecurityPolicy@CallInfo@@QEAAXPEAPEAUISecurityPolicy@@@Z; CallInfo::GetSecurityPolicy(ISecurityPolicy * *)
0x180046fe0  cmp     rdi, r15
0x180046fe3  jnz     short loc_18004703F
0x180046fe5  mov     rax, 87180ECE08A2DA5Fh
0x180046fef  mov     rcx, r15
0x180046ff2  sub     rcx, rsi
0x180046ff5  sar     rcx, 4
0x180046ff9  imul    rcx, rax
0x180046ffd  mov     rax, rcx
0x180047000  shr     rax, 2
0x180047004  imul    rdx, rax, 7
0x180047008  mov     rax, 4EF583648CA55h
0x180047012  add     rdx, 8
0x180047016  cmp     rdx, rax
0x180047019  cmova   rdx, rax
0x18004701d  cmp     rcx, rdx
0x180047020  jnb     short loc_180047058
0x180047022  lea     rcx, [rsp+1AA0h+Block]
0x180047027  call    ?_SetCapacity@?$vector@UCallNotificationData@@V?$allocator@UCallNotificationData@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<CallNotificationData,utl::allocator<CallNotificationData>>::_SetCapacity(unsigned __int64)
0x18004702c  mov     r15, [rsp+1AA0h+var_1A58]
0x180047031  mov     rdi, [rsp+1AA0h+Block+8]
0x180047036  mov     rsi, [rsp+1AA0h+Block]
0x18004703b  test    al, al
0x18004703d  jz      short loc_180047058
0x18004703f  lea     rdx, [rsp+1AA0h+var_1A30]
0x180047044  mov     rcx, rdi
0x180047047  call    ??0CallNotificationData@@QEAA@$$QEAU0@@Z; CallNotificationData::CallNotificationData(CallNotificationData &&)
0x18004704c  add     rdi, 19F0h
0x180047053  mov     [rsp+1AA0h+Block+8], rdi
0x180047058  mov     rcx, [rbp+19A0h+var_48]
0x18004705f  test    rcx, rcx
0x180047062  jz      short loc_180047070
0x180047064  mov     rax, [rcx]
0x180047067  mov     rax, [rax+10h]
0x18004706b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047070  lea     rcx, [rbp+19A0h+var_68]
0x180047077  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x18004707c  add     rbx, 8
0x180047080  jmp     loc_180046F5E
0x180047085  mov     edx, r13d; int
0x180047088  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004708d  mov     r9d, 11ABh
0x180047093  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004709a  mov     edx, 1
0x18004709f  mov     ecx, r13d
0x1800470a2  call    Log_HREvent_7
0x1800470a7  mov     rcx, [rbp+19A0h+var_48]
0x1800470ae  test    rcx, rcx
0x1800470b1  jz      short loc_1800470BF
0x1800470b3  mov     rax, [rcx]
0x1800470b6  mov     rax, [rax+10h]
0x1800470ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470bf  lea     rcx, [rbp+19A0h+var_68]
0x1800470c6  call    ?_Uninit@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_Uninit(void)
0x1800470cb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800470cf  jz      short loc_180047109
0x1800470d1  sub     rdi, rsi
0x1800470d4  mov     rax, 9DEB06C9194AA417h
0x1800470de  imul    rdi
0x1800470e1  add     rdx, rdi
0x1800470e4  sar     rdx, 0Ch
0x1800470e8  mov     r8, rdx
0x1800470eb  shr     r8, 3Fh
0x1800470ef  add     r8, rdx
0x1800470f2  mov     rdx, rsi
0x1800470f5  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x1800470fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047101  mov     rcx, rsi; Block
0x180047104  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047109  mov     ebx, r13d
0x18004710c  jmp     loc_180047375
0x180047111  mov     ecx, 38h ; '8'; Size
0x180047116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004711b  mov     rbx, rax
0x18004711e  test    rax, rax
0x180047121  jz      loc_1800472F9
0x180047127  mov     [rax+0Ch], r12
0x18004712b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004712f  mov     [rax+14h], r12
0x180047133  mov     [rax+1Ch], r12d
0x180047137  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18004713e  mov     [rax+8], r12d
0x180047142  mov     [rax+20h], r13
0x180047146  mov     [rax+28h], r13
0x18004714a  mov     [rax+30h], r13
0x18004714e  lea     rax, ??_7?$CComObject@VSendAssociatedDevicesChangedMessage@@@ATL@@6B@; const ATL::CComObject<SendAssociatedDevicesChangedMessage>::`vftable'
0x180047155  mov     [rbx], rax
0x180047158  mov     rax, [rcx]
0x18004715b  mov     rax, [rax+8]
0x18004715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047164  mov     rax, [rbx]
0x180047167  mov     rcx, rbx
0x18004716a  mov     rax, [rax+8]
0x18004716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047173  mov     rax, [rbx]
0x180047176  mov     rcx, rbx
0x180047179  mov     rax, [rax+8]
0x18004717d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047182  mov     rax, [rbx]
0x180047185  mov     rcx, rbx
0x180047188  mov     rax, [rax+10h]
0x18004718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047191  mov     r9, [rbx+20h]
0x180047195  lea     r13, [rbx+28h]
0x180047199  mov     r12, 9DEB06C9194AA417h
0x1800471a3  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800471a7  jz      short loc_1800471E3
0x1800471a9  mov     rcx, [r13+0]
0x1800471ad  mov     rax, r12
0x1800471b0  sub     rcx, r9
0x1800471b3  mov     [r13+0], r9
0x1800471b7  imul    rcx
0x1800471ba  add     rdx, rcx
0x1800471bd  sar     rdx, 0Ch
0x1800471c1  mov     r8, rdx
0x1800471c4  shr     r8, 3Fh
0x1800471c8  add     r8, rdx
0x1800471cb  mov     rdx, r9
0x1800471ce  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x1800471d3  mov     rcx, [rbx+20h]; Block
0x1800471d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800471de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800471e3  mov     rcx, [rsp+1AA0h+var_1A70]
0x1800471e8  mov     rdx, rbx
0x1800471eb  mov     [rbx+20h], rsi
0x1800471ef  mov     [r13+0], rdi
0x1800471f3  mov     [rbx+30h], r15
0x1800471f7  mov     dword ptr [rbx+18h], 27h ; '''
0x1800471fe  mov     rcx, [rcx+0D0h]
0x180047205  mov     rax, [rcx]
0x180047208  mov     rax, [rax+28h]
0x18004720c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047211  mov     edi, eax
0x180047213  test    eax, eax
0x180047215  jns     short loc_180047293
0x180047217  mov     edx, eax; int
0x180047219  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004721e  mov     r9d, 11B6h
0x180047224  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004722b  mov     edx, 1
0x180047230  mov     ecx, edi
0x180047232  call    Log_HREvent_7
0x180047237  mov     rcx, [rbx]
0x18004723a  mov     rax, [rcx+10h]
0x18004723e  mov     rcx, rbx
0x180047241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047246  movq    rbx, xmm6
0x18004724b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004724f  jz      short loc_18004728C
0x180047251  psrldq  xmm6, 8
0x180047256  mov     rax, r12
0x180047259  movq    rcx, xmm6
0x18004725e  sub     rcx, rbx
0x180047261  imul    rcx
0x180047264  add     rdx, rcx
0x180047267  sar     rdx, 0Ch
0x18004726b  mov     r8, rdx
0x18004726e  shr     r8, 3Fh
0x180047272  add     r8, rdx
0x180047275  mov     rdx, rbx
0x180047278  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x18004727d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047284  mov     rcx, rbx; Block
0x180047287  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004728c  mov     ebx, edi
0x18004728e  jmp     loc_180047375
0x180047293  mov     rax, [rbx]
0x180047296  mov     rcx, rbx
0x180047299  mov     rax, [rax+10h]
0x18004729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472a2  movq    rbx, xmm6
0x1800472a7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800472ab  jz      short loc_1800472E8
0x1800472ad  psrldq  xmm6, 8
0x1800472b2  mov     rax, r12
0x1800472b5  movq    rcx, xmm6
0x1800472ba  sub     rcx, rbx
0x1800472bd  imul    rcx
0x1800472c0  add     rdx, rcx
0x1800472c3  sar     rdx, 0Ch
0x1800472c7  mov     r8, rdx
0x1800472ca  shr     r8, 3Fh
0x1800472ce  add     r8, rdx
0x1800472d1  mov     rdx, rbx
0x1800472d4  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x1800472d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800472e0  mov     rcx, rbx; Block
0x1800472e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800472e8  lea     rcx, [rsp+1AA0h+var_1A50]
0x1800472ed  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800472f2  xor     eax, eax
0x1800472f4  jmp     loc_180047381
0x1800472f9  mov     ebx, 8007000Eh
0x1800472fe  lea     r8, aOnecoreuapNetP_24; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047305  mov     ecx, ebx
0x180047307  mov     r9d, 4ADh
0x18004730d  mov     edx, 1
0x180047312  call    Log_HREvent_7
0x180047317  mov     edx, ebx; int
0x180047319  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004731e  mov     r9d, 11B5h
0x180047324  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004732b  mov     edx, 1
0x180047330  mov     ecx, ebx
0x180047332  call    Log_HREvent_7
0x180047337  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004733b  jz      short loc_180047375
0x18004733d  sub     rdi, rsi
0x180047340  mov     rax, 9DEB06C9194AA417h
0x18004734a  imul    rdi
0x18004734d  add     rdx, rdi
0x180047350  sar     rdx, 0Ch
0x180047354  mov     r8, rdx
0x180047357  shr     r8, 3Fh
0x18004735b  add     r8, rdx
0x18004735e  mov     rdx, rsi
0x180047361  call    ??$_RangeDestroyApc@V?$allocator@UCallNotificationData@@@utl@@@utl@@YAXAEAV?$allocator@UCallNotificationData@@@0@PEAUCallNotificationData@@_K@Z; utl::_RangeDestroyApc<utl::allocator<CallNotificationData>>(utl::allocator<CallNotificationData> &,CallNotificationData *,unsigned __int64)
0x180047366  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004736d  mov     rcx, rsi; Block
0x180047370  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047375  lea     rcx, [rsp+1AA0h+var_1A50]
0x18004737a  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004737f  mov     eax, ebx
0x180047381  mov     rcx, [rbp+19A0h+var_40]
  ... truncated ...
```
