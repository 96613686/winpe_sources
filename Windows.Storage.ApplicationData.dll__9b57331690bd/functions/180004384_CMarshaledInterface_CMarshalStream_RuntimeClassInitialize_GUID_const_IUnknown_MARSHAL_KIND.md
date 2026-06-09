# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180004384`
- end: `0x180004446`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `194`
- prototype: `HRESULT __fastcall(CMarshaledInterface::CMarshalStream *this, const _GUID *riid, IUnknown *punk, MARSHAL_KIND mk)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000444c`

## callees

- `0x180003820`
- `0x180004384`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004399`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180004433`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180004433`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800043cf`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800043cf`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        CMarshaledInterface::CMarshalStream *this,
        const _GUID *riid,
        IUnknown *punk,
        MARSHAL_KIND mk)
{
  DWORD CurrentThreadId; // eax
  IAgileReference *ptr; // rax
  unsigned int AgileReference; // ebx
  IAgileReference *v11; // rdx
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *v12; // rcx
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> v14; // [rsp+50h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  this->m_marshalingKind = mk;
  this->m_marshalThreadId = CurrentThreadId;
  if ( mk == MK_STRONG )
  {
    ptr = 0;
    AgileReference = 0;
    v14.ptr_ = 0;
    if ( punk )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
      AgileReference = RoGetAgileReference(0, riid, punk, &v14);
      ptr = (IAgileReference *)v14.ptr_;
    }
    v11 = this->m_agileRef.m_agileRef.ptr_;
    v12 = 0;
    v14.ptr_ = 0;
    this->m_agileRef.m_agileRef.ptr_ = ptr;
    if ( v11 )
    {
      v11->Release(v11);
      v12 = v14.ptr_;
    }
    if ( v12 )
    {
      v14.ptr_ = 0;
      v12->Release(v12);
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&this->m_stream);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(riid, punk, &this->m_stream.ptr_);
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180004384  push    rbx
0x180004386  push    rbp
0x180004387  push    rsi
0x180004388  push    rdi
0x180004389  sub     rsp, 28h
0x18000438d  mov     ebx, mk
0x180004390  mov     rsi, punk
0x180004393  mov     rbp, riid
0x180004396  mov     rdi, this
0x180004399  call    cs:__imp_GetCurrentThreadId
0x18000439f  mov     [rdi+18h], ebx
0x1800043a2  mov     [rdi+28h], eax
0x1800043a5  cmp     ebx, 2
0x1800043a8  jnz     short loc_180004420
0x1800043aa  xor     eax, eax
0x1800043ac  xor     ebx, ebx
0x1800043ae  mov     [rsp+48h+arg_0.ptr_], rax
0x1800043b3  test    rsi, rsi
0x1800043b6  jz      short loc_1800043DC
0x1800043b8  lea     this, [rsp+48h+arg_0]; this
0x1800043bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800043c2  lea     r9, [rsp+48h+arg_0]
0x1800043c7  mov     punk, rsi
0x1800043ca  mov     riid, rbp
0x1800043cd  xor     ecx, ecx
0x1800043cf  call    cs:__imp_RoGetAgileReference
0x1800043d5  mov     ebx, eax
0x1800043d7  mov     rax, [rsp+48h+arg_0.ptr_]
0x1800043dc  mov     riid, [rdi+20h]
0x1800043e0  xor     ecx, ecx
0x1800043e2  mov     [rsp+48h+arg_0.ptr_], this
0x1800043e7  mov     [rdi+20h], rax
0x1800043eb  test    riid, riid
0x1800043ee  jz      short loc_180004404
0x1800043f0  mov     rax, [riid]
0x1800043f3  mov     this, riid
0x1800043f6  mov     rax, [rax+10h]
0x1800043fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ff  mov     this, [rsp+48h+arg_0.ptr_]
0x180004404  test    this, this
0x180004407  jz      short loc_18000443B
0x180004409  mov     [rsp+48h+arg_0.ptr_], 0
0x180004412  mov     rax, [this]
0x180004415  mov     rax, [rax+10h]
0x180004419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441e  jmp     short loc_18000443B
0x180004420  lea     this, [rdi+10h]; this
0x180004424  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180004429  lea     punk, [rdi+10h]; ppStm
0x18000442d  mov     riid, rsi; pUnk
0x180004430  mov     this, rbp; riid
0x180004433  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180004439  mov     ebx, eax
0x18000443b  mov     eax, ebx
0x18000443d  add     rsp, 28h
0x180004441  pop     rdi
0x180004442  pop     rsi
0x180004443  pop     rbp
0x180004444  pop     rbx
0x180004445  retn
```
