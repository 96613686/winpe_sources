# CFilterWithBatchedChunk::~CFilterWithBatchedChunk(void)

- ea: `0x14003f1bc`
- end: `0x14003f23b`
- name: `??1CFilterWithBatchedChunk@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(CFilterWithBatchedChunk *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003f4f0`

## callees

- `0x14003376c`
- `0x14003f1bc`
- `0x14003f8a4`
- `0x140041500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f204`

## pseudocode

```c
void __fastcall CFilterWithBatchedChunk::~CFilterWithBatchedChunk(CFilterWithBatchedChunk *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CFilterWithBatchedChunk::`vftable';
  *((_QWORD *)this + 1) = &CFilterWithBatchedChunk::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 2) = &CFilterWithBatchedChunk::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IInitializeWithStream>'};
  CFilterWithBatchedChunk::Cleanup(this);
  std::wstring::_Tidy_deallocate((char *)this + 96);
  v2 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 56);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 48);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 40);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 32);
  *((_DWORD *)this + 7) = -1073741823;
}

```

## disassembly

```asm
0x14003f1bc  push    rbx
0x14003f1be  sub     rsp, 20h
0x14003f1c2  lea     rax, ??_7CFilterWithBatchedChunk@@6B@; const CFilterWithBatchedChunk::`vftable'
0x14003f1c9  mov     rbx, rcx
0x14003f1cc  mov     [rcx], rax
0x14003f1cf  lea     rax, ??_7CFilterWithBatchedChunk@@6BIPersistStream@@@; const CFilterWithBatchedChunk::`vftable'{for `IPersistStream'}
0x14003f1d6  mov     [rcx+8], rax
0x14003f1da  lea     rax, ??_7CFilterWithBatchedChunk@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIInitializeWithStream@@@Details@WRL@Microsoft@@@; const CFilterWithBatchedChunk::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IInitializeWithStream>'}
0x14003f1e1  mov     [rcx+10h], rax
0x14003f1e5  call    ?Cleanup@CFilterWithBatchedChunk@@AEAAXXZ; CFilterWithBatchedChunk::Cleanup(void)
0x14003f1ea  lea     rcx, [rbx+60h]
0x14003f1ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003f1f3  mov     rcx, [rbx+58h]; pv
0x14003f1f7  mov     qword ptr [rbx+58h], 0
0x14003f1ff  test    rcx, rcx
0x14003f202  jz      short loc_14003F20A
0x14003f204  call    cs:__imp_CoTaskMemFree
0x14003f20a  lea     rcx, [rbx+38h]
0x14003f20e  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f213  lea     rcx, [rbx+30h]
0x14003f217  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f21c  lea     rcx, [rbx+28h]
0x14003f220  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f225  lea     rcx, [rbx+20h]
0x14003f229  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f22e  mov     dword ptr [rbx+1Ch], 0C0000001h
0x14003f235  add     rsp, 20h
0x14003f239  pop     rbx
0x14003f23a  retn
```
