# ChangeApplicationContext::CreateItemLevelChangeConflict(ChangeConflictType)

- ea: `0x1800752b4`
- end: `0x180075495`
- name: `?CreateItemLevelChangeConflict@ChangeApplicationContext@@AEAAJW4ChangeConflictType@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18007549c`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001df64`
- `0x1800752b4`
- `0x18007ac30`
- `0x18007c190`
- `0x18007c32c`
- `0x18007c6a8`
- `0x18007e17c`
- `0x18007f028`

## string_xrefs

- `0x1800752ea`: `ChangeApplicationContext::CreateItemLevelChangeConflict`
- `0x18007545d`: `ChangeApplicationContext::CreateItemLevelChangeConflict`

## pseudocode

```c
__int64 __fastcall ChangeApplicationContext::CreateItemLevelChangeConflict(__int64 *a1, int a2)
{
  void *v4; // rax
  int v5; // ebx
  struct ISyncChange *v6; // rcx
  int v7; // eax
  void *v8; // rax
  void *v9; // rax
  struct ISyncChange *v11; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids,
      "ChangeApplicationContext::CreateItemLevelChangeConflict");
  }
  v4 = SeAlloc(0x118u);
  if ( v4 )
    v4 = (void *)ItemChangeWrapper::ItemChangeWrapper(v4, (char *)a1 + 36, a1 + 18);
  v5 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(a1 + 23, (__int64)v4);
  if ( v5 >= 0 )
  {
    v6 = (struct ISyncChange *)a1[23];
    if ( a1[10] )
      v7 = ItemChangeWrapper::InitializeFromExternalSourceChange(v6);
    else
      v7 = ItemChangeWrapper::InitializeForgottenDelete(v6, a1 + 14, a1 + 15, a1 + 11);
    v5 = v7;
  }
  v11 = 0;
  if ( v5 >= 0 )
  {
    v8 = SeAlloc(0x118u);
    if ( v8 )
      v8 = (void *)ItemChangeWrapper::ItemChangeWrapper(v8, (char *)a1 + 36, a1 + 18);
    v5 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach((__int64 *)&v11, (__int64)v8);
    if ( v5 >= 0 )
    {
      v5 = ItemChangeWrapper::InitializeFromExternalDestinationVersion(v11);
      if ( v5 >= 0 )
      {
        v9 = SeAlloc(0x90u);
        if ( v9 )
          v9 = (void *)ChangeConflict::ChangeConflict(
                         (__int64)v9,
                         (__int64)a1 + 36,
                         a1 + 9,
                         a1 + 23,
                         (__int64 *)&v11,
                         a1 + 20,
                         a1 + 21,
                         a2);
        v5 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(a1 + 24, (__int64)v9);
        if ( v5 >= 0 )
          v5 = ChangeConflict::Initialize((ChangeConflict *)a1[24]);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids,
      (unsigned int)"ChangeApplicationContext::CreateItemLevelChangeConflict",
      v5);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800752b4  push    rbx
0x1800752b6  push    rbp
0x1800752b7  push    rsi
0x1800752b8  push    rdi
0x1800752b9  push    r12
0x1800752bb  push    r14
0x1800752bd  sub     rsp, 48h
0x1800752c1  mov     r14d, edx
0x1800752c4  mov     rdi, rcx
0x1800752c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800752ce  lea     r12, WPP_GLOBAL_Control
0x1800752d5  cmp     rcx, r12
0x1800752d8  jz      short loc_180075302
0x1800752da  test    byte ptr [rcx+1Ch], 80h
0x1800752de  jz      short loc_180075302
0x1800752e0  cmp     byte ptr [rcx+19h], 5
0x1800752e4  jb      short loc_180075302
0x1800752e6  mov     rcx, [rcx+10h]
0x1800752ea  lea     r9, aChangeapplicat_29; "ChangeApplicationContext::CreateItemLev"...
0x1800752f1  mov     edx, 36h ; '6'
0x1800752f6  lea     r8, WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids
0x1800752fd  call    WPP_SF_s
0x180075302  mov     ecx, 118h; unsigned __int64
0x180075307  lea     rsi, [rdi+0B8h]
0x18007530e  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180075313  lea     rbp, [rdi+24h]
0x180075317  test    rax, rax
0x18007531a  jz      short loc_18007532E
0x18007531c  lea     r8, [rdi+90h]
0x180075323  mov     rdx, rbp
0x180075326  mov     rcx, rax
0x180075329  call    ??0ItemChangeWrapper@@QEAA@AEBUIdDescription@@AEBV?$SharedRefPtr@UISyncFilterInfo@@@@@Z; ItemChangeWrapper::ItemChangeWrapper(IdDescription const &,SharedRefPtr<ISyncFilterInfo> const &)
0x18007532e  mov     rdx, rax
0x180075331  mov     rcx, rsi
0x180075334  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x180075339  mov     ebx, eax
0x18007533b  test    eax, eax
0x18007533d  js      short loc_18007536D
0x18007533f  mov     rcx, [rsi]; struct ISyncChange *
0x180075342  lea     rdx, [rdi+50h]
0x180075346  cmp     qword ptr [rdx], 0
0x18007534a  jnz     short loc_18007535F
0x18007534c  lea     r9, [rdi+58h]
0x180075350  lea     r8, [rdi+78h]
0x180075354  lea     rdx, [rdi+70h]
0x180075358  call    ?InitializeForgottenDelete@ItemChangeWrapper@@QEAAJAEBV?$SharedRefPtr@UISyncKnowledge@@@@AEBV?$SharedRefPtr@UIForgottenKnowledge@@@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeWrapper::InitializeForgottenDelete(SharedRefPtr<ISyncKnowledge> const &,SharedRefPtr<IForgottenKnowledge> const &,SharedRefPtr<ISyncChange> const &)
0x18007535d  jmp     short loc_18007536B
0x18007535f  lea     r8, [rdi+80h]
0x180075366  call    ?InitializeFromExternalSourceChange@ItemChangeWrapper@@QEAAJAEAV?$SharedRefPtr@UISyncChange@@@@AEAV?$SharedRefPtr@UISyncKnowledge@@@@@Z; ItemChangeWrapper::InitializeFromExternalSourceChange(SharedRefPtr<ISyncChange> &,SharedRefPtr<ISyncKnowledge> &)
0x18007536b  mov     ebx, eax
0x18007536d  mov     [rsp+78h+arg_0], 0
0x180075379  test    ebx, ebx
0x18007537b  js      loc_180075441
0x180075381  mov     ecx, 118h; unsigned __int64
0x180075386  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18007538b  test    rax, rax
0x18007538e  jz      short loc_1800753A2
0x180075390  lea     r8, [rdi+90h]
0x180075397  mov     rdx, rbp
0x18007539a  mov     rcx, rax
0x18007539d  call    ??0ItemChangeWrapper@@QEAA@AEBUIdDescription@@AEBV?$SharedRefPtr@UISyncFilterInfo@@@@@Z; ItemChangeWrapper::ItemChangeWrapper(IdDescription const &,SharedRefPtr<ISyncFilterInfo> const &)
0x1800753a2  mov     rdx, rax
0x1800753a5  lea     rcx, [rsp+78h+arg_0]
0x1800753ad  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x1800753b2  mov     ebx, eax
0x1800753b4  test    eax, eax
0x1800753b6  js      loc_180075441
0x1800753bc  mov     rcx, [rsp+78h+arg_0]; struct ISyncChange *
0x1800753c4  lea     rdx, [rdi+58h]
0x1800753c8  call    ?InitializeFromExternalDestinationVersion@ItemChangeWrapper@@QEAAJAEAV?$SharedRefPtr@UISyncChange@@@@AEAV?$SharedRefPtr@UISyncKnowledge@@@@@Z; ItemChangeWrapper::InitializeFromExternalDestinationVersion(SharedRefPtr<ISyncChange> &,SharedRefPtr<ISyncKnowledge> &)
0x1800753cd  mov     ebx, eax
0x1800753cf  test    eax, eax
0x1800753d1  js      short loc_180075441
0x1800753d3  mov     ecx, 90h; unsigned __int64
0x1800753d8  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800753dd  test    rax, rax
0x1800753e0  jz      short loc_18007541E
0x1800753e2  mov     [rsp+78h+var_40], r14d
0x1800753e7  lea     rcx, [rdi+0A8h]
0x1800753ee  mov     [rsp+78h+var_48], rcx
0x1800753f3  lea     r9, [rdi+0A0h]
0x1800753fa  mov     [rsp+78h+var_50], r9
0x1800753ff  lea     rcx, [rsp+78h+arg_0]
0x180075407  mov     [rsp+78h+var_58], rcx
0x18007540c  lea     r8, [rdi+48h]
0x180075410  mov     rcx, rax
0x180075413  mov     r9, rsi
0x180075416  mov     rdx, rbp
0x180075419  call    ??0ChangeConflict@@QEAA@AEBUIdDescription@@AEBV?$SharedRefPtr@VIChangeApplicationServicesReports@@@@AEBV?$SharedRefPtr@VItemChangeWrapper@@@@2AEBV?$SharedRefPtr@UIUnknown@@@@3W4ChangeConflictType@@@Z; ChangeConflict::ChangeConflict(IdDescription const &,SharedRefPtr<IChangeApplicationServicesReports> const &,SharedRefPtr<ItemChangeWrapper> const &,SharedRefPtr<ItemChangeWrapper> const &,SharedRefPtr<IUnknown> const &,SharedRefPtr<IUnknown> const &,ChangeConflictType)
0x18007541e  mov     rdx, rax
0x180075421  lea     rcx, [rdi+0C0h]
0x180075428  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x18007542d  mov     ebx, eax
0x18007542f  test    eax, eax
0x180075431  js      short loc_180075441
0x180075433  mov     rcx, [rdi+0C0h]; this
0x18007543a  call    ?Initialize@ChangeConflict@@QEAAJXZ; ChangeConflict::Initialize(void)
0x18007543f  mov     ebx, eax
0x180075441  mov     rcx, cs:WPP_GLOBAL_Control
0x180075448  cmp     rcx, r12
0x18007544b  jz      short loc_180075479
0x18007544d  test    byte ptr [rcx+1Ch], 80h
0x180075451  jz      short loc_180075479
0x180075453  cmp     byte ptr [rcx+19h], 5
0x180075457  jb      short loc_180075479
0x180075459  mov     rcx, [rcx+10h]
0x18007545d  lea     r9, aChangeapplicat_29; "ChangeApplicationContext::CreateItemLev"...
0x180075464  mov     edx, 37h ; '7'
0x180075469  mov     dword ptr [rsp+78h+var_58], ebx
0x18007546d  lea     r8, WPP_ea1ebbbe88c730e42fdf891d4c557d97_Traceguids
0x180075474  call    WPP_SF_sD
0x180075479  lea     rcx, [rsp+78h+arg_0]
0x180075481  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180075486  mov     eax, ebx
0x180075488  add     rsp, 48h
0x18007548c  pop     r14
0x18007548e  pop     r12
0x180075490  pop     rdi
0x180075491  pop     rsi
0x180075492  pop     rbp
0x180075493  pop     rbx
0x180075494  retn
```
