# PimIMService::HandleAddOrEdit(OLITEMID const &,int)

- ea: `0x180007630`
- end: `0x180007840`
- name: `?HandleAddOrEdit@PimIMService@@UEAAJAEBUOLITEMID@@H@Z`
- size: `528`
- prototype: `__int64 __fastcall(PimIMService *this, const struct OLITEMID *, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x180003468`
- `0x18000428c`
- `0x1800046a4`
- `0x18000502c`
- `0x180006f48`
- `0x180007630`
- `0x1800086a0`
- `0x18000c734`
- `0x18000d248`
- `0x18000d63c`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800076ce`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800076eb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::HandleAddOrEdit(PimIMService *this, const struct OLITEMID *a2, __int64 a3)
{
  unsigned int v3; // r15d
  struct IUnknown *v6; // rbx
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // xmm0_8
  int IndexManager; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct IUnknown *v14; // rdx
  _BYTE v16[8]; // [rsp+30h] [rbp-29h] BYREF
  struct IndexedFiltering::IIndexManager *v17; // [rsp+38h] [rbp-21h] BYREF
  struct IUnknown *v18; // [rsp+40h] [rbp-19h] BYREF
  struct IUnknown *v19; // [rsp+48h] [rbp-11h] BYREF
  struct IUnknown **v20; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  int v22; // [rsp+60h] [rbp+7h]
  __int64 v23; // [rsp+70h] [rbp+17h] BYREF
  int v24; // [rsp+78h] [rbp+1Fh]

  v3 = a3;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      HANDLE_ADD_OR_EDIT_START,
      a3,
      1,
      &v23);
  v6 = 0;
  v16[1] = 1;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  if ( g_ZeroOlItemId == *(_DWORD *)a2 && *(&g_ZeroOlItemId + 1) == *((_DWORD *)a2 + 1) && !*((_DWORD *)a2 + 2) )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2456);
  v7 = FailOnServiceShutdown((__int64)this, (__int64)a2, a3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = *((_QWORD *)this + 27);
    v10 = *(_QWORD *)a2;
    v22 = *((_DWORD *)a2 + 2);
    v21 = v10;
    IndexManager = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, struct IUnknown **))(*(_QWORD *)v9 + 200LL))(
                     v9,
                     &v21,
                     &IID_IUnknown,
                     &v19);
    if ( IndexManager >= 0 )
    {
      v13 = *((_DWORD *)a2 + 2);
      v23 = *(_QWORD *)a2;
      v24 = v13;
      IndexManager = PimIndexedPropertySupplier::CreateInstance((int *)&v23, v19, &v20);
      if ( IndexManager >= 0 )
      {
        if ( *((_QWORD *)this + 36) )
        {
          v14 = (struct IUnknown *)(((unsigned __int64)this + 184)
                                  & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
          if ( !v14 || (ATL::AtlComPtrAssign(&v18, v14), (v6 = v18) == 0) )
          {
            IndexManager = -2147467262;
LABEL_21:
            v8 = IndexManager;
            goto LABEL_22;
          }
        }
        IndexManager = PimIMService::GetIndexManager((struct IndexedFiltering::IIndexManager **)this, 0, 1, &v17);
        if ( IndexManager >= 0 )
          IndexManager = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager *, struct IUnknown **, struct IUnknown *, _QWORD))(*(_QWORD *)v17 + 32LL))(
                           v17,
                           v20,
                           v6,
                           v3);
      }
    }
    if ( IndexManager == -2147023728 )
    {
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x40) != 0 )
        McTemplateU0q_EventWriteTransfer(v12, PIMIndex_HandleAddOnDeletedItem, *((unsigned int *)a2 + 2));
      IndexManager = 0;
    }
    goto LABEL_21;
  }
  Log_HREvent(
    (unsigned int)v7,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    2458);
LABEL_22:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  tlx::_UndoSolo__lambda_aa660732a5ff8b6caa642806e0daa7f6___::__UndoSolo__lambda_aa660732a5ff8b6caa642806e0daa7f6___(v16);
  return v8;
}

```

## disassembly

```asm
0x180007630  mov     [rsp-8+arg_18], rbx
0x180007635  push    rbp
0x180007636  push    rsi
0x180007637  push    rdi
0x180007638  push    r14
0x18000763a  push    r15
0x18000763c  lea     rbp, [rsp-37h]
0x180007641  sub     rsp, 90h
0x180007648  mov     rax, cs:__security_cookie
0x18000764f  xor     rax, rsp
0x180007652  mov     [rbp+57h+var_30], rax
0x180007656  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x18000765d  mov     r15d, r8d
0x180007660  mov     rdi, rdx
0x180007663  mov     r14, rcx
0x180007666  jz      short loc_18000768A
0x180007668  lea     rax, [rbp+57h+var_40]
0x18000766c  mov     r9d, 1
0x180007672  lea     rdx, HANDLE_ADD_OR_EDIT_START
0x180007679  mov     [rsp+0B0h+var_90], rax
0x18000767e  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180007685  call    McGenEventWrite_EventWriteTransfer
0x18000768a  mov     eax, dword ptr cs:?g_ZeroOlItemId@@3UOLITEMID@@B; OLITEMID const g_ZeroOlItemId
0x180007690  xor     ebx, ebx
0x180007692  mov     [rbp+57h+var_7F], 1
0x180007696  mov     [rbp+57h+var_60], 0
0x18000769e  mov     [rbp+57h+var_68], 0
0x1800076a6  mov     [rbp+57h+var_70], rbx
0x1800076aa  mov     [rbp+57h+var_78], rbx
0x1800076ae  cmp     eax, [rdi]
0x1800076b0  jnz     short loc_1800076DA
0x1800076b2  mov     eax, dword ptr cs:?g_ZeroOlItemId@@3UOLITEMID@@B+4; OLITEMID const g_ZeroOlItemId
0x1800076b8  cmp     eax, [rdi+4]
0x1800076bb  jnz     short loc_1800076DA
0x1800076bd  mov     eax, cs:dword_1800263D8
0x1800076c3  cmp     eax, [rdi+8]
0x1800076c6  jnz     short loc_1800076DA
0x1800076c8  mov     r8d, 998h
0x1800076ce  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800076d5  call    Log_AssertionEvent
0x1800076da  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x1800076df  mov     esi, eax
0x1800076e1  test    eax, eax
0x1800076e3  jns     short loc_180007703
0x1800076e5  mov     r9d, 99Ah
0x1800076eb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800076f2  mov     edx, 1
0x1800076f7  mov     ecx, eax
0x1800076f9  call    Log_HREvent
0x1800076fe  jmp     loc_1800077EE
0x180007703  mov     eax, [rdi+8]
0x180007706  lea     r9, [rbp+57h+var_68]
0x18000770a  mov     rcx, [r14+0D8h]
0x180007711  lea     r8, IID_IUnknown
0x180007718  movsd   xmm0, qword ptr [rdi]
0x18000771c  lea     rdx, [rbp+57h+var_58]
0x180007720  mov     [rbp+57h+var_50], eax
0x180007723  movsd   [rbp+57h+var_58], xmm0
0x180007728  mov     rax, [rcx]
0x18000772b  mov     rax, [rax+0C8h]
0x180007732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007737  test    eax, eax
0x180007739  js      loc_1800077CA
0x18000773f  movsd   xmm0, qword ptr [rdi]
0x180007743  lea     r8, [rbp+57h+var_60]
0x180007747  mov     eax, [rdi+8]
0x18000774a  lea     rcx, [rbp+57h+var_40]
0x18000774e  mov     rdx, [rbp+57h+var_68]
0x180007752  movsd   [rbp+57h+var_40], xmm0
0x180007757  mov     [rbp+57h+var_38], eax
0x18000775a  call    ?CreateInstance@PimIndexedPropertySupplier@@SAJUOLITEMID@@PEAUIUnknown@@PEAPEAV1@@Z; PimIndexedPropertySupplier::CreateInstance(OLITEMID,IUnknown *,PimIndexedPropertySupplier * *)
0x18000775f  test    eax, eax
0x180007761  js      short loc_1800077CA
0x180007763  cmp     [r14+120h], rbx
0x18000776a  jz      short loc_18000779A
0x18000776c  mov     rax, r14
0x18000776f  lea     rcx, [r14+0B8h]
0x180007776  neg     rax
0x180007779  sbb     rdx, rdx
0x18000777c  and     rdx, rcx; struct IUnknown *
0x18000777f  jz      short loc_180007793
0x180007781  lea     rcx, [rbp+57h+var_70]; struct IUnknown **
0x180007785  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000778a  mov     rbx, [rbp+57h+var_70]
0x18000778e  test    rbx, rbx
0x180007791  jnz     short loc_18000779A
0x180007793  mov     eax, 80004002h
0x180007798  jmp     short loc_1800077EC
0x18000779a  xor     edx, edx; int
0x18000779c  lea     r9, [rbp+57h+var_78]; struct IndexedFiltering::IIndexManager **
0x1800077a0  mov     rcx, r14; this
0x1800077a3  lea     r8d, [rdx+1]; int
0x1800077a7  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x1800077ac  test    eax, eax
0x1800077ae  js      short loc_1800077CA
0x1800077b0  mov     rcx, [rbp+57h+var_78]
0x1800077b4  mov     r9d, r15d
0x1800077b7  mov     rdx, [rbp+57h+var_60]
0x1800077bb  mov     r8, rbx
0x1800077be  mov     rax, [rcx]
0x1800077c1  mov     rax, [rax+20h]
0x1800077c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ca  cmp     eax, 80070490h
0x1800077cf  jnz     short loc_1800077EC
0x1800077d1  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 40h
0x1800077d8  jz      short loc_1800077EA
0x1800077da  mov     r8d, [rdi+8]
0x1800077de  lea     rdx, PIMIndex_HandleAddOnDeletedItem
0x1800077e5  call    McTemplateU0q_EventWriteTransfer
0x1800077ea  xor     eax, eax
0x1800077ec  mov     esi, eax
0x1800077ee  lea     rcx, [rbp+57h+var_78]
0x1800077f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800077f7  lea     rcx, [rbp+57h+var_70]
0x1800077fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007800  lea     rcx, [rbp+57h+var_68]
0x180007804  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007809  lea     rcx, [rbp+57h+var_60]
0x18000780d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007812  lea     rcx, [rbp+57h+var_80]
0x180007816  call    tlx___UndoSolo__lambda_aa660732a5ff8b6caa642806e0daa7f6_______UndoSolo__lambda_aa660732a5ff8b6caa642806e0daa7f6___
0x18000781b  mov     eax, esi
0x18000781d  mov     rcx, [rbp+57h+var_30]
0x180007821  xor     rcx, rsp; StackCookie
0x180007824  call    __security_check_cookie
0x180007829  mov     rbx, [rsp+0B0h+arg_18]
0x180007831  add     rsp, 90h
0x180007838  pop     r15
0x18000783a  pop     r14
0x18000783c  pop     rdi
0x18000783d  pop     rsi
0x18000783e  pop     rbp
0x18000783f  retn
```
