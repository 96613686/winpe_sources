# Dred::CBreadcrumbBuffer::CBreadcrumbBuffer(CDevice *,unsigned __int64,Dred::CBreadcrumbBufferList &)

- ea: `0x1800aafa8`
- end: `0x1800ab2ad`
- name: `??0CBreadcrumbBuffer@Dred@@QEAA@PEAVCDevice@@_KAEAVCBreadcrumbBufferList@1@@Z`
- size: `773`
- prototype: `_QWORD(Dred::CBreadcrumbBuffer *__hidden this, struct CDevice *, unsigned __int64, struct Dred::CBreadcrumbBufferList *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000916c`

## callees

- `0x180003c84`
- `0x180004a20`
- `0x18000b010`
- `0x18000d560`
- `0x18000d770`
- `0x18000e6ec`
- `0x180017d60`
- `0x1800aafa8`
- `0x1800ab2b4`
- `0x1800ab3e8`
- `0x1800bb480`
- `0x1800bc094`
- `0x180224e94`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ab21d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ab21d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800ab049`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800ab049`

## string_xrefs

- `0x1800ab190`: `D3D12CoreAutoBreadcrumbsBuffer`
- `0x1800ab0fc`: `D3D12CoreAutoBreadcrumbsHeap`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
Dred::CBreadcrumbBuffer *__fastcall Dred::CBreadcrumbBuffer::CBreadcrumbBuffer(
        Dred::CBreadcrumbBuffer *this,
        struct CDevice *a2,
        SIZE_T a3,
        struct Dred::CBreadcrumbBufferList *a4)
{
  LPVOID v8; // r14
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  _QWORD *v17; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v18; // [rsp+58h] [rbp-71h] BYREF
  __int64 v19; // [rsp+60h] [rbp-69h] BYREF
  LPVOID v20; // [rsp+68h] [rbp-61h] BYREF
  __int64 v21; // [rsp+70h] [rbp-59h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v23[3]; // [rsp+98h] [rbp-31h] BYREF
  int v24; // [rsp+B0h] [rbp-19h]
  __int64 v25; // [rsp+B4h] [rbp-15h]
  __int64 v26; // [rsp+BCh] [rbp-Dh]
  int v27; // [rsp+C4h] [rbp-5h]
  __int64 v28; // [rsp+C8h] [rbp-1h]

  pExceptionObject[3] = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 26) = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>((char *)this + 216);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>((char *)this + 240);
  v8 = VirtualAlloc(0, a3, 0x3000u, 4u);
  v20 = v8;
  if ( !v8 )
  {
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &hlsl::RDAT::CheckedReader::exception::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v19 = 0;
  (**(void (__fastcall ***)(struct CDevice *, GUID *, __int64 *))a2)(
    a2,
    &GUID_433be922_0f1b_4078_850c_16630f94406f,
    &v19);
  v21 = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
  v9 = *((_QWORD *)a2 + 96);
  v18 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, LPVOID, GUID *, _QWORD **))(*(_QWORD *)v9 + 384LL))(
          v9,
          v8,
          &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
          &v18);
  ThrowFailure(v10);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *))(*v18 + 48LL))(v18, L"D3D12CoreAutoBreadcrumbsHeap");
  v17 = 0;
  v23[0] = 1;
  v26 = 1;
  v28 = 16;
  v23[1] = 0x10000;
  v25 = 65537;
  v23[2] = a3;
  v24 = 1;
  v27 = 1;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD *, _DWORD, _QWORD, GUID *, _QWORD **))(*(_QWORD *)v9 + 232LL))(
          v9,
          v18[20],
          0,
          v23,
          0,
          0,
          &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
          &v17);
  ThrowFailure(v11);
  (*(void (__fastcall **)(_QWORD *, const wchar_t *))(*v17 + 48LL))(v17, L"D3D12CoreAutoBreadcrumbsBuffer");
  ThrowFailure(v17[46] == 0 ? 0x80004001 : 0);
  CUsePtr<CFence>::operator=((char *)this + 16, v17);
  v12 = v18;
  if ( *((_QWORD **)this + 1) != v18 )
  {
    if ( v18 )
      CLockOwnerChild<CDevice,0>::UCAddUse(v18 + 18);
    v13 = *((_QWORD *)this + 1);
    if ( v13 )
      CLockOwnerChild<CDevice,0>::UCReleaseUse(v13 + 144);
    *((_QWORD *)this + 1) = v12;
  }
  *((_QWORD *)this + 3) = a3;
  v20 = 0;
  v14 = *(void **)this;
  *(_QWORD *)this = v8;
  if ( v14 )
    VirtualFree(v14, 0, 0x8000u);
  memset_0((char *)this + 112, 0, 0x60u);
  v15 = *(_QWORD *)this;
  *((_QWORD *)this + 22) = *(_QWORD *)this + 4096LL;
  *((_QWORD *)this + 21) = v15;
  *((_QWORD *)this + 4) = *(_QWORD *)a4;
  *(_QWORD *)a4 = this;
  ++*((_QWORD *)a4 + 1);
  ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v17);
  ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v18);
  ScopedD3D12InternalDeviceChildCreation::~ScopedD3D12InternalDeviceChildCreation((ScopedD3D12InternalDeviceChildCreation *)&v21);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v19);
  std::unique_ptr<void,Dred::VirtualFreeDeleter>::~unique_ptr<void,Dred::VirtualFreeDeleter>(&v20);
  return this;
}

```

## disassembly

```asm
0x1800aafa8  push    rbp
0x1800aafaa  push    rbx
0x1800aafab  push    rsi
0x1800aafac  push    rdi
0x1800aafad  push    r12
0x1800aafaf  push    r13
0x1800aafb1  push    r14
0x1800aafb3  push    r15
0x1800aafb5  lea     rbp, [rsp-1Fh]
0x1800aafba  sub     rsp, 0E8h
0x1800aafc1  mov     rax, cs:__security_cookie
0x1800aafc8  xor     rax, rsp
0x1800aafcb  mov     [rbp+57h+var_50], rax
0x1800aafcf  mov     rsi, r9
0x1800aafd2  mov     r15, r8
0x1800aafd5  mov     rbx, rdx
0x1800aafd8  mov     rdi, rcx
0x1800aafdb  mov     [rbp+57h+var_90], rcx
0x1800aafdf  xor     r13d, r13d
0x1800aafe2  mov     [rcx], r13
0x1800aafe5  mov     [rcx+8], r13
0x1800aafe9  mov     [rcx+10h], r13
0x1800aafed  mov     [rcx+18h], r13
0x1800aaff1  mov     [rcx+20h], r13
0x1800aaff5  mov     [rcx+28h], r13
0x1800aaff9  mov     [rcx+30h], r13
0x1800aaffd  mov     [rcx+38h], r13
0x1800ab001  mov     [rcx+40h], r13
0x1800ab005  mov     [rcx+48h], r13
0x1800ab009  mov     [rcx+50h], r13
0x1800ab00d  mov     [rcx+58h], r13
0x1800ab011  mov     [rcx+60h], r13
0x1800ab015  mov     [rcx+68h], r13
0x1800ab019  mov     [rcx+0D0h], r13
0x1800ab020  add     rcx, 0D8h; void *
0x1800ab027  call    ??$?0AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(std::allocator<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>> const &)
0x1800ab02c  nop
0x1800ab02d  lea     rcx, [rdi+0F0h]; void *
0x1800ab034  call    ??$?0AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(std::allocator<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>> const &)
0x1800ab039  nop
0x1800ab03a  lea     r9d, [r13+4]; flProtect
0x1800ab03e  mov     r8d, 3000h; flAllocationType
0x1800ab044  mov     rdx, r15; dwSize
0x1800ab047  xor     ecx, ecx; lpAddress
0x1800ab049  call    cs:__imp_VirtualAlloc
0x1800ab04f  mov     r14, rax
0x1800ab052  mov     [rbp+57h+var_B8], rax
0x1800ab056  test    rax, rax
0x1800ab059  jnz     short loc_1800AB089
0x1800ab05b  xorps   xmm0, xmm0
0x1800ab05e  movups  [rbp+57h+var_A0], xmm0
0x1800ab062  lea     rax, aBadAllocation; "bad allocation"
0x1800ab069  mov     qword ptr [rbp+57h+var_A0], rax
0x1800ab06d  lea     rax, ??_7exception@CheckedReader@RDAT@hlsl@@6B@; const hlsl::RDAT::CheckedReader::exception::`vftable'
0x1800ab074  mov     [rbp+57h+pExceptionObject], rax
0x1800ab078  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800ab07f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800ab083  call    _CxxThrowException_0
0x1800ab089  mov     [rbp+57h+var_C0], r13
0x1800ab08d  mov     rax, [rbx]
0x1800ab090  lea     r8, [rbp+57h+var_C0]
0x1800ab094  lea     rdx, _GUID_433be922_0f1b_4078_850c_16630f94406f
0x1800ab09b  mov     rcx, rbx
0x1800ab09e  mov     rax, [rax]
0x1800ab0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0a6  mov     rcx, [rbp+57h+var_C0]
0x1800ab0aa  mov     [rbp+57h+var_B0], rcx
0x1800ab0ae  test    rcx, rcx
0x1800ab0b1  jz      short loc_1800AB0C0
0x1800ab0b3  mov     rax, [rcx]
0x1800ab0b6  mov     rax, [rax+48h]
0x1800ab0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0bf  nop
0x1800ab0c0  mov     rbx, [rbx+300h]
0x1800ab0c7  mov     [rbp+57h+var_C8], r13
0x1800ab0cb  mov     rax, [rbx]
0x1800ab0ce  lea     r9, [rbp+57h+var_C8]
0x1800ab0d2  lea     r13, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x1800ab0d9  mov     r8, r13
0x1800ab0dc  mov     rdx, r14
0x1800ab0df  mov     rcx, rbx
0x1800ab0e2  mov     rax, [rax+180h]
0x1800ab0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0ee  mov     ecx, eax; int
0x1800ab0f0  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800ab0f5  mov     rcx, [rbp+57h+var_C8]
0x1800ab0f9  mov     rax, [rcx]
0x1800ab0fc  lea     rdx, aD3d12coreautob_0; "D3D12CoreAutoBreadcrumbsHeap"
0x1800ab103  mov     rax, [rax+30h]
0x1800ab107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab10c  xor     edx, edx
0x1800ab10e  mov     [rbp+57h+var_D0], rdx
0x1800ab112  mov     [rbp+57h+var_88], 1
0x1800ab11a  mov     [rbp+57h+var_64], 1
0x1800ab122  mov     [rbp+57h+var_58], 10h
0x1800ab12a  lea     eax, [rdx+1]
0x1800ab12d  mov     [rbp+57h+var_80], 10000h
0x1800ab135  mov     [rbp+57h+var_6C], 10001h
0x1800ab13d  mov     [rbp+57h+var_78], r15
0x1800ab141  mov     [rbp+57h+var_70], eax
0x1800ab144  mov     [rbp+57h+var_5C], eax
0x1800ab147  mov     rax, [rbx]
0x1800ab14a  lea     rcx, [rbp+57h+var_D0]
0x1800ab14e  mov     [rsp+120h+var_E8], rcx
0x1800ab153  mov     [rsp+120h+var_F0], r13
0x1800ab158  mov     [rsp+120h+var_F8], rdx
0x1800ab15d  mov     [rsp+120h+var_100], edx
0x1800ab161  lea     r9, [rbp+57h+var_88]
0x1800ab165  xor     r8d, r8d
0x1800ab168  mov     rdx, [rbp+57h+var_C8]
0x1800ab16c  mov     rdx, [rdx+0A0h]
0x1800ab173  mov     rcx, rbx
0x1800ab176  mov     rax, [rax+0E8h]
0x1800ab17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab182  mov     ecx, eax; int
0x1800ab184  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800ab189  mov     rcx, [rbp+57h+var_D0]
0x1800ab18d  mov     rax, [rcx]
0x1800ab190  lea     rdx, aD3d12coreautob; "D3D12CoreAutoBreadcrumbsBuffer"
0x1800ab197  mov     rax, [rax+30h]
0x1800ab19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab1a0  mov     rax, [rbp+57h+var_D0]
0x1800ab1a4  mov     rdx, [rax+170h]
0x1800ab1ab  neg     rdx
0x1800ab1ae  sbb     ecx, ecx
0x1800ab1b0  not     ecx
0x1800ab1b2  and     ecx, 80004001h; int
0x1800ab1b8  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800ab1bd  mov     rdx, [rbp+57h+var_D0]
0x1800ab1c1  lea     rcx, [rdi+10h]
0x1800ab1c5  call    ??4?$CUsePtr@VCFence@@@@QEAAAEAV0@PEAVCFence@@@Z; CUsePtr<CFence>::operator=(CFence *)
0x1800ab1ca  mov     rbx, [rbp+57h+var_C8]
0x1800ab1ce  cmp     [rdi+8], rbx
0x1800ab1d2  jz      short loc_1800AB1FE
0x1800ab1d4  test    rbx, rbx
0x1800ab1d7  jz      short loc_1800AB1E5
0x1800ab1d9  lea     rcx, [rbx+90h]
0x1800ab1e0  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x1800ab1e5  mov     rcx, [rdi+8]
0x1800ab1e9  test    rcx, rcx
0x1800ab1ec  jz      short loc_1800AB1FA
0x1800ab1ee  add     rcx, 90h
0x1800ab1f5  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x1800ab1fa  mov     [rdi+8], rbx
0x1800ab1fe  mov     [rdi+18h], r15
0x1800ab202  mov     [rbp+57h+var_B8], 0
0x1800ab20a  mov     rcx, [rdi]; lpAddress
0x1800ab20d  mov     [rdi], r14
0x1800ab210  test    rcx, rcx
0x1800ab213  jz      short loc_1800AB223
0x1800ab215  xor     edx, edx; dwSize
0x1800ab217  mov     r8d, 8000h; dwFreeType
0x1800ab21d  call    cs:__imp_VirtualFree
0x1800ab223  lea     rcx, [rdi+70h]; void *
0x1800ab227  xor     edx, edx; Val
0x1800ab229  lea     r8d, [rdx+60h]; Size
0x1800ab22d  call    memset_0
0x1800ab232  mov     rcx, [rdi]
0x1800ab235  lea     rax, [rcx+1000h]
0x1800ab23c  mov     [rdi+0B0h], rax
0x1800ab243  mov     [rdi+0A8h], rcx
0x1800ab24a  mov     rax, [rsi]
0x1800ab24d  mov     [rdi+20h], rax
0x1800ab251  mov     [rsi], rdi
0x1800ab254  inc     qword ptr [rsi+8]
0x1800ab258  lea     rcx, [rbp+57h+var_D0]
0x1800ab25c  call    ??1?$CComPtrBase@VCApplicationIdentity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(void)
0x1800ab261  nop
0x1800ab262  lea     rcx, [rbp+57h+var_C8]
0x1800ab266  call    ??1?$CComPtrBase@VCApplicationIdentity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(void)
0x1800ab26b  nop
0x1800ab26c  lea     rcx, [rbp+57h+var_B0]; this
0x1800ab270  call    ??1ScopedD3D12InternalDeviceChildCreation@@QEAA@XZ; ScopedD3D12InternalDeviceChildCreation::~ScopedD3D12InternalDeviceChildCreation(void)
0x1800ab275  nop
0x1800ab276  lea     rcx, [rbp+57h+var_C0]
0x1800ab27a  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800ab27f  nop
0x1800ab280  lea     rcx, [rbp+57h+var_B8]
0x1800ab284  call    ??1?$unique_ptr@XVVirtualFreeDeleter@Dred@@@std@@QEAA@XZ; std::unique_ptr<void,Dred::VirtualFreeDeleter>::~unique_ptr<void,Dred::VirtualFreeDeleter>(void)
0x1800ab289  nop
0x1800ab28a  mov     rax, rdi
0x1800ab28d  mov     rcx, [rbp+57h+var_50]
0x1800ab291  xor     rcx, rsp; StackCookie
0x1800ab294  call    __security_check_cookie
0x1800ab299  add     rsp, 0E8h
0x1800ab2a0  pop     r15
0x1800ab2a2  pop     r14
0x1800ab2a4  pop     r13
0x1800ab2a6  pop     r12
0x1800ab2a8  pop     rdi
0x1800ab2a9  pop     rsi
0x1800ab2aa  pop     rbx
0x1800ab2ab  pop     rbp
0x1800ab2ac  retn
```
