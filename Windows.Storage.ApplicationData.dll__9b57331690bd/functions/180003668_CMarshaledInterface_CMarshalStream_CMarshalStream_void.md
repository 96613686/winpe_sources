# CMarshaledInterface::CMarshalStream::~CMarshalStream(void)

- ea: `0x180003668`
- end: `0x180003703`
- name: `??1CMarshalStream@CMarshaledInterface@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CMarshaledInterface::CMarshalStream *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003630`

## callees

- `0x180003668`
- `0x180003820`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003689`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003689`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180003697`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180003697`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800036d0`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1800036d0`

## pseudocode

```c
void __fastcall CMarshaledInterface::CMarshalStream::~CMarshalStream(CMarshaledInterface::CMarshalStream *this)
{
  Microsoft::WRL::ComPtr<IStream> *p_m_stream; // rbx
  bool v3; // zf
  IStream *ptr; // rcx
  Microsoft::WRL::ComPtr<IUnknown> spUnknown; // [rsp+30h] [rbp+8h] BYREF

  p_m_stream = &this->m_stream;
  v3 = this->m_stream.ptr_ == 0;
  this->__vftable = (CMarshaledInterface::CMarshalStream_vtbl *)CMarshaledInterface::CMarshalStream::`vftable';
  if ( !v3 )
  {
    if ( this->m_marshalThreadId == GetCurrentThreadId() )
    {
      CoReleaseMarshalData(p_m_stream->ptr_);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)p_m_stream);
    }
    else
    {
      spUnknown.ptr_ = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spUnknown);
      ptr = p_m_stream->ptr_;
      p_m_stream->ptr_ = 0;
      CoGetInterfaceAndReleaseStream(ptr, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&spUnknown.ptr_);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spUnknown);
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&this->m_agileRef);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)p_m_stream);
  this->refcount_ = -1073741823;
}

```

## disassembly

```asm
0x180003668  mov     [rsp+arg_8], rbx
0x18000366d  push    rdi
0x18000366e  sub     rsp, 20h
0x180003672  lea     rbx, [this+10h]
0x180003676  mov     rdi, this
0x180003679  cmp     qword ptr [rbx], 0
0x18000367d  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x180003684  mov     [this], rax
0x180003687  jz      short loc_1800036E0
0x180003689  call    cs:__imp_GetCurrentThreadId
0x18000368f  cmp     [rdi+28h], eax
0x180003692  jnz     short loc_1800036A7
0x180003694  mov     this, [rbx]; pStm
0x180003697  call    cs:__imp_CoReleaseMarshalData
0x18000369d  mov     this, rbx; this
0x1800036a0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800036a5  jmp     short loc_1800036E0
0x1800036a7  lea     this, [rsp+28h+spUnknown]; this
0x1800036ac  mov     [rsp+28h+spUnknown.ptr_], 0
0x1800036b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800036ba  mov     this, [rbx]; pStm
0x1800036bd  lea     r8, [rsp+28h+spUnknown]; ppv
0x1800036c2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1800036c9  mov     qword ptr [rbx], 0
0x1800036d0  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1800036d6  lea     this, [rsp+28h+spUnknown]; this
0x1800036db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800036e0  lea     this, [rdi+20h]; this
0x1800036e4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800036e9  mov     this, rbx; this
0x1800036ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800036f1  mov     rbx, [rsp+28h+arg_8]
0x1800036f6  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800036fd  add     rsp, 20h
0x180003701  pop     rdi
0x180003702  retn
```
