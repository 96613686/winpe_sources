# PimIMService::UpdateFolder(SyncPartnerData const &,IPOutlookFolderCollection *,int)

- ea: `0x18000ab48`
- end: `0x18000ad98`
- name: `?UpdateFolder@PimIMService@@AEAAJAEBUSyncPartnerData@@PEAUIPOutlookFolderCollection@@H@Z`
- size: `592`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, const struct SyncPartnerData *, struct IPOutlookFolderCollection *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000b004`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180003f90`
- `0x18000428c`
- `0x180004370`
- `0x180004490`
- `0x18000523c`
- `0x180009250`
- `0x18000ab48`
- `0x18000c51c`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x18000ad33`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::UpdateFolder(
        PimIMService *this,
        const struct SyncPartnerData *a2,
        struct IPOutlookFolderCollection *a3,
        unsigned int a4)
{
  __int64 v8; // r8
  int v9; // edi
  __int64 v10; // rax
  int v11; // eax
  int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  _BYTE v16[4]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v17[4]; // [rsp+44h] [rbp-55h] BYREF
  __int64 v18; // [rsp+48h] [rbp-51h] BYREF
  int v19; // [rsp+50h] [rbp-49h] BYREF
  __int64 v20; // [rsp+58h] [rbp-41h] BYREF
  int v21; // [rsp+60h] [rbp-39h] BYREF
  int v22; // [rsp+64h] [rbp-35h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v24[3]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v25; // [rsp+98h] [rbp-1h] BYREF
  int v26; // [rsp+A0h] [rbp+7h]
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+A8h] [rbp+Fh] BYREF

  v18 = 0;
  v25 = 0;
  v26 = 0;
  v22 = 0;
  v20 = 0;
  utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v23);
  utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v24);
  v9 = 1;
  v19 = 1;
  v21 = 0;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      (const EVENT_DESCRIPTOR *)PIMIndex_FolderChangeProcessing_START,
      v8,
      1u,
      &v27);
  v17[1] = 1;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      (const EVENT_DESCRIPTOR *)UPDATE_FOLDER_START,
      v8,
      1u,
      &v27);
  v10 = *(_QWORD *)a3;
  v16[1] = 1;
  v11 = (*(__int64 (__fastcall **)(struct IPOutlookFolderCollection *, _QWORD, __int64 *))(v10 + 96))(a3, a4, &v18);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 1575;
LABEL_11:
    v14 = (unsigned int)v11;
    goto LABEL_20;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 48LL))(v18, &v21);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 1578;
    goto LABEL_11;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v25);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 1581;
    goto LABEL_11;
  }
  while ( 1 )
  {
    v12 = PimIMService::CollectChanges(v24, (__int64 *)a2, &v25, &v20, v9 == 0, v24, v23);
    if ( v12 < 0 )
      break;
    if ( v23[0] == v23[1] )
    {
      tlx::_UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___::__UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___(v16);
      tlx::_UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___::__UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___(v17);
      utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v24);
      utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v23);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
      return 0;
    }
    v12 = PimIMService::ProcessChanges(this, a2, v23, v24, &v22, &v19);
    if ( v12 < 0 )
    {
      v13 = 1600;
      goto LABEL_19;
    }
    v9 = v19;
  }
  v13 = 1592;
LABEL_19:
  v14 = (unsigned int)v12;
LABEL_20:
  Log_HREvent(
    v14,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v13);
  tlx::_UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___::__UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___(v16);
  tlx::_UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___::__UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___(v17);
  utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v24);
  utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit((__int64)v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000ab48  push    rbp
0x18000ab4a  push    rbx
0x18000ab4b  push    rsi
0x18000ab4c  push    rdi
0x18000ab4d  push    r12
0x18000ab4f  push    r14
0x18000ab51  push    r15
0x18000ab53  lea     rbp, [rsp-27h]
0x18000ab58  sub     rsp, 0C0h
0x18000ab5f  mov     rax, cs:__security_cookie
0x18000ab66  xor     rax, rsp
0x18000ab69  mov     [rbp+57h+var_38], rax
0x18000ab6d  xor     eax, eax
0x18000ab6f  mov     [rbp+57h+var_A8], 0
0x18000ab77  mov     r15, rcx
0x18000ab7a  mov     [rbp+57h+var_58], rax
0x18000ab7e  lea     rcx, [rbp+57h+var_88]
0x18000ab82  mov     [rbp+57h+var_50], eax
0x18000ab85  mov     [rbp+57h+var_8C], eax
0x18000ab88  mov     r14d, r9d
0x18000ab8b  mov     [rbp+57h+var_98], rax
0x18000ab8f  mov     rbx, r8
0x18000ab92  mov     rsi, rdx
0x18000ab95  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18000ab9a  lea     rcx, [rbp+57h+var_70]
0x18000ab9e  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18000aba3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x18000abaa  mov     r12d, 1
0x18000abb0  mov     edi, r12d
0x18000abb3  mov     [rbp+57h+var_A0], r12d
0x18000abb7  mov     [rbp+57h+var_90], 0
0x18000abbe  jz      short loc_18000ABDF
0x18000abc0  lea     rax, [rbp+57h+var_48]
0x18000abc4  mov     r9d, r12d
0x18000abc7  lea     rdx, PIMIndex_FolderChangeProcessing_START
0x18000abce  mov     [rsp+0F0h+var_D0], rax
0x18000abd3  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000abda  call    McGenEventWrite_EventWriteTransfer
0x18000abdf  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x18000abe6  mov     [rbp+57h+var_AB], r12b
0x18000abea  jz      short loc_18000AC0B
0x18000abec  lea     rax, [rbp+57h+var_48]
0x18000abf0  mov     r9d, r12d
0x18000abf3  lea     rdx, UPDATE_FOLDER_START
0x18000abfa  mov     [rsp+0F0h+var_D0], rax
0x18000abff  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000ac06  call    McGenEventWrite_EventWriteTransfer
0x18000ac0b  mov     rax, [rbx]
0x18000ac0e  lea     r8, [rbp+57h+var_A8]
0x18000ac12  mov     edx, r14d
0x18000ac15  mov     [rbp+57h+var_AF], r12b
0x18000ac19  mov     rcx, rbx
0x18000ac1c  mov     rax, [rax+60h]
0x18000ac20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac25  mov     ebx, eax
0x18000ac27  test    eax, eax
0x18000ac29  jns     short loc_18000AC33
0x18000ac2b  mov     r9d, 627h
0x18000ac31  jmp     short loc_18000AC75
0x18000ac33  mov     rcx, [rbp+57h+var_A8]
0x18000ac37  lea     rdx, [rbp+57h+var_90]
0x18000ac3b  mov     rax, [rcx]
0x18000ac3e  mov     rax, [rax+30h]
0x18000ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac47  mov     ebx, eax
0x18000ac49  test    eax, eax
0x18000ac4b  jns     short loc_18000AC55
0x18000ac4d  mov     r9d, 62Ah
0x18000ac53  jmp     short loc_18000AC75
0x18000ac55  mov     rcx, [rbp+57h+var_A8]
0x18000ac59  lea     rdx, [rbp+57h+var_58]
0x18000ac5d  mov     rax, [rcx]
0x18000ac60  mov     rax, [rax+18h]
0x18000ac64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac69  mov     ebx, eax
0x18000ac6b  test    eax, eax
0x18000ac6d  jns     short loc_18000AC7C
0x18000ac6f  mov     r9d, 62Dh
0x18000ac75  mov     ecx, eax
0x18000ac77  jmp     loc_18000AD33
0x18000ac7c  xor     eax, eax
0x18000ac7e  lea     rcx, [rbp+57h+var_88]
0x18000ac82  mov     [rsp+0F0h+var_C0], rcx
0x18000ac87  lea     r9, [rbp+57h+var_98]
0x18000ac8b  lea     rcx, [rbp+57h+var_70]
0x18000ac8f  test    edi, edi
0x18000ac91  mov     [rsp+0F0h+var_C8], rcx
0x18000ac96  lea     r8, [rbp+57h+var_58]
0x18000ac9a  setz    al
0x18000ac9d  mov     rdx, rsi
0x18000aca0  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000aca4  call    ?CollectChanges@PimIMService@@AEAAJAEBUSyncPartnerData@@AEAUOLITEMID@@PEAPEAUIUnknown@@HAEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@AEAV?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@6@@Z; PimIMService::CollectChanges(SyncPartnerData const &,OLITEMID &,IUnknown * *,int,utl::vector<OLITEMID,utl::allocator<OLITEMID>> &,utl::vector<ChangeInfo,utl::allocator<ChangeInfo>> &)
0x18000aca9  mov     ebx, eax
0x18000acab  test    eax, eax
0x18000acad  js      short loc_18000AD2B
0x18000acaf  mov     rax, [rbp+57h+var_80]
0x18000acb3  cmp     [rbp+57h+var_88], rax
0x18000acb7  jz      short loc_18000ACF1
0x18000acb9  lea     rax, [rbp+57h+var_A0]
0x18000acbd  mov     rdx, rsi
0x18000acc0  mov     [rsp+0F0h+var_C8], rax
0x18000acc5  lea     r9, [rbp+57h+var_70]
0x18000acc9  lea     rax, [rbp+57h+var_8C]
0x18000accd  mov     rcx, r15
0x18000acd0  lea     r8, [rbp+57h+var_88]
0x18000acd4  mov     [rsp+0F0h+var_D0], rax
0x18000acd9  call    ?ProcessChanges@PimIMService@@AEAAJAEBUSyncPartnerData@@AEBV?$vector@UChangeInfo@@V?$allocator@UChangeInfo@@@utl@@@utl@@AEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@4@AEAH3@Z; PimIMService::ProcessChanges(SyncPartnerData const &,utl::vector<ChangeInfo,utl::allocator<ChangeInfo>> const &,utl::vector<OLITEMID,utl::allocator<OLITEMID>> &,int &,int &)
0x18000acde  mov     ebx, eax
0x18000ace0  test    eax, eax
0x18000ace2  js      short loc_18000ACE9
0x18000ace4  mov     edi, [rbp+57h+var_A0]
0x18000ace7  jmp     short loc_18000AC7C
0x18000ace9  mov     r9d, 640h
0x18000acef  jmp     short loc_18000AD31
0x18000acf1  lea     rcx, [rbp+57h+var_B0]
0x18000acf5  call    tlx___UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa_______UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___
0x18000acfa  lea     rcx, [rbp+57h+var_AC]
0x18000acfe  call    tlx___UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400_______UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___
0x18000ad03  lea     rcx, [rbp+57h+var_70]
0x18000ad07  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x18000ad0c  lea     rcx, [rbp+57h+var_88]
0x18000ad10  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x18000ad15  lea     rcx, [rbp+57h+var_98]
0x18000ad19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad1e  lea     rcx, [rbp+57h+var_A8]
0x18000ad22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad27  xor     eax, eax
0x18000ad29  jmp     short loc_18000AD7A
0x18000ad2b  mov     r9d, 638h
0x18000ad31  mov     ecx, ebx
0x18000ad33  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ad3a  mov     edx, r12d
0x18000ad3d  call    Log_HREvent
0x18000ad42  lea     rcx, [rbp+57h+var_B0]
0x18000ad46  call    tlx___UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa_______UndoSolo__lambda_66f2dd8ff912da7f37599d12d5aec3fa___
0x18000ad4b  lea     rcx, [rbp+57h+var_AC]
0x18000ad4f  call    tlx___UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400_______UndoSolo__lambda_4cb4c933a9a092a8ce290935f9cb3400___
0x18000ad54  lea     rcx, [rbp+57h+var_70]
0x18000ad58  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x18000ad5d  lea     rcx, [rbp+57h+var_88]
0x18000ad61  call    ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
0x18000ad66  lea     rcx, [rbp+57h+var_98]
0x18000ad6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad6f  lea     rcx, [rbp+57h+var_A8]
0x18000ad73  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ad78  mov     eax, ebx
0x18000ad7a  mov     rcx, [rbp+57h+var_38]
0x18000ad7e  xor     rcx, rsp; StackCookie
0x18000ad81  call    __security_check_cookie
0x18000ad86  add     rsp, 0C0h
0x18000ad8d  pop     r15
0x18000ad8f  pop     r14
0x18000ad91  pop     r12
0x18000ad93  pop     rdi
0x18000ad94  pop     rsi
0x18000ad95  pop     rbx
0x18000ad96  pop     rbp
0x18000ad97  retn
```
