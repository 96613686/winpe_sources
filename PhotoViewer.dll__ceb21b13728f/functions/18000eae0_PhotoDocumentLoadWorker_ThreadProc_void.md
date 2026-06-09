# PhotoDocumentLoadWorker::ThreadProc(void)

- ea: `0x18000eae0`
- end: `0x18000ec4a`
- name: `?ThreadProc@PhotoDocumentLoadWorker@@EEAAXXZ`
- size: `362`
- prototype: `void __fastcall(PhotoDocumentLoadWorker *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000e164`
- `0x18000eae0`
- `0x18000ec50`
- `0x180031f58`
- `0x180032a78`
- `0x180037b70`
- `0x180061c8c`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000eb2b`
- `ole32!CoCreateInstance` at `0x18000eb2b`
- `ole32!CoUninitialize` at `0x18000ec3b`
- `ole32!CoUninitialize` at `0x18000ec3b`
- `ole32!CoInitialize` at `0x18000eaf9`
- `ole32!CoInitialize` at `0x18000eaf9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000eb37`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000eb7b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000eb37`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000eb7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PhotoDocumentLoadWorker::ThreadProc(PhotoDocumentLoadWorker *this)
{
  PhotoDocumentLoadWorker *v1; // rbx
  _QWORD *v2; // rsi
  HRESULT Instance; // eax
  int v4; // edx
  PhotoDocumentLoadWorker *v5; // rdi
  unsigned int v6; // eax
  int v7; // eax
  int v8; // edx
  struct IWICBitmapDecoder *v9; // rdx
  __int64 v10; // rcx
  _BYTE v11[40]; // [rsp+30h] [rbp-28h] BYREF
  bool v15; // [rsp+68h] [rbp+10h]
  unsigned int v16; // [rsp+70h] [rbp+18h] BYREF
  _QWORD *v17; // [rsp+78h] [rbp+20h]

  v1 = this;
  v16 = 0;
  v15 = CoInitialize(0) >= 0;
  v2 = (_QWORD *)((char *)v1 + 312);
  v17 = (_QWORD *)((char *)v1 + 312);
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)v1 + 39);
  try
  {
    if ( Instance < 0 )
      Base::Throw((Base *)(unsigned int)Instance, v4);
    v5 = (PhotoDocumentLoadWorker *)((char *)v1 - 16);
    PhotoDocumentLoadWorker::EnsureDecoder((PhotoDocumentLoadWorker *)((char *)v1 - 16));
    if ( (*((_BYTE *)v1 + 385) & 2) != 0 )
    {
      v6 = 1;
      v16 = 1;
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v1 + 40) + 96LL))(
             *((_QWORD *)v1 + 40),
             &v16);
      if ( v7 < 0 )
        Base::Throw((Base *)(unsigned int)v7, v8);
      v6 = v16;
    }
    ATL::CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>::SetCount(
      (char *)v1 + 232,
      v6);
    if ( !*((_BYTE *)v1 + 384) )
      PhotoDocumentLoadWorker::LoadPreview((CodecUtil **)v1 - 2, v9);
    if ( !*((_BYTE *)v1 + 384) )
      PhotoDocumentLoadWorker::LoadFullRes((PhotoDocumentLoadWorker *)((char *)v1 - 16));
    PhotoDocumentLoadWorker::UpdateEditableStatus((PhotoDocumentLoadWorker *)((char *)v1 - 16));
  }
  catch ( Base::Exception v11 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16);
    Base::Exception::~Exception((Base::Exception *)v11);
    v1 = this;
    v5 = (PhotoDocumentLoadWorker *)((char *)this - 16);
    v2 = v17;
  }
  if ( !*((_BYTE *)v5 + 400) && v16 > 1 )
  {
    try
    {
      PhotoDocumentLoadWorker::LazyLoadFullRes(v5);
    }
    catch ( ... )
    {
      v1 = this;
      v2 = v17;
    }
  }
  v10 = *((_QWORD *)v1 + 40);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)v1 + 40) = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  if ( v15 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18000eae0  mov     [rsp+arg_0], rcx
0x18000eae5  push    rbx
0x18000eae6  push    rsi
0x18000eae7  push    rdi
0x18000eae8  sub     rsp, 40h
0x18000eaec  mov     rbx, rcx
0x18000eaef  mov     [rsp+58h+arg_10], 0
0x18000eaf7  xor     ecx, ecx; pvReserved
0x18000eaf9  call    cs:__imp_CoInitialize
0x18000eaff  test    eax, eax
0x18000eb01  setns   [rsp+58h+arg_8]
0x18000eb06  lea     rsi, [rbx+138h]
0x18000eb0d  mov     [rsp+58h+arg_18], rsi
0x18000eb12  mov     [rsp+58h+ppv], rsi; ppv
0x18000eb17  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000eb1e  xor     edx, edx; pUnkOuter
0x18000eb20  lea     r8d, [rdx+1]; dwClsContext
0x18000eb24  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000eb2b  call    cs:__imp_CoCreateInstance
0x18000eb31  test    eax, eax
0x18000eb33  jns     short loc_18000EB3D
0x18000eb35  mov     ecx, eax
0x18000eb37  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000eb3d  lea     rdi, [rbx-10h]
0x18000eb41  mov     rcx, rdi; this
0x18000eb44  call    ?EnsureDecoder@PhotoDocumentLoadWorker@@AEAAXXZ; PhotoDocumentLoadWorker::EnsureDecoder(void)
0x18000eb49  test    byte ptr [rbx+181h], 2
0x18000eb50  jz      short loc_18000EB5D
0x18000eb52  mov     eax, 1
0x18000eb57  mov     [rsp+58h+arg_10], eax
0x18000eb5b  jmp     short loc_18000EB85
0x18000eb5d  mov     rcx, [rbx+140h]
0x18000eb64  mov     rax, [rcx]
0x18000eb67  lea     rdx, [rsp+58h+arg_10]
0x18000eb6c  mov     rax, [rax+60h]
0x18000eb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb75  test    eax, eax
0x18000eb77  jns     short loc_18000EB81
0x18000eb79  mov     ecx, eax
0x18000eb7b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18000eb81  mov     eax, [rsp+58h+arg_10]
0x18000eb85  mov     edx, eax
0x18000eb87  lea     rcx, [rbx+0E8h]
0x18000eb8e  call    ?SetCount@?$CAtlArray@VLayerDefinition@PhotoDocumentLoadWorker@@V?$CElementTraits@VLayerDefinition@PhotoDocumentLoadWorker@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>::SetCount(unsigned __int64,int)
0x18000eb93  mov     al, [rbx+180h]
0x18000eb99  test    al, al
0x18000eb9b  jnz     short loc_18000EBA5
0x18000eb9d  mov     rcx, rdi; this
0x18000eba0  call    ?LoadPreview@PhotoDocumentLoadWorker@@AEAAXXZ; PhotoDocumentLoadWorker::LoadPreview(void)
0x18000eba5  mov     al, [rbx+180h]
0x18000ebab  test    al, al
0x18000ebad  jnz     short loc_18000EBB7
0x18000ebaf  mov     rcx, rdi; this
0x18000ebb2  call    ?LoadFullRes@PhotoDocumentLoadWorker@@AEAAXXZ; PhotoDocumentLoadWorker::LoadFullRes(void)
0x18000ebb7  mov     rcx, rdi; this
0x18000ebba  call    ?UpdateEditableStatus@PhotoDocumentLoadWorker@@AEAAXXZ; PhotoDocumentLoadWorker::UpdateEditableStatus(void)
0x18000ebbf  nop
0x18000ebc0  jmp     short loc_18000EBD0
0x18000ebc2  mov     rbx, [rsp+58h+arg_0]
0x18000ebc7  lea     rdi, [rbx-10h]
0x18000ebcb  mov     rsi, [rsp+58h+arg_18]
0x18000ebd0  mov     al, [rdi+190h]
0x18000ebd6  test    al, al
0x18000ebd8  jnz     short loc_18000EBF6
0x18000ebda  cmp     [rsp+58h+arg_10], 1
0x18000ebdf  jbe     short loc_18000EBF6
0x18000ebe1  mov     rcx, rdi; this
0x18000ebe4  call    ?LazyLoadFullRes@PhotoDocumentLoadWorker@@AEAAXXZ; PhotoDocumentLoadWorker::LazyLoadFullRes(void)
0x18000ebe9  nop
0x18000ebea  jmp     short loc_18000EBF6
0x18000ebec  mov     rbx, [rsp+58h+arg_0]
0x18000ebf1  mov     rsi, [rsp+58h+arg_18]
0x18000ebf6  mov     rcx, [rbx+140h]
0x18000ebfd  test    rcx, rcx
0x18000ec00  jz      short loc_18000EC19
0x18000ec02  mov     rax, [rcx]
0x18000ec05  mov     rax, [rax+10h]
0x18000ec09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec0e  mov     qword ptr [rbx+140h], 0
0x18000ec19  mov     rcx, [rsi]
0x18000ec1c  test    rcx, rcx
0x18000ec1f  jz      short loc_18000EC34
0x18000ec21  mov     rax, [rcx]
0x18000ec24  mov     rax, [rax+10h]
0x18000ec28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec2d  mov     qword ptr [rsi], 0
0x18000ec34  cmp     [rsp+58h+arg_8], 0
0x18000ec39  jz      short loc_18000EC42
0x18000ec3b  call    cs:__imp_CoUninitialize
0x18000ec41  nop
0x18000ec42  add     rsp, 40h
0x18000ec46  pop     rdi
0x18000ec47  pop     rsi
0x18000ec48  pop     rbx
0x18000ec49  retn
```
