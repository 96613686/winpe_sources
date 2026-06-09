# ChangeApplicationServices::GetChangeApplicationContext(ISyncChange *,ISyncChange *,IChangeApplicationContext * *)

- ea: `0x180029810`
- end: `0x180029ea3`
- name: `?GetChangeApplicationContext@ChangeApplicationServices@@UEAAJPEAUISyncChange@@0PEAPEAUIChangeApplicationContext@@@Z`
- size: `1683`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChange *, struct ISyncChange *, struct IChangeApplicationContext **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180005f20`
- `0x180007584`
- `0x1800084ec`
- `0x18000a0f0`
- `0x18000a2b8`
- `0x180011f60`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x18002070c`
- `0x180029810`
- `0x180046bb0`
- `0x180047300`
- `0x18004882c`
- `0x18004a8fc`
- `0x18004aa60`
- `0x180073dac`
- `0x1800748b8`
- `0x18008387c`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x180029876`: `ChangeApplicationServices::GetChangeApplicationContext`
- `0x180029e38`: `ChangeApplicationServices::GetChangeApplicationContext`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::GetChangeApplicationContext(
        ChangeApplicationServices *this,
        struct ISyncChange *a2,
        struct ISyncChange *a3,
        struct IChangeApplicationContext **a4)
{
  char v4; // r12
  struct IChangeApplicationContext **v5; // r13
  signed int v9; // ebx
  __int64 v10; // r14
  int v11; // eax
  struct ISyncChangeVtbl *lpVtbl; // rax
  struct ISyncChange *v13; // rcx
  __int64 NextElement; // rax
  int v15; // r11d
  ChangeApplicationServices *v16; // rcx
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r15
  __int64 v23; // rsi
  void *v24; // rbx
  __int64 *v25; // rax
  __int64 v26; // rax
  __int64 (__fastcall ***v27)(_QWORD, GUID *, struct IChangeApplicationContext **); // rsi
  void *v29; // [rsp+80h] [rbp-59h] BYREF
  struct ISyncKnowledge *v30; // [rsp+88h] [rbp-51h] BYREF
  __int64 v31; // [rsp+90h] [rbp-49h] BYREF
  __int64 v32; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v33[4]; // [rsp+A0h] [rbp-39h] BYREF
  int v34; // [rsp+A4h] [rbp-35h]
  __int64 v35; // [rsp+A8h] [rbp-31h]
  struct IChangeApplicationContext **v36; // [rsp+B0h] [rbp-29h]
  char *v37; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-19h]
  __int16 v39; // [rsp+C8h] [rbp-11h]
  __int16 v40; // [rsp+CAh] [rbp-Fh]
  int v41; // [rsp+CCh] [rbp-Dh]
  __int16 v42; // [rsp+D0h] [rbp-9h]
  __int16 v43; // [rsp+D2h] [rbp-7h]
  __int128 v44; // [rsp+D8h] [rbp-1h] BYREF

  v4 = 0;
  v36 = a4;
  LODWORD(v44) = 0;
  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::GetChangeApplicationContext");
  }
  if ( !a2 && !a3 || !v5 )
    goto LABEL_12;
  if ( *((_DWORD *)this + 9) != 2 )
  {
    if ( *((_DWORD *)this + 9) != 3 )
    {
      v9 = -2147217407;
      goto LABEL_18;
    }
    goto LABEL_13;
  }
  if ( !a2 )
  {
LABEL_12:
    v9 = -2147467261;
    goto LABEL_18;
  }
LABEL_13:
  if ( *((_DWORD *)this + 56) )
  {
    v9 = -2147217370;
  }
  else
  {
    v9 = 0;
    if ( a2 && a3 )
      v9 = ChangeApplicationServices::VerifySourceChangeAndDestinationVersion(this, a2, a3);
  }
LABEL_18:
  v10 = 0;
  v34 = 0;
  v35 = 0;
  if ( v9 >= 0 )
  {
    v11 = SyncId::InitializeForRetrieval((SyncId *)v33, (ChangeApplicationServices *)((char *)this + 48));
    v10 = v35;
    v9 = v11;
    if ( v11 >= 0 )
    {
      LODWORD(v44) = (unsigned __int16)v34;
      if ( a2 )
      {
        lpVtbl = a2->lpVtbl;
        v13 = a2;
      }
      else
      {
        lpVtbl = a3->lpVtbl;
        v13 = a3;
      }
      v9 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64, __int128 *))lpVtbl->GetRootItemId)(
             v13,
             v35 + 4,
             &v44);
      if ( v9 >= 0 )
      {
        v29 = 0;
        if ( (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
                                (char *)this + 176,
                                v33,
                                &v29) )
        {
          if ( *((_DWORD *)v29 + 5) )
          {
            v38 = 0;
            v37 = (char *)v29 + 56;
            while ( 1 )
            {
              NextElement = TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(&v37);
              if ( !NextElement )
                break;
              if ( *(_DWORD *)(*(_QWORD *)(NextElement + 16) + 20LL) == v15 )
                goto LABEL_29;
            }
          }
          else
          {
LABEL_29:
            v9 = -2147217407;
          }
        }
        SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v29);
      }
    }
  }
  v32 = 0;
  v30 = 0;
  if ( v9 >= 0 )
  {
    if ( !a2 )
    {
      SharedRefPtr<IClockVector>::operator=((__int64 *)&v30, (__int64 *)this + 12);
LABEL_56:
      if ( *((struct ISyncKnowledge **)this + 15) != v30 )
      {
        v20 = *((_QWORD *)this + 10);
        v29 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, void **))(*(_QWORD *)v20 + 96LL))(
               v20,
               v30,
               &v29);
        if ( v9 >= 0 )
        {
          SharedRefPtr<IClockVector>::operator=((__int64 *)this + 16, (__int64 *)&v29);
          SharedRefPtr<IClockVector>::operator=((__int64 *)this + 15, (__int64 *)&v30);
        }
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v29);
      }
      goto LABEL_60;
    }
    SharedRefPtr<IUnknown>::AttachExternal(&v32, a2);
    v9 = ((__int64 (__fastcall *)(struct ISyncChange *, struct ISyncKnowledge **))a2->lpVtbl->GetMadeWithKnowledge)(
           a2,
           &v30);
    if ( v9 >= 0 )
    {
      if ( !v30 )
      {
        v9 = -2147217399;
LABEL_41:
        v31 = 0;
        *(_QWORD *)&v44 = 0;
        goto LABEL_87;
      }
      v9 = ChangeApplicationServices::ValidateIdParameters(v16, (ChangeApplicationServices *)((char *)this + 40), v30);
      if ( v9 >= 0 )
      {
        v17 = ContainsChangeVersion((ChangeApplicationServices *)((char *)this + 40));
        v9 = 0;
        if ( v17 != -2147217394 )
          v9 = v17;
        if ( v9 == 1 )
          goto LABEL_40;
        if ( v9 >= 0 )
        {
          v18 = ContainsChangeVersion((ChangeApplicationServices *)((char *)this + 40));
          v9 = v18;
          if ( v18 == 1 )
          {
LABEL_40:
            v9 = -2147217402;
            goto LABEL_41;
          }
          if ( v18 >= 0 )
          {
            HIDWORD(v37) = 0;
            v38 = 0;
            v9 = SyncId::InitializeForRetrieval((SyncId *)&v37, (ChangeApplicationServices *)((char *)this + 40));
            if ( v9 >= 0 )
            {
              LODWORD(v44) = WORD2(v37);
              v9 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64, __int128 *))v30->lpVtbl->GetOwnerReplicaId)(
                     v30,
                     v38 + 4,
                     &v44);
            }
            if ( v9 >= 0 && (!*((_WORD *)this + 102) || !(unsigned int)SyncId::operator==((char *)this + 200, &v37)) )
            {
              SyncId::operator=((__int64)this + 200, (__int64)&v37);
              v19 = *((_QWORD *)this + 10);
              v29 = 0;
              v9 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64, void **))v30->lpVtbl->MapRemoteToLocal)(
                     v30,
                     v19,
                     &v29);
              if ( v9 >= 0 )
                SharedRefPtr<IClockVector>::operator=((__int64 *)this + 14, (__int64 *)&v29);
              SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v29);
            }
            SyncId::~SyncId((SyncId *)&v37);
            if ( v9 >= 0 )
              goto LABEL_56;
          }
        }
      }
    }
  }
LABEL_60:
  v31 = 0;
  if ( v9 < 0 )
    goto LABEL_73;
  if ( !a3 )
  {
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    v9 = CreateSyncService(&IID_IProviderSyncServices, &v29);
    if ( v9 >= 0 )
    {
      HIDWORD(v37) = *((_DWORD *)this + 10);
      LODWORD(v38) = *((unsigned __int16 *)this + 22);
      HIDWORD(v38) = *((_DWORD *)this + 12);
      v39 = *((_WORD *)this + 26);
      v40 = 0;
      v41 = *((_DWORD *)this + 14);
      v42 = *((_WORD *)this + 30);
      v43 = 0;
      LODWORD(v37) = 28;
      v9 = (*(__int64 (__fastcall **)(void *, char **))(*(_QWORD *)v29 + 24LL))(v29, &v37);
    }
    HIDWORD(v37) = 0;
    v38 = 0;
    if ( v9 >= 0 )
    {
      v9 = SyncId::InitializeForRetrieval((SyncId *)&v37, (ChangeApplicationServices *)((char *)this + 40));
      if ( v9 >= 0 )
      {
        v21 = *((_QWORD *)this + 10);
        v22 = v38;
        LODWORD(v44) = WORD2(v37);
        v23 = v38 + 4;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v21 + 24LL))(v21, v38 + 4, &v44);
        if ( v9 >= 0 )
        {
          v44 = 0;
          if ( (v34 & 0x20000) == 0 )
            v10 += 4;
          if ( (HIDWORD(v37) & 0x20000) != 0 )
            v23 = v22;
          v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int128 *, __int128 *, int, GUID *, __int64 *))(*(_QWORD *)v29 + 136LL))(
                 v29,
                 v23,
                 v10,
                 &v44,
                 &v44,
                 2,
                 &IID_ISyncChange,
                 &v31);
        }
      }
    }
    SyncId::~SyncId((SyncId *)&v37);
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v29);
LABEL_73:
    *(_QWORD *)&v44 = 0;
    if ( v9 < 0 )
      goto LABEL_87;
    goto LABEL_74;
  }
  SharedRefPtr<IUnknown>::AttachExternal(&v31, a3);
LABEL_74:
  v24 = SeAlloc(0x100u);
  if ( v24 )
  {
    v25 = (__int64 *)((char *)this + 112);
    if ( this )
    {
      v29 = (char *)this + 8;
      if ( this != (ChangeApplicationServices *)-8LL )
      {
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
        v25 = (__int64 *)((char *)this + 112);
      }
    }
    else
    {
      v29 = 0;
    }
    v26 = ChangeApplicationContext::ChangeApplicationContext(
            (__int64)v24,
            (__int64)this + 40,
            *((_DWORD *)this + 16),
            (__int64 *)&v29,
            &v32,
            &v31,
            (__int64 *)this + 10,
            (__int64 *)this + 11,
            (__int64 *)this + 12,
            (__int64 *)this + 13,
            v25,
            (__int64 *)this + 16,
            (__int64 *)this + 17,
            (__int64 *)this + 18,
            (__int64 *)this + 20,
            (__int64 *)this + 21);
    v5 = v36;
    v27 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IChangeApplicationContext **))v26;
    v4 = 1;
  }
  else
  {
    v27 = 0;
  }
  *(_QWORD *)&v44 = v27;
  v9 = v27 == 0 ? 0x8007000E : 0;
  if ( (v4 & 1) != 0 )
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v29);
  if ( v27 )
  {
    v9 = (**v27)(v27, &IID_IChangeApplicationContext, v5);
    if ( v9 >= 0 )
      *((_DWORD *)this + 56) = 1;
  }
LABEL_87:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::GetChangeApplicationContext",
      v9);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v44);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v31);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v30);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v32);
  SyncId::~SyncId((SyncId *)v33);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029810  push    rbp
0x180029812  push    rbx
0x180029813  push    rsi
0x180029814  push    rdi
0x180029815  push    r12
0x180029817  push    r13
0x180029819  push    r14
0x18002981b  push    r15
0x18002981d  lea     rbp, [rsp-1Fh]
0x180029822  sub     rsp, 0F8h
0x180029829  mov     rax, cs:__security_cookie
0x180029830  xor     rax, rsp
0x180029833  mov     [rbp+57h+var_48], rax
0x180029837  xor     r12d, r12d
0x18002983a  mov     [rbp+57h+var_80], r9
0x18002983e  mov     dword ptr [rbp+57h+var_58], r12d
0x180029842  mov     r13, r9
0x180029845  mov     r15, r8
0x180029848  mov     rsi, rdx
0x18002984b  mov     rdi, rcx
0x18002984e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029855  lea     rax, WPP_GLOBAL_Control
0x18002985c  cmp     rcx, rax
0x18002985f  jz      short loc_180029889
0x180029861  test    byte ptr [rcx+1Ch], 80h
0x180029865  jz      short loc_180029889
0x180029867  cmp     byte ptr [rcx+19h], 5
0x18002986b  jb      short loc_180029889
0x18002986d  mov     rcx, [rcx+10h]
0x180029871  lea     edx, [r12+1Ah]
0x180029876  lea     r9, aChangeapplicat_25; "ChangeApplicationServices::GetChangeApp"...
0x18002987d  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180029884  call    WPP_SF_s
0x180029889  test    rsi, rsi
0x18002988c  jnz     short loc_180029893
0x18002988e  test    r15, r15
0x180029891  jz      short loc_1800298B0
0x180029893  test    r13, r13
0x180029896  jz      short loc_1800298B0
0x180029898  cmp     dword ptr [rdi+24h], 2
0x18002989c  jz      short loc_1800298AB
0x18002989e  cmp     dword ptr [rdi+24h], 3
0x1800298a2  jz      short loc_1800298B7
0x1800298a4  mov     ebx, 80041001h
0x1800298a9  jmp     short loc_1800298E3
0x1800298ab  test    rsi, rsi
0x1800298ae  jnz     short loc_1800298B7
0x1800298b0  mov     ebx, 80004003h
0x1800298b5  jmp     short loc_1800298E3
0x1800298b7  cmp     [rdi+0E0h], r12d
0x1800298be  jz      short loc_1800298C7
0x1800298c0  mov     ebx, 80041026h
0x1800298c5  jmp     short loc_1800298E3
0x1800298c7  xor     ebx, ebx
0x1800298c9  test    rsi, rsi
0x1800298cc  jz      short loc_1800298E3
0x1800298ce  test    r15, r15
0x1800298d1  jz      short loc_1800298E3
0x1800298d3  mov     r8, r15; struct ISyncChange *
0x1800298d6  mov     rdx, rsi; struct ISyncChange *
0x1800298d9  mov     rcx, rdi; this
0x1800298dc  call    ?VerifySourceChangeAndDestinationVersion@ChangeApplicationServices@@AEAAJPEAUISyncChange@@0@Z; ChangeApplicationServices::VerifySourceChangeAndDestinationVersion(ISyncChange *,ISyncChange *)
0x1800298e1  mov     ebx, eax
0x1800298e3  xor     r14d, r14d
0x1800298e6  mov     [rbp+57h+var_8C], r12d
0x1800298ea  mov     [rbp+57h+var_88], r14
0x1800298ee  test    ebx, ebx
0x1800298f0  js      loc_18002999D
0x1800298f6  lea     rdx, [rdi+30h]; struct IdFormat *
0x1800298fa  lea     rcx, [rbp+57h+var_90]; this
0x1800298fe  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180029903  mov     r14, [rbp+57h+var_88]
0x180029907  mov     ebx, eax
0x180029909  test    eax, eax
0x18002990b  js      loc_18002999D
0x180029911  movzx   eax, word ptr [rbp+57h+var_8C]
0x180029915  lea     r8, [rbp+57h+var_58]
0x180029919  mov     dword ptr [rbp+57h+var_58], eax
0x18002991c  lea     rdx, [r14+4]
0x180029920  test    rsi, rsi
0x180029923  jz      short loc_18002992D
0x180029925  mov     rax, [rsi]
0x180029928  mov     rcx, rsi
0x18002992b  jmp     short loc_180029933
0x18002992d  mov     rax, [r15]
0x180029930  mov     rcx, r15
0x180029933  mov     rax, [rax+20h]
0x180029937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002993c  mov     ebx, eax
0x18002993e  test    eax, eax
0x180029940  js      short loc_18002999D
0x180029942  lea     rcx, [rdi+0B0h]
0x180029949  mov     [rbp+57h+var_B0], r12
0x18002994d  lea     r8, [rbp+57h+var_B0]
0x180029951  lea     rdx, [rbp+57h+var_90]
0x180029955  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x18002995a  xor     r11d, r11d
0x18002995d  test    al, al
0x18002995f  jz      short loc_180029994
0x180029961  mov     rax, [rbp+57h+var_B0]
0x180029965  cmp     [rax+14h], r11d
0x180029969  jz      short loc_18002998F
0x18002996b  add     rax, 38h ; '8'
0x18002996f  mov     [rbp+57h+var_70], r11
0x180029973  mov     [rbp+57h+var_78], rax
0x180029977  lea     rcx, [rbp+57h+var_78]
0x18002997b  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x180029980  test    rax, rax
0x180029983  jz      short loc_180029994
0x180029985  mov     rax, [rax+10h]
0x180029989  cmp     [rax+14h], r11d
0x18002998d  jnz     short loc_180029977
0x18002998f  mov     ebx, 80041001h
0x180029994  lea     rcx, [rbp+57h+var_B0]
0x180029998  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x18002999d  mov     [rbp+57h+var_98], r12
0x1800299a1  mov     [rbp+57h+var_A8], r12
0x1800299a5  test    ebx, ebx
0x1800299a7  js      loc_180029B76
0x1800299ad  test    rsi, rsi
0x1800299b0  jz      loc_180029B1B
0x1800299b6  mov     rdx, rsi
0x1800299b9  lea     rcx, [rbp+57h+var_98]
0x1800299bd  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x1800299c2  mov     rax, [rsi]
0x1800299c5  lea     rdx, [rbp+57h+var_A8]
0x1800299c9  mov     rcx, rsi
0x1800299cc  mov     rax, [rax+50h]
0x1800299d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d5  mov     ebx, eax
0x1800299d7  test    eax, eax
0x1800299d9  js      loc_180029B76
0x1800299df  mov     r8, [rbp+57h+var_A8]; struct ISyncKnowledge *
0x1800299e3  test    r8, r8
0x1800299e6  jnz     short loc_1800299EF
0x1800299e8  mov     ebx, 80041009h
0x1800299ed  jmp     short loc_180029A2C
0x1800299ef  lea     rsi, [rdi+28h]
0x1800299f3  mov     rdx, rsi; struct IdDescription *
0x1800299f6  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800299fb  mov     ebx, eax
0x1800299fd  test    eax, eax
0x1800299ff  js      loc_180029B76
0x180029a05  xor     r9d, r9d
0x180029a08  lea     r8, [rbp+57h+var_98]
0x180029a0c  lea     rdx, [rbp+57h+var_A8]
0x180029a10  mov     rcx, rsi; struct IdFormat *
0x180029a13  call    ?ContainsChangeVersion@@YAJAEBUIdDescription@@AEBV?$SharedRefPtr@UISyncKnowledge@@@@AEBV?$SharedRefPtr@UISyncChange@@@@W4ChangeVersionKind@@@Z; ContainsChangeVersion(IdDescription const &,SharedRefPtr<ISyncKnowledge> const &,SharedRefPtr<ISyncChange> const &,ChangeVersionKind)
0x180029a18  xor     ebx, ebx
0x180029a1a  cmp     eax, 8004100Eh
0x180029a1f  cmovnz  ebx, eax
0x180029a22  cmp     ebx, 1
0x180029a25  jnz     short loc_180029A39
0x180029a27  mov     ebx, 80041006h
0x180029a2c  mov     [rbp+57h+var_A0], r12
0x180029a30  mov     qword ptr [rbp+57h+var_58], r12
0x180029a34  jmp     loc_180029E15
0x180029a39  test    ebx, ebx
0x180029a3b  js      loc_180029B76
0x180029a41  mov     r9d, 1
0x180029a47  lea     r8, [rbp+57h+var_98]
0x180029a4b  lea     rdx, [rbp+57h+var_A8]
0x180029a4f  mov     rcx, rsi; struct IdFormat *
0x180029a52  call    ?ContainsChangeVersion@@YAJAEBUIdDescription@@AEBV?$SharedRefPtr@UISyncKnowledge@@@@AEBV?$SharedRefPtr@UISyncChange@@@@W4ChangeVersionKind@@@Z; ContainsChangeVersion(IdDescription const &,SharedRefPtr<ISyncKnowledge> const &,SharedRefPtr<ISyncChange> const &,ChangeVersionKind)
0x180029a57  mov     ebx, eax
0x180029a59  cmp     eax, 1
0x180029a5c  jz      short loc_180029A27
0x180029a5e  test    eax, eax
0x180029a60  js      loc_180029B76
0x180029a66  mov     rdx, rsi; struct IdFormat *
0x180029a69  mov     dword ptr [rbp+57h+var_78+4], r12d
0x180029a6d  lea     rcx, [rbp+57h+var_78]; this
0x180029a71  mov     [rbp+57h+var_70], r12
0x180029a75  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180029a7a  mov     ebx, eax
0x180029a7c  test    eax, eax
0x180029a7e  js      short loc_180029AA5
0x180029a80  mov     rcx, [rbp+57h+var_A8]
0x180029a84  lea     r8, [rbp+57h+var_58]
0x180029a88  movzx   eax, word ptr [rbp+57h+var_78+4]
0x180029a8c  mov     rdx, [rbp+57h+var_70]
0x180029a90  mov     dword ptr [rbp+57h+var_58], eax
0x180029a93  add     rdx, 4
0x180029a97  mov     rax, [rcx]
0x180029a9a  mov     rax, [rax+18h]
0x180029a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029aa3  mov     ebx, eax
0x180029aa5  test    ebx, ebx
0x180029aa7  js      short loc_180029B0C
0x180029aa9  lea     rsi, [rdi+0C8h]
0x180029ab0  movzx   eax, word ptr [rsi+4]
0x180029ab4  test    eax, eax
0x180029ab6  jz      short loc_180029AC8
0x180029ab8  lea     rdx, [rbp+57h+var_78]
0x180029abc  mov     rcx, rsi
0x180029abf  call    ??8SyncId@@QEBAHAEBV0@@Z; SyncId::operator==(SyncId const &)
0x180029ac4  test    eax, eax
0x180029ac6  jnz     short loc_180029B0C
0x180029ac8  lea     rdx, [rbp+57h+var_78]
0x180029acc  mov     rcx, rsi
0x180029acf  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x180029ad4  mov     rcx, [rbp+57h+var_A8]
0x180029ad8  lea     r8, [rbp+57h+var_B0]
0x180029adc  mov     rdx, [rdi+50h]
0x180029ae0  mov     [rbp+57h+var_B0], r12
0x180029ae4  mov     rax, [rcx]
0x180029ae7  mov     rax, [rax+60h]
0x180029aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af0  mov     ebx, eax
0x180029af2  test    eax, eax
0x180029af4  js      short loc_180029B03
0x180029af6  lea     rcx, [rdi+70h]
0x180029afa  lea     rdx, [rbp+57h+var_B0]
0x180029afe  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180029b03  lea     rcx, [rbp+57h+var_B0]
0x180029b07  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180029b0c  lea     rcx, [rbp+57h+var_78]; this
0x180029b10  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180029b15  test    ebx, ebx
0x180029b17  js      short loc_180029B76
0x180029b19  jmp     short loc_180029B28
0x180029b1b  lea     rdx, [rdi+60h]
0x180029b1f  lea     rcx, [rbp+57h+var_A8]
0x180029b23  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180029b28  mov     rdx, [rbp+57h+var_A8]
0x180029b2c  cmp     [rdi+78h], rdx
0x180029b30  jz      short loc_180029B76
0x180029b32  mov     rcx, [rdi+50h]
0x180029b36  lea     r8, [rbp+57h+var_B0]
0x180029b3a  mov     [rbp+57h+var_B0], r12
0x180029b3e  mov     rax, [rcx]
0x180029b41  mov     rax, [rax+60h]
0x180029b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b4a  mov     ebx, eax
0x180029b4c  test    eax, eax
0x180029b4e  js      short loc_180029B6D
0x180029b50  lea     rcx, [rdi+80h]
0x180029b57  lea     rdx, [rbp+57h+var_B0]
0x180029b5b  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180029b60  lea     rdx, [rbp+57h+var_A8]
0x180029b64  lea     rcx, [rdi+78h]
0x180029b68  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180029b6d  lea     rcx, [rbp+57h+var_B0]
0x180029b71  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180029b76  mov     [rbp+57h+var_A0], r12
0x180029b7a  test    ebx, ebx
0x180029b7c  js      loc_180029CC9
0x180029b82  test    r15, r15
0x180029b85  jnz     loc_180029D36
0x180029b8b  lea     rcx, [rbp+57h+var_B0]
0x180029b8f  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180029b94  lea     rdx, [rbp+57h+var_B0]; void **
0x180029b98  lea     rcx, IID_IProviderSyncServices; struct _GUID *
0x180029b9f  call    ?CreateSyncService@@YAJAEBU_GUID@@PEAPEAX@Z; CreateSyncService(_GUID const &,void * *)
0x180029ba4  mov     ebx, eax
0x180029ba6  test    eax, eax
0x180029ba8  js      short loc_180029C03
0x180029baa  mov     eax, [rdi+28h]
0x180029bad  lea     rdx, [rbp+57h+var_78]
0x180029bb1  mov     rcx, [rbp+57h+var_B0]
0x180029bb5  mov     dword ptr [rbp+57h+var_78+4], eax
0x180029bb8  movzx   eax, word ptr [rdi+2Ch]
0x180029bbc  mov     word ptr [rbp+57h+var_70], ax
0x180029bc0  xor     eax, eax
0x180029bc2  mov     word ptr [rbp+57h+var_70+2], ax
0x180029bc6  mov     eax, [rdi+30h]
0x180029bc9  mov     dword ptr [rbp+57h+var_70+4], eax
0x180029bcc  movzx   eax, word ptr [rdi+34h]
0x180029bd0  mov     [rbp+57h+var_68], ax
0x180029bd4  xor     eax, eax
0x180029bd6  mov     [rbp+57h+var_66], ax
0x180029bda  mov     eax, [rdi+38h]
0x180029bdd  mov     [rbp+57h+var_64], eax
0x180029be0  movzx   eax, word ptr [rdi+3Ch]
0x180029be4  mov     [rbp+57h+var_60], ax
0x180029be8  xor     eax, eax
0x180029bea  mov     [rbp+57h+var_5E], ax
0x180029bee  mov     dword ptr [rbp+57h+var_78], 1Ch
0x180029bf5  mov     rax, [rcx]
0x180029bf8  mov     rax, [rax+18h]
0x180029bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c01  mov     ebx, eax
0x180029c03  mov     dword ptr [rbp+57h+var_78+4], r12d
0x180029c07  mov     [rbp+57h+var_70], r12
0x180029c0b  test    ebx, ebx
0x180029c0d  js      loc_180029CB7
0x180029c13  lea     rdx, [rdi+28h]; struct IdFormat *
0x180029c17  lea     rcx, [rbp+57h+var_78]; this
0x180029c1b  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180029c20  mov     ebx, eax
0x180029c22  test    eax, eax
0x180029c24  js      loc_180029CB7
0x180029c2a  mov     rcx, [rdi+50h]
0x180029c2e  lea     r8, [rbp+57h+var_58]
0x180029c32  movzx   eax, word ptr [rbp+57h+var_78+4]
0x180029c36  mov     r15, [rbp+57h+var_70]
0x180029c3a  mov     dword ptr [rbp+57h+var_58], eax
0x180029c3d  mov     rax, [rcx]
0x180029c40  lea     rsi, [r15+4]
0x180029c44  mov     rdx, rsi
  ... truncated ...
```
