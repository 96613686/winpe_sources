# ChangeApplicationServices::GetUpdatedDestinationKnowledge(ISyncKnowledge * *,IForgottenKnowledge * *)

- ea: `0x180047cd0`
- end: `0x18004823d`
- name: `?GetUpdatedDestinationKnowledge@ChangeApplicationServices@@UEAAJPEAPEAUISyncKnowledge@@PEAPEAUIForgottenKnowledge@@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncKnowledge **, struct IForgottenKnowledge **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x1800084ec`
- `0x18001a038`
- `0x18001ae20`
- `0x18001dc70`
- `0x1800209f4`
- `0x180047cd0`
- `0x180073fac`
- `0x180074098`
- `0x180094010`

## string_xrefs

- `0x180047d16`: `ChangeApplicationServices::GetUpdatedDestinationKnowledge`
- `0x1800481f2`: `ChangeApplicationServices::GetUpdatedDestinationKnowledge`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::GetUpdatedDestinationKnowledge(
        ChangeApplicationServices *this,
        struct ISyncKnowledge **a2,
        struct IForgottenKnowledge **a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct IForgottenKnowledge **); // rbx
  __int64 NextElement; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v26; // r8
  __int64 v27; // rdx
  struct IForgottenKnowledge **v28; // r8
  GUID *v29; // rdx
  struct ISyncKnowledge *v31; // [rsp+30h] [rbp-50h] BYREF
  __int64 v32; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  __int64 v34; // [rsp+48h] [rbp-38h] BYREF
  __int64 v35; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v37[3]; // [rsp+68h] [rbp-18h] BYREF
  struct IForgottenKnowledge *v38; // [rsp+C8h] [rbp+48h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, struct IForgottenKnowledge **); // [rsp+D8h] [rbp+58h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::GetUpdatedDestinationKnowledge");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_6;
  if ( *((_DWORD *)this + 9) != 3 )
  {
    if ( *((_DWORD *)this + 9) != 2 )
    {
      v7 = -2147217407;
      goto LABEL_25;
    }
LABEL_9:
    v8 = *((_QWORD *)this + 10);
    v31 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v8 + 80LL))(v8, &v31);
    v38 = 0;
    v7 = v9;
    if ( v9 >= 0 )
    {
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_16;
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IForgottenKnowledge **)))(**((_QWORD **)this + 11) + 80LL))(
             *((_QWORD *)this + 11),
             &v39);
      if ( v7 >= 0 )
      {
        v10 = v39;
        if ( v38 )
          ((void (__fastcall *)(struct IForgottenKnowledge *))v38->lpVtbl->Release)(v38);
        v7 = (**v10)(v10, &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2, &v38);
      }
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v39);
      if ( v7 >= 0 )
      {
LABEL_16:
        v36[1] = 0;
        v36[0] = (char *)this + 176;
        while ( 1 )
        {
          NextElement = TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(v36);
          v12 = NextElement;
          if ( !NextElement )
            break;
          v13 = *(_QWORD *)(NextElement + 16) + 48LL;
          v32 = 0;
          v14 = GetLearnedKnowledgeForChange(v13, (char *)this + 80, &v32);
          v39 = 0;
          v7 = v14;
          if ( v14 >= 0 )
          {
            v7 = GetLearnedForgottenKnowledgeForChange(*(_QWORD *)(v12 + 16) + 48LL, &v39);
            if ( v7 >= 0 )
            {
              if ( !v39 )
                goto LABEL_30;
              if ( *((_DWORD *)this + 9) == 2 )
              {
                v7 = -2147217368;
              }
              else
              {
                if ( !v39 )
                  goto LABEL_30;
                v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 152LL))(v32);
                v7 = v15;
                if ( v15 == 1 )
                {
                  v7 = -2147217371;
                }
                else if ( v15 >= 0 )
                {
LABEL_30:
                  v16 = *(_QWORD *)(v12 + 16);
                  if ( !*(_DWORD *)(v16 + 72) )
                  {
                    if ( !*(_DWORD *)(v16 + 20) )
                      goto LABEL_78;
                    v17 = *(_QWORD *)(v12 + 8);
                    if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                      v17 += 4;
                    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 136LL))(v32, v17);
                    if ( v7 >= 0 )
                    {
                      if ( !v39 )
                        goto LABEL_78;
                      v18 = *(_QWORD *)(v12 + 8);
                      if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                        v18 += 4;
                      v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IForgottenKnowledge **), __int64))(*v39)[17])(
                             v39,
                             v18);
LABEL_77:
                      if ( v7 >= 0 )
                      {
LABEL_78:
                        v7 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))v31->lpVtbl->Union)(v31, v32);
                        if ( v7 >= 0 && v39 )
                        {
                          if ( v38 )
                            v7 = ((__int64 (__fastcall *)(struct IForgottenKnowledge *))v38->lpVtbl->Union)(v38);
                          else
                            SharedRefPtr<IForgottenKnowledge>::operator=(&v38, &v39);
                        }
                      }
                    }
                    goto LABEL_83;
                  }
                  v37[0] = v16 + 56;
                  v37[1] = 0;
                  while ( 1 )
                  {
                    v19 = TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v37);
                    v20 = v19;
                    if ( !v19 )
                      goto LABEL_78;
                    if ( !*(_DWORD *)(*(_QWORD *)(v19 + 16) + 20LL) )
                      break;
                    if ( v7 < 0 )
                      goto LABEL_83;
                    v26 = *(_QWORD *)(v19 + 8);
                    v27 = *(_QWORD *)(v12 + 8);
                    if ( (*(_DWORD *)(v19 + 4) & 0x20000) == 0 )
                      v26 += 4;
                    if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                      v27 += 4;
                    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 144LL))(v32, v27, v26);
                    if ( v7 < 0 )
                      goto LABEL_83;
                    if ( v39 )
                    {
                      v28 = *(struct IForgottenKnowledge ***)(v20 + 8);
                      v29 = *(GUID **)(v12 + 8);
                      if ( (*(_DWORD *)(v20 + 4) & 0x20000) == 0 )
                        v28 = (struct IForgottenKnowledge **)((char *)v28 + 4);
                      if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                        v29 = (GUID *)((char *)v29 + 4);
                      v7 = (*v39)[18](v39, v29, v28);
LABEL_76:
                      if ( v7 < 0 )
                        goto LABEL_77;
                      continue;
                    }
                  }
                  if ( *(_DWORD *)(*(_QWORD *)(v12 + 16) + 20LL) )
                  {
                    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
                    v21 = *(_QWORD *)(v20 + 8);
                    v22 = *(_QWORD *)(v12 + 8);
                    if ( (*(_DWORD *)(v20 + 4) & 0x20000) == 0 )
                      v21 += 4;
                    if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                      v22 += 4;
                    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v32 + 120LL))(
                           v32,
                           v22,
                           v21,
                           &v34);
                    if ( v7 >= 0 )
                    {
                      v7 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))v31->lpVtbl->Union)(v31, v34);
                      if ( v7 >= 0 )
                      {
                        if ( v39 )
                        {
                          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
                          v23 = *(_QWORD *)(v20 + 8);
                          v24 = *(_QWORD *)(v12 + 8);
                          if ( (*(_DWORD *)(v20 + 4) & 0x20000) == 0 )
                            v23 += 4;
                          if ( (*(_DWORD *)(v12 + 4) & 0x20000) == 0 )
                            v24 += 4;
                          v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IForgottenKnowledge **), __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*v39)[15])(
                                 v39,
                                 v24,
                                 v23,
                                 &v33);
                          if ( v7 >= 0 )
                          {
                            if ( v38 )
                            {
                              v7 = ((__int64 (__fastcall *)(struct IForgottenKnowledge *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))v38->lpVtbl->Union)(
                                     v38,
                                     v33);
                            }
                            else
                            {
                              v25 = v33;
                              v35 = 0;
                              if ( v33 )
                                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v33)[2])(v33);
                              v7 = (**v25)(v25, &GUID_615bbb53_c945_4203_bf4b_2cb65919a0aa, (__int64 *)&v33);
                              if ( v7 >= 0 )
                                SharedRefPtr<IForgottenKnowledge>::operator=(&v38, &v35);
                              SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v35);
                            }
                          }
                          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v33);
                        }
                      }
                    }
                    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v34);
                  }
                  goto LABEL_76;
                }
              }
            }
          }
LABEL_83:
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v39);
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v32);
          if ( v7 < 0 )
            goto LABEL_87;
        }
        *a2 = v31;
        v31 = 0;
        if ( a3 )
        {
          *a3 = v38;
          v38 = 0;
        }
      }
    }
LABEL_87:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_88;
  }
  if ( a3 )
    goto LABEL_9;
LABEL_6:
  v7 = -2147467261;
LABEL_25:
  v31 = 0;
  v38 = 0;
LABEL_88:
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      25,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::GetUpdatedDestinationKnowledge",
      v7);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v38);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047cd0  mov     [rsp-38h+arg_0], rbx
0x180047cd5  push    rbp
0x180047cd6  push    rsi
0x180047cd7  push    rdi
0x180047cd8  push    r12
0x180047cda  push    r13
0x180047cdc  push    r14
0x180047cde  push    r15
0x180047ce0  mov     rbp, rsp
0x180047ce3  sub     rsp, 80h
0x180047cea  mov     r15, r8
0x180047ced  mov     r12, rdx
0x180047cf0  mov     r14, rcx
0x180047cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cfa  lea     rax, WPP_GLOBAL_Control
0x180047d01  cmp     rcx, rax
0x180047d04  jz      short loc_180047D35
0x180047d06  test    byte ptr [rcx+1Ch], 80h
0x180047d0a  jz      short loc_180047D35
0x180047d0c  cmp     byte ptr [rcx+19h], 5
0x180047d10  jb      short loc_180047D35
0x180047d12  mov     rcx, [rcx+10h]
0x180047d16  lea     r9, aChangeapplicat_11; "ChangeApplicationServices::GetUpdatedDe"...
0x180047d1d  mov     edx, 18h
0x180047d22  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047d29  call    WPP_SF_s
0x180047d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d35  xor     r13d, r13d
0x180047d38  test    r12, r12
0x180047d3b  jnz     short loc_180047D47
0x180047d3d  mov     ebx, 80004003h
0x180047d42  jmp     loc_180047E7B
0x180047d47  cmp     dword ptr [r14+24h], 3
0x180047d4c  jnz     loc_180047E6B
0x180047d52  test    r15, r15
0x180047d55  jz      short loc_180047D3D
0x180047d57  mov     rcx, [r14+50h]
0x180047d5b  lea     rdx, [rbp+var_50]
0x180047d5f  mov     [rbp+var_50], r13
0x180047d63  mov     rax, [rcx]
0x180047d66  mov     rax, [rax+50h]
0x180047d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d6f  mov     [rbp+arg_8], r13
0x180047d73  mov     ebx, eax
0x180047d75  test    eax, eax
0x180047d77  js      loc_1800481CF
0x180047d7d  cmp     [r14+58h], r13
0x180047d81  jz      short loc_180047DEB
0x180047d83  lea     rcx, [rbp+arg_18]
0x180047d87  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180047d8c  mov     rcx, [r14+58h]
0x180047d90  lea     rdx, [rbp+arg_18]
0x180047d94  mov     rax, [rcx]
0x180047d97  mov     rax, [rax+50h]
0x180047d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047da0  mov     ebx, eax
0x180047da2  test    eax, eax
0x180047da4  js      short loc_180047DDA
0x180047da6  mov     rcx, [rbp+arg_8]
0x180047daa  mov     rbx, [rbp+arg_18]
0x180047dae  test    rcx, rcx
0x180047db1  jz      short loc_180047DBF
0x180047db3  mov     rax, [rcx]
0x180047db6  mov     rax, [rax+10h]
0x180047dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dbf  mov     rax, [rbx]
0x180047dc2  lea     r8, [rbp+arg_8]
0x180047dc6  lea     rdx, _GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2
0x180047dcd  mov     rcx, rbx
0x180047dd0  mov     rax, [rax]
0x180047dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dd8  mov     ebx, eax
0x180047dda  lea     rcx, [rbp+arg_18]
0x180047dde  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180047de3  test    ebx, ebx
0x180047de5  js      loc_1800481CF
0x180047deb  lea     rax, [r14+0B0h]
0x180047df2  mov     [rbp+var_20], r13
0x180047df6  mov     [rbp+var_28], rax
0x180047dfa  lea     rcx, [rbp+var_28]
0x180047dfe  call    ?GetNextElement@?$TableEnumerator@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(void)
0x180047e03  mov     rdi, rax
0x180047e06  test    rax, rax
0x180047e09  jz      loc_1800481B3
0x180047e0f  mov     rcx, [rax+10h]
0x180047e13  lea     rdx, [r14+50h]
0x180047e17  add     rcx, 30h ; '0'
0x180047e1b  mov     [rbp+var_48], r13
0x180047e1f  lea     r8, [rbp+var_48]
0x180047e23  call    ?GetLearnedKnowledgeForChange@@YAJAEAV?$SharedRefPtr@UISyncChange@@@@AEAV?$SharedRefPtr@UISyncKnowledge@@@@1@Z; GetLearnedKnowledgeForChange(SharedRefPtr<ISyncChange> &,SharedRefPtr<ISyncKnowledge> &,SharedRefPtr<ISyncKnowledge> &)
0x180047e28  mov     [rbp+arg_18], r13
0x180047e2c  mov     ebx, eax
0x180047e2e  test    eax, eax
0x180047e30  js      loc_180048197
0x180047e36  mov     rcx, [rdi+10h]
0x180047e3a  lea     rdx, [rbp+arg_18]
0x180047e3e  add     rcx, 30h ; '0'
0x180047e42  call    ?GetLearnedForgottenKnowledgeForChange@@YAJAEAV?$SharedRefPtr@UISyncChange@@@@AEAV?$SharedRefPtr@UIForgottenKnowledge@@@@@Z; GetLearnedForgottenKnowledgeForChange(SharedRefPtr<ISyncChange> &,SharedRefPtr<IForgottenKnowledge> &)
0x180047e47  mov     ebx, eax
0x180047e49  test    eax, eax
0x180047e4b  js      loc_180048197
0x180047e51  mov     rdx, [rbp+arg_18]
0x180047e55  test    rdx, rdx
0x180047e58  jz      short loc_180047EB9
0x180047e5a  cmp     dword ptr [r14+24h], 2
0x180047e5f  jnz     short loc_180047E88
0x180047e61  mov     ebx, 80041028h
0x180047e66  jmp     loc_180048197
0x180047e6b  cmp     dword ptr [r14+24h], 2
0x180047e70  jz      loc_180047D57
0x180047e76  mov     ebx, 80041001h
0x180047e7b  mov     [rbp+var_50], r13
0x180047e7f  mov     [rbp+arg_8], r13
0x180047e83  jmp     loc_1800481D6
0x180047e88  test    rdx, rdx
0x180047e8b  jz      short loc_180047EB9
0x180047e8d  mov     rcx, [rbp+var_48]
0x180047e91  mov     rax, [rcx]
0x180047e94  mov     rax, [rax+98h]
0x180047e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ea0  mov     ebx, eax
0x180047ea2  cmp     eax, 1
0x180047ea5  jnz     short loc_180047EB1
0x180047ea7  mov     ebx, 80041025h
0x180047eac  jmp     loc_180048197
0x180047eb1  test    eax, eax
0x180047eb3  js      loc_180048197
0x180047eb9  mov     rax, [rdi+10h]
0x180047ebd  lea     rcx, [rax+38h]
0x180047ec1  cmp     [rcx+10h], r13d
0x180047ec5  jnz     short loc_180047F37
0x180047ec7  cmp     [rax+14h], r13d
0x180047ecb  jz      loc_18004814E
0x180047ed1  mov     rdx, [rdi+8]
0x180047ed5  mov     rcx, [rbp+var_48]
0x180047ed9  test    dword ptr [rdi+4], 20000h
0x180047ee0  lea     rax, [rdx+4]
0x180047ee4  mov     r8, [rcx]
0x180047ee7  cmovz   rdx, rax
0x180047eeb  mov     rax, [r8+88h]
0x180047ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ef7  mov     ebx, eax
0x180047ef9  test    eax, eax
0x180047efb  js      loc_180048197
0x180047f01  mov     rcx, [rbp+arg_18]
0x180047f05  test    rcx, rcx
0x180047f08  jz      loc_18004814E
0x180047f0e  mov     rdx, [rdi+8]
0x180047f12  mov     r8, [rcx]
0x180047f15  test    dword ptr [rdi+4], 20000h
0x180047f1c  lea     rax, [rdx+4]
0x180047f20  cmovz   rdx, rax
0x180047f24  mov     rax, [r8+88h]
0x180047f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f30  mov     ebx, eax
0x180047f32  jmp     loc_18004814A
0x180047f37  mov     [rbp+var_18], rcx
0x180047f3b  mov     [rbp+var_10], r13
0x180047f3f  lea     rcx, [rbp+var_18]
0x180047f43  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x180047f48  mov     rsi, rax
0x180047f4b  test    rax, rax
0x180047f4e  jz      loc_18004814E
0x180047f54  mov     rcx, [rax+10h]
0x180047f58  cmp     [rcx+14h], r13d
0x180047f5c  jnz     loc_1800480B3
0x180047f62  mov     rcx, [rdi+10h]
0x180047f66  cmp     [rcx+14h], r13d
0x180047f6a  jz      loc_180048142
0x180047f70  lea     rcx, [rbp+var_38]
0x180047f74  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180047f79  mov     r8, [rsi+8]
0x180047f7d  mov     r9d, 20000h
0x180047f83  test    [rsi+4], r9d
0x180047f87  mov     rdx, [rdi+8]
0x180047f8b  mov     rcx, [rbp+var_48]
0x180047f8f  lea     rax, [r8+4]
0x180047f93  cmovz   r8, rax
0x180047f97  test    [rdi+4], r9d
0x180047f9b  lea     rax, [rdx+4]
0x180047f9f  mov     r10, [rcx]
0x180047fa2  lea     r9, [rbp+var_38]
0x180047fa6  cmovz   rdx, rax
0x180047faa  mov     rax, [r10+78h]
0x180047fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fb3  mov     ebx, eax
0x180047fb5  test    eax, eax
0x180047fb7  js      loc_1800480A5
0x180047fbd  mov     rcx, [rbp+var_50]
0x180047fc1  mov     rdx, [rbp+var_38]
0x180047fc5  mov     rax, [rcx]
0x180047fc8  mov     rax, [rax+68h]
0x180047fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fd1  mov     ebx, eax
0x180047fd3  test    eax, eax
0x180047fd5  js      loc_1800480A5
0x180047fdb  cmp     [rbp+arg_18], r13
0x180047fdf  jz      loc_1800480A5
0x180047fe5  lea     rcx, [rbp+var_40]
0x180047fe9  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180047fee  mov     r8, [rsi+8]
0x180047ff2  mov     r9d, 20000h
0x180047ff8  test    [rsi+4], r9d
0x180047ffc  mov     rdx, [rdi+8]
0x180048000  mov     rcx, [rbp+arg_18]
0x180048004  lea     rax, [r8+4]
0x180048008  cmovz   r8, rax
0x18004800c  test    [rdi+4], r9d
0x180048010  lea     rax, [rdx+4]
0x180048014  mov     r10, [rcx]
0x180048017  lea     r9, [rbp+var_40]
0x18004801b  cmovz   rdx, rax
0x18004801f  mov     rax, [r10+78h]
0x180048023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048028  mov     ebx, eax
0x18004802a  test    eax, eax
0x18004802c  js      short loc_18004809C
0x18004802e  mov     rcx, [rbp+arg_8]
0x180048032  test    rcx, rcx
0x180048035  jnz     short loc_18004808A
0x180048037  mov     rbx, [rbp+var_40]
0x18004803b  mov     [rbp+var_30], r13
0x18004803f  test    rbx, rbx
0x180048042  jz      short loc_180048053
0x180048044  mov     rax, [rbx]
0x180048047  mov     rcx, rbx
0x18004804a  mov     rax, [rax+10h]
0x18004804e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048053  mov     rax, [rbx]
0x180048056  lea     r8, [rbp+var_40]
0x18004805a  lea     rdx, _GUID_615bbb53_c945_4203_bf4b_2cb65919a0aa
0x180048061  mov     rcx, rbx
0x180048064  mov     rax, [rax]
0x180048067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004806c  mov     ebx, eax
0x18004806e  test    eax, eax
0x180048070  js      short loc_18004807F
0x180048072  lea     rdx, [rbp+var_30]
0x180048076  lea     rcx, [rbp+arg_8]
0x18004807a  call    ??4?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IForgottenKnowledge>::operator=(SharedRefPtr<IForgottenKnowledge> const &)
0x18004807f  lea     rcx, [rbp+var_30]
0x180048083  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048088  jmp     short loc_18004809C
0x18004808a  mov     rax, [rcx]
0x18004808d  mov     rdx, [rbp+var_40]
0x180048091  mov     rax, [rax+68h]
0x180048095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004809a  mov     ebx, eax
0x18004809c  lea     rcx, [rbp+var_40]
0x1800480a0  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800480a5  lea     rcx, [rbp+var_38]
0x1800480a9  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800480ae  jmp     loc_180048142
0x1800480b3  test    ebx, ebx
0x1800480b5  js      loc_180048197
0x1800480bb  mov     r8, [rax+8]
0x1800480bf  mov     r10d, 20000h
0x1800480c5  test    [rax+4], r10d
0x1800480c9  mov     rdx, [rdi+8]
0x1800480cd  mov     rcx, [rbp+var_48]
0x1800480d1  lea     rax, [r8+4]
0x1800480d5  cmovz   r8, rax
0x1800480d9  test    [rdi+4], r10d
0x1800480dd  lea     rax, [rdx+4]
0x1800480e1  mov     r9, [rcx]
0x1800480e4  cmovz   rdx, rax
0x1800480e8  mov     rax, [r9+90h]
0x1800480ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480f4  mov     ebx, eax
0x1800480f6  test    eax, eax
0x1800480f8  js      loc_180048197
0x1800480fe  mov     rcx, [rbp+arg_18]
0x180048102  test    rcx, rcx
0x180048105  jz      loc_180047F3F
0x18004810b  mov     r8, [rsi+8]
0x18004810f  mov     r10d, 20000h
0x180048115  mov     rdx, [rdi+8]
0x180048119  test    [rsi+4], r10d
0x18004811d  mov     r9, [rcx]
0x180048120  lea     rax, [r8+4]
0x180048124  cmovz   r8, rax
0x180048128  test    [rdi+4], r10d
0x18004812c  lea     rax, [rdx+4]
0x180048130  cmovz   rdx, rax
0x180048134  mov     rax, [r9+90h]
0x18004813b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048140  mov     ebx, eax
0x180048142  test    ebx, ebx
0x180048144  jns     loc_180047F3F
0x18004814a  test    ebx, ebx
0x18004814c  js      short loc_180048197
0x18004814e  mov     rcx, [rbp+var_50]
0x180048152  mov     rdx, [rbp+var_48]
0x180048156  mov     rax, [rcx]
0x180048159  mov     rax, [rax+68h]
0x18004815d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048162  mov     ebx, eax
0x180048164  test    eax, eax
0x180048166  js      short loc_180048197
0x180048168  mov     rdx, [rbp+arg_18]
  ... truncated ...
```
