# CServerObject_RawFactory::GetNonApartmentProvider(long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x140007698`
- end: `0x140007c66`
- name: `?GetNonApartmentProvider@CServerObject_RawFactory@@QEAAJJPEAUIWbemContext@@PEAU_GUID@@PEBG22AEBU3@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `1486`
- prototype: `__int64 __fastcall(CServerObject_RawFactory *this, int, struct IWbemContext *, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, const struct _GUID *, void **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003d0c0`

## callees

- `0x140005a14`
- `0x140007384`
- `0x140007698`
- `0x1400085ec`
- `0x14000a0f0`
- `0x14000a530`
- `0x14000aaf4`
- `0x1400234b8`
- `0x14002ffe4`
- `0x140030530`
- `0x140035a5c`
- `0x14003d5f4`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007899`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007875`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007ade`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007875`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140007ade`
- `wbemcomn!GetMemLogObject` at `0x140007b1f`
- `wbemcomn!GetMemLogObject` at `0x140007bdf`
- `wbemcomn!GetMemLogObject` at `0x140007b1f`
- `wbemcomn!GetMemLogObject` at `0x140007bdf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007b2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007bea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007b2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140007bea`
- `wbemcomn!?PublishProviderStarted@CPublishWMIOperationEvent@@SAJPEAGJ0K0@Z` at `0x1400078b4`
- `wbemcomn!?PublishProviderStarted@CPublishWMIOperationEvent@@SAJPEAGJ0K0@Z` at `0x1400078b4`
- `wbemcomn!?Init@CPublishWMIOperationEvent@@SAJXZ` at `0x140007882`
- `wbemcomn!?Init@CPublishWMIOperationEvent@@SAJXZ` at `0x140007882`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140007c5b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140007c5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_RawFactory::GetNonApartmentProvider(
        CServerObject_RawFactory *this,
        int a2,
        struct IWbemContext *a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        const struct _GUID *a8,
        void **a9,
        unsigned __int16 **a10)
{
  unsigned __int16 *v12; // r13
  int SyncProvider; // edi
  CInterceptor_IWbemServices_RestrictingInterceptor *v14; // rbx
  unsigned __int16 *v15; // r14
  DWORD CurrentProcessId; // eax
  struct IUnknown *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // r8
  _QWORD *v21; // rcx
  CMemoryLog *MemLogObject; // rax
  void *v23; // rax
  CMemoryLog *v24; // rax
  int v25; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h]
  struct _GUID *v27; // [rsp+50h] [rbp-B0h]
  struct IUnknown *v29; // [rsp+98h] [rbp-68h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-60h] BYREF
  void **v31; // [rsp+A8h] [rbp-58h]
  struct IWbemContext *v32; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v33; // [rsp+B8h] [rbp-48h]
  OLECHAR sz[80]; // [rsp+C0h] [rbp-40h] BYREF

  v32 = a3;
  v33 = a7;
  v31 = a9;
  lpMem = 0;
  if ( (int)ProviderSubSystem_Common_Globals::GetNamespacePath(
              *((struct IWbemPath **)this + 7),
              (unsigned __int16 **)&lpMem) < 0 )
  {
    SyncProvider = -2147217402;
LABEL_38:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, SyncProvider);
    goto LABEL_20;
  }
  v29 = 0;
  v12 = (unsigned __int16 *)lpMem;
  SyncProvider = CServerObject_RawFactory::CreateServerSide(
                   (struct CServerObject_ProviderRegistrationV1 *)a10,
                   a4,
                   a5,
                   a6,
                   (unsigned __int16 *)lpMem,
                   &v29);
  if ( SyncProvider >= 0 )
  {
    if ( *((_DWORD *)a10 + 420) == 1 )
    {
      v23 = operator new(0xC8u);
      lpMem = v23;
      if ( v23 )
        v14 = CInterceptor_IWbemServices_RestrictingInterceptor::CInterceptor_IWbemServices_RestrictingInterceptor(
                (CInterceptor_IWbemServices_RestrictingInterceptor *)v23,
                *((struct WmiAllocator **)this + 3),
                *((struct IWbemServices **)this + 9),
                (struct CServerObject_ProviderRegistrationV1 *)a10);
      else
        v14 = 0;
      if ( !v14 )
        goto LABEL_5;
      (*(void (__fastcall **)(CInterceptor_IWbemServices_RestrictingInterceptor *))(*(_QWORD *)v14 + 8LL))(v14);
      SyncProvider = CInterceptor_IWbemServices_RestrictingInterceptor::ServiceInitialize(v14);
    }
    else
    {
      v14 = (CInterceptor_IWbemServices_RestrictingInterceptor *)*((_QWORD *)this + 9);
      (*(void (__fastcall **)(CInterceptor_IWbemServices_RestrictingInterceptor *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( !v14 )
      {
LABEL_5:
        SyncProvider = -2147217402;
        goto LABEL_6;
      }
    }
    if ( SyncProvider < 0 )
    {
LABEL_32:
      (*(void (__fastcall **)(CInterceptor_IWbemServices_RestrictingInterceptor *))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_6:
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
      goto LABEL_8;
    }
    v18 = v29;
    if ( !v29 )
      goto LABEL_27;
    SyncProvider = CServerObject_RawFactory::InitializeServerProvider(
                     this,
                     (struct IWbemServices *)v14,
                     v29,
                     v12,
                     a2,
                     v32,
                     a4,
                     a5,
                     a6,
                     v33,
                     &IID_IUnknown,
                     v31,
                     (struct CServerObject_ProviderRegistrationV1 *)a10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v25 = SyncProvider;
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v18);
    }
    if ( SyncProvider >= 0 )
    {
LABEL_27:
      SyncProvider = CServerObject_RawFactory::CreateSyncProvider(
                       this,
                       (struct IWbemServices *)v14,
                       v18,
                       v12,
                       v25,
                       v32,
                       a4,
                       a5,
                       a6,
                       v26,
                       v27,
                       v31,
                       (struct CServerObject_ProviderRegistrationV1 *)a10);
      if ( SyncProvider >= 0 )
        goto LABEL_28;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
          (unsigned int)SyncProvider);
      }
    }
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, SyncProvider);
LABEL_28:
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
          (unsigned int)SyncProvider);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 5u )
        WPP_SF_SD(v21[2], 31, (unsigned int)WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, (_DWORD)v12, SyncProvider);
    }
    goto LABEL_32;
  }
LABEL_8:
  if ( a4 )
    StringFromGUID2(a4, sz, 78);
  v15 = (unsigned __int16 *)(a10 + 9);
  if ( SyncProvider >= 0 )
    WmiSetAndCommitObject(
      qword_140061370,
      1,
      v12,
      a10[8],
      (unsigned __int64)a5 & -(__int64)(*((_DWORD *)a10 + 414) != 0),
      (unsigned __int64)a6 & -(__int64)(*((_DWORD *)a10 + 415) != 0),
      (unsigned __int64)sz & -(__int64)(a4 != 0),
      (unsigned int)a10[6],
      a10 + 139);
  else
    WmiSetAndCommitObject(
      qword_140061378,
      1,
      v12,
      a10[8],
      (unsigned __int64)a5 & -(__int64)(*((_DWORD *)a10 + 414) != 0),
      (unsigned __int64)a6 & -(__int64)(*((_DWORD *)a10 + 415) != 0),
      (unsigned __int64)sz & -(__int64)(a4 != 0),
      (unsigned int)a10[6],
      a10 + 139);
  if ( a10[8] )
  {
    CPublishWMIOperationEvent::Init();
    if ( *((_DWORD *)a10 + 8) != 1 )
    {
      v15 = 0;
      if ( *((_DWORD *)a10 + 9) == 1 )
        v15 = (unsigned __int16 *)(a10 + 74);
    }
    CurrentProcessId = GetCurrentProcessId();
    CPublishWMIOperationEvent::PublishProviderStarted(a10[8], SyncProvider, L"wmiprvse.exe", CurrentProcessId, v15);
  }
  if ( SyncProvider < 0 )
    SyncProvider = -2147217389;
  operator delete(v12);
  if ( SyncProvider < 0 )
    goto LABEL_38;
LABEL_20:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)SyncProvider);
  }
  return (unsigned int)SyncProvider;
}

```

## disassembly

```asm
0x140007698  push    rbp
0x14000769a  push    rbx
0x14000769b  push    rsi
0x14000769c  push    rdi
0x14000769d  push    r12
0x14000769f  push    r13
0x1400076a1  push    r14
0x1400076a3  push    r15
0x1400076a5  lea     rbp, [rsp-78h]
0x1400076aa  sub     rsp, 178h
0x1400076b1  mov     rax, cs:__security_cookie
0x1400076b8  xor     rax, rsp
0x1400076bb  mov     [rbp+0B0h+var_50], rax
0x1400076bf  mov     r12, r9
0x1400076c2  mov     [rbp+0B0h+var_100], r8
0x1400076c6  mov     [rbp+0B0h+var_120], edx
0x1400076c9  mov     r15, rcx
0x1400076cc  mov     rbx, [rbp+0B0h+arg_20]
0x1400076d3  mov     [rbp+0B0h+var_128], rbx
0x1400076d7  mov     rdi, [rbp+0B0h+arg_28]
0x1400076de  mov     [rbp+0B0h+var_130], rdi
0x1400076e2  mov     rax, [rbp+0B0h+arg_30]
0x1400076e9  mov     [rbp+0B0h+var_F8], rax
0x1400076ed  mov     rax, [rbp+0B0h+arg_40]
0x1400076f4  mov     [rbp+0B0h+var_108], rax
0x1400076f8  mov     rsi, [rbp+0B0h+arg_48]
0x1400076ff  mov     [rbp+0B0h+lpMem], 0
0x140007707  lea     rdx, [rbp+0B0h+lpMem]; unsigned __int16 **
0x14000770b  mov     rcx, [rcx+38h]; struct IWbemPath *
0x14000770f  call    ?GetNamespacePath@ProviderSubSystem_Common_Globals@@SAJPEAUIWbemPath@@AEAPEAG@Z; ProviderSubSystem_Common_Globals::GetNamespacePath(IWbemPath *,ushort * &)
0x140007714  test    eax, eax
0x140007716  js      loc_140007B1A
0x14000771c  mov     [rbp+0B0h+var_118], 0
0x140007724  lea     rax, [rbp+0B0h+var_118]
0x140007728  mov     [rsp+1B0h+var_188], rax; struct IUnknown **
0x14000772d  mov     r13, [rbp+0B0h+lpMem]
0x140007731  mov     [rsp+1B0h+var_190], r13; unsigned __int16 *
0x140007736  mov     r9, rdi; unsigned __int16 *
0x140007739  mov     r8, rbx; unsigned __int16 *
0x14000773c  mov     rdx, r12; struct _GUID *
0x14000773f  mov     rcx, rsi; struct CServerObject_ProviderRegistrationV1 *
0x140007742  call    ?CreateServerSide@CServerObject_RawFactory@@SAJAEAVCServerObject_ProviderRegistrationV1@@PEAU_GUID@@PEBG2PEAGPEAPEAUIUnknown@@@Z; CServerObject_RawFactory::CreateServerSide(CServerObject_ProviderRegistrationV1 &,_GUID *,ushort const *,ushort const *,ushort *,IUnknown * *)
0x140007747  mov     edi, eax
0x140007749  test    eax, eax
0x14000774b  js      short loc_140007790
0x14000774d  cmp     dword ptr [rsi+690h], 1
0x140007754  jz      loc_140007B35
0x14000775a  mov     rbx, [r15+48h]
0x14000775e  mov     rax, [rbx]
0x140007761  mov     rcx, rbx
0x140007764  mov     rax, [rax+8]
0x140007768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000776d  test    rbx, rbx
0x140007770  jnz     loc_14000790D
0x140007776  mov     edi, 80041006h
0x14000777b  mov     rcx, [rbp+0B0h+var_118]
0x14000777f  test    rcx, rcx
0x140007782  jz      short loc_140007790
0x140007784  mov     rax, [rcx]
0x140007787  mov     rax, [rax+10h]
0x14000778b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007790  test    r12, r12
0x140007793  jnz     loc_140007C4E
0x140007799  mov     ecx, [rsi+24h]
0x14000779c  lea     r15, [rsi+250h]
0x1400077a3  lea     r14, [rsi+48h]
0x1400077a7  mov     edx, [rsi+20h]
0x1400077aa  mov     r9d, [rsi+67Ch]
0x1400077b1  mov     ebx, [rsi+678h]
0x1400077b7  xor     eax, eax
0x1400077b9  test    edi, edi
0x1400077bb  jns     loc_140007A2D
0x1400077c1  mov     r11, r15
0x1400077c4  cmp     ecx, 1
0x1400077c7  cmovnz  r11, rax
0x1400077cb  mov     r10, r14
0x1400077ce  cmp     edx, 1
0x1400077d1  cmovnz  r10, rax
0x1400077d5  xor     r9d, r9d
0x1400077d8  cmp     ecx, 1
0x1400077db  setnz   r9b
0x1400077df  dec     r9d
0x1400077e2  xor     r8d, r8d
0x1400077e5  cmp     edx, 1
0x1400077e8  setnz   r8b
0x1400077ec  dec     r8d
0x1400077ef  neg     r12
0x1400077f2  sbb     rdx, rdx
0x1400077f5  lea     rax, [rbp+0B0h+sz]
0x1400077f9  and     rdx, rax
0x1400077fc  mov     eax, [rsi+67Ch]
0x140007802  neg     eax
0x140007804  sbb     rcx, rcx
0x140007807  and     rcx, [rbp+0B0h+var_130]
0x14000780b  neg     ebx
0x14000780d  sbb     rax, rax
0x140007810  and     rax, [rbp+0B0h+var_128]
0x140007814  mov     [rsp+1B0h+var_138], edi
0x140007818  mov     r12d, [rsi+1Ch]
0x14000781c  mov     [rsp+1B0h+var_140], r12d
0x140007821  mov     r12d, [rsi+18h]
0x140007825  mov     [rsp+1B0h+var_148], r12d
0x14000782a  mov     [rsp+1B0h+var_150], r11
0x14000782f  mov     [rsp+1B0h+var_158], r10
0x140007834  mov     dword ptr [rsp+1B0h+var_160], r9d
0x140007839  mov     dword ptr [rsp+1B0h+var_168], r8d
0x14000783e  lea     r8, [rsi+458h]
0x140007845  mov     [rsp+1B0h+var_170], r8
0x14000784a  mov     r8, [rsi+30h]
0x14000784e  mov     [rsp+1B0h+var_178], r8
0x140007853  mov     [rsp+1B0h+rguid], rdx
0x140007858  mov     [rsp+1B0h+var_188], rcx
0x14000785d  mov     [rsp+1B0h+var_190], rax
0x140007862  mov     r9, [rsi+40h]
0x140007866  mov     r8, r13
0x140007869  mov     edx, 1
0x14000786e  mov     rcx, cs:qword_140061378
0x140007875  call    cs:__imp_WmiSetAndCommitObject
0x14000787b  cmp     qword ptr [rsi+40h], 0
0x140007880  jz      short loc_1400078BA
0x140007882  call    cs:__imp_?Init@CPublishWMIOperationEvent@@SAJXZ; CPublishWMIOperationEvent::Init(void)
0x140007888  cmp     dword ptr [rsi+20h], 1
0x14000788c  jz      short loc_140007899
0x14000788e  xor     r14d, r14d
0x140007891  cmp     dword ptr [rsi+24h], 1
0x140007895  cmovz   r14, r15
0x140007899  call    cs:__imp_GetCurrentProcessId
0x14000789f  mov     [rsp+1B0h+var_190], r14
0x1400078a4  mov     r9d, eax
0x1400078a7  lea     r8, aWmiprvseExe; "wmiprvse.exe"
0x1400078ae  mov     edx, edi
0x1400078b0  mov     rcx, [rsi+40h]
0x1400078b4  call    cs:__imp_?PublishProviderStarted@CPublishWMIOperationEvent@@SAJPEAGJ0K0@Z; CPublishWMIOperationEvent::PublishProviderStarted(ushort *,long,ushort *,ulong,ushort *)
0x1400078ba  mov     eax, 80041013h
0x1400078bf  test    edi, edi
0x1400078c1  cmovs   edi, eax
0x1400078c4  mov     rcx, r13; lpMem
0x1400078c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400078cc  test    edi, edi
0x1400078ce  js      loc_140007B1F
0x1400078d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078db  lea     rax, WPP_GLOBAL_Control
0x1400078e2  cmp     rcx, rax
0x1400078e5  jnz     loc_140007AE9
0x1400078eb  mov     eax, edi
0x1400078ed  mov     rcx, [rbp+0B0h+var_50]
0x1400078f1  xor     rcx, rsp; StackCookie
0x1400078f4  call    __security_check_cookie
0x1400078f9  add     rsp, 178h
0x140007900  pop     r15
0x140007902  pop     r14
0x140007904  pop     r13
0x140007906  pop     r12
0x140007908  pop     rdi
0x140007909  pop     rsi
0x14000790a  pop     rbx
0x14000790b  pop     rbp
0x14000790c  retn
0x14000790d  test    edi, edi
0x14000790f  js      loc_140007A19
0x140007915  mov     r14, [rbp+0B0h+var_118]
0x140007919  test    r14, r14
0x14000791c  jz      loc_1400079A4
0x140007922  mov     [rsp+1B0h+var_150], rsi; struct CServerObject_ProviderRegistrationV1 *
0x140007927  mov     rax, [rbp+0B0h+var_108]
0x14000792b  mov     [rsp+1B0h+var_158], rax; void **
0x140007930  lea     rax, IID_IUnknown
0x140007937  mov     [rsp+1B0h+var_160], rax; struct _GUID *
0x14000793c  mov     rax, [rbp+0B0h+var_F8]
0x140007940  mov     [rsp+1B0h+var_168], rax; unsigned __int16 *
0x140007945  mov     rax, [rbp+0B0h+var_130]
0x140007949  mov     [rsp+1B0h+var_170], rax; unsigned __int16 *
0x14000794e  mov     rax, [rbp+0B0h+var_128]
0x140007952  mov     [rsp+1B0h+var_178], rax; unsigned __int16 *
0x140007957  mov     [rsp+1B0h+rguid], r12; rguid
0x14000795c  mov     rax, [rbp+0B0h+var_100]
0x140007960  mov     [rsp+1B0h+var_188], rax; struct IWbemContext *
0x140007965  mov     eax, [rbp+0B0h+var_120]
0x140007968  mov     dword ptr [rsp+1B0h+var_190], eax; int
0x14000796c  mov     r9, r13; unsigned __int16 *
0x14000796f  mov     r8, r14; struct IUnknown *
0x140007972  mov     rdx, rbx; struct IWbemServices *
0x140007975  mov     rcx, r15; this
0x140007978  call    ?InitializeServerProvider@CServerObject_RawFactory@@QEAAJPEAUIWbemServices@@PEAUIUnknown@@PEAGJPEAUIWbemContext@@PEAU_GUID@@PEBG55AEBU5@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_RawFactory::InitializeServerProvider(IWbemServices *,IUnknown *,ushort *,long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)
0x14000797d  mov     edi, eax
0x14000797f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007986  lea     rax, WPP_GLOBAL_Control
0x14000798d  cmp     rcx, rax
0x140007990  jz      short loc_14000799C
0x140007992  test    byte ptr [rcx+1Ch], 4
0x140007996  jnz     loc_140007B89
0x14000799c  test    edi, edi
0x14000799e  js      loc_140007BDF
0x1400079a4  mov     [rsp+1B0h+var_150], rsi; struct CServerObject_ProviderRegistrationV1 *
0x1400079a9  mov     rax, [rbp+0B0h+var_108]
0x1400079ad  mov     [rsp+1B0h+var_158], rax; void **
0x1400079b2  mov     rax, [rbp+0B0h+var_130]
0x1400079b6  mov     [rsp+1B0h+var_170], rax; unsigned __int16 *
0x1400079bb  mov     rax, [rbp+0B0h+var_128]
0x1400079bf  mov     [rsp+1B0h+var_178], rax; unsigned __int16 *
0x1400079c4  mov     [rsp+1B0h+rguid], r12; struct _GUID *
0x1400079c9  mov     rax, [rbp+0B0h+var_100]
0x1400079cd  mov     [rsp+1B0h+var_188], rax; struct IWbemContext *
0x1400079d2  mov     r9, r13; unsigned __int16 *
0x1400079d5  mov     r8, r14; struct IUnknown *
0x1400079d8  mov     rdx, rbx; struct IWbemServices *
0x1400079db  mov     rcx, r15; this
0x1400079de  call    ?CreateSyncProvider@CServerObject_RawFactory@@QEAAJPEAUIWbemServices@@PEAUIUnknown@@PEAGJPEAUIWbemContext@@PEAU_GUID@@PEBG55AEBU5@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z; CServerObject_RawFactory::CreateSyncProvider(IWbemServices *,IUnknown *,ushort *,long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)
0x1400079e3  mov     edi, eax
0x1400079e5  test    eax, eax
0x1400079e7  js      loc_140007BA8
0x1400079ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079f4  lea     r14, WPP_GLOBAL_Control
0x1400079fb  cmp     rcx, r14
0x1400079fe  jz      short loc_140007A19
0x140007a00  test    byte ptr [rcx+1Ch], 4
0x140007a04  jnz     loc_140007BF5
0x140007a0a  cmp     rcx, r14
0x140007a0d  jz      short loc_140007A19
0x140007a0f  test    byte ptr [rcx+1Ch], 4
0x140007a13  jnz     loc_140007C23
0x140007a19  mov     rax, [rbx]
0x140007a1c  mov     rcx, rbx
0x140007a1f  mov     rax, [rax+10h]
0x140007a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a28  jmp     loc_14000777B
0x140007a2d  mov     rbx, r15
0x140007a30  cmp     ecx, 1
0x140007a33  cmovnz  rbx, rax
0x140007a37  mov     r11, r14
0x140007a3a  cmp     edx, 1
0x140007a3d  cmovnz  r11, rax
0x140007a41  xor     r10d, r10d
0x140007a44  cmp     ecx, 1
0x140007a47  setnz   r10b
0x140007a4b  dec     r10d
0x140007a4e  xor     r8d, r8d
0x140007a51  cmp     edx, 1
0x140007a54  setnz   r8b
0x140007a58  dec     r8d
0x140007a5b  neg     r12
0x140007a5e  sbb     rdx, rdx
0x140007a61  lea     rax, [rbp+0B0h+sz]
0x140007a65  and     rdx, rax
0x140007a68  neg     r9d
0x140007a6b  sbb     rcx, rcx
0x140007a6e  and     rcx, [rbp+0B0h+var_130]
0x140007a72  mov     eax, [rsi+678h]
0x140007a78  neg     eax
0x140007a7a  sbb     rax, rax
0x140007a7d  and     rax, [rbp+0B0h+var_128]
0x140007a81  mov     r12d, [rsi+1Ch]
0x140007a85  mov     [rsp+1B0h+var_140], r12d
0x140007a8a  mov     r12d, [rsi+18h]
0x140007a8e  mov     [rsp+1B0h+var_148], r12d
0x140007a93  mov     [rsp+1B0h+var_150], rbx
0x140007a98  mov     [rsp+1B0h+var_158], r11
0x140007a9d  mov     dword ptr [rsp+1B0h+var_160], r10d
0x140007aa2  mov     dword ptr [rsp+1B0h+var_168], r8d
0x140007aa7  lea     r8, [rsi+458h]
0x140007aae  mov     [rsp+1B0h+var_170], r8
0x140007ab3  mov     r8, [rsi+30h]
0x140007ab7  mov     [rsp+1B0h+var_178], r8
0x140007abc  mov     [rsp+1B0h+rguid], rdx
0x140007ac1  mov     [rsp+1B0h+var_188], rcx
0x140007ac6  mov     [rsp+1B0h+var_190], rax
0x140007acb  mov     r9, [rsi+40h]
0x140007acf  mov     r8, r13
0x140007ad2  mov     edx, 1
0x140007ad7  mov     rcx, cs:qword_140061370
0x140007ade  call    cs:__imp_WmiSetAndCommitObject
0x140007ae4  jmp     loc_14000787B
0x140007ae9  test    byte ptr [rcx+1Ch], 4
0x140007aed  jz      loc_1400078EB
0x140007af3  cmp     byte ptr [rcx+19h], 2
0x140007af7  jb      loc_1400078EB
0x140007afd  mov     edx, 20h ; ' '
0x140007b02  mov     r9d, edi
0x140007b05  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140007b0c  mov     rcx, [rcx+10h]
0x140007b10  call    WPP_SF_d
0x140007b15  jmp     loc_1400078EB
0x140007b1a  mov     edi, 80041006h
0x140007b1f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140007b25  mov     edx, edi
0x140007b27  mov     rcx, rax
0x140007b2a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140007b30  jmp     loc_1400078D4
0x140007b35  mov     ecx, 0C8h; dwBytes
0x140007b3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007b3f  mov     [rbp+0B0h+lpMem], rax
0x140007b43  test    rax, rax
0x140007b46  jz      short loc_140007B60
0x140007b48  mov     r9, rsi; struct CServerObject_ProviderRegistrationV1 *
0x140007b4b  mov     r8, [r15+48h]; struct IWbemServices *
0x140007b4f  mov     rdx, [r15+18h]; struct WmiAllocator *
0x140007b53  mov     rcx, rax; this
0x140007b56  call    ??0CInterceptor_IWbemServices_RestrictingInterceptor@@QEAA@AEAVWmiAllocator@@PEAUIWbemServices@@AEAVCServerObject_ProviderRegistrationV1@@@Z; CInterceptor_IWbemServices_RestrictingInterceptor::CInterceptor_IWbemServices_RestrictingInterceptor(WmiAllocator &,IWbemServices *,CServerObject_ProviderRegistrationV1 &)
0x140007b5b  mov     rbx, rax
0x140007b5e  jmp     short loc_140007B62
  ... truncated ...
```
