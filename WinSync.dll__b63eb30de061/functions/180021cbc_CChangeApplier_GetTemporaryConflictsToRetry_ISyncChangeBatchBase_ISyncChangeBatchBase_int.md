# CChangeApplier::GetTemporaryConflictsToRetry(ISyncChangeBatchBase *,ISyncChangeBatchBase * *,int *)

- ea: `0x180021cbc`
- end: `0x18002200b`
- name: `?GetTemporaryConflictsToRetry@CChangeApplier@@AEAAJPEAUISyncChangeBatchBase@@PEAPEAU2@PEAH@Z`
- size: `847`
- prototype: `__int64 __fastcall(CChangeApplier *this, struct ISyncChangeBatchBase *, struct ISyncChangeBatchBase **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180035a7c`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180021cbc`
- `0x180022014`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x180021d07`: `CChangeApplier::GetTemporaryConflictsToRetry`
- `0x180021fd5`: `CChangeApplier::GetTemporaryConflictsToRetry`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetTemporaryConflictsToRetry(
        CChangeApplier *this,
        struct ISyncChangeBatchBase *a2,
        struct ISyncChangeBatchBase **a3,
        unsigned int *a4)
{
  PVOID *v8; // rcx
  int v9; // ebx
  __int64 *v10; // rcx
  struct CSyncChangeBatch *v11; // rdi
  unsigned int v12; // esi
  __int64 v13; // rax
  struct ISyncChangeBatchBaseVtbl *lpVtbl; // rax
  int v15; // eax
  bool v16; // zf
  struct ISyncChangeBatchBaseVtbl *v17; // rax
  __int64 v18; // rdx
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  struct CSyncChangeBatch *v21; // [rsp+48h] [rbp-28h] BYREF
  struct IEnumLoggedConflicts *v22; // [rsp+50h] [rbp-20h] BYREF
  struct ISyncKnowledge *v23; // [rsp+58h] [rbp-18h] BYREF
  struct IForgottenKnowledge *v24; // [rsp+60h] [rbp-10h] BYREF
  struct ISyncFilterInfo *v25; // [rsp+68h] [rbp-8h] BYREF
  int v26; // [rsp+B8h] [rbp+48h] BYREF
  struct ISyncChangeBatchBase **v27; // [rsp+C0h] [rbp+50h]

  v27 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      166,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetTemporaryConflictsToRetry");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = -2147467261;
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    v10 = (__int64 *)*((_QWORD *)this + 79);
    v22 = 0;
    v11 = 0;
    v23 = 0;
    v12 = 0;
    v24 = 0;
    v25 = 0;
    v13 = *v10;
    *a4 = 0;
    v21 = 0;
    v26 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, struct IEnumLoggedConflicts **))(v13 + 48))(v10, &v22);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct ISyncChangeBatchBase *, struct ISyncKnowledge **))a2->lpVtbl->GetPrerequisiteKnowledge)(
             a2,
             &v23);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(struct ISyncChangeBatchBase *, struct IForgottenKnowledge **))a2->lpVtbl->GetSourceForgottenKnowledge)(
               a2,
               &v24);
        if ( v9 >= 0 )
        {
          lpVtbl = a2->lpVtbl;
          v20 = 0;
          v9 = ((__int64 (__fastcall *)(struct ISyncChangeBatchBase *, GUID *, __int64 *))lpVtbl->QueryInterface)(
                 a2,
                 &GUID_0f1a4995_cbc8_421d_b550_5d0bebf3e9a5,
                 &v20);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncFilterInfo **))(*(_QWORD *)v20 + 24LL))(v20, &v25);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( v9 >= 0 )
            {
              v15 = CSyncChangeBatch_CreateInstance(
                      *((struct IdParameters **)this + 22),
                      v23,
                      v24,
                      v25,
                      0,
                      0,
                      0,
                      (void **)&v21);
              v11 = v21;
              v9 = v15;
              if ( v15 >= 0 )
              {
                while ( !v12 )
                {
                  if ( *((int *)this + 162) >= 5 )
                  {
                    if ( v9 < 0 )
                      goto LABEL_30;
                    break;
                  }
                  v9 = CChangeApplier::FillTemporaryConflictBatchForCurrentStage(this, v22, v11, &v26);
                  if ( v9 < 0 )
                    goto LABEL_30;
                  v12 = v26;
                  v16 = v26 == 0;
                  if ( v26 > 0 )
                  {
                    v17 = a2->lpVtbl;
                    LODWORD(v20) = 0;
                    v9 = ((__int64 (__fastcall *)(struct ISyncChangeBatchBase *, __int64 *))v17->GetRemainingWorkEstimateForSession)(
                           a2,
                           &v20);
                    if ( v9 < 0 )
                      goto LABEL_30;
                    v18 = (unsigned int)v20 + v12;
                    if ( (unsigned int)v18 < (unsigned int)v20 )
                      v18 = 0xFFFFFFFFLL;
                    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*((_QWORD *)v11 + 2) + 120LL))(
                           (__int64)v11 + 16,
                           v18);
                    if ( v9 < 0 )
                      goto LABEL_30;
                    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v11 + 2) + 112LL))(
                           (__int64)v11 + 16,
                           v12);
                    if ( v9 < 0 )
                      goto LABEL_30;
                    v16 = v12 == 0;
                  }
                  if ( v16 && (int)++*((_DWORD *)this + 162) > 5 )
                  {
                    v9 = -2147217379;
                    goto LABEL_30;
                  }
                }
                v9 = (**(__int64 (__fastcall ***)(struct CSyncChangeBatch *, GUID *, struct ISyncChangeBatchBase **))v11)(
                       v11,
                       &GUID_52f6e694_6a71_4494_a184_a8311bf5d227,
                       v27);
                if ( v9 >= 0 )
                  *a4 = v12;
              }
            }
          }
        }
      }
    }
LABEL_30:
    if ( v22 )
      (*(void (__fastcall **)(struct IEnumLoggedConflicts *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v23->lpVtbl->Release)(v23);
    if ( v24 )
      ((void (__fastcall *)(struct IForgottenKnowledge *))v24->lpVtbl->Release)(v24);
    if ( v25 )
      ((void (__fastcall *)(struct ISyncFilterInfo *))v25->lpVtbl->Release)(v25);
    if ( v11 )
      (*(void (__fastcall **)(struct CSyncChangeBatch *))(*(_QWORD *)v11 + 16LL))(v11);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      167,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetTemporaryConflictsToRetry",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021cbc  mov     [rsp-38h+arg_0], rbx
0x180021cc1  mov     [rsp-38h+arg_10], r8
0x180021cc6  push    rbp
0x180021cc7  push    rsi
0x180021cc8  push    rdi
0x180021cc9  push    r12
0x180021ccb  push    r13
0x180021ccd  push    r14
0x180021ccf  push    r15
0x180021cd1  mov     rbp, rsp
0x180021cd4  sub     rsp, 70h
0x180021cd8  mov     r13, r9
0x180021cdb  mov     r12, r8
0x180021cde  mov     r14, rdx
0x180021ce1  mov     r15, rcx
0x180021ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ceb  lea     rax, WPP_GLOBAL_Control
0x180021cf2  cmp     rcx, rax
0x180021cf5  jz      short loc_180021D26
0x180021cf7  test    byte ptr [rcx+1Ch], 8
0x180021cfb  jz      short loc_180021D26
0x180021cfd  cmp     byte ptr [rcx+19h], 5
0x180021d01  jb      short loc_180021D26
0x180021d03  mov     rcx, [rcx+10h]
0x180021d07  lea     r9, aCchangeapplier_11; "CChangeApplier::GetTemporaryConflictsTo"...
0x180021d0e  mov     edx, 0A6h
0x180021d13  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180021d1a  call    WPP_SF_s
0x180021d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d26  mov     ebx, 80004003h
0x180021d2b  test    r14, r14
0x180021d2e  jz      loc_180021FB9
0x180021d34  test    r12, r12
0x180021d37  jz      loc_180021FB9
0x180021d3d  test    r13, r13
0x180021d40  jz      loc_180021FB9
0x180021d46  mov     qword ptr [r12], 0
0x180021d4e  lea     rdx, [rbp+var_20]
0x180021d52  mov     rcx, [r15+278h]
0x180021d59  xor     r12d, r12d
0x180021d5c  mov     [rbp+var_20], r12
0x180021d60  mov     edi, r12d
0x180021d63  mov     [rbp+var_18], r12
0x180021d67  mov     esi, r12d
0x180021d6a  mov     [rbp+var_10], r12
0x180021d6e  mov     [rbp+var_8], r12
0x180021d72  mov     rax, [rcx]
0x180021d75  mov     [r13+0], r12d
0x180021d79  mov     [rbp+var_28], r12
0x180021d7d  mov     [rbp+arg_8], r12d
0x180021d81  mov     rax, [rax+30h]
0x180021d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d8a  mov     ebx, eax
0x180021d8c  test    eax, eax
0x180021d8e  js      loc_180021F4A
0x180021d94  mov     rax, [r14]
0x180021d97  lea     rdx, [rbp+var_18]
0x180021d9b  mov     rcx, r14
0x180021d9e  mov     rax, [rax+58h]
0x180021da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da7  mov     ebx, eax
0x180021da9  test    eax, eax
0x180021dab  js      loc_180021F4A
0x180021db1  mov     rax, [r14]
0x180021db4  lea     rdx, [rbp+var_10]
0x180021db8  mov     rcx, r14
0x180021dbb  mov     rax, [rax+60h]
0x180021dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dc4  mov     ebx, eax
0x180021dc6  test    eax, eax
0x180021dc8  js      loc_180021F4A
0x180021dce  mov     rax, [r14]
0x180021dd1  lea     r8, [rbp+var_30]
0x180021dd5  lea     rdx, _GUID_0f1a4995_cbc8_421d_b550_5d0bebf3e9a5
0x180021ddc  mov     [rbp+var_30], r12
0x180021de0  mov     rcx, r14
0x180021de3  mov     rax, [rax]
0x180021de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021deb  mov     ebx, eax
0x180021ded  test    eax, eax
0x180021def  js      loc_180021F4A
0x180021df5  mov     rcx, [rbp+var_30]
0x180021df9  lea     rdx, [rbp+var_8]
0x180021dfd  mov     rax, [rcx]
0x180021e00  mov     rax, [rax+18h]
0x180021e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e09  mov     rcx, [rbp+var_30]
0x180021e0d  mov     ebx, eax
0x180021e0f  mov     rax, [rcx]
0x180021e12  mov     rax, [rax+10h]
0x180021e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e1b  test    ebx, ebx
0x180021e1d  js      loc_180021F4A
0x180021e23  mov     r9, [rbp+var_8]; struct ISyncFilterInfo *
0x180021e27  lea     rax, [rbp+var_28]
0x180021e2b  mov     r8, [rbp+var_10]; struct IForgottenKnowledge *
0x180021e2f  mov     rdx, [rbp+var_18]; struct ISyncKnowledge *
0x180021e33  mov     rcx, [r15+0B0h]; this
0x180021e3a  mov     [rsp+70h+var_38], rax; void **
0x180021e3f  mov     [rsp+70h+var_40], r12d; int
0x180021e44  mov     [rsp+70h+var_48], r12; unsigned __int8 *
0x180021e49  mov     [rsp+70h+var_50], r12d; int
0x180021e4e  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x180021e53  mov     rdi, [rbp+var_28]
0x180021e57  mov     ebx, eax
0x180021e59  test    eax, eax
0x180021e5b  js      loc_180021F4A
0x180021e61  test    esi, esi
0x180021e63  jnz     loc_180021F27
0x180021e69  cmp     dword ptr [r15+288h], 5
0x180021e71  jge     loc_180021F23
0x180021e77  mov     rdx, [rbp+var_20]; struct IEnumLoggedConflicts *
0x180021e7b  lea     r9, [rbp+arg_8]; int *
0x180021e7f  mov     r8, rdi; struct CSyncChangeBatch *
0x180021e82  mov     rcx, r15; this
0x180021e85  call    ?FillTemporaryConflictBatchForCurrentStage@CChangeApplier@@AEAAJPEAUIEnumLoggedConflicts@@PEAVCSyncChangeBatch@@PEAH@Z; CChangeApplier::FillTemporaryConflictBatchForCurrentStage(IEnumLoggedConflicts *,CSyncChangeBatch *,int *)
0x180021e8a  mov     ebx, eax
0x180021e8c  test    eax, eax
0x180021e8e  js      loc_180021F4A
0x180021e94  mov     esi, [rbp+arg_8]
0x180021e97  test    esi, esi
0x180021e99  jle     short loc_180021F01
0x180021e9b  mov     rax, [r14]
0x180021e9e  lea     rdx, [rbp+var_30]
0x180021ea2  mov     rcx, r14
0x180021ea5  mov     dword ptr [rbp+var_30], r12d
0x180021ea9  mov     rax, [rax+30h]
0x180021ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eb2  mov     ebx, eax
0x180021eb4  test    eax, eax
0x180021eb6  js      loc_180021F4A
0x180021ebc  mov     eax, dword ptr [rbp+var_30]
0x180021ebf  lea     r12, [rdi+10h]
0x180021ec3  or      ecx, 0FFFFFFFFh
0x180021ec6  lea     edx, [rax+rsi]
0x180021ec9  cmp     edx, eax
0x180021ecb  mov     rax, [r12]
0x180021ecf  cmovb   edx, ecx
0x180021ed2  mov     rcx, r12
0x180021ed5  mov     rax, [rax+78h]
0x180021ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ede  mov     ebx, eax
0x180021ee0  test    eax, eax
0x180021ee2  js      short loc_180021F4A
0x180021ee4  mov     rax, [r12]
0x180021ee8  mov     edx, esi
0x180021eea  mov     rcx, r12
0x180021eed  mov     rax, [rax+70h]
0x180021ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ef6  xor     r12d, r12d
0x180021ef9  mov     ebx, eax
0x180021efb  test    eax, eax
0x180021efd  js      short loc_180021F4A
0x180021eff  test    esi, esi
0x180021f01  jnz     loc_180021E61
0x180021f07  inc     dword ptr [r15+288h]
0x180021f0e  cmp     dword ptr [r15+288h], 5
0x180021f16  jle     loc_180021E61
0x180021f1c  mov     ebx, 8004101Dh
0x180021f21  jmp     short loc_180021F4A
0x180021f23  test    ebx, ebx
0x180021f25  js      short loc_180021F4A
0x180021f27  mov     rax, [rdi]
0x180021f2a  lea     rdx, _GUID_52f6e694_6a71_4494_a184_a8311bf5d227
0x180021f31  mov     r8, [rbp+arg_10]
0x180021f35  mov     rcx, rdi
0x180021f38  mov     rax, [rax]
0x180021f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f40  mov     ebx, eax
0x180021f42  test    eax, eax
0x180021f44  js      short loc_180021F4A
0x180021f46  mov     [r13+0], esi
0x180021f4a  mov     rcx, [rbp+var_20]
0x180021f4e  test    rcx, rcx
0x180021f51  jz      short loc_180021F5F
0x180021f53  mov     rax, [rcx]
0x180021f56  mov     rax, [rax+10h]
0x180021f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f5f  mov     rcx, [rbp+var_18]
0x180021f63  test    rcx, rcx
0x180021f66  jz      short loc_180021F74
0x180021f68  mov     rax, [rcx]
0x180021f6b  mov     rax, [rax+10h]
0x180021f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f74  mov     rcx, [rbp+var_10]
0x180021f78  test    rcx, rcx
0x180021f7b  jz      short loc_180021F89
0x180021f7d  mov     rax, [rcx]
0x180021f80  mov     rax, [rax+10h]
0x180021f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f89  mov     rcx, [rbp+var_8]
0x180021f8d  test    rcx, rcx
0x180021f90  jz      short loc_180021F9E
0x180021f92  mov     rax, [rcx]
0x180021f95  mov     rax, [rax+10h]
0x180021f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9e  test    rdi, rdi
0x180021fa1  jz      short loc_180021FB2
0x180021fa3  mov     rax, [rdi]
0x180021fa6  mov     rcx, rdi
0x180021fa9  mov     rax, [rax+10h]
0x180021fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fb9  lea     rax, WPP_GLOBAL_Control
0x180021fc0  cmp     rcx, rax
0x180021fc3  jz      short loc_180021FF1
0x180021fc5  test    byte ptr [rcx+1Ch], 8
0x180021fc9  jz      short loc_180021FF1
0x180021fcb  cmp     byte ptr [rcx+19h], 5
0x180021fcf  jb      short loc_180021FF1
0x180021fd1  mov     rcx, [rcx+10h]
0x180021fd5  lea     r9, aCchangeapplier_11; "CChangeApplier::GetTemporaryConflictsTo"...
0x180021fdc  mov     edx, 0A7h
0x180021fe1  mov     [rsp+70h+var_50], ebx
0x180021fe5  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180021fec  call    WPP_SF_sD
0x180021ff1  mov     eax, ebx
0x180021ff3  mov     rbx, [rsp+70h+arg_0]
0x180021ffb  add     rsp, 70h
0x180021fff  pop     r15
0x180022001  pop     r14
0x180022003  pop     r13
0x180022005  pop     r12
0x180022007  pop     rdi
0x180022008  pop     rsi
0x180022009  pop     rbp
0x18002200a  retn
```
