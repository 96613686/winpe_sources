# SyncKnowledge::Complement(ISyncKnowledge *,ISyncKnowledge * *)

- ea: `0x1800844f0`
- end: `0x1800846ce`
- name: `?Complement@SyncKnowledge@@UEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z`
- size: `478`
- prototype: `__int64 __fastcall(SyncKnowledge *__hidden this, struct ISyncKnowledge *, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180005e8c`
- `0x180006f8c`
- `0x180007584`
- `0x1800093e4`
- `0x18000a0f0`
- `0x18000a18c`
- `0x18000c9f0`
- `0x18000d6e0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001dea0`
- `0x1800844f0`
- `0x180094010`

## string_xrefs

- `0x18008452f`: `SyncKnowledge::Complement`
- `0x18008468d`: `SyncKnowledge::Complement`

## pseudocode

```c
__int64 __fastcall SyncKnowledge::Complement(
        SyncKnowledge *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge **a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // eax
  SyncKnowledge *v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  int v13; // ecx
  __int64 v15[2]; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF
  __int64 v17; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      "SyncKnowledge::Complement");
  }
  if ( !a2 || !a3 )
  {
    v6 = -2147467261;
    goto LABEL_17;
  }
  if ( (*((_BYTE *)this + 176) & 1) == 0 )
  {
    v6 = -2147217379;
LABEL_17:
    v16 = -1;
    v17 = 0;
    goto LABEL_18;
  }
  v7 = SyncKnowledge::ValidateIdParameters(this, a2);
  v8 = 0;
  v6 = v7;
  v17 = 0;
  if ( !v7 )
  {
    v9 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_ISyncKnowledge2,
           &v17);
    v8 = v17;
    v6 = v9;
  }
  v16 = -1;
  if ( !v6 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 256LL))(v8, &v16);
    if ( !v6 && v16 > 5 )
      v6 = -2147217387;
  }
LABEL_18:
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( !v6 )
  {
    v10 = (SyncKnowledge *)SeAlloc(0x2F8u);
    if ( v10 )
      v10 = SyncKnowledge::SyncKnowledge(v10);
    v6 = ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach(v15, (__int64)v10);
    if ( !v6 )
    {
      v11 = v15[0];
      v6 = CoreKnowledge::InitializeByMergingWithExternalInstance((CoreKnowledge *)(v15[0] + 48));
      if ( !v6 )
      {
        v6 = MarkerManager::InitializeByCloning((MarkerManager *)(v11 + 288), (SyncKnowledge *)((char *)this + 288));
        if ( !v6 )
        {
          v12 = *((_DWORD *)this + 180);
          v13 = v16;
          v15[0] = 0;
          if ( v12 > v16 )
            v13 = v12;
          *(_DWORD *)(v11 + 720) = v13;
          *a3 = (struct ISyncKnowledge *)v11;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      (unsigned int)"SyncKnowledge::Complement",
      v6);
  }
  SharedRefPtr<KnowledgeCookie>::~SharedRefPtr<KnowledgeCookie>(v15);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
  return v6;
}

```

## disassembly

```asm
0x1800844f0  mov     [rsp-28h+arg_0], rbx
0x1800844f5  push    rbp
0x1800844f6  push    rsi
0x1800844f7  push    rdi
0x1800844f8  push    r12
0x1800844fa  push    r14
0x1800844fc  mov     rbp, rsp
0x1800844ff  sub     rsp, 40h
0x180084503  mov     r14, r8
0x180084506  mov     rdi, rdx
0x180084509  mov     rsi, rcx
0x18008450c  mov     rcx, cs:WPP_GLOBAL_Control
0x180084513  lea     r12, WPP_GLOBAL_Control
0x18008451a  cmp     rcx, r12
0x18008451d  jz      short loc_180084547
0x18008451f  test    byte ptr [rcx+1Ch], 40h
0x180084523  jz      short loc_180084547
0x180084525  cmp     byte ptr [rcx+19h], 5
0x180084529  jb      short loc_180084547
0x18008452b  mov     rcx, [rcx+10h]
0x18008452f  lea     r9, aSyncknowledgeC_5; "SyncKnowledge::Complement"
0x180084536  mov     edx, 22h ; '"'
0x18008453b  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x180084542  call    WPP_SF_s
0x180084547  test    rdi, rdi
0x18008454a  jz      short loc_1800845C9
0x18008454c  test    r14, r14
0x18008454f  jz      short loc_1800845C9
0x180084551  test    byte ptr [rsi+0B0h], 1
0x180084558  jnz     short loc_180084561
0x18008455a  mov     ebx, 8004101Dh
0x18008455f  jmp     short loc_1800845CE
0x180084561  mov     rdx, rdi; struct ISyncKnowledge *
0x180084564  mov     rcx, rsi; this
0x180084567  call    ?ValidateIdParameters@SyncKnowledge@@AEBAJPEAUISyncKnowledge@@@Z; SyncKnowledge::ValidateIdParameters(ISyncKnowledge *)
0x18008456c  xor     ecx, ecx
0x18008456e  mov     ebx, eax
0x180084570  mov     [rbp+arg_18], rcx
0x180084574  test    eax, eax
0x180084576  jnz     short loc_180084597
0x180084578  mov     rax, [rdi]
0x18008457b  lea     r8, [rbp+arg_18]
0x18008457f  lea     rdx, IID_ISyncKnowledge2
0x180084586  mov     rcx, rdi
0x180084589  mov     rax, [rax]
0x18008458c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084591  mov     rcx, [rbp+arg_18]
0x180084595  mov     ebx, eax
0x180084597  mov     [rbp+arg_8], 0FFFFFFFFh
0x18008459e  test    ebx, ebx
0x1800845a0  jnz     short loc_1800845DD
0x1800845a2  mov     rax, [rcx]
0x1800845a5  lea     rdx, [rbp+arg_8]
0x1800845a9  mov     rax, [rax+100h]
0x1800845b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845b5  mov     ebx, eax
0x1800845b7  test    eax, eax
0x1800845b9  jnz     short loc_1800845DD
0x1800845bb  cmp     [rbp+arg_8], 5
0x1800845bf  mov     eax, 80041015h
0x1800845c4  cmovg   ebx, eax
0x1800845c7  jmp     short loc_1800845DD
0x1800845c9  mov     ebx, 80004003h
0x1800845ce  mov     [rbp+arg_8], 0FFFFFFFFh
0x1800845d5  mov     [rbp+arg_18], 0
0x1800845dd  lea     rcx, [rbp+var_10]
0x1800845e1  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x1800845e6  test    ebx, ebx
0x1800845e8  jnz     loc_180084671
0x1800845ee  mov     ecx, 2F8h; unsigned __int64
0x1800845f3  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800845f8  test    rax, rax
0x1800845fb  jz      short loc_180084605
0x1800845fd  mov     rcx, rax; this
0x180084600  call    ??0SyncKnowledge@@QEAA@XZ; SyncKnowledge::SyncKnowledge(void)
0x180084605  mov     rdx, rax
0x180084608  lea     rcx, [rbp+var_10]
0x18008460c  call    ?Attach@?$ScopedPtrBase@VSyncKnowledge@@V?$ScopedRefPtr@VSyncKnowledge@@@@@@QEAAJPEAVSyncKnowledge@@@Z; ScopedPtrBase<SyncKnowledge,ScopedRefPtr<SyncKnowledge>>::Attach(SyncKnowledge *)
0x180084611  mov     ebx, eax
0x180084613  test    eax, eax
0x180084615  jnz     short loc_180084671
0x180084617  mov     rdi, [rbp+var_10]
0x18008461b  lea     rdx, [rsi+30h]
0x18008461f  lea     r9, ?Complement@ClockVector@@SAJAEBV1@0AEAV1@@Z; ClockVector::Complement(ClockVector const &,ClockVector const &,ClockVector &)
0x180084626  lea     r8, [rbp+arg_18]
0x18008462a  lea     rcx, [rdi+30h]; this
0x18008462e  call    ?InitializeByMergingWithExternalInstance@CoreKnowledge@@QEAAJAEAV1@AEAV?$SharedRefPtr@UISyncKnowledge2@@@@P6AJAEBVClockVector@@2AEAV3@@Z@Z; CoreKnowledge::InitializeByMergingWithExternalInstance(CoreKnowledge &,SharedRefPtr<ISyncKnowledge2> &,long (*)(ClockVector const &,ClockVector const &,ClockVector &))
0x180084633  mov     ebx, eax
0x180084635  test    eax, eax
0x180084637  jnz     short loc_180084671
0x180084639  lea     rdx, [rsi+120h]; struct MarkerManager *
0x180084640  lea     rcx, [rdi+120h]; this
0x180084647  call    ?InitializeByCloning@MarkerManager@@QEAAJAEBV1@@Z; MarkerManager::InitializeByCloning(MarkerManager const &)
0x18008464c  mov     ebx, eax
0x18008464e  test    eax, eax
0x180084650  jnz     short loc_180084671
0x180084652  mov     eax, [rsi+2D0h]
0x180084658  mov     ecx, [rbp+arg_8]
0x18008465b  cmp     eax, ecx
0x18008465d  mov     [rbp+var_10], 0
0x180084665  cmovg   ecx, eax
0x180084668  mov     [rdi+2D0h], ecx
0x18008466e  mov     [r14], rdi
0x180084671  mov     rcx, cs:WPP_GLOBAL_Control
0x180084678  cmp     rcx, r12
0x18008467b  jz      short loc_1800846A9
0x18008467d  test    byte ptr [rcx+1Ch], 40h
0x180084681  jz      short loc_1800846A9
0x180084683  cmp     byte ptr [rcx+19h], 5
0x180084687  jb      short loc_1800846A9
0x180084689  mov     rcx, [rcx+10h]
0x18008468d  lea     r9, aSyncknowledgeC_5; "SyncKnowledge::Complement"
0x180084694  mov     edx, 23h ; '#'
0x180084699  mov     [rsp+40h+var_20], ebx
0x18008469d  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x1800846a4  call    WPP_SF_sD
0x1800846a9  lea     rcx, [rbp+var_10]
0x1800846ad  call    ??1?$SharedRefPtr@VKnowledgeCookie@@@@QEAA@XZ; SharedRefPtr<KnowledgeCookie>::~SharedRefPtr<KnowledgeCookie>(void)
0x1800846b2  lea     rcx, [rbp+arg_18]
0x1800846b6  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800846bb  mov     eax, ebx
0x1800846bd  mov     rbx, [rsp+40h+arg_0]
0x1800846c2  add     rsp, 40h
0x1800846c6  pop     r14
0x1800846c8  pop     r12
0x1800846ca  pop     rdi
0x1800846cb  pop     rsi
0x1800846cc  pop     rbp
0x1800846cd  retn
```
