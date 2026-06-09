# ChangeApplicationServices::BeginChangeApplication(ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,ISyncCallback *,IUnknown *,IUnknown *)

- ea: `0x180047350`
- end: `0x18004751d`
- name: `?BeginChangeApplication@ChangeApplicationServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@PEAUISyncCallback@@PEAUIUnknown@@4@Z`
- size: `461`
- prototype: `__int64 __fastcall(ChangeApplicationServices *this, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncFilterInfo *, struct ISyncCallback *, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180005f20`
- `0x18001a038`
- `0x18001ae20`
- `0x180047300`
- `0x180047350`
- `0x1800477f0`
- `0x180048940`
- `0x18004a8fc`

## string_xrefs

- `0x18004738c`: `ChangeApplicationServices::BeginChangeApplication`
- `0x1800474e8`: `ChangeApplicationServices::BeginChangeApplication`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::BeginChangeApplication(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge *a3,
        struct ISyncFilterInfo *a4,
        struct ISyncCallback *a5,
        struct IUnknown *a6,
        struct IUnknown *a7)
{
  ChangeApplicationServices *v11; // rcx
  ChangeApplicationServices *v12; // rcx
  int v13; // ebx
  struct ISyncCallback *v14; // rsi
  int v15; // eax
  __int64 v17; // [rsp+78h] [rbp+10h] BYREF

  v11 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::BeginChangeApplication");
    v11 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  if ( !a2 || !a6 || !a7 )
  {
    v13 = -2147467261;
    v17 = 0;
    goto LABEL_20;
  }
  v13 = ChangeApplicationServices::ValidateIdParameters(v11, (ChangeApplicationServices *)((char *)this + 40), a2);
  if ( v13 >= 0 )
  {
    if ( !a3
      || (v13 = ChangeApplicationServices::ValidateIdParameters(
                  v12,
                  (ChangeApplicationServices *)((char *)this + 40),
                  a3),
          v13 >= 0) )
    {
      v13 = ChangeApplicationServices::ChangeState(this, 2);
    }
  }
  v17 = 0;
  if ( v13 >= 0 )
  {
    v14 = a5;
    if ( !a5 )
    {
LABEL_17:
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 80, a2);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 88, a3);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 136, a4);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 144, v14);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 160, a6);
      SharedRefPtr<IUnknown>::AttachExternal((char *)this + 168, a7);
      SharedRefPtr<IClockVector>::operator=((__int64 *)this + 19, &v17);
      goto LABEL_18;
    }
    v15 = SharedRefPtr<ISyncCallback2>::QueryInterface(&v17, a5);
    v13 = v15;
    if ( v15 == -2147467262 )
    {
      v13 = 0;
      goto LABEL_17;
    }
    if ( v15 >= 0 )
      goto LABEL_17;
  }
LABEL_18:
  v11 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v11 != (ChangeApplicationServices *)&WPP_GLOBAL_Control && *((char *)v11 + 28) < 0 && *((_BYTE *)v11 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v11 + 2),
      15,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::BeginChangeApplication",
      v13);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v17);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180047350  push    rbx
0x180047352  push    rbp
0x180047353  push    rsi
0x180047354  push    rdi
0x180047355  push    r13
0x180047357  push    r14
0x180047359  sub     rsp, 38h
0x18004735d  mov     r13, r9
0x180047360  mov     r14, r8
0x180047363  mov     rbp, rdx
0x180047366  mov     rdi, rcx
0x180047369  mov     rcx, cs:WPP_GLOBAL_Control
0x180047370  lea     rax, WPP_GLOBAL_Control
0x180047377  cmp     rcx, rax
0x18004737a  jz      short loc_1800473AB
0x18004737c  test    byte ptr [rcx+1Ch], 80h
0x180047380  jz      short loc_1800473AB
0x180047382  cmp     byte ptr [rcx+19h], 5
0x180047386  jb      short loc_1800473AB
0x180047388  mov     rcx, [rcx+10h]
0x18004738c  lea     r9, aChangeapplicat_21; "ChangeApplicationServices::BeginChangeA"...
0x180047393  mov     edx, 0Eh
0x180047398  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004739f  call    WPP_SF_s
0x1800473a4  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800473ab  test    rbp, rbp
0x1800473ae  jz      loc_1800474BE
0x1800473b4  cmp     [rsp+68h+arg_28], 0
0x1800473bd  jz      loc_1800474BE
0x1800473c3  cmp     [rsp+68h+arg_30], 0
0x1800473cc  jz      loc_1800474BE
0x1800473d2  mov     r8, rbp; struct ISyncKnowledge *
0x1800473d5  lea     rdx, [rdi+28h]; struct IdDescription *
0x1800473d9  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800473de  mov     ebx, eax
0x1800473e0  test    eax, eax
0x1800473e2  js      short loc_18004740A
0x1800473e4  test    r14, r14
0x1800473e7  jz      short loc_1800473FB
0x1800473e9  mov     r8, r14; struct ISyncKnowledge *
0x1800473ec  lea     rdx, [rdi+28h]; struct IdDescription *
0x1800473f0  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800473f5  mov     ebx, eax
0x1800473f7  test    eax, eax
0x1800473f9  js      short loc_18004740A
0x1800473fb  mov     edx, 2
0x180047400  mov     rcx, rdi
0x180047403  call    ?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z; ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)
0x180047408  mov     ebx, eax
0x18004740a  mov     [rsp+68h+arg_8], 0
0x180047413  test    ebx, ebx
0x180047415  js      loc_1800474B5
0x18004741b  mov     rsi, [rsp+68h+arg_20]
0x180047423  test    rsi, rsi
0x180047426  jz      short loc_180047446
0x180047428  mov     rdx, rsi
0x18004742b  lea     rcx, [rsp+68h+arg_8]
0x180047430  call    ?QueryInterface@?$SharedRefPtr@UISyncCallback2@@@@QEAAJPEAUIUnknown@@@Z; SharedRefPtr<ISyncCallback2>::QueryInterface(IUnknown *)
0x180047435  mov     ebx, eax
0x180047437  cmp     eax, 80004002h
0x18004743c  jnz     short loc_180047442
0x18004743e  xor     ebx, ebx
0x180047440  jmp     short loc_180047446
0x180047442  test    eax, eax
0x180047444  js      short loc_1800474B5
0x180047446  lea     rcx, [rdi+50h]
0x18004744a  mov     rdx, rbp
0x18004744d  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047452  lea     rcx, [rdi+58h]
0x180047456  mov     rdx, r14
0x180047459  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004745e  lea     rcx, [rdi+88h]
0x180047465  mov     rdx, r13
0x180047468  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004746d  lea     rcx, [rdi+90h]
0x180047474  mov     rdx, rsi
0x180047477  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x18004747c  mov     rdx, [rsp+68h+arg_28]
0x180047484  lea     rcx, [rdi+0A0h]
0x18004748b  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x180047490  mov     rdx, [rsp+68h+arg_30]
0x180047498  lea     rcx, [rdi+0A8h]
0x18004749f  call    ?AttachExternal@?$SharedRefPtr@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; SharedRefPtr<IUnknown>::AttachExternal(IUnknown *)
0x1800474a4  lea     rcx, [rdi+98h]
0x1800474ab  lea     rdx, [rsp+68h+arg_8]
0x1800474b0  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x1800474b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474bc  jmp     short loc_1800474CC
0x1800474be  mov     ebx, 80004003h
0x1800474c3  mov     [rsp+68h+arg_8], 0
0x1800474cc  lea     rax, WPP_GLOBAL_Control
0x1800474d3  cmp     rcx, rax
0x1800474d6  jz      short loc_180047504
0x1800474d8  test    byte ptr [rcx+1Ch], 80h
0x1800474dc  jz      short loc_180047504
0x1800474de  cmp     byte ptr [rcx+19h], 5
0x1800474e2  jb      short loc_180047504
0x1800474e4  mov     rcx, [rcx+10h]
0x1800474e8  lea     r9, aChangeapplicat_21; "ChangeApplicationServices::BeginChangeA"...
0x1800474ef  mov     edx, 0Fh
0x1800474f4  mov     [rsp+68h+var_48], ebx
0x1800474f8  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800474ff  call    WPP_SF_sD
0x180047504  lea     rcx, [rsp+68h+arg_8]
0x180047509  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004750e  mov     eax, ebx
0x180047510  add     rsp, 38h
0x180047514  pop     r14
0x180047516  pop     r13
0x180047518  pop     rdi
0x180047519  pop     rsi
0x18004751a  pop     rbp
0x18004751b  pop     rbx
0x18004751c  retn
```
