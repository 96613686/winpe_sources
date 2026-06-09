# ChangeApplicationServices::EndChangeApplication(ISyncKnowledge *,ISyncKnowledge * *)

- ea: `0x180047900`
- end: `0x180047a53`
- name: `?EndChangeApplication@ChangeApplicationServices@@UEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct ISyncKnowledge **this, struct ISyncKnowledge *, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180047150`
- `0x1800477f0`
- `0x180047900`
- `0x180048340`
- `0x1800489c0`
- `0x180049288`
- `0x18004a8fc`
- `0x180073930`
- `0x180094010`

## string_xrefs

- `0x180047937`: `ChangeApplicationServices::EndChangeApplication`
- `0x180047a2a`: `ChangeApplicationServices::EndChangeApplication`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::EndChangeApplication(
        struct ISyncKnowledge **this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge **a3)
{
  ChangeApplicationServices *v6; // rcx
  int v7; // ebx
  struct ISyncKnowledge *v8; // rax

  v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::EndChangeApplication");
    v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    v7 = ChangeApplicationServices::ValidateIdParameters(v6, (const struct IdDescription *)(this + 5), a2);
    if ( v7 >= 0 )
    {
      v7 = ChangeApplicationServices::ChangeState((__int64)this, 4);
      if ( v7 >= 0 )
      {
        v7 = ChangeApplicationServices::ReportFailedChanges((ChangeApplicationServices *)this);
        if ( v7 >= 0 )
        {
          v7 = ChangeApplicationStatistics::Save(this + 27, this + 9);
          if ( v7 >= 0 )
          {
            v7 = ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite(
                   (ChangeApplicationServices *)this,
                   a2);
            if ( v7 >= 0 )
            {
              v7 = ChangeApplicationServices::ApplyExclusions((ChangeApplicationServices *)this, a2);
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, struct ISyncKnowledge *))this[10]->lpVtbl->Union)(
                       this[10],
                       a2);
                if ( v7 >= 0 )
                {
                  v8 = this[10];
                  this[10] = 0;
                  *a3 = v8;
                  ChangeApplicationServices::ReleaseChangeApplicationState((ChangeApplicationServices *)this);
                }
              }
            }
          }
        }
      }
    }
    v6 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = -2147467261;
  }
  if ( v6 != (ChangeApplicationServices *)&WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v6 + 2),
      19,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::EndChangeApplication",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047900  push    rbx
0x180047902  push    rbp
0x180047903  push    rsi
0x180047904  push    rdi
0x180047905  push    r14
0x180047907  sub     rsp, 30h
0x18004790b  mov     r14, r8
0x18004790e  mov     rsi, rdx
0x180047911  mov     rdi, rcx
0x180047914  mov     rcx, cs:WPP_GLOBAL_Control
0x18004791b  lea     rbp, WPP_GLOBAL_Control
0x180047922  cmp     rcx, rbp
0x180047925  jz      short loc_180047956
0x180047927  test    byte ptr [rcx+1Ch], 80h
0x18004792b  jz      short loc_180047956
0x18004792d  cmp     byte ptr [rcx+19h], 5
0x180047931  jb      short loc_180047956
0x180047933  mov     rcx, [rcx+10h]
0x180047937  lea     r9, aChangeapplicat_23; "ChangeApplicationServices::EndChangeApp"...
0x18004793e  mov     edx, 12h
0x180047943  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004794a  call    WPP_SF_s
0x18004794f  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180047956  test    rsi, rsi
0x180047959  jz      loc_180047A10
0x18004795f  test    r14, r14
0x180047962  jz      loc_180047A10
0x180047968  lea     rdx, [rdi+28h]; struct IdDescription *
0x18004796c  mov     r8, rsi; struct ISyncKnowledge *
0x18004796f  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180047974  mov     ebx, eax
0x180047976  test    eax, eax
0x180047978  js      loc_180047A07
0x18004797e  mov     edx, 4
0x180047983  mov     rcx, rdi
0x180047986  call    ?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z; ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)
0x18004798b  mov     ebx, eax
0x18004798d  test    eax, eax
0x18004798f  js      short loc_180047A07
0x180047991  mov     rcx, rdi; this
0x180047994  call    ?ReportFailedChanges@ChangeApplicationServices@@AEAAJXZ; ChangeApplicationServices::ReportFailedChanges(void)
0x180047999  mov     ebx, eax
0x18004799b  test    eax, eax
0x18004799d  js      short loc_180047A07
0x18004799f  lea     rdx, [rdi+48h]
0x1800479a3  lea     rcx, [rdi+0D8h]
0x1800479aa  call    ?Save@ChangeApplicationStatistics@@QEAAJAEBV?$SharedRefPtr@UISyncSessionState@@@@@Z; ChangeApplicationStatistics::Save(SharedRefPtr<ISyncSessionState> const &)
0x1800479af  mov     ebx, eax
0x1800479b1  test    eax, eax
0x1800479b3  js      short loc_180047A07
0x1800479b5  mov     rdx, rsi; struct ISyncKnowledge *
0x1800479b8  mov     rcx, rdi; this
0x1800479bb  call    ?LearnAppliedChangesWithUnsatisfiedPrerequisite@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z; ChangeApplicationServices::LearnAppliedChangesWithUnsatisfiedPrerequisite(ISyncKnowledge *)
0x1800479c0  mov     ebx, eax
0x1800479c2  test    eax, eax
0x1800479c4  js      short loc_180047A07
0x1800479c6  mov     rdx, rsi; struct ISyncKnowledge *
0x1800479c9  mov     rcx, rdi; this
0x1800479cc  call    ?ApplyExclusions@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z; ChangeApplicationServices::ApplyExclusions(ISyncKnowledge *)
0x1800479d1  mov     ebx, eax
0x1800479d3  test    eax, eax
0x1800479d5  js      short loc_180047A07
0x1800479d7  mov     rcx, [rdi+50h]
0x1800479db  mov     rdx, rsi
0x1800479de  mov     rax, [rcx]
0x1800479e1  mov     rax, [rax+68h]
0x1800479e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479ea  mov     ebx, eax
0x1800479ec  test    eax, eax
0x1800479ee  js      short loc_180047A07
0x1800479f0  mov     rax, [rdi+50h]
0x1800479f4  mov     rcx, rdi; this
0x1800479f7  mov     qword ptr [rdi+50h], 0
0x1800479ff  mov     [r14], rax
0x180047a02  call    ?ReleaseChangeApplicationState@ChangeApplicationServices@@AEAAXXZ; ChangeApplicationServices::ReleaseChangeApplicationState(void)
0x180047a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a0e  jmp     short loc_180047A15
0x180047a10  mov     ebx, 80004003h
0x180047a15  cmp     rcx, rbp
0x180047a18  jz      short loc_180047A46
0x180047a1a  test    byte ptr [rcx+1Ch], 80h
0x180047a1e  jz      short loc_180047A46
0x180047a20  cmp     byte ptr [rcx+19h], 5
0x180047a24  jb      short loc_180047A46
0x180047a26  mov     rcx, [rcx+10h]
0x180047a2a  lea     r9, aChangeapplicat_23; "ChangeApplicationServices::EndChangeApp"...
0x180047a31  mov     edx, 13h
0x180047a36  mov     [rsp+58h+var_38], ebx
0x180047a3a  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047a41  call    WPP_SF_sD
0x180047a46  mov     eax, ebx
0x180047a48  add     rsp, 30h
0x180047a4c  pop     r14
0x180047a4e  pop     rdi
0x180047a4f  pop     rsi
0x180047a50  pop     rbp
0x180047a51  pop     rbx
0x180047a52  retn
```
