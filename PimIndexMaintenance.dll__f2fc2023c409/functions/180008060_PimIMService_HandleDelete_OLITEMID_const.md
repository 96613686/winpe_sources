# PimIMService::HandleDelete(OLITEMID const &)

- ea: `0x180008060`
- end: `0x180008191`
- name: `?HandleDelete@PimIMService@@UEAAJAEBUOLITEMID@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IndexedFiltering::IIndexManager **this, const struct OLITEMID *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003468`
- `0x18000428c`
- `0x180004744`
- `0x18000502c`
- `0x180006f48`
- `0x180008060`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800080ed`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000812b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::HandleDelete(
        struct IndexedFiltering::IIndexManager **this,
        const struct OLITEMID *a2,
        __int64 a3)
{
  struct IUnknown *v5; // rbx
  struct IUnknown *v6; // rdx
  unsigned int v7; // edi
  int IndexManager; // eax
  _BYTE v10[8]; // [rsp+30h] [rbp-30h] BYREF
  struct IndexedFiltering::IIndexManager *v11; // [rsp+38h] [rbp-28h] BYREF
  struct IUnknown *v12[2]; // [rsp+40h] [rbp-20h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      HANDLE_DELETE_START,
      a3,
      1,
      v12);
  v5 = 0;
  v10[1] = 1;
  v12[0] = 0;
  if ( !this[36]
    || (v6 = (struct IUnknown *)((unsigned __int64)(this + 23)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64))) != 0
    && (ATL::AtlComPtrAssign(v12, v6), (v5 = v12[0]) != 0) )
  {
    v11 = 0;
    IndexManager = PimIMService::GetIndexManager(this, 0, 1, &v11);
    v7 = IndexManager;
    if ( IndexManager >= 0 )
      v7 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager *, const struct OLITEMID *, struct IUnknown *))(*(_QWORD *)v11 + 40LL))(
             v11,
             a2,
             v5);
    else
      Log_HREvent(
        (unsigned int)IndexManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2520);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
  }
  else
  {
    v7 = -2147467262;
    Log_HREvent(
      2147500034LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2515);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v12);
  tlx::_UndoSolo__lambda_cb46689e06a0ea390f9285eeead98947___::__UndoSolo__lambda_cb46689e06a0ea390f9285eeead98947___(v10);
  return v7;
}

```

## disassembly

```asm
0x180008060  mov     [rsp-18h+arg_10], rbx
0x180008065  push    rbp
0x180008066  push    rsi
0x180008067  push    rdi
0x180008068  mov     rbp, rsp
0x18000806b  sub     rsp, 60h
0x18000806f  mov     rax, cs:__security_cookie
0x180008076  xor     rax, rsp
0x180008079  mov     [rbp+var_10], rax
0x18000807d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x180008084  mov     rsi, rdx
0x180008087  mov     rdi, rcx
0x18000808a  jz      short loc_1800080AE
0x18000808c  lea     rax, [rbp+var_20]
0x180008090  mov     r9d, 1
0x180008096  lea     rdx, HANDLE_DELETE_START
0x18000809d  mov     [rsp+60h+var_40], rax
0x1800080a2  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x1800080a9  call    McGenEventWrite_EventWriteTransfer
0x1800080ae  xor     ebx, ebx
0x1800080b0  mov     [rbp+var_2F], 1
0x1800080b4  mov     [rbp+var_20], rbx
0x1800080b8  cmp     [rdi+120h], rbx
0x1800080bf  jz      short loc_180008105
0x1800080c1  mov     rax, rdi
0x1800080c4  lea     rcx, [rdi+0B8h]
0x1800080cb  neg     rax
0x1800080ce  sbb     rdx, rdx
0x1800080d1  and     rdx, rcx; struct IUnknown *
0x1800080d4  jz      short loc_1800080E8
0x1800080d6  lea     rcx, [rbp+var_20]; struct IUnknown **
0x1800080da  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800080df  mov     rbx, [rbp+var_20]
0x1800080e3  test    rbx, rbx
0x1800080e6  jnz     short loc_180008105
0x1800080e8  mov     edi, 80004002h
0x1800080ed  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800080f4  mov     ecx, edi
0x1800080f6  mov     r9d, 9D3h
0x1800080fc  xor     edx, edx
0x1800080fe  call    Log_HREvent
0x180008103  jmp     short loc_180008161
0x180008105  xor     edx, edx; int
0x180008107  mov     [rbp+var_28], 0
0x18000810f  lea     r9, [rbp+var_28]; struct IndexedFiltering::IIndexManager **
0x180008113  mov     rcx, rdi; this
0x180008116  lea     r8d, [rdx+1]; int
0x18000811a  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x18000811f  mov     edi, eax
0x180008121  test    eax, eax
0x180008123  jns     short loc_180008140
0x180008125  mov     r9d, 9D8h
0x18000812b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008132  mov     edx, 1
0x180008137  mov     ecx, eax
0x180008139  call    Log_HREvent
0x18000813e  jmp     short loc_180008158
0x180008140  mov     rcx, [rbp+var_28]
0x180008144  mov     r8, rbx
0x180008147  mov     rdx, rsi
0x18000814a  mov     rax, [rcx]
0x18000814d  mov     rax, [rax+28h]
0x180008151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008156  mov     edi, eax
0x180008158  lea     rcx, [rbp+var_28]
0x18000815c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008161  lea     rcx, [rbp+var_20]
0x180008165  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000816a  lea     rcx, [rbp+var_30]
0x18000816e  call    tlx___UndoSolo__lambda_cb46689e06a0ea390f9285eeead98947_______UndoSolo__lambda_cb46689e06a0ea390f9285eeead98947___
0x180008173  mov     eax, edi
0x180008175  mov     rcx, [rbp+var_10]
0x180008179  xor     rcx, rsp; StackCookie
0x18000817c  call    __security_check_cookie
0x180008181  mov     rbx, [rsp+60h+arg_10]
0x180008189  add     rsp, 60h
0x18000818d  pop     rdi
0x18000818e  pop     rsi
0x18000818f  pop     rbp
0x180008190  retn
```
