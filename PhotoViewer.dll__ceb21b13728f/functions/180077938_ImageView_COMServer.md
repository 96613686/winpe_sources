# ImageView_COMServer

- ea: `0x180077938`
- end: `0x180077a6c`
- name: `ImageView_COMServer`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180044d50`

## callees

- `0x18000cb74`
- `0x18000fe20`
- `0x1800770b8`
- `0x180077238`
- `0x180077938`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007794b`
- `KERNEL32!GetCurrentThreadId` at `0x18007794b`
- `USER32!GetMessageW` at `0x180077a25`
- `USER32!GetMessageW` at `0x180077a25`
- `USER32!DispatchMessageW` at `0x180077a12`
- `USER32!DispatchMessageW` at `0x180077a12`
- `USER32!TranslateMessage` at `0x180077a07`
- `USER32!TranslateMessage` at `0x180077a07`
- `ole32!CoRevokeClassObject` at `0x180077a36`
- `ole32!CoRevokeClassObject` at `0x180077a36`
- `ole32!CoRegisterClassObject` at `0x1800779dc`
- `ole32!CoRegisterClassObject` at `0x1800779dc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077975`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800779a8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800779e8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077a42`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077975`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800779a8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800779e8`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180077a42`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ImageView_COMServer(__int64 a1, IUnknown *a2, __int64 a3, DWORD a4)
{
  int v4; // eax
  int v5; // edx
  ATL::CComModule *v6; // rcx
  int ClassObject; // eax
  int v8; // edx
  HRESULT v9; // eax
  int v10; // edx
  HRESULT v11; // eax
  int v12; // edx
  _BYTE v13[16]; // [rsp+30h] [rbp-48h] BYREF
  MSG Msg; // [rsp+40h] [rbp-38h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+10h] BYREF
  __int64 v16; // [rsp+90h] [rbp+18h] BYREF
  DWORD dwRegister; // [rsp+98h] [rbp+20h] BYREF

  dwRegister = a4;
  v16 = a3;
  pUnk = a2;
  g_dwThreadID = GetCurrentThreadId();
  LODWORD(v16) = -2147467259;
  v4 = ComHelpers::CCoInit::Initialize((ComHelpers::CCoInit *)&v16);
  try
  {
    if ( v4 < 0 )
      Base::Throw((Base *)(unsigned int)v4, v5);
    pUnk = 0;
    ClassObject = ATL::CComModule::GetClassObject(
                    v6,
                    &CLSID_AutoplayForViewer,
                    &GUID_00000000_0000_0000_c000_000000000046,
                    (void **)&pUnk);
    if ( ClassObject < 0 )
      Base::Throw((Base *)(unsigned int)ClassObject, v8);
    dwRegister = 0;
    v9 = CoRegisterClassObject(&CLSID_AutoplayForViewer, pUnk, 4u, 0, &dwRegister);
    if ( v9 < 0 )
      Base::Throw((Base *)(unsigned int)v9, v10);
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    v11 = CoRevokeClassObject(dwRegister);
    if ( v11 < 0 )
      Base::Throw((Base *)(unsigned int)v11, v12);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&pUnk);
    ComHelpers::CCoInit::~CCoInit((ComHelpers::CCoInit *)&v16);
  }
  catch ( Base::Exception v13 )
  {
    Base::Exception::operator long(v13);
    Base::Exception::~Exception((Base::Exception *)v13);
  }
}

```

## disassembly

```asm
0x180077938  mov     [rsp+dwRegister], r9d
0x18007793d  mov     [rsp+arg_10], r8
0x180077942  mov     [rsp+pUnk], rdx
0x180077947  sub     rsp, 78h
0x18007794b  call    cs:__imp_GetCurrentThreadId
0x180077951  mov     cs:?g_dwThreadID@@3KA, eax; ulong g_dwThreadID
0x180077957  mov     dword ptr [rsp+78h+arg_10], 80004005h
0x180077962  lea     rcx, [rsp+78h+arg_10]; this
0x18007796a  call    ?Initialize@CCoInit@ComHelpers@@QEAAJXZ; ComHelpers::CCoInit::Initialize(void)
0x18007796f  test    eax, eax
0x180077971  jns     short loc_18007797B
0x180077973  mov     ecx, eax
0x180077975  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18007797b  mov     [rsp+78h+pUnk], 0
0x180077987  lea     r9, [rsp+78h+pUnk]; void **
0x18007798f  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180077996  lea     rdx, CLSID_AutoplayForViewer; struct _GUID *
0x18007799d  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x1800779a2  test    eax, eax
0x1800779a4  jns     short loc_1800779AE
0x1800779a6  mov     ecx, eax
0x1800779a8  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800779ae  mov     [rsp+78h+dwRegister], 0
0x1800779b9  lea     rax, [rsp+78h+dwRegister]
0x1800779c1  mov     [rsp+78h+lpdwRegister], rax; lpdwRegister
0x1800779c6  xor     r9d, r9d; flags
0x1800779c9  lea     r8d, [r9+4]; dwClsContext
0x1800779cd  mov     rdx, [rsp+78h+pUnk]; pUnk
0x1800779d5  lea     rcx, CLSID_AutoplayForViewer; rclsid
0x1800779dc  call    cs:__imp_CoRegisterClassObject
0x1800779e2  test    eax, eax
0x1800779e4  jns     short loc_1800779EE
0x1800779e6  mov     ecx, eax
0x1800779e8  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800779ee  xorps   xmm0, xmm0
0x1800779f1  movups  xmmword ptr [rsp+78h+Msg.hwnd], xmm0
0x1800779f6  movups  xmmword ptr [rsp+78h+Msg.wParam], xmm0
0x1800779fb  movups  xmmword ptr [rsp+78h+Msg.time], xmm0
0x180077a00  jmp     short loc_180077A18
0x180077a02  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180077a07  call    cs:__imp_TranslateMessage
0x180077a0d  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180077a12  call    cs:__imp_DispatchMessageW
0x180077a18  xor     r9d, r9d; wMsgFilterMax
0x180077a1b  xor     r8d, r8d; wMsgFilterMin
0x180077a1e  xor     edx, edx; hWnd
0x180077a20  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180077a25  call    cs:__imp_GetMessageW
0x180077a2b  test    eax, eax
0x180077a2d  jnz     short loc_180077A02
0x180077a2f  mov     ecx, [rsp+78h+dwRegister]; dwRegister
0x180077a36  call    cs:__imp_CoRevokeClassObject
0x180077a3c  test    eax, eax
0x180077a3e  jns     short loc_180077A49
0x180077a40  mov     ecx, eax
0x180077a42  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180077a48  nop
0x180077a49  lea     rcx, [rsp+78h+pUnk]
0x180077a51  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180077a56  nop
0x180077a57  lea     rcx, [rsp+78h+arg_10]; this
0x180077a5f  call    ??1CCoInit@ComHelpers@@QEAA@XZ; ComHelpers::CCoInit::~CCoInit(void)
0x180077a64  nop
0x180077a65  jmp     short $+2
0x180077a67  add     rsp, 78h
0x180077a6b  retn
```
