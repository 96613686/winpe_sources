# CInterceptor_IWbemSyncProvider::Helper_DeleteInstanceAsync(int,ushort * const,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14000e9a0`
- end: `0x14000ed56`
- name: `?Helper_DeleteInstanceAsync@CInterceptor_IWbemSyncProvider@@AEAAJHQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `950`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, int@<edx>, unsigned __int16 *const@<r8>, int@<r9d>, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000f7a0`

## callees

- `0x14000a530`
- `0x14000c190`
- `0x14000d1e0`
- `0x14000e9a0`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14000eaf7`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000eaf7`
- `wbemcomn!GetMemLogObject` at `0x14000ed40`
- `wbemcomn!GetMemLogObject` at `0x14000ed40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000ed4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000ed4b`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e9ed`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e9ed`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ed30`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ed30`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ecb9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ecd6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ecb9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000ecd6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000ebee`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000ed22`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000ebee`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000ed22`

## string_xrefs

- `0x14000eca5`: `DeleteInstanceAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_DeleteInstanceAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        unsigned __int16 *const a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  OLECHAR *v11; // rbp
  __int64 v12; // rdx
  struct IWbemContext *v13; // rdi
  unsigned __int64 v14; // rsi
  int v15; // ebx
  int v16; // eax
  char *v17; // rcx
  bool v18; // zf
  void (__fastcall *v19)(char *); // rax
  int v20; // esi
  unsigned int v21; // esi
  struct IWbemServices *v22; // r15
  struct IWbemClassObject *v23; // r8
  unsigned __int16 *v24; // r9
  unsigned int v26; // esi
  CMemoryLog *MemLogObject; // rax
  __int64 v28[9]; // [rsp+50h] [rbp-48h] BYREF

  v28[0] = 0;
  if ( !a5 || ((int (__fastcall *)(struct IWbemContext *, __int64 *))a5->lpVtbl->Clone)(a5, v28) >= 0 )
  {
    v11 = SysAllocString(a3);
    if ( v11 )
    {
      v13 = (struct IWbemContext *)operator new(0xB0u);
      a5 = v13;
      v14 = (unsigned __int64)this + 232;
      if ( v13 )
      {
        CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(
          (__int64)v13,
          v12,
          (__int64)a6,
          (__int64)this,
          v14 & -(__int64)(this != 0));
        v13->lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `IWbemObjectSinkEx'};
        v13[1].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `IWbemShutdown'};
        v13[2].lpVtbl = (struct IWbemContextVtbl *)&CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'};
        LODWORD(v13[19].lpVtbl) = a4 & 0xFFFFFDFF;
        v13[20].lpVtbl = (struct IWbemContextVtbl *)v11;
        v13[21].lpVtbl = (struct IWbemContextVtbl *)this;
        if ( this )
        {
          (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)this + 8LL))(this);
          WmiSetAndCommitObject(
            qword_1400613C0,
            1,
            v13[21].lpVtbl[6].Next,
            *((_QWORD *)v13[21].lpVtbl[6].Clone + 8),
            v13[21].lpVtbl[6].BeginEnumeration,
            v13[21].lpVtbl[6].GetNames,
            v13[21].lpVtbl[6].EndEnumeration,
            v13[19].lpVtbl);
        }
      }
      else
      {
        v13 = 0;
      }
      if ( v13 )
      {
        ((void (__fastcall *)(struct IWbemContext *))v13->lpVtbl->AddRef)(v13);
        v15 = ((__int64 (__fastcall *)(struct IWbemContext *))v13->lpVtbl->DeleteValue)(v13);
        if ( v15 < 0 )
        {
LABEL_16:
          ((void (__fastcall *)(struct IWbemContext *))v13->lpVtbl->Release)(v13);
          goto LABEL_17;
        }
        a5 = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 48LL))((char *)this + 232);
        v16 = (*(__int64 (__fastcall **)(char *, struct IWbemContext *, struct IWbemContext **))(*(_QWORD *)v14 + 64LL))(
                (char *)this + 232,
                v13 + 2,
                &a5);
        v17 = (char *)this + 232;
        v18 = v16 == 0;
        v19 = *(void (__fastcall **)(char *))(*(_QWORD *)v14 + 56LL);
        if ( !v18 )
        {
          v19(v17);
          v15 = -2147217402;
          goto LABEL_28;
        }
        v19(v17);
        v20 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
        if ( a2 && CoImpersonateClient() < 0 )
          goto LABEL_30;
        v21 = a4 & v20;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 21);
        ++*((_QWORD *)this + 85);
        v22 = a7;
        v15 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, __int64, struct IWbemContext *))a7->lpVtbl->DeleteInstanceAsync)(
                a7,
                v11,
                v21,
                v28[0],
                v13);
        CoRevertToSelf();
        if ( v15 == -2147217355 || v15 == -2147217400 )
        {
          if ( a2 && CoImpersonateClient() < 0 )
          {
LABEL_30:
            v15 = -2147217405;
            goto LABEL_15;
          }
          v26 = v21 & 0xFFFFFF7F;
          if ( ProviderSubSystem_Globals::s_SharedCounters )
            ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 21);
          ++*((_QWORD *)this + 85);
          v15 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, __int64, struct IWbemContext *))v22->lpVtbl->DeleteInstanceAsync)(
                  v22,
                  v11,
                  v26,
                  v28[0],
                  v13);
          CoRevertToSelf();
        }
LABEL_15:
        if ( v15 >= 0 )
          goto LABEL_16;
LABEL_28:
        CInterceptor_IWbemSyncProvider::SetStatus(
          this,
          L"DeleteInstanceAsync",
          v23,
          v24,
          v15,
          (struct IWbemObjectSink *)v13);
        goto LABEL_16;
      }
      SysFreeString(v11);
    }
  }
  v15 = -2147217402;
LABEL_17:
  if ( v28[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
  if ( v15 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000e9a0  push    rbx
0x14000e9a2  push    rbp
0x14000e9a3  push    rsi
0x14000e9a4  push    rdi
0x14000e9a5  push    r12
0x14000e9a7  push    r14
0x14000e9a9  push    r15
0x14000e9ab  sub     rsp, 60h
0x14000e9af  mov     r15d, r9d
0x14000e9b2  mov     rbx, r8
0x14000e9b5  mov     r12d, edx
0x14000e9b8  mov     r14, rcx
0x14000e9bb  mov     [rsp+98h+var_48], 0
0x14000e9c4  mov     rcx, [rsp+98h+arg_20]
0x14000e9cc  test    rcx, rcx
0x14000e9cf  jz      short loc_14000E9EA
0x14000e9d1  mov     rax, [rcx]
0x14000e9d4  lea     rdx, [rsp+98h+var_48]
0x14000e9d9  mov     rax, [rax+18h]
0x14000e9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9e2  test    eax, eax
0x14000e9e4  js      loc_14000ED36
0x14000e9ea  mov     rcx, rbx; psz
0x14000e9ed  call    cs:__imp_SysAllocString
0x14000e9f3  mov     rbp, rax
0x14000e9f6  test    rax, rax
0x14000e9f9  jz      loc_14000ED36
0x14000e9ff  mov     ecx, 0B0h; dwBytes
0x14000ea04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ea09  mov     rdi, rax
0x14000ea0c  mov     [rsp+98h+arg_20], rax
0x14000ea14  lea     rsi, [r14+0E8h]
0x14000ea1b  test    rax, rax
0x14000ea1e  jz      loc_14000EC65
0x14000ea24  mov     ebx, r15d
0x14000ea27  btr     ebx, 9
0x14000ea2b  mov     rax, r14
0x14000ea2e  neg     rax
0x14000ea31  sbb     rcx, rcx
0x14000ea34  and     rcx, rsi
0x14000ea37  mov     qword ptr [rsp+98h+var_78], rcx
0x14000ea3c  mov     r9, r14
0x14000ea3f  mov     r8, [rsp+98h+arg_28]
0x14000ea47  mov     rcx, rdi
0x14000ea4a  call    ??0CCommon_IWbemSyncObjectSink@@QEAA@AEAVWmiAllocator@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CCommon_IWbemSyncObjectSink::CCommon_IWbemSyncObjectSink(WmiAllocator &,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x14000ea4f  nop
0x14000ea50  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync@@6BIWbemObjectSinkEx@@@; const CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `IWbemObjectSinkEx'}
0x14000ea57  mov     [rdi], rax
0x14000ea5a  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync@@6BIWbemShutdown@@@; const CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `IWbemShutdown'}
0x14000ea61  mov     [rdi+8], rax
0x14000ea65  lea     rax, ??_7CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync@@6BWmiContainerElement@?$WmiContainerController@PEAX@@@; const CInterceptor_IWbemSyncObjectSink_DeleteInstanceAsync::`vftable'{for `WmiContainerController<void *>::WmiContainerElement'}
0x14000ea6c  mov     [rdi+10h], rax
0x14000ea70  mov     [rdi+98h], ebx
0x14000ea76  mov     [rdi+0A0h], rbp
0x14000ea7d  mov     [rdi+0A8h], r14
0x14000ea84  test    r14, r14
0x14000ea87  jz      short loc_14000EAFE
0x14000ea89  mov     rax, [r14]
0x14000ea8c  mov     rcx, r14
0x14000ea8f  mov     rax, [rax+8]
0x14000ea93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea98  mov     r8, [rdi+0A8h]
0x14000ea9f  mov     r9, [r8+258h]
0x14000eaa6  mov     rax, [rdi+0A0h]
0x14000eaad  mov     [rsp+98h+var_58], rax
0x14000eab2  mov     eax, [rdi+98h]
0x14000eab8  mov     [rsp+98h+var_60], eax
0x14000eabc  mov     rax, [r8+278h]
0x14000eac3  mov     [rsp+98h+var_68], rax
0x14000eac8  mov     rax, [r8+260h]
0x14000eacf  mov     [rsp+98h+var_70], rax
0x14000ead4  mov     rax, [r8+268h]
0x14000eadb  mov     qword ptr [rsp+98h+var_78], rax
0x14000eae0  mov     r9, [r9+40h]
0x14000eae4  mov     r8, [r8+270h]
0x14000eaeb  mov     edx, 1
0x14000eaf0  mov     rcx, cs:qword_1400613C0
0x14000eaf7  call    cs:__imp_WmiSetAndCommitObject
0x14000eafd  nop
0x14000eafe  test    rdi, rdi
0x14000eb01  jz      loc_14000ED2D
0x14000eb07  mov     rax, [rdi]
0x14000eb0a  mov     rcx, rdi
0x14000eb0d  mov     rax, [rax+8]
0x14000eb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb16  mov     rax, [rdi]
0x14000eb19  mov     rcx, rdi
0x14000eb1c  mov     rax, [rax+50h]
0x14000eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb25  mov     ebx, eax
0x14000eb27  test    eax, eax
0x14000eb29  js      loc_14000EC14
0x14000eb2f  mov     [rsp+98h+arg_20], 0
0x14000eb3b  mov     rax, [rsi]
0x14000eb3e  mov     rcx, rsi
0x14000eb41  mov     rax, [rax+30h]
0x14000eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb4a  mov     rax, [rsi]
0x14000eb4d  lea     rdx, [rdi+10h]
0x14000eb51  lea     r8, [rsp+98h+arg_20]
0x14000eb59  mov     rcx, rsi
0x14000eb5c  mov     rax, [rax+40h]
0x14000eb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb65  mov     rdx, [rsi]
0x14000eb68  mov     r8, [rdx+38h]
0x14000eb6c  mov     rcx, rsi
0x14000eb6f  test    eax, eax
0x14000eb71  mov     rax, r8
0x14000eb74  jnz     loc_14000EC92
0x14000eb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb7f  mov     rax, [r14+258h]
0x14000eb86  mov     ecx, [rax+6CCh]
0x14000eb8c  neg     ecx
0x14000eb8e  sbb     esi, esi
0x14000eb90  and     esi, 80h
0x14000eb96  add     esi, 0FFFFFD7Fh
0x14000eb9c  test    r12d, r12d
0x14000eb9f  jnz     loc_14000ECB9
0x14000eba5  and     esi, r15d
0x14000eba8  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000ebaf  test    rax, rax
0x14000ebb2  jz      short loc_14000EBBB
0x14000ebb4  inc     qword ptr [rax+0A8h]
0x14000ebbb  inc     qword ptr [r14+2A8h]
0x14000ebc2  mov     r15, [rsp+98h+arg_30]
0x14000ebca  mov     rax, [r15]
0x14000ebcd  mov     qword ptr [rsp+98h+var_78], rdi
0x14000ebd2  mov     r9, [rsp+98h+var_48]
0x14000ebd7  mov     r8d, esi
0x14000ebda  mov     rdx, rbp
0x14000ebdd  mov     rcx, r15
0x14000ebe0  mov     rax, [rax+88h]
0x14000ebe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebec  mov     ebx, eax
0x14000ebee  call    cs:__imp_CoRevertToSelf
0x14000ebf4  cmp     ebx, 80041035h
0x14000ebfa  jz      loc_14000ECD1
0x14000ec00  cmp     ebx, 80041008h
0x14000ec06  jz      loc_14000ECD1
0x14000ec0c  test    ebx, ebx
0x14000ec0e  js      loc_14000EC9C
0x14000ec14  mov     rax, [rdi]
0x14000ec17  mov     rcx, rdi
0x14000ec1a  mov     rax, [rax+10h]
0x14000ec1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec23  mov     rcx, [rsp+98h+var_48]
0x14000ec28  test    rcx, rcx
0x14000ec2b  jz      short loc_14000EC39
0x14000ec2d  mov     rax, [rcx]
0x14000ec30  mov     rax, [rax+10h]
0x14000ec34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec39  test    ebx, ebx
0x14000ec3b  js      loc_14000ED40
0x14000ec41  lea     rax, WPP_GLOBAL_Control
0x14000ec48  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec4f  cmp     rcx, rax
0x14000ec52  jnz     short loc_14000EC6C
0x14000ec54  mov     eax, ebx
0x14000ec56  add     rsp, 60h
0x14000ec5a  pop     r15
0x14000ec5c  pop     r14
0x14000ec5e  pop     r12
0x14000ec60  pop     rdi
0x14000ec61  pop     rsi
0x14000ec62  pop     rbp
0x14000ec63  pop     rbx
0x14000ec64  retn
0x14000ec65  xor     edi, edi
0x14000ec67  jmp     loc_14000EAFE
0x14000ec6c  test    byte ptr [rcx+1Ch], 4
0x14000ec70  jz      short loc_14000EC54
0x14000ec72  cmp     byte ptr [rcx+19h], 2
0x14000ec76  jb      short loc_14000EC54
0x14000ec78  mov     edx, 6Bh ; 'k'
0x14000ec7d  mov     r9d, ebx
0x14000ec80  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14000ec87  mov     rcx, [rcx+10h]
0x14000ec8b  call    WPP_SF_d
0x14000ec90  jmp     short loc_14000EC54
0x14000ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec97  mov     ebx, 80041006h
0x14000ec9c  mov     [rsp+98h+var_70], rdi; struct IWbemObjectSink *
0x14000eca1  mov     [rsp+98h+var_78], ebx; int
0x14000eca5  lea     rdx, aDeleteinstance; "DeleteInstanceAsync"
0x14000ecac  mov     rcx, r14; this
0x14000ecaf  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x14000ecb4  jmp     loc_14000EC14
0x14000ecb9  call    cs:__imp_CoImpersonateClient
0x14000ecbf  test    eax, eax
0x14000ecc1  jns     loc_14000EBA5
0x14000ecc7  mov     ebx, 80041003h
0x14000eccc  jmp     loc_14000EC0C
0x14000ecd1  test    r12d, r12d
0x14000ecd4  jz      short loc_14000ECE0
0x14000ecd6  call    cs:__imp_CoImpersonateClient
0x14000ecdc  test    eax, eax
0x14000ecde  js      short loc_14000ECC7
0x14000ece0  btr     esi, 7
0x14000ece4  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14000eceb  test    rax, rax
0x14000ecee  jz      short loc_14000ECF7
0x14000ecf0  inc     qword ptr [rax+0A8h]
0x14000ecf7  inc     qword ptr [r14+2A8h]
0x14000ecfe  mov     rax, [r15]
0x14000ed01  mov     qword ptr [rsp+98h+var_78], rdi
0x14000ed06  mov     r9, [rsp+98h+var_48]
0x14000ed0b  mov     r8d, esi
0x14000ed0e  mov     rdx, rbp
0x14000ed11  mov     rcx, r15
0x14000ed14  mov     rax, [rax+88h]
0x14000ed1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed20  mov     ebx, eax
0x14000ed22  call    cs:__imp_CoRevertToSelf
0x14000ed28  jmp     loc_14000EC0C
0x14000ed2d  mov     rcx, rbp; bstrString
0x14000ed30  call    cs:__imp_SysFreeString
0x14000ed36  mov     ebx, 80041006h
0x14000ed3b  jmp     loc_14000EC23
0x14000ed40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000ed46  mov     edx, ebx
0x14000ed48  mov     rcx, rax
0x14000ed4b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000ed51  jmp     loc_14000EC41
```
