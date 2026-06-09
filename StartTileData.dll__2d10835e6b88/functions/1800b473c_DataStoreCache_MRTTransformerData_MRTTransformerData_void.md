# DataStoreCache::MRTTransformerData::~MRTTransformerData(void)

- ea: `0x1800b473c`
- end: `0x1800b4843`
- name: `??1MRTTransformerData@DataStoreCache@@UEAA@XZ`
- size: `263`
- prototype: `void __fastcall(DataStoreCache::MRTTransformerData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b4700`

## callees

- `0x18000ce94`
- `0x18001ac50`
- `0x18007b054`
- `0x1800b473c`
- `0x1800f22a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b475c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b478c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b475c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b478c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b47ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4804`

## pseudocode

```c
void __fastcall DataStoreCache::MRTTransformerData::~MRTTransformerData(DataStoreCache::MRTTransformerData *this)
{
  void *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 24);
  if ( v2 )
    tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>::Release(v2);
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  WindowsDeleteString(*((HSTRING *)this + 22));
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 15);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,DataStoreCache::IMRTTransformerData,DataStoreCache::IMRTDumpData,DataStoreCache::IMRTDataItemCache,DataStoreCache::IValidateMRTData,DataStoreCache::IMRTTransformerDataGetRaw>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,DataStoreCache::IMRTTransformerData,DataStoreCache::IMRTDumpData,DataStoreCache::IMRTDataItemCache,DataStoreCache::IValidateMRTData,DataStoreCache::IMRTTransformerDataGetRaw>(this);
}

```

## disassembly

```asm
0x1800b473c  push    rbx
0x1800b473e  sub     rsp, 20h
0x1800b4742  mov     rbx, rcx
0x1800b4745  mov     rcx, [rcx+0C0h]; pv
0x1800b474c  test    rcx, rcx
0x1800b474f  jnz     loc_1800B4839
0x1800b4755  mov     rcx, [rbx+0B8h]; string
0x1800b475c  call    cs:__imp_WindowsDeleteString
0x1800b4762  mov     qword ptr [rbx+0B8h], 0
0x1800b476d  mov     rcx, [rbx+0B0h]; string
0x1800b4774  call    cs:__imp_WindowsDeleteString
0x1800b477a  mov     qword ptr [rbx+0B0h], 0
0x1800b4785  mov     rcx, [rbx+0A8h]; string
0x1800b478c  call    cs:__imp_WindowsDeleteString
0x1800b4792  mov     qword ptr [rbx+0A8h], 0
0x1800b479d  mov     rcx, [rbx+0A0h]; string
0x1800b47a4  call    cs:__imp_WindowsDeleteString
0x1800b47aa  mov     qword ptr [rbx+0A0h], 0
0x1800b47b5  mov     rcx, [rbx+98h]; string
0x1800b47bc  call    cs:__imp_WindowsDeleteString
0x1800b47c2  mov     qword ptr [rbx+98h], 0
0x1800b47cd  mov     rcx, [rbx+90h]; string
0x1800b47d4  call    cs:__imp_WindowsDeleteString
0x1800b47da  mov     qword ptr [rbx+90h], 0
0x1800b47e5  mov     rcx, [rbx+88h]; string
0x1800b47ec  call    cs:__imp_WindowsDeleteString
0x1800b47f2  mov     qword ptr [rbx+88h], 0
0x1800b47fd  mov     rcx, [rbx+80h]; string
0x1800b4804  call    cs:__imp_WindowsDeleteString
0x1800b480a  mov     qword ptr [rbx+80h], 0
0x1800b4815  mov     rcx, [rbx+78h]; this
0x1800b4819  test    rcx, rcx
0x1800b481c  jz      short loc_1800B4823
0x1800b481e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4823  lea     rcx, [rbx+68h]
0x1800b4827  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b482c  mov     rcx, rbx
0x1800b482f  add     rsp, 20h
0x1800b4833  pop     rbx
0x1800b4834  jmp     ??1?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIMRTTransformerData@DataStoreCache@@UIMRTDumpData@6@UIMRTDataItemCache@6@UIValidateMRTData@6@UIMRTTransformerDataGetRaw@6@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,DataStoreCache::IMRTTransformerData,DataStoreCache::IMRTDumpData,DataStoreCache::IMRTDataItemCache,DataStoreCache::IValidateMRTData,DataStoreCache::IMRTTransformerDataGetRaw>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,DataStoreCache::IMRTTransformerData,DataStoreCache::IMRTDumpData,DataStoreCache::IMRTDataItemCache,DataStoreCache::IValidateMRTData,DataStoreCache::IMRTTransformerDataGetRaw>(void)
0x1800b4839  call    ?Release@?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>::Release(void)
0x1800b483e  jmp     loc_1800B4755
```
