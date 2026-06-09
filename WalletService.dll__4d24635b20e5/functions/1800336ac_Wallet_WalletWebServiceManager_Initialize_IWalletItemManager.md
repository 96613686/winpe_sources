# Wallet::WalletWebServiceManager::Initialize(IWalletItemManager *)

- ea: `0x1800336ac`
- end: `0x1800337cb`
- name: `?Initialize@WalletWebServiceManager@Wallet@@QEAAJPEAUIWalletItemManager@@@Z`
- size: `287`
- prototype: `int(Wallet::WalletWebServiceManager *__hidden this, struct IWalletItemManager *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018bd0`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x180014328`
- `0x180018274`
- `0x180033280`
- `0x1800336ac`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003370c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003370c`

## string_xrefs

- `0x1800336fc`: `Software\Microsoft\Wallet\WalletWebServiceManager`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebServiceManager::Initialize(
        Wallet::WalletWebServiceManager *this,
        struct IUnknown *a2)
{
  unsigned __int16 *v4; // r9
  int v5; // ebx
  signed int LastError; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v11; // [rsp+20h] [rbp-38h]
  __int64 (__fastcall *v12)(__int64, struct IUnknown **, __int64 *); // [rsp+40h] [rbp-18h] BYREF
  int v13; // [rsp+48h] [rbp-10h]
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v15; // [rsp+70h] [rbp+18h] BYREF

  ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v14, (__int64)this);
  if ( a2 )
  {
    if ( *((struct IUnknown **)this + 3) != a2 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 3, a2);
    if ( (unsigned int)ATL::CRegKey::Create(
                         (HKEY *)this + 4,
                         HKEY_LOCAL_MACHINE,
                         L"Software\\Microsoft\\Wallet\\WalletWebServiceManager",
                         v4,
                         v11) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v5 = -2143748092;
      }
    }
    else
    {
      v7 = *((_QWORD *)this + 13);
      if ( v7 )
      {
        *((_QWORD *)this + 13) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v15 = (_QWORD *)((char *)this + 104);
      v12 = Wallet::WalletWebService::Initialize;
      v13 = 0;
      v5 = ce::CreateAndInitializeComObject<Wallet::WalletWebService,Wallet::WalletWebService,ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager>,ce::details::ptr_raw_assigner,Wallet::WalletWebService>(
             (__int64)&v12,
             (__int64)this + 24,
             &v14,
             &v15);
      if ( v5 >= 0 )
      {
        v8 = v14;
        *((_DWORD *)this + 4) = 1;
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
        v5 = 0;
        if ( v9 < 0 )
          v5 = v9;
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800336ac  mov     [rsp+arg_0], rbx
0x1800336b1  mov     [rsp+arg_18], rsi
0x1800336b6  push    rdi
0x1800336b7  sub     rsp, 50h
0x1800336bb  mov     rbx, rdx
0x1800336be  mov     rdi, rcx
0x1800336c1  mov     rdx, rcx
0x1800336c4  lea     rcx, [rsp+58h+arg_8]
0x1800336c9  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800336ce  test    rbx, rbx
0x1800336d1  jnz     short loc_1800336DD
0x1800336d3  mov     ebx, 80004003h
0x1800336d8  jmp     loc_1800337AF
0x1800336dd  lea     rsi, [rdi+18h]
0x1800336e1  cmp     [rsi], rbx
0x1800336e4  jz      short loc_1800336F1
0x1800336e6  mov     rdx, rbx; struct IUnknown *
0x1800336e9  mov     rcx, rsi; struct IUnknown **
0x1800336ec  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800336f1  lea     rcx, [rdi+20h]; this
0x1800336f5  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800336fc  lea     r8, ?sc_szWalletWebServiceManagerXmlRegKey@WalletWebServiceManager@Wallet@@2QBGB; "Software\\Microsoft\\Wallet\\WalletWebS"...
0x180033703  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180033708  test    eax, eax
0x18003370a  jz      short loc_180033733
0x18003370c  call    cs:__imp_GetLastError
0x180033712  mov     ebx, eax
0x180033714  test    eax, eax
0x180033716  jz      short loc_18003372C
0x180033718  jle     loc_1800337AF
0x18003371e  movzx   ebx, ax
0x180033721  or      ebx, 80070000h
0x180033727  jmp     loc_1800337AF
0x18003372c  mov     ebx, 80390004h
0x180033731  jmp     short loc_1800337AF
0x180033733  lea     rbx, [rdi+68h]
0x180033737  mov     rcx, [rbx]
0x18003373a  test    rcx, rcx
0x18003373d  jz      short loc_180033752
0x18003373f  mov     qword ptr [rbx], 0
0x180033746  mov     rax, [rcx]
0x180033749  mov     rax, [rax+10h]
0x18003374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033752  lea     rax, ?Initialize@WalletWebService@Wallet@@QEAAJAEAV?$CComPtr@UIWalletItemManager@@@ATL@@V?$CComPtr@VWalletWebServiceManager@Wallet@@@4@@Z; Wallet::WalletWebService::Initialize(ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager>)
0x180033759  mov     [rsp+58h+arg_10], rbx
0x18003375e  mov     [rsp+58h+var_18], rax
0x180033763  lea     r9, [rsp+58h+arg_10]
0x180033768  mov     eax, [rsp+58h+var_C]
0x18003376c  lea     r8, [rsp+58h+arg_8]
0x180033771  mov     rdx, rsi
0x180033774  mov     [rsp+58h+var_C], eax
0x180033778  lea     rcx, [rsp+58h+var_18]
0x18003377d  mov     [rsp+58h+var_10], 0
0x180033785  call    ??$CreateAndInitializeComObject@VWalletWebService@Wallet@@V12@AEAV?$CComPtr@UIWalletItemManager@@@ATL@@V?$CComPtr@VWalletWebServiceManager@Wallet@@@4@Vptr_raw_assigner@details@ce@@V12@@ce@@YAJP8WalletWebService@Wallet@@EAAJAEAV?$CComPtr@UIWalletItemManager@@@ATL@@V?$CComPtr@VWalletWebServiceManager@Wallet@@@4@@Z0AEBV54@AEBV?$ptr_raw_assigner@VWalletWebService@Wallet@@@details@0@@Z; ce::CreateAndInitializeComObject<Wallet::WalletWebService,Wallet::WalletWebService,ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager>,ce::details::ptr_raw_assigner,Wallet::WalletWebService>(long (Wallet::WalletWebService::*)(ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager>),ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager> const &,ce::details::ptr_raw_assigner<Wallet::WalletWebService> const &)
0x18003378a  mov     ebx, eax
0x18003378c  test    eax, eax
0x18003378e  js      short loc_1800337AF
0x180033790  mov     rcx, [rsp+58h+arg_8]
0x180033795  mov     dword ptr [rdi+10h], 1
0x18003379c  mov     rax, [rcx]
0x18003379f  mov     rax, [rax+18h]
0x1800337a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a8  xor     ebx, ebx
0x1800337aa  test    eax, eax
0x1800337ac  cmovs   ebx, eax
0x1800337af  lea     rcx, [rsp+58h+arg_8]
0x1800337b4  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800337b9  mov     rsi, [rsp+58h+arg_18]
0x1800337be  mov     eax, ebx
0x1800337c0  mov     rbx, [rsp+58h+arg_0]
0x1800337c5  add     rsp, 50h
0x1800337c9  pop     rdi
0x1800337ca  retn
```
