# CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem(CSyncChangeWrapper *,ISyncKnowledge *,ISyncKnowledge *)

- ea: `0x18006a890`
- end: `0x18006ab9f`
- name: `?HandleNewMoveInOfCreationVersionKnownItem@CSyncChangeWrapper@@QEAAJPEAV1@PEAUISyncKnowledge@@1@Z`
- size: `783`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct CSyncChangeWrapper *, struct ISyncKnowledge *, struct ISyncKnowledge *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800383f4`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180066f20`
- `0x18006a890`
- `0x18006cc00`
- `0x1800709c0`
- `0x180071b20`
- `0x180071f70`
- `0x180072974`
- `0x180094010`

## string_xrefs

- `0x18006a8e0`: `CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem`
- `0x18006ab69`: `CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem(
        CSyncChangeWrapper *this,
        struct CSyncChangeWrapper *a2,
        struct ISyncKnowledge *a3,
        struct ISyncKnowledge *a4)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v9; // ebx
  int v10; // r14d
  int v11; // r13d
  __int64 v12; // rcx
  CSyncChangeWrapper *v13; // rsi
  unsigned int v14; // r15d
  unsigned int v15; // edx
  unsigned int *v16; // r9
  CEnumSyncChangeUnitWrappers *v17; // rcx
  unsigned __int8 *v18; // r12
  unsigned int v19; // eax
  CSyncChangeUnitWrapper *v20; // rbx
  unsigned int v21; // esi
  unsigned int v22; // eax
  __int64 v23; // rdx
  int v25; // [rsp+30h] [rbp-20h]
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v27; // [rsp+40h] [rbp-10h] BYREF
  CSyncChangeUnitWrapper *v28; // [rsp+48h] [rbp-8h] BYREF
  int v29; // [rsp+90h] [rbp+40h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem");
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 41);
  v26 = 0;
  v9 = (**v8)(v8, &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8, &v26);
  if ( v9 )
    goto LABEL_41;
  v10 = 1;
  v11 = 1;
  v25 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, _QWORD))(*(_QWORD *)v26 + 272LL))(
         v26,
         a3,
         *((_QWORD *)this + 20));
  if ( v9 == 1
    && (v10 = 0,
        v9 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, _QWORD))(*(_QWORD *)v26 + 272LL))(
               v26,
               a4,
               *((_QWORD *)this + 20)),
        v9 == 1) )
  {
    v11 = 0;
    v25 = 0;
  }
  else if ( v9 )
  {
    goto LABEL_41;
  }
  v12 = *((_QWORD *)this + 25);
  if ( !v12 )
  {
    if ( v10 )
    {
      v13 = this;
      v14 = 3;
    }
    else
    {
      if ( !v11 )
      {
        v9 = CSyncChangeWrapper::SetConflict(this, a2, 0, 0);
        if ( !v9 )
        {
          v13 = this;
          goto LABEL_38;
        }
        goto LABEL_41;
      }
      v13 = this;
      v14 = 524291;
    }
LABEL_39:
    v9 = CSyncChangeWrapper::AddTransferFilter(v13, v14);
    if ( !v9 )
      *((_DWORD *)this + 62) |= 2u;
    goto LABEL_41;
  }
  v29 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
  do
  {
    v17 = (CEnumSyncChangeUnitWrappers *)*((_QWORD *)this + 25);
    v18 = 0;
    v27 = 0;
    v28 = 0;
    v19 = CEnumSyncChangeUnitWrappers::Next(v17, v15, &v28, v16);
    v20 = v28;
    v21 = v19;
    if ( !v19 )
    {
      v22 = CSyncChangeUnitWrapper::GetChangeUnitIdInternal(v28, &v27);
      v18 = v27;
      v21 = v22;
      if ( !v22 )
      {
        if ( v11 )
          goto LABEL_26;
        v21 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, _QWORD, unsigned __int8 *))(*(_QWORD *)v26 + 280LL))(
                v26,
                a4,
                *((_QWORD *)this + 20),
                v27);
        if ( v21 == 1 )
        {
          ++v29;
          v21 = CSyncChangeUnitWrapper::SetConflict(v20);
          if ( v21 )
            goto LABEL_29;
          v11 = 1;
          v21 = CSyncChangeUnitWrapper::AddTransferFilter(v20, 0x80000);
        }
        if ( !v21 && !v11 )
        {
LABEL_26:
          v23 = 3;
          if ( !v10 )
            v23 = 524291;
          v21 = CSyncChangeUnitWrapper::AddTransferFilter(v20, v23);
        }
      }
    }
LABEL_29:
    if ( v20 )
      (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v20 + 16LL))(v20);
    IdParameters::FreeId(v18);
    v11 = v25;
  }
  while ( !v21 );
  v9 = 0;
  if ( v21 != 1 )
    v9 = v21;
  if ( !v9 )
  {
    v13 = this;
    if ( !v29 )
    {
      v14 = ((v10 ^ 1) << 19) + 3;
      goto LABEL_39;
    }
    v9 = CSyncChangeWrapper::SetConflict(this, a2, 0, 0);
    if ( !v9 )
    {
LABEL_38:
      v14 = 0x80000;
      goto LABEL_39;
    }
  }
LABEL_41:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::HandleNewMoveInOfCreationVersionKnownItem",
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18006a890  mov     [rsp-38h+arg_10], rbx
0x18006a895  mov     [rsp-38h+arg_18], r9
0x18006a89a  mov     [rsp-38h+arg_8], rdx
0x18006a89f  push    rbp
0x18006a8a0  push    rsi
0x18006a8a1  push    rdi
0x18006a8a2  push    r12
0x18006a8a4  push    r13
0x18006a8a6  push    r14
0x18006a8a8  push    r15
0x18006a8aa  mov     rbp, rsp
0x18006a8ad  sub     rsp, 50h
0x18006a8b1  mov     r12, r9
0x18006a8b4  mov     rsi, r8
0x18006a8b7  mov     r15, rdx
0x18006a8ba  mov     rdi, rcx
0x18006a8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a8c4  lea     r14, WPP_GLOBAL_Control
0x18006a8cb  cmp     rcx, r14
0x18006a8ce  jz      short loc_18006A8F8
0x18006a8d0  test    byte ptr [rcx+1Ch], 8
0x18006a8d4  jz      short loc_18006A8F8
0x18006a8d6  cmp     byte ptr [rcx+19h], 5
0x18006a8da  jb      short loc_18006A8F8
0x18006a8dc  mov     rcx, [rcx+10h]
0x18006a8e0  lea     r9, aCsyncchangewra_6; "CSyncChangeWrapper::HandleNewMoveInOfCr"...
0x18006a8e7  mov     edx, 23h ; '#'
0x18006a8ec  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006a8f3  call    WPP_SF_s
0x18006a8f8  mov     rcx, [rdi+148h]
0x18006a8ff  lea     r8, [rbp+var_18]
0x18006a903  mov     [rbp+var_18], 0
0x18006a90b  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x18006a912  mov     rax, [rcx]
0x18006a915  mov     rax, [rax]
0x18006a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a91d  mov     ebx, eax
0x18006a91f  test    eax, eax
0x18006a921  jnz     loc_18006AB38
0x18006a927  mov     rcx, [rbp+var_18]
0x18006a92b  lea     eax, [rbx+1]
0x18006a92e  mov     r8, [rdi+0A0h]
0x18006a935  mov     r14d, eax
0x18006a938  mov     r13d, eax
0x18006a93b  mov     [rbp+var_20], eax
0x18006a93e  mov     rdx, rsi
0x18006a941  mov     rax, [rcx]
0x18006a944  mov     rax, [rax+110h]
0x18006a94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a950  mov     ebx, eax
0x18006a952  cmp     eax, r13d
0x18006a955  jnz     short loc_18006A987
0x18006a957  mov     rcx, [rbp+var_18]
0x18006a95b  mov     rdx, r12
0x18006a95e  mov     r8, [rdi+0A0h]
0x18006a965  xor     r14d, r14d
0x18006a968  mov     rax, [rcx]
0x18006a96b  mov     rax, [rax+110h]
0x18006a972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a977  mov     ebx, eax
0x18006a979  cmp     eax, r13d
0x18006a97c  jnz     short loc_18006A987
0x18006a97e  xor     r13d, r13d
0x18006a981  mov     [rbp+var_20], r13d
0x18006a985  jmp     short loc_18006A98F
0x18006a987  test    ebx, ebx
0x18006a989  jnz     loc_18006AB31
0x18006a98f  mov     rcx, [rdi+0C8h]
0x18006a996  test    rcx, rcx
0x18006a999  jnz     short loc_18006A9E2
0x18006a99b  test    r14d, r14d
0x18006a99e  jz      short loc_18006A9AC
0x18006a9a0  mov     rsi, rdi
0x18006a9a3  lea     r15d, [rcx+3]
0x18006a9a7  jmp     loc_18006AB10
0x18006a9ac  test    r13d, r13d
0x18006a9af  jz      short loc_18006A9BF
0x18006a9b1  mov     rsi, rdi
0x18006a9b4  mov     r15d, 80003h
0x18006a9ba  jmp     loc_18006AB10
0x18006a9bf  xor     r9d, r9d; int
0x18006a9c2  xor     r8d, r8d; struct CSyncChangeWrapper *
0x18006a9c5  mov     rdx, r15; struct CSyncChangeWrapper *
0x18006a9c8  mov     rcx, rdi; this
0x18006a9cb  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x18006a9d0  mov     ebx, eax
0x18006a9d2  test    eax, eax
0x18006a9d4  jnz     loc_18006AB31
0x18006a9da  mov     rsi, rdi
0x18006a9dd  jmp     loc_18006AB0A
0x18006a9e2  xor     eax, eax
0x18006a9e4  mov     [rbp+arg_0], eax
0x18006a9e7  mov     rax, [rcx]
0x18006a9ea  mov     rax, [rax+28h]
0x18006a9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9f3  mov     r15d, 3
0x18006a9f9  mov     rcx, [rdi+0C8h]; this
0x18006aa00  lea     r8, [rbp+var_8]; struct CSyncChangeUnitWrapper **
0x18006aa04  xor     r12d, r12d
0x18006aa07  mov     [rbp+var_10], r12
0x18006aa0b  mov     [rbp+var_8], r12
0x18006aa0f  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x18006aa14  mov     rbx, [rbp+var_8]
0x18006aa18  mov     esi, eax
0x18006aa1a  test    eax, eax
0x18006aa1c  jnz     loc_18006AAA9
0x18006aa22  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x18006aa26  mov     rcx, rbx; this
0x18006aa29  call    ?GetChangeUnitIdInternal@CSyncChangeUnitWrapper@@QEAAJPEAPEAE@Z; CSyncChangeUnitWrapper::GetChangeUnitIdInternal(uchar * *)
0x18006aa2e  mov     r12, [rbp+var_10]
0x18006aa32  mov     esi, eax
0x18006aa34  test    eax, eax
0x18006aa36  jnz     short loc_18006AAA9
0x18006aa38  test    r13d, r13d
0x18006aa3b  jnz     short loc_18006AA92
0x18006aa3d  mov     rcx, [rbp+var_18]
0x18006aa41  mov     r9, r12
0x18006aa44  mov     r8, [rdi+0A0h]
0x18006aa4b  mov     rdx, [rbp+arg_18]
0x18006aa4f  mov     rax, [rcx]
0x18006aa52  mov     rax, [rax+118h]
0x18006aa59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa5e  mov     esi, eax
0x18006aa60  cmp     eax, 1
0x18006aa63  jnz     short loc_18006AA89
0x18006aa65  inc     [rbp+arg_0]
0x18006aa68  mov     rcx, rbx; this
0x18006aa6b  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x18006aa70  mov     esi, eax
0x18006aa72  test    eax, eax
0x18006aa74  jnz     short loc_18006AAA9
0x18006aa76  mov     edx, 80000h
0x18006aa7b  lea     r13d, [rax+1]
0x18006aa7f  mov     rcx, rbx
0x18006aa82  call    ?AddTransferFilter@CSyncChangeUnitWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x18006aa87  mov     esi, eax
0x18006aa89  test    esi, esi
0x18006aa8b  jnz     short loc_18006AAA9
0x18006aa8d  test    r13d, r13d
0x18006aa90  jnz     short loc_18006AAA9
0x18006aa92  mov     rcx, rbx
0x18006aa95  mov     edx, r15d
0x18006aa98  test    r14d, r14d
0x18006aa9b  jnz     short loc_18006AAA2
0x18006aa9d  mov     edx, 80003h
0x18006aaa2  call    ?AddTransferFilter@CSyncChangeUnitWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x18006aaa7  mov     esi, eax
0x18006aaa9  test    rbx, rbx
0x18006aaac  jz      short loc_18006AABD
0x18006aaae  mov     rax, [rbx]
0x18006aab1  mov     rcx, rbx
0x18006aab4  mov     rax, [rax+10h]
0x18006aab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aabd  mov     rcx, r12; unsigned __int8 *
0x18006aac0  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18006aac5  mov     r13d, [rbp+var_20]
0x18006aac9  test    esi, esi
0x18006aacb  jz      loc_18006A9F9
0x18006aad1  xor     ebx, ebx
0x18006aad3  cmp     esi, 1
0x18006aad6  cmovnz  ebx, esi
0x18006aad9  test    ebx, ebx
0x18006aadb  jnz     short loc_18006AB31
0x18006aadd  mov     rsi, rdi
0x18006aae0  cmp     [rbp+arg_0], ebx
0x18006aae3  jnz     short loc_18006AAF2
0x18006aae5  xor     r14d, 1
0x18006aae9  shl     r14d, 13h
0x18006aaed  add     r15d, r14d
0x18006aaf0  jmp     short loc_18006AB10
0x18006aaf2  mov     rdx, [rbp+arg_8]; struct CSyncChangeWrapper *
0x18006aaf6  xor     r9d, r9d; int
0x18006aaf9  xor     r8d, r8d; struct CSyncChangeWrapper *
0x18006aafc  mov     rcx, rdi; this
0x18006aaff  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x18006ab04  mov     ebx, eax
0x18006ab06  test    eax, eax
0x18006ab08  jnz     short loc_18006AB31
0x18006ab0a  mov     r15d, 80000h
0x18006ab10  mov     edx, r15d
0x18006ab13  mov     rcx, rsi
0x18006ab16  call    ?AddTransferFilter@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x18006ab1b  lea     r14, WPP_GLOBAL_Control
0x18006ab22  mov     ebx, eax
0x18006ab24  test    eax, eax
0x18006ab26  jnz     short loc_18006AB38
0x18006ab28  or      dword ptr [rdi+0F8h], 2
0x18006ab2f  jmp     short loc_18006AB38
0x18006ab31  lea     r14, WPP_GLOBAL_Control
0x18006ab38  mov     rcx, [rbp+var_18]
0x18006ab3c  test    rcx, rcx
0x18006ab3f  jz      short loc_18006AB4D
0x18006ab41  mov     rax, [rcx]
0x18006ab44  mov     rax, [rax+10h]
0x18006ab48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab54  cmp     rcx, r14
0x18006ab57  jz      short loc_18006AB85
0x18006ab59  test    byte ptr [rcx+1Ch], 8
0x18006ab5d  jz      short loc_18006AB85
0x18006ab5f  cmp     byte ptr [rcx+19h], 5
0x18006ab63  jb      short loc_18006AB85
0x18006ab65  mov     rcx, [rcx+10h]
0x18006ab69  lea     r9, aCsyncchangewra_6; "CSyncChangeWrapper::HandleNewMoveInOfCr"...
0x18006ab70  mov     edx, 24h ; '$'
0x18006ab75  mov     [rsp+50h+var_30], ebx
0x18006ab79  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x18006ab80  call    WPP_SF_sD
0x18006ab85  mov     eax, ebx
0x18006ab87  mov     rbx, [rsp+50h+arg_10]
0x18006ab8f  add     rsp, 50h
0x18006ab93  pop     r15
0x18006ab95  pop     r14
0x18006ab97  pop     r13
0x18006ab99  pop     r12
0x18006ab9b  pop     rdi
0x18006ab9c  pop     rsi
0x18006ab9d  pop     rbp
0x18006ab9e  retn
```
