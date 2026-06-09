# CSmStore::_FindMessageById(ISmEntryId *,ISmMessage * *,int)

- ea: `0x180013a8c`
- end: `0x180013c85`
- name: `?_FindMessageById@CSmStore@@AEAAJPEAUISmEntryId@@PEAPEAUISmMessage@@H@Z`
- size: `505`
- prototype: `__int64 __fastcall(CSmStore *__hidden this, struct ISmEntryId *, struct ISmMessage **, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e200`
- `0x18000ee20`

## callees

- `0x180005c50`
- `0x18000bc08`
- `0x18000be18`
- `0x18000bf4c`
- `0x180012498`
- `0x180013a8c`
- `0x18001a5e4`
- `0x18002e638`
- `0x1800c6940`

## import_xrefs

- `CEMAPI!MAPIFreeBuffer` at `0x180013c03`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c12`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c2e`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c3d`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c59`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c03`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c12`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c2e`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c3d`
- `CEMAPI!MAPIFreeBuffer` at `0x180013c59`
- `CEMAPI!MAPI_CompareEntryIDs` at `0x180013b87`
- `CEMAPI!MAPI_CompareEntryIDs` at `0x180013b87`

## pseudocode

```c
__int64 __fastcall CSmStore::_FindMessageById(CSmStore *this, struct ISmEntryId *a2, struct ISmMessage **a3, int a4)
{
  __int64 v5; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  void **v11; // rax
  int Props; // eax
  void *v13; // rcx
  void **v14; // rax
  int Instance; // eax
  struct ISmConversation *v16; // rdx
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v19; // [rsp+38h] [rbp-28h] BYREF
  struct IMAPIProp *v20; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+54h] [rbp-Ch]

  *a3 = 0;
  v5 = *((_QWORD *)this + 10);
  v20 = 0;
  ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(
    &v18,
    v5);
  v9 = OpenEntry<IMAPIConversation,ATL::CComPtr<ICEMsgStore>>(&v18, (__int64 *)a2, (__int64)&v20);
  v10 = v9;
  if ( v9 < 0 )
  {
    Log_HREvent_1(v9);
LABEL_14:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    return v10;
  }
  if ( !v20 )
    goto LABEL_23;
  v19 = 0;
  v22 = 1;
  v23 = 268108034;
  v11 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&v19);
  Props = GetProps(v20, &v22, (struct _SPropValue **)v11);
  v10 = Props;
  if ( Props < 0 )
  {
    Log_HREvent_1(Props);
LABEL_12:
    if ( v19 )
      MAPIFreeBuffer(v19);
    goto LABEL_14;
  }
  v13 = v19;
  if ( *(_DWORD *)v19 != v23 )
  {
LABEL_21:
    if ( v13 )
      MAPIFreeBuffer(v13);
LABEL_23:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    return 2147943568LL;
  }
  if ( !MAPI_CompareEntryIDs(
          *((_DWORD *)v19 + 2),
          *((struct ENTRYID **)v19 + 2),
          *((_DWORD *)this + 40),
          *((struct ENTRYID **)this + 21)) )
  {
    v13 = v19;
    goto LABEL_21;
  }
  pv = 0;
  v14 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&pv);
  Instance = GetProps(v20, &CSmMessage::s_rgColumns, (struct _SPropValue **)v14);
  v10 = Instance;
  if ( Instance < 0
    || (Instance = CSmMessage::CreateInstance(this, v16, a4, (const struct _SPropValue *const)pv, a3),
        v10 = Instance,
        Instance < 0) )
  {
    Log_HREvent_1(Instance);
    if ( pv )
      MAPIFreeBuffer(pv);
    goto LABEL_12;
  }
  if ( pv )
    MAPIFreeBuffer(pv);
  if ( v19 )
    MAPIFreeBuffer(v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return 0;
}

```

## disassembly

```asm
0x180013a8c  push    rbp
0x180013a8e  push    rbx
0x180013a8f  push    rsi
0x180013a90  push    r14
0x180013a92  push    r15
0x180013a94  mov     rbp, rsp
0x180013a97  sub     rsp, 60h
0x180013a9b  mov     rax, cs:__security_cookie
0x180013aa2  xor     rax, rsp
0x180013aa5  mov     [rbp+var_8], rax
0x180013aa9  mov     rbx, rdx
0x180013aac  mov     qword ptr [r8], 0
0x180013ab3  mov     rdx, [rcx+50h]
0x180013ab7  mov     rsi, rcx
0x180013aba  lea     rcx, [rbp+var_30]
0x180013abe  mov     [rbp+var_20], 0
0x180013ac6  mov     r15d, r9d
0x180013ac9  mov     r14, r8
0x180013acc  call    ??0?$CComPtrBase@VAsyncMediaServiceCommitDocumentTransaction@@@ATL@@IEAA@PEAVAsyncMediaServiceCommitDocumentTransaction@@@Z; ATL::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>::CComPtrBase<AsyncMediaServiceCommitDocumentTransaction>(AsyncMediaServiceCommitDocumentTransaction *)
0x180013ad1  lea     r8, [rbp+var_20]
0x180013ad5  mov     rdx, rbx
0x180013ad8  lea     rcx, [rbp+var_30]
0x180013adc  call    ??$OpenEntry@UIMAPIConversation@@V?$CComPtr@VICEMsgStore@@@ATL@@@@YAJV?$CComPtr@VICEMsgStore@@@ATL@@PEAUISmEntryId@@PEAPEAUIMAPIConversation@@@Z; OpenEntry<IMAPIConversation,ATL::CComPtr<ICEMsgStore>>(ATL::CComPtr<ICEMsgStore>,ISmEntryId *,IMAPIConversation * *)
0x180013ae1  mov     ebx, eax
0x180013ae3  test    eax, eax
0x180013ae5  jns     short loc_180013B05
0x180013ae7  mov     r9d, 0E8h
0x180013aed  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\messagingom"...
0x180013af4  mov     edx, 1
0x180013af9  mov     ecx, eax; int
0x180013afb  call    Log_HREvent_1
0x180013b00  jmp     loc_180013C18
0x180013b05  cmp     [rbp+var_20], 0
0x180013b0a  jz      loc_180013C5F
0x180013b10  lea     rcx, [rbp+var_28]
0x180013b14  mov     [rbp+var_28], 0
0x180013b1c  mov     [rbp+var_10], 1
0x180013b23  mov     [rbp+var_C], 0FFB0102h
0x180013b2a  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x180013b2f  mov     rcx, [rbp+var_20]; struct IMAPIProp *
0x180013b33  lea     rdx, [rbp+var_10]; unsigned int *
0x180013b37  mov     r8, rax; struct _SPropValue **
0x180013b3a  call    ?GetProps@@YAJPEAUIMAPIProp@@QEBKPEAPEAU_SPropValue@@@Z; GetProps(IMAPIProp *,ulong const * const,_SPropValue * *)
0x180013b3f  mov     ebx, eax
0x180013b41  test    eax, eax
0x180013b43  jns     short loc_180013B63
0x180013b45  mov     r9d, 0F6h
0x180013b4b  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\messagingom"...
0x180013b52  mov     edx, 1
0x180013b57  mov     ecx, eax; int
0x180013b59  call    Log_HREvent_1
0x180013b5e  jmp     loc_180013C09
0x180013b63  mov     rcx, [rbp+var_28]
0x180013b67  mov     eax, [rbp+var_C]
0x180013b6a  cmp     [rcx], eax
0x180013b6c  jnz     loc_180013C54
0x180013b72  mov     rdx, [rcx+10h]
0x180013b76  mov     ecx, [rcx+8]
0x180013b79  mov     r9, [rsi+0A8h]
0x180013b80  mov     r8d, [rsi+0A0h]
0x180013b87  call    cs:__imp_?MAPI_CompareEntryIDs@@YAHKPEAUENTRYID@@K0@Z; MAPI_CompareEntryIDs(ulong,ENTRYID *,ulong,ENTRYID *)
0x180013b8d  test    eax, eax
0x180013b8f  jz      loc_180013C50
0x180013b95  lea     rcx, [rbp+pv]
0x180013b99  mov     [rbp+pv], 0
0x180013ba1  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x180013ba6  mov     rcx, [rbp+var_20]; struct IMAPIProp *
0x180013baa  lea     rdx, ?s_rgColumns@CSmMessage@@2QBKB; unsigned int *
0x180013bb1  mov     r8, rax; struct _SPropValue **
0x180013bb4  call    ?GetProps@@YAJPEAUIMAPIProp@@QEBKPEAPEAU_SPropValue@@@Z; GetProps(IMAPIProp *,ulong const * const,_SPropValue * *)
0x180013bb9  mov     ebx, eax
0x180013bbb  test    eax, eax
0x180013bbd  jns     short loc_180013BC7
0x180013bbf  mov     r9d, 100h
0x180013bc5  jmp     short loc_180013BE7
0x180013bc7  mov     r9, [rbp+pv]; struct _SPropValue *
0x180013bcb  mov     r8d, r15d; int
0x180013bce  mov     rcx, rsi; struct ISmStorePriv *
0x180013bd1  mov     [rsp+60h+var_40], r14; struct ISmMessage **
0x180013bd6  call    ?CreateInstance@CSmMessage@@SAJPEAUISmStorePriv@@PEAUISmConversation@@HQEBU_SPropValue@@PEAPEAUISmMessage@@@Z; CSmMessage::CreateInstance(ISmStorePriv *,ISmConversation *,int,_SPropValue const * const,ISmMessage * *)
0x180013bdb  mov     ebx, eax
0x180013bdd  test    eax, eax
0x180013bdf  jns     short loc_180013C25
0x180013be1  mov     r9d, 102h
0x180013be7  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\messagingom"...
0x180013bee  mov     edx, 1
0x180013bf3  mov     ecx, eax; int
0x180013bf5  call    Log_HREvent_1
0x180013bfa  mov     rcx, [rbp+pv]; pv
0x180013bfe  test    rcx, rcx
0x180013c01  jz      short loc_180013C09
0x180013c03  call    cs:__imp_MAPIFreeBuffer
0x180013c09  mov     rcx, [rbp+var_28]; pv
0x180013c0d  test    rcx, rcx
0x180013c10  jz      short loc_180013C18
0x180013c12  call    cs:__imp_MAPIFreeBuffer
0x180013c18  lea     rcx, [rbp+var_20]
0x180013c1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013c21  mov     eax, ebx
0x180013c23  jmp     short loc_180013C6D
0x180013c25  mov     rcx, [rbp+pv]; pv
0x180013c29  test    rcx, rcx
0x180013c2c  jz      short loc_180013C34
0x180013c2e  call    cs:__imp_MAPIFreeBuffer
0x180013c34  mov     rcx, [rbp+var_28]; pv
0x180013c38  test    rcx, rcx
0x180013c3b  jz      short loc_180013C43
0x180013c3d  call    cs:__imp_MAPIFreeBuffer
0x180013c43  lea     rcx, [rbp+var_20]
0x180013c47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013c4c  xor     eax, eax
0x180013c4e  jmp     short loc_180013C6D
0x180013c50  mov     rcx, [rbp+var_28]; pv
0x180013c54  test    rcx, rcx
0x180013c57  jz      short loc_180013C5F
0x180013c59  call    cs:__imp_MAPIFreeBuffer
0x180013c5f  lea     rcx, [rbp+var_20]
0x180013c63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013c68  mov     eax, 80070490h
0x180013c6d  mov     rcx, [rbp+var_8]
0x180013c71  xor     rcx, rsp; StackCookie
0x180013c74  call    __security_check_cookie
0x180013c79  add     rsp, 60h
0x180013c7d  pop     r15
0x180013c7f  pop     r14
0x180013c81  pop     rsi
0x180013c82  pop     rbx
0x180013c83  pop     rbp
0x180013c84  retn
```
