# ChangeApplicationServices::ReportRecoverableErrorOnItemChange(ISyncChange *,long,IRecoverableErrorData *)

- ea: `0x18004a070`
- end: `0x18004a1bb`
- name: `?ReportRecoverableErrorOnItemChange@ChangeApplicationServices@@UEAAJPEAUISyncChange@@JPEAUIRecoverableErrorData@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChange *, int, struct IRecoverableErrorData *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x18001a038`
- `0x18001ae20`
- `0x18004a070`
- `0x18004a8fc`
- `0x180094010`

## string_xrefs

- `0x18004a0ac`: `ChangeApplicationServices::ReportRecoverableErrorOnItemChange`
- `0x18004a190`: `ChangeApplicationServices::ReportRecoverableErrorOnItemChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportRecoverableErrorOnItemChange(
        ChangeApplicationServices *this,
        struct ISyncChange *a2,
        unsigned int a3,
        struct IRecoverableErrorData *a4)
{
  PVOID *v8; // rcx
  int v9; // ebx
  ChangeApplicationServices *v10; // rcx
  struct ISyncKnowledge *v12; // [rsp+88h] [rbp+10h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportRecoverableErrorOnItemChange");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( (unsigned int)(*((_DWORD *)this + 9) - 2) <= 1 )
    {
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      v9 = ((__int64 (__fastcall *)(struct ISyncChange *, struct ISyncKnowledge **))a2->lpVtbl->GetMadeWithKnowledge)(
             a2,
             &v12);
      if ( v9 >= 0 )
      {
        if ( v12 )
          v9 = ChangeApplicationServices::ValidateIdParameters(
                 v10,
                 (ChangeApplicationServices *)((char *)this + 40),
                 v12);
        else
          v9 = -2147217399;
      }
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v12);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(char *, struct ISyncChange *, _QWORD, struct IRecoverableErrorData *, int, int))(*((_QWORD *)this + 1) + 24LL))(
               (char *)this + 8,
               a2,
               a3,
               a4,
               1,
               2);
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
      33,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportRecoverableErrorOnItemChange",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a070  push    rbx
0x18004a072  push    rbp
0x18004a073  push    rsi
0x18004a074  push    rdi
0x18004a075  push    r14
0x18004a077  push    r15
0x18004a079  sub     rsp, 48h
0x18004a07d  mov     rbp, r9
0x18004a080  mov     r14d, r8d
0x18004a083  mov     rdi, rdx
0x18004a086  mov     rsi, rcx
0x18004a089  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a090  lea     r15, WPP_GLOBAL_Control
0x18004a097  cmp     rcx, r15
0x18004a09a  jz      short loc_18004A0CB
0x18004a09c  test    byte ptr [rcx+1Ch], 80h
0x18004a0a0  jz      short loc_18004A0CB
0x18004a0a2  cmp     byte ptr [rcx+19h], 5
0x18004a0a6  jb      short loc_18004A0CB
0x18004a0a8  mov     rcx, [rcx+10h]
0x18004a0ac  lea     r9, aChangeapplicat_45; "ChangeApplicationServices::ReportRecove"...
0x18004a0b3  mov     edx, 20h ; ' '
0x18004a0b8  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a0bf  call    WPP_SF_s
0x18004a0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0cb  test    rdi, rdi
0x18004a0ce  jnz     short loc_18004A0DA
0x18004a0d0  mov     ebx, 80004003h
0x18004a0d5  jmp     loc_18004A17B
0x18004a0da  mov     eax, [rsi+24h]
0x18004a0dd  sub     eax, 2
0x18004a0e0  cmp     eax, 1
0x18004a0e3  jbe     short loc_18004A0EF
0x18004a0e5  mov     ebx, 80041001h
0x18004a0ea  jmp     loc_18004A17B
0x18004a0ef  lea     rcx, [rsp+78h+arg_8]
0x18004a0f7  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004a0fc  mov     rcx, [rdi]
0x18004a0ff  lea     rdx, [rsp+78h+arg_8]
0x18004a107  mov     rax, [rcx+50h]
0x18004a10b  mov     rcx, rdi
0x18004a10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a113  mov     ebx, eax
0x18004a115  test    eax, eax
0x18004a117  js      short loc_18004A138
0x18004a119  mov     r8, [rsp+78h+arg_8]; struct ISyncKnowledge *
0x18004a121  test    r8, r8
0x18004a124  jnz     short loc_18004A12D
0x18004a126  mov     ebx, 80041009h
0x18004a12b  jmp     short loc_18004A138
0x18004a12d  lea     rdx, [rsi+28h]; struct IdDescription *
0x18004a131  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x18004a136  mov     ebx, eax
0x18004a138  lea     rcx, [rsp+78h+arg_8]
0x18004a140  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a145  test    ebx, ebx
0x18004a147  js      short loc_18004A174
0x18004a149  lea     rcx, [rsi+8]
0x18004a14d  mov     [rsp+78h+var_50], 2
0x18004a155  mov     rax, [rcx]
0x18004a158  mov     r9, rbp
0x18004a15b  mov     r8d, r14d
0x18004a15e  mov     [rsp+78h+var_58], 1
0x18004a166  mov     rdx, rdi
0x18004a169  mov     rax, [rax+18h]
0x18004a16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a172  mov     ebx, eax
0x18004a174  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a17b  cmp     rcx, r15
0x18004a17e  jz      short loc_18004A1AC
0x18004a180  test    byte ptr [rcx+1Ch], 80h
0x18004a184  jz      short loc_18004A1AC
0x18004a186  cmp     byte ptr [rcx+19h], 5
0x18004a18a  jb      short loc_18004A1AC
0x18004a18c  mov     rcx, [rcx+10h]
0x18004a190  lea     r9, aChangeapplicat_45; "ChangeApplicationServices::ReportRecove"...
0x18004a197  mov     edx, 21h ; '!'
0x18004a19c  mov     [rsp+78h+var_58], ebx
0x18004a1a0  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a1a7  call    WPP_SF_sD
0x18004a1ac  mov     eax, ebx
0x18004a1ae  add     rsp, 48h
0x18004a1b2  pop     r15
0x18004a1b4  pop     r14
0x18004a1b6  pop     rdi
0x18004a1b7  pop     rsi
0x18004a1b8  pop     rbp
0x18004a1b9  pop     rbx
0x18004a1ba  retn
```
