# Wallet::WalletWebService::Initialize(ATL::CComPtr<IWalletItemManager> &,ATL::CComPtr<Wallet::WalletWebServiceManager>)

- ea: `0x180034920`
- end: `0x1800349df`
- name: `?Initialize@WalletWebService@Wallet@@QEAAJAEAV?$CComPtr@UIWalletItemManager@@@ATL@@V?$CComPtr@VWalletWebServiceManager@Wallet@@@4@@Z`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x18001108c`
- `0x18001183c`
- `0x180018128`
- `0x180034920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003497d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003497d`

## string_xrefs

- `0x180034966`: `Software\Microsoft\Wallet\WalletWebServiceManager`
- `0x1800349a4`: `MaximumServiceRetries`
- `0x1800349b9`: `MaximumDaysServiceRetries`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebService::Initialize(__int64 a1, struct IUnknown **a2, __int64 *a3)
{
  struct IUnknown *v3; // rdx
  struct IUnknown **v5; // rcx
  __int64 v7; // rdx
  signed int LastError; // eax
  unsigned int v9; // ebx

  v3 = *a2;
  v5 = (struct IUnknown **)(a1 + 128);
  if ( *v5 != v3 )
    ATL::AtlComPtrAssign(v5, v3);
  v7 = *a3;
  *a3 = 0;
  ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach((__int64 *)(a1 + 136), v7);
  if ( (unsigned int)ATL::CRegKey::Open(
                       (HKEY *)(a1 + 144),
                       HKEY_LOCAL_MACHINE,
                       L"Software\\Microsoft\\Wallet\\WalletWebServiceManager",
                       0x20019u) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v9 = -2143748092;
    }
  }
  else
  {
    v9 = 0;
    ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)(a1 + 144), L"MaximumServiceRetries", (unsigned int *)(a1 + 116));
    ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)(a1 + 144), L"MaximumDaysServiceRetries", (unsigned int *)(a1 + 120));
    *(_DWORD *)(a1 + 112) = 1;
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(a3);
  return v9;
}

```

## disassembly

```asm
0x180034920  push    rbx
0x180034922  push    rbp
0x180034923  push    rsi
0x180034924  push    rdi
0x180034925  sub     rsp, 28h
0x180034929  mov     rdx, [rdx]; struct IUnknown *
0x18003492c  mov     rdi, rcx
0x18003492f  sub     rcx, 0FFFFFFFFFFFFFF80h; struct IUnknown **
0x180034933  mov     rsi, r8
0x180034936  cmp     [rcx], rdx
0x180034939  jz      short loc_180034940
0x18003493b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180034940  mov     rdx, [rsi]
0x180034943  lea     rcx, [rdi+88h]
0x18003494a  mov     qword ptr [rsi], 0
0x180034951  call    ?Attach@?$CComPtrBase@UIWalletWebServiceRequest@Wallet@@@ATL@@QEAAXPEAUIWalletWebServiceRequest@Wallet@@@Z; ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach(Wallet::IWalletWebServiceRequest *)
0x180034956  lea     rbp, [rdi+90h]
0x18003495d  mov     r9d, 20019h; unsigned int
0x180034963  mov     rcx, rbp; this
0x180034966  lea     r8, ?sc_szWalletWebServiceManagerXmlRegKey@WalletWebServiceManager@Wallet@@2QBGB; "Software\\Microsoft\\Wallet\\WalletWebS"...
0x18003496d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180034974  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180034979  test    eax, eax
0x18003497b  jz      short loc_18003499D
0x18003497d  call    cs:__imp_GetLastError
0x180034983  mov     ebx, eax
0x180034985  test    eax, eax
0x180034987  jz      short loc_180034996
0x180034989  jle     short loc_1800349CC
0x18003498b  movzx   ebx, ax
0x18003498e  or      ebx, 80070000h
0x180034994  jmp     short loc_1800349CC
0x180034996  mov     ebx, 80390004h
0x18003499b  jmp     short loc_1800349CC
0x18003499d  lea     r8, [rdi+74h]; unsigned int *
0x1800349a1  mov     rcx, rbp; this
0x1800349a4  lea     rdx, ?sc_szMaximumServiceRetriesRegKeyName@WalletWebService@Wallet@@2QBGB; "MaximumServiceRetries"
0x1800349ab  xor     ebx, ebx
0x1800349ad  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800349b2  lea     r8, [rdi+78h]; unsigned int *
0x1800349b6  mov     rcx, rbp; this
0x1800349b9  lea     rdx, ?sc_szMaximumDaysServiceRetriesRegKeyName@WalletWebService@Wallet@@2QBGB; "MaximumDaysServiceRetries"
0x1800349c0  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800349c5  mov     dword ptr [rdi+70h], 1
0x1800349cc  mov     rcx, rsi
0x1800349cf  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800349d4  mov     eax, ebx
0x1800349d6  add     rsp, 28h
0x1800349da  pop     rdi
0x1800349db  pop     rsi
0x1800349dc  pop     rbp
0x1800349dd  pop     rbx
0x1800349de  retn
```
