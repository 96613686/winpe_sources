# SystemSettings::StorageSenseHandlers::CTempFilesElevateSetting<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(HWND__ *)

- ea: `0x180090210`
- end: `0x180090395`
- name: `?Invoke@?$CTempFilesElevateSetting@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@MEAAJPEAUHWND__@@@Z`
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
- `0x180085104`
- `0x180090210`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090283`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180090283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090319`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180090338`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180090338`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CTempFilesElevateSetting<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::Invoke(
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
      (unsigned int)&unk_180152F0F,
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_24e171de4c086d399d296c0ff14eefac_ &>,_lambda_24e171de4c086d399d296c0ff14eefac_ &>(
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
0x180090210  mov     [rsp-18h+arg_10], rbx
0x180090215  mov     [rsp-18h+arg_18], rsi
0x18009021a  push    rbp
0x18009021b  push    rdi
0x18009021c  push    r14
0x18009021e  mov     rbp, rsp
0x180090221  sub     rsp, 30h
0x180090225  mov     r14, rdx
0x180090228  mov     rsi, rcx
0x18009022b  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x180090230  mov     r9, rax
0x180090233  mov     r8d, [rax]
0x180090236  cmp     r8d, 5
0x18009023a  jbe     short loc_180090272
0x18009023c  mov     rdx, 400000000000h
0x180090246  mov     rcx, rax
0x180090249  call    _tlgKeywordOn
0x18009024e  test    al, al
0x180090250  jz      short loc_180090272
0x180090252  mov     [rbp+arg_0], 1000000h
0x18009025a  lea     rax, [rbp+arg_0]
0x18009025e  mov     [rsp+30h+var_10], rax
0x180090263  lea     rdx, unk_180152F0F
0x18009026a  mov     rcx, r9
0x18009026d  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180090272  mov     rdi, [rsi+0F0h]
0x180090279  lea     rbx, [rdi+228h]
0x180090280  mov     rcx, rbx; lpCriticalSection
0x180090283  call    cs:__imp_EnterCriticalSection
0x180090289  mov     [rbp+arg_0], rbx
0x18009028d  lea     rcx, [rdi+258h]
0x180090294  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180090299  lea     rcx, [rdi+260h]
0x1800902a0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800902a5  mov     byte ptr [rdi+1FCh], 1
0x1800902ac  mov     [rdi+200h], r14
0x1800902b3  lea     rdx, stru_180112530; unsigned __int16 *
0x1800902ba  mov     rcx, rdi; this
0x1800902bd  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800902c2  lea     rcx, [rbp+arg_0]; this
0x1800902c6  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800902cb  mov     rbx, [rsi+0F0h]
0x1800902d2  mov     [rbp+arg_0], rbx
0x1800902d6  lea     rcx, [rbp+arg_0]
0x1800902da  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800902df  mov     [rbp+arg_0], rbx
0x1800902e3  lea     rcx, [rbp+arg_0]
0x1800902e7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800902ec  lea     rdx, [rbp+arg_0]
0x1800902f0  lea     rcx, [rbp+arg_8]
0x1800902f4  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_24e171de4c086d399d296c0ff14eefac_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_24e171de4c086d399d296c0ff14eefac_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_24e171de4c086d399d296c0ff14eefac_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_24e171de4c086d399d296c0ff14eefac_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_24e171de4c086d399d296c0ff14eefac_ &>,_lambda_24e171de4c086d399d296c0ff14eefac_ &>(_lambda_24e171de4c086d399d296c0ff14eefac_ &)
0x1800902f9  mov     rdi, [rax]
0x1800902fc  mov     qword ptr [rax], 0
0x180090303  mov     rcx, [rbp+arg_8]
0x180090307  test    rcx, rcx
0x18009030a  jz      short loc_180090319
0x18009030c  mov     [rbp+arg_8], 0
0x180090314  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180090319  call    cs:__imp_GetCurrentThreadId
0x18009031f  mov     [rsp+30h+var_8], 0
0x180090328  mov     [rsp+30h+var_10], rdi
0x18009032d  xor     r9d, r9d
0x180090330  mov     r8d, eax
0x180090333  xor     edx, edx
0x180090335  lea     ecx, [rdx+3]
0x180090338  call    cs:__imp_SHTaskPoolQueueTask
0x18009033e  mov     esi, eax
0x180090340  test    rdi, rdi
0x180090343  jz      short loc_180090355
0x180090345  mov     rdx, [rdi]
0x180090348  mov     rcx, rdi
0x18009034b  mov     rax, [rdx+10h]
0x18009034f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090354  nop
0x180090355  mov     rcx, [rbp+arg_0]
0x180090359  test    rcx, rcx
0x18009035c  jz      short loc_18009036B
0x18009035e  mov     rax, [rcx]
0x180090361  mov     rax, [rax+10h]
0x180090365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009036a  nop
0x18009036b  test    rbx, rbx
0x18009036e  jz      short loc_180090380
0x180090370  mov     rax, [rbx]
0x180090373  mov     rcx, rbx
0x180090376  mov     rax, [rax+10h]
0x18009037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009037f  nop
0x180090380  mov     eax, esi
0x180090382  mov     rbx, [rsp+30h+arg_10]
0x180090387  mov     rsi, [rsp+30h+arg_18]
0x18009038c  add     rsp, 30h
0x180090390  pop     r14
0x180090392  pop     rdi
0x180090393  pop     rbp
0x180090394  retn
```
