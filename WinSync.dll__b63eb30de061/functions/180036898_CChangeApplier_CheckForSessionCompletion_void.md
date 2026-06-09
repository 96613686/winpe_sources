# CChangeApplier::CheckForSessionCompletion(void)

- ea: `0x180036898`
- end: `0x180036bf1`
- name: `?CheckForSessionCompletion@CChangeApplier@@AEAAHXZ`
- size: `857`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045df0`
- `0x180046160`

## callees

- `0x18000f810`
- `0x18001a038`
- `0x18001ae20`
- `0x18002d338`
- `0x1800347e0`
- `0x180035a7c`
- `0x180036898`
- `0x18003b590`
- `0x180043e50`
- `0x180081f68`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003692c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036b23`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003692c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036b23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800368f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003693c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003693c`

## string_xrefs

- `0x1800368d1`: `CChangeApplier::CheckForSessionCompletion`
- `0x180036bc1`: `CChangeApplier::CheckForSessionCompletion`

## pseudocode

```c
__int64 __fastcall CChangeApplier::CheckForSessionCompletion(CChangeApplier *this)
{
  int v2; // ecx
  unsigned int v3; // r15d
  bool v4; // zf
  void *v5; // rcx
  BOOL v6; // esi
  int v7; // r14d
  struct ISyncChangeBatchBase *v8; // r12
  int v9; // eax
  int v10; // r12d
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r14
  const struct _GUID *v14; // r8
  unsigned int v16; // [rsp+70h] [rbp+40h] BYREF
  struct ISyncChangeBatchBase *v17; // [rsp+78h] [rbp+48h] BYREF
  struct IEnumSyncChanges *v18; // [rsp+80h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::CheckForSessionCompletion");
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  v2 = *((_DWORD *)this + 84);
  if ( ((v2 - 17) & 0xFFFFFFFA) != 0 || v2 == 18 )
  {
    v3 = 0;
    v6 = 0;
  }
  else
  {
    v3 = 1;
    v4 = v2 == 17;
    v5 = (void *)*((_QWORD *)this + 34);
    v6 = !v4;
    if ( v5 )
      SetEvent(v5);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  if ( v3 && *((_DWORD *)this + 23) && *((_QWORD *)this + 56) )
  {
    v17 = 0;
    v16 = 0;
    v7 = CChangeApplier::GetChangeApplierInfoWrapper(this, (unsigned __int8 **)&v17, &v16);
    if ( v7 < 0 )
      goto LABEL_17;
    v8 = v17;
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncChangeBatchBase *, _QWORD))(**((_QWORD **)this + 56) + 40LL))(
           *((_QWORD *)this + 56),
           v17,
           v16);
    if ( v8 )
      SeFree(v8);
    if ( v7 < 0 )
    {
LABEL_17:
      if ( !v6 )
      {
        *((_DWORD *)this + 70) = v7;
        v6 = 1;
      }
      goto LABEL_27;
    }
  }
  if ( v6 )
  {
    if ( !v3 )
      goto LABEL_41;
    goto LABEL_27;
  }
  if ( !v3 )
    goto LABEL_41;
  if ( *((_DWORD *)this + 23) )
  {
    v17 = (struct ISyncChangeBatchBase *)*((_QWORD *)this + 83);
    v16 = 0;
    v9 = CChangeApplier::CheckConflictLogForFurtherChanges(this, &v17, (int *)&v16);
    if ( v9 >= 0 )
    {
      if ( !v16 )
        goto LABEL_27;
      v18 = 0;
      v9 = CChangeApplier::ApplyOneChangeBatchHelper(this, &v17, &v18, 0, 0, (int *)&v16);
      v3 = 0;
      if ( v9 >= 0 )
        goto LABEL_41;
    }
    v3 = 1;
    *((_DWORD *)this + 70) = v9;
    v6 = 1;
  }
LABEL_27:
  v10 = *((_DWORD *)this + 23);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
  }
  if ( !*((_DWORD *)this + 24) && (!v6 || *((_DWORD *)this + 170)) )
  {
    v11 = *((_QWORD *)this + 16);
    *((_DWORD *)this + 24) = 1;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 48LL))(
      v11,
      ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 18) + 40LL))(
      *((_QWORD *)this + 18),
      ((unsigned __int64)this + 24) & -(__int64)(this != 0));
    if ( *((_DWORD *)this + 150) )
    {
      v12 = *((_QWORD *)this + 77);
      *((_DWORD *)this + 150) = 0;
      (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v12 + 40LL))(
        v12,
        ((unsigned __int64)this + 24) & -(__int64)(this != 0));
    }
  }
  SetEvent(*((HANDLE *)this + 44));
  if ( v10 )
  {
    v13 = *((_QWORD *)this + 16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    CChangeApplier::ResetChangeApplierState(this);
    if ( v6 )
    {
      SetErrorInfoHelper(*((_DWORD *)this + 70), &IID_IAsynchronousNotifyingChangeApplier, v14);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 112LL))(v13, *((unsigned int *)this + 70));
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 104LL))(v13);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    _InterlockedDecrement(&g_cRefThisDll);
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::CheckForSessionCompletion",
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180036898  push    rbp
0x18003689a  push    rsi
0x18003689b  push    rdi
0x18003689c  push    r12
0x18003689e  push    r13
0x1800368a0  push    r14
0x1800368a2  push    r15
0x1800368a4  mov     rbp, rsp
0x1800368a7  sub     rsp, 30h
0x1800368ab  mov     rdi, rcx
0x1800368ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368b5  lea     rax, WPP_GLOBAL_Control
0x1800368bc  cmp     rcx, rax
0x1800368bf  jz      short loc_1800368E9
0x1800368c1  test    byte ptr [rcx+1Ch], 8
0x1800368c5  jz      short loc_1800368E9
0x1800368c7  cmp     byte ptr [rcx+19h], 5
0x1800368cb  jb      short loc_1800368E9
0x1800368cd  mov     rcx, [rcx+10h]
0x1800368d1  lea     r9, aCchangeapplier_58; "CChangeApplier::CheckForSessionCompleti"...
0x1800368d8  mov     edx, 5Dh ; ']'
0x1800368dd  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800368e4  call    WPP_SF_s
0x1800368e9  lea     r14, [rdi+120h]
0x1800368f0  mov     rcx, r14; lpCriticalSection
0x1800368f3  call    cs:__imp_EnterCriticalSection
0x1800368f9  mov     ecx, [rdi+150h]
0x1800368ff  mov     r13d, 1
0x180036905  lea     eax, [rcx-11h]
0x180036908  test    eax, 0FFFFFFFAh
0x18003690d  jnz     short loc_180036934
0x18003690f  cmp     ecx, 12h
0x180036912  jz      short loc_180036934
0x180036914  xor     esi, esi
0x180036916  mov     r15d, r13d
0x180036919  cmp     ecx, 11h
0x18003691c  mov     rcx, [rdi+110h]; hEvent
0x180036923  setnz   sil
0x180036927  test    rcx, rcx
0x18003692a  jz      short loc_180036939
0x18003692c  call    cs:__imp_SetEvent
0x180036932  jmp     short loc_180036939
0x180036934  xor     r15d, r15d
0x180036937  xor     esi, esi
0x180036939  mov     rcx, r14; lpCriticalSection
0x18003693c  call    cs:__imp_LeaveCriticalSection
0x180036942  test    r15d, r15d
0x180036945  jz      loc_1800369CF
0x18003694b  cmp     dword ptr [rdi+5Ch], 0
0x18003694f  jz      short loc_1800369CF
0x180036951  cmp     qword ptr [rdi+1C0h], 0
0x180036959  jz      short loc_1800369CF
0x18003695b  lea     r8, [rbp+arg_0]; unsigned int *
0x18003695f  mov     [rbp+arg_8], 0
0x180036967  lea     rdx, [rbp+arg_8]; unsigned __int8 **
0x18003696b  mov     [rbp+arg_0], 0
0x180036972  mov     rcx, rdi; this
0x180036975  call    ?GetChangeApplierInfoWrapper@CChangeApplier@@AEAAJPEAPEAEPEAK@Z; CChangeApplier::GetChangeApplierInfoWrapper(uchar * *,ulong *)
0x18003697a  mov     r14d, eax
0x18003697d  test    eax, eax
0x18003697f  js      short loc_1800369B4
0x180036981  mov     rcx, [rdi+1C0h]
0x180036988  mov     r12, [rbp+arg_8]
0x18003698c  mov     r8d, [rbp+arg_0]
0x180036990  mov     rdx, r12
0x180036993  mov     rax, [rcx]
0x180036996  mov     rax, [rax+28h]
0x18003699a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003699f  mov     r14d, eax
0x1800369a2  test    r12, r12
0x1800369a5  jz      short loc_1800369AF
0x1800369a7  mov     rcx, r12; void *
0x1800369aa  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x1800369af  test    r14d, r14d
0x1800369b2  jns     short loc_1800369CF
0x1800369b4  test    esi, esi
0x1800369b6  jnz     loc_180036A57
0x1800369bc  mov     [rdi+118h], r14d
0x1800369c3  mov     esi, r13d
0x1800369c6  test    r14d, r14d
0x1800369c9  js      loc_180036A57
0x1800369cf  test    esi, esi
0x1800369d1  jnz     short loc_180036A4E
0x1800369d3  test    r15d, r15d
0x1800369d6  jz      loc_180036B9E
0x1800369dc  cmp     [rdi+5Ch], esi
0x1800369df  jz      short loc_180036A57
0x1800369e1  mov     rax, [rdi+298h]
0x1800369e8  lea     r8, [rbp+arg_0]; int *
0x1800369ec  lea     rdx, [rbp+arg_8]; struct ISyncChangeBatchBase **
0x1800369f0  mov     [rbp+arg_8], rax
0x1800369f4  mov     rcx, rdi; this
0x1800369f7  mov     [rbp+arg_0], esi
0x1800369fa  call    ?CheckConflictLogForFurtherChanges@CChangeApplier@@AEAAJPEAPEAUISyncChangeBatchBase@@PEAH@Z; CChangeApplier::CheckConflictLogForFurtherChanges(ISyncChangeBatchBase * *,int *)
0x1800369ff  test    eax, eax
0x180036a01  js      short loc_180036A40
0x180036a03  cmp     [rbp+arg_0], esi
0x180036a06  jz      short loc_180036A57
0x180036a08  lea     rax, [rbp+arg_0]
0x180036a0c  mov     [rbp+arg_10], 0
0x180036a14  mov     [rsp+30h+var_8], rax; int *
0x180036a19  lea     r8, [rbp+arg_10]; struct IEnumSyncChanges **
0x180036a1d  xor     r9d, r9d; struct ISyncKnowledge *
0x180036a20  mov     [rsp+30h+var_10], 0; struct IForgottenKnowledge *
0x180036a29  lea     rdx, [rbp+arg_8]; struct ISyncChangeBatchBase **
0x180036a2d  mov     rcx, rdi; this
0x180036a30  call    ?ApplyOneChangeBatchHelper@CChangeApplier@@AEAAJPEAPEAUISyncChangeBatchBase@@PEAPEAUIEnumSyncChanges@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAH@Z; CChangeApplier::ApplyOneChangeBatchHelper(ISyncChangeBatchBase * *,IEnumSyncChanges * *,ISyncKnowledge *,IForgottenKnowledge *,int *)
0x180036a35  xor     r15d, r15d
0x180036a38  test    eax, eax
0x180036a3a  jns     loc_180036B9E
0x180036a40  mov     r15d, r13d
0x180036a43  mov     [rdi+118h], eax
0x180036a49  mov     esi, r13d
0x180036a4c  jmp     short loc_180036A57
0x180036a4e  test    r15d, r15d
0x180036a51  jz      loc_180036B9E
0x180036a57  mov     r12d, [rdi+5Ch]
0x180036a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a62  lea     rax, WPP_GLOBAL_Control
0x180036a69  cmp     rcx, rax
0x180036a6c  jz      short loc_180036A8F
0x180036a6e  test    byte ptr [rcx+1Ch], 8
0x180036a72  jz      short loc_180036A8F
0x180036a74  cmp     byte ptr [rcx+19h], 5
0x180036a78  jb      short loc_180036A8F
0x180036a7a  mov     rcx, [rcx+10h]
0x180036a7e  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180036a85  mov     edx, 5Eh ; '^'
0x180036a8a  call    WPP_SF_
0x180036a8f  cmp     dword ptr [rdi+60h], 0
0x180036a93  jnz     loc_180036B1C
0x180036a99  test    esi, esi
0x180036a9b  jz      short loc_180036AA6
0x180036a9d  cmp     dword ptr [rdi+2A8h], 0
0x180036aa4  jz      short loc_180036B1C
0x180036aa6  mov     rcx, [rdi+80h]
0x180036aad  lea     r8, [rdi+10h]
0x180036ab1  mov     [rdi+60h], r13d
0x180036ab5  mov     rax, rdi
0x180036ab8  neg     rax
0x180036abb  mov     r9, [rcx]
0x180036abe  sbb     rdx, rdx
0x180036ac1  and     rdx, r8
0x180036ac4  mov     rax, [r9+30h]
0x180036ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036acd  mov     rcx, [rdi+90h]
0x180036ad4  lea     rdx, [rdi+18h]
0x180036ad8  mov     rax, rdi
0x180036adb  neg     rax
0x180036ade  mov     rax, [rcx]
0x180036ae1  sbb     r14, r14
0x180036ae4  and     r14, rdx
0x180036ae7  mov     rdx, r14
0x180036aea  mov     rax, [rax+28h]
0x180036aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036af3  cmp     dword ptr [rdi+258h], 0
0x180036afa  jz      short loc_180036B1C
0x180036afc  mov     rcx, [rdi+268h]
0x180036b03  mov     rdx, r14
0x180036b06  mov     dword ptr [rdi+258h], 0
0x180036b10  mov     rax, [rcx]
0x180036b13  mov     rax, [rax+28h]
0x180036b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b1c  mov     rcx, [rdi+160h]; hEvent
0x180036b23  call    cs:__imp_SetEvent
0x180036b29  test    r12d, r12d
0x180036b2c  jz      short loc_180036B9E
0x180036b2e  mov     r14, [rdi+80h]
0x180036b35  mov     rcx, r14
0x180036b38  mov     rax, [r14]
0x180036b3b  mov     rax, [rax+8]
0x180036b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b44  mov     rcx, rdi; this
0x180036b47  call    ?ResetChangeApplierState@CChangeApplier@@AEAAXXZ; CChangeApplier::ResetChangeApplierState(void)
0x180036b4c  test    esi, esi
0x180036b4e  jz      short loc_180036B79
0x180036b50  mov     ecx, [rdi+118h]; dwMessageId
0x180036b56  lea     rdx, IID_IAsynchronousNotifyingChangeApplier; struct _GUID *
0x180036b5d  call    ?SetErrorInfoHelper@@YAXJAEBU_GUID@@0@Z; SetErrorInfoHelper(long,_GUID const &,_GUID const &)
0x180036b62  mov     rax, [r14]
0x180036b65  mov     rcx, r14
0x180036b68  mov     edx, [rdi+118h]
0x180036b6e  mov     rax, [rax+70h]
0x180036b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b77  jmp     short loc_180036B88
0x180036b79  mov     rax, [r14]
0x180036b7c  mov     rcx, r14
0x180036b7f  mov     rax, [rax+68h]
0x180036b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b88  mov     rax, [r14]
0x180036b8b  mov     rcx, r14
0x180036b8e  mov     rax, [rax+10h]
0x180036b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b97  lock dec cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x180036b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ba5  lea     rax, WPP_GLOBAL_Control
0x180036bac  cmp     rcx, rax
0x180036baf  jz      short loc_180036BDE
0x180036bb1  test    byte ptr [rcx+1Ch], 8
0x180036bb5  jz      short loc_180036BDE
0x180036bb7  cmp     byte ptr [rcx+19h], 5
0x180036bbb  jb      short loc_180036BDE
0x180036bbd  mov     rcx, [rcx+10h]
0x180036bc1  lea     r9, aCchangeapplier_58; "CChangeApplier::CheckForSessionCompleti"...
0x180036bc8  mov     edx, 5Fh ; '_'
0x180036bcd  mov     dword ptr [rsp+30h+var_10], r15d
0x180036bd2  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180036bd9  call    WPP_SF_sD
0x180036bde  mov     eax, r15d
0x180036be1  add     rsp, 30h
0x180036be5  pop     r15
0x180036be7  pop     r14
0x180036be9  pop     r13
0x180036beb  pop     r12
0x180036bed  pop     rdi
0x180036bee  pop     rsi
0x180036bef  pop     rbp
0x180036bf0  retn
```
