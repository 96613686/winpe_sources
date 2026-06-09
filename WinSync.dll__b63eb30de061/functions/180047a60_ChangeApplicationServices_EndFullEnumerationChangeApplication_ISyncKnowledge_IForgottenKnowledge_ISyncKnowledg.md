# ChangeApplicationServices::EndFullEnumerationChangeApplication(ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge * *,IForgottenKnowledge * *)

- ea: `0x180047a60`
- end: `0x180047c23`
- name: `?EndFullEnumerationChangeApplication@ChangeApplicationServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAU2@PEAPEAU3@@Z`
- size: `451`
- prototype: `__int64 __fastcall(ChangeApplicationServices *this, struct ISyncKnowledge *, struct ISyncKnowledge *, struct ISyncKnowledge **, struct IForgottenKnowledge **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180047150`
- `0x1800477f0`
- `0x180047a60`
- `0x1800489c0`
- `0x180049288`
- `0x18004a8fc`
- `0x180073930`
- `0x180094010`

## string_xrefs

- `0x180047aa0`: `ChangeApplicationServices::EndFullEnumerationChangeApplication`
- `0x180047bf4`: `ChangeApplicationServices::EndFullEnumerationChangeApplication`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::EndFullEnumerationChangeApplication(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge *a3,
        struct ISyncKnowledge **a4,
        struct IForgottenKnowledge **a5)
{
  ChangeApplicationServices *v9; // rcx
  ChangeApplicationServices *v10; // rcx
  int v11; // ebx
  struct ISyncKnowledge *v12; // rax
  struct IForgottenKnowledge *v13; // rax

  v9 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::EndFullEnumerationChangeApplication");
    v9 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 && a5 )
  {
    v11 = ChangeApplicationServices::ValidateIdParameters(v9, (ChangeApplicationServices *)((char *)this + 40), a2);
    if ( v11 >= 0 )
    {
      v11 = ChangeApplicationServices::ValidateIdParameters(v10, (ChangeApplicationServices *)((char *)this + 40), a3);
      if ( v11 >= 0 )
      {
        v11 = ChangeApplicationServices::ChangeState((__int64)this, 5);
        if ( v11 >= 0 )
        {
          v11 = ChangeApplicationServices::ReportFailedChanges(this);
          if ( v11 >= 0 )
          {
            v11 = ChangeApplicationStatistics::Save((char *)this + 216, (char *)this + 72);
            if ( v11 >= 0 )
            {
              v11 = ChangeApplicationServices::ApplyExclusions(this, a2);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge *))(**((_QWORD **)this + 10) + 104LL))(
                        *((_QWORD *)this + 10),
                        a2);
                if ( v11 >= 0 )
                {
                  v11 = ChangeApplicationServices::ApplyExclusions(this, a3);
                  if ( v11 >= 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge *))(**((_QWORD **)this + 11) + 104LL))(
                            *((_QWORD *)this + 11),
                            a3);
                    if ( v11 >= 0 )
                    {
                      v12 = (struct ISyncKnowledge *)*((_QWORD *)this + 10);
                      *((_QWORD *)this + 10) = 0;
                      *a4 = v12;
                      v13 = (struct IForgottenKnowledge *)*((_QWORD *)this + 11);
                      *((_QWORD *)this + 11) = 0;
                      *a5 = v13;
                      ChangeApplicationServices::ReleaseChangeApplicationState(this);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v9 = (ChangeApplicationServices *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v9 != (ChangeApplicationServices *)&WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      *((_QWORD *)v9 + 2),
      21,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::EndFullEnumerationChangeApplication",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180047a60  push    rbx
0x180047a62  push    rbp
0x180047a63  push    rsi
0x180047a64  push    rdi
0x180047a65  push    r12
0x180047a67  push    r13
0x180047a69  push    r14
0x180047a6b  push    r15
0x180047a6d  sub     rsp, 38h
0x180047a71  mov     r12, r9
0x180047a74  mov     r14, r8
0x180047a77  mov     rsi, rdx
0x180047a7a  mov     rdi, rcx
0x180047a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a84  lea     r13, WPP_GLOBAL_Control
0x180047a8b  cmp     rcx, r13
0x180047a8e  jz      short loc_180047ABF
0x180047a90  test    byte ptr [rcx+1Ch], 80h
0x180047a94  jz      short loc_180047ABF
0x180047a96  cmp     byte ptr [rcx+19h], 5
0x180047a9a  jb      short loc_180047ABF
0x180047a9c  mov     rcx, [rcx+10h]
0x180047aa0  lea     r9, aChangeapplicat_18; "ChangeApplicationServices::EndFullEnume"...
0x180047aa7  mov     edx, 14h
0x180047aac  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047ab3  call    WPP_SF_s
0x180047ab8  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180047abf  test    rsi, rsi
0x180047ac2  jz      loc_180047BDA
0x180047ac8  test    r14, r14
0x180047acb  jz      loc_180047BDA
0x180047ad1  test    r12, r12
0x180047ad4  jz      loc_180047BDA
0x180047ada  mov     r15, [rsp+78h+arg_20]
0x180047ae2  test    r15, r15
0x180047ae5  jz      loc_180047BDA
0x180047aeb  mov     r8, rsi; struct ISyncKnowledge *
0x180047aee  lea     rdx, [rdi+28h]; struct IdDescription *
0x180047af2  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180047af7  mov     ebx, eax
0x180047af9  test    eax, eax
0x180047afb  js      loc_180047BD1
0x180047b01  mov     r8, r14; struct ISyncKnowledge *
0x180047b04  lea     rdx, [rdi+28h]; struct IdDescription *
0x180047b08  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180047b0d  mov     ebx, eax
0x180047b0f  test    eax, eax
0x180047b11  js      loc_180047BD1
0x180047b17  mov     edx, 5
0x180047b1c  mov     rcx, rdi
0x180047b1f  call    ?ChangeState@ChangeApplicationServices@@AEAAJW4ChangeApplicationServicesState@@@Z; ChangeApplicationServices::ChangeState(ChangeApplicationServicesState)
0x180047b24  mov     ebx, eax
0x180047b26  test    eax, eax
0x180047b28  js      loc_180047BD1
0x180047b2e  mov     rcx, rdi; this
0x180047b31  call    ?ReportFailedChanges@ChangeApplicationServices@@AEAAJXZ; ChangeApplicationServices::ReportFailedChanges(void)
0x180047b36  mov     ebx, eax
0x180047b38  test    eax, eax
0x180047b3a  js      loc_180047BD1
0x180047b40  lea     rdx, [rdi+48h]
0x180047b44  lea     rcx, [rdi+0D8h]
0x180047b4b  call    ?Save@ChangeApplicationStatistics@@QEAAJAEBV?$SharedRefPtr@UISyncSessionState@@@@@Z; ChangeApplicationStatistics::Save(SharedRefPtr<ISyncSessionState> const &)
0x180047b50  mov     ebx, eax
0x180047b52  test    eax, eax
0x180047b54  js      short loc_180047BD1
0x180047b56  mov     rdx, rsi; struct ISyncKnowledge *
0x180047b59  mov     rcx, rdi; this
0x180047b5c  call    ?ApplyExclusions@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z; ChangeApplicationServices::ApplyExclusions(ISyncKnowledge *)
0x180047b61  mov     ebx, eax
0x180047b63  test    eax, eax
0x180047b65  js      short loc_180047BD1
0x180047b67  mov     rcx, [rdi+50h]
0x180047b6b  mov     rdx, rsi
0x180047b6e  mov     rax, [rcx]
0x180047b71  mov     rax, [rax+68h]
0x180047b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b7a  mov     ebx, eax
0x180047b7c  test    eax, eax
0x180047b7e  js      short loc_180047BD1
0x180047b80  mov     rdx, r14; struct ISyncKnowledge *
0x180047b83  mov     rcx, rdi; this
0x180047b86  call    ?ApplyExclusions@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z; ChangeApplicationServices::ApplyExclusions(ISyncKnowledge *)
0x180047b8b  mov     ebx, eax
0x180047b8d  test    eax, eax
0x180047b8f  js      short loc_180047BD1
0x180047b91  mov     rcx, [rdi+58h]
0x180047b95  mov     rdx, r14
0x180047b98  mov     rax, [rcx]
0x180047b9b  mov     rax, [rax+68h]
0x180047b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ba4  mov     ebx, eax
0x180047ba6  test    eax, eax
0x180047ba8  js      short loc_180047BD1
0x180047baa  mov     rax, [rdi+50h]
0x180047bae  mov     rcx, rdi; this
0x180047bb1  mov     qword ptr [rdi+50h], 0
0x180047bb9  mov     [r12], rax
0x180047bbd  mov     rax, [rdi+58h]
0x180047bc1  mov     qword ptr [rdi+58h], 0
0x180047bc9  mov     [r15], rax
0x180047bcc  call    ?ReleaseChangeApplicationState@ChangeApplicationServices@@AEAAXXZ; ChangeApplicationServices::ReleaseChangeApplicationState(void)
0x180047bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bd8  jmp     short loc_180047BDF
0x180047bda  mov     ebx, 80004003h
0x180047bdf  cmp     rcx, r13
0x180047be2  jz      short loc_180047C10
0x180047be4  test    byte ptr [rcx+1Ch], 80h
0x180047be8  jz      short loc_180047C10
0x180047bea  cmp     byte ptr [rcx+19h], 5
0x180047bee  jb      short loc_180047C10
0x180047bf0  mov     rcx, [rcx+10h]
0x180047bf4  lea     r9, aChangeapplicat_18; "ChangeApplicationServices::EndFullEnume"...
0x180047bfb  mov     edx, 15h
0x180047c00  mov     [rsp+78h+var_58], ebx
0x180047c04  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047c0b  call    WPP_SF_sD
0x180047c10  mov     eax, ebx
0x180047c12  add     rsp, 38h
0x180047c16  pop     r15
0x180047c18  pop     r14
0x180047c1a  pop     r13
0x180047c1c  pop     r12
0x180047c1e  pop     rdi
0x180047c1f  pop     rsi
0x180047c20  pop     rbp
0x180047c21  pop     rbx
0x180047c22  retn
```
