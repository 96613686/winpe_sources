# ChangeApplicationServices::BeginFullEnumerationChangeApplication(ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,ISyncCallback *,IUnknown *,IUnknown *)

- ea: `0x180047530`
- end: `0x1800477e7`
- name: `?BeginFullEnumerationChangeApplication@ChangeApplicationServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@01PEAUISyncFilterInfo@@PEAUISyncCallback@@PEAUIUnknown@@4@Z`
- size: `695`
- prototype: `__int64 __fastcall(ChangeApplicationServices *this, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncFilterInfo *, struct ISyncCallback *, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180005f20`
- `0x180007584`
- `0x18001a038`
- `0x18001ae20`
- `0x180047300`
- `0x180047530`
- `0x1800477f0`
- `0x180048940`
- `0x18004a8fc`
- `0x180094010`

## string_xrefs

- `0x18004757d`: `ChangeApplicationServices::BeginFullEnumerationChangeApplication`
- `0x1800477a7`: `ChangeApplicationServices::BeginFullEnumerationChangeApplication`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::BeginFullEnumerationChangeApplication(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge *a3,
        struct ISyncKnowledge *a4,
        struct ISyncKnowledge *a5,
        struct ISyncFilterInfo *a6,
        struct ISyncCallback *a7,
        struct IUnknown *a8,
        struct IUnknown *a9)
{
  ChangeApplicationServices *v13; // rcx
  ChangeApplicationServices *v14; // rcx
  int v15; // ebx
  ChangeApplicationServices *v16; // rcx
  ChangeApplicationServices *v17; // rcx
  int v18; // eax
  int Interface; // eax
  int v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23[2]; // [rsp+40h] [rbp-10h] BYREF

  v13 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::BeginFullEnumerationChangeApplication");
    v13 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  if ( !a2 || !a3 || !a4 || !a5 || !a8 || !a9 )
  {
    v15 = -2147467261;
    v23[0] = 0;
    goto LABEL_32;
  }
  v15 = ChangeApplicationServices::ValidateIdParameters(v13, (ChangeApplicationServices *)((char *)this + 40), a2);
  if ( v15 >= 0 )
  {
    v15 = ChangeApplicationServices::ValidateIdParameters(v14, (ChangeApplicationServices *)((char *)this + 40), a3);
    if ( v15 >= 0 )
    {
      v15 = ChangeApplicationServices::ValidateIdParameters(v16, (ChangeApplicationServices *)((char *)this + 40), a4);
      if ( v15 >= 0 )
      {
        v15 = ChangeApplicationServices::ValidateIdParameters(v17, (ChangeApplicationServices *)((char *)this + 40), a5);
        if ( v15 >= 0 )
        {
          if ( !a6 )
            goto LABEL_23;
          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          v18 = ((__int64 (__fastcall *)(struct ISyncFilterInfo *, GUID *, __int64 *))a6->lpVtbl->QueryInterface)(
                  a6,
                  &GUID_19b394ba_e3d0_468c_934d_321968b2ab34,
                  &v22);
          v21 = 0;
          v15 = v18;
          if ( v18 >= 0 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 32LL))(v22, &v21);
            if ( v15 >= 0 && (v21 & 1) != 0 )
              v15 = -2147217369;
          }
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v22);
          if ( v15 >= 0 )
LABEL_23:
            v15 = ChangeApplicationServices::ChangeState(this, 3);
        }
      }
    }
  }
  v23[0] = 0;
  if ( v15 >= 0 )
  {
    if ( !a7 )
    {
LABEL_29:
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 80, a2);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 88, a3);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 96, a4);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 104, a5);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 136, a6);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 144, a7);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 160, a8);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 168, a9);
      SharedRefPtr<IClockVector>::operator=((__int64 *)this + 19, v23);
      goto LABEL_30;
    }
    Interface = SharedRefPtr<ISyncCallback2>::QueryInterface(v23, a7);
    v15 = Interface;
    if ( Interface == -2147467262 )
    {
      v15 = 0;
      goto LABEL_29;
    }
    if ( Interface >= 0 )
      goto LABEL_29;
  }
LABEL_30:
  v13 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
LABEL_32:
  if ( v13 != (ChangeApplicationServices *)&WPP_GLOBAL_Control && *((char *)v13 + 28) < 0 && *((_BYTE *)v13 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v13 + 2),
      17,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::BeginFullEnumerationChangeApplication",
      v15);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(v23);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180047530  mov     [rsp-28h+arg_0], rbx
0x180047535  mov     [rsp-28h+arg_10], rsi
0x18004753a  mov     [rsp-28h+arg_8], rdx
0x18004753f  push    rbp
0x180047540  push    rdi
0x180047541  push    r12
0x180047543  push    r13
0x180047545  push    r14
0x180047547  mov     rbp, rsp
0x18004754a  sub     rsp, 50h
0x18004754e  mov     r12, r9
0x180047551  mov     r13, r8
0x180047554  mov     rbx, rdx
0x180047557  mov     rsi, rcx
0x18004755a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047561  lea     rax, WPP_GLOBAL_Control
0x180047568  cmp     rcx, rax
0x18004756b  jz      short loc_18004759C
0x18004756d  test    byte ptr [rcx+1Ch], 80h
0x180047571  jz      short loc_18004759C
0x180047573  cmp     byte ptr [rcx+19h], 5
0x180047577  jb      short loc_18004759C
0x180047579  mov     rcx, [rcx+10h]
0x18004757d  lea     r9, aChangeapplicat_49; "ChangeApplicationServices::BeginFullEnu"...
0x180047584  mov     edx, 10h
0x180047589  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047590  call    WPP_SF_s
0x180047595  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004759c  xor     eax, eax
0x18004759e  test    rbx, rbx
0x1800475a1  jz      loc_180047782
0x1800475a7  test    r13, r13
0x1800475aa  jz      loc_180047782
0x1800475b0  test    r12, r12
0x1800475b3  jz      loc_180047782
0x1800475b9  cmp     [rbp+arg_20], rax
0x1800475bd  jz      loc_180047782
0x1800475c3  cmp     [rbp+arg_38], rax
0x1800475c7  jz      loc_180047782
0x1800475cd  cmp     [rbp+arg_40], rax
0x1800475d1  jz      loc_180047782
0x1800475d7  lea     rdi, [rsi+28h]
0x1800475db  mov     r8, rbx; struct ISyncKnowledge *
0x1800475de  mov     rdx, rdi; struct IdDescription *
0x1800475e1  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800475e6  mov     r14, [rbp+arg_28]
0x1800475ea  mov     ebx, eax
0x1800475ec  test    eax, eax
0x1800475ee  js      loc_1800476BF
0x1800475f4  mov     r8, r13; struct ISyncKnowledge *
0x1800475f7  mov     rdx, rdi; struct IdDescription *
0x1800475fa  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800475ff  mov     ebx, eax
0x180047601  test    eax, eax
0x180047603  js      loc_1800476BF
0x180047609  mov     r8, r12; struct ISyncKnowledge *
0x18004760c  mov     rdx, rdi; struct IdDescription *
0x18004760f  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180047614  mov     ebx, eax
0x180047616  test    eax, eax
0x180047618  js      loc_1800476BF
0x18004761e  mov     r8, [rbp+arg_20]; struct ISyncKnowledge *
0x180047622  mov     rdx, rdi; struct IdDescription *
0x180047625  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x18004762a  mov     ebx, eax
0x18004762c  test    eax, eax
0x18004762e  js      loc_1800476BF
0x180047634  test    r14, r14
0x180047637  jz      short loc_1800476B0
0x180047639  lea     rcx, [rbp+var_18]
0x18004763d  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180047642  mov     rcx, [rbp+var_18]
0x180047646  test    rcx, rcx
0x180047649  jz      short loc_180047657
0x18004764b  mov     rax, [rcx]
0x18004764e  mov     rax, [rax+10h]
0x180047652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047657  mov     rax, [r14]
0x18004765a  lea     r8, [rbp+var_18]
0x18004765e  lea     rdx, _GUID_19b394ba_e3d0_468c_934d_321968b2ab34
0x180047665  mov     rcx, r14
0x180047668  mov     rax, [rax]
0x18004766b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047670  mov     [rbp+var_20], 0
0x180047677  mov     ebx, eax
0x180047679  test    eax, eax
0x18004767b  js      short loc_1800476A3
0x18004767d  mov     rcx, [rbp+var_18]
0x180047681  lea     rdx, [rbp+var_20]
0x180047685  mov     rax, [rcx]
0x180047688  mov     rax, [rax+20h]
0x18004768c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047691  mov     ebx, eax
0x180047693  test    eax, eax
0x180047695  js      short loc_1800476A3
0x180047697  test    byte ptr [rbp+var_20], 1
0x18004769b  mov     eax, 80041027h
0x1800476a0  cmovnz  ebx, eax
0x1800476a3  lea     rcx, [rbp+var_18]
0x1800476a7  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800476ac  test    ebx, ebx
0x1800476ae  js      short loc_1800476BF
0x1800476b0  mov     edx, 3
0x1800476b5  mov     rcx, rsi
0x1800476b8  call    ?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z; ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)
0x1800476bd  mov     ebx, eax
0x1800476bf  mov     [rbp+var_10], 0
0x1800476c7  test    ebx, ebx
0x1800476c9  js      loc_180047779
0x1800476cf  mov     rdi, [rbp+arg_30]
0x1800476d3  test    rdi, rdi
0x1800476d6  jz      short loc_1800476F9
0x1800476d8  mov     rdx, rdi
0x1800476db  lea     rcx, [rbp+var_10]
0x1800476df  call    ?QueryInterface@?$SharedRefPtr@UISyncCallback2@@@@QEAAJPEAUIUnknown@@@Z; SharedRefPtr<ISyncCallback2>::QueryInterface(IUnknown *)
0x1800476e4  mov     ebx, eax
0x1800476e6  cmp     eax, 80004002h
0x1800476eb  jnz     short loc_1800476F1
0x1800476ed  xor     ebx, ebx
0x1800476ef  jmp     short loc_1800476F9
0x1800476f1  test    eax, eax
0x1800476f3  js      loc_180047779
0x1800476f9  mov     rdx, [rbp+arg_8]
0x1800476fd  lea     rcx, [rsi+50h]
0x180047701  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047706  lea     rcx, [rsi+58h]
0x18004770a  mov     rdx, r13
0x18004770d  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047712  lea     rcx, [rsi+60h]
0x180047716  mov     rdx, r12
0x180047719  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004771e  mov     rdx, [rbp+arg_20]
0x180047722  lea     rcx, [rsi+68h]
0x180047726  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004772b  lea     rcx, [rsi+88h]
0x180047732  mov     rdx, r14
0x180047735  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004773a  lea     rcx, [rsi+90h]
0x180047741  mov     rdx, rdi
0x180047744  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047749  mov     rdx, [rbp+arg_38]
0x18004774d  lea     rcx, [rsi+0A0h]
0x180047754  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047759  mov     rdx, [rbp+arg_40]
0x18004775d  lea     rcx, [rsi+0A8h]
0x180047764  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047769  lea     rcx, [rsi+98h]
0x180047770  lea     rdx, [rbp+var_10]
0x180047774  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180047779  mov     rcx, cs:WPP_GLOBAL_Control
0x180047780  jmp     short loc_18004778B
0x180047782  mov     ebx, 80004003h
0x180047787  mov     [rbp+var_10], rax
0x18004778b  lea     rax, WPP_GLOBAL_Control
0x180047792  cmp     rcx, rax
0x180047795  jz      short loc_1800477C3
0x180047797  test    byte ptr [rcx+1Ch], 80h
0x18004779b  jz      short loc_1800477C3
0x18004779d  cmp     byte ptr [rcx+19h], 5
0x1800477a1  jb      short loc_1800477C3
0x1800477a3  mov     rcx, [rcx+10h]
0x1800477a7  lea     r9, aChangeapplicat_49; "ChangeApplicationServices::BeginFullEnu"...
0x1800477ae  mov     edx, 11h
0x1800477b3  mov     [rsp+50h+var_30], ebx
0x1800477b7  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800477be  call    WPP_SF_sD
0x1800477c3  lea     rcx, [rbp+var_10]
0x1800477c7  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800477cc  lea     r11, [rsp+50h+var_s0]
0x1800477d1  mov     eax, ebx
0x1800477d3  mov     rbx, [r11+30h]
0x1800477d7  mov     rsi, [r11+40h]
0x1800477db  mov     rsp, r11
0x1800477de  pop     r14
0x1800477e0  pop     r13
0x1800477e2  pop     r12
0x1800477e4  pop     rdi
0x1800477e5  pop     rbp
0x1800477e6  retn
```
