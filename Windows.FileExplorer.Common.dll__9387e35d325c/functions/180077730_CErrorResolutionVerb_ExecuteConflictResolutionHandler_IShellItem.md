# CErrorResolutionVerb::_ExecuteConflictResolutionHandler(IShellItem *)

- ea: `0x180077730`
- end: `0x18007797b`
- name: `?_ExecuteConflictResolutionHandler@CErrorResolutionVerb@@AEAAJPEAUIShellItem@@@Z`
- size: `587`
- prototype: `int(CErrorResolutionVerb *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180072cf0`

## callees

- `0x180004a54`
- `0x18000b9b0`
- `0x18001213c`
- `0x180037780`
- `0x1800386e4`
- `0x180044718`
- `0x180044da8`
- `0x180074828`
- `0x180077730`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_SHExtCoCreateInstanceCheckCategory` at `0x1800778fb`
- `Windows.Storage!__imp_SHExtCoCreateInstanceCheckCategory` at `0x1800778fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180077890`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180077890`
- `PROPSYS!PropVariantToGUID` at `0x180077884`
- `PROPSYS!PropVariantToGUID` at `0x180077884`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-1!MonitorFromPoint` at `0x18007791b`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-1!MonitorFromPoint` at `0x18007791b`

## string_xrefs

- `0x18007784f`: `ConflictResolutionCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CErrorResolutionVerb::_ExecuteConflictResolutionHandler(POINT *this, struct IShellItem *a2)
{
  const unsigned __int16 *v4; // rdx
  int FileSystemOrPlaceholderPath; // ebx
  __int64 v6; // rdx
  HRESULT FailIf; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  bool v10; // bl
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, SyncEngineStatusUtils *, HMONITOR); // rbx
  HMONITOR v13; // rax
  int *v15; // [rsp+20h] [rbp-39h]
  enum SYNC_TRANSFER_STATUS v16[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v17; // [rsp+48h] [rbp-11h] BYREF
  SyncEngineStatusUtils *v18; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h]
  __int64 v20; // [rsp+60h] [rbp+7h]
  PROPVARIANT propvar[3]; // [rsp+68h] [rbp+Fh] BYREF
  GUID pguid; // [rsp+80h] [rbp+27h] BYREF

  v18 = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  v19 = -1;
  v20 = -1;
  FileSystemOrPlaceholderPath = GetFileSystemOrPlaceholderPath(a2, (unsigned __int16 **)&v18);
  if ( FileSystemOrPlaceholderPath >= 0 )
  {
    FileSystemOrPlaceholderPath = -2147023728;
    LODWORD(v17) = 0;
    v16[0] = STS_NONE;
    if ( (int)SyncEngineStatusUtils::GetSyncTransferStatusFromIndexer(
                v18,
                v4,
                (struct ISyncTransferStatus *)&v17,
                v16,
                v15) >= 0
      && (_DWORD)v17 == 16
      && v16[0] == (STS_INCOMPLETE|STS_EXCLUDED|STS_TRANSFERRING|STS_NEEDSDOWNLOAD|STS_NEEDSUPLOAD|0x80040800) )
    {
      v17 = 0;
      *(_QWORD *)v16 = 0;
      FailIf = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, enum SYNC_TRANSFER_STATUS *))a2->lpVtbl->QueryInterface)(
                 a2,
                 &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                 v16);
      if ( FailIf < 0 )
        goto LABEL_15;
      FailIf = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**(_QWORD **)v16 + 64LL))(
                 *(_QWORD *)v16,
                 1024,
                 &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                 &v17);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 16LL))(*(_QWORD *)v16);
      if ( FailIf < 0 )
        goto LABEL_15;
      pguid = GUID_NULL;
      LOWORD(propvar[0]) = 0;
      FailIf = CPropertyStoreHelperBase<INamedPropertyStore>::GetFailIfEmpty<unsigned short const *>(
                 &v17,
                 L"ConflictResolutionCLSID",
                 propvar);
      if ( FailIf >= 0 )
      {
        pguid = GUID_NULL;
        if ( LOWORD(propvar[0]) )
          FailIf = PropVariantToGUID(propvar, &pguid);
        else
          FailIf = -2147023728;
      }
      PropVariantClear(propvar);
      if ( FailIf < 0 )
      {
LABEL_15:
        FileSystemOrPlaceholderPath = FailIf;
      }
      else
      {
        v10 = memcmp_0(&pguid, &CLSID_CachedFileUpdaterMergeHandler, 0x10u) == 0;
        *(_QWORD *)v16 = 0;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v16);
        FileSystemOrPlaceholderPath = SHExtCoCreateInstanceCheckCategory(
                                        &pguid,
                                        &CATID_FilePlaceholderMergeHandler,
                                        0,
                                        v10 ? 1 : 4,
                                        0,
                                        &GUID_d97b5aac_c792_433c_975d_35c4eadc7a9d,
                                        v16);
        if ( FileSystemOrPlaceholderPath >= 0 )
        {
          v11 = *(_QWORD *)v16;
          v12 = *(__int64 (__fastcall **)(__int64, SyncEngineStatusUtils *, HMONITOR))(**(_QWORD **)v16 + 32LL);
          v13 = MonitorFromPoint(this[10], 2u);
          FileSystemOrPlaceholderPath = v12(v11, v18, v13);
        }
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v16);
      }
      CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(&v17, v6, v8, v9);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  return (unsigned int)FileSystemOrPlaceholderPath;
}

```

## disassembly

```asm
0x180077730  mov     [rsp-8+arg_10], rbx
0x180077735  mov     [rsp-8+arg_18], rsi
0x18007773a  push    rbp
0x18007773b  push    rdi
0x18007773c  push    r14
0x18007773e  lea     rbp, [rsp-47h]
0x180077743  sub     rsp, 0A0h
0x18007774a  mov     rax, cs:__security_cookie
0x180077751  xor     rax, rsp
0x180077754  mov     [rbp+57h+var_20], rax
0x180077758  mov     rdi, rdx
0x18007775b  mov     rsi, rcx
0x18007775e  xor     r14d, r14d
0x180077761  mov     [rbp+57h+var_60], r14
0x180077765  mov     [rbp+57h+var_58], r14
0x180077769  mov     [rbp+57h+var_50], r14
0x18007776d  lea     rcx, [rbp+57h+var_60]
0x180077771  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180077776  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007777a  mov     [rbp+57h+var_58], rax
0x18007777e  mov     [rbp+57h+var_50], rax
0x180077782  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x180077786  mov     rcx, rdi; struct IShellItem *
0x180077789  call    ?GetFileSystemOrPlaceholderPath@@YAJPEAUIShellItem@@PEAPEAG@Z; GetFileSystemOrPlaceholderPath(IShellItem *,ushort * *)
0x18007778e  mov     ebx, eax
0x180077790  test    eax, eax
0x180077792  js      loc_18007794C
0x180077798  mov     ebx, 80070490h
0x18007779d  mov     dword ptr [rbp+57h+var_68], r14d
0x1800777a1  mov     [rbp+57h+var_70], r14d
0x1800777a5  lea     r9, [rbp+57h+var_70]; enum SYNC_TRANSFER_STATUS *
0x1800777a9  lea     r8, [rbp+57h+var_68]; struct ISyncTransferStatus *
0x1800777ad  mov     rcx, [rbp+57h+var_60]; this
0x1800777b1  call    ?GetSyncTransferStatusFromIndexer@SyncEngineStatusUtils@@YAJPEBGPEAUISyncTransferStatus@@PEAW4SYNC_TRANSFER_STATUS@@PEAJ@Z; SyncEngineStatusUtils::GetSyncTransferStatusFromIndexer(ushort const *,ISyncTransferStatus *,SYNC_TRANSFER_STATUS *,long *)
0x1800777b6  test    eax, eax
0x1800777b8  js      loc_18007794C
0x1800777be  cmp     dword ptr [rbp+57h+var_68], 10h
0x1800777c2  jnz     loc_18007794C
0x1800777c8  cmp     [rbp+57h+var_70], 80040B07h
0x1800777cf  jnz     loc_18007794C
0x1800777d5  mov     [rbp+57h+var_68], r14
0x1800777d9  mov     qword ptr [rbp+57h+var_70], r14
0x1800777dd  mov     rax, [rdi]
0x1800777e0  lea     r8, [rbp+57h+var_70]
0x1800777e4  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1800777eb  mov     rcx, rdi
0x1800777ee  mov     rax, [rax]
0x1800777f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777f6  mov     edi, eax
0x1800777f8  test    eax, eax
0x1800777fa  js      loc_180077940
0x180077800  mov     rcx, qword ptr [rbp+57h+var_70]
0x180077804  mov     rax, [rcx]
0x180077807  lea     r9, [rbp+57h+var_68]
0x18007780b  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180077812  mov     edx, 400h
0x180077817  mov     rax, [rax+40h]
0x18007781b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077820  mov     edi, eax
0x180077822  mov     rcx, qword ptr [rbp+57h+var_70]
0x180077826  mov     rax, [rcx]
0x180077829  mov     rax, [rax+10h]
0x18007782d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077832  test    edi, edi
0x180077834  js      loc_180077940
0x18007783a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180077841  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180077846  mov     word ptr [rbp+57h+propvar], r14w
0x18007784b  lea     r8, [rbp+57h+propvar]
0x18007784f  lea     rdx, aConflictresolu; "ConflictResolutionCLSID"
0x180077856  lea     rcx, [rbp+57h+var_68]
0x18007785a  call    ??$GetFailIfEmpty@PEBG@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEBAJPEBGPEAUtagPROPVARIANT@@@Z; CPropertyStoreHelperBase<INamedPropertyStore>::GetFailIfEmpty<ushort const *>(ushort const *,tagPROPVARIANT *)
0x18007785f  mov     edi, eax
0x180077861  test    eax, eax
0x180077863  js      short loc_18007788C
0x180077865  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007786c  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180077871  cmp     word ptr [rbp+57h+propvar], r14w
0x180077876  jnz     short loc_18007787C
0x180077878  mov     edi, ebx
0x18007787a  jmp     short loc_18007788C
0x18007787c  lea     rdx, [rbp+57h+pguid]; pguid
0x180077880  lea     rcx, [rbp+57h+propvar]; propvar
0x180077884  call    cs:__imp_PropVariantToGUID
0x18007788a  mov     edi, eax
0x18007788c  lea     rcx, [rbp+57h+propvar]; pvar
0x180077890  call    cs:__imp_PropVariantClear
0x180077896  test    edi, edi
0x180077898  js      loc_180077940
0x18007789e  mov     r8d, 10h; Size
0x1800778a4  lea     rdx, CLSID_CachedFileUpdaterMergeHandler; Buf2
0x1800778ab  lea     rcx, [rbp+57h+pguid]; Buf1
0x1800778af  call    memcmp_0
0x1800778b4  test    eax, eax
0x1800778b6  setz    bl
0x1800778b9  mov     qword ptr [rbp+57h+var_70], r14
0x1800778bd  lea     rcx, [rbp+57h+var_70]
0x1800778c1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800778c6  neg     bl
0x1800778c8  sbb     r9d, r9d
0x1800778cb  and     r9d, 0FFFFFFFDh
0x1800778cf  add     r9d, 4
0x1800778d3  lea     rax, [rbp+57h+var_70]
0x1800778d7  mov     [rsp+0B0h+var_80], rax
0x1800778dc  lea     rax, _GUID_d97b5aac_c792_433c_975d_35c4eadc7a9d
0x1800778e3  mov     [rsp+0B0h+var_88], rax
0x1800778e8  mov     dword ptr [rsp+0B0h+var_90], r14d
0x1800778ed  xor     r8d, r8d
0x1800778f0  lea     rdx, CATID_FilePlaceholderMergeHandler
0x1800778f7  lea     rcx, [rbp+57h+pguid]
0x1800778fb  call    cs:__imp_SHExtCoCreateInstanceCheckCategory
0x180077901  mov     ebx, eax
0x180077903  test    eax, eax
0x180077905  js      short loc_180077935
0x180077907  mov     rdi, qword ptr [rbp+57h+var_70]
0x18007790b  mov     rax, [rdi]
0x18007790e  mov     rbx, [rax+20h]
0x180077912  mov     edx, 2; dwFlags
0x180077917  mov     rcx, [rsi+50h]; pt
0x18007791b  call    cs:__imp_MonitorFromPoint
0x180077921  mov     r8, rax
0x180077924  mov     rdx, [rbp+57h+var_60]
0x180077928  mov     rcx, rdi
0x18007792b  mov     rax, rbx
0x18007792e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077933  mov     ebx, eax
0x180077935  lea     rcx, [rbp+57h+var_70]
0x180077939  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18007793e  jmp     short loc_180077942
0x180077940  mov     ebx, edi
0x180077942  lea     rcx, [rbp+57h+var_68]
0x180077946  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x18007794b  nop
0x18007794c  lea     rcx, [rbp+57h+var_60]
0x180077950  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180077955  mov     eax, ebx
0x180077957  mov     rcx, [rbp+57h+var_20]
0x18007795b  xor     rcx, rsp; StackCookie
0x18007795e  call    __security_check_cookie
0x180077963  lea     r11, [rsp+0B0h+var_10]
0x18007796b  mov     rbx, [r11+30h]
0x18007796f  mov     rsi, [r11+38h]
0x180077973  mov     rsp, r11
0x180077976  pop     r14
0x180077978  pop     rdi
0x180077979  pop     rbp
0x18007797a  retn
```
