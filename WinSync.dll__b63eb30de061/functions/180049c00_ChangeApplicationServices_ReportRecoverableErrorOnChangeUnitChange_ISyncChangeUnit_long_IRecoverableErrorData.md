# ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange(ISyncChangeUnit *,long,IRecoverableErrorData *)

- ea: `0x180049c00`
- end: `0x180049d7a`
- name: `?ReportRecoverableErrorOnChangeUnitChange@ChangeApplicationServices@@UEAAJPEAUISyncChangeUnit@@JPEAUIRecoverableErrorData@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChangeUnit *, int, struct IRecoverableErrorData *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x18001a038`
- `0x18001ae20`
- `0x180049c00`
- `0x18004a8fc`
- `0x180094010`

## string_xrefs

- `0x180049c3c`: `ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange`
- `0x180049d42`: `ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange(
        ChangeApplicationServices *this,
        struct ISyncChangeUnit *a2,
        unsigned int a3,
        struct IRecoverableErrorData *a4)
{
  PVOID *v8; // rcx
  int v9; // ebx
  ChangeApplicationServices *v10; // rcx
  struct ISyncKnowledge *v12[9]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v13; // [rsp+98h] [rbp+10h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = 0;
  if ( a2 )
  {
    if ( (unsigned int)(*((_DWORD *)this + 9) - 2) <= 1 )
    {
      v9 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, __int64 *))a2->lpVtbl->GetItemChange)(a2, &v13);
      if ( v9 >= 0 )
      {
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v13 + 80LL))(v13, v12);
        if ( v9 >= 0 )
        {
          if ( v12[0] )
            v9 = ChangeApplicationServices::ValidateIdParameters(
                   v10,
                   (ChangeApplicationServices *)((char *)this + 40),
                   v12[0]);
          else
            v9 = -2147217399;
        }
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)v12);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(char *, struct ISyncChangeUnit *, _QWORD, struct IRecoverableErrorData *, int, int))(*((_QWORD *)this + 1) + 32LL))(
                 (char *)this + 8,
                 a2,
                 a3,
                 a4,
                 1,
                 2);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v9 = -2147217407;
    }
  }
  else
  {
    v9 = -2147467261;
  }
  if ( v8 != &WPP_GLOBAL_Control && *((char *)v8 + 28) < 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      35,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange",
      v9);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180049c00  push    rbx
0x180049c02  push    rbp
0x180049c03  push    rsi
0x180049c04  push    rdi
0x180049c05  push    r12
0x180049c07  push    r14
0x180049c09  sub     rsp, 58h
0x180049c0d  mov     rbp, r9
0x180049c10  mov     r14d, r8d
0x180049c13  mov     rdi, rdx
0x180049c16  mov     rsi, rcx
0x180049c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c20  lea     r12, WPP_GLOBAL_Control
0x180049c27  cmp     rcx, r12
0x180049c2a  jz      short loc_180049C5B
0x180049c2c  test    byte ptr [rcx+1Ch], 80h
0x180049c30  jz      short loc_180049C5B
0x180049c32  cmp     byte ptr [rcx+19h], 5
0x180049c36  jb      short loc_180049C5B
0x180049c38  mov     rcx, [rcx+10h]
0x180049c3c  lea     r9, aChangeapplicat_47; "ChangeApplicationServices::ReportRecove"...
0x180049c43  mov     edx, 22h ; '"'
0x180049c48  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049c4f  call    WPP_SF_s
0x180049c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c5b  mov     [rsp+88h+arg_8], 0
0x180049c67  test    rdi, rdi
0x180049c6a  jnz     short loc_180049C76
0x180049c6c  mov     ebx, 80004003h
0x180049c71  jmp     loc_180049D2D
0x180049c76  mov     eax, [rsi+24h]
0x180049c79  sub     eax, 2
0x180049c7c  cmp     eax, 1
0x180049c7f  jbe     short loc_180049C8B
0x180049c81  mov     ebx, 80041001h
0x180049c86  jmp     loc_180049D2D
0x180049c8b  mov     rax, [rdi]
0x180049c8e  lea     rdx, [rsp+88h+arg_8]
0x180049c96  mov     rcx, rdi
0x180049c99  mov     rax, [rax+18h]
0x180049c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ca2  mov     ebx, eax
0x180049ca4  test    eax, eax
0x180049ca6  js      short loc_180049D26
0x180049ca8  lea     rcx, [rsp+88h+var_48]
0x180049cad  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180049cb2  mov     rcx, [rsp+88h+arg_8]
0x180049cba  lea     rdx, [rsp+88h+var_48]
0x180049cbf  mov     rax, [rcx]
0x180049cc2  mov     rax, [rax+50h]
0x180049cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ccb  mov     ebx, eax
0x180049ccd  test    eax, eax
0x180049ccf  js      short loc_180049CED
0x180049cd1  mov     r8, [rsp+88h+var_48]; struct ISyncKnowledge *
0x180049cd6  test    r8, r8
0x180049cd9  jnz     short loc_180049CE2
0x180049cdb  mov     ebx, 80041009h
0x180049ce0  jmp     short loc_180049CED
0x180049ce2  lea     rdx, [rsi+28h]; struct IdDescription *
0x180049ce6  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180049ceb  mov     ebx, eax
0x180049ced  lea     rcx, [rsp+88h+var_48]
0x180049cf2  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049cf7  test    ebx, ebx
0x180049cf9  js      short loc_180049D26
0x180049cfb  lea     rcx, [rsi+8]
0x180049cff  mov     [rsp+88h+var_60], 2
0x180049d07  mov     rax, [rcx]
0x180049d0a  mov     r9, rbp
0x180049d0d  mov     r8d, r14d
0x180049d10  mov     [rsp+88h+var_68], 1
0x180049d18  mov     rdx, rdi
0x180049d1b  mov     rax, [rax+20h]
0x180049d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d24  mov     ebx, eax
0x180049d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d2d  cmp     rcx, r12
0x180049d30  jz      short loc_180049D5E
0x180049d32  test    byte ptr [rcx+1Ch], 80h
0x180049d36  jz      short loc_180049D5E
0x180049d38  cmp     byte ptr [rcx+19h], 5
0x180049d3c  jb      short loc_180049D5E
0x180049d3e  mov     rcx, [rcx+10h]
0x180049d42  lea     r9, aChangeapplicat_47; "ChangeApplicationServices::ReportRecove"...
0x180049d49  mov     edx, 23h ; '#'
0x180049d4e  mov     [rsp+88h+var_68], ebx
0x180049d52  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049d59  call    WPP_SF_sD
0x180049d5e  lea     rcx, [rsp+88h+arg_8]
0x180049d66  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049d6b  mov     eax, ebx
0x180049d6d  add     rsp, 58h
0x180049d71  pop     r14
0x180049d73  pop     r12
0x180049d75  pop     rdi
0x180049d76  pop     rsi
0x180049d77  pop     rbp
0x180049d78  pop     rbx
0x180049d79  retn
```
