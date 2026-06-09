# CCommandQueue<14>::ExecuteCommandListsImpl(uint,ID3D12CommandList * const *)

- ea: `0x1800b0f84`
- end: `0x1800b1697`
- name: `?ExecuteCommandListsImpl@?$CCommandQueue@$0O@@@QEAAXIPEBQEAUID3D12CommandList@@@Z`
- size: `1811`
- prototype: `__int64 __fastcall(CCastableCommandQueue *this, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800b0f20`

## callees

- `0x18000ac4c`
- `0x18000b010`
- `0x18000b2a0`
- `0x18000b630`
- `0x18000ccfc`
- `0x180017d60`
- `0x180022150`
- `0x1800221bc`
- `0x180048ae0`
- `0x18004bb30`
- `0x18004dc60`
- `0x180060b44`
- `0x180075168`
- `0x1800a09c0`
- `0x1800a21ec`
- `0x1800a6754`
- `0x1800a6af4`
- `0x1800b0f84`
- `0x18012cd98`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800b1629`
- `msvcp_win!_Mtx_unlock` at `0x1800b1629`

## string_xrefs

- `0x1800b11a9`: `Node mask mismatch between command list and command queue.`
- `0x1800b1170`: `Command lists must be successfully closed before execution.`
- `0x1800b1145`: `Command lists must be closed before execution.`
- `0x1800b1113`: `Command lists must have matching type to queue.`
- `0x1800b10e3`: `A bundle cannot be passed to ExecuteCommandLists.`
- `0x1800b13f6`: `Up to %d swapchains can be written to by a single ExecuteCommandLists call. `

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
void __fastcall CCommandQueue<14>::ExecuteCommandListsImpl(
        CCastableCommandQueue *this,
        unsigned int a2,
        struct ID3D12CommandList *const *a3)
{
  struct _Mtx_internal_imp_t *v5; // r12
  __int64 **v6; // r14
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  char v10; // r15
  struct ID3D12CommandList *const *v11; // rdi
  char v12; // al
  __int64 v13; // rcx
  struct ID3D12CommandList *v14; // rdi
  ID3D12CommandList_vtbl *v15; // rdx
  int v16; // eax
  int v17; // eax
  ID3D12CommandList_vtbl *v18; // r15
  HRESULT (__fastcall *i)(IUnknown *, const _GUID *, void **); // r14
  Dred::CBreadcrumbBuffer *v20; // rcx
  char v21; // si
  ID3D12CommandList_vtbl *v22; // rsi
  HRESULT (__fastcall *SetPrivateData)(ID3D12Object *, const _GUID *, unsigned int, const void *); // rax
  _QWORD *v24; // rcx
  int v25; // eax
  HRESULT (__fastcall *SetPrivateDataInterface)(ID3D12Object *, const _GUID *, const IUnknown *); // rax
  __int64 v27; // rdx
  HRESULT (__fastcall **p_GetDevice)(ID3D12DeviceChild *, const _GUID *, void **); // rdi
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, HRESULT (__fastcall **)(ID3D12DeviceChild *, const _GUID *, void **)); // rax
  __int64 *v31; // rdi
  __int64 *v32; // r14
  _QWORD *v33; // rsi
  int v34; // ecx
  char v35; // [rsp+30h] [rbp-B8h]
  int v36; // [rsp+34h] [rbp-B4h]
  CCastableCommandQueue *v37; // [rsp+38h] [rbp-B0h] BYREF
  ID3D12CommandList_vtbl *v38; // [rsp+40h] [rbp-A8h] BYREF
  int v39; // [rsp+48h] [rbp-A0h]
  ID3D12CommandList_vtbl *v40; // [rsp+50h] [rbp-98h] BYREF
  HRESULT (__fastcall *v41)(ID3D12Object *, const _GUID *, unsigned int, const void *); // [rsp+58h] [rbp-90h]
  __int64 v42; // [rsp+60h] [rbp-88h] BYREF
  struct ID3D12CommandList *v43; // [rsp+68h] [rbp-80h]
  CTrackedWorkload *v44; // [rsp+70h] [rbp-78h]
  __int64 v45; // [rsp+78h] [rbp-70h] BYREF
  char v46; // [rsp+80h] [rbp-68h]
  char *v47; // [rsp+88h] [rbp-60h]
  CCastableCommandQueue *v48; // [rsp+90h] [rbp-58h]
  char v49[72]; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v52; // [rsp+108h] [rbp+20h] BYREF

  v36 = 0;
  v5 = (CCastableCommandQueue *)((char *)this + 368);
  v47 = (char *)this + 368;
  std::_Mutex_base::lock((CCastableCommandQueue *)((char *)this + 368));
  v6 = (__int64 **)((char *)this + 584);
  v7 = *((_QWORD *)this + 73);
  if ( v7 != *((_QWORD *)this + 74) )
    *((_QWORD *)this + 74) = v7;
  v8 = *((_QWORD *)this + 76);
  if ( v8 != *((_QWORD *)this + 77) )
    *((_QWORD *)this + 77) = v8;
  v9 = *((_QWORD *)this + 19);
  v45 = v9 + 4832;
  v46 = 0;
  if ( *(_BYTE *)(v9 + 4912) )
    std::unique_lock<std::recursive_mutex>::lock(&v45);
  v10 = 0;
  LOBYTE(v52) = 0;
  v48 = this;
  v11 = a3;
  v44 = CCastableCommandQueue::CompleteTrackedWorkloadPairs(this, a2, a3);
  v12 = 0;
  v35 = 0;
  v13 = 0;
  v39 = 0;
  while ( (unsigned int)v13 < a2 )
  {
    v14 = v11[v13];
    v43 = v14;
    v15 = v14[-2].__vftable;
    if ( v15 )
      v15[2].GetType = (D3D12_COMMAND_LIST_TYPE (__fastcall *)(ID3D12CommandList *))_InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 19) + 7752LL));
    if ( !LODWORD(v14[17].__vftable) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
        1131,
        0);
      ThrowFailure(-2147024809);
    }
    v16 = (int)v14[3].__vftable;
    if ( v16 == 1 )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_BUNDLENOTSUPPORTED,
        "A bundle cannot be passed to ExecuteCommandLists.");
      ThrowFailure(-2147024809);
    }
    else if ( v16 != *((_DWORD *)this + 113) )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_COMMANDLISTMISMATCH,
        "Command lists must have matching type to queue.");
      ThrowFailure(-2147024809);
    }
    if ( v14[19].__vftable != (ID3D12CommandList_vtbl *)-1LL )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_OPENCOMMANDLIST,
        "Command lists must be closed before execution.");
      ThrowFailure(-2147024809);
    }
    if ( SLODWORD(v14[18].__vftable) < 0 )
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_EXECUTECOMMANDLISTS_FAILEDCOMMANDLIST,
        "Command lists must be successfully closed before execution.");
      ThrowFailure(-2147024809);
    }
    if ( *((_DWORD *)this + 116) == (*((_DWORD *)this + 116) & HIDWORD(v14[3].__vftable)) )
    {
      v36 = 0;
    }
    else
    {
      CDevice::ReportRetailValidationErrorF(
        (CDevice *)(*((_QWORD *)this + 19) + 288LL),
        D3D12_MESSAGE_ID_NODE_MASK_MISMATCH,
        "Node mask mismatch between command list and command queue.");
      ThrowFailure(-2147024809);
      v36 = -2147024809;
    }
    v17 = ((__int64 (__fastcall *)(struct ID3D12CommandList *))v14[-8].GetPrivateData)(&v14[-8]);
    ThrowFailure(v17);
    v18 = v14[34].__vftable;
    for ( i = v18->QueryInterface;
          (char *)i != (char *)v18;
          i = *(HRESULT (__fastcall **)(IUnknown *, const _GUID *, void **))i )
    {
      v22 = (ID3D12CommandList_vtbl *)*((_QWORD *)i + 2);
      v38 = v22;
      SetPrivateData = v22[4].SetPrivateData;
      v41 = SetPrivateData;
      v24 = (_QWORD *)*((_QWORD *)SetPrivateData + 1);
      if ( v24 )
      {
        v40 = 0;
        v37 = 0;
        if ( (*(int (__fastcall **)(_QWORD, GUID *, ID3D12CommandList_vtbl **, GUID *, CCastableCommandQueue **))(*(_QWORD *)*v24 + 40LL))(
               *v24,
               &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
               &v40,
               &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
               &v37) >= 0 )
        {
          if ( v40 != v22 || v37 != this )
          {
            NDXGI::CDevice::RemoveDevice(*(NDXGI::CDevice **)(*((_QWORD *)this + 19) + 760LL), -2005270485);
            ThrowFailure(-2147024809);
          }
          v25 = (*(__int64 (__fastcall **)(_QWORD))(***((_QWORD ***)v41 + 1) + 48LL))(**((_QWORD **)v41 + 1));
          ThrowFailure(v25);
        }
        ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v37);
        ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v40);
        SetPrivateData = v41;
      }
      if ( (*((_BYTE *)SetPrivateData + 16) & 1) != 0 )
      {
        std::_Hash<std::_Umap_traits<CResource *,unsigned int,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,unsigned int>>,0>>::find(
          (char *)this + 304,
          &v42,
          &v38);
        if ( v42 == *((_QWORD *)this + 39) )
        {
          if ( *((_QWORD *)this + 40) >= 8u )
          {
            CDevice::ReportRetailValidationErrorF(
              (CDevice *)(*((_QWORD *)this + 19) + 288LL),
              D3D12_MESSAGE_ID_COMMAND_QUEUE_TOO_MANY_SWAPCHAIN_REFERENCES,
              "Up to %d swapchains can be written to by a single ExecuteCommandLists call. ",
              8);
            ThrowFailure(-2147024809);
          }
          if ( LOBYTE(v22[5].SetPrivateData) == 4 )
            SetPrivateDataInterface = 0;
          else
            SetPrivateDataInterface = v22[5].SetPrivateDataInterface;
          LODWORD(v37) = *((_DWORD *)SetPrivateDataInterface + 62);
          v27 = *((_QWORD *)this + 19);
          if ( *(_DWORD *)(v27 + 2832) )
          {
            p_GetDevice = &v22[5].GetDevice;
            v29 = v27 + 8288;
            v30 = (__int64 (__fastcall *)(__int64, HRESULT (__fastcall **)(ID3D12DeviceChild *, const _GUID *, void **)))(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v27 + 5296) + 712LL))(*(_QWORD *)(v27 + 5296), *(_QWORD *)(v27 + 5288));
            LODWORD(v37) = v30(v29, p_GetDevice);
            v14 = v43;
          }
          std::_Hash<std::_Umap_traits<CResource *,unsigned int,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,unsigned int>>,0>>::emplace<CResource * &,unsigned int &>(
            (char *)this + 304,
            v49,
            &v38,
            &v37);
        }
      }
    }
    v20 = (Dred::CBreadcrumbBuffer *)v14[-2].__vftable;
    if ( v20 )
      Dred::CBreadcrumbBuffer::SetCommandQueue(v20, this);
    v38 = (ID3D12CommandList_vtbl *)&v14[78];
    v6 = (__int64 **)((char *)this + 584);
    std::vector<D3D12DDI_HCOMMANDLIST>::push_back((char *)this + 584, &v38);
    v38 = v14[-12].__vftable;
    std::vector<void const *>::push_back((char *)this + 608, &v38);
    v21 = (char)v14[13].__vftable;
    if ( LODWORD(v14[3].__vftable) || !BYTE5(v14[183].__vftable) )
      goto LABEL_32;
    if ( !v35 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
        1209,
        0);
      ThrowFailure(-2147024809);
LABEL_32:
      v12 = v35;
      goto LABEL_33;
    }
    v12 = 0;
    v35 = 0;
LABEL_33:
    v10 = v21 | v52;
    LOBYTE(v52) = v21 | v52;
    if ( !LODWORD(v14[3].__vftable) )
    {
      if ( BYTE4(v14[183].__vftable) )
        v12 = 1;
      v35 = v12;
    }
    v13 = (unsigned int)++v39;
    v11 = a3;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
      1210,
      0);
    ThrowFailure(-2147024809);
  }
  if ( !v10 || *(_BYTE *)(*((_QWORD *)this + 19) + 4913LL) )
  {
    if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
      McTemplateU0pqPR1_EtwEventWriteTransfer(
        v13,
        (unsigned int)EventD3D12StartExecuteCommandLists,
        *((_QWORD *)this + 20),
        (__int64)(*((_QWORD *)this + 77) - *((_QWORD *)this + 76)) >> 3,
        *((_QWORD *)this + 76));
    TableFunctionTraits<11>::Detail::InvokerImpl<TableFunctionTraitsImpl<11>::FunctionTraits<83,0,void>,void,void,D3D12DDI_HCOMMANDQUEUE,unsigned int,D3D12DDI_HCOMMANDLIST const *>::Call<CCommandQueue<14>>(
      this,
      (char *)this + 640,
      v6[1] - *v6,
      *v6);
    if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
      McTemplateU0pqPR1_EtwEventWriteTransfer(
        v34,
        (unsigned int)EventD3D12StopExecuteCommandLists,
        *((_QWORD *)this + 20),
        (__int64)(*((_QWORD *)this + 77) - *((_QWORD *)this + 76)) >> 3,
        *((_QWORD *)this + 76));
  }
  else
  {
    v31 = *v6;
    v32 = v6[1];
    while ( v31 != v32 )
    {
      v52 = *v31;
      v33 = (_QWORD *)(v52 - 720);
      if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
        McTemplateU0pp_EtwEventWriteTransfer(v13, EventD3D12StartExecuteCommandList, *((_QWORD *)this + 20), *v33);
      TableFunctionTraits<11>::Detail::InvokerImpl<TableFunctionTraitsImpl<11>::FunctionTraits<83,0,void>,void,void,D3D12DDI_HCOMMANDQUEUE,unsigned int,D3D12DDI_HCOMMANDLIST const *>::Call<CCommandQueue<14>>(
        this,
        (char *)this + 640,
        1,
        &v52);
      if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
        McTemplateU0pp_EtwEventWriteTransfer(v13, EventD3D12StopExecuteCommandList, *((_QWORD *)this + 20), *v33);
      ++v31;
    }
  }
  if ( v44 )
    CTrackedWorkload::SignalTrackedWorkload(v44);
  std::_Hash<std::_Umap_traits<CResource *,unsigned int,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,unsigned int>>,0>>::clear((char *)this + 304);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v45);
  _Mtx_unlock(v5);
  if ( v36 < 0 )
    NDXGI::CDevice::RemoveDevice(*(NDXGI::CDevice **)(*((_QWORD *)this + 19) + 760LL), -2005270527);
}

```

## disassembly

```asm
0x1800b0f84  mov     rax, rsp
0x1800b0f87  mov     [rax+18h], r8
0x1800b0f8b  mov     [rax+10h], edx
0x1800b0f8e  mov     [rax+8], rcx
0x1800b0f92  push    rbx
0x1800b0f93  push    rsi
0x1800b0f94  push    rdi
0x1800b0f95  push    r12
0x1800b0f97  push    r14
0x1800b0f99  push    r15
0x1800b0f9b  sub     rsp, 0B8h
0x1800b0fa2  mov     esi, edx
0x1800b0fa4  mov     rbx, rcx
0x1800b0fa7  xor     edi, edi
0x1800b0fa9  mov     [rsp+0E8h+var_B4], edi
0x1800b0fad  lea     r12, [rcx+170h]
0x1800b0fb4  mov     [rax-60h], r12
0x1800b0fb8  mov     rcx, r12; this
0x1800b0fbb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800b0fc0  nop
0x1800b0fc1  lea     r14, [rbx+248h]
0x1800b0fc8  mov     rax, [r14]
0x1800b0fcb  cmp     rax, [r14+8]
0x1800b0fcf  jz      short loc_1800B0FD5
0x1800b0fd1  mov     [r14+8], rax
0x1800b0fd5  lea     rdi, [rbx+260h]
0x1800b0fdc  mov     rax, [rdi]
0x1800b0fdf  cmp     rax, [rdi+8]
0x1800b0fe3  jz      short loc_1800B0FE9
0x1800b0fe5  mov     [rdi+8], rax
0x1800b0fe9  mov     rcx, [rbx+98h]
0x1800b0ff0  lea     rax, [rcx+12E0h]
0x1800b0ff7  mov     [rsp+0E8h+var_70], rax
0x1800b0ffc  mov     [rsp+0E8h+var_68], 0
0x1800b1004  cmp     byte ptr [rcx+1330h], 0
0x1800b100b  jz      short loc_1800B1017
0x1800b100d  lea     rcx, [rsp+0E8h+var_70]
0x1800b1012  call    ?lock@?$unique_lock@Vrecursive_mutex@std@@@std@@QEAAXXZ; std::unique_lock<std::recursive_mutex>::lock(void)
0x1800b1017  xor     r15b, r15b
0x1800b101a  mov     byte ptr [rsp+0E8h+arg_18], r15b
0x1800b1022  mov     [rsp+0E8h+var_58], rbx
0x1800b102a  mov     rdi, [rsp+0E8h+arg_10]
0x1800b1032  mov     r8, rdi; struct ID3D12CommandList **
0x1800b1035  mov     edx, esi; unsigned int
0x1800b1037  mov     rcx, rbx; this
0x1800b103a  call    ?CompleteTrackedWorkloadPairs@CCastableCommandQueue@@IEAAPEAVCTrackedWorkload@@IPEBQEAUID3D12CommandList@@@Z; CCastableCommandQueue::CompleteTrackedWorkloadPairs(uint,ID3D12CommandList * const *)
0x1800b103f  mov     [rsp+0E8h+var_78], rax
0x1800b1044  xor     al, al
0x1800b1046  mov     [rsp+0E8h+var_B8], eax
0x1800b104a  xor     ecx, ecx
0x1800b104c  mov     [rsp+0E8h+var_A0], ecx
0x1800b1050  lea     r8d, [rcx+1]
0x1800b1054  mov     esi, 80070057h
0x1800b1059  cmp     ecx, [rsp+0E8h+arg_8]
0x1800b1060  jnb     loc_1800B14A1
0x1800b1066  mov     rdi, [rdi+rcx*8]
0x1800b106a  mov     [rsp+0E8h+var_80], rdi
0x1800b106f  mov     rdx, [rdi-10h]
0x1800b1073  test    rdx, rdx
0x1800b1076  jz      short loc_1800B1095
0x1800b1078  mov     rax, [rbx+98h]
0x1800b107f  mov     rcx, r8
0x1800b1082  lock xadd [rax+1E48h], rcx
0x1800b108b  add     rcx, r8
0x1800b108e  mov     [rdx+0D0h], rcx
0x1800b1095  cmp     dword ptr [rdi+88h], 0
0x1800b109c  jnz     short loc_1800B10CD
0x1800b109e  mov     rax, [rbx+98h]
0x1800b10a5  mov     rcx, [rax+308h]
0x1800b10ac  mov     rax, [rcx]
0x1800b10af  xor     r8d, r8d
0x1800b10b2  mov     edx, 46Bh
0x1800b10b7  mov     rax, [rax+20h]
0x1800b10bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b10c0  mov     ecx, esi; int
0x1800b10c2  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b10c7  mov     r8d, 1
0x1800b10cd  mov     eax, [rdi+18h]
0x1800b10d0  cmp     eax, r8d
0x1800b10d3  jnz     short loc_1800B10FD
0x1800b10d5  mov     rcx, [rbx+98h]
0x1800b10dc  add     rcx, 120h; this
0x1800b10e3  lea     r8, aABundleCannotB; "A bundle cannot be passed to ExecuteCom"...
0x1800b10ea  mov     edx, 343h; enum D3D12_MESSAGE_ID
0x1800b10ef  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b10f4  mov     ecx, esi; int
0x1800b10f6  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b10fb  jmp     short loc_1800B112B
0x1800b10fd  cmp     eax, [rbx+1C4h]
0x1800b1103  jz      short loc_1800B112B
0x1800b1105  mov     rcx, [rbx+98h]
0x1800b110c  add     rcx, 120h; this
0x1800b1113  lea     r8, aCommandListsMu_0; "Command lists must have matching type t"...
0x1800b111a  mov     edx, 344h; enum D3D12_MESSAGE_ID
0x1800b111f  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b1124  mov     ecx, esi; int
0x1800b1126  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b112b  mov     r14d, 120h
0x1800b1131  cmp     qword ptr [rdi+98h], 0FFFFFFFFFFFFFFFFh
0x1800b1139  jz      short loc_1800B115D
0x1800b113b  mov     rcx, [rbx+98h]
0x1800b1142  add     rcx, r14; this
0x1800b1145  lea     r8, aCommandListsMu; "Command lists must be closed before exe"...
0x1800b114c  mov     edx, 345h; enum D3D12_MESSAGE_ID
0x1800b1151  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b1156  mov     ecx, esi; int
0x1800b1158  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b115d  cmp     dword ptr [rdi+90h], 0
0x1800b1164  jge     short loc_1800B1188
0x1800b1166  mov     rcx, [rbx+98h]
0x1800b116d  add     rcx, r14; this
0x1800b1170  lea     r8, aCommandListsMu_1; "Command lists must be successfully clos"...
0x1800b1177  mov     edx, 346h; enum D3D12_MESSAGE_ID
0x1800b117c  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b1181  mov     ecx, esi; int
0x1800b1183  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b1188  mov     ecx, [rbx+1D0h]
0x1800b118e  mov     eax, [rdi+1Ch]
0x1800b1191  and     eax, ecx
0x1800b1193  cmp     ecx, eax
0x1800b1195  jnz     short loc_1800B119F
0x1800b1197  xor     eax, eax
0x1800b1199  mov     [rsp+0E8h+var_B4], eax
0x1800b119d  jmp     short loc_1800B11C5
0x1800b119f  mov     rcx, [rbx+98h]
0x1800b11a6  add     rcx, r14; this
0x1800b11a9  lea     r8, aNodeMaskMismat_5; "Node mask mismatch between command list"...
0x1800b11b0  mov     edx, 386h; enum D3D12_MESSAGE_ID
0x1800b11b5  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b11ba  mov     ecx, esi; int
0x1800b11bc  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b11c1  mov     [rsp+0E8h+var_B4], esi
0x1800b11c5  lea     rcx, [rdi-40h]
0x1800b11c9  mov     rax, [rcx]
0x1800b11cc  mov     rax, [rax+18h]
0x1800b11d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b11d5  mov     ecx, eax; int
0x1800b11d7  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b11dc  mov     r15, [rdi+110h]
0x1800b11e3  mov     r14, [r15]
0x1800b11e6  cmp     r14, r15
0x1800b11e9  jnz     loc_1800B12D8
0x1800b11ef  mov     rcx, [rdi-10h]; this
0x1800b11f3  test    rcx, rcx
0x1800b11f6  jz      short loc_1800B1200
0x1800b11f8  mov     rdx, rbx; struct CCastableCommandQueue *
0x1800b11fb  call    ?SetCommandQueue@CBreadcrumbBuffer@Dred@@QEAAXPEAVCCastableCommandQueue@@@Z; Dred::CBreadcrumbBuffer::SetCommandQueue(CCastableCommandQueue *)
0x1800b1200  lea     rax, [rdi+270h]
0x1800b1207  mov     [rsp+0E8h+var_A8], rax
0x1800b120c  lea     rdx, [rsp+0E8h+var_A8]
0x1800b1211  lea     r14, [rbx+248h]
0x1800b1218  mov     rcx, r14
0x1800b121b  call    ?push_back@?$vector@UD3D12DDI_HCOMMANDLIST@@V?$allocator@UD3D12DDI_HCOMMANDLIST@@@std@@@std@@QEAAX$$QEAUD3D12DDI_HCOMMANDLIST@@@Z; std::vector<D3D12DDI_HCOMMANDLIST>::push_back(D3D12DDI_HCOMMANDLIST &&)
0x1800b1220  mov     rax, [rdi-60h]
0x1800b1224  mov     [rsp+0E8h+var_A8], rax
0x1800b1229  lea     rdx, [rsp+0E8h+var_A8]
0x1800b122e  lea     rax, [rbx+260h]
0x1800b1235  mov     rcx, rax
0x1800b1238  call    ?push_back@?$vector@PEBXV?$allocator@PEBX@std@@@std@@QEAAX$$QEAPEBX@Z; std::vector<void const *>::push_back(void const * &&)
0x1800b123d  mov     sil, [rdi+68h]
0x1800b1241  cmp     dword ptr [rdi+18h], 0
0x1800b1245  jnz     short loc_1800B1283
0x1800b1247  cmp     byte ptr [rdi+5BDh], 0
0x1800b124e  jz      short loc_1800B1283
0x1800b1250  cmp     byte ptr [rsp+0E8h+var_B8], 0
0x1800b1255  jnz     short loc_1800B12D0
0x1800b1257  mov     rax, [rbx+98h]
0x1800b125e  mov     rcx, [rax+308h]
0x1800b1265  mov     rax, [rcx]
0x1800b1268  xor     r8d, r8d
0x1800b126b  mov     edx, 4B9h
0x1800b1270  mov     rax, [rax+20h]
0x1800b1274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1279  mov     ecx, 80070057h; int
0x1800b127e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b1283  mov     eax, [rsp+0E8h+var_B8]
0x1800b1287  mov     r15b, byte ptr [rsp+0E8h+arg_18]
0x1800b128f  or      r15b, sil
0x1800b1292  mov     byte ptr [rsp+0E8h+arg_18], r15b
0x1800b129a  mov     r8d, 1
0x1800b12a0  cmp     dword ptr [rdi+18h], 0
0x1800b12a4  jnz     short loc_1800B12B8
0x1800b12a6  movzx   eax, al
0x1800b12a9  cmp     byte ptr [rdi+5BCh], 0
0x1800b12b0  cmovnz  eax, r8d
0x1800b12b4  mov     [rsp+0E8h+var_B8], eax
0x1800b12b8  mov     ecx, [rsp+0E8h+var_A0]
0x1800b12bc  add     ecx, r8d
0x1800b12bf  mov     [rsp+0E8h+var_A0], ecx
0x1800b12c3  mov     rdi, [rsp+0E8h+arg_10]
0x1800b12cb  jmp     loc_1800B1054
0x1800b12d0  xor     al, al
0x1800b12d2  mov     [rsp+0E8h+var_B8], eax
0x1800b12d6  jmp     short loc_1800B1287
0x1800b12d8  mov     rsi, [r14+10h]
0x1800b12dc  mov     [rsp+0E8h+var_A8], rsi
0x1800b12e1  mov     rax, [rsi+140h]
0x1800b12e8  mov     [rsp+0E8h+var_90], rax
0x1800b12ed  mov     rcx, [rax+8]
0x1800b12f1  test    rcx, rcx
0x1800b12f4  jz      loc_1800B13A6
0x1800b12fa  mov     [rsp+0E8h+var_98], 0
0x1800b1303  mov     [rsp+0E8h+var_B0], 0
0x1800b130c  mov     rcx, [rcx]
0x1800b130f  mov     rax, [rcx]
0x1800b1312  lea     rdx, [rsp+0E8h+var_B0]
0x1800b1317  mov     [rsp+0E8h+var_C8], rdx
0x1800b131c  lea     r9, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x1800b1323  lea     r8, [rsp+0E8h+var_98]
0x1800b1328  lea     rdx, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x1800b132f  mov     rax, [rax+28h]
0x1800b1333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1338  test    eax, eax
0x1800b133a  js      short loc_1800B138C
0x1800b133c  cmp     [rsp+0E8h+var_98], rsi
0x1800b1341  jnz     short loc_1800B134A
0x1800b1343  cmp     [rsp+0E8h+var_B0], rbx
0x1800b1348  jz      short loc_1800B136C
0x1800b134a  mov     rcx, [rbx+98h]
0x1800b1351  mov     edx, 887A002Bh; int
0x1800b1356  mov     rcx, [rcx+2F8h]; this
0x1800b135d  call    ?RemoveDevice@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::RemoveDevice(long)
0x1800b1362  mov     ecx, 80070057h; int
0x1800b1367  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b136c  mov     rax, [rsp+0E8h+var_90]
0x1800b1371  mov     rax, [rax+8]
0x1800b1375  mov     rcx, [rax]
0x1800b1378  mov     rax, [rcx]
0x1800b137b  mov     rax, [rax+30h]
0x1800b137f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1384  mov     ecx, eax; int
0x1800b1386  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b138b  nop
0x1800b138c  lea     rcx, [rsp+0E8h+var_B0]
0x1800b1391  call    ??1?$CComPtrBase@VCApplicationIdentity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(void)
0x1800b1396  nop
0x1800b1397  lea     rcx, [rsp+0E8h+var_98]
0x1800b139c  call    ??1?$CComPtrBase@VCApplicationIdentity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(void)
0x1800b13a1  mov     rax, [rsp+0E8h+var_90]
0x1800b13a6  test    byte ptr [rax+10h], 1
0x1800b13aa  jz      loc_1800B1499
0x1800b13b0  lea     rcx, [rbx+130h]
0x1800b13b7  lea     r8, [rsp+0E8h+var_A8]
0x1800b13bc  lea     rdx, [rsp+0E8h+var_88]
0x1800b13c1  call    ?find@?$_Hash@V?$_Umap_traits@PEAVCResource@@IV?$_Uhash_compare@PEAVCResource@@U?$hash@PEAVCResource@@@std@@U?$equal_to@PEAVCResource@@@3@@std@@V?$allocator@U?$pair@QEAVCResource@@I@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVCResource@@I@std@@@std@@@std@@@2@AEBQEAVCResource@@@Z; std::_Hash<std::_Umap_traits<CResource *,uint,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,uint>>,0>>::find(CResource * const &)
0x1800b13c6  mov     rax, [rbx+138h]
0x1800b13cd  cmp     [rsp+0E8h+var_88], rax
0x1800b13d2  jnz     loc_1800B1499
0x1800b13d8  cmp     qword ptr [rbx+140h], 8
0x1800b13e0  jb      short loc_1800B1411
0x1800b13e2  mov     rcx, [rbx+98h]
0x1800b13e9  add     rcx, 120h; this
0x1800b13f0  mov     r9d, 8
0x1800b13f6  lea     r8, aUpToDSwapchain; "Up to %d swapchains can be written to b"...
0x1800b13fd  mov     edx, 38Ah; enum D3D12_MESSAGE_ID
0x1800b1402  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x1800b1407  mov     ecx, 80070057h; int
0x1800b140c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b1411  cmp     byte ptr [rsi+188h], 4
0x1800b1418  jnz     short loc_1800B141E
0x1800b141a  xor     eax, eax
0x1800b141c  jmp     short loc_1800B1425
0x1800b141e  mov     rax, [rsi+190h]
0x1800b1425  mov     eax, [rax+0F8h]
0x1800b142b  mov     dword ptr [rsp+0E8h+var_B0], eax
0x1800b142f  mov     rdx, [rbx+98h]
0x1800b1436  cmp     dword ptr [rdx+0B10h], 0
0x1800b143d  jz      short loc_1800B147B
0x1800b143f  lea     rdi, [rsi+1A0h]
0x1800b1446  lea     rsi, [rdx+2060h]
0x1800b144d  mov     rcx, [rdx+14B0h]
0x1800b1454  mov     rax, [rcx]
0x1800b1457  mov     rdx, [rdx+14A8h]
0x1800b145e  mov     rax, [rax+2C8h]
0x1800b1465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b146a  mov     rdx, rdi
0x1800b146d  mov     rcx, rsi
0x1800b1470  call    rax
0x1800b1472  mov     dword ptr [rsp+0E8h+var_B0], eax
0x1800b1476  mov     rdi, [rsp+0E8h+var_80]
0x1800b147b  lea     r9, [rsp+0E8h+var_B0]
0x1800b1480  lea     r8, [rsp+0E8h+var_A8]
0x1800b1485  lea     rdx, [rsp+0E8h+var_48]
0x1800b148d  lea     rcx, [rbx+130h]
0x1800b1494  call    ??$emplace@AEAPEAVCResource@@AEAI@?$_Hash@V?$_Umap_traits@PEAVCResource@@IV?$_Uhash_compare@PEAVCResource@@U?$hash@PEAVCResource@@@std@@U?$equal_to@PEAVCResource@@@3@@std@@V?$allocator@U?$pair@QEAVCResource@@I@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVCResource@@I@std@@@std@@@std@@@std@@_N@1@AEAPEAVCResource@@AEAI@Z; std::_Hash<std::_Umap_traits<CResource *,uint,std::_Uhash_compare<CResource *,std::hash<CResource *>,std::equal_to<CResource *>>,std::allocator<std::pair<CResource * const,uint>>,0>>::emplace<CResource * &,uint &>(CResource * &,uint &)
0x1800b1499  mov     r14, [r14]
0x1800b149c  jmp     loc_1800B11E6
0x1800b14a1  test    al, al
0x1800b14a3  jz      short loc_1800B14CE
0x1800b14a5  mov     rax, [rbx+98h]
0x1800b14ac  mov     rcx, [rax+308h]
0x1800b14b3  mov     rax, [rcx]
0x1800b14b6  xor     r8d, r8d
0x1800b14b9  mov     edx, 4BAh
0x1800b14be  mov     rax, [rax+20h]
0x1800b14c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b14c7  mov     ecx, esi; int
0x1800b14c9  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800b14ce  test    r15b, r15b
0x1800b14d1  jz      loc_1800B156E
  ... truncated ...
```
