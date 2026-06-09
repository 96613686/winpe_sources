# PimIMService::OnStopping(int)

- ea: `0x180008fe0`
- end: `0x1800090ce`
- name: `?OnStopping@PimIMService@@UEAAJH@Z`
- size: `238`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003560`

## callees

- `0x180002c2c`
- `0x180002da8`
- `0x1800031d0`
- `0x180008fe0`
- `0x180009778`
- `0x180009814`
- `0x180009c48`
- `0x1800104b8`
- `0x180010638`
- `0x18001146c`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x18000904e`
- `ESENT!JetCommitTransaction` at `0x18000904e`

## string_xrefs

- `0x180008ffc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009023`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000907a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800090b1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::OnStopping(PimIMService *this)
{
  int v2; // eax
  int v3; // eax
  JET_SESID v4; // rcx
  JET_ERR v5; // eax
  int HresultFromJetError; // ebx
  __int64 v7; // r8
  ESEDataSource *v8; // rcx
  int v9; // eax

  v2 = RpcTeardown();
  if ( v2 < 0 )
    Log_HREvent(
      (unsigned int)v2,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      428);
  PimIMService::SetServiceShuttingdown();
  v3 = PimIMService::Reset(this);
  if ( v3 < 0 )
    Log_HREvent(
      (unsigned int)v3,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      436);
  if ( qword_18002D0C0 )
  {
    v4 = *(_QWORD *)(qword_18002D0C0 + 56);
    if ( v4 != -1 )
    {
      v5 = JetCommitTransaction(v4, 8u);
      if ( v5 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v5);
        Log_HREvent_2((unsigned int)HresultFromJetError, 0, v7, 720);
        if ( HresultFromJetError < 0 )
          Log_HREvent(
            (unsigned int)HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            439);
      }
    }
  }
  ATL::CComPtrBase<IndexedFiltering::IIndexManager>::Release((char *)this + 464);
  McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context);
  v9 = ESEDataSource::Terminate(v8);
  if ( v9 < 0 )
    Log_HREvent(
      (unsigned int)v9,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      448);
  return 0;
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp+arg_0], rbx
0x180008fe5  push    rdi
0x180008fe6  sub     rsp, 30h
0x180008fea  mov     rdi, rcx
0x180008fed  call    ?RpcTeardown@@YAJXZ; RpcTeardown(void)
0x180008ff2  test    eax, eax
0x180008ff4  jns     short loc_18000900C
0x180008ff6  mov     r9d, 1ACh
0x180008ffc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009003  xor     edx, edx
0x180009005  mov     ecx, eax
0x180009007  call    Log_HREvent
0x18000900c  call    ?SetServiceShuttingdown@PimIMService@@SAXXZ; PimIMService::SetServiceShuttingdown(void)
0x180009011  mov     rcx, rdi; this
0x180009014  call    ?Reset@PimIMService@@QEAAJXZ; PimIMService::Reset(void)
0x180009019  test    eax, eax
0x18000901b  jns     short loc_180009033
0x18000901d  mov     r9d, 1B4h
0x180009023  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000902a  xor     edx, edx
0x18000902c  mov     ecx, eax
0x18000902e  call    Log_HREvent
0x180009033  mov     rax, cs:qword_18002D0C0
0x18000903a  test    rax, rax
0x18000903d  jz      short loc_18000908A
0x18000903f  mov     rcx, [rax+38h]; sesid
0x180009043  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009047  jz      short loc_18000908A
0x180009049  mov     edx, 8; grbit
0x18000904e  call    cs:__imp_JetCommitTransaction
0x180009054  test    eax, eax
0x180009056  jns     short loc_18000908A
0x180009058  mov     ecx, eax; int
0x18000905a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000905f  xor     edx, edx
0x180009061  mov     r9d, 2D0h
0x180009067  mov     ecx, eax
0x180009069  mov     ebx, eax
0x18000906b  call    Log_HREvent_2
0x180009070  test    ebx, ebx
0x180009072  jns     short loc_18000908A
0x180009074  mov     r9d, 1B7h
0x18000907a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009081  xor     edx, edx
0x180009083  mov     ecx, ebx
0x180009085  call    Log_HREvent
0x18000908a  lea     rcx, [rdi+1D0h]
0x180009091  call    ?Release@?$CComPtrBase@UIIndexManager@IndexedFiltering@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IndexedFiltering::IIndexManager>::Release(void)
0x180009096  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000909d  call    McGenEventUnregister_EventUnregister
0x1800090a2  call    ?Terminate@ESEDataSource@@QEAAJXZ; ESEDataSource::Terminate(void)
0x1800090a7  test    eax, eax
0x1800090a9  jns     short loc_1800090C1
0x1800090ab  mov     r9d, 1C0h
0x1800090b1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800090b8  xor     edx, edx
0x1800090ba  mov     ecx, eax
0x1800090bc  call    Log_HREvent
0x1800090c1  mov     rbx, [rsp+38h+arg_0]
0x1800090c6  xor     eax, eax
0x1800090c8  add     rsp, 30h
0x1800090cc  pop     rdi
0x1800090cd  retn
```
