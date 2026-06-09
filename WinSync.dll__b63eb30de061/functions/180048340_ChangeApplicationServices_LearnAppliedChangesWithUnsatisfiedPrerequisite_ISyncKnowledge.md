# ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite(ISyncKnowledge *)

- ea: `0x180048340`
- end: `0x1800487a8`
- name: `?LearnAppliedChangesWithUnsatisfiedPrerequisite@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncKnowledge *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180047900`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x1800209f4`
- `0x180046bb0`
- `0x180048340`
- `0x1800487b0`
- `0x1800488a8`
- `0x1800488f4`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x18004837e`: `ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite`
- `0x18004876f`: `ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 NextElement; // rdi
  int v7; // eax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // eax
  int v13; // r14d
  __int64 v14; // rsi
  int v15; // eax
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // r10
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-50h] BYREF
  __int64 v23; // [rsp+38h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  __int64 v26; // [rsp+50h] [rbp-30h] BYREF
  __int64 v27; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v28[4]; // [rsp+60h] [rbp-20h] BYREF
  int v29; // [rsp+64h] [rbp-1Ch]
  __int64 v30; // [rsp+68h] [rbp-18h]
  _QWORD v31[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v34; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite");
  }
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  v4 = ScopedRefPtr<ISyncKnowledge2>::QueryInterface(&v24, *((_QWORD *)this + 10));
  v31[1] = 0;
  v31[0] = (char *)this + 176;
  v5 = v4;
  while ( v5 >= 0 )
  {
    NextElement = TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(v31);
    if ( !NextElement )
      break;
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    v7 = ScopedRefPtr<ISyncChangeWithPrerequisite>::QueryInterface(
           &v27,
           *(_QWORD *)(*(_QWORD *)(NextElement + 16) + 48LL));
    v5 = 0;
    if ( v7 != -2147467262 )
      v5 = v7;
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    if ( v5 >= 0 && v27 )
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 24LL))(v27, &v23);
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    if ( v5 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(NextElement + 16) + 48LL) + 72LL))(
             *(_QWORD *)(*(_QWORD *)(NextElement + 16) + 48LL),
             &v22);
      v5 = v8;
      if ( v8 == -2147217393 )
      {
        v5 = 0;
      }
      else if ( v8 < 0 )
      {
        goto LABEL_61;
      }
      if ( v22 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
        v13 = 0;
        v14 = 0;
        v29 = 0;
        v5 = v12;
        v30 = 0;
        if ( v12 >= 0 )
        {
          v15 = SyncId::InitializeForRetrieval((SyncId *)v28, (ChangeApplicationServices *)((char *)this + 56));
          v14 = v30;
          v5 = v15;
          v13 = v29;
        }
        while ( 2 )
        {
          if ( v5 < 0 )
          {
LABEL_60:
            SyncId::~SyncId((SyncId *)v28);
            goto LABEL_61;
          }
          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
          v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 24LL))(v22, 1, &v34);
          v5 = v16;
          if ( v16 == 1 )
          {
            v5 = 0;
            SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v34);
            goto LABEL_60;
          }
          if ( v16 >= 0 )
          {
            LODWORD(v32) = (unsigned __int16)v13;
            v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v34 + 32LL))(v34, v14 + 4, &v32);
          }
          v32 = 0;
          if ( v5 >= 0
            && (!(unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                                    *(_QWORD *)(NextElement + 16) + 56LL,
                                    v28,
                                    &v32)
             || !*(_DWORD *)(v32 + 20)) )
          {
            if ( !v23 )
              goto LABEL_48;
            v17 = v14;
            if ( (v13 & 0x20000) == 0 )
              v17 = v14 + 4;
            v18 = *(_QWORD *)(NextElement + 8);
            if ( (*(_DWORD *)(NextElement + 4) & 0x20000) == 0 )
              v18 += 4;
            v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v24 + 280LL))(
                   v24,
                   v23,
                   v18,
                   v17);
            if ( v5 == 1 )
            {
              v5 = 0;
LABEL_48:
              if ( !v33 )
                v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(NextElement + 16) + 48LL)
                                                                  + 88LL))(
                       *(_QWORD *)(*(_QWORD *)(NextElement + 16) + 48LL),
                       &v33);
              ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
              if ( v5 >= 0 )
              {
                v19 = v14;
                if ( (v13 & 0x20000) == 0 )
                  v19 = v14 + 4;
                v20 = *(_QWORD *)(NextElement + 8);
                if ( (*(_DWORD *)(NextElement + 4) & 0x20000) == 0 )
                  v20 += 4;
                v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v33 + 120LL))(
                       v33,
                       v20,
                       v19,
                       &v26);
                if ( v5 >= 0 )
                  v5 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))a2->lpVtbl->Union)(a2, v26);
              }
              SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
            }
          }
          SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v32);
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v34);
          continue;
        }
      }
      v9 = *(_QWORD *)(NextElement + 16);
      if ( !*(_DWORD *)(v9 + 72) && *(_DWORD *)(v9 + 20) == (_DWORD)v22 )
      {
        if ( v23 )
        {
          v10 = *(_QWORD *)(NextElement + 8);
          if ( (*(_DWORD *)(NextElement + 4) & 0x20000) == 0 )
            v10 += 4;
          v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 272LL))(v24, v23, v10);
          if ( v5 != 1 )
            goto LABEL_61;
          v5 = 0;
        }
        if ( !v33 )
          v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*(_QWORD *)(NextElement + 16) + 48LL) + 88LL))(
                 *(_QWORD *)(*(_QWORD *)(NextElement + 16) + 48LL),
                 &v33);
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        if ( v5 >= 0 )
        {
          v11 = *(_QWORD *)(NextElement + 8);
          if ( (*(_DWORD *)(NextElement + 4) & 0x20000) == 0 )
            v11 += 4;
          v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 112LL))(v33, v11, &v25);
          if ( v5 >= 0 )
            v5 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))a2->lpVtbl->Union)(a2, v25);
        }
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v25);
      }
    }
LABEL_61:
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v22);
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v33);
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v23);
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v27);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite",
      v5);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180048340  push    rbp
0x180048342  push    rbx
0x180048343  push    rsi
0x180048344  push    rdi
0x180048345  push    r12
0x180048347  push    r14
0x180048349  push    r15
0x18004834b  mov     rbp, rsp
0x18004834e  sub     rsp, 80h
0x180048355  mov     r12, rdx
0x180048358  mov     r15, rcx
0x18004835b  mov     rcx, cs:WPP_GLOBAL_Control
0x180048362  lea     rsi, WPP_GLOBAL_Control
0x180048369  cmp     rcx, rsi
0x18004836c  jz      short loc_180048396
0x18004836e  test    byte ptr [rcx+1Ch], 80h
0x180048372  jz      short loc_180048396
0x180048374  cmp     byte ptr [rcx+19h], 5
0x180048378  jb      short loc_180048396
0x18004837a  mov     rcx, [rcx+10h]
0x18004837e  lea     r9, aChangeapplicat_22; "ChangeApplicationServices::LearnApplied"...
0x180048385  mov     edx, 32h ; '2'
0x18004838a  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048391  call    WPP_SF_s
0x180048396  lea     rcx, [rbp+var_40]
0x18004839a  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004839f  mov     rdx, [r15+50h]
0x1800483a3  lea     rcx, [rbp+var_40]
0x1800483a7  call    ?QueryInterface@?$ScopedRefPtr@UISyncKnowledge2@@@@QEAAJPEAUIUnknown@@@Z; ScopedRefPtr<ISyncKnowledge2>::QueryInterface(IUnknown *)
0x1800483ac  mov     [rbp+var_8], 0
0x1800483b4  lea     rcx, [r15+0B0h]
0x1800483bb  mov     [rbp+var_10], rcx
0x1800483bf  mov     ebx, eax
0x1800483c1  test    eax, eax
0x1800483c3  js      loc_180048753
0x1800483c9  lea     rcx, [rbp+var_10]
0x1800483cd  call    ?GetNextElement@?$TableEnumerator@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(void)
0x1800483d2  mov     rdi, rax
0x1800483d5  test    rax, rax
0x1800483d8  jz      loc_18004874C
0x1800483de  lea     rcx, [rbp+var_28]
0x1800483e2  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x1800483e7  mov     rdx, [rdi+10h]
0x1800483eb  lea     rcx, [rbp+var_28]
0x1800483ef  mov     rdx, [rdx+30h]
0x1800483f3  call    ?QueryInterface@?$ScopedRefPtr@UISyncChangeWithPrerequisite@@@@QEAAJPEAUIUnknown@@@Z; ScopedRefPtr<ISyncChangeWithPrerequisite>::QueryInterface(IUnknown *)
0x1800483f8  xor     ebx, ebx
0x1800483fa  lea     rcx, [rbp+var_48]
0x1800483fe  cmp     eax, 80004002h
0x180048403  cmovnz  ebx, eax
0x180048406  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004840b  test    ebx, ebx
0x18004840d  js      short loc_18004842A
0x18004840f  mov     rcx, [rbp+var_28]
0x180048413  test    rcx, rcx
0x180048416  jz      short loc_18004842A
0x180048418  mov     rax, [rcx]
0x18004841b  lea     rdx, [rbp+var_48]
0x18004841f  mov     rax, [rax+18h]
0x180048423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048428  mov     ebx, eax
0x18004842a  lea     rcx, [rbp+arg_10]
0x18004842e  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180048433  lea     rcx, [rbp+var_50]
0x180048437  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004843c  test    ebx, ebx
0x18004843e  js      loc_180048720
0x180048444  mov     rax, [rdi+10h]
0x180048448  lea     rdx, [rbp+var_50]
0x18004844c  mov     rcx, [rax+30h]
0x180048450  mov     rax, [rcx]
0x180048453  mov     rax, [rax+48h]
0x180048457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004845c  mov     ebx, eax
0x18004845e  cmp     eax, 8004100Fh
0x180048463  jnz     short loc_180048469
0x180048465  xor     ebx, ebx
0x180048467  jmp     short loc_180048471
0x180048469  test    eax, eax
0x18004846b  js      loc_180048720
0x180048471  mov     rcx, [rbp+var_50]
0x180048475  test    rcx, rcx
0x180048478  jnz     loc_18004854F
0x18004847e  mov     rax, [rdi+10h]
0x180048482  cmp     [rax+48h], ecx
0x180048485  jnz     loc_180048720
0x18004848b  cmp     [rax+14h], ecx
0x18004848e  jnz     loc_180048720
0x180048494  mov     rdx, [rbp+var_48]
0x180048498  test    rdx, rdx
0x18004849b  jz      short loc_1800484D0
0x18004849d  mov     r8, [rdi+8]
0x1800484a1  mov     rcx, [rbp+var_40]
0x1800484a5  test    dword ptr [rdi+4], 20000h
0x1800484ac  lea     rax, [r8+4]
0x1800484b0  mov     r9, [rcx]
0x1800484b3  cmovz   r8, rax
0x1800484b7  mov     rax, [r9+110h]
0x1800484be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484c3  mov     ebx, eax
0x1800484c5  cmp     eax, 1
0x1800484c8  jnz     loc_180048720
0x1800484ce  xor     ebx, ebx
0x1800484d0  cmp     [rbp+arg_10], 0
0x1800484d5  jnz     short loc_1800484F1
0x1800484d7  mov     rax, [rdi+10h]
0x1800484db  lea     rdx, [rbp+arg_10]
0x1800484df  mov     rcx, [rax+30h]
0x1800484e3  mov     rax, [rcx]
0x1800484e6  mov     rax, [rax+58h]
0x1800484ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484ef  mov     ebx, eax
0x1800484f1  lea     rcx, [rbp+var_38]
0x1800484f5  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x1800484fa  test    ebx, ebx
0x1800484fc  js      short loc_180048541
0x1800484fe  mov     rdx, [rdi+8]
0x180048502  lea     r8, [rbp+var_38]
0x180048506  mov     rcx, [rbp+arg_10]
0x18004850a  test    dword ptr [rdi+4], 20000h
0x180048511  lea     rax, [rdx+4]
0x180048515  mov     r9, [rcx]
0x180048518  cmovz   rdx, rax
0x18004851c  mov     rax, [r9+70h]
0x180048520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048525  mov     ebx, eax
0x180048527  test    eax, eax
0x180048529  js      short loc_180048541
0x18004852b  mov     rax, [r12]
0x18004852f  mov     rcx, r12
0x180048532  mov     rdx, [rbp+var_38]
0x180048536  mov     rax, [rax+68h]
0x18004853a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004853f  mov     ebx, eax
0x180048541  lea     rcx, [rbp+var_38]
0x180048545  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004854a  jmp     loc_180048720
0x18004854f  mov     rax, [rcx]
0x180048552  mov     rax, [rax+28h]
0x180048556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004855b  xor     r14d, r14d
0x18004855e  xor     esi, esi
0x180048560  mov     [rbp+var_1C], r14d
0x180048564  mov     ebx, eax
0x180048566  mov     [rbp+var_18], rsi
0x18004856a  test    eax, eax
0x18004856c  js      short loc_180048585
0x18004856e  lea     rdx, [r15+38h]; struct IdFormat *
0x180048572  lea     rcx, [rbp+var_20]; this
0x180048576  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004857b  mov     rsi, [rbp+var_18]
0x18004857f  mov     ebx, eax
0x180048581  mov     r14d, [rbp+var_1C]
0x180048585  test    ebx, ebx
0x180048587  js      loc_180048717
0x18004858d  lea     rcx, [rbp+arg_18]
0x180048591  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180048596  mov     rcx, [rbp+var_50]
0x18004859a  lea     r8, [rbp+arg_18]
0x18004859e  xor     r9d, r9d
0x1800485a1  mov     rax, [rcx]
0x1800485a4  lea     edx, [r9+1]
0x1800485a8  mov     rax, [rax+18h]
0x1800485ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485b1  mov     ebx, eax
0x1800485b3  cmp     eax, 1
0x1800485b6  jz      loc_18004870C
0x1800485bc  test    eax, eax
0x1800485be  js      short loc_1800485E1
0x1800485c0  mov     rcx, [rbp+arg_18]
0x1800485c4  lea     rdx, [rsi+4]
0x1800485c8  movzx   eax, r14w
0x1800485cc  lea     r8, [rbp+arg_0]
0x1800485d0  mov     dword ptr [rbp+arg_0], eax
0x1800485d3  mov     rax, [rcx]
0x1800485d6  mov     rax, [rax+20h]
0x1800485da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485df  mov     ebx, eax
0x1800485e1  mov     [rbp+arg_0], 0
0x1800485e9  test    ebx, ebx
0x1800485eb  js      loc_1800486F5
0x1800485f1  mov     rcx, [rdi+10h]
0x1800485f5  lea     r8, [rbp+arg_0]
0x1800485f9  add     rcx, 38h ; '8'
0x1800485fd  lea     rdx, [rbp+var_20]
0x180048601  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180048606  test    al, al
0x180048608  jz      short loc_180048618
0x18004860a  mov     rax, [rbp+arg_0]
0x18004860e  cmp     dword ptr [rax+14h], 0
0x180048612  jnz     loc_1800486F5
0x180048618  mov     rdx, [rbp+var_48]
0x18004861c  test    rdx, rdx
0x18004861f  jz      short loc_180048666
0x180048621  mov     rcx, [rbp+var_40]
0x180048625  mov     r8d, 20000h
0x18004862b  mov     r9, rsi
0x18004862e  mov     rax, [rcx]
0x180048631  test    r8d, r14d
0x180048634  jnz     short loc_18004863A
0x180048636  lea     r9, [rsi+4]
0x18004863a  test    [rdi+4], r8d
0x18004863e  mov     r10, [rdi+8]
0x180048642  mov     rax, [rax+118h]
0x180048649  lea     r8, [r10+4]
0x18004864d  cmovz   r10, r8
0x180048651  mov     r8, r10
0x180048654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048659  mov     ebx, eax
0x18004865b  cmp     eax, 1
0x18004865e  jnz     loc_1800486F5
0x180048664  xor     ebx, ebx
0x180048666  cmp     [rbp+arg_10], 0
0x18004866b  jnz     short loc_180048687
0x18004866d  mov     rax, [rdi+10h]
0x180048671  lea     rdx, [rbp+arg_10]
0x180048675  mov     rcx, [rax+30h]
0x180048679  mov     rax, [rcx]
0x18004867c  mov     rax, [rax+58h]
0x180048680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048685  mov     ebx, eax
0x180048687  lea     rcx, [rbp+var_30]
0x18004868b  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180048690  test    ebx, ebx
0x180048692  js      short loc_1800486EC
0x180048694  mov     rcx, [rbp+arg_10]
0x180048698  mov     r8d, 20000h
0x18004869e  mov     rax, [rcx]
0x1800486a1  mov     r10, [rax+78h]
0x1800486a5  mov     rax, rsi
0x1800486a8  test    r8d, r14d
0x1800486ab  jnz     short loc_1800486B1
0x1800486ad  lea     rax, [rsi+4]
0x1800486b1  test    [rdi+4], r8d
0x1800486b5  lea     r9, [rbp+var_30]
0x1800486b9  mov     rdx, [rdi+8]
0x1800486bd  lea     r8, [rdx+4]
0x1800486c1  cmovz   rdx, r8
0x1800486c5  mov     r8, rax
0x1800486c8  mov     rax, r10
0x1800486cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486d0  mov     ebx, eax
0x1800486d2  test    eax, eax
0x1800486d4  js      short loc_1800486EC
0x1800486d6  mov     rax, [r12]
0x1800486da  mov     rcx, r12
0x1800486dd  mov     rdx, [rbp+var_30]
0x1800486e1  mov     rax, [rax+68h]
0x1800486e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486ea  mov     ebx, eax
0x1800486ec  lea     rcx, [rbp+var_30]
0x1800486f0  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800486f5  lea     rcx, [rbp+arg_0]
0x1800486f9  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x1800486fe  lea     rcx, [rbp+arg_18]
0x180048702  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048707  jmp     loc_180048585
0x18004870c  xor     ebx, ebx
0x18004870e  lea     rcx, [rbp+arg_18]
0x180048712  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048717  lea     rcx, [rbp+var_20]; this
0x18004871b  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180048720  lea     rcx, [rbp+var_50]
0x180048724  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048729  lea     rcx, [rbp+arg_10]
0x18004872d  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048732  lea     rcx, [rbp+var_48]
0x180048736  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004873b  lea     rcx, [rbp+var_28]
0x18004873f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048744  test    ebx, ebx
0x180048746  jns     loc_1800483C9
0x18004874c  lea     rsi, WPP_GLOBAL_Control
0x180048753  mov     rcx, cs:WPP_GLOBAL_Control
0x18004875a  cmp     rcx, rsi
0x18004875d  jz      short loc_18004878B
0x18004875f  test    byte ptr [rcx+1Ch], 80h
0x180048763  jz      short loc_18004878B
0x180048765  cmp     byte ptr [rcx+19h], 5
0x180048769  jb      short loc_18004878B
0x18004876b  mov     rcx, [rcx+10h]
0x18004876f  lea     r9, aChangeapplicat_22; "ChangeApplicationServices::LearnApplied"...
0x180048776  mov     edx, 33h ; '3'
0x18004877b  mov     [rsp+80h+var_60], ebx
0x18004877f  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048786  call    WPP_SF_sD
0x18004878b  lea     rcx, [rbp+var_40]
0x18004878f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048794  mov     eax, ebx
0x180048796  add     rsp, 80h
0x18004879d  pop     r15
0x18004879f  pop     r14
0x1800487a1  pop     r12
0x1800487a3  pop     rdi
0x1800487a4  pop     rsi
0x1800487a5  pop     rbx
0x1800487a6  pop     rbp
0x1800487a7  retn
```
