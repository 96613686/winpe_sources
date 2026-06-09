# CInterceptor_IWbemSyncProvider::Helper_PutInstanceAsync(int,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000b420`
- end: `0x14000b7ca`
- name: `?Helper_PutInstanceAsync@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, int, struct IWbemContextVtbl *, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140021dc0`

## callees

- `0x14000a530`
- `0x14000b420`
- `0x14000c190`
- `0x14000d1e0`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14000b57a`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000b57a`
- `wbemcomn!GetMemLogObject` at `0x14000b7b4`
- `wbemcomn!GetMemLogObject` at `0x14000b7b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000b7bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000b7bf`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000b743`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000b760`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000b743`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000b760`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b66e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b7a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b66e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000b7a9`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_PutInstanceAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        struct IWbemContextVtbl *a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  int v11; // edx
  struct IWbemContext *v12; // rdi
  unsigned __int64 v13; // rsi
  struct IWbemContextVtbl *lpVtbl; // rcx
  struct IWbemContextVtbl *v15; // r8
  int v16; // ebx
  int v17; // eax
  char *v18; // rcx
  bool v19; // zf
  void (__fastcall *v20)(char *); // rax
  int v21; // esi
  unsigned int v22; // esi
  struct IWbemServices *v23; // r15
  unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // r9
  unsigned int v27; // esi
  CMemoryLog *MemLogObject; // rax
  __int64 v29[9]; // [rsp+50h] [rbp-48h] BYREF

  v29[0] = 0;
  if ( !a5 || ((int (__fastcall *)(struct IWbemContext *, __int64 *))a5->lpVtbl->Clone)(a5, v29) >= 0 )
  {
    v12 = (struct IWbemContext *)operator new(0xB0u);
    a5 = v12;
    v13 = (unsigned __int64)this + 232;
    if ( v12 )
    {
      CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(
        (_DWORD)v12,
        v11,
        (_DWORD)a6,
        (_DWORD)this,
        v13 & -(__int64)(this != 0));
      v12->lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `IWbemObjectSinkEx'};
      v12[1].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `IWbemShutdown'};
      v12[2].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'};
      LODWORD(v12[19].lpVtbl) = a4 & 0xFFFFFDFF;
      v12[20].lpVtbl = a3;
      v12[21].lpVtbl = (struct IWbemContextVtbl *)this;
      if ( a3 )
        (*((void (__fastcall **)(struct IWbemContextVtbl *))a3->QueryInterface + 1))(a3);
      lpVtbl = v12[21].lpVtbl;
      if ( lpVtbl )
      {
        (*((void (__fastcall **)(struct IWbemContextVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
        v15 = v12[21].lpVtbl;
        WmiSetAndCommitObject(
          qword_1400613B8,
          1,
          v15[6].Next,
          *((_QWORD *)v15[6].Clone + 8),
          v15[6].BeginEnumeration,
          v15[6].GetNames,
          v15[6].EndEnumeration,
          v12[19].lpVtbl,
          v12[20].lpVtbl);
      }
    }
    else
    {
      v12 = 0;
    }
    if ( v12 )
    {
      ((void (__fastcall *)(struct IWbemContext *))v12->lpVtbl->AddRef)(v12);
      v16 = ((__int64 (__fastcall *)(struct IWbemContext *))v12->lpVtbl->DeleteValue)(v12);
      if ( v16 < 0 )
      {
LABEL_17:
        ((void (__fastcall *)(struct IWbemContext *))v12->lpVtbl->Release)(v12);
        goto LABEL_18;
      }
      a5 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 48LL))((char *)this + 232);
      v17 = (*(__int64 (__fastcall **)(char *, struct IWbemContext *, struct IWbemContext **))(*(_QWORD *)v13 + 64LL))(
              (char *)this + 232,
              v12 + 2,
              &a5);
      v18 = (char *)this + 232;
      v19 = v17 == 0;
      v20 = *(void (__fastcall **)(char *))(*(_QWORD *)v13 + 56LL);
      if ( !v19 )
      {
        v20(v18);
        v16 = -2147217402;
        goto LABEL_29;
      }
      v20(v18);
      v21 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
      if ( a2 && CoImpersonateClient() < 0 )
        goto LABEL_32;
      v22 = a4 & v21;
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 20);
      ++*((_QWORD *)this + 84);
      v23 = a7;
      v16 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemContextVtbl *, _QWORD, __int64, struct IWbemContext *))a7->lpVtbl->PutInstanceAsync)(
              a7,
              a3,
              v22,
              v29[0],
              v12);
      CoRevertToSelf();
      if ( v16 == -2147217355 || v16 == -2147217400 )
      {
        if ( a2 && CoImpersonateClient() < 0 )
        {
LABEL_32:
          v16 = -2147217405;
          goto LABEL_16;
        }
        v27 = v22 & 0xFFFFFF7F;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 20);
        ++*((_QWORD *)this + 84);
        v16 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemContextVtbl *, _QWORD, __int64, struct IWbemContext *))v23->lpVtbl->PutInstanceAsync)(
                v23,
                a3,
                v27,
                v29[0],
                v12);
        CoRevertToSelf();
      }
LABEL_16:
      if ( v16 >= 0 )
        goto LABEL_17;
LABEL_29:
      CInterceptor_IWbemSyncProvider::SetStatus(this, L"PutInstanceAsync", v24, v25, v16, (struct IWbemObjectSink *)v12);
      goto LABEL_17;
    }
  }
  v16 = -2147217402;
LABEL_18:
  if ( v29[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  if ( v16 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v16);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000b420  push    rbx
0x14000b422  push    rbp
0x14000b423  push    rsi
0x14000b424  push    rdi
0x14000b425  push    r12
0x14000b427  push    r14
0x14000b429  push    r15
0x14000b42b  sub     rsp, 60h
0x14000b42f  mov     r15d, r9d
0x14000b432  mov     r14, r8
0x14000b435  mov     r12d, edx
0x14000b438  mov     rbp, rcx
0x14000b43b  mov     [rsp+98h+var_48], 0
0x14000b444  mov     rcx, [rsp+98h+arg_20]
0x14000b44c  test    rcx, rcx
0x14000b44f  jz      short loc_14000B46A
0x14000b451  mov     rax, [rcx]
0x14000b454  lea     rdx, [rsp+98h+var_48]
0x14000b459  mov     rax, [rax+18h]
0x14000b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b462  test    eax, eax
0x14000b464  js      loc_14000B739
0x14000b46a  mov     ecx, 0B0h; dwBytes
0x14000b46f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b474  mov     rdi, rax
0x14000b477  mov     [rsp+98h+arg_20], rax
0x14000b47f  lea     rsi, [rbp+0E8h]
0x14000b486  test    rax, rax
0x14000b489  jz      loc_14000B70B
0x14000b48f  mov     ebx, r15d
0x14000b492  btr     ebx, 9
0x14000b496  mov     rax, rbp
0x14000b499  neg     rax
0x14000b49c  sbb     rcx, rcx
0x14000b49f  and     rcx, rsi
0x14000b4a2  mov     qword ptr [rsp+98h+var_78], rcx
0x14000b4a7  mov     r9, rbp
0x14000b4aa  mov     r8, [rsp+98h+arg_28]
0x14000b4b2  mov     rcx, rdi
0x14000b4b5  call    ??0CCommon_IWbemSyncObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(WmiAllocator &,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x14000b4ba  nop
0x14000b4bb  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_PutInstanceAsync@@6BIWbemObjectSinkEx@@@; const CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `IWbemObjectSinkEx'}
0x14000b4c2  mov     [rdi], rax
0x14000b4c5  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_PutInstanceAsync@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `IWbemShutdown'}
0x14000b4cc  mov     [rdi+8], rax
0x14000b4d0  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_PutInstanceAsync@@6BWmiContainerElement@?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncObjectSink_PutInstanceAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'}
0x14000b4d7  mov     [rdi+10h], rax
0x14000b4db  mov     [rdi+98h], ebx
0x14000b4e1  mov     [rdi+0A0h], r14
0x14000b4e8  mov     [rdi+0A8h], rbp
0x14000b4ef  test    r14, r14
0x14000b4f2  jz      short loc_14000B503
0x14000b4f4  mov     rax, [r14]
0x14000b4f7  mov     rcx, r14
0x14000b4fa  mov     rax, [rax+8]
0x14000b4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b503  mov     rcx, [rdi+0A8h]
0x14000b50a  test    rcx, rcx
0x14000b50d  jz      short loc_14000B581
0x14000b50f  mov     rax, [rcx]
0x14000b512  mov     rax, [rax+8]
0x14000b516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b51b  mov     r8, [rdi+0A8h]
0x14000b522  mov     r9, [r8+258h]
0x14000b529  mov     rax, [rdi+0A0h]
0x14000b530  mov     [rsp+98h+var_58], rax
0x14000b535  mov     eax, [rdi+98h]
0x14000b53b  mov     [rsp+98h+var_60], eax
0x14000b53f  mov     rax, [r8+278h]
0x14000b546  mov     [rsp+98h+var_68], rax
0x14000b54b  mov     rax, [r8+260h]
0x14000b552  mov     [rsp+98h+var_70], rax
0x14000b557  mov     rax, [r8+268h]
0x14000b55e  mov     qword ptr [rsp+98h+var_78], rax
0x14000b563  mov     r9, [r9+40h]
0x14000b567  mov     r8, [r8+270h]
0x14000b56e  mov     edx, 1
0x14000b573  mov     rcx, cs:qword_1400613B8
0x14000b57a  call    cs:__imp_WmiSetAndCommitObject
0x14000b580  nop
0x14000b581  test    rdi, rdi
0x14000b584  jz      loc_14000B739
0x14000b58a  mov     rax, [rdi]
0x14000b58d  mov     rcx, rdi
0x14000b590  mov     rax, [rax+8]
0x14000b594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b599  mov     rax, [rdi]
0x14000b59c  mov     rcx, rdi
0x14000b59f  mov     rax, [rax+50h]
0x14000b5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5a8  mov     ebx, eax
0x14000b5aa  test    eax, eax
0x14000b5ac  js      loc_14000B694
0x14000b5b2  mov     [rsp+98h+arg_20], 0
0x14000b5be  mov     rax, [rsi]
0x14000b5c1  mov     rcx, rsi
0x14000b5c4  mov     rax, [rax+30h]
0x14000b5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5cd  mov     rax, [rsi]
0x14000b5d0  lea     rdx, [rdi+10h]
0x14000b5d4  lea     r8, [rsp+98h+arg_20]
0x14000b5dc  mov     rcx, rsi
0x14000b5df  mov     rax, [rax+40h]
0x14000b5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5e8  mov     rdx, [rsi]
0x14000b5eb  mov     r8, [rdx+38h]
0x14000b5ef  mov     rcx, rsi
0x14000b5f2  test    eax, eax
0x14000b5f4  mov     rax, r8
0x14000b5f7  jnz     loc_14000B712
0x14000b5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b602  mov     rax, [rbp+258h]
0x14000b609  mov     ecx, [rax+6CCh]
0x14000b60f  neg     ecx
0x14000b611  sbb     esi, esi
0x14000b613  and     esi, 80h
0x14000b619  add     esi, 0FFFFFD7Fh
0x14000b61f  test    r12d, r12d
0x14000b622  jnz     loc_14000B743
0x14000b628  and     esi, r15d
0x14000b62b  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000b632  test    rax, rax
0x14000b635  jz      short loc_14000B63E
0x14000b637  inc     qword ptr [rax+0A0h]
0x14000b63e  inc     qword ptr [rbp+2A0h]
0x14000b645  mov     r15, [rsp+98h+arg_30]
0x14000b64d  mov     rax, [r15]
0x14000b650  mov     qword ptr [rsp+98h+var_78], rdi
0x14000b655  mov     r9, [rsp+98h+var_48]
0x14000b65a  mov     r8d, esi
0x14000b65d  mov     rdx, r14
0x14000b660  mov     rcx, r15
0x14000b663  mov     rax, [rax+78h]
0x14000b667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b66c  mov     ebx, eax
0x14000b66e  call    cs:__imp_CoRevertToSelf
0x14000b674  cmp     ebx, 80041035h
0x14000b67a  jz      loc_14000B75B
0x14000b680  cmp     ebx, 80041008h
0x14000b686  jz      loc_14000B75B
0x14000b68c  test    ebx, ebx
0x14000b68e  js      loc_14000B71C
0x14000b694  mov     rax, [rdi]
0x14000b697  mov     rcx, rdi
0x14000b69a  mov     rax, [rax+10h]
0x14000b69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6a3  mov     rcx, [rsp+98h+var_48]
0x14000b6a8  test    rcx, rcx
0x14000b6ab  jz      short loc_14000B6B9
0x14000b6ad  mov     rax, [rcx]
0x14000b6b0  mov     rax, [rax+10h]
0x14000b6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6b9  test    ebx, ebx
0x14000b6bb  js      loc_14000B7B4
0x14000b6c1  lea     rax, WPP_GLOBAL_Control
0x14000b6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6cf  cmp     rcx, rax
0x14000b6d2  jnz     short loc_14000B6E5
0x14000b6d4  mov     eax, ebx
0x14000b6d6  add     rsp, 60h
0x14000b6da  pop     r15
0x14000b6dc  pop     r14
0x14000b6de  pop     r12
0x14000b6e0  pop     rdi
0x14000b6e1  pop     rsi
0x14000b6e2  pop     rbp
0x14000b6e3  pop     rbx
0x14000b6e4  retn
0x14000b6e5  test    byte ptr [rcx+1Ch], 4
0x14000b6e9  jz      short loc_14000B6D4
0x14000b6eb  cmp     byte ptr [rcx+19h], 2
0x14000b6ef  jb      short loc_14000B6D4
0x14000b6f1  mov     edx, 67h ; 'g'
0x14000b6f6  mov     r9d, ebx
0x14000b6f9  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000b700  mov     rcx, [rcx+10h]
0x14000b704  call    WPP_SF_d
0x14000b709  jmp     short loc_14000B6D4
0x14000b70b  xor     edi, edi
0x14000b70d  jmp     loc_14000B581
0x14000b712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b717  mov     ebx, 80041006h
0x14000b71c  mov     [rsp+98h+var_70], rdi; struct IWbemObjectSink *
0x14000b721  mov     [rsp+98h+var_78], ebx; int
0x14000b725  lea     rdx, aPutinstanceasy; "PutInstanceAsync"
0x14000b72c  mov     rcx, rbp; this
0x14000b72f  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x14000b734  jmp     loc_14000B694
0x14000b739  mov     ebx, 80041006h
0x14000b73e  jmp     loc_14000B6A3
0x14000b743  call    cs:__imp_CoImpersonateClient
0x14000b749  test    eax, eax
0x14000b74b  jns     loc_14000B628
0x14000b751  mov     ebx, 80041003h
0x14000b756  jmp     loc_14000B68C
0x14000b75b  test    r12d, r12d
0x14000b75e  jz      short loc_14000B76A
0x14000b760  call    cs:__imp_CoImpersonateClient
0x14000b766  test    eax, eax
0x14000b768  js      short loc_14000B751
0x14000b76a  btr     esi, 7
0x14000b76e  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000b775  test    rax, rax
0x14000b778  jz      short loc_14000B781
0x14000b77a  inc     qword ptr [rax+0A0h]
0x14000b781  inc     qword ptr [rbp+2A0h]
0x14000b788  mov     rax, [r15]
0x14000b78b  mov     qword ptr [rsp+98h+var_78], rdi
0x14000b790  mov     r9, [rsp+98h+var_48]
0x14000b795  mov     r8d, esi
0x14000b798  mov     rdx, r14
0x14000b79b  mov     rcx, r15
0x14000b79e  mov     rax, [rax+78h]
0x14000b7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7a7  mov     ebx, eax
0x14000b7a9  call    cs:__imp_CoRevertToSelf
0x14000b7af  jmp     loc_14000B68C
0x14000b7b4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000b7ba  mov     edx, ebx
0x14000b7bc  mov     rcx, rax
0x14000b7bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000b7c5  jmp     loc_14000B6C1
```
