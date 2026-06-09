# MigrateUpgradeHistory(IMMDevice *,IMMDevice *)

- ea: `0x180035738`
- end: `0x1800359cf`
- name: `?MigrateUpgradeHistory@@YAJPEAUIMMDevice@@0@Z`
- size: `663`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f474`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180035738`
- `0x18003f7a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800358e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800358e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357ba`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357c5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003599d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800359a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357ba`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357c5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003599d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800359a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800357af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800357af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035991`

## string_xrefs

- `0x180035794`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180035872`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall MigrateUpgradeHistory(struct IMMDevice *a1, struct IMMDevice *a2)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  __int64 v12; // r9
  int v13; // ebx
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  LPVOID v16; // rax
  unsigned int v17; // r9d
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD *v20; // [rsp+30h] [rbp-20h]
  PROPVARIANT v21[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  __int64 v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h] BYREF

  v25 = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  *(_OWORD *)pvar = 0;
  v20 = 0;
  pv = 0;
  lpVtbl = a1->lpVtbl;
  v26 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a1, 0, &v26);
  v6 = v5;
  if ( v5 >= 0 )
  {
    OpenPropertyStore = a2->lpVtbl->OpenPropertyStore;
    v8 = v25;
    v25 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v9 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, __int64 *))OpenPropertyStore)(a2, 1, &v25);
    v6 = v9;
    if ( v9 >= 0 )
    {
      GetId = a1->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      v9 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a1, &pv);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v13 = 1;
        (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v26 + 40LL))(
          v26,
          PKEY_AudioEndpoint_MigrationHistory,
          v21);
        if ( LOWORD(v21[0]) == 4127 )
        {
          v13 = LODWORD(v21[1]) + 1;
          if ( (unsigned int)(LODWORD(v21[1]) + 1) > 0xA )
            v13 = 10;
        }
        v14 = CoTaskMemAlloc(8LL * v13);
        v15 = v14;
        if ( !v14 )
        {
          v6 = -2147024882;
          v12 = 2147942414LL;
          v10 = 9202;
LABEL_16:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)v12,
            (int)pvar[0]);
          if ( pv )
            CoTaskMemFree(pv);
LABEL_30:
          PropVariantClear(pvar);
          PropVariantClear(v21);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
          return v6;
        }
        memset_0(v14, 0, 8LL * v13);
        LOWORD(pvar[0]) = 4127;
        LODWORD(pvar[1]) = v13;
        v20 = v15;
        v16 = pv;
        pv = 0;
        *v15 = v16;
        v17 = 1;
        if ( v13 > 1 )
        {
          do
          {
            v20[v17] = *(_QWORD *)(v22 + 8LL * v17 - 8);
            *(_QWORD *)(v22 + 8LL * v17++ - 8) = 0;
          }
          while ( (int)v17 < v13 );
        }
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 48LL))(
               v25,
               PKEY_AudioEndpoint_MigrationHistory,
               pvar);
        v6 = v9;
        if ( v9 >= 0 )
        {
          if ( pv )
            CoTaskMemFree(pv);
          v6 = 0;
          goto LABEL_30;
        }
        v10 = 9227;
      }
      else
      {
        v10 = 9186;
      }
    }
    else
    {
      v10 = 9183;
    }
    v12 = (unsigned int)v9;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23DD,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v5,
    (int)pvar[0]);
  if ( pv )
    CoTaskMemFree(pv);
  PropVariantClear(pvar);
  PropVariantClear(v21);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return v6;
}

```

## disassembly

```asm
0x180035738  push    rbp
0x18003573a  push    rbx
0x18003573b  push    rsi
0x18003573c  push    rdi
0x18003573d  push    r12
0x18003573f  mov     rbp, rsp
0x180035742  sub     rsp, 50h
0x180035746  mov     rdi, rdx
0x180035749  mov     rsi, rcx
0x18003574c  mov     [rbp+arg_10], 0
0x180035754  xorps   xmm0, xmm0
0x180035757  xor     eax, eax
0x180035759  movups  xmmword ptr [rbp+var_18], xmm0
0x18003575d  mov     [rbp+var_8], rax
0x180035761  movups  xmmword ptr [rbp+pvar], xmm0
0x180035765  mov     [rbp+var_20], rax
0x180035769  mov     [rbp+pv], rax
0x18003576d  mov     rax, [rcx]
0x180035770  mov     [rbp+arg_18], 0
0x180035778  lea     r8, [rbp+arg_18]
0x18003577c  xor     edx, edx
0x18003577e  mov     rax, [rax+20h]
0x180035782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035787  mov     ebx, eax
0x180035789  test    eax, eax
0x18003578b  jns     short loc_1800357FD
0x18003578d  mov     rcx, [rbp+28h]; this
0x180035791  mov     r9d, eax; char *
0x180035794  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18003579b  mov     edx, 23DDh; void *
0x1800357a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800357a5  nop
0x1800357a6  mov     rcx, [rbp+pv]; pv
0x1800357aa  test    rcx, rcx
0x1800357ad  jz      short loc_1800357B6
0x1800357af  call    cs:__imp_CoTaskMemFree
0x1800357b5  nop
0x1800357b6  lea     rcx, [rbp+pvar]; pvar
0x1800357ba  call    cs:__imp_PropVariantClear
0x1800357c0  nop
0x1800357c1  lea     rcx, [rbp+var_18]; pvar
0x1800357c5  call    cs:__imp_PropVariantClear
0x1800357cb  nop
0x1800357cc  mov     rcx, [rbp+arg_18]
0x1800357d0  test    rcx, rcx
0x1800357d3  jz      short loc_1800357E2
0x1800357d5  mov     rax, [rcx]
0x1800357d8  mov     rax, [rax+10h]
0x1800357dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357e1  nop
0x1800357e2  mov     rcx, [rbp+arg_10]
0x1800357e6  test    rcx, rcx
0x1800357e9  jz      short loc_1800357F8
0x1800357eb  mov     rax, [rcx]
0x1800357ee  mov     rax, [rax+10h]
0x1800357f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357f7  nop
0x1800357f8  jmp     loc_1800359C2
0x1800357fd  mov     rax, [rdi]
0x180035800  mov     rbx, [rax+20h]
0x180035804  mov     rcx, [rbp+arg_10]
0x180035808  mov     [rbp+arg_10], 0
0x180035810  test    rcx, rcx
0x180035813  jz      short loc_180035822
0x180035815  mov     rdx, [rcx]
0x180035818  mov     rax, [rdx+10h]
0x18003581c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035821  nop
0x180035822  lea     r8, [rbp+arg_10]
0x180035826  mov     edx, 1
0x18003582b  mov     rcx, rdi
0x18003582e  mov     rax, rbx
0x180035831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035836  mov     ebx, eax
0x180035838  test    eax, eax
0x18003583a  jns     short loc_180035843
0x18003583c  mov     edx, 23DFh
0x180035841  jmp     short loc_18003586F
0x180035843  mov     rax, [rsi]
0x180035846  mov     rbx, [rax+28h]
0x18003584a  xor     edx, edx
0x18003584c  lea     rcx, [rbp+pv]
0x180035850  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035855  lea     rdx, [rbp+pv]
0x180035859  mov     rcx, rsi
0x18003585c  mov     rax, rbx
0x18003585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035864  mov     ebx, eax
0x180035866  test    eax, eax
0x180035868  jns     short loc_18003589B
0x18003586a  mov     edx, 23E2h; void *
0x18003586f  mov     r9d, eax; char *
0x180035872  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180035879  mov     rcx, [rbp+28h]; this
0x18003587d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035882  nop
0x180035883  mov     rcx, [rbp+pv]; pv
0x180035887  test    rcx, rcx
0x18003588a  jz      loc_180035999
0x180035890  call    cs:__imp_CoTaskMemFree
0x180035896  jmp     loc_180035999
0x18003589b  mov     ebx, 1
0x1800358a0  mov     rcx, [rbp+arg_18]
0x1800358a4  mov     rax, [rcx]
0x1800358a7  lea     r8, [rbp+var_18]
0x1800358ab  lea     rdx, PKEY_AudioEndpoint_MigrationHistory
0x1800358b2  mov     rax, [rax+28h]
0x1800358b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bb  mov     r12d, 101Fh
0x1800358c1  cmp     word ptr [rbp+var_18], r12w
0x1800358c6  jnz     short loc_1800358D7
0x1800358c8  mov     ebx, dword ptr [rbp+var_18+8]
0x1800358cb  inc     ebx
0x1800358cd  mov     eax, 0Ah
0x1800358d2  cmp     ebx, eax
0x1800358d4  cmova   ebx, eax
0x1800358d7  movsxd  rdi, ebx
0x1800358da  shl     rdi, 3
0x1800358de  mov     rcx, rdi; cb
0x1800358e1  call    cs:__imp_CoTaskMemAlloc
0x1800358e7  mov     rsi, rax
0x1800358ea  test    rax, rax
0x1800358ed  jnz     short loc_180035901
0x1800358ef  mov     ebx, 8007000Eh
0x1800358f4  mov     r9d, ebx
0x1800358f7  mov     edx, 23F2h
0x1800358fc  jmp     loc_180035872
0x180035901  mov     r8, rdi; Size
0x180035904  xor     edx, edx; Val
0x180035906  mov     rcx, rsi; void *
0x180035909  call    memset_0
0x18003590e  mov     word ptr [rbp+pvar], r12w
0x180035913  mov     dword ptr [rbp+pvar+8], ebx
0x180035916  mov     [rbp+var_20], rsi
0x18003591a  mov     rax, [rbp+pv]
0x18003591e  mov     [rbp+pv], 0
0x180035926  mov     [rsi], rax
0x180035929  mov     r9d, 1
0x18003592f  cmp     ebx, r9d
0x180035932  jle     short loc_18003595D
0x180035934  mov     r8d, r9d
0x180035937  mov     rax, [rbp+var_8]
0x18003593b  mov     rcx, [rax+r8*8-8]
0x180035940  mov     rax, [rbp+var_20]
0x180035944  mov     [rax+r8*8], rcx
0x180035948  mov     rax, [rbp+var_8]
0x18003594c  mov     qword ptr [rax+r8*8-8], 0
0x180035955  inc     r9d
0x180035958  cmp     r9d, ebx
0x18003595b  jl      short loc_180035934
0x18003595d  mov     rcx, [rbp+arg_10]
0x180035961  mov     rax, [rcx]
0x180035964  lea     r8, [rbp+pvar]
0x180035968  lea     rdx, PKEY_AudioEndpoint_MigrationHistory
0x18003596f  mov     rax, [rax+30h]
0x180035973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035978  mov     ebx, eax
0x18003597a  test    eax, eax
0x18003597c  jns     short loc_180035988
0x18003597e  mov     edx, 240Bh
0x180035983  jmp     loc_18003586F
0x180035988  mov     rcx, [rbp+pv]; pv
0x18003598c  test    rcx, rcx
0x18003598f  jz      short loc_180035997
0x180035991  call    cs:__imp_CoTaskMemFree
0x180035997  xor     ebx, ebx
0x180035999  lea     rcx, [rbp+pvar]; pvar
0x18003599d  call    cs:__imp_PropVariantClear
0x1800359a3  nop
0x1800359a4  lea     rcx, [rbp+var_18]; pvar
0x1800359a8  call    cs:__imp_PropVariantClear
0x1800359ae  nop
0x1800359af  lea     rcx, [rbp+arg_18]
0x1800359b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800359b8  nop
0x1800359b9  lea     rcx, [rbp+arg_10]
0x1800359bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800359c2  mov     eax, ebx
0x1800359c4  add     rsp, 50h
0x1800359c8  pop     r12
0x1800359ca  pop     rdi
0x1800359cb  pop     rsi
0x1800359cc  pop     rbx
0x1800359cd  pop     rbp
0x1800359ce  retn
```
