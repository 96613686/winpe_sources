# ChangeApplicationServices::VerifySourceChangeAndDestinationVersion(ISyncChange *,ISyncChange *)

- ea: `0x18004aa60`
- end: `0x18004aee4`
- name: `?VerifySourceChangeAndDestinationVersion@ChangeApplicationServices@@AEAAJPEAUISyncChange@@0@Z`
- size: `1156`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChange *, struct ISyncChange *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180029810`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x18000a2b8`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x18004aa60`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x18004aaa5`: `ChangeApplicationServices::VerifySourceChangeAndDestinationVersion`
- `0x18004ae8e`: `ChangeApplicationServices::VerifySourceChangeAndDestinationVersion`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::VerifySourceChangeAndDestinationVersion(
        ChangeApplicationServices *this,
        struct ISyncChange *a2,
        struct ISyncChange *a3)
{
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // r14
  int v11; // eax
  __int64 v12; // rsi
  int v13; // eax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-59h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  int v18; // [rsp+40h] [rbp-49h] BYREF
  __int64 v19; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h] BYREF
  __int64 v21; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v22[4]; // [rsp+60h] [rbp-29h] BYREF
  int v23; // [rsp+64h] [rbp-25h]
  __int64 v24; // [rsp+68h] [rbp-21h]
  _BYTE v25[4]; // [rsp+70h] [rbp-19h] BYREF
  int v26; // [rsp+74h] [rbp-15h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  _BYTE v28[4]; // [rsp+80h] [rbp-9h] BYREF
  int v29; // [rsp+84h] [rbp-5h]
  __int64 v30; // [rsp+88h] [rbp-1h]
  _BYTE v31[4]; // [rsp+90h] [rbp+7h] BYREF
  int v32; // [rsp+94h] [rbp+Bh]
  __int64 v33; // [rsp+98h] [rbp+Fh]
  int v34; // [rsp+108h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::VerifySourceChangeAndDestinationVersion");
  }
  v32 = 0;
  v33 = 0;
  v6 = SyncId::InitializeForRetrieval((SyncId *)v31, (ChangeApplicationServices *)((char *)this + 48));
  if ( v6 >= 0 )
  {
    v16 = (unsigned __int16)v32;
    v6 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64, int *))a2->lpVtbl->GetRootItemId)(a2, v33 + 4, &v16);
  }
  v29 = 0;
  v30 = 0;
  if ( v6 < 0
    || (v6 = SyncId::InitializeForRetrieval((SyncId *)v28, (ChangeApplicationServices *)((char *)this + 48)), v6 < 0)
    || (v16 = (unsigned __int16)v29,
        v6 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64, int *))a3->lpVtbl->GetRootItemId)(
               a3,
               v30 + 4,
               &v16),
        v6 < 0) )
  {
    v34 = 0;
  }
  else
  {
    v7 = SyncId::operator==(v31, v28);
    v34 = 0;
    if ( v7 )
    {
      v6 = ((__int64 (__fastcall *)(struct ISyncChange *, int *))a2->lpVtbl->GetFlags)(a2, &v34);
      if ( v6 >= 0 && (v34 & 0xFFFFFFFE) != 0 )
        v6 = -2147024809;
    }
    else
    {
      v6 = -2147217397;
    }
  }
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( v6 < 0 )
    goto LABEL_23;
  v8 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64 *))a2->lpVtbl->GetChangeUnits)(a2, &v20);
  v6 = v8;
  if ( v8 == -2147217393 )
  {
    v6 = 0;
  }
  else if ( v8 < 0 )
  {
    goto LABEL_23;
  }
  if ( (v34 & 1) == 0 )
  {
LABEL_23:
    v18 = 0;
    if ( v6 < 0 )
      goto LABEL_27;
    goto LABEL_24;
  }
  v18 = 0;
  if ( v20 )
  {
    v6 = -2147217394;
    goto LABEL_27;
  }
LABEL_24:
  v6 = ((__int64 (__fastcall *)(struct ISyncChange *, int *))a3->lpVtbl->GetFlags)(a3, &v18);
  if ( v6 >= 0 && (v18 & 0xFFFFFFFC) != 0 )
    v6 = -2147024809;
LABEL_27:
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( v6 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64 *))a3->lpVtbl->GetChangeUnits)(a3, &v19);
    v6 = v9;
    if ( v9 == -2147217393 )
    {
      v6 = 0;
    }
    else if ( v9 < 0 )
    {
      goto LABEL_64;
    }
    if ( (v18 & 3) != 0 && v19 )
    {
      v6 = -2147217394;
    }
    else if ( v20 && v19 )
    {
      v6 = (*(__int64 (**)(void))(*(_QWORD *)v20 + 40LL))();
      if ( v6 >= 0 )
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
      v26 = 0;
      v10 = 0;
      v27 = 0;
      if ( v6 >= 0 )
      {
        v11 = SyncId::InitializeForRetrieval((SyncId *)v25, (ChangeApplicationServices *)((char *)this + 56));
        v10 = v27;
        v6 = v11;
      }
      v23 = 0;
      v12 = 0;
      v24 = 0;
      if ( v6 >= 0 )
      {
        v13 = SyncId::InitializeForRetrieval((SyncId *)v22, (ChangeApplicationServices *)((char *)this + 56));
        v12 = v24;
        v6 = v13;
      }
      while ( v6 >= 0 )
      {
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, 1, &v21, 0);
        if ( v6 == 1 )
          goto LABEL_53;
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        if ( v6 >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v19 + 24LL))(
                  v19,
                  1,
                  &v17,
                  0);
          v6 = v14;
          if ( v14 == 1 )
          {
            SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
LABEL_53:
            SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v21);
            ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
            v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v20 + 24LL))(
                   v20,
                   1,
                   &v17,
                   0);
            if ( v6 )
            {
              if ( v6 == 1 )
                v6 = 0;
            }
            else
            {
              v6 = -2147217404;
            }
            SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
            if ( v6 >= 0 )
            {
              ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
              v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v19 + 24LL))(
                     v19,
                     1,
                     &v17,
                     0);
              if ( v6 )
              {
                if ( v6 == 1 )
                  v6 = 0;
              }
              else
              {
                v6 = -2147217404;
              }
              SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
            }
            break;
          }
          if ( v14 >= 0 )
          {
            v16 = (unsigned __int16)v26;
            v6 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v21 + 32LL))(v21, v10 + 4, &v16);
            if ( v6 >= 0 )
            {
              v16 = (unsigned __int16)v23;
              v6 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v17 + 32LL))(v17, v12 + 4, &v16);
              if ( v6 >= 0 && !(unsigned int)SyncId::operator==(v25, v22) )
                v6 = -2147217404;
            }
          }
        }
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v21);
      }
      SyncId::~SyncId((SyncId *)v22);
      SyncId::~SyncId((SyncId *)v25);
    }
  }
LABEL_64:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::VerifySourceChangeAndDestinationVersion",
      v6);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v19);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v20);
  SyncId::~SyncId((SyncId *)v28);
  SyncId::~SyncId((SyncId *)v31);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004aa60  push    rbp
0x18004aa62  push    rbx
0x18004aa63  push    rsi
0x18004aa64  push    rdi
0x18004aa65  push    r12
0x18004aa67  push    r13
0x18004aa69  push    r14
0x18004aa6b  push    r15
0x18004aa6d  lea     rbp, [rsp-1Fh]
0x18004aa72  sub     rsp, 0A8h
0x18004aa79  mov     r14, r8
0x18004aa7c  mov     rdi, rdx
0x18004aa7f  mov     r15, rcx
0x18004aa82  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa89  lea     rax, WPP_GLOBAL_Control
0x18004aa90  cmp     rcx, rax
0x18004aa93  jz      short loc_18004AABD
0x18004aa95  test    byte ptr [rcx+1Ch], 80h
0x18004aa99  jz      short loc_18004AABD
0x18004aa9b  cmp     byte ptr [rcx+19h], 5
0x18004aa9f  jb      short loc_18004AABD
0x18004aaa1  mov     rcx, [rcx+10h]
0x18004aaa5  lea     r9, aChangeapplicat_14; "ChangeApplicationServices::VerifySource"...
0x18004aaac  mov     edx, 3Ah ; ':'
0x18004aab1  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004aab8  call    WPP_SF_s
0x18004aabd  xor     r12d, r12d
0x18004aac0  lea     rdx, [r15+30h]; struct IdFormat *
0x18004aac4  lea     rcx, [rbp+57h+var_50]; this
0x18004aac8  mov     [rbp+57h+var_4C], r12d
0x18004aacc  mov     [rbp+57h+var_48], r12
0x18004aad0  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004aad5  mov     ebx, eax
0x18004aad7  test    eax, eax
0x18004aad9  js      short loc_18004AAFF
0x18004aadb  movzx   eax, word ptr [rbp+57h+var_4C]
0x18004aadf  lea     r8, [rbp+57h+var_B0]
0x18004aae3  mov     rdx, [rbp+57h+var_48]
0x18004aae7  mov     rcx, rdi
0x18004aaea  mov     [rbp+57h+var_B0], eax
0x18004aaed  add     rdx, 4
0x18004aaf1  mov     rax, [rdi]
0x18004aaf4  mov     rax, [rax+20h]
0x18004aaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aafd  mov     ebx, eax
0x18004aaff  mov     [rbp+57h+var_5C], r12d
0x18004ab03  mov     r13d, 80070057h
0x18004ab09  mov     [rbp+57h+var_58], r12
0x18004ab0d  test    ebx, ebx
0x18004ab0f  js      short loc_18004AB68
0x18004ab11  lea     rdx, [r15+30h]; struct IdFormat *
0x18004ab15  lea     rcx, [rbp+57h+var_60]; this
0x18004ab19  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004ab1e  mov     ebx, eax
0x18004ab20  test    eax, eax
0x18004ab22  js      short loc_18004AB68
0x18004ab24  movzx   eax, word ptr [rbp+57h+var_5C]
0x18004ab28  lea     r8, [rbp+57h+var_B0]
0x18004ab2c  mov     rdx, [rbp+57h+var_58]
0x18004ab30  mov     rcx, r14
0x18004ab33  mov     [rbp+57h+var_B0], eax
0x18004ab36  add     rdx, 4
0x18004ab3a  mov     rax, [r14]
0x18004ab3d  mov     rax, [rax+20h]
0x18004ab41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab46  mov     ebx, eax
0x18004ab48  test    eax, eax
0x18004ab4a  js      short loc_18004AB68
0x18004ab4c  lea     rdx, [rbp+57h+var_60]
0x18004ab50  lea     rcx, [rbp+57h+var_50]
0x18004ab54  call    ??8SyncId@@QEBAHAEBV0@@Z; SyncId::operator==(SyncId const &)
0x18004ab59  mov     [rbp+57h+arg_18], r12d
0x18004ab5d  test    eax, eax
0x18004ab5f  jnz     short loc_18004AB70
0x18004ab61  mov     ebx, 8004100Bh
0x18004ab66  jmp     short loc_18004AB94
0x18004ab68  mov     [rbp+57h+arg_18], r12d
0x18004ab6c  test    ebx, ebx
0x18004ab6e  js      short loc_18004AB94
0x18004ab70  mov     rax, [rdi]
0x18004ab73  lea     rdx, [rbp+57h+arg_18]
0x18004ab77  mov     rcx, rdi
0x18004ab7a  mov     rax, [rax+38h]
0x18004ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab83  mov     ebx, eax
0x18004ab85  test    eax, eax
0x18004ab87  js      short loc_18004AB94
0x18004ab89  test    [rbp+57h+arg_18], 0FFFFFFFEh
0x18004ab90  cmovnz  ebx, r13d
0x18004ab94  lea     rcx, [rbp+57h+var_90]
0x18004ab98  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004ab9d  mov     esi, 8004100Eh
0x18004aba2  mov     r13d, 1
0x18004aba8  test    ebx, ebx
0x18004abaa  js      short loc_18004ABE5
0x18004abac  mov     rax, [rdi]
0x18004abaf  lea     rdx, [rbp+57h+var_90]
0x18004abb3  mov     rcx, rdi
0x18004abb6  mov     rax, [rax+48h]
0x18004abba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abbf  mov     ebx, eax
0x18004abc1  cmp     eax, 8004100Fh
0x18004abc6  jnz     short loc_18004ABCD
0x18004abc8  mov     ebx, r12d
0x18004abcb  jmp     short loc_18004ABD1
0x18004abcd  test    eax, eax
0x18004abcf  js      short loc_18004ABE5
0x18004abd1  test    byte ptr [rbp+57h+arg_18], r13b
0x18004abd5  jz      short loc_18004ABE5
0x18004abd7  mov     [rbp+57h+var_A0], r12d
0x18004abdb  cmp     [rbp+57h+var_90], r12
0x18004abdf  jz      short loc_18004ABED
0x18004abe1  mov     ebx, esi
0x18004abe3  jmp     short loc_18004AC15
0x18004abe5  mov     [rbp+57h+var_A0], r12d
0x18004abe9  test    ebx, ebx
0x18004abeb  js      short loc_18004AC15
0x18004abed  mov     rax, [r14]
0x18004abf0  lea     rdx, [rbp+57h+var_A0]
0x18004abf4  mov     rcx, r14
0x18004abf7  mov     rax, [rax+38h]
0x18004abfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac00  mov     ebx, eax
0x18004ac02  test    eax, eax
0x18004ac04  js      short loc_18004AC15
0x18004ac06  test    [rbp+57h+var_A0], 0FFFFFFFCh
0x18004ac0d  mov     eax, 80070057h
0x18004ac12  cmovnz  ebx, eax
0x18004ac15  lea     rcx, [rbp+57h+var_98]
0x18004ac19  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004ac1e  test    ebx, ebx
0x18004ac20  js      loc_18004AE6B
0x18004ac26  mov     rax, [r14]
0x18004ac29  lea     rdx, [rbp+57h+var_98]
0x18004ac2d  mov     rcx, r14
0x18004ac30  mov     rax, [rax+48h]
0x18004ac34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac39  mov     ebx, eax
0x18004ac3b  cmp     eax, 8004100Fh
0x18004ac40  jnz     short loc_18004AC47
0x18004ac42  mov     ebx, r12d
0x18004ac45  jmp     short loc_18004AC4F
0x18004ac47  test    eax, eax
0x18004ac49  js      loc_18004AE6B
0x18004ac4f  test    byte ptr [rbp+57h+var_A0], 3
0x18004ac53  mov     rax, [rbp+57h+var_98]
0x18004ac57  jz      short loc_18004AC65
0x18004ac59  test    rax, rax
0x18004ac5c  jz      short loc_18004AC65
0x18004ac5e  mov     ebx, esi
0x18004ac60  jmp     loc_18004AE6B
0x18004ac65  mov     rcx, [rbp+57h+var_90]
0x18004ac69  test    rcx, rcx
0x18004ac6c  jz      loc_18004AE6B
0x18004ac72  test    rax, rax
0x18004ac75  jz      loc_18004AE6B
0x18004ac7b  mov     rax, [rcx]
0x18004ac7e  mov     rax, [rax+28h]
0x18004ac82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac87  mov     ebx, eax
0x18004ac89  test    eax, eax
0x18004ac8b  js      short loc_18004AC9F
0x18004ac8d  mov     rcx, [rbp+57h+var_98]
0x18004ac91  mov     rax, [rcx]
0x18004ac94  mov     rax, [rax+28h]
0x18004ac98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac9d  mov     ebx, eax
0x18004ac9f  mov     [rbp+57h+var_6C], r12d
0x18004aca3  mov     r14, r12
0x18004aca6  mov     [rbp+57h+var_68], r12
0x18004acaa  lea     rdi, [r15+38h]
0x18004acae  test    ebx, ebx
0x18004acb0  js      short loc_18004ACC4
0x18004acb2  mov     rdx, rdi; struct IdFormat *
0x18004acb5  lea     rcx, [rbp+57h+var_70]; this
0x18004acb9  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004acbe  mov     r14, [rbp+57h+var_68]
0x18004acc2  mov     ebx, eax
0x18004acc4  mov     [rbp+57h+var_7C], r12d
0x18004acc8  mov     rsi, r12
0x18004accb  mov     [rbp+57h+var_78], r12
0x18004accf  test    ebx, ebx
0x18004acd1  js      short loc_18004ACE5
0x18004acd3  mov     rdx, rdi; struct IdFormat *
0x18004acd6  lea     rcx, [rbp+57h+var_80]; this
0x18004acda  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004acdf  mov     rsi, [rbp+57h+var_78]
0x18004ace3  mov     ebx, eax
0x18004ace5  mov     edi, 80041004h
0x18004acea  test    ebx, ebx
0x18004acec  js      loc_18004AE59
0x18004acf2  lea     rcx, [rbp+57h+var_88]
0x18004acf6  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004acfb  mov     rcx, [rbp+57h+var_90]
0x18004acff  lea     r8, [rbp+57h+var_88]
0x18004ad03  xor     r9d, r9d
0x18004ad06  mov     edx, r13d
0x18004ad09  mov     rax, [rcx]
0x18004ad0c  mov     rax, [rax+18h]
0x18004ad10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad15  mov     ebx, eax
0x18004ad17  cmp     eax, r13d
0x18004ad1a  jz      loc_18004ADD2
0x18004ad20  lea     rcx, [rbp+57h+var_A8]
0x18004ad24  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004ad29  test    ebx, ebx
0x18004ad2b  js      loc_18004ADB2
0x18004ad31  mov     rcx, [rbp+57h+var_98]
0x18004ad35  lea     r8, [rbp+57h+var_A8]
0x18004ad39  xor     r9d, r9d
0x18004ad3c  mov     edx, r13d
0x18004ad3f  mov     rax, [rcx]
0x18004ad42  mov     rax, [rax+18h]
0x18004ad46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad4b  mov     ebx, eax
0x18004ad4d  cmp     eax, r13d
0x18004ad50  jz      short loc_18004ADC9
0x18004ad52  test    eax, eax
0x18004ad54  js      short loc_18004ADB2
0x18004ad56  mov     rcx, [rbp+57h+var_88]
0x18004ad5a  lea     rdx, [r14+4]
0x18004ad5e  movzx   eax, word ptr [rbp+57h+var_6C]
0x18004ad62  lea     r8, [rbp+57h+var_B0]
0x18004ad66  mov     [rbp+57h+var_B0], eax
0x18004ad69  mov     rax, [rcx]
0x18004ad6c  mov     rax, [rax+20h]
0x18004ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad75  mov     ebx, eax
0x18004ad77  test    eax, eax
0x18004ad79  js      short loc_18004ADB2
0x18004ad7b  mov     rcx, [rbp+57h+var_A8]
0x18004ad7f  lea     rdx, [rsi+4]
0x18004ad83  movzx   eax, word ptr [rbp+57h+var_7C]
0x18004ad87  lea     r8, [rbp+57h+var_B0]
0x18004ad8b  mov     [rbp+57h+var_B0], eax
0x18004ad8e  mov     rax, [rcx]
0x18004ad91  mov     rax, [rax+20h]
0x18004ad95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad9a  mov     ebx, eax
0x18004ad9c  test    eax, eax
0x18004ad9e  js      short loc_18004ADB2
0x18004ada0  lea     rdx, [rbp+57h+var_80]
0x18004ada4  lea     rcx, [rbp+57h+var_70]
0x18004ada8  call    ??8SyncId@@QEBAHAEBV0@@Z; SyncId::operator==(SyncId const &)
0x18004adad  test    eax, eax
0x18004adaf  cmovz   ebx, edi
0x18004adb2  lea     rcx, [rbp+57h+var_A8]
0x18004adb6  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004adbb  lea     rcx, [rbp+57h+var_88]
0x18004adbf  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004adc4  jmp     loc_18004ACEA
0x18004adc9  lea     rcx, [rbp+57h+var_A8]
0x18004adcd  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004add2  lea     rcx, [rbp+57h+var_88]
0x18004add6  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004addb  lea     rcx, [rbp+57h+var_A8]
0x18004addf  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004ade4  mov     rcx, [rbp+57h+var_90]
0x18004ade8  lea     r8, [rbp+57h+var_A8]
0x18004adec  xor     r9d, r9d
0x18004adef  mov     edx, r13d
0x18004adf2  mov     rax, [rcx]
0x18004adf5  mov     rax, [rax+18h]
0x18004adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adfe  mov     ebx, eax
0x18004ae00  test    eax, eax
0x18004ae02  jnz     short loc_18004AE08
0x18004ae04  mov     ebx, edi
0x18004ae06  jmp     short loc_18004AE0F
0x18004ae08  cmp     ebx, r13d
0x18004ae0b  cmovz   ebx, r12d
0x18004ae0f  lea     rcx, [rbp+57h+var_A8]
0x18004ae13  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004ae18  test    ebx, ebx
0x18004ae1a  js      short loc_18004AE59
0x18004ae1c  lea     rcx, [rbp+57h+var_A8]
0x18004ae20  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004ae25  mov     rcx, [rbp+57h+var_98]
0x18004ae29  lea     r8, [rbp+57h+var_A8]
0x18004ae2d  xor     r9d, r9d
0x18004ae30  mov     edx, r13d
0x18004ae33  mov     rax, [rcx]
0x18004ae36  mov     rax, [rax+18h]
0x18004ae3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae3f  mov     ebx, eax
0x18004ae41  test    eax, eax
0x18004ae43  jnz     short loc_18004AE49
0x18004ae45  mov     ebx, edi
0x18004ae47  jmp     short loc_18004AE50
0x18004ae49  cmp     ebx, r13d
0x18004ae4c  cmovz   ebx, r12d
0x18004ae50  lea     rcx, [rbp+57h+var_A8]
0x18004ae54  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004ae59  lea     rcx, [rbp+57h+var_80]; this
0x18004ae5d  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004ae62  lea     rcx, [rbp+57h+var_70]; this
0x18004ae66  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004ae6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae72  lea     rax, WPP_GLOBAL_Control
0x18004ae79  cmp     rcx, rax
  ... truncated ...
```
