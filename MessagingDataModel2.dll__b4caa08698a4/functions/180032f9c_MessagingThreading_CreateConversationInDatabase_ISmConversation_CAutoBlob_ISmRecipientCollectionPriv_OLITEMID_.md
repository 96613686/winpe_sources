# MessagingThreading::CreateConversationInDatabase(ISmConversation *,CAutoBlob &,ISmRecipientCollectionPriv *,OLITEMID,bool,_FILETIME const &,ISmConversation * *)

- ea: `0x180032f9c`
- end: `0x1800332f6`
- name: `?CreateConversationInDatabase@MessagingThreading@@QEAAJPEAUISmConversation@@AEAVCAutoBlob@@PEAVISmRecipientCollectionPriv@@UOLITEMID@@_NAEBU_FILETIME@@PEAPEAU2@@Z`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180032848`
- `0x180037640`

## callees

- `0x180005c50`
- `0x18000be18`
- `0x18000d1e4`
- `0x1800179ac`
- `0x1800187fc`
- `0x18002e638`
- `0x180032f9c`
- `0x180033bf0`
- `0x180033c28`
- `0x18003d894`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003305e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003305e`
- `CEMAPI!MAPIFreeBuffer` at `0x180033280`
- `CEMAPI!MAPIFreeBuffer` at `0x1800332b1`
- `CEMAPI!MAPIFreeBuffer` at `0x180033280`
- `CEMAPI!MAPIFreeBuffer` at `0x1800332b1`
- `CEMAPI!HrSetOneProp` at `0x180033214`
- `CEMAPI!HrSetOneProp` at `0x180033214`

## string_xrefs

- `0x180032fef`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180033073`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800330cb`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x18003312b`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180033224`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180033260`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`

## pseudocode

```c
__int64 __fastcall MessagingThreading::CreateConversationInDatabase(
        __int64 a1,
        struct ISmConversation *a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5,
        unsigned __int8 a6,
        unsigned __int64 *a7,
        struct ISmConversation **a8)
{
  __int64 v11; // rcx
  struct ISmStore *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  HRESULT v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // xmm0_8
  HRESULT v23; // eax
  void **v24; // rax
  int Props; // eax
  int v27; // [rsp+20h] [rbp-B1h]
  __int64 v29; // [rsp+50h] [rbp-81h] BYREF
  int v30; // [rsp+58h] [rbp-79h]
  LPMAPIPROP lpMapiProp; // [rsp+60h] [rbp-71h] BYREF
  __int64 v32; // [rsp+68h] [rbp-69h] BYREF
  unsigned int v33; // [rsp+70h] [rbp-61h] BYREF
  unsigned int v34; // [rsp+74h] [rbp-5Dh] BYREF
  int v35; // [rsp+78h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-51h] BYREF
  int v37; // [rsp+88h] [rbp-49h] BYREF
  __int64 v38; // [rsp+90h] [rbp-41h] BYREF
  struct _SPropValue Prop; // [rsp+98h] [rbp-39h] BYREF
  GUID pguid; // [rsp+B0h] [rbp-21h] BYREF

  if ( !CSmStoreTransaction::IsOwned((struct ISmStore *)a1) )
  {
    Log_AssertionEvent_13(v11, "onecoreuap\\base\\appmodel\\messagingom\\src\\threading.cpp", 692);
    if ( !CSmStoreTransaction::IsOwned(v12) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v13 = *(_QWORD *)a2;
  v38 = 0;
  v14 = (*(__int64 (__fastcall **)(struct ISmConversation *, __int64 *))(v13 + 88))(a2, &v38);
  v15 = v14;
  if ( v14 >= 0 )
  {
    (*(void (__fastcall **)(struct ISmConversation *))(*(_QWORD *)a2 + 8LL))(a2);
    v15 = 0;
    *a8 = a2;
    goto LABEL_27;
  }
  if ( v14 != -2147467259 )
    goto LABEL_27;
  pguid = GUID_NULL;
  v16 = CoCreateGuid(&pguid);
  v15 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent_14(v16);
    goto LABEL_27;
  }
  v17 = *(_QWORD *)(a1 + 16);
  lpMapiProp = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *, _QWORD, _DWORD, LPMAPIPROP *))(*(_QWORD *)v17
                                                                                                  + 160LL))(
          v17,
          0,
          16,
          &pguid,
          0,
          0,
          &lpMapiProp);
  v15 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_14(v18);
LABEL_11:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
    goto LABEL_27;
  }
  v32 = 0;
  ATL::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>(
    &v32,
    a2);
  v19 = *a4;
  v37 = 0;
  v34 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, int *, unsigned int *))(v19 + 104))(a4, &v37, &v34);
  v15 = v20;
  if ( v20 < 0 )
    goto LABEL_13;
  v21 = *a4;
  v33 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v21 + 56))(a4, &v33);
  v15 = v20;
  if ( v20 < 0 )
    goto LABEL_13;
  v35 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v32 + 408LL))(
          v32,
          a6,
          v34,
          v33,
          &v35);
  v15 = v20;
  if ( v20 < 0
    || (v22 = *a5,
        v30 = *((_DWORD *)a5 + 2),
        LOBYTE(v27) = v35 == 1,
        v29 = v22,
        v20 = CSmConversation::WriteConversationProperties(v32, lpMapiProp, a3, a4, v27, &v29),
        v15 = v20,
        v20 < 0) )
  {
LABEL_13:
    Log_HREvent_14(v20);
LABEL_14:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    goto LABEL_11;
  }
  Prop.Value = (union _PV)*a7;
  Prop.dwAlignPad = 0;
  Prop.ulPropTag = -2103836608;
  v23 = HrSetOneProp(lpMapiProp, &Prop);
  if ( v23 < 0 )
    Log_HREvent_14(v23);
  pv = 0;
  v24 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&pv);
  Props = GetProps(lpMapiProp, &CSmConversation::s_rgColumns, (struct _SPropValue **)v24);
  v15 = Props;
  if ( Props < 0
    || (Props = CSmConversation::CreateInstance(*(struct ISmStorePriv **)a1, (const struct _SPropValue *const)pv, a8),
        v15 = Props,
        Props < 0) )
  {
    Log_HREvent_14(Props);
    if ( pv )
      MAPIFreeBuffer(pv);
    goto LABEL_14;
  }
  if ( pv )
    MAPIFreeBuffer(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
  v15 = 0;
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
  return v15;
}

```

## disassembly

```asm
0x180032f9c  push    rbp
0x180032f9e  push    rbx
0x180032f9f  push    rsi
0x180032fa0  push    rdi
0x180032fa1  push    r12
0x180032fa3  push    r13
0x180032fa5  push    r14
0x180032fa7  push    r15
0x180032fa9  lea     rbp, [rsp-7]
0x180032fae  sub     rsp, 0D8h
0x180032fb5  mov     rax, cs:__security_cookie
0x180032fbc  xor     rax, rsp
0x180032fbf  mov     [rbp+3Fh+var_50], rax
0x180032fc3  mov     r13, [rbp+3Fh+arg_20]
0x180032fc7  mov     rsi, r9
0x180032fca  mov     r12, [rbp+3Fh+arg_30]
0x180032fce  mov     rdi, rdx
0x180032fd1  mov     r14, [rbp+3Fh+arg_38]
0x180032fd8  mov     r15, rcx
0x180032fdb  mov     [rsp+110h+var_D0], r8
0x180032fe0  call    ?IsOwned@CSmStoreTransaction@@SA_NPEAUISmStore@@@Z; CSmStoreTransaction::IsOwned(ISmStore *)
0x180032fe5  test    al, al
0x180032fe7  jnz     short loc_180033009
0x180032fe9  mov     r8d, 2B4h
0x180032fef  lea     rdx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032ff6  call    Log_AssertionEvent_13
0x180032ffb  call    ?IsOwned@CSmStoreTransaction@@SA_NPEAUISmStore@@@Z; CSmStoreTransaction::IsOwned(ISmStore *)
0x180033000  test    al, al
0x180033002  jnz     short loc_180033009
0x180033004  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180033009  mov     rax, [rdi]
0x18003300c  lea     rdx, [rbp+3Fh+var_80]
0x180033010  mov     rcx, rdi
0x180033013  mov     [rbp+3Fh+var_80], 0
0x18003301b  mov     rax, [rax+58h]
0x18003301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033024  mov     ebx, eax
0x180033026  test    eax, eax
0x180033028  js      short loc_180033043
0x18003302a  mov     rax, [rdi]
0x18003302d  mov     rcx, rdi
0x180033030  mov     rax, [rax+8]
0x180033034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033039  xor     ebx, ebx
0x18003303b  mov     [r14], rdi
0x18003303e  jmp     loc_1800332CB
0x180033043  cmp     eax, 80004005h
0x180033048  jnz     loc_1800332CB
0x18003304e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180033055  lea     rcx, [rbp+3Fh+pguid]; pguid
0x180033059  movdqu  xmmword ptr [rbp+3Fh+pguid.Data1], xmm0
0x18003305e  call    cs:__imp_CoCreateGuid
0x180033064  xor     r8d, r8d
0x180033067  mov     ebx, eax
0x180033069  test    eax, eax
0x18003306b  jns     short loc_18003308B
0x18003306d  mov     r9d, 2C5h
0x180033073  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003307a  mov     edx, 1
0x18003307f  mov     ecx, eax; int
0x180033081  call    Log_HREvent_14
0x180033086  jmp     loc_1800332CB
0x18003308b  mov     rcx, [r15+10h]
0x18003308f  lea     rdx, [rbp+3Fh+lpMapiProp]
0x180033093  mov     [rsp+110h+var_E0], rdx
0x180033098  lea     r9, [rbp+3Fh+pguid]
0x18003309c  mov     [rbp+3Fh+lpMapiProp], r8
0x1800330a0  xor     edx, edx
0x1800330a2  mov     dword ptr [rsp+110h+var_E8], r8d
0x1800330a7  mov     rax, [rcx]
0x1800330aa  mov     [rsp+110h+var_F0], r8
0x1800330af  lea     r8d, [rdx+10h]
0x1800330b3  mov     rax, [rax+0A0h]
0x1800330ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330bf  mov     ebx, eax
0x1800330c1  test    eax, eax
0x1800330c3  jns     short loc_1800330EC
0x1800330c5  mov     r9d, 2C9h
0x1800330cb  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800330d2  mov     edx, 1
0x1800330d7  mov     ecx, eax; int
0x1800330d9  call    Log_HREvent_14
0x1800330de  lea     rcx, [rbp+3Fh+lpMapiProp]
0x1800330e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800330e7  jmp     loc_1800332CB
0x1800330ec  mov     rdx, rdi
0x1800330ef  mov     [rbp+3Fh+var_A8], 0
0x1800330f7  lea     rcx, [rbp+3Fh+var_A8]
0x1800330fb  call    ??0?$CComQIPtr@VISmConversationInternal@@$1?_GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>(IUnknown *)
0x180033100  mov     rax, [rsi]
0x180033103  lea     r8, [rbp+3Fh+var_9C]
0x180033107  xor     edi, edi
0x180033109  lea     rdx, [rbp+3Fh+var_88]
0x18003310d  mov     rcx, rsi
0x180033110  mov     [rbp+3Fh+var_88], edi
0x180033113  mov     [rbp+3Fh+var_9C], edi
0x180033116  mov     rax, [rax+68h]
0x18003311a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003311f  mov     ebx, eax
0x180033121  test    eax, eax
0x180033123  jns     short loc_180033149
0x180033125  mov     r9d, 2D0h
0x18003312b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180033132  mov     edx, 1
0x180033137  mov     ecx, eax; int
0x180033139  call    Log_HREvent_14
0x18003313e  lea     rcx, [rbp+3Fh+var_A8]
0x180033142  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180033147  jmp     short loc_1800330DE
0x180033149  mov     rax, [rsi]
0x18003314c  lea     rdx, [rbp+3Fh+var_A0]
0x180033150  mov     rcx, rsi
0x180033153  mov     [rbp+3Fh+var_A0], edi
0x180033156  mov     rax, [rax+38h]
0x18003315a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003315f  mov     ebx, eax
0x180033161  test    eax, eax
0x180033163  jns     short loc_18003316D
0x180033165  mov     r9d, 2D3h
0x18003316b  jmp     short loc_18003312B
0x18003316d  mov     rcx, [rbp+3Fh+var_A8]
0x180033171  lea     r8, [rbp+3Fh+var_98]
0x180033175  movzx   edx, [rbp+3Fh+arg_28]
0x180033179  mov     r9d, [rbp+3Fh+var_A0]
0x18003317d  mov     [rbp+3Fh+var_98], edi
0x180033180  mov     rax, [rcx]
0x180033183  mov     [rsp+110h+var_F0], r8
0x180033188  mov     r8d, [rbp+3Fh+var_9C]
0x18003318c  mov     rax, [rax+198h]
0x180033193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033198  mov     ebx, eax
0x18003319a  test    eax, eax
0x18003319c  jns     short loc_1800331A6
0x18003319e  mov     r9d, 2D6h
0x1800331a4  jmp     short loc_18003312B
0x1800331a6  cmp     [rbp+3Fh+var_98], 1
0x1800331aa  mov     r9, rsi
0x1800331ad  mov     eax, [r13+8]
0x1800331b1  movsd   xmm0, qword ptr [r13+0]
0x1800331b7  setz    r10b
0x1800331bb  mov     r8, [rsp+110h+var_D0]
0x1800331c0  mov     rdx, [rbp+3Fh+lpMapiProp]
0x1800331c4  mov     rcx, [rbp+3Fh+var_A8]
0x1800331c8  mov     [rbp+3Fh+var_B8], eax
0x1800331cb  lea     rax, [rsp+110h+var_C0]
0x1800331d0  mov     [rsp+110h+var_E8], rax
0x1800331d5  mov     byte ptr [rsp+110h+var_F0], r10b
0x1800331da  movsd   [rsp+110h+var_C0], xmm0
0x1800331e0  call    ?WriteConversationProperties@CSmConversation@@SAJPEAVISmConversationInternal@@PEAUIMAPIConversation@@AEAVCAutoBlob@@PEAVISmRecipientCollectionPriv@@_NUOLITEMID@@@Z; CSmConversation::WriteConversationProperties(ISmConversationInternal *,IMAPIConversation *,CAutoBlob &,ISmRecipientCollectionPriv *,bool,OLITEMID)
0x1800331e5  mov     ebx, eax
0x1800331e7  test    eax, eax
0x1800331e9  jns     short loc_1800331F6
0x1800331eb  mov     r9d, 2D9h
0x1800331f1  jmp     loc_18003312B
0x1800331f6  mov     rax, [r12]
0x1800331fa  lea     rdx, [rbp+3Fh+Prop]; lpProp
0x1800331fe  mov     rcx, [rbp+3Fh+lpMapiProp]; lpMapiProp
0x180033202  mov     qword ptr [rbp+3Fh+Prop.Value], rax
0x180033206  mov     [rbp+3Fh+Prop.dwAlignPad], edi
0x180033209  mov     qword ptr [rbp+3Fh+Prop.Value+8], rdi
0x18003320d  mov     [rbp+3Fh+Prop.ulPropTag], 829A0040h
0x180033214  call    cs:__imp_HrSetOneProp
0x18003321a  test    eax, eax
0x18003321c  jns     short loc_180033234
0x18003321e  mov     r9d, 2E0h
0x180033224  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003322b  xor     edx, edx
0x18003322d  mov     ecx, eax; int
0x18003322f  call    Log_HREvent_14
0x180033234  lea     rcx, [rbp+3Fh+pv]
0x180033238  mov     [rbp+3Fh+pv], rdi
0x18003323c  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x180033241  mov     rcx, [rbp+3Fh+lpMapiProp]; struct IMAPIProp *
0x180033245  lea     rdx, ?s_rgColumns@CSmConversation@@2QBKB; unsigned int *
0x18003324c  mov     r8, rax; struct _SPropValue **
0x18003324f  call    ?GetProps@@YAJPEAUIMAPIProp@@QEBKPEAPEAU_SPropValue@@@Z; GetProps(IMAPIProp *,ulong const * const,_SPropValue * *)
0x180033254  mov     ebx, eax
0x180033256  test    eax, eax
0x180033258  jns     short loc_18003328B
0x18003325a  mov     r9d, 2E3h
0x180033260  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180033267  mov     edx, 1
0x18003326c  mov     ecx, eax; int
0x18003326e  call    Log_HREvent_14
0x180033273  mov     rcx, [rbp+3Fh+pv]; pv
0x180033277  test    rcx, rcx
0x18003327a  jz      loc_18003313E
0x180033280  call    cs:__imp_MAPIFreeBuffer
0x180033286  jmp     loc_18003313E
0x18003328b  mov     rdx, [rbp+3Fh+pv]; struct _SPropValue *
0x18003328f  mov     r8, r14; struct ISmConversation **
0x180033292  mov     rcx, [r15]; struct ISmStorePriv *
0x180033295  call    ?CreateInstance@CSmConversation@@SAJPEAUISmStorePriv@@QEBU_SPropValue@@PEAPEAUISmConversation@@@Z; CSmConversation::CreateInstance(ISmStorePriv *,_SPropValue const * const,ISmConversation * *)
0x18003329a  mov     ebx, eax
0x18003329c  test    eax, eax
0x18003329e  jns     short loc_1800332A8
0x1800332a0  mov     r9d, 2E5h
0x1800332a6  jmp     short loc_180033260
0x1800332a8  mov     rcx, [rbp+3Fh+pv]; pv
0x1800332ac  test    rcx, rcx
0x1800332af  jz      short loc_1800332B7
0x1800332b1  call    cs:__imp_MAPIFreeBuffer
0x1800332b7  lea     rcx, [rbp+3Fh+var_A8]
0x1800332bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800332c0  lea     rcx, [rbp+3Fh+lpMapiProp]
0x1800332c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800332c9  mov     ebx, edi
0x1800332cb  lea     rcx, [rbp+3Fh+var_80]
0x1800332cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800332d4  mov     eax, ebx
0x1800332d6  mov     rcx, [rbp+3Fh+var_50]
0x1800332da  xor     rcx, rsp; StackCookie
0x1800332dd  call    __security_check_cookie
0x1800332e2  add     rsp, 0D8h
0x1800332e9  pop     r15
0x1800332eb  pop     r14
0x1800332ed  pop     r13
0x1800332ef  pop     r12
0x1800332f1  pop     rdi
0x1800332f2  pop     rsi
0x1800332f3  pop     rbx
0x1800332f4  pop     rbp
0x1800332f5  retn
```
