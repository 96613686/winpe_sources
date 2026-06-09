# CChangeApplier::CreateProviderForgottenKnowledge(ISyncKnowledge *,IForgottenKnowledge * *)

- ea: `0x180037cb0`
- end: `0x180037e44`
- name: `?CreateProviderForgottenKnowledge@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAPEAUIForgottenKnowledge@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct ISyncKnowledge *, struct IForgottenKnowledge **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800331dc`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002070c`
- `0x18002d1c8`
- `0x180037cb0`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x180037cfd`: `CChangeApplier::CreateProviderForgottenKnowledge`
- `0x180037e06`: `CChangeApplier::CreateProviderForgottenKnowledge`

## pseudocode

```c
__int64 __fastcall CChangeApplier::CreateProviderForgottenKnowledge(
        CChangeApplier *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge **a3)
{
  PVOID *v6; // rcx
  int Parameters; // ebx
  struct ISyncKnowledgeVtbl *lpVtbl; // rax
  IdParameters *v9; // rcx
  void *v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  struct _ID_PARAMETERS v13; // [rsp+40h] [rbp-30h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      184,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::CreateProviderForgottenKnowledge");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  Parameters = -2147467261;
  if ( a2 && a3 )
  {
    lpVtbl = a2->lpVtbl;
    v12 = 0;
    Parameters = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64 *))lpVtbl->GetReplicaKeyMap)(a2, &v12);
    if ( Parameters >= 0 )
    {
      v9 = (IdParameters *)*((_QWORD *)this + 22);
      v11 = 0;
      memset(&v13, 0, sizeof(v13));
      Parameters = IdParameters::GetParameters(v9, &v13);
      if ( Parameters >= 0 )
      {
        Parameters = CreateSyncService(&IID_IProviderSyncServices, &v11);
        if ( Parameters >= 0 )
        {
          Parameters = (*(__int64 (__fastcall **)(void *, struct _ID_PARAMETERS *))(*(_QWORD *)v11 + 24LL))(v11, &v13);
          if ( Parameters >= 0 )
            Parameters = (*(__int64 (__fastcall **)(void *, __int64, struct IForgottenKnowledge **))(*(_QWORD *)v11 + 72LL))(
                           v11,
                           v12,
                           a3);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      185,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::CreateProviderForgottenKnowledge",
      Parameters);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x180037cb0  mov     [rsp-28h+arg_0], rbx
0x180037cb5  push    rbp
0x180037cb6  push    rsi
0x180037cb7  push    rdi
0x180037cb8  push    r14
0x180037cba  push    r15
0x180037cbc  mov     rbp, rsp
0x180037cbf  sub     rsp, 70h
0x180037cc3  mov     rax, cs:__security_cookie
0x180037cca  xor     rax, rsp
0x180037ccd  mov     [rbp+var_10], rax
0x180037cd1  mov     rsi, r8
0x180037cd4  mov     rdi, rdx
0x180037cd7  mov     r14, rcx
0x180037cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ce1  lea     r15, WPP_GLOBAL_Control
0x180037ce8  cmp     rcx, r15
0x180037ceb  jz      short loc_180037D1C
0x180037ced  test    byte ptr [rcx+1Ch], 8
0x180037cf1  jz      short loc_180037D1C
0x180037cf3  cmp     byte ptr [rcx+19h], 5
0x180037cf7  jb      short loc_180037D1C
0x180037cf9  mov     rcx, [rcx+10h]
0x180037cfd  lea     r9, aCchangeapplier_49; "CChangeApplier::CreateProviderForgotten"...
0x180037d04  mov     edx, 0B8h
0x180037d09  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037d10  call    WPP_SF_s
0x180037d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d1c  mov     ebx, 80004003h
0x180037d21  test    rdi, rdi
0x180037d24  jz      loc_180037DF1
0x180037d2a  test    rsi, rsi
0x180037d2d  jz      loc_180037DF1
0x180037d33  mov     rax, [rdi]
0x180037d36  lea     rdx, [rbp+var_38]
0x180037d3a  mov     rcx, rdi
0x180037d3d  mov     [rbp+var_38], 0
0x180037d45  mov     rax, [rax+48h]
0x180037d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d4e  mov     ebx, eax
0x180037d50  test    eax, eax
0x180037d52  js      loc_180037DEA
0x180037d58  mov     rcx, [r14+0B0h]; this
0x180037d5f  lea     rdx, [rbp+var_30]; struct _ID_PARAMETERS *
0x180037d63  xorps   xmm0, xmm0
0x180037d66  mov     [rbp+var_40], 0
0x180037d6e  movups  xmmword ptr [rbp+var_30.dwSize], xmm0
0x180037d72  movups  xmmword ptr [rbp+var_30.itemId.fIsVariable], xmm0
0x180037d76  call    ?GetParameters@IdParameters@@QEAAJPEAU_ID_PARAMETERS@@@Z; IdParameters::GetParameters(_ID_PARAMETERS *)
0x180037d7b  mov     ebx, eax
0x180037d7d  test    eax, eax
0x180037d7f  js      short loc_180037DDA
0x180037d81  lea     rdx, [rbp+var_40]; void **
0x180037d85  lea     rcx, IID_IProviderSyncServices; struct _GUID *
0x180037d8c  call    ?CreateSyncService@@YAJAEBU_GUID@@PEAPEAX@Z; CreateSyncService(_GUID const &,void * *)
0x180037d91  mov     ebx, eax
0x180037d93  test    eax, eax
0x180037d95  js      short loc_180037DDA
0x180037d97  mov     rcx, [rbp+var_40]
0x180037d9b  lea     rdx, [rbp+var_30]
0x180037d9f  mov     rax, [rcx]
0x180037da2  mov     rax, [rax+18h]
0x180037da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037dab  mov     ebx, eax
0x180037dad  test    eax, eax
0x180037daf  js      short loc_180037DCA
0x180037db1  mov     rcx, [rbp+var_40]
0x180037db5  mov     r8, rsi
0x180037db8  mov     rdx, [rbp+var_38]
0x180037dbc  mov     rax, [rcx]
0x180037dbf  mov     rax, [rax+48h]
0x180037dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037dc8  mov     ebx, eax
0x180037dca  mov     rcx, [rbp+var_40]
0x180037dce  mov     rax, [rcx]
0x180037dd1  mov     rax, [rax+10h]
0x180037dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037dda  mov     rcx, [rbp+var_38]
0x180037dde  mov     rax, [rcx]
0x180037de1  mov     rax, [rax+10h]
0x180037de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180037df1  cmp     rcx, r15
0x180037df4  jz      short loc_180037E22
0x180037df6  test    byte ptr [rcx+1Ch], 8
0x180037dfa  jz      short loc_180037E22
0x180037dfc  cmp     byte ptr [rcx+19h], 5
0x180037e00  jb      short loc_180037E22
0x180037e02  mov     rcx, [rcx+10h]
0x180037e06  lea     r9, aCchangeapplier_49; "CChangeApplier::CreateProviderForgotten"...
0x180037e0d  mov     edx, 0B9h
0x180037e12  mov     [rsp+70h+var_50], ebx
0x180037e16  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037e1d  call    WPP_SF_sD
0x180037e22  mov     eax, ebx
0x180037e24  mov     rcx, [rbp+var_10]
0x180037e28  xor     rcx, rsp; StackCookie
0x180037e2b  call    __security_check_cookie
0x180037e30  mov     rbx, [rsp+70h+arg_0]
0x180037e38  add     rsp, 70h
0x180037e3c  pop     r15
0x180037e3e  pop     r14
0x180037e40  pop     rdi
0x180037e41  pop     rsi
0x180037e42  pop     rbp
0x180037e43  retn
```
