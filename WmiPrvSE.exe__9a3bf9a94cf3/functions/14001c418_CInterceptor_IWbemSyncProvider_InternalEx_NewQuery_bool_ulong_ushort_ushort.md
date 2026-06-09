# CInterceptor_IWbemSyncProvider::InternalEx_NewQuery(bool,ulong,ushort *,ushort *)

- ea: `0x14001c418`
- end: `0x14001c6d2`
- name: `?InternalEx_NewQuery@CInterceptor_IWbemSyncProvider@@AEAAJ_NKPEAG1@Z`
- size: `698`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, bool@<dl>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c3f0`
- `0x14003a750`

## callees

- `0x1400054a0`
- `0x140006c64`
- `0x14001c418`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c4a1`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c57e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c4a1`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c57e`
- `wbemcomn!GetMemLogObject` at `0x14001c63e`
- `wbemcomn!GetMemLogObject` at `0x14001c67b`
- `wbemcomn!GetMemLogObject` at `0x14001c63e`
- `wbemcomn!GetMemLogObject` at `0x14001c67b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c649`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c68b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c649`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c68b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c604`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c604`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_NewQuery(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v9; // r12
  struct IUnknown *v10; // r8
  int v11; // edi
  struct IUnknown *v13; // rcx
  int v14; // eax
  struct IUnknown *v15; // r15
  struct IServerSecurity *v16; // r13
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  int v19; // [rsp+60h] [rbp-21h] BYREF
  int v20; // [rsp+64h] [rbp-1Dh] BYREF
  struct IUnknown *v21; // [rsp+68h] [rbp-19h] BYREF
  struct IUnknown *v22; // [rsp+70h] [rbp-11h] BYREF
  struct IServerSecurity *v23; // [rsp+78h] [rbp-9h] BYREF
  struct IUnknown *v24; // [rsp+80h] [rbp-1h] BYREF
  int v25; // [rsp+E0h] [rbp+5Fh] BYREF

  if ( *((_QWORD *)this + 45) )
  {
    v9 = a5;
    WmiSetAndCommitObject(
      qword_140061400,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a3);
    v10 = (struct IUnknown *)*((_QWORD *)this + 45);
    v19 = 0;
    v24 = 0;
    v23 = 0;
    v21 = 0;
    v25 = 0;
    v22 = 0;
    v11 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
            this,
            a2,
            v10,
            &IID_IWbemEventProviderQuerySink,
            4u,
            &v19,
            &v24,
            &v23,
            &v20,
            &v21,
            &v25,
            &v22);
    if ( v11 >= 0 )
    {
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 35);
      v13 = v21;
      ++*((_QWORD *)this + 103);
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, unsigned __int16 *, unsigned __int16 *))v13->lpVtbl[1].QueryInterface)(
              v13,
              a3,
              a4,
              v9);
      v15 = v22;
      v11 = v14;
      v16 = v23;
      v21 = v24;
      CoRevertToSelf();
      if ( v15 )
        ProviderSubSystem_Common_Globals::RevertProxyState(
          (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
          4u,
          v15,
          v25);
      ProviderSubSystem_Common_Globals::EndImpersonation(v21, v16, v19);
    }
    WmiSetAndCommitObject(
      qword_140061470,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a3);
    if ( v11 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v11);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v11);
    }
    return (unsigned int)v11;
  }
  else
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217372);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749924LL);
    }
    return 2147749924LL;
  }
}

```

## disassembly

```asm
0x14001c418  push    rbp
0x14001c41a  push    rbx
0x14001c41b  push    rsi
0x14001c41c  push    rdi
0x14001c41d  push    r12
0x14001c41f  push    r13
0x14001c421  push    r14
0x14001c423  push    r15
0x14001c425  lea     rbp, [rsp-17h]
0x14001c42a  sub     rsp, 98h
0x14001c431  xor     r15d, r15d
0x14001c434  mov     rsi, r9
0x14001c437  mov     r14d, r8d
0x14001c43a  mov     dil, dl
0x14001c43d  mov     rbx, rcx
0x14001c440  cmp     [rcx+168h], r15
0x14001c447  jz      loc_14001C67B
0x14001c44d  mov     rax, [rcx+278h]
0x14001c454  lea     edx, [r15+1]
0x14001c458  mov     r9, [rcx+258h]
0x14001c45f  mov     r12, [rbp+4Fh+arg_20]
0x14001c463  mov     [rsp+0D0h+var_88], r12
0x14001c468  mov     [rsp+0D0h+var_90], rsi
0x14001c46d  mov     r9, [r9+40h]
0x14001c471  mov     dword ptr [rsp+0D0h+var_98], r8d
0x14001c476  mov     r8, [rcx+270h]
0x14001c47d  mov     [rsp+0D0h+var_A0], rax
0x14001c482  mov     rax, [rcx+260h]
0x14001c489  mov     [rsp+0D0h+var_A8], rax
0x14001c48e  mov     rax, [rcx+268h]
0x14001c495  mov     rcx, cs:qword_140061400
0x14001c49c  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14001c4a1  call    cs:__imp_WmiSetAndCommitObject
0x14001c4a7  mov     r8, [rbx+168h]; struct IUnknown *
0x14001c4ae  lea     rax, [rbp+4Fh+var_60]
0x14001c4b2  mov     [rsp+0D0h+var_78], rax; struct IUnknown **
0x14001c4b7  lea     r9, IID_IWbemEventProviderQuerySink; struct _GUID *
0x14001c4be  lea     rax, [rbp+4Fh+arg_0]
0x14001c4c2  mov     [rbp+4Fh+var_70], r15d
0x14001c4c6  mov     [rsp+0D0h+var_80], rax; int *
0x14001c4cb  mov     dl, dil; bool
0x14001c4ce  lea     rax, [rbp+4Fh+var_68]
0x14001c4d2  mov     [rbp+4Fh+var_50], r15
0x14001c4d6  mov     [rsp+0D0h+var_88], rax; struct IUnknown **
0x14001c4db  mov     rcx, rbx; this
0x14001c4de  lea     rax, [rbp+4Fh+var_6C]
0x14001c4e2  mov     [rbp+4Fh+var_58], r15
0x14001c4e6  mov     [rsp+0D0h+var_90], rax; int *
0x14001c4eb  lea     rax, [rbp+4Fh+var_58]
0x14001c4ef  mov     [rsp+0D0h+var_98], rax; struct IServerSecurity **
0x14001c4f4  lea     rax, [rbp+4Fh+var_50]
0x14001c4f8  mov     [rsp+0D0h+var_A0], rax; struct IUnknown **
0x14001c4fd  lea     rax, [rbp+4Fh+var_70]
0x14001c501  mov     [rsp+0D0h+var_A8], rax; int *
0x14001c506  mov     [rsp+0D0h+var_B0], 4; unsigned int
0x14001c50e  mov     [rbp+4Fh+var_68], r15
0x14001c512  mov     [rbp+4Fh+arg_0], r15d
0x14001c516  mov     [rbp+4Fh+var_60], r15
0x14001c51a  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001c51f  mov     edi, eax
0x14001c521  test    eax, eax
0x14001c523  jns     loc_14001C5BF
0x14001c529  mov     rax, [rbx+278h]
0x14001c530  mov     edx, 1
0x14001c535  mov     r9, [rbx+258h]
0x14001c53c  mov     r8, [rbx+270h]
0x14001c543  mov     rcx, cs:qword_140061470
0x14001c54a  mov     dword ptr [rsp+0D0h+var_80], edi
0x14001c54e  mov     r9, [r9+40h]
0x14001c552  mov     [rsp+0D0h+var_88], r12
0x14001c557  mov     [rsp+0D0h+var_90], rsi
0x14001c55c  mov     dword ptr [rsp+0D0h+var_98], r14d
0x14001c561  mov     [rsp+0D0h+var_A0], rax
0x14001c566  mov     rax, [rbx+260h]
0x14001c56d  mov     [rsp+0D0h+var_A8], rax
0x14001c572  mov     rax, [rbx+268h]
0x14001c579  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14001c57e  call    cs:__imp_WmiSetAndCommitObject
0x14001c584  test    edi, edi
0x14001c586  js      loc_14001C63E
0x14001c58c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c593  lea     rax, WPP_GLOBAL_Control
0x14001c59a  cmp     rcx, rax
0x14001c59d  jz      short loc_14001C5A9
0x14001c59f  test    byte ptr [rcx+1Ch], 4
0x14001c5a3  jnz     loc_14001C654
0x14001c5a9  mov     eax, edi
0x14001c5ab  add     rsp, 98h
0x14001c5b2  pop     r15
0x14001c5b4  pop     r14
0x14001c5b6  pop     r13
0x14001c5b8  pop     r12
0x14001c5ba  pop     rdi
0x14001c5bb  pop     rsi
0x14001c5bc  pop     rbx
0x14001c5bd  pop     rbp
0x14001c5be  retn
0x14001c5bf  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14001c5c6  test    rax, rax
0x14001c5c9  jz      short loc_14001C5D2
0x14001c5cb  inc     qword ptr [rax+118h]
0x14001c5d2  mov     rcx, [rbp+4Fh+var_68]
0x14001c5d6  mov     r9, r12
0x14001c5d9  inc     qword ptr [rbx+338h]
0x14001c5e0  mov     r8, rsi
0x14001c5e3  mov     edx, r14d
0x14001c5e6  mov     rax, [rcx]
0x14001c5e9  mov     rax, [rax+18h]
0x14001c5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c5f2  mov     r15, [rbp+4Fh+var_60]
0x14001c5f6  mov     edi, eax
0x14001c5f8  mov     rax, [rbp+4Fh+var_50]
0x14001c5fc  mov     r13, [rbp+4Fh+var_58]
0x14001c600  mov     [rbp+4Fh+var_68], rax
0x14001c604  call    cs:__imp_CoRevertToSelf
0x14001c60a  test    r15, r15
0x14001c60d  jnz     short loc_14001C624
0x14001c60f  mov     r8d, [rbp+4Fh+var_70]; int
0x14001c613  mov     rdx, r13; struct IServerSecurity *
0x14001c616  mov     rcx, [rbp+4Fh+var_68]; struct IUnknown *
0x14001c61a  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001c61f  jmp     loc_14001C529
0x14001c624  mov     r9d, [rbp+4Fh+arg_0]; int
0x14001c628  lea     rcx, [rbx+1B8h]; struct ProxyContainer *
0x14001c62f  mov     r8, r15; struct IUnknown *
0x14001c632  mov     edx, 4; unsigned int
0x14001c637  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001c63c  jmp     short loc_14001C60F
0x14001c63e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001c644  mov     rcx, rax
0x14001c647  mov     edx, edi
0x14001c649  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001c64f  jmp     loc_14001C58C
0x14001c654  cmp     byte ptr [rcx+19h], 2
0x14001c658  jb      loc_14001C5A9
0x14001c65e  mov     rcx, [rcx+10h]
0x14001c662  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001c669  mov     edx, 8Bh
0x14001c66e  mov     r9d, edi
0x14001c671  call    WPP_SF_d
0x14001c676  jmp     loc_14001C5A9
0x14001c67b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001c681  mov     ebx, 80041024h
0x14001c686  mov     rcx, rax
0x14001c689  mov     edx, ebx
0x14001c68b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001c691  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c698  lea     rax, WPP_GLOBAL_Control
0x14001c69f  cmp     rcx, rax
0x14001c6a2  jz      short loc_14001C6CB
0x14001c6a4  test    byte ptr [rcx+1Ch], 4
0x14001c6a8  jz      short loc_14001C6CB
0x14001c6aa  cmp     byte ptr [rcx+19h], 2
0x14001c6ae  jb      short loc_14001C6CB
0x14001c6b0  mov     rcx, [rcx+10h]
0x14001c6b4  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001c6bb  mov     edx, 8Ch
0x14001c6c0  mov     r9d, 80041024h
0x14001c6c6  call    WPP_SF_d
0x14001c6cb  mov     eax, ebx
0x14001c6cd  jmp     loc_14001C5AB
```
