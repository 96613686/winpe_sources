# PhoneController::_UpdateVerbs(void)

- ea: `0x18004a790`
- end: `0x18004ad6c`
- name: `?_UpdateVerbs@PhoneController@@IEAAJXZ`
- size: `1500`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180034e08`
- `0x18004a5b4`

## callees

- `0x180006e94`
- `0x18000e1a4`
- `0x180010664`
- `0x1800107d8`
- `0x18002c574`
- `0x18002c580`
- `0x180035af0`
- `0x180036b60`
- `0x18003c7d8`
- `0x18004a790`
- `0x18005292c`
- `0x180052a58`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a7db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a7db`

## string_xrefs

- `0x18004a7cf`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a84c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a933`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004ab59`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004acbc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_UpdateVerbs(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  int AllCalls; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // ebx
  __int64 v8; // rsi
  int v9; // edx
  _QWORD *v10; // rdi
  __int64 v11; // rbx
  int v12; // r15d
  int v13; // r8d
  int v14; // r14d
  __int64 v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // r12d
  _QWORD *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  struct CallInfo *v21; // rdi
  __int64 v22; // rcx
  struct CallInfo *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  struct CallInfo *v26; // rdi
  int v27; // eax
  int v28; // eax
  __int64 v29; // r14
  _QWORD *i; // rax
  __int64 v31; // r14
  _QWORD *j; // rax
  __int64 v33; // r8
  __int64 v34; // r14
  int v35; // r8d
  int v36; // r9d
  int v37; // r10d
  int v38; // r11d
  unsigned int v39; // edx
  int v40; // eax
  int GlobalDialAvailability; // eax
  BackTraceCollection *v42; // rcx
  unsigned int v43; // esi
  unsigned int v44; // r15d
  struct CallInfo *v45; // [rsp+30h] [rbp-89h] BYREF
  int v46; // [rsp+38h] [rbp-81h] BYREF
  int v47; // [rsp+3Ch] [rbp-7Dh]
  int v48; // [rsp+40h] [rbp-79h]
  int v49; // [rsp+44h] [rbp-75h]
  __int128 v50; // [rsp+48h] [rbp-71h] BYREF
  __int128 v51; // [rsp+58h] [rbp-61h]
  __int128 v52; // [rsp+68h] [rbp-51h]
  _OWORD v53[3]; // [rsp+80h] [rbp-39h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v55; // [rsp+C0h] [rbp+7h]

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3589);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v50 = 0;
  v51 = 0;
  v52 = 0;
  PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)&v50, 0);
  v3 = *((_QWORD *)this + 12);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v55 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v3, &si128, 0);
  v6 = AllCalls;
  if ( AllCalls < 0 )
  {
    BackTraceCollection::Capture(v5, AllCalls);
    Log_HREvent_7(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3602);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    return v6;
  }
  v8 = si128.m128i_i64[0];
  v9 = 0;
  v47 = 0;
  v10 = (_QWORD *)si128.m128i_i64[0];
  v11 = 0;
  v46 = 0;
  v12 = 0;
  v48 = 0;
  v13 = 73;
  while ( v10 != (_QWORD *)si128.m128i_i64[1] )
  {
    v14 = *(_DWORD *)(*v10 + 6624LL);
    *(_DWORD *)(*v10 + 3052LL) = v14;
    if ( !v11 )
    {
      v15 = *v10;
      v16 = *(_DWORD *)(*v10 + 3040LL);
      if ( v16 <= 6 && _bittest(&v13, v16) && v15 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 8LL))(*v10);
        v9 = v47;
        v13 = 73;
        v11 = v15;
      }
    }
    if ( (v14 & 8) != 0 )
    {
      v5 = (BackTraceCollection *)*(unsigned int *)(*v10 + 3040LL);
      if ( (unsigned int)v5 <= 6 && _bittest(&v13, (unsigned int)v5) )
      {
        v9 = 1;
        v47 = 1;
      }
      else
      {
        v14 &= ~8u;
      }
    }
    v12 |= v14;
    ++v10;
  }
  v17 = DWORD1(v50);
  if ( !v11 )
  {
    if ( HIDWORD(v51) != DWORD1(v50) )
    {
      Log_AssertionEvent_3(v5, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3654);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v18 = (_QWORD *)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &v45, 2, 0);
    v19 = *v18;
    if ( *v18 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(*v18);
      v11 = v19;
    }
    if ( v45 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v45 + 16LL))(v45);
    v9 = v47;
  }
  if ( (v12 & 0x18) == 0x18 )
    v12 |= 0x20u;
  v49 = v12 & 0x20;
  if ( (v12 & 0x10) != 0 )
  {
    if ( (v12 & 0x20) != 0 || (_DWORD)v50 + DWORD1(v51) + DWORD2(v51) && !v9 || (_DWORD)v51 )
    {
      v46 = 1;
      v12 &= ~0x10u;
    }
    else
    {
      v46 = 0;
    }
  }
  if ( (v12 & 8) != 0 && v17 )
  {
    v48 = 1;
    v12 &= ~8u;
  }
  if ( HIDWORD(v50) && v11 )
  {
    v20 = *((_QWORD *)this + 12);
    v45 = 0;
    PhoneCallStorage::FindCallByState(v20, &v45, 1, 0);
    v21 = v45;
    if ( !(unsigned int)PhoneController::_CanDoCompositeVerbs(this, (const struct CallInfo *)v11, v45) )
    {
      *((_DWORD *)v21 + 763) |= 4u;
      v12 |= 4u;
      *(_DWORD *)(v11 + 3052) |= 4u;
    }
    if ( v21 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( v17 && v11 )
  {
    v22 = *((_QWORD *)this + 12);
    v45 = 0;
    PhoneCallStorage::FindCallByState(v22, &v45, 4, 0);
    v23 = v45;
    if ( !(unsigned int)PhoneController::_CanDoCompositeVerbs(this, (const struct CallInfo *)v11, v45) )
    {
      *((_DWORD *)v23 + 763) |= 4u;
      v12 |= 4u;
      *(_DWORD *)(v11 + 3052) |= 4u;
    }
    if ( v23 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = *((_QWORD *)this + 12);
  v45 = 0;
  PhoneCallStorage::FindCallByState(v24, &v45, 1, 0);
  v26 = v45;
  if ( v45 )
  {
    v27 = *((_DWORD *)v45 + 763);
    if ( (v27 & 4) != 0 )
    {
      v25 = 1024;
      *((_DWORD *)v45 + 763) = v27 | 0x400;
      v12 |= 0x400u;
    }
  }
  v28 = HIDWORD(v51);
  if ( (_DWORD)v52 && HIDWORD(v51) > 1 )
  {
    v29 = *((_QWORD *)this + 12);
    utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v45, v29 + 48);
    for ( i = *(_QWORD **)(v29 + 24); i != (_QWORD *)(v29 + 24); i = (_QWORD *)*i )
      *(_DWORD *)(i[2] + 3052LL) &= ~0x40u;
    utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>((volatile __int32 **)&v45);
    v28 = HIDWORD(v51);
    v12 &= ~0x40u;
  }
  if ( (v12 & 0x80u) != 0 && (int)v51 + v28 > v17 )
  {
    if ( !v11 )
    {
      Log_AssertionEvent_3(v25, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3750);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v31 = *((_QWORD *)this + 12);
    utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v45, v31 + 48);
    for ( j = *(_QWORD **)(v31 + 24); j != (_QWORD *)(v31 + 24); j = (_QWORD *)*j )
    {
      v33 = j[2];
      if ( *(_QWORD *)(v33 + 6640) != *(_QWORD *)(v11 + 6640) )
        *(_DWORD *)(v33 + 3052) &= ~0x80u;
    }
    utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>((volatile __int32 **)&v45);
    v34 = *(_QWORD *)PhoneCallStorage::FindCallByStateAndVerbSupport(
                       *((_QWORD *)this + 12),
                       (unsigned int)&v45,
                       7,
                       128,
                       0);
    if ( v45 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v45 + 16LL))(v45);
    if ( !v34 )
      v12 &= ~0x80u;
  }
  v35 = v49;
  v36 = v48;
  if ( v49 || v46 || v48 )
  {
    v37 = v47;
    v38 = 73;
    while ( v8 != si128.m128i_i64[1] )
    {
      v39 = *(_DWORD *)(*(_QWORD *)v8 + 3040LL);
      v40 = *(_DWORD *)(*(_QWORD *)v8 + 3052LL);
      if ( v39 <= 6 && _bittest(&v38, v39) )
      {
        if ( (v40 & 8) == 0 )
          goto LABEL_90;
        if ( v35 )
          v40 |= 0x20u;
        if ( v36 )
          v40 &= ~8u;
      }
      else
      {
        if ( (v40 & 0x10) == 0 )
          goto LABEL_90;
        v40 &= 0xFFFFFFCF;
        if ( v37 && v35 )
          v40 |= 0x20u;
      }
      *(_DWORD *)(*(_QWORD *)v8 + 3052LL) = v40;
LABEL_90:
      v8 += 8;
    }
  }
  v46 = 0;
  v53[0] = v50;
  v53[1] = v51;
  v53[2] = v52;
  GlobalDialAvailability = PhoneController::_GetGlobalDialAvailability(
                             this,
                             &GUID_00000000_0000_0000_0000_000000000000,
                             v53,
                             &v46);
  v43 = GlobalDialAvailability;
  if ( GlobalDialAvailability >= 0 )
  {
    if ( v46 )
      v44 = v12 & 0xFFFFFFFE;
    else
      v44 = v12 | 1;
    *((_DWORD *)this + 20) = v44;
    if ( v26 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v26 + 16LL))(v26);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v42, GlobalDialAvailability);
    Log_HREvent_7(v43, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3814);
    if ( v26 )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v26 + 16LL))(v26);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return v43;
  }
}

```

## disassembly

```asm
0x18004a790  push    rbp
0x18004a792  push    rbx
0x18004a793  push    rsi
0x18004a794  push    rdi
0x18004a795  push    r12
0x18004a797  push    r13
0x18004a799  push    r14
0x18004a79b  push    r15
0x18004a79d  lea     rbp, [rsp-1Fh]
0x18004a7a2  sub     rsp, 0D8h
0x18004a7a9  mov     rax, cs:__security_cookie
0x18004a7b0  xor     rax, rsp
0x18004a7b3  mov     [rbp+57h+var_48], rax
0x18004a7b7  mov     r13, rcx
0x18004a7ba  call    cs:__imp_GetCurrentThreadId
0x18004a7c0  cmp     [r13+0F0h], eax
0x18004a7c7  jz      short loc_18004A7EF
0x18004a7c9  mov     r8d, 0E05h
0x18004a7cf  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a7d6  call    Log_AssertionEvent_3
0x18004a7db  call    cs:__imp_GetCurrentThreadId
0x18004a7e1  cmp     [r13+0F0h], eax
0x18004a7e8  jz      short loc_18004A7EF
0x18004a7ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a7ef  xorps   xmm0, xmm0
0x18004a7f2  lea     r8, [rbp+57h+var_C8]; struct PH_PHONE_CALL_COUNTS *
0x18004a7f6  xor     r9d, r9d; struct ISecurityToken *
0x18004a7f9  mov     rcx, r13; this
0x18004a7fc  movups  [rbp+57h+var_C8], xmm0
0x18004a800  movups  [rbp+57h+var_B8], xmm0
0x18004a804  lea     edx, [r9+1]; int
0x18004a808  movups  [rbp+57h+var_A8], xmm0
0x18004a80c  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x18004a811  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004a819  lea     rdx, [rbp+57h+var_60]
0x18004a81d  mov     rcx, [r13+60h]
0x18004a821  xor     r8d, r8d
0x18004a824  movdqu  [rbp+57h+var_60], xmm0
0x18004a829  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x18004a831  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x18004a836  xor     r14d, r14d
0x18004a839  mov     ebx, eax
0x18004a83b  test    eax, eax
0x18004a83d  jns     short loc_18004A86E
0x18004a83f  mov     edx, eax; int
0x18004a841  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004a846  mov     r9d, 0E12h
0x18004a84c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a853  lea     edx, [r14+1]
0x18004a857  mov     ecx, ebx
0x18004a859  call    Log_HREvent_7
0x18004a85e  lea     rcx, [rbp+57h+var_60]
0x18004a862  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004a867  mov     eax, ebx
0x18004a869  jmp     loc_18004AD4C
0x18004a86e  mov     rsi, qword ptr [rbp+57h+var_60]
0x18004a872  mov     edx, r14d
0x18004a875  mov     [rbp+57h+var_D4], edx
0x18004a878  mov     rdi, rsi
0x18004a87b  mov     rbx, r14
0x18004a87e  mov     [rsp+110h+var_D8], r14d
0x18004a883  mov     r15d, r14d
0x18004a886  mov     [rbp+57h+var_D0], r14d
0x18004a88a  mov     r8d, 49h ; 'I'
0x18004a890  cmp     rdi, qword ptr [rbp+57h+var_60+8]
0x18004a894  jz      loc_18004A91B
0x18004a89a  mov     rax, [rdi]
0x18004a89d  mov     r14d, [rax+19E0h]
0x18004a8a4  mov     [rax+0BECh], r14d
0x18004a8ab  test    rbx, rbx
0x18004a8ae  jnz     short loc_18004A8E7
0x18004a8b0  mov     r12, [rdi]
0x18004a8b3  mov     eax, [r12+0BE0h]
0x18004a8bb  cmp     eax, 6
0x18004a8be  ja      short loc_18004A8E7
0x18004a8c0  bt      r8d, eax
0x18004a8c4  jnb     short loc_18004A8E7
0x18004a8c6  test    r12, r12
0x18004a8c9  jz      short loc_18004A8E7
0x18004a8cb  mov     rax, [r12]
0x18004a8cf  mov     rcx, r12
0x18004a8d2  mov     rax, [rax+8]
0x18004a8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8db  mov     edx, [rbp+57h+var_D4]
0x18004a8de  mov     r8d, 49h ; 'I'
0x18004a8e4  mov     rbx, r12
0x18004a8e7  test    r14b, 8
0x18004a8eb  jz      short loc_18004A90F
0x18004a8ed  mov     rax, [rdi]
0x18004a8f0  mov     ecx, [rax+0BE0h]
0x18004a8f6  cmp     ecx, 6
0x18004a8f9  ja      short loc_18004A90B
0x18004a8fb  bt      r8d, ecx
0x18004a8ff  jnb     short loc_18004A90B
0x18004a901  mov     edx, 1
0x18004a906  mov     [rbp+57h+var_D4], edx
0x18004a909  jmp     short loc_18004A90F
0x18004a90b  and     r14d, 0FFFFFFF7h
0x18004a90f  or      r15d, r14d
0x18004a912  add     rdi, 8
0x18004a916  jmp     loc_18004A890
0x18004a91b  mov     r12d, dword ptr [rbp+57h+var_C8+4]
0x18004a91f  xor     r14d, r14d
0x18004a922  test    rbx, rbx
0x18004a925  jnz     short loc_18004A98C
0x18004a927  cmp     dword ptr [rbp+57h+var_B8+0Ch], r12d
0x18004a92b  jz      short loc_18004A944
0x18004a92d  mov     r8d, 0E46h
0x18004a933  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a93a  call    Log_AssertionEvent_3
0x18004a93f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a944  mov     rcx, [r13+60h]
0x18004a948  lea     rdx, [rsp+110h+var_E0]
0x18004a94d  xor     r9d, r9d
0x18004a950  lea     r8d, [r9+2]
0x18004a954  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x18004a959  mov     rdi, [rax]
0x18004a95c  test    rdi, rdi
0x18004a95f  jz      short loc_18004A973
0x18004a961  mov     rax, [rdi]
0x18004a964  mov     rcx, rdi
0x18004a967  mov     rax, [rax+8]
0x18004a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a970  mov     rbx, rdi
0x18004a973  mov     rcx, [rsp+110h+var_E0]
0x18004a978  test    rcx, rcx
0x18004a97b  jz      short loc_18004A989
0x18004a97d  mov     rax, [rcx]
0x18004a980  mov     rax, [rax+10h]
0x18004a984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a989  mov     edx, [rbp+57h+var_D4]
0x18004a98c  mov     eax, r15d
0x18004a98f  and     eax, 18h
0x18004a992  cmp     al, 18h
0x18004a994  jnz     short loc_18004A99A
0x18004a996  or      r15d, 20h
0x18004a99a  mov     eax, r15d
0x18004a99d  and     eax, 20h
0x18004a9a0  mov     [rbp+57h+var_CC], eax
0x18004a9a3  test    r15b, 10h
0x18004a9a7  jz      short loc_18004A9D5
0x18004a9a9  test    eax, eax
0x18004a9ab  jnz     short loc_18004A9C9
0x18004a9ad  mov     ecx, dword ptr [rbp+57h+var_B8+8]
0x18004a9b0  add     ecx, dword ptr [rbp+57h+var_B8+4]
0x18004a9b3  add     ecx, dword ptr [rbp+57h+var_C8]
0x18004a9b6  jz      short loc_18004A9BC
0x18004a9b8  test    edx, edx
0x18004a9ba  jz      short loc_18004A9C9
0x18004a9bc  cmp     dword ptr [rbp+57h+var_B8], r14d
0x18004a9c0  jnz     short loc_18004A9C9
0x18004a9c2  mov     [rsp+110h+var_D8], r14d
0x18004a9c7  jmp     short loc_18004A9D5
0x18004a9c9  mov     [rsp+110h+var_D8], 1
0x18004a9d1  and     r15d, 0FFFFFFEFh
0x18004a9d5  test    r15b, 8
0x18004a9d9  jz      short loc_18004A9EB
0x18004a9db  test    r12d, r12d
0x18004a9de  jz      short loc_18004A9EB
0x18004a9e0  mov     [rbp+57h+var_D0], 1
0x18004a9e7  and     r15d, 0FFFFFFF7h
0x18004a9eb  cmp     dword ptr [rbp+57h+var_C8+0Ch], r14d
0x18004a9ef  jz      short loc_18004AA4D
0x18004a9f1  test    rbx, rbx
0x18004a9f4  jz      short loc_18004AA4D
0x18004a9f6  mov     rcx, [r13+60h]
0x18004a9fa  lea     rdx, [rsp+110h+var_E0]
0x18004a9ff  xor     r9d, r9d
0x18004aa02  mov     [rsp+110h+var_E0], r14
0x18004aa07  lea     r8d, [r9+1]
0x18004aa0b  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x18004aa10  mov     rdi, [rsp+110h+var_E0]
0x18004aa15  mov     rdx, rbx; struct CallInfo *
0x18004aa18  mov     r8, rdi; struct CallInfo *
0x18004aa1b  mov     rcx, r13; this
0x18004aa1e  call    ?_CanDoCompositeVerbs@PhoneController@@IEBAHPEBVCallInfo@@0@Z; PhoneController::_CanDoCompositeVerbs(CallInfo const *,CallInfo const *)
0x18004aa23  test    eax, eax
0x18004aa25  jnz     short loc_18004AA39
0x18004aa27  or      dword ptr [rdi+0BECh], 4
0x18004aa2e  or      r15d, 4
0x18004aa32  or      dword ptr [rbx+0BECh], 4
0x18004aa39  test    rdi, rdi
0x18004aa3c  jz      short loc_18004AA4D
0x18004aa3e  mov     rax, [rdi]
0x18004aa41  mov     rcx, rdi
0x18004aa44  mov     rax, [rax+10h]
0x18004aa48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa4d  test    r12d, r12d
0x18004aa50  jz      short loc_18004AAAE
0x18004aa52  test    rbx, rbx
0x18004aa55  jz      short loc_18004AAAE
0x18004aa57  mov     rcx, [r13+60h]
0x18004aa5b  lea     rdx, [rsp+110h+var_E0]
0x18004aa60  xor     r9d, r9d
0x18004aa63  mov     [rsp+110h+var_E0], r14
0x18004aa68  lea     r8d, [r9+4]
0x18004aa6c  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x18004aa71  mov     rdi, [rsp+110h+var_E0]
0x18004aa76  mov     rdx, rbx; struct CallInfo *
0x18004aa79  mov     r8, rdi; struct CallInfo *
0x18004aa7c  mov     rcx, r13; this
0x18004aa7f  call    ?_CanDoCompositeVerbs@PhoneController@@IEBAHPEBVCallInfo@@0@Z; PhoneController::_CanDoCompositeVerbs(CallInfo const *,CallInfo const *)
0x18004aa84  test    eax, eax
0x18004aa86  jnz     short loc_18004AA9A
0x18004aa88  or      dword ptr [rdi+0BECh], 4
0x18004aa8f  or      r15d, 4
0x18004aa93  or      dword ptr [rbx+0BECh], 4
0x18004aa9a  test    rdi, rdi
0x18004aa9d  jz      short loc_18004AAAE
0x18004aa9f  mov     rax, [rdi]
0x18004aaa2  mov     rcx, rdi
0x18004aaa5  mov     rax, [rax+10h]
0x18004aaa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaae  mov     rcx, [r13+60h]
0x18004aab2  lea     rdx, [rsp+110h+var_E0]
0x18004aab7  xor     r9d, r9d
0x18004aaba  mov     [rsp+110h+var_E0], r14
0x18004aabf  lea     r8d, [r9+1]
0x18004aac3  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x18004aac8  mov     rdi, [rsp+110h+var_E0]
0x18004aacd  test    rdi, rdi
0x18004aad0  jz      short loc_18004AAEC
0x18004aad2  mov     eax, [rdi+0BECh]
0x18004aad8  test    al, 4
0x18004aada  jz      short loc_18004AAEC
0x18004aadc  mov     ecx, 400h
0x18004aae1  or      eax, ecx
0x18004aae3  mov     [rdi+0BECh], eax
0x18004aae9  or      r15d, ecx
0x18004aaec  mov     eax, dword ptr [rbp+57h+var_B8+0Ch]
0x18004aaef  cmp     dword ptr [rbp+57h+var_A8], r14d
0x18004aaf3  jbe     short loc_18004AB39
0x18004aaf5  cmp     eax, 1
0x18004aaf8  jbe     short loc_18004AB39
0x18004aafa  mov     r14, [r13+60h]
0x18004aafe  lea     rcx, [rsp+110h+var_E0]
0x18004ab03  lea     rdx, [r14+30h]
0x18004ab07  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x18004ab0c  lea     rcx, [r14+18h]
0x18004ab10  mov     rax, [rcx]
0x18004ab13  cmp     rax, rcx
0x18004ab16  jz      short loc_18004AB28
0x18004ab18  mov     rdx, [rax+10h]
0x18004ab1c  and     dword ptr [rdx+0BECh], 0FFFFFFBFh
0x18004ab23  mov     rax, [rax]
0x18004ab26  jmp     short loc_18004AB13
0x18004ab28  lea     rcx, [rsp+110h+var_E0]
0x18004ab2d  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x18004ab32  mov     eax, dword ptr [rbp+57h+var_B8+0Ch]
0x18004ab35  and     r15d, 0FFFFFFBFh
0x18004ab39  test    r15b, r15b
0x18004ab3c  jns     loc_18004ABF8
0x18004ab42  add     eax, dword ptr [rbp+57h+var_B8]
0x18004ab45  cmp     eax, r12d
0x18004ab48  jbe     loc_18004ABF8
0x18004ab4e  test    rbx, rbx
0x18004ab51  jnz     short loc_18004AB6A
0x18004ab53  mov     r8d, 0EA6h
0x18004ab59  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004ab60  call    Log_AssertionEvent_3
0x18004ab65  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004ab6a  mov     r14, [r13+60h]
0x18004ab6e  lea     rcx, [rsp+110h+var_E0]
0x18004ab73  lea     rdx, [r14+30h]
0x18004ab77  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x18004ab7c  lea     rcx, [r14+18h]
0x18004ab80  mov     rax, [rcx]
0x18004ab83  cmp     rax, rcx
0x18004ab86  jz      short loc_18004ABAA
0x18004ab88  mov     r8, [rax+10h]
0x18004ab8c  mov     rdx, [rbx+19F0h]
0x18004ab93  cmp     [r8+19F0h], rdx
0x18004ab9a  jz      short loc_18004ABA5
0x18004ab9c  btr     dword ptr [r8+0BECh], 7
0x18004aba5  mov     rax, [rax]
0x18004aba8  jmp     short loc_18004AB83
0x18004abaa  lea     rcx, [rsp+110h+var_E0]
0x18004abaf  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x18004abb4  mov     rcx, [r13+60h]
0x18004abb8  lea     rdx, [rsp+110h+var_E0]
0x18004abbd  mov     r9d, 80h
0x18004abc3  mov     [rsp+110h+var_F0], 0
0x18004abcc  lea     r8d, [r9-79h]
0x18004abd0  call    ?FindCallByStateAndVerbSupport@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@W4CallVerbs@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByStateAndVerbSupport(PH_CALLSTATE,CallVerbs,ISecurityToken *)
0x18004abd5  mov     rcx, [rsp+110h+var_E0]
0x18004abda  mov     r14, [rax]
0x18004abdd  test    rcx, rcx
0x18004abe0  jz      short loc_18004ABEE
0x18004abe2  mov     rax, [rcx]
0x18004abe5  mov     rax, [rax+10h]
0x18004abe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abee  test    r14, r14
0x18004abf1  jnz     short loc_18004ABF8
0x18004abf3  btr     r15d, 7
0x18004abf8  mov     r8d, [rbp+57h+var_CC]
0x18004abfc  mov     r9d, [rbp+57h+var_D0]
0x18004ac00  test    r8d, r8d
0x18004ac03  jnz     short loc_18004AC11
0x18004ac05  cmp     [rsp+110h+var_D8], r8d
0x18004ac0a  jnz     short loc_18004AC11
  ... truncated ...
```
