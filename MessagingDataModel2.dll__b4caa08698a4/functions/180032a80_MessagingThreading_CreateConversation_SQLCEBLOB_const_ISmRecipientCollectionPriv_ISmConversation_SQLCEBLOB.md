# MessagingThreading::CreateConversation(_SQLCEBLOB const *,ISmRecipientCollectionPriv *,ISmConversation * *,_SQLCEBLOB *)

- ea: `0x180032a80`
- end: `0x180032f93`
- name: `?CreateConversation@MessagingThreading@@QEAAJPEBU_SQLCEBLOB@@PEAVISmRecipientCollectionPriv@@PEAPEAUISmConversation@@PEAU2@@Z`
- size: `1299`
- prototype: `__int64 __usercall@<rax>(MessagingThreading *__hidden this@<rcx>, const struct _SQLCEBLOB *@<rdx>, struct ISmRecipientCollectionPriv *@<r8>, struct ISmConversation **@<r9>, struct _SQLCEBLOB *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003749c`

## callees

- `0x180005c50`
- `0x18000be18`
- `0x18000d1e4`
- `0x180017854`
- `0x1800178d8`
- `0x180017aa4`
- `0x1800187fc`
- `0x18002e638`
- `0x180032a80`
- `0x1800332fc`
- `0x180033c28`
- `0x180035e70`
- `0x18003d150`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032b36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032b36`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180032d21`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180032d21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180032e2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180032e2c`
- `CEMAPI!MAPIFreeBuffer` at `0x180032ea8`
- `CEMAPI!MAPIFreeBuffer` at `0x180032ef5`
- `CEMAPI!MAPIFreeBuffer` at `0x180032ea8`
- `CEMAPI!MAPIFreeBuffer` at `0x180032ef5`
- `CEMAPI!HrSetOneProp` at `0x180032e3b`
- `CEMAPI!HrSetOneProp` at `0x180032e3b`

## string_xrefs

- `0x180032b48`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032bdf`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032cb5`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032d37`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032d90`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032df5`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032e4b`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032e8c`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032f39`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`

## pseudocode

```c
__int64 __fastcall MessagingThreading::CreateConversation(
        struct IUnknown **this,
        const struct _SQLCEBLOB *a2,
        struct ISmRecipientCollectionPriv *a3,
        struct ISmConversation **a4,
        struct _SQLCEBLOB *a5)
{
  HRESULT v5; // r15d
  struct IUnknown *v7; // rdx
  int started; // eax
  unsigned int v12; // edi
  HRESULT v13; // eax
  LPVOID v14; // rax
  int v15; // edi
  __int64 v16; // rcx
  LPVOID v17; // xmm6_8
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  HRESULT v21; // eax
  struct IUnknown *v22; // rcx
  int v23; // eax
  struct IUnknown *v24; // rdx
  int v25; // eax
  HRESULT v26; // eax
  void **v27; // rax
  int Props; // eax
  struct ISmConversation *v29; // rdx
  int v30; // eax
  int v32; // [rsp+38h] [rbp-D0h]
  LPVOID v33; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A8h]
  LPMAPIPROP lpMapiProp; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-90h]
  LPVOID ppv; // [rsp+80h] [rbp-88h] BYREF
  int v39; // [rsp+88h] [rbp-80h] BYREF
  struct ISmRecipient *v40; // [rsp+90h] [rbp-78h] BYREF
  __int64 v41; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v42[4]; // [rsp+A0h] [rbp-68h] BYREF
  struct _SPropValue Prop; // [rsp+C0h] [rbp-48h] BYREF
  GUID pguid; // [rsp+D8h] [rbp-30h] BYREF

  v5 = 0;
  *a4 = 0;
  v7 = *this;
  v42[0] = &CSmStoreTransaction::`vftable';
  memset(&v42[1], 0, 24);
  started = CSmStoreTransaction::StartTransaction((CSmStoreTransaction *)v42, v7);
  v12 = started;
  if ( started < 0 )
    goto LABEL_11;
  if ( *(_DWORD *)a2 != 20 || *(_DWORD *)(*((_QWORD *)a2 + 1) + 8LL) != 6 )
    goto LABEL_9;
  ppv = 0;
  v13 = CoCreateInstance(
          &GUID_6312362e_eda0_42ba_b7b1_9c8fe3d4d1a4,
          0,
          0x17u,
          &GUID_8651a787_1630_4357_b445_267a6b5c7144,
          &ppv);
  v12 = v13;
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 56LL))(
            ppv,
            *((_QWORD *)a2 + 1),
            *(unsigned int *)a2);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, struct ISmConversation **))(*this)->lpVtbl[3].QueryInterface)(
              *this,
              ppv,
              a4);
      v12 = v13;
      if ( v13 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_9:
        if ( !*a4 )
        {
          started = MessagingThreading::FindConversation((MessagingThreading *)this, a2, a4);
          v12 = started;
          if ( started < 0 )
          {
LABEL_11:
            Log_HREvent_14(started);
            goto LABEL_49;
          }
        }
        v14 = 0;
        v15 = 0;
        pv = 0;
        LODWORD(v37) = 0;
        if ( !*a4 )
        {
          if ( *(_DWORD *)a2 == 12
            && ((v16 = *((_QWORD *)a2 + 1), *(_DWORD *)(v16 + 4) == 458754)
             || *(_DWORD *)(v16 + 4) == 196618
             || *(_DWORD *)(v16 + 4) == 196609) )
          {
            v17 = *(LPVOID *)v16;
            v15 = *(_DWORD *)(v16 + 8);
            v14 = *(LPVOID *)v16;
            pv = *(LPVOID *)v16;
            LODWORD(v37) = v15;
          }
          else
          {
            v17 = 0;
          }
          if ( v14 == (LPVOID)g_ZeroOlItemId && !v15
            || (v18 = *(_QWORD *)a3,
                v39 = 0,
                (*(void (__fastcall **)(struct ISmRecipientCollectionPriv *, int *))(v18 + 56))(a3, &v39),
                v39 != 1) )
          {
LABEL_27:
            if ( !*a4 )
            {
              pguid = GUID_NULL;
              v21 = CoCreateGuid(&pguid);
              v5 = v21;
              if ( v21 < 0 )
              {
                Log_HREvent_14(v21);
                goto LABEL_48;
              }
              v22 = this[2];
              lpMapiProp = 0;
              v23 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, GUID *, _QWORD, _DWORD, LPMAPIPROP *))v22->lpVtbl[6].Release)(
                      v22,
                      0,
                      16,
                      &pguid,
                      0,
                      0,
                      &lpMapiProp);
              v5 = v23;
              if ( v23 < 0 )
              {
                Log_HREvent_14(v23);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
                goto LABEL_48;
              }
              v24 = *this;
              v5 = 0;
              LOBYTE(v32) = 0;
              v33 = v17;
              LODWORD(v34) = v15;
              v25 = CSmConversation::WriteConversationProperties(lpMapiProp, v24, 0, a2, a3, 0, v32, &v33);
              v12 = v25;
              if ( v25 < 0 )
              {
                Log_HREvent_14(v25);
LABEL_34:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
                goto LABEL_49;
              }
              memset(&Prop, 0, sizeof(Prop));
              Prop.ulPropTag = -2103836608;
              GetSystemTimeAsFileTime((LPFILETIME)&Prop.Value);
              v26 = HrSetOneProp(lpMapiProp, &Prop);
              if ( v26 < 0 )
                Log_HREvent_14(v26);
              pv = 0;
              v27 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&pv);
              Props = GetProps(lpMapiProp, &CSmConversation::s_rgColumns, (struct _SPropValue **)v27);
              v12 = Props;
              if ( Props < 0
                || (Props = CSmConversation::CreateInstance(
                              (struct ISmStorePriv *)*this,
                              (const struct _SPropValue *const)pv,
                              a4),
                    v12 = Props,
                    Props < 0)
                || (Props = CSmStoreTransaction::EndTransaction((CSmStoreTransaction *)v42, 1), v12 = Props, Props < 0) )
              {
                Log_HREvent_14(Props);
                if ( pv )
                  MAPIFreeBuffer(pv);
                goto LABEL_34;
              }
              if ( pv )
                MAPIFreeBuffer(pv);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&lpMapiProp);
            }
            v29 = *a4;
            v41 = 0;
            ATL::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>(
              &v41,
              v29);
            v30 = (*(__int64 (__fastcall **)(__int64, struct _SQLCEBLOB *))(*(_QWORD *)v41 + 392LL))(v41, a5);
            v12 = v30;
            if ( v30 < 0 )
            {
              Log_HREvent_14(v30);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              goto LABEL_49;
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
LABEL_48:
            v12 = v5;
            goto LABEL_49;
          }
          v19 = *(_QWORD *)a3;
          v40 = 0;
          v20 = (*(__int64 (__fastcall **)(struct ISmRecipientCollectionPriv *, _QWORD, struct ISmRecipient **))(v19 + 48))(
                  a3,
                  0,
                  &v40);
          v12 = v20;
          if ( v20 < 0
            || (v20 = MessagingThreading::UpgradeConversation(
                        (MessagingThreading *)this,
                        v40,
                        (const struct OLITEMID *)&pv,
                        a4),
                v12 = v20,
                v20 < 0) )
          {
            Log_HREvent_14(v20);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
            goto LABEL_49;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
          v15 = v37;
        }
        v17 = pv;
        goto LABEL_27;
      }
    }
  }
  Log_HREvent_14(v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_49:
  CSmStoreTransaction::~CSmStoreTransaction((CSmStoreTransaction *)v42);
  return v12;
}

```

## disassembly

```asm
0x180032a80  mov     rax, rsp
0x180032a83  push    rbp
0x180032a84  push    rbx
0x180032a85  push    rsi
0x180032a86  push    rdi
0x180032a87  push    r12
0x180032a89  push    r13
0x180032a8b  push    r14
0x180032a8d  push    r15
0x180032a8f  lea     rbp, [rax-48h]
0x180032a93  sub     rsp, 108h
0x180032a9a  movaps  xmmword ptr [rax-58h], xmm6
0x180032a9e  mov     rax, cs:__security_cookie
0x180032aa5  xor     rax, rsp
0x180032aa8  mov     [rbp+40h+var_60], rax
0x180032aac  mov     rax, [rbp+40h+arg_20]
0x180032ab0  xor     r15d, r15d
0x180032ab3  mov     [rsp+40h], rax
0x180032ab8  mov     r14, rdx
0x180032abb  mov     [r9], r15
0x180032abe  lea     rax, ??_7CSmStoreTransaction@@6B@; const CSmStoreTransaction::`vftable'
0x180032ac5  mov     rdx, [rcx]; struct ISmStore *
0x180032ac8  mov     r12, rcx
0x180032acb  lea     rcx, [rbp+40h+var_A8]; this
0x180032acf  mov     [rbp+40h+var_A8], rax
0x180032ad3  mov     rsi, r9
0x180032ad6  mov     [rbp+40h+var_98], r15
0x180032ada  mov     r13, r8
0x180032add  mov     [rbp+40h+var_A0], r15
0x180032ae1  mov     [rbp+40h+var_90], r15
0x180032ae5  call    ?StartTransaction@CSmStoreTransaction@@QEAAJPEAUISmStore@@@Z; CSmStoreTransaction::StartTransaction(ISmStore *)
0x180032aea  mov     edi, eax
0x180032aec  test    eax, eax
0x180032aee  jns     short loc_180032AFB
0x180032af0  mov     r9d, 320h
0x180032af6  jmp     loc_180032BDF
0x180032afb  cmp     dword ptr [r14], 14h
0x180032aff  jnz     loc_180032BC0
0x180032b05  mov     rax, [r14+8]
0x180032b09  cmp     dword ptr [rax+8], 6
0x180032b0d  jnz     loc_180032BC0
0x180032b13  xor     edx, edx; pUnkOuter
0x180032b15  mov     [rsp+140h+var_C8], r15
0x180032b1a  lea     rax, [rsp+140h+var_C8]
0x180032b1f  lea     r9, _GUID_8651a787_1630_4357_b445_267a6b5c7144; riid
0x180032b26  mov     [rsp+140h+ppv], rax; ppv
0x180032b2b  lea     rcx, _GUID_6312362e_eda0_42ba_b7b1_9c8fe3d4d1a4; rclsid
0x180032b32  lea     r8d, [rdx+17h]; dwClsContext
0x180032b36  call    cs:__imp_CoCreateInstance
0x180032b3c  mov     edi, eax
0x180032b3e  test    eax, eax
0x180032b40  jns     short loc_180032B6A
0x180032b42  mov     r9d, 32Bh
0x180032b48  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032b4f  mov     edx, 1
0x180032b54  mov     ecx, eax; int
0x180032b56  call    Log_HREvent_14
0x180032b5b  lea     rcx, [rsp+140h+var_C8]
0x180032b60  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032b65  jmp     loc_180032F60
0x180032b6a  mov     rcx, [rsp+140h+var_C8]
0x180032b6f  mov     r8d, [r14]
0x180032b72  mov     rdx, [r14+8]
0x180032b76  mov     rax, [rcx]
0x180032b79  mov     rax, [rax+38h]
0x180032b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b82  mov     edi, eax
0x180032b84  test    eax, eax
0x180032b86  jns     short loc_180032B90
0x180032b88  mov     r9d, 32Ch
0x180032b8e  jmp     short loc_180032B48
0x180032b90  mov     rcx, [r12]
0x180032b94  mov     r8, rsi
0x180032b97  mov     rdx, [rsp+140h+var_C8]
0x180032b9c  mov     rax, [rcx]
0x180032b9f  mov     rax, [rax+48h]
0x180032ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ba8  mov     edi, eax
0x180032baa  test    eax, eax
0x180032bac  jns     short loc_180032BB6
0x180032bae  mov     r9d, 32Eh
0x180032bb4  jmp     short loc_180032B48
0x180032bb6  lea     rcx, [rsp+140h+var_C8]
0x180032bbb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032bc0  cmp     [rsi], r15
0x180032bc3  jnz     short loc_180032BF7
0x180032bc5  mov     r8, rsi; struct ISmConversation **
0x180032bc8  mov     rdx, r14; struct _SQLCEBLOB *
0x180032bcb  mov     rcx, r12; this
0x180032bce  call    ?FindConversation@MessagingThreading@@QEAAJPEBU_SQLCEBLOB@@PEAPEAUISmConversation@@@Z; MessagingThreading::FindConversation(_SQLCEBLOB const *,ISmConversation * *)
0x180032bd3  mov     edi, eax
0x180032bd5  test    eax, eax
0x180032bd7  jns     short loc_180032BF7
0x180032bd9  mov     r9d, 338h
0x180032bdf  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032be6  mov     edx, 1
0x180032beb  mov     ecx, eax; int
0x180032bed  call    Log_HREvent_14
0x180032bf2  jmp     loc_180032F60
0x180032bf7  xor     eax, eax
0x180032bf9  mov     edi, eax
0x180032bfb  mov     [rsp+140h+pv], rax
0x180032c00  mov     dword ptr [rsp+140h+var_D0], eax
0x180032c04  lea     ebx, [rax+1]
0x180032c07  cmp     [rsi], r15
0x180032c0a  jnz     loc_180032D02
0x180032c10  cmp     dword ptr [r14], 0Ch
0x180032c14  jnz     short loc_180032C4D
0x180032c16  mov     rcx, [r14+8]
0x180032c1a  cmp     dword ptr [rcx+4], 70002h
0x180032c21  jz      short loc_180032C35
0x180032c23  cmp     dword ptr [rcx+4], 3000Ah
0x180032c2a  jz      short loc_180032C35
0x180032c2c  cmp     dword ptr [rcx+4], 30001h
0x180032c33  jnz     short loc_180032C4D
0x180032c35  movsd   xmm6, qword ptr [rcx]
0x180032c39  mov     edi, [rcx+8]
0x180032c3c  movq    rax, xmm6
0x180032c41  movsd   [rsp+140h+pv], xmm6
0x180032c47  mov     dword ptr [rsp+140h+var_D0], edi
0x180032c4b  jmp     short loc_180032C52
0x180032c4d  movq    xmm6, rax
0x180032c52  cmp     cs:?g_ZeroOlItemId@@3UOLITEMID@@B, eax; OLITEMID const g_ZeroOlItemId
0x180032c58  jnz     short loc_180032C72
0x180032c5a  shr     rax, 20h
0x180032c5e  cmp     cs:dword_1800D8D7C, eax
0x180032c64  jnz     short loc_180032C72
0x180032c66  cmp     cs:dword_1800D8D80, edi
0x180032c6c  jz      loc_180032D08
0x180032c72  mov     rax, [r13+0]
0x180032c76  lea     rdx, [rbp+40h+var_C0]
0x180032c7a  mov     rcx, r13
0x180032c7d  mov     [rbp+40h+var_C0], r15d
0x180032c81  mov     rax, [rax+38h]
0x180032c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c8a  cmp     [rbp+40h+var_C0], ebx
0x180032c8d  jnz     short loc_180032D08
0x180032c8f  mov     rax, [r13+0]
0x180032c93  lea     r8, [rbp+40h+var_B8]
0x180032c97  xor     edx, edx
0x180032c99  mov     [rbp+40h+var_B8], r15
0x180032c9d  mov     rcx, r13
0x180032ca0  mov     rax, [rax+30h]
0x180032ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ca9  mov     edi, eax
0x180032cab  test    eax, eax
0x180032cad  jns     short loc_180032CD3
0x180032caf  mov     r9d, 355h
0x180032cb5  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032cbc  mov     edx, ebx
0x180032cbe  mov     ecx, eax; int
0x180032cc0  call    Log_HREvent_14
0x180032cc5  lea     rcx, [rbp+40h+var_B8]
0x180032cc9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032cce  jmp     loc_180032F60
0x180032cd3  mov     rdx, [rbp+40h+var_B8]; struct ISmRecipient *
0x180032cd7  lea     r8, [rsp+140h+pv]; struct OLITEMID *
0x180032cdc  mov     r9, rsi; struct ISmConversation **
0x180032cdf  mov     rcx, r12; this
0x180032ce2  call    ?UpgradeConversation@MessagingThreading@@QEAAJPEAUISmRecipient@@AEBUOLITEMID@@PEAPEAUISmConversation@@@Z; MessagingThreading::UpgradeConversation(ISmRecipient *,OLITEMID const &,ISmConversation * *)
0x180032ce7  mov     edi, eax
0x180032ce9  test    eax, eax
0x180032ceb  jns     short loc_180032CF5
0x180032ced  mov     r9d, 357h
0x180032cf3  jmp     short loc_180032CB5
0x180032cf5  lea     rcx, [rbp+40h+var_B8]
0x180032cf9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032cfe  mov     edi, dword ptr [rsp+140h+var_D0]
0x180032d02  movsd   xmm6, [rsp+140h+pv]
0x180032d08  cmp     [rsi], r15
0x180032d0b  jnz     loc_180032F05
0x180032d11  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032d18  lea     rcx, [rbp+40h+pguid]; pguid
0x180032d1c  movdqu  xmmword ptr [rbp+40h+pguid.Data1], xmm0
0x180032d21  call    cs:__imp_CoCreateGuid
0x180032d27  xor     r8d, r8d
0x180032d2a  mov     r15d, eax
0x180032d2d  test    eax, eax
0x180032d2f  jns     short loc_180032D4C
0x180032d31  mov     r9d, 363h
0x180032d37  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032d3e  mov     edx, ebx
0x180032d40  mov     ecx, eax; int
0x180032d42  call    Log_HREvent_14
0x180032d47  jmp     loc_180032F5D
0x180032d4c  mov     rcx, [r12+10h]
0x180032d51  lea     rdx, [rsp+140h+lpMapiProp]
0x180032d56  mov     [rsp+140h+var_110], rdx
0x180032d5b  lea     r9, [rbp+40h+pguid]
0x180032d5f  mov     [rsp+140h+lpMapiProp], r8
0x180032d64  xor     edx, edx
0x180032d66  mov     dword ptr [rsp+140h+var_118], r8d
0x180032d6b  mov     rax, [rcx]
0x180032d6e  mov     [rsp+140h+ppv], r8
0x180032d73  lea     r8d, [rdx+10h]
0x180032d77  mov     rax, [rax+0A0h]
0x180032d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d83  mov     r15d, eax
0x180032d86  test    eax, eax
0x180032d88  jns     short loc_180032DAF
0x180032d8a  mov     r9d, 367h
0x180032d90  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032d97  mov     edx, ebx
0x180032d99  mov     ecx, eax; int
0x180032d9b  call    Log_HREvent_14
0x180032da0  lea     rcx, [rsp+140h+lpMapiProp]
0x180032da5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032daa  jmp     loc_180032F5D
0x180032daf  mov     rdx, [r12]
0x180032db3  lea     rax, [rsp+140h+var_F0]
0x180032db8  mov     rcx, [rsp+140h+lpMapiProp]
0x180032dbd  xor     r15d, r15d
0x180032dc0  mov     [rsp+140h+var_108], rax
0x180032dc5  mov     r9, r14
0x180032dc8  mov     byte ptr [rsp+140h+var_110], r15b
0x180032dcd  xor     r8d, r8d
0x180032dd0  mov     [rsp+140h+var_118], r15
0x180032dd5  mov     [rsp+140h+ppv], r13
0x180032dda  movsd   [rsp+140h+var_F0], xmm6
0x180032de0  mov     dword ptr [rsp+140h+var_E8], edi
0x180032de4  call    ?WriteConversationProperties@CSmConversation@@SAJPEAUIMAPIConversation@@PEAUISmStorePriv@@HPEBU_SQLCEBLOB@@PEAVISmRecipientCollectionPriv@@3_NUOLITEMID@@@Z; CSmConversation::WriteConversationProperties(IMAPIConversation *,ISmStorePriv *,int,_SQLCEBLOB const *,ISmRecipientCollectionPriv *,ISmRecipientCollectionPriv *,bool,OLITEMID)
0x180032de9  mov     edi, eax
0x180032deb  test    eax, eax
0x180032ded  jns     short loc_180032E14
0x180032def  mov     r9d, 36Ah
0x180032df5  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032dfc  mov     edx, ebx
0x180032dfe  mov     ecx, eax; int
0x180032e00  call    Log_HREvent_14
0x180032e05  lea     rcx, [rsp+140h+lpMapiProp]
0x180032e0a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032e0f  jmp     loc_180032F60
0x180032e14  xorps   xmm0, xmm0
0x180032e17  lea     rcx, [rbp+40h+Prop.Value]; lpSystemTimeAsFileTime
0x180032e1b  xor     eax, eax
0x180032e1d  movups  xmmword ptr [rbp-48h], xmm0
0x180032e21  mov     [rbp+40h+Prop.ulPropTag], 829A0040h
0x180032e28  mov     qword ptr [rbp+40h+Prop.Value+8], rax
0x180032e2c  call    cs:__imp_GetSystemTimeAsFileTime
0x180032e32  mov     rcx, [rsp+140h+lpMapiProp]; lpMapiProp
0x180032e37  lea     rdx, [rbp+40h+Prop]; lpProp
0x180032e3b  call    cs:__imp_HrSetOneProp
0x180032e41  test    eax, eax
0x180032e43  jns     short loc_180032E5B
0x180032e45  mov     r9d, 371h
0x180032e4b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032e52  xor     edx, edx
0x180032e54  mov     ecx, eax; int
0x180032e56  call    Log_HREvent_14
0x180032e5b  lea     rcx, [rsp+140h+pv]
0x180032e60  mov     [rsp+140h+pv], r15
0x180032e65  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x180032e6a  mov     rcx, [rsp+140h+lpMapiProp]; struct IMAPIProp *
0x180032e6f  lea     rdx, ?s_rgColumns@CSmConversation@@2QBKB; unsigned int *
0x180032e76  mov     r8, rax; struct _SPropValue **
0x180032e79  call    ?GetProps@@YAJPEAUIMAPIProp@@QEBKPEAPEAU_SPropValue@@@Z; GetProps(IMAPIProp *,ulong const * const,_SPropValue * *)
0x180032e7e  mov     edi, eax
0x180032e80  test    eax, eax
0x180032e82  jns     short loc_180032EB3
0x180032e84  mov     r9d, 374h
0x180032e8a  mov     edx, ebx
0x180032e8c  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032e93  mov     ecx, eax; int
0x180032e95  call    Log_HREvent_14
0x180032e9a  mov     rcx, [rsp+140h+pv]; pv
0x180032e9f  test    rcx, rcx
0x180032ea2  jz      loc_180032E05
0x180032ea8  call    cs:__imp_MAPIFreeBuffer
0x180032eae  jmp     loc_180032E05
0x180032eb3  mov     rdx, [rsp+140h+pv]; struct _SPropValue *
0x180032eb8  mov     r8, rsi; struct ISmConversation **
0x180032ebb  mov     rcx, [r12]; struct ISmStorePriv *
0x180032ebf  call    ?CreateInstance@CSmConversation@@SAJPEAUISmStorePriv@@QEBU_SPropValue@@PEAPEAUISmConversation@@@Z; CSmConversation::CreateInstance(ISmStorePriv *,_SPropValue const * const,ISmConversation * *)
0x180032ec4  mov     edi, eax
0x180032ec6  mov     edx, ebx; int
0x180032ec8  test    eax, eax
0x180032eca  jns     short loc_180032ED4
0x180032ecc  mov     r9d, 376h
0x180032ed2  jmp     short loc_180032E8C
0x180032ed4  lea     rcx, [rbp+40h+var_A8]; this
0x180032ed8  call    ?EndTransaction@CSmStoreTransaction@@QEAAJH@Z; CSmStoreTransaction::EndTransaction(int)
0x180032edd  mov     edi, eax
0x180032edf  test    eax, eax
0x180032ee1  jns     short loc_180032EEB
0x180032ee3  mov     r9d, 378h
0x180032ee9  jmp     short loc_180032E8A
0x180032eeb  mov     rcx, [rsp+140h+pv]; pv
0x180032ef0  test    rcx, rcx
0x180032ef3  jz      short loc_180032EFB
0x180032ef5  call    cs:__imp_MAPIFreeBuffer
0x180032efb  lea     rcx, [rsp+140h+lpMapiProp]
0x180032f00  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032f05  mov     rdx, [rsi]
0x180032f08  lea     rcx, [rbp+40h+var_B0]
0x180032f0c  mov     [rbp+40h+var_B0], r15
0x180032f10  call    ??0?$CComQIPtr@VISmConversationInternal@@$1?_GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>::CComQIPtr<ISmConversationInternal,&__s_GUID const _GUID_afbd9824_c03e_4601_b0ca_f7443d58bd1a>(IUnknown *)
0x180032f15  mov     rcx, [rbp+40h+var_B0]
0x180032f19  mov     rdx, [rsp+40h]
0x180032f1e  mov     rax, [rcx]
0x180032f21  mov     rax, [rax+188h]
  ... truncated ...
```
