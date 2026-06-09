# PhoneController::AcceptIncoming(PhoneAcceptCallParameters const &,ISecurityToken *)

- ea: `0x1800211b0`
- end: `0x180021a22`
- name: `?AcceptIncoming@PhoneController@@UEAAJAEBUPhoneAcceptCallParameters@@PEAUISecurityToken@@@Z`
- size: `2162`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct PhoneAcceptCallParameters *, struct ISecurityToken *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x1800091a8`
- `0x18001de50`
- `0x18001f514`
- `0x1800211b0`
- `0x18002c580`
- `0x1800340b0`
- `0x1800349d8`
- `0x180034b10`
- `0x180035af0`
- `0x18003617c`
- `0x1800368d0`
- `0x180036b60`
- `0x180037efc`
- `0x1800380bc`
- `0x18003dc20`
- `0x180046b60`
- `0x18004ae58`
- `0x18004b150`
- `0x18004ef10`
- `0x1800524c8`
- `0x18005292c`
- `0x180052bf4`
- `0x180053040`
- `0x180053254`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## string_xrefs

- `0x18002122c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180021262`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002130f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180021353`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800213a8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180021495`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180021506`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002156d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800215a7`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002170d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180021743`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18002179b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800211fe`: `PhoneController::AcceptIncoming`

## pseudocode

```c
__int64 __fastcall PhoneController::AcceptIncoming(
        PhoneController *this,
        const struct PhoneAcceptCallParameters *a2,
        struct ISecurityToken *a3)
{
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // r12d
  unsigned int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // r9
  struct PhoneLine *v12; // rbx
  __int64 v13; // rcx
  struct PhoneLine **v14; // rax
  struct PhoneLine *v15; // rdi
  BackTraceCollection *v16; // rcx
  __int64 v17; // r9
  int v18; // eax
  int v19; // eax
  BackTraceCollection *v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  BackTraceCollection *v23; // rcx
  __int64 v24; // r8
  BackTraceCollection *v25; // rcx
  struct PhoneLine *v26; // rsi
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  int v30; // eax
  BackTraceCollection *v31; // rcx
  __int64 v32; // rcx
  struct CallInfo *v33; // rdi
  struct CallInfo **v34; // rax
  struct CallInfo *v35; // r12
  struct CallInfo **v36; // rax
  struct CallInfo *v37; // r12
  BackTraceCollection *v38; // rcx
  struct CallInfo **v39; // rax
  struct CallInfo *v40; // r12
  int v41; // eax
  int v42; // eax
  BackTraceCollection *v43; // rcx
  __int64 v44; // r9
  int v45; // eax
  BackTraceCollection *v46; // rcx
  int v47; // ecx
  unsigned int v48; // eax
  int v49; // r9d
  int v50; // eax
  BackTraceCollection *v51; // rcx
  int v52; // ecx
  unsigned int v53; // eax
  int v54; // r9d
  int v55; // eax
  BackTraceCollection *v56; // rcx
  int v57; // eax
  BackTraceCollection *v58; // rcx
  int v59; // ecx
  unsigned int v60; // eax
  int v61; // r9d
  int v62; // eax
  BackTraceCollection *v63; // rcx
  unsigned int v65; // [rsp+40h] [rbp-C0h] BYREF
  struct PhoneLine *v66; // [rsp+48h] [rbp-B8h] BYREF
  struct CallInfo *v67[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct ISecurityToken *v68; // [rsp+60h] [rbp-A0h]
  __int128 v69; // [rsp+68h] [rbp-98h] BYREF
  __int128 v70; // [rsp+78h] [rbp-88h]
  __int128 v71; // [rsp+88h] [rbp-78h]
  void *Block[2]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v73; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+AAh] [rbp-56h]
  int v75; // [rsp+B2h] [rbp-4Eh]
  __int16 v76; // [rsp+B6h] [rbp-4Ah]
  LPCRITICAL_SECTION v77[8]; // [rsp+C0h] [rbp-40h] BYREF

  v68 = a3;
  memset_0(v77, 0, sizeof(v77));
  AutoLockWithWatchdog::AutoLockWithWatchdog(
    (AutoLockWithWatchdog *)v77,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 224),
    "PhoneController::AcceptIncoming");
  v6 = PhoneController::_CheckControllerActive(this);
  v8 = 0;
  v9 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    Log_HREvent_7(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6873);
    goto LABEL_104;
  }
  if ( (*((_DWORD *)this + 20) & 0x400) == 0 )
  {
    v10 = -2147020579;
    BackTraceCollection::Capture(v7, -2147020579);
    v11 = 6876;
LABEL_5:
    Log_HREvent_7(v10, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v11);
LABEL_6:
    v9 = v10;
    goto LABEL_104;
  }
  v12 = 0;
  v13 = *((_QWORD *)this + 12);
  v66 = 0;
  if ( *(_DWORD *)a2 )
  {
    v14 = (struct PhoneLine **)PhoneCallStorage::FindCall(v13, v67, a2, a3);
    v15 = *v14;
    if ( *v14 )
    {
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v15 + 8LL))(*v14);
      v12 = v15;
    }
    else
    {
      v15 = 0;
    }
    v16 = v67[0];
    if ( v67[0] )
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v67[0] + 16LL))(v67[0]);
    if ( !v15 )
    {
      v10 = -2147024809;
      BackTraceCollection::Capture(v16, -2147024809);
      v11 = 6883;
      goto LABEL_5;
    }
    if ( (*((_DWORD *)v15 + 763) & 0x400) == 0 )
    {
      v10 = -2147020579;
      BackTraceCollection::Capture(v16, -2147020579);
      v17 = 6884;
LABEL_17:
      Log_HREvent_7(v10, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v17);
LABEL_18:
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v12 + 16LL))(v12);
      goto LABEL_6;
    }
LABEL_23:
    v19 = PhoneController::_CheckLineOwnershipForCall(v16, v12, a3);
    v10 = v19;
    if ( v19 < 0 )
    {
      BackTraceCollection::Capture(v20, v19);
      v21 = 6891;
      goto LABEL_25;
    }
    v22 = VerifyCallCanBeControlledIfDeviceIdWasSpecified(v12, (const unsigned __int16 *)a2 + 8);
    v10 = v22;
    if ( v22 < 0 )
    {
      BackTraceCollection::Capture(v23, v22);
      v21 = 6893;
LABEL_25:
      Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v21);
      if ( !v12 )
        goto LABEL_6;
      goto LABEL_18;
    }
    if ( *((_DWORD *)a2 + 2) == 1 )
    {
      if ( *((_DWORD *)v12 + 817) != 1 )
      {
        v10 = -2147024809;
        BackTraceCollection::Capture(v23, -2147024809);
        v17 = 6898;
        goto LABEL_17;
      }
    }
    else if ( *((_DWORD *)v12 + 817) != 1 )
    {
      goto LABEL_35;
    }
    if ( !*((_DWORD *)a2 + 2) )
      *((_DWORD *)v12 + 1709) = 1;
LABEL_35:
    *((_DWORD *)v12 + 1249) = *((_DWORD *)a2 + 3);
    Block[0] = &v73;
    Block[1] = &v73;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v73 = 0;
    if ( a2 != (const struct PhoneAcceptCallParameters *)-16LL )
    {
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)a2 + v24 + 8) );
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
    {
      v10 = -2147024882;
      BackTraceCollection::Capture(v25, -2147024882);
      Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6912);
      goto LABEL_40;
    }
    v66 = 0;
    CallInfo::GetPhoneLine(v12, &v66);
    v26 = v66;
    v27 = *((unsigned int *)a2 + 1);
    *(_OWORD *)v67 = *(_OWORD *)((char *)v66 + 88);
    v28 = PhoneController::_EnablePhoneCallAudio(this, v67, v27, 1);
    if ( v28 < 0 )
      Log_HREvent_7((unsigned int)v28, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6917);
    v69 = 0;
    v70 = 0;
    v71 = 0;
    PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)&v69, 0);
    v65 = v70 + HIDWORD(v70);
    if ( !(_DWORD)v69 && !(_DWORD)v70 && (unsigned int)(v70 + HIDWORD(v70)) < 2 )
    {
      v29 = PhoneController::_RejectPendingVideoRequests(this);
      if ( v29 < 0 )
        Log_HREvent_7((unsigned int)v29, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6931);
      v30 = PhoneController::_AcceptCall(this, v12, *((unsigned int *)a2 + 2), Block);
      v10 = v30;
      if ( v30 < 0 )
      {
        BackTraceCollection::Capture(v31, v30);
        Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6935);
        PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_40;
      }
      goto LABEL_100;
    }
    v32 = *((_QWORD *)this + 12);
    LODWORD(v66) = 0;
    v67[0] = 0;
    PhoneCallStorage::FindCallForOtherVoipApp(v32, v67, v12);
    v33 = v67[0];
    if ( v67[0] )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy>::GetImpl'::`2'::impl) )
        v8 = 1;
      LODWORD(v66) = v8;
    }
    else
    {
      v34 = (struct CallInfo **)PhoneCallStorage::GetActiveCall(*((_QWORD *)this + 12), v67);
      v35 = *v34;
      if ( *v34 )
      {
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v35 + 8LL))(*v34);
        v33 = v35;
      }
      if ( v67[0] )
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v67[0] + 16LL))(v67[0]);
    }
    if ( !v33 )
    {
      v36 = (struct CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), v67, 2, 0);
      v37 = *v36;
      if ( *v36 )
      {
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v37 + 8LL))(*v36);
        v33 = v37;
      }
      v38 = v67[0];
      if ( v67[0] )
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v67[0] + 16LL))(v67[0]);
      if ( !v33 )
      {
        if ( v65 < 2 )
          goto LABEL_71;
        v39 = (struct CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), v67, 4, 0);
        v40 = *v39;
        if ( *v39 )
        {
          (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v40 + 8LL))(*v39);
          v33 = v40;
        }
        v38 = v67[0];
        if ( v67[0] )
          (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v67[0] + 16LL))(v67[0]);
        if ( !v33 )
        {
LABEL_71:
          v10 = -2147019873;
          BackTraceCollection::Capture(v38, -2147019873);
          Log_HREvent_7(2147947423LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6970);
          PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
          (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_40:
          if ( Block[0] != &v73 )
            operator delete(Block[0]);
          goto LABEL_18;
        }
      }
    }
    v41 = PhoneController::_RejectPendingVideoRequests(this);
    if ( v41 < 0 )
      Log_HREvent_7((unsigned int)v41, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6974);
    if ( v65 >= 2 )
    {
      if ( (unsigned int)PhoneController::_CanDoCompositeVerbs(this, v12, v33) )
      {
        if ( (*((_BYTE *)v12 + 3052) & 4) != 0 )
        {
          v52 = *((_DWORD *)a2 + 3);
          LODWORD(v66) = *((_DWORD *)v12 + 767);
          v53 = *((_DWORD *)v33 + 768);
          if ( !v53 )
            v53 = *((_DWORD *)v33 + 767);
          v54 = *((_DWORD *)a2 + 2);
          v65 = v53;
          v55 = PhoneController::_UseDropAcceptForIncoming(
                  (_DWORD)this,
                  (unsigned int)&v65,
                  (unsigned int)&v66,
                  v54,
                  v52,
                  (__int64)Block,
                  (__int64)v68);
          v8 = v55;
          if ( v55 < 0 )
          {
            BackTraceCollection::Capture(v56, v55);
            v44 = 7023;
            goto LABEL_78;
          }
        }
        else
        {
          v57 = PhoneController::_AcceptIncomingCallAndDropOtherLineCall(this);
          v8 = v57;
          if ( v57 < 0 )
          {
            BackTraceCollection::Capture(v58, v57);
            v44 = 7031;
            goto LABEL_78;
          }
        }
      }
      else
      {
        v59 = *((_DWORD *)a2 + 3);
        LODWORD(v66) = *((_DWORD *)v12 + 767);
        v60 = *((_DWORD *)v33 + 768);
        if ( !v60 )
          v60 = *((_DWORD *)v33 + 767);
        v61 = *((_DWORD *)a2 + 2);
        v65 = v60;
        v62 = PhoneController::_UseDropAcceptForIncoming(
                (_DWORD)this,
                (unsigned int)&v65,
                (unsigned int)&v66,
                v61,
                v59,
                (__int64)Block,
                (__int64)v68);
        v8 = v62;
        if ( v62 < 0 )
        {
          BackTraceCollection::Capture(v63, v62);
          v44 = 7044;
          goto LABEL_78;
        }
      }
    }
    else if ( (unsigned int)PhoneController::_CanDoCompositeVerbs(this, v33, v12) )
    {
      v42 = PhoneController::_AcceptCall(this, v12, *((unsigned int *)a2 + 2), Block);
      v8 = v42;
      if ( v42 < 0 )
      {
        BackTraceCollection::Capture(v43, v42);
        v44 = 6984;
LABEL_78:
        Log_HREvent_7(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v44);
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v33 + 16LL))(v33);
        PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
LABEL_101:
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( Block[0] != &v73 )
          operator delete(Block[0]);
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v12 + 16LL))(v12);
        v9 = v8;
        goto LABEL_104;
      }
    }
    else if ( (*((_BYTE *)v33 + 3052) & 8) == 0 || (_DWORD)v66 )
    {
      v47 = *((_DWORD *)a2 + 3);
      LODWORD(v66) = *((_DWORD *)v12 + 767);
      v48 = *((_DWORD *)v33 + 768);
      if ( !v48 )
        v48 = *((_DWORD *)v33 + 767);
      v49 = *((_DWORD *)a2 + 2);
      v65 = v48;
      v50 = PhoneController::_UseDropAcceptForIncoming(
              (_DWORD)this,
              (unsigned int)&v65,
              (unsigned int)&v66,
              v49,
              v47,
              (__int64)Block,
              (__int64)v68);
      v8 = v50;
      if ( v50 < 0 )
      {
        BackTraceCollection::Capture(v51, v50);
        v44 = 7003;
        goto LABEL_78;
      }
    }
    else
    {
      v45 = PhoneController::_HoldActiveCallAcceptIncomingCall(this, v33, v12, (__int64)Block);
      v8 = v45;
      if ( v45 < 0 )
      {
        BackTraceCollection::Capture(v46, v45);
        v44 = 6991;
        goto LABEL_78;
      }
    }
    *((_DWORD *)this + 68) = 1;
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v33 + 16LL))(v33);
    v8 = 0;
LABEL_100:
    *((_DWORD *)v12 + 1655) = 1;
    goto LABEL_101;
  }
  v18 = PhoneCallStorage::FindRelevantCallForVerb(v13, 1024, &v66, a3);
  v9 = v18;
  if ( v18 >= 0 )
  {
    v12 = v66;
    goto LABEL_23;
  }
  BackTraceCollection::Capture(v16, v18);
  Log_HREvent_7(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6888);
  if ( v66 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v66 + 16LL))(v66);
LABEL_104:
  AutoLockWithWatchdog::~AutoLockWithWatchdog(v77);
  return v9;
}

```

## disassembly

```asm
0x1800211b0  mov     [rsp-8+arg_18], rbx
0x1800211b5  push    rbp
0x1800211b6  push    rsi
0x1800211b7  push    rdi
0x1800211b8  push    r12
0x1800211ba  push    r13
0x1800211bc  push    r14
0x1800211be  push    r15
0x1800211c0  lea     rbp, [rsp-10h]
0x1800211c5  sub     rsp, 110h
0x1800211cc  mov     rax, cs:__security_cookie
0x1800211d3  xor     rax, rsp
0x1800211d6  mov     [rbp+40h+var_40], rax
0x1800211da  mov     r13, rdx
0x1800211dd  mov     [rsp+140h+var_E0], r8
0x1800211e2  xor     edx, edx; Val
0x1800211e4  mov     rsi, r8
0x1800211e7  mov     r15, rcx
0x1800211ea  lea     rcx, [rbp+40h+var_80]; void *
0x1800211ee  lea     r8d, [rdx+40h]; Size
0x1800211f2  call    memset_0
0x1800211f7  lea     rdx, [r15+0E0h]; struct utl::recursive_mutex *
0x1800211fe  lea     r8, aPhonecontrolle_70; "PhoneController::AcceptIncoming"
0x180021205  lea     rcx, [rbp+40h+var_80]; this
0x180021209  call    ??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z; AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)
0x18002120e  mov     rcx, r15; this
0x180021211  call    ?_CheckControllerActive@PhoneController@@IEAAJXZ; PhoneController::_CheckControllerActive(void)
0x180021216  xor     r12d, r12d
0x180021219  mov     ebx, eax
0x18002121b  test    eax, eax
0x18002121d  jns     short loc_180021244
0x18002121f  mov     edx, eax; int
0x180021221  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180021226  mov     r9d, 1AD9h
0x18002122c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180021233  lea     edx, [r12+1]
0x180021238  mov     ecx, ebx
0x18002123a  call    Log_HREvent_7
0x18002123f  jmp     loc_1800219F0
0x180021244  mov     r14d, 400h
0x18002124a  test    [r15+50h], r14d
0x18002124e  jnz     short loc_180021279
0x180021250  mov     edi, 800710DDh
0x180021255  mov     edx, edi; int
0x180021257  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002125c  mov     r9d, 1ADCh
0x180021262  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180021269  xor     edx, edx
0x18002126b  mov     ecx, edi
0x18002126d  call    Log_HREvent_7
0x180021272  mov     ebx, edi
0x180021274  jmp     loc_1800219F0
0x180021279  mov     rbx, r12
0x18002127c  mov     rcx, [r15+60h]
0x180021280  mov     r9, rsi
0x180021283  mov     [rsp+140h+var_F8], rbx
0x180021288  cmp     [r13+0], r12d
0x18002128c  jz      loc_180021333
0x180021292  mov     r8, r13
0x180021295  lea     rdx, [rsp+140h+var_F0]
0x18002129a  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x18002129f  mov     rdi, [rax]
0x1800212a2  test    rdi, rdi
0x1800212a5  jnz     short loc_1800212AC
0x1800212a7  mov     rdi, r12
0x1800212aa  jmp     short loc_1800212BE
0x1800212ac  mov     rax, [rdi]
0x1800212af  mov     rcx, rdi
0x1800212b2  mov     rax, [rax+8]
0x1800212b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212bb  mov     rbx, rdi
0x1800212be  mov     rcx, [rsp+140h+var_F0]
0x1800212c3  test    rcx, rcx
0x1800212c6  jz      short loc_1800212D4
0x1800212c8  mov     rax, [rcx]
0x1800212cb  mov     rax, [rax+10h]
0x1800212cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212d4  test    rdi, rdi
0x1800212d7  jnz     short loc_1800212F0
0x1800212d9  mov     edi, 80070057h
0x1800212de  mov     edx, edi; int
0x1800212e0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800212e5  mov     r9d, 1AE3h
0x1800212eb  jmp     loc_180021262
0x1800212f0  test    [rdi+0BECh], r14d
0x1800212f7  jnz     loc_18002138A
0x1800212fd  mov     edi, 800710DDh
0x180021302  mov     edx, edi; int
0x180021304  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180021309  mov     r9d, 1AE4h
0x18002130f  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180021316  xor     edx, edx
0x180021318  mov     ecx, edi
0x18002131a  call    Log_HREvent_7
0x18002131f  mov     rax, [rbx]
0x180021322  mov     rcx, rbx
0x180021325  mov     rax, [rax+10h]
0x180021329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002132e  jmp     loc_180021272
0x180021333  lea     r8, [rsp+140h+var_F8]
0x180021338  mov     edx, r14d
0x18002133b  call    ?FindRelevantCallForVerb@PhoneCallStorage@@QEAAJW4CallVerbs@@PEAPEAVCallInfo@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindRelevantCallForVerb(CallVerbs,CallInfo * *,ISecurityToken *)
0x180021340  mov     ebx, eax
0x180021342  test    eax, eax
0x180021344  jns     short loc_180021385
0x180021346  mov     edx, eax; int
0x180021348  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002134d  mov     r9d, 1AE8h
0x180021353  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002135a  mov     edx, 1
0x18002135f  mov     ecx, ebx
0x180021361  call    Log_HREvent_7
0x180021366  mov     rcx, [rsp+140h+var_F8]
0x18002136b  test    rcx, rcx
0x18002136e  jz      loc_1800219F0
0x180021374  mov     rax, [rcx]
0x180021377  mov     rax, [rax+10h]
0x18002137b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021380  jmp     loc_1800219F0
0x180021385  mov     rbx, [rsp+140h+var_F8]
0x18002138a  mov     r8, rsi; struct ISecurityToken *
0x18002138d  mov     rdx, rbx; struct CallInfo *
0x180021390  call    ?_CheckLineOwnershipForCall@PhoneController@@AEAAJPEAVCallInfo@@PEAUISecurityToken@@@Z; PhoneController::_CheckLineOwnershipForCall(CallInfo *,ISecurityToken *)
0x180021395  mov     edi, eax
0x180021397  test    eax, eax
0x180021399  jns     short loc_1800213C9
0x18002139b  mov     edx, eax; int
0x18002139d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800213a2  mov     r9d, 1AEBh
0x1800213a8  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800213af  mov     edx, 1
0x1800213b4  mov     ecx, edi
0x1800213b6  call    Log_HREvent_7
0x1800213bb  test    rbx, rbx
0x1800213be  jz      loc_180021272
0x1800213c4  jmp     loc_18002131F
0x1800213c9  lea     rsi, [r13+10h]
0x1800213cd  mov     rcx, rbx; struct CallInfo *
0x1800213d0  mov     rdx, rsi; unsigned __int16 *
0x1800213d3  call    ?VerifyCallCanBeControlledIfDeviceIdWasSpecified@@YAJPEAVCallInfo@@PEBG@Z; VerifyCallCanBeControlledIfDeviceIdWasSpecified(CallInfo *,ushort const *)
0x1800213d8  mov     edi, eax
0x1800213da  test    eax, eax
0x1800213dc  jns     short loc_1800213ED
0x1800213de  mov     edx, eax; int
0x1800213e0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800213e5  mov     r9d, 1AEDh
0x1800213eb  jmp     short loc_1800213A8
0x1800213ed  mov     r14d, 1
0x1800213f3  cmp     [r13+8], r14d
0x1800213f7  jnz     short loc_180021419
0x1800213f9  cmp     [rbx+0CC4h], r14d
0x180021400  jz      short loc_180021422
0x180021402  mov     edi, 80070057h
0x180021407  mov     edx, edi; int
0x180021409  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002140e  mov     r9d, 1AF2h
0x180021414  jmp     loc_18002130F
0x180021419  cmp     [rbx+0CC4h], r14d
0x180021420  jnz     short loc_18002142F
0x180021422  cmp     [r13+8], r12d
0x180021426  jnz     short loc_18002142F
0x180021428  mov     [rbx+1AB4h], r14d
0x18002142f  mov     eax, [r13+0Ch]
0x180021433  mov     [rbx+1384h], eax
0x180021439  lea     rax, [rbp+40h+var_98]
0x18002143d  mov     [rbp+40h+Block], rax
0x180021441  lea     rax, [rbp+40h+var_98]
0x180021445  mov     [rbp+40h+var_A0], rax
0x180021449  mov     [rbp+40h+var_96], r12
0x18002144d  mov     [rbp+40h+var_8E], r12d
0x180021451  mov     [rbp+40h+var_8A], r12w
0x180021456  mov     [rbp+40h+var_98], r12w
0x18002145b  test    rsi, rsi
0x18002145e  jz      short loc_180021470
0x180021460  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021464  inc     r8
0x180021467  cmp     [rsi+r8*2], r12w
0x18002146c  jnz     short loc_180021464
0x18002146e  jmp     short loc_180021473
0x180021470  mov     r8, r12
0x180021473  mov     rdx, rsi
0x180021476  lea     rcx, [rbp+40h+Block]
0x18002147a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002147f  test    al, al
0x180021481  jnz     short loc_1800214C7
0x180021483  mov     edi, 8007000Eh
0x180021488  mov     edx, edi; int
0x18002148a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18002148f  mov     r9d, 1B00h
0x180021495  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002149c  xor     edx, edx
0x18002149e  mov     ecx, edi
0x1800214a0  call    Log_HREvent_7
0x1800214a5  mov     rcx, [rbp+40h+Block]; Block
0x1800214a9  lea     rax, [rbp+40h+var_98]
0x1800214ad  cmp     rcx, rax
0x1800214b0  jz      loc_18002131F
0x1800214b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800214bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800214c2  jmp     loc_18002131F
0x1800214c7  lea     rdx, [rsp+140h+var_F8]; struct PhoneLine **
0x1800214cc  mov     [rsp+140h+var_F8], r12
0x1800214d1  mov     rcx, rbx; this
0x1800214d4  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x1800214d9  mov     rsi, [rsp+140h+var_F8]
0x1800214de  lea     rdx, [rsp+140h+var_F0]
0x1800214e3  mov     r8d, [r13+4]
0x1800214e7  mov     r9d, r14d
0x1800214ea  mov     rcx, r15
0x1800214ed  movups  xmm0, xmmword ptr [rsi+58h]
0x1800214f1  movdqu  xmmword ptr [rsp+140h+var_F0], xmm0
0x1800214f7  call    ?_EnablePhoneCallAudio@PhoneController@@AEAAJAEBU_GUID@@W4PhoneAudioEndpoint@@H@Z; PhoneController::_EnablePhoneCallAudio(_GUID const &,PhoneAudioEndpoint,int)
0x1800214fc  test    eax, eax
0x1800214fe  jns     short loc_180021516
0x180021500  mov     r9d, 1B05h
0x180021506  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18002150d  xor     edx, edx
0x18002150f  mov     ecx, eax
0x180021511  call    Log_HREvent_7
0x180021516  xorps   xmm0, xmm0
0x180021519  lea     r8, [rsp+140h+var_D8]; struct PH_PHONE_CALL_COUNTS *
0x18002151e  xor     r9d, r9d; struct ISecurityToken *
0x180021521  mov     edx, r14d; int
0x180021524  mov     rcx, r15; this
0x180021527  movups  [rsp+140h+var_D8], xmm0
0x18002152c  movups  [rsp+140h+var_C8], xmm0
0x180021531  movups  [rbp+40h+var_B8], xmm0
0x180021535  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x18002153a  mov     eax, dword ptr [rbp+40h+var_C8+0Ch]
0x18002153d  mov     ecx, dword ptr [rsp+140h+var_C8]
0x180021541  add     eax, ecx
0x180021543  mov     [rsp+140h+var_100], eax
0x180021547  cmp     dword ptr [rsp+140h+var_D8], r12d
0x18002154c  jnz     loc_1800215D4
0x180021552  test    ecx, ecx
0x180021554  jnz     short loc_1800215D4
0x180021556  cmp     eax, 2
0x180021559  jnb     short loc_1800215D4
0x18002155b  mov     rcx, r15; this
0x18002155e  call    ?_RejectPendingVideoRequests@PhoneController@@IEAAJXZ; PhoneController::_RejectPendingVideoRequests(void)
0x180021563  test    eax, eax
0x180021565  jns     short loc_18002157D
0x180021567  mov     r9d, 1B13h
0x18002156d  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180021574  xor     edx, edx
0x180021576  mov     ecx, eax
0x180021578  call    Log_HREvent_7
0x18002157d  mov     r8d, [r13+8]
0x180021581  lea     r9, [rbp+40h+Block]
0x180021585  mov     rdx, rbx
0x180021588  mov     rcx, r15
0x18002158b  call    ?_AcceptCall@PhoneController@@IEAAJPEAVCallInfo@@W4PhoneCallType@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; PhoneController::_AcceptCall(CallInfo *,PhoneCallType,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180021590  mov     edi, eax
0x180021592  test    eax, eax
0x180021594  jns     loc_1800219AF
0x18002159a  mov     edx, eax; int
0x18002159c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800215a1  mov     r9d, 1B17h
0x1800215a7  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800215ae  mov     edx, r14d
0x1800215b1  mov     ecx, edi
0x1800215b3  call    Log_HREvent_7
0x1800215b8  mov     rcx, r15; this
0x1800215bb  call    ?_DisablePhoneCallAudioIfNotNeeded@PhoneController@@AEAAXXZ; PhoneController::_DisablePhoneCallAudioIfNotNeeded(void)
0x1800215c0  mov     rcx, [rsi]
0x1800215c3  mov     rax, [rcx+10h]
0x1800215c7  mov     rcx, rsi
0x1800215ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215cf  jmp     loc_1800214A5
0x1800215d4  mov     rcx, [r15+60h]
0x1800215d8  lea     rdx, [rsp+140h+var_F0]
0x1800215dd  mov     r8, rbx
0x1800215e0  mov     dword ptr [rsp+140h+var_F8], r12d
0x1800215e5  mov     [rsp+140h+var_F0], r12
0x1800215ea  call    ?FindCallForOtherVoipApp@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEAVCallInfo@@@Z; PhoneCallStorage::FindCallForOtherVoipApp(CallInfo *)
0x1800215ef  mov     rdi, [rsp+140h+var_F0]
0x1800215f4  test    rdi, rdi
0x1800215f7  jnz     short loc_18002163A
0x1800215f9  mov     rcx, [r15+60h]
0x1800215fd  lea     rdx, [rsp+140h+var_F0]
0x180021602  call    ?GetActiveCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@XZ; PhoneCallStorage::GetActiveCall(void)
0x180021607  mov     r12, [rax]
0x18002160a  test    r12, r12
0x18002160d  jz      short loc_180021622
0x18002160f  mov     rax, [r12]
0x180021613  mov     rcx, r12
0x180021616  mov     rax, [rax+8]
0x18002161a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002161f  mov     rdi, r12
0x180021622  mov     rcx, [rsp+140h+var_F0]
0x180021627  test    rcx, rcx
0x18002162a  jz      short loc_180021651
0x18002162c  mov     rax, [rcx]
0x18002162f  mov     rax, [rax+10h]
0x180021633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021638  jmp     short loc_180021651
0x18002163a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy> `wil::Feature<__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy>::GetImpl(void)'::`2'::impl
0x180021641  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calling_Fix_CrossAppVoipHoldPolicy>::__private_IsEnabled(void)
0x180021646  test    al, al
0x180021648  cmovz   r12d, r14d
  ... truncated ...
```
