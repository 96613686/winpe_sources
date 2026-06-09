# CInterceptor_IWbemSyncProvider::Helper_PutClassAsync(int,IWbemClassObject *,long,IWbemContext *,IWbemObjectSink *,IWbemServices *)

- ea: `0x14003804c`
- end: `0x140038311`
- name: `?Helper_PutClassAsync@CInterceptor_IWbemSyncProvider@@AEAAJHPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAUIWbemObjectSink@@PEAUIWbemServices@@@Z`
- size: `709`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *this, int, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemObjectSink *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003b520`

## callees

- `0x14000a530`
- `0x14000c190`
- `0x1400234b8`
- `0x14003804c`
- `0x14003c940`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1400382b8`
- `wbemcomn!GetMemLogObject` at `0x1400382b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400382c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400382c3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003819c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140038211`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14003819c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140038211`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400381f6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003825a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400381f6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14003825a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInterceptor_IWbemSyncProvider::Helper_PutClassAsync(
        CInterceptor_IWbemSyncProvider *this,
        int a2,
        struct IWbemClassObject *a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSink *a6,
        struct IWbemServices *a7)
{
  struct IWbemContext *v11; // r10
  unsigned __int64 v12; // rsi
  struct IWbemObjectSink *v13; // rdi
  int v14; // ebx
  int v15; // eax
  char *v16; // rcx
  bool v17; // zf
  void (__fastcall *v18)(char *); // rax
  int v19; // esi
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // r9
  unsigned int v22; // esi
  struct IWbemServices *v23; // r14
  unsigned int v24; // esi
  CMemoryLog *MemLogObject; // rax
  _QWORD v27[9]; // [rsp+50h] [rbp-48h] BYREF

  v27[0] = 0;
  if ( !a5 || ((int (__fastcall *)(struct IWbemContext *, _QWORD *))a5->lpVtbl->Clone)(a5, v27) >= 0 )
  {
    v11 = (struct IWbemContext *)operator new(0xB0u);
    a5 = v11;
    v12 = (unsigned __int64)this + 232;
    v13 = v11
        ? (struct IWbemObjectSink *)CInterceptor_IWbemSyncObjectSink_PutClassAsync::CInterceptor_IWbemSyncObjectSink_PutClassAsync(
                                      (__int64)v11,
                                      v12 & -(__int64)(this != 0),
                                      a4 & 0xFFFFFDFF,
                                      (__int64)a3,
                                      (__int64)this,
                                      (__int64)a6,
                                      (__int64)this,
                                      v12 & -(__int64)(this != 0))
        : 0LL;
    if ( v13 )
    {
      ((void (__fastcall *)(struct IWbemObjectSink *))v13->lpVtbl->AddRef)(v13);
      v14 = ((__int64 (__fastcall *)(struct IWbemObjectSink *))v13->lpVtbl[2].QueryInterface)(v13);
      if ( v14 < 0 )
        goto LABEL_25;
      a5 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 48LL))((char *)this + 232);
      v15 = (*(__int64 (__fastcall **)(char *, struct IWbemObjectSink *, struct IWbemContext **))(*(_QWORD *)v12 + 64LL))(
              (char *)this + 232,
              v13 + 2,
              &a5);
      v16 = (char *)this + 232;
      v17 = v15 == 0;
      v18 = *(void (__fastcall **)(char *))(*(_QWORD *)v12 + 56LL);
      if ( !v17 )
      {
        v18(v16);
        v14 = -2147217402;
LABEL_24:
        CInterceptor_IWbemSyncProvider::SetStatus(this, L"PutClassAsync", v20, v21, v14, v13);
        goto LABEL_25;
      }
      v18(v16);
      v19 = *(_DWORD *)(*((_QWORD *)this + 75) + 1740LL) != 0 ? -513 : -641;
      if ( a2 && CoImpersonateClient() < 0 )
        goto LABEL_11;
      v22 = a4 & v19;
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 17);
      ++*((_QWORD *)this + 81);
      v23 = a7;
      v14 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, _QWORD, _QWORD, struct IWbemObjectSink *))a7->lpVtbl->PutClassAsync)(
              a7,
              a3,
              v22,
              v27[0],
              v13);
      CoRevertToSelf();
      if ( v14 == -2147217355 || v14 == -2147217400 )
      {
        if ( a2 && CoImpersonateClient() < 0 )
        {
LABEL_11:
          v14 = -2147217405;
          goto LABEL_21;
        }
        v24 = v22 & 0xFFFFFF7F;
        if ( ProviderSubSystem_Globals::s_SharedCounters )
          ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 17);
        ++*((_QWORD *)this + 81);
        v14 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, _QWORD, _QWORD, struct IWbemObjectSink *))v23->lpVtbl->PutClassAsync)(
                v23,
                a3,
                v24,
                v27[0],
                v13);
        CoRevertToSelf();
      }
LABEL_21:
      if ( v14 < 0 )
        goto LABEL_24;
LABEL_25:
      ((void (__fastcall *)(struct IWbemObjectSink *))v13->lpVtbl->Release)(v13);
      goto LABEL_27;
    }
  }
  v14 = -2147217402;
LABEL_27:
  if ( v27[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 16LL))(v27[0]);
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003804c  push    rbx
0x14003804e  push    rbp
0x14003804f  push    rsi
0x140038050  push    rdi
0x140038051  push    r12
0x140038053  push    r14
0x140038055  push    r15
0x140038057  sub     rsp, 60h
0x14003805b  mov     r14d, r9d
0x14003805e  mov     r12, r8
0x140038061  mov     r15d, edx
0x140038064  mov     rbp, rcx
0x140038067  mov     [rsp+98h+var_48], 0
0x140038070  mov     rcx, [rsp+98h+arg_20]
0x140038078  test    rcx, rcx
0x14003807b  jz      short loc_140038096
0x14003807d  mov     rax, [rcx]
0x140038080  lea     rdx, [rsp+98h+var_48]
0x140038085  mov     rax, [rax+18h]
0x140038089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003808e  test    eax, eax
0x140038090  js      loc_140038299
0x140038096  mov     ecx, 0B0h; dwBytes
0x14003809b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400380a0  mov     r10, rax
0x1400380a3  mov     [rsp+98h+arg_20], rax
0x1400380ab  lea     rsi, [rbp+0E8h]
0x1400380b2  test    rax, rax
0x1400380b5  jz      short loc_1400380F7
0x1400380b7  mov     rcx, rbp
0x1400380ba  neg     rcx
0x1400380bd  sbb     rdx, rdx
0x1400380c0  and     rdx, rsi
0x1400380c3  mov     r8d, r14d
0x1400380c6  btr     r8d, 9
0x1400380cb  mov     [rsp+98h+var_60], rdx
0x1400380d0  mov     [rsp+98h+var_68], rbp
0x1400380d5  mov     rax, [rsp+98h+arg_28]
0x1400380dd  mov     [rsp+98h+var_70], rax
0x1400380e2  mov     qword ptr [rsp+98h+var_78], rbp
0x1400380e7  mov     r9, r12
0x1400380ea  mov     rcx, r10
0x1400380ed  call    ??0CInterceptor_IWbemSyncObjectSink_PutClassAsync@@QEAA@AEAVWmiAllocator@@JPEAUIWbemClassObject@@PEAVCInterceptor_IWbemSyncProvider@@PEAUIWbemObjectSink@@PEAUIUnknown@@PEAV?$WmiContainerController@PEAX@@K@Z; CInterceptor_IWbemSyncObjectSink_PutClassAsync::CInterceptor_IWbemSyncObjectSink_PutClassAsync(WmiAllocator &,long,IWbemClassObject *,CInterceptor_IWbemSyncProvider *,IWbemObjectSink *,IUnknown *,WmiContainerController<void *> *,ulong)
0x1400380f2  mov     rdi, rax
0x1400380f5  jmp     short loc_1400380F9
0x1400380f7  xor     edi, edi
0x1400380f9  test    rdi, rdi
0x1400380fc  jz      loc_140038299
0x140038102  mov     rax, [rdi]
0x140038105  mov     rcx, rdi
0x140038108  mov     rax, [rax+8]
0x14003810c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038111  mov     rax, [rdi]
0x140038114  mov     rcx, rdi
0x140038117  mov     rax, [rax+50h]
0x14003811b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038120  mov     ebx, eax
0x140038122  test    eax, eax
0x140038124  js      loc_140038288
0x14003812a  mov     [rsp+98h+arg_20], 0
0x140038136  mov     rax, [rsi]
0x140038139  mov     rcx, rsi
0x14003813c  mov     rax, [rax+30h]
0x140038140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038145  mov     rax, [rsi]
0x140038148  lea     rdx, [rdi+10h]
0x14003814c  lea     r8, [rsp+98h+arg_20]
0x140038154  mov     rcx, rsi
0x140038157  mov     rax, [rax+40h]
0x14003815b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038160  mov     rdx, [rsi]
0x140038163  mov     r8, [rdx+38h]
0x140038167  mov     rcx, rsi
0x14003816a  test    eax, eax
0x14003816c  mov     rax, r8
0x14003816f  jnz     loc_140038266
0x140038175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003817a  mov     rax, [rbp+258h]
0x140038181  mov     ecx, [rax+6CCh]
0x140038187  neg     ecx
0x140038189  sbb     esi, esi
0x14003818b  and     esi, 80h
0x140038191  add     esi, 0FFFFFD7Fh
0x140038197  test    r15d, r15d
0x14003819a  jz      short loc_1400381B0
0x14003819c  call    cs:__imp_CoImpersonateClient
0x1400381a2  test    eax, eax
0x1400381a4  jns     short loc_1400381B0
0x1400381a6  mov     ebx, 80041003h
0x1400381ab  jmp     loc_140038260
0x1400381b0  and     esi, r14d
0x1400381b3  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x1400381ba  test    rax, rax
0x1400381bd  jz      short loc_1400381C6
0x1400381bf  inc     qword ptr [rax+88h]
0x1400381c6  inc     qword ptr [rbp+288h]
0x1400381cd  mov     r14, [rsp+98h+arg_30]
0x1400381d5  mov     rax, [r14]
0x1400381d8  mov     qword ptr [rsp+98h+var_78], rdi
0x1400381dd  mov     r9, [rsp+98h+var_48]
0x1400381e2  mov     r8d, esi
0x1400381e5  mov     rdx, r12
0x1400381e8  mov     rcx, r14
0x1400381eb  mov     rax, [rax+48h]
0x1400381ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400381f4  mov     ebx, eax
0x1400381f6  call    cs:__imp_CoRevertToSelf
0x1400381fc  cmp     ebx, 80041035h
0x140038202  jz      short loc_14003820C
0x140038204  cmp     ebx, 80041008h
0x14003820a  jnz     short loc_140038260
0x14003820c  test    r15d, r15d
0x14003820f  jz      short loc_14003821B
0x140038211  call    cs:__imp_CoImpersonateClient
0x140038217  test    eax, eax
0x140038219  js      short loc_1400381A6
0x14003821b  btr     esi, 7
0x14003821f  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140038226  test    rax, rax
0x140038229  jz      short loc_140038232
0x14003822b  inc     qword ptr [rax+88h]
0x140038232  inc     qword ptr [rbp+288h]
0x140038239  mov     rax, [r14]
0x14003823c  mov     qword ptr [rsp+98h+var_78], rdi
0x140038241  mov     r9, [rsp+98h+var_48]
0x140038246  mov     r8d, esi
0x140038249  mov     rdx, r12
0x14003824c  mov     rcx, r14
0x14003824f  mov     rax, [rax+48h]
0x140038253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038258  mov     ebx, eax
0x14003825a  call    cs:__imp_CoRevertToSelf
0x140038260  test    ebx, ebx
0x140038262  jns     short loc_140038288
0x140038264  jmp     short loc_140038270
0x140038266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003826b  mov     ebx, 80041006h
0x140038270  mov     [rsp+98h+var_70], rdi; struct IWbemObjectSink *
0x140038275  mov     [rsp+98h+var_78], ebx; int
0x140038279  lea     rdx, aPutclassasync; "PutClassAsync"
0x140038280  mov     rcx, rbp; this
0x140038283  call    ?SetStatus@CInterceptor_IWbemSyncProvider@@AEAAJPEAG00JPEAUIWbemObjectSink@@@Z; CInterceptor_IWbemSyncProvider::SetStatus(ushort *,ushort *,ushort *,long,IWbemObjectSink *)
0x140038288  mov     rax, [rdi]
0x14003828b  mov     rcx, rdi
0x14003828e  mov     rax, [rax+10h]
0x140038292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038297  jmp     short loc_14003829E
0x140038299  mov     ebx, 80041006h
0x14003829e  mov     rcx, [rsp+98h+var_48]
0x1400382a3  test    rcx, rcx
0x1400382a6  jz      short loc_1400382B4
0x1400382a8  mov     rax, [rcx]
0x1400382ab  mov     rax, [rax+10h]
0x1400382af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400382b4  test    ebx, ebx
0x1400382b6  jns     short loc_1400382C9
0x1400382b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400382be  mov     edx, ebx
0x1400382c0  mov     rcx, rax
0x1400382c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400382c9  lea     rax, WPP_GLOBAL_Control
0x1400382d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400382d7  cmp     rcx, rax
0x1400382da  jz      short loc_140038300
0x1400382dc  test    byte ptr [rcx+1Ch], 4
0x1400382e0  jz      short loc_140038300
0x1400382e2  cmp     byte ptr [rcx+19h], 2
0x1400382e6  jb      short loc_140038300
0x1400382e8  mov     edx, 58h ; 'X'
0x1400382ed  mov     r9d, ebx
0x1400382f0  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400382f7  mov     rcx, [rcx+10h]
0x1400382fb  call    WPP_SF_d
0x140038300  mov     eax, ebx
0x140038302  add     rsp, 60h
0x140038306  pop     r15
0x140038308  pop     r14
0x14003830a  pop     r12
0x14003830c  pop     rdi
0x14003830d  pop     rsi
0x14003830e  pop     rbp
0x14003830f  pop     rbx
0x140038310  retn
```
