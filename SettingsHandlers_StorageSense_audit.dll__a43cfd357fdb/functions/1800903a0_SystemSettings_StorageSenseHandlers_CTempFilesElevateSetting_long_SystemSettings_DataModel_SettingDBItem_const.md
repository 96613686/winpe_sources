# SystemSettings::StorageSenseHandlers::CTempFilesElevateSetting<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(HWND__ *)

- ea: `0x1800903a0`
- end: `0x180090525`
- name: `?Invoke@?$CTempFilesElevateSetting@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000171c`
- `0x1800044f0`
- `0x18000c964`
- `0x180011280`
- `0x18001f468`
- `0x18001f53c`
- `0x18001fc0c`
- `0x18001fe08`
- `0x18008519c`
- `0x1800903a0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800904a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800904a9`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800904c8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800904c8`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CTempFilesElevateSetting<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(
        __int64 a1,
        __int64 a2)
{
  const struct _tlgProvider_t *v4; // rax
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int v12; // esi
  __int64 v14; // [rsp+50h] [rbp+20h] BYREF
  __int64 v15; // [rsp+58h] [rbp+28h] BYREF

  v4 = SettingsHandlersStorageSenseLogging::Provider();
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    v14 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v6,
      (unsigned int)&unk_180152F6E,
      v5,
      v6,
      (__int64)&v14);
  }
  v7 = *(_QWORD *)(a1 + 240);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 552));
  v14 = v7 + 552;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v7 + 600);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v7 + 608);
  *(_BYTE *)(v7 + 508) = 1;
  *(_QWORD *)(v7 + 512) = a2;
  SystemSettings::DataModel::CSettingBase::OnValueChanged(
    (SystemSettings::DataModel::CSettingBase *)v7,
    (const unsigned __int16 *)&stru_180112530);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
  v14 = *(_QWORD *)(a1 + 240);
  v8 = v14;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v14);
  v14 = v8;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v14);
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_2cf42c15a7bb8f47605d0996e76ebd74_ &>,_lambda_2cf42c15a7bb8f47605d0996e76ebd74_ &>(
                    &v15,
                    &v14);
  v10 = *v9;
  *v9 = 0;
  if ( v15 )
  {
    v15 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v12 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v10, 0);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v12;
}

```

## disassembly

```asm
0x1800903a0  mov     [rsp-18h+arg_10], rbx
0x1800903a5  mov     [rsp-18h+arg_18], rsi
0x1800903aa  push    rbp
0x1800903ab  push    rdi
0x1800903ac  push    r14
0x1800903ae  mov     rbp, rsp
0x1800903b1  sub     rsp, 30h
0x1800903b5  mov     r14, rdx
0x1800903b8  mov     rsi, rcx
0x1800903bb  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800903c0  mov     r9, rax
0x1800903c3  mov     r8d, [rax]
0x1800903c6  cmp     r8d, 5
0x1800903ca  jbe     short loc_180090402
0x1800903cc  mov     rdx, 400000000000h
0x1800903d6  mov     rcx, rax
0x1800903d9  call    _tlgKeywordOn
0x1800903de  test    al, al
0x1800903e0  jz      short loc_180090402
0x1800903e2  mov     [rbp+arg_0], 1000000h
0x1800903ea  lea     rax, [rbp+arg_0]
0x1800903ee  mov     [rsp+30h+var_10], rax
0x1800903f3  lea     rdx, unk_180152F6E
0x1800903fa  mov     rcx, r9
0x1800903fd  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180090402  mov     rdi, [rsi+0F0h]
0x180090409  lea     rbx, [rdi+228h]
0x180090410  mov     rcx, rbx; lpCriticalSection
0x180090413  call    cs:__imp_EnterCriticalSection
0x180090419  mov     [rbp+arg_0], rbx
0x18009041d  lea     rcx, [rdi+258h]
0x180090424  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180090429  lea     rcx, [rdi+260h]
0x180090430  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180090435  mov     byte ptr [rdi+1FCh], 1
0x18009043c  mov     [rdi+200h], r14
0x180090443  lea     rdx, stru_180112530; unsigned __int16 *
0x18009044a  mov     rcx, rdi; this
0x18009044d  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180090452  lea     rcx, [rbp+arg_0]; this
0x180090456  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18009045b  mov     rbx, [rsi+0F0h]
0x180090462  mov     [rbp+arg_0], rbx
0x180090466  lea     rcx, [rbp+arg_0]
0x18009046a  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009046f  mov     [rbp+arg_0], rbx
0x180090473  lea     rcx, [rbp+arg_0]
0x180090477  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009047c  lea     rdx, [rbp+arg_0]
0x180090480  lea     rcx, [rbp+arg_8]
0x180090484  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_2cf42c15a7bb8f47605d0996e76ebd74_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_2cf42c15a7bb8f47605d0996e76ebd74_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_2cf42c15a7bb8f47605d0996e76ebd74_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_2cf42c15a7bb8f47605d0996e76ebd74_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_2cf42c15a7bb8f47605d0996e76ebd74_ &>,_lambda_2cf42c15a7bb8f47605d0996e76ebd74_ &>(_lambda_2cf42c15a7bb8f47605d0996e76ebd74_ &)
0x180090489  mov     rdi, [rax]
0x18009048c  mov     qword ptr [rax], 0
0x180090493  mov     rcx, [rbp+arg_8]
0x180090497  test    rcx, rcx
0x18009049a  jz      short loc_1800904A9
0x18009049c  mov     [rbp+arg_8], 0
0x1800904a4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800904a9  call    cs:__imp_GetCurrentThreadId
0x1800904af  mov     [rsp+30h+var_8], 0
0x1800904b8  mov     [rsp+30h+var_10], rdi
0x1800904bd  xor     r9d, r9d
0x1800904c0  mov     r8d, eax
0x1800904c3  xor     edx, edx
0x1800904c5  lea     ecx, [rdx+3]
0x1800904c8  call    cs:__imp_SHTaskPoolQueueTask
0x1800904ce  mov     esi, eax
0x1800904d0  test    rdi, rdi
0x1800904d3  jz      short loc_1800904E5
0x1800904d5  mov     rdx, [rdi]
0x1800904d8  mov     rcx, rdi
0x1800904db  mov     rax, [rdx+10h]
0x1800904df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904e4  nop
0x1800904e5  mov     rcx, [rbp+arg_0]
0x1800904e9  test    rcx, rcx
0x1800904ec  jz      short loc_1800904FB
0x1800904ee  mov     rax, [rcx]
0x1800904f1  mov     rax, [rax+10h]
0x1800904f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904fa  nop
0x1800904fb  test    rbx, rbx
0x1800904fe  jz      short loc_180090510
0x180090500  mov     rax, [rbx]
0x180090503  mov     rcx, rbx
0x180090506  mov     rax, [rax+10h]
0x18009050a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009050f  nop
0x180090510  mov     eax, esi
0x180090512  mov     rbx, [rsp+30h+arg_10]
0x180090517  mov     rsi, [rsp+30h+arg_18]
0x18009051c  add     rsp, 30h
0x180090520  pop     r14
0x180090522  pop     rdi
0x180090523  pop     rbp
0x180090524  retn
```
