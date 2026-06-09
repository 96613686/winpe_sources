# CInterceptor_IWbemSyncProvider::InternalEx_CancelQuery(bool,ulong)

- ea: `0x14001c138`
- end: `0x14001c3e0`
- name: `?InternalEx_CancelQuery@CInterceptor_IWbemSyncProvider@@AEAAJ_NK@Z`
- size: `680`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, bool, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c0d0`
- `0x140039370`

## callees

- `0x1400054a0`
- `0x140006c64`
- `0x14001c138`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c1b3`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c2ef`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c1b3`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001c2ef`
- `wbemcomn!GetMemLogObject` at `0x14001c32e`
- `wbemcomn!GetMemLogObject` at `0x14001c39e`
- `wbemcomn!GetMemLogObject` at `0x14001c32e`
- `wbemcomn!GetMemLogObject` at `0x14001c39e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c33e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c3a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c33e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001c3a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c287`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001c287`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_CancelQuery(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        unsigned int a3)
{
  struct IUnknown *v6; // r8
  int v7; // edi
  struct IUnknown *v8; // rcx
  int v9; // eax
  struct IUnknown *v10; // r14
  struct IServerSecurity *v11; // r15
  struct IUnknown *v12; // r12
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax
  int v16; // [rsp+68h] [rbp+7h] BYREF
  struct IUnknown *v17; // [rsp+70h] [rbp+Fh] BYREF
  struct IUnknown *v18; // [rsp+78h] [rbp+17h] BYREF
  struct IServerSecurity *v19; // [rsp+80h] [rbp+1Fh] BYREF
  struct IUnknown *v20; // [rsp+88h] [rbp+27h] BYREF
  int v21; // [rsp+C8h] [rbp+67h] BYREF
  int v22; // [rsp+E0h] [rbp+7Fh] BYREF

  if ( *((_QWORD *)this + 45) )
  {
    WmiSetAndCommitObject(
      qword_1400613F8,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a3);
    v6 = (struct IUnknown *)*((_QWORD *)this + 45);
    v22 = 0;
    v20 = 0;
    v19 = 0;
    v17 = 0;
    v21 = 0;
    v18 = 0;
    v7 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
           this,
           a2,
           v6,
           &IID_IWbemEventProviderQuerySink,
           4u,
           &v22,
           &v20,
           &v19,
           &v16,
           &v17,
           &v21,
           &v18);
    if ( v7 >= 0 )
    {
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 36);
      v8 = v17;
      ++*((_QWORD *)this + 104);
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v8->lpVtbl[1].AddRef)(v8, a3);
      v10 = v18;
      v7 = v9;
      v11 = v19;
      v12 = v20;
      CoRevertToSelf();
      if ( v10 )
        ProviderSubSystem_Common_Globals::RevertProxyState(
          (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
          4u,
          v10,
          v21);
      ProviderSubSystem_Common_Globals::EndImpersonation(v12, v11, v22);
    }
    WmiSetAndCommitObject(
      qword_140061468,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      a3);
    if ( v7 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v7);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
        (unsigned int)v7);
    }
    return (unsigned int)v7;
  }
  else
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2147217372);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749924LL);
    }
    return 2147749924LL;
  }
}

```

## disassembly

```asm
0x14001c138  mov     rax, rsp
0x14001c13b  mov     [rax+10h], rbx
0x14001c13f  mov     [rax+18h], rsi
0x14001c143  push    rbp
0x14001c144  push    rdi
0x14001c145  push    r12
0x14001c147  push    r14
0x14001c149  push    r15
0x14001c14b  lea     rbp, [rax-5Fh]
0x14001c14f  sub     rsp, 90h
0x14001c156  cmp     qword ptr [rcx+168h], 0
0x14001c15e  mov     esi, r8d
0x14001c161  mov     dil, dl
0x14001c164  mov     rbx, rcx
0x14001c167  jz      loc_14001C32E
0x14001c16d  mov     r9, [rcx+258h]
0x14001c174  mov     edx, 1
0x14001c179  mov     [rax-80h], r8d
0x14001c17d  mov     rax, [rcx+278h]
0x14001c184  mov     r8, [rcx+270h]
0x14001c18b  mov     r9, [r9+40h]
0x14001c18f  mov     [rsp+0B0h+var_80], rax
0x14001c194  mov     rax, [rcx+260h]
0x14001c19b  mov     [rsp+0B0h+var_88], rax
0x14001c1a0  mov     rax, [rcx+268h]
0x14001c1a7  mov     rcx, cs:qword_1400613F8
0x14001c1ae  mov     qword ptr [rsp+0B0h+var_90], rax
0x14001c1b3  call    cs:__imp_WmiSetAndCommitObject
0x14001c1b9  mov     r8, [rbx+168h]; struct IUnknown *
0x14001c1c0  lea     rax, [rbp+57h+var_40]
0x14001c1c4  mov     [rsp+0B0h+var_58], rax; struct IUnknown **
0x14001c1c9  lea     r9, IID_IWbemEventProviderQuerySink; struct _GUID *
0x14001c1d0  lea     rax, [rbp+57h+arg_0]
0x14001c1d4  mov     [rbp+57h+arg_18], 0
0x14001c1db  mov     [rsp+0B0h+var_60], rax; int *
0x14001c1e0  mov     dl, dil; bool
0x14001c1e3  lea     rax, [rbp+57h+var_48]
0x14001c1e7  mov     [rbp+57h+var_30], 0
0x14001c1ef  mov     [rsp+0B0h+var_68], rax; struct IUnknown **
0x14001c1f4  mov     rcx, rbx; this
0x14001c1f7  lea     rax, [rbp+57h+var_50]
0x14001c1fb  mov     [rbp+57h+var_38], 0
0x14001c203  mov     [rsp+0B0h+var_70], rax; int *
0x14001c208  lea     rax, [rbp+57h+var_38]
0x14001c20c  mov     [rsp+0B0h+var_78], rax; struct IServerSecurity **
0x14001c211  lea     rax, [rbp+57h+var_30]
0x14001c215  mov     [rsp+0B0h+var_80], rax; struct IUnknown **
0x14001c21a  lea     rax, [rbp+57h+arg_18]
0x14001c21e  mov     [rsp+0B0h+var_88], rax; int *
0x14001c223  mov     [rsp+0B0h+var_90], 4; unsigned int
0x14001c22b  mov     [rbp+57h+var_48], 0
0x14001c233  mov     [rbp+57h+arg_0], 0
0x14001c23a  mov     [rbp+57h+var_40], 0
0x14001c242  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001c247  mov     edi, eax
0x14001c249  test    eax, eax
0x14001c24b  js      short loc_14001C2A5
0x14001c24d  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14001c254  test    rax, rax
0x14001c257  jz      short loc_14001C260
0x14001c259  inc     qword ptr [rax+120h]
0x14001c260  mov     rcx, [rbp+57h+var_48]
0x14001c264  mov     edx, esi
0x14001c266  inc     qword ptr [rbx+340h]
0x14001c26d  mov     rax, [rcx]
0x14001c270  mov     rax, [rax+20h]
0x14001c274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c279  mov     r14, [rbp+57h+var_40]
0x14001c27d  mov     edi, eax
0x14001c27f  mov     r15, [rbp+57h+var_38]
0x14001c283  mov     r12, [rbp+57h+var_30]
0x14001c287  call    cs:__imp_CoRevertToSelf
0x14001c28d  test    r14, r14
0x14001c290  jnz     loc_14001C381
0x14001c296  mov     r8d, [rbp+57h+arg_18]; int
0x14001c29a  mov     rdx, r15; struct IServerSecurity *
0x14001c29d  mov     rcx, r12; struct IUnknown *
0x14001c2a0  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001c2a5  mov     rax, [rbx+278h]
0x14001c2ac  mov     edx, 1
0x14001c2b1  mov     r9, [rbx+258h]
0x14001c2b8  mov     r8, [rbx+270h]
0x14001c2bf  mov     rcx, cs:qword_140061468
0x14001c2c6  mov     dword ptr [rsp+0B0h+var_70], edi
0x14001c2ca  mov     r9, [r9+40h]
0x14001c2ce  mov     dword ptr [rsp+0B0h+var_78], esi
0x14001c2d2  mov     [rsp+0B0h+var_80], rax
0x14001c2d7  mov     rax, [rbx+260h]
0x14001c2de  mov     [rsp+0B0h+var_88], rax
0x14001c2e3  mov     rax, [rbx+268h]
0x14001c2ea  mov     qword ptr [rsp+0B0h+var_90], rax
0x14001c2ef  call    cs:__imp_WmiSetAndCommitObject
0x14001c2f5  test    edi, edi
0x14001c2f7  js      loc_14001C39E
0x14001c2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c304  lea     rax, WPP_GLOBAL_Control
0x14001c30b  cmp     rcx, rax
0x14001c30e  jnz     short loc_14001C35B
0x14001c310  mov     eax, edi
0x14001c312  lea     r11, [rsp+0B0h+var_20]
0x14001c31a  mov     rbx, [r11+38h]
0x14001c31e  mov     rsi, [r11+40h]
0x14001c322  mov     rsp, r11
0x14001c325  pop     r15
0x14001c327  pop     r14
0x14001c329  pop     r12
0x14001c32b  pop     rdi
0x14001c32c  pop     rbp
0x14001c32d  retn
0x14001c32e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001c334  mov     ebx, 80041024h
0x14001c339  mov     rcx, rax
0x14001c33c  mov     edx, ebx
0x14001c33e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001c344  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c34b  lea     rax, WPP_GLOBAL_Control
0x14001c352  cmp     rcx, rax
0x14001c355  jnz     short loc_14001C3B4
0x14001c357  mov     eax, ebx
0x14001c359  jmp     short loc_14001C312
0x14001c35b  test    byte ptr [rcx+1Ch], 4
0x14001c35f  jz      short loc_14001C310
0x14001c361  cmp     byte ptr [rcx+19h], 2
0x14001c365  jb      short loc_14001C310
0x14001c367  mov     rcx, [rcx+10h]
0x14001c36b  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001c372  mov     edx, 8Dh
0x14001c377  mov     r9d, edi
0x14001c37a  call    WPP_SF_d
0x14001c37f  jmp     short loc_14001C310
0x14001c381  mov     r9d, [rbp+57h+arg_0]; int
0x14001c385  lea     rcx, [rbx+1B8h]; struct ProxyContainer *
0x14001c38c  mov     r8, r14; struct IUnknown *
0x14001c38f  mov     edx, 4; unsigned int
0x14001c394  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001c399  jmp     loc_14001C296
0x14001c39e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001c3a4  mov     rcx, rax
0x14001c3a7  mov     edx, edi
0x14001c3a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001c3af  jmp     loc_14001C2FD
0x14001c3b4  test    byte ptr [rcx+1Ch], 4
0x14001c3b8  jz      short loc_14001C357
0x14001c3ba  cmp     byte ptr [rcx+19h], 2
0x14001c3be  jb      short loc_14001C357
0x14001c3c0  mov     rcx, [rcx+10h]
0x14001c3c4  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001c3cb  mov     edx, 8Eh
0x14001c3d0  mov     r9d, 80041024h
0x14001c3d6  call    WPP_SF_d
0x14001c3db  jmp     loc_14001C357
```
