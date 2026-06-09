# CServerObject_RawFactory::CreateSyncProvider(IWbemServices *,IUnknown *,ushort *,long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x14000aaf4`
- end: `0x14000b008`
- name: `?CreateSyncProvider@CServerObject_RawFactory@@QEAAJPEAUIWbemServices@@PEAUIUnknown@@PEAGJPEAUIWbemContext@@PEAU_GUID@@PEBG55AEBU5@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `1300`
- prototype: `__int64 __fastcall(struct WmiAllocator **this, struct IWbemServices *, struct IUnknown *, unsigned __int16 *, int, struct IWbemContext *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, struct CServerObject_ProviderRegistrationV1 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007698`

## callees

- `0x140006d34`
- `0x14000a530`
- `0x14000aaf4`
- `0x14001ebc4`
- `0x14001eec0`
- `0x1400234b8`
- `0x14003cfd8`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000ae8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000ae8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000adb6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000adb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000acb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000acb7`
- `wbemcomn!GetMemLogObject` at `0x14000acce`
- `wbemcomn!GetMemLogObject` at `0x14000aee3`
- `wbemcomn!GetMemLogObject` at `0x14000acce`
- `wbemcomn!GetMemLogObject` at `0x14000aee3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000acd9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000aeee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000acd9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000aeee`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000ab63`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000ab63`

## pseudocode

```c
__int64 __fastcall CServerObject_RawFactory::CreateSyncProvider(
        struct WmiAllocator **this,
        struct IWbemServices *a2,
        struct IUnknown *a3,
        unsigned __int16 *a4,
        int a5,
        struct IWbemContext *a6,
        struct _GUID *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        const struct _GUID *a11,
        void **a12,
        struct CServerObject_ProviderRegistrationV1 *a13)
{
  CInterceptor_IWbemSyncProvider *v16; // rax
  CInterceptor_IWbemSyncProvider *v17; // rdi
  bool v18; // zf
  void (*v19)(void); // rax
  int v20; // ebx
  CServerObject_ProviderInitSink *v21; // rax
  struct _SECURITY_DESCRIPTOR *v22; // rdx
  CServerObject_ProviderInitSink *inited; // rax
  CServerObject_ProviderInitSink *v24; // rsi
  int v25; // r14d
  HANDLE EventW; // rax
  CMemoryLog *MemLogObject; // rax
  CInterceptor_IWbemProviderInitSink *v28; // rax
  CInterceptor_IWbemProviderInitSink *v29; // r14
  _QWORD *v30; // rcx
  void *v31; // rcx
  CMemoryLog *v33; // rax
  __int64 v34; // [rsp+60h] [rbp-51h] BYREF
  CInterceptor_IWbemSyncProvider *v35; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int64 v36; // [rsp+70h] [rbp-41h]
  unsigned __int64 v37; // [rsp+78h] [rbp-39h]
  unsigned __int16 *v38; // [rsp+80h] [rbp-31h]
  struct _GUID *v39; // [rsp+88h] [rbp-29h]
  CServerObject_ProviderInitSink *v40; // [rsp+90h] [rbp-21h]
  GUID pguid; // [rsp+98h] [rbp-19h] BYREF

  v38 = a4;
  v37 = (unsigned __int64)a8;
  v36 = (unsigned __int64)a9;
  v39 = a7;
  pguid = 0;
  if ( CoCreateGuid(&pguid) < 0 )
  {
    v20 = -2147217398;
    goto LABEL_41;
  }
  v16 = (CInterceptor_IWbemSyncProvider *)operator new(0x368u);
  v35 = v16;
  if ( v16 )
    v17 = CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(
            v16,
            this[3],
            (__int64)a3,
            (__int64)a2,
            ProviderSubSystem_Globals::s_SyncProviderController,
            a6,
            (__int64)a13,
            (__int64)&pguid);
  else
    v17 = 0;
  if ( !v17 )
  {
    v20 = -2147217402;
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, v17, a3);
  }
  (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)v17 + 8LL))(v17);
  v35 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController + 48LL))(ProviderSubSystem_Globals::s_SyncProviderController);
  v18 = (*(unsigned int (__fastcall **)(__int64, __int64, CInterceptor_IWbemSyncProvider **))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController
                                                                                            + 64LL))(
          ProviderSubSystem_Globals::s_SyncProviderController,
          (__int64)v17 + 176,
          &v35) == 0;
  v19 = *(void (**)(void))(*(_QWORD *)ProviderSubSystem_Globals::s_SyncProviderController + 56LL);
  if ( !v18 )
  {
    v19();
    v20 = -2147217402;
    goto LABEL_33;
  }
  v19();
  v34 = 0;
  v20 = (**(__int64 (__fastcall ***)(CInterceptor_IWbemSyncProvider *, GUID *, __int64 *))v17)(
          v17,
          &IID__IWmiProviderInitialize,
          &v34);
  if ( v20 >= 0 )
  {
    v21 = (CServerObject_ProviderInitSink *)operator new(0x28u);
    v40 = v21;
    if ( !v21
      || (inited = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(v21, v22), (v24 = inited) == 0) )
    {
      v20 = -2147217402;
      goto LABEL_32;
    }
    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)inited + 8LL))(inited);
    v25 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v24 + 2) = EventW;
    v20 = -2147217402;
    if ( !EventW )
    {
      v25 = -2147217402;
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids,
        (unsigned int)v25);
    }
    if ( v25 < 0 )
    {
      v20 = v25;
    }
    else
    {
      v28 = (CInterceptor_IWbemProviderInitSink *)operator new(0x20u);
      v40 = v28;
      if ( v28 )
        v29 = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
                v28,
                (struct IWbemProviderInitSink *)v24);
      else
        v29 = 0;
      if ( v29 )
      {
        (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v29 + 8LL))(v29);
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemContext *, struct _GUID *, unsigned __int64, unsigned __int64, unsigned __int16 *, _QWORD, _QWORD, CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v34 + 24LL))(
                v34,
                0,
                a6,
                v39,
                v37 & -(__int64)(*((_DWORD *)a13 + 414) != 0),
                v36 & -(__int64)(*((_DWORD *)a13 + 415) != 0),
                v38,
                0,
                0,
                v29);
        if ( v20 >= 0 )
        {
          if ( WaitForSingleObject(*((HANDLE *)v24 + 2), *((_DWORD *)a13 + 430)) == 258 )
            *((_DWORD *)v24 + 6) = -2147217389;
          v20 = *((_DWORD *)v24 + 6);
          if ( v20 >= 0 )
          {
            v20 = (**(__int64 (__fastcall ***)(CInterceptor_IWbemSyncProvider *, GUID *, void **))v17)(
                    v17,
                    &IID_IUnknown,
                    a12);
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                (unsigned int)v20);
              v30 = WPP_GLOBAL_Control;
            }
            if ( v20 < 0 )
              goto LABEL_28;
            v20 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v17 + 16) + 40LL))((__int64)v17 + 128);
          }
        }
        v30 = WPP_GLOBAL_Control;
LABEL_28:
        if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 4) != 0 && *((_BYTE *)v30 + 25) >= 5u )
          WPP_SF_d(v30[2], 19, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, (unsigned int)v20);
        (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
    (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v24 + 16LL))(v24);
LABEL_32:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
LABEL_33:
  *((_DWORD *)v17 + 131) = v20;
  _InterlockedExchange((volatile __int32 *)v17 + 130, 1);
  v31 = (void *)*((_QWORD *)v17 + 66);
  if ( v31 )
    SetEvent(v31);
  (*(void (__fastcall **)(CInterceptor_IWbemSyncProvider *))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_36:
  if ( v20 < 0 )
  {
LABEL_41:
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, v20);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
      (unsigned int)v20);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14000aaf4  push    rbp
0x14000aaf6  push    rbx
0x14000aaf7  push    rsi
0x14000aaf8  push    rdi
0x14000aaf9  push    r12
0x14000aafb  push    r13
0x14000aafd  push    r14
0x14000aaff  push    r15
0x14000ab01  lea     rbp, [rsp-7]
0x14000ab06  sub     rsp, 0B8h
0x14000ab0d  mov     rax, cs:__security_cookie
0x14000ab14  xor     rax, rsp
0x14000ab17  mov     [rbp+3Fh+var_48], rax
0x14000ab1b  mov     [rbp+3Fh+var_70], r9
0x14000ab1f  mov     rbx, r8
0x14000ab22  mov     rsi, rdx
0x14000ab25  mov     rdi, rcx
0x14000ab28  mov     rax, [rbp+3Fh+arg_38]
0x14000ab2f  mov     [rbp+3Fh+var_78], rax
0x14000ab33  mov     rax, [rbp+3Fh+arg_40]
0x14000ab3a  mov     [rbp+3Fh+var_80], rax
0x14000ab3e  mov     r12, [rbp+3Fh+arg_28]
0x14000ab42  mov     rax, [rbp+3Fh+arg_30]
0x14000ab46  mov     [rbp+3Fh+var_68], rax
0x14000ab4a  mov     r13, [rbp+3Fh+arg_58]
0x14000ab51  mov     r15, [rbp+3Fh+arg_60]
0x14000ab58  xorps   xmm0, xmm0
0x14000ab5b  movups  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x14000ab5f  lea     rcx, [rbp+3Fh+pguid]; pguid
0x14000ab63  call    cs:__imp_CoCreateGuid
0x14000ab69  lea     r14, WPP_GLOBAL_Control
0x14000ab70  test    eax, eax
0x14000ab72  js      loc_14000AEDE
0x14000ab78  mov     ecx, 368h; dwBytes
0x14000ab7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ab82  mov     [rbp+3Fh+var_88], rax
0x14000ab86  test    rax, rax
0x14000ab89  jz      loc_14000AF17
0x14000ab8f  mov     rcx, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14000ab96  lea     rdx, [rbp+3Fh+pguid]
0x14000ab9a  mov     [rsp+0F0h+var_B8], rdx; __int64
0x14000ab9f  mov     [rsp+0F0h+var_C0], r15; __int64
0x14000aba4  mov     [rsp+0F0h+var_C8], r12; __int64
0x14000aba9  mov     [rsp+0F0h+var_D0], rcx; __int64
0x14000abae  mov     r9, rsi
0x14000abb1  mov     r8, rbx
0x14000abb4  mov     rdx, [rdi+18h]
0x14000abb8  mov     rcx, rax; this
0x14000abbb  call    ??0CInterceptor_IWbemSyncProvider@@QEAA@AEAVWmiAllocator@@PEAUIUnknown@@PEAUIWbemServices@@PEAV?$WmiContainerController@U_GUID@@@@PEAUIWbemContext@@AEAVCServerObject_ProviderRegistrationV1@@AEAU_GUID@@@Z; CInterceptor_IWbemSyncProvider::CInterceptor_IWbemSyncProvider(WmiAllocator &,IUnknown *,IWbemServices *,WmiContainerController<_GUID> *,IWbemContext *,CServerObject_ProviderRegistrationV1 &,_GUID &)
0x14000abc0  mov     rdi, rax
0x14000abc3  test    rdi, rdi
0x14000abc6  jz      loc_14000AF00
0x14000abcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000abd3  cmp     rcx, r14
0x14000abd6  jz      short loc_14000ABE2
0x14000abd8  test    byte ptr [rcx+1Ch], 4
0x14000abdc  jnz     loc_14000AF1E
0x14000abe2  mov     rax, [rdi]
0x14000abe5  mov     rcx, rdi
0x14000abe8  mov     rax, [rax+8]
0x14000abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abf1  mov     [rbp+3Fh+var_88], 0
0x14000abf9  mov     rcx, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14000ac00  mov     rax, [rcx]
0x14000ac03  mov     rax, [rax+30h]
0x14000ac07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac0c  mov     rcx, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14000ac13  mov     rax, [rcx]
0x14000ac16  lea     rdx, [rdi+0B0h]
0x14000ac1d  lea     r8, [rbp+3Fh+var_88]
0x14000ac21  mov     rax, [rax+40h]
0x14000ac25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac2a  mov     rcx, cs:?s_SyncProviderController@ProviderSubSystem_Globals@@2PEAV?$WmiContainerController@U_GUID@@@@EA; WmiContainerController<_GUID> * ProviderSubSystem_Globals::s_SyncProviderController
0x14000ac31  test    eax, eax
0x14000ac33  mov     rax, [rcx]
0x14000ac36  mov     rax, [rax+38h]
0x14000ac3a  jnz     loc_14000AFD2
0x14000ac40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac45  mov     [rbp+3Fh+var_90], 0
0x14000ac4d  mov     rax, [rdi]
0x14000ac50  lea     r8, [rbp+3Fh+var_90]
0x14000ac54  lea     rdx, IID__IWmiProviderInitialize
0x14000ac5b  mov     rcx, rdi
0x14000ac5e  mov     rax, [rax]
0x14000ac61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac66  mov     ebx, eax
0x14000ac68  test    eax, eax
0x14000ac6a  js      loc_14000AE70
0x14000ac70  mov     ecx, 28h ; '('; dwBytes
0x14000ac75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ac7a  mov     [rbp+3Fh+var_60], rax
0x14000ac7e  test    rax, rax
0x14000ac81  jz      loc_14000AEF6
0x14000ac87  mov     rcx, rax; this
0x14000ac8a  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x14000ac8f  mov     rsi, rax
0x14000ac92  test    rax, rax
0x14000ac95  jz      loc_14000AEF6
0x14000ac9b  mov     rcx, [rax]
0x14000ac9e  mov     rax, [rcx+8]
0x14000aca2  mov     rcx, rsi
0x14000aca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acaa  xor     r14d, r14d
0x14000acad  xor     r9d, r9d; lpName
0x14000acb0  xor     r8d, r8d; bInitialState
0x14000acb3  xor     edx, edx; bManualReset
0x14000acb5  xor     ecx, ecx; lpEventAttributes
0x14000acb7  call    cs:__imp_CreateEventW
0x14000acbd  mov     [rsi+10h], rax
0x14000acc1  mov     ebx, 80041006h
0x14000acc6  test    rax, rax
0x14000acc9  jnz     short loc_14000ACDF
0x14000accb  mov     r14d, ebx
0x14000acce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000acd4  mov     edx, ebx
0x14000acd6  mov     rcx, rax
0x14000acd9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000acdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ace6  lea     rax, WPP_GLOBAL_Control
0x14000aced  cmp     rcx, rax
0x14000acf0  jz      short loc_14000ACFC
0x14000acf2  test    byte ptr [rcx+1Ch], 4
0x14000acf6  jnz     loc_14000AF4A
0x14000acfc  test    r14d, r14d
0x14000acff  js      loc_14000AF07
0x14000ad05  mov     ecx, 20h ; ' '; dwBytes
0x14000ad0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ad0f  mov     [rbp+3Fh+var_60], rax
0x14000ad13  test    rax, rax
0x14000ad16  jz      loc_14000AF0F
0x14000ad1c  mov     rdx, rsi; struct IWbemProviderInitSink *
0x14000ad1f  mov     rcx, rax; this
0x14000ad22  call    ??0CInterceptor_IWbemProviderInitSink@@QEAA@PEAUIWbemProviderInitSink@@@Z; CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(IWbemProviderInitSink *)
0x14000ad27  mov     r14, rax
0x14000ad2a  test    r14, r14
0x14000ad2d  jz      loc_14000AE4A
0x14000ad33  mov     rax, [r14]
0x14000ad36  mov     rcx, r14
0x14000ad39  mov     rax, [rax+8]
0x14000ad3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad42  mov     rcx, [rbp+3Fh+var_90]
0x14000ad46  mov     rdx, [rcx]
0x14000ad49  mov     eax, [r15+67Ch]
0x14000ad50  neg     eax
0x14000ad52  sbb     r11, r11
0x14000ad55  and     r11, [rbp+3Fh+var_80]
0x14000ad59  mov     eax, [r15+678h]
0x14000ad60  neg     eax
0x14000ad62  sbb     r10, r10
0x14000ad65  and     r10, [rbp+3Fh+var_78]
0x14000ad69  mov     rax, [rdx+18h]
0x14000ad6d  mov     [rsp+0F0h+var_A8], r14
0x14000ad72  mov     [rsp+0F0h+var_B0], 0
0x14000ad7b  mov     [rsp+0F0h+var_B8], 0
0x14000ad84  mov     rdx, [rbp+3Fh+var_70]
0x14000ad88  mov     [rsp+0F0h+var_C0], rdx
0x14000ad8d  mov     [rsp+0F0h+var_C8], r11
0x14000ad92  mov     [rsp+0F0h+var_D0], r10
0x14000ad97  mov     r9, [rbp+3Fh+var_68]
0x14000ad9b  mov     r8, r12
0x14000ad9e  xor     edx, edx
0x14000ada0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ada5  mov     ebx, eax
0x14000ada7  test    eax, eax
0x14000ada9  js      short loc_14000AE1E
0x14000adab  mov     edx, [r15+6B8h]; dwMilliseconds
0x14000adb2  mov     rcx, [rsi+10h]; hHandle
0x14000adb6  call    cs:__imp_WaitForSingleObject
0x14000adbc  cmp     eax, 102h
0x14000adc1  jz      loc_14000AF71
0x14000adc7  mov     ebx, [rsi+18h]
0x14000adca  test    ebx, ebx
0x14000adcc  js      short loc_14000AE1E
0x14000adce  mov     rax, [rdi]
0x14000add1  mov     r8, r13
0x14000add4  lea     rdx, IID_IUnknown
0x14000addb  mov     rcx, rdi
0x14000adde  mov     rax, [rax]
0x14000ade1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ade6  mov     ebx, eax
0x14000ade8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adef  lea     rax, WPP_GLOBAL_Control
0x14000adf6  cmp     rcx, rax
0x14000adf9  jz      short loc_14000AE05
0x14000adfb  test    byte ptr [rcx+1Ch], 4
0x14000adff  jnz     loc_14000AF7D
0x14000ae05  test    ebx, ebx
0x14000ae07  js      short loc_14000AE25
0x14000ae09  lea     rcx, [rdi+80h]
0x14000ae10  mov     rax, [rcx]
0x14000ae13  mov     rax, [rax+28h]
0x14000ae17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae1c  mov     ebx, eax
0x14000ae1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae25  lea     rax, WPP_GLOBAL_Control
0x14000ae2c  cmp     rcx, rax
0x14000ae2f  jz      short loc_14000AE3B
0x14000ae31  test    byte ptr [rcx+1Ch], 4
0x14000ae35  jnz     loc_14000AFAB
0x14000ae3b  mov     rax, [r14]
0x14000ae3e  mov     rcx, r14
0x14000ae41  mov     rax, [rax+10h]
0x14000ae45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae4a  mov     rax, [rsi]
0x14000ae4d  mov     rcx, rsi
0x14000ae50  mov     rax, [rax+10h]
0x14000ae54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae59  lea     r14, WPP_GLOBAL_Control
0x14000ae60  mov     rcx, [rbp+3Fh+var_90]
0x14000ae64  mov     rax, [rcx]
0x14000ae67  mov     rax, [rax+10h]
0x14000ae6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae70  mov     [rdi+20Ch], ebx
0x14000ae76  mov     eax, 1
0x14000ae7b  xchg    eax, [rdi+208h]
0x14000ae81  mov     rcx, [rdi+210h]; hEvent
0x14000ae88  test    rcx, rcx
0x14000ae8b  jz      short loc_14000AE93
0x14000ae8d  call    cs:__imp_SetEvent
0x14000ae93  mov     rax, [rdi]
0x14000ae96  mov     rcx, rdi
0x14000ae99  mov     rax, [rax+10h]
0x14000ae9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aea2  test    ebx, ebx
0x14000aea4  js      short loc_14000AEE3
0x14000aea6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aead  cmp     rcx, r14
0x14000aeb0  jz      short loc_14000AEBC
0x14000aeb2  test    byte ptr [rcx+1Ch], 4
0x14000aeb6  jnz     loc_14000AFE1
0x14000aebc  mov     eax, ebx
0x14000aebe  mov     rcx, [rbp+3Fh+var_48]
0x14000aec2  xor     rcx, rsp; StackCookie
0x14000aec5  call    __security_check_cookie
0x14000aeca  add     rsp, 0B8h
0x14000aed1  pop     r15
0x14000aed3  pop     r14
0x14000aed5  pop     r13
0x14000aed7  pop     r12
0x14000aed9  pop     rdi
0x14000aeda  pop     rsi
0x14000aedb  pop     rbx
0x14000aedc  pop     rbp
0x14000aedd  retn
0x14000aede  mov     ebx, 8004100Ah
0x14000aee3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14000aee9  mov     edx, ebx
0x14000aeeb  mov     rcx, rax
0x14000aeee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14000aef4  jmp     short loc_14000AEA6
0x14000aef6  mov     ebx, 80041006h
0x14000aefb  jmp     loc_14000AE60
0x14000af00  mov     ebx, 80041006h
0x14000af05  jmp     short loc_14000AEA2
0x14000af07  mov     ebx, r14d
0x14000af0a  jmp     loc_14000AE4A
0x14000af0f  xor     r14d, r14d
0x14000af12  jmp     loc_14000AD2A
0x14000af17  xor     edi, edi
0x14000af19  jmp     loc_14000ABC3
0x14000af1e  cmp     byte ptr [rcx+19h], 5
0x14000af22  jb      loc_14000ABE2
0x14000af28  mov     edx, 11h
0x14000af2d  mov     [rsp+0F0h+var_D0], rbx
0x14000af32  mov     r9, rdi
0x14000af35  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14000af3c  mov     rcx, [rcx+10h]
0x14000af40  call    WPP_SF_qq
0x14000af45  jmp     loc_14000ABE2
0x14000af4a  cmp     byte ptr [rcx+19h], 2
0x14000af4e  jb      loc_14000ACFC
0x14000af54  mov     edx, 0Ah
0x14000af59  mov     r9d, r14d
0x14000af5c  lea     r8, WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids
0x14000af63  mov     rcx, [rcx+10h]
0x14000af67  call    WPP_SF_d
0x14000af6c  jmp     loc_14000ACFC
0x14000af71  mov     dword ptr [rsi+18h], 80041013h
0x14000af78  jmp     loc_14000ADC7
0x14000af7d  cmp     byte ptr [rcx+19h], 5
0x14000af81  jb      loc_14000AE05
0x14000af87  mov     edx, 12h
0x14000af8c  mov     r9d, ebx
0x14000af8f  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14000af96  mov     rcx, [rcx+10h]
0x14000af9a  call    WPP_SF_d
0x14000af9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afa6  jmp     loc_14000AE05
0x14000afab  cmp     byte ptr [rcx+19h], 5
0x14000afaf  jb      loc_14000AE3B
0x14000afb5  mov     edx, 13h
0x14000afba  mov     r9d, ebx
0x14000afbd  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x14000afc4  mov     rcx, [rcx+10h]
0x14000afc8  call    WPP_SF_d
0x14000afcd  jmp     loc_14000AE3B
0x14000afd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afd7  mov     ebx, 80041006h
0x14000afdc  jmp     loc_14000AE70
0x14000afe1  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
