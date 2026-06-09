# CCreateDeviceCache::SelectAdapter(IUnknown *)

- ea: `0x1800567c8`
- end: `0x1800569ce`
- name: `?SelectAdapter@CCreateDeviceCache@@QEAAJPEAUIUnknown@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(CCreateDeviceCache *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007703c`

## callees

- `0x180003c84`
- `0x18000b010`
- `0x1800567c8`
- `0x1800569d4`
- `0x180056b3c`
- `0x180056c18`
- `0x1800bb480`
- `0x1800bc094`
- `0x180262020`

## import_xrefs

- `dxgi!CreateDXGIFactory2` at `0x180056864`
- `dxgi!CreateDXGIFactory2` at `0x1800569ae`
- `dxgi!CreateDXGIFactory2` at `0x180056864`
- `dxgi!CreateDXGIFactory2` at `0x1800569ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCreateDeviceCache::SelectAdapter(CCreateDeviceCache *this, struct IUnknown *a2)
{
  _QWORD *v4; // rax
  int v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  int v8; // eax
  HRESULT v10; // eax
  _QWORD *v11; // rsi
  void **v12; // r8
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  void *ppFactory; // [rsp+30h] [rbp-178h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-170h] BYREF
  _BYTE v21[296]; // [rsp+50h] [rbp-158h] BYREF
  __int64 v22; // [rsp+178h] [rbp-30h]

  ppFactory = 0;
  if ( (int)VersionedDXCoreAdapterFactory::Create((char *)this + 24) >= 0 )
  {
    if ( a2 && (int)VersionedDXCoreAdapter::CreateFromIDXCoreAdapter(a2, (char *)this + 40) >= 0 )
    {
      v4 = (_QWORD *)*((_QWORD *)this + 5);
      if ( *v4 )
        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, CCreateDeviceCache *))(*(_QWORD *)*v4 + 48LL))(
               *v4,
               0,
               8,
               this);
      else
        v5 = (*(__int64 (__fastcall **)(_QWORD, CCreateDeviceCache *))(*(_QWORD *)v4[1] + 48LL))(v4[1], this);
      ThrowFailure(v5);
    }
    else
    {
      v6 = CreateDXGIFactory2(0x80000000, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &ppFactory);
      ThrowFailure(v6);
      v20[0] = 0;
      if ( a2 )
        v7 = a2->QueryInterface(a2, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, (void **)v20);
      else
        v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD *))(*(_QWORD *)ppFactory + 56LL))(ppFactory, 0, v20);
      ThrowFailure(v7);
      memset_0(v21, 0, 0x130u);
      v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v20[0] + 64LL))(v20[0], v21);
      ThrowFailure(v8);
      *(_QWORD *)this = v22;
      VersionedDXCoreAdapterFactory::CreateAdapterFromLUID(*((_QWORD *)this + 3), this, (char *)this + 40);
      if ( v20[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20[0] + 16LL))(v20[0]);
    }
  }
  if ( !*((_QWORD *)this + 5) )
  {
    if ( ppFactory )
      v10 = 0;
    else
      v10 = CreateDXGIFactory2(0x80000000, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &ppFactory);
    ThrowFailure(v10);
    v11 = (_QWORD *)((char *)this + 16);
    v12 = (void **)((char *)this + 16);
    if ( a2 )
    {
      if ( a2->QueryInterface(a2, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, v12) < 0 )
      {
        v20[0] = 0;
        v13 = a2->QueryInterface(a2, &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e, (void **)v20);
        ThrowFailure(v13);
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, CCreateDeviceCache *))(*(_QWORD *)v20[0] + 48LL))(
                v20[0],
                0,
                8,
                this);
        ThrowFailure(v14);
        v15 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, char *))(*(_QWORD *)ppFactory + 208LL))(
                ppFactory,
                *(_QWORD *)this,
                &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0,
                (char *)this + 16);
        ThrowFailure(v15);
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v20);
LABEL_25:
        v18 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v11)(
                *v11,
                &GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf,
                (char *)this + 8);
        ThrowFailure(v18);
        goto LABEL_11;
      }
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(void *, _QWORD, void **))(*(_QWORD *)ppFactory + 56LL))(ppFactory, 0, v12);
      ThrowFailure(v16);
    }
    memset_0(v21, 0, 0x130u);
    v17 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v11 + 64LL))(*v11, v21);
    ThrowFailure(v17);
    *(_QWORD *)this = v22;
    goto LABEL_25;
  }
LABEL_11:
  if ( ppFactory )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  return 0;
}

```

## disassembly

```asm
0x1800567c8  mov     [rsp+arg_10], rbx
0x1800567cd  push    rsi
0x1800567ce  push    rdi
0x1800567cf  push    r14
0x1800567d1  sub     rsp, 190h
0x1800567d8  mov     rax, cs:__security_cookie
0x1800567df  xor     rax, rsp
0x1800567e2  mov     [rsp+1A8h+var_28], rax
0x1800567ea  mov     rdi, rdx
0x1800567ed  mov     rbx, rcx
0x1800567f0  mov     [rsp+1A8h+ppFactory], 0
0x1800567f9  add     rcx, 18h
0x1800567fd  call    ?Create@VersionedDXCoreAdapterFactory@@SAJAEAV?$shared_ptr@VVersionedDXCoreAdapterFactory@@@std@@@Z; VersionedDXCoreAdapterFactory::Create(std::shared_ptr<VersionedDXCoreAdapterFactory> &)
0x180056802  test    eax, eax
0x180056804  js      loc_180056906
0x18005680a  test    rdi, rdi
0x18005680d  jz      short loc_180056847
0x18005680f  lea     rdx, [rbx+28h]
0x180056813  mov     rcx, rdi
0x180056816  call    ?CreateFromIDXCoreAdapter@VersionedDXCoreAdapter@@SAJPEAUIUnknown@@AEAV?$shared_ptr@VVersionedDXCoreAdapter@@@std@@@Z; VersionedDXCoreAdapter::CreateFromIDXCoreAdapter(IUnknown *,std::shared_ptr<VersionedDXCoreAdapter> &)
0x18005681b  test    eax, eax
0x18005681d  js      short loc_180056847
0x18005681f  mov     rax, [rbx+28h]
0x180056823  mov     rcx, [rax]
0x180056826  test    rcx, rcx
0x180056829  jnz     loc_180056960
0x18005682f  mov     rcx, [rax+8]
0x180056833  mov     rax, [rcx]
0x180056836  mov     rdx, rbx
0x180056839  mov     rax, [rax+30h]
0x18005683d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056842  jmp     loc_180056975
0x180056847  cmp     [rsp+1A8h+ppFactory], 0
0x18005684d  jnz     loc_180056959
0x180056853  lea     r8, [rsp+1A8h+ppFactory]; ppFactory
0x180056858  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x18005685f  mov     ecx, 80000000h; Flags
0x180056864  call    cs:__imp_CreateDXGIFactory2
0x18005686a  mov     ecx, eax; int
0x18005686c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180056871  mov     [rsp+1A8h+var_170], 0
0x18005687a  lea     r8, [rsp+1A8h+var_170]
0x18005687f  test    rdi, rdi
0x180056882  jz      loc_18005697E
0x180056888  mov     rax, [rdi]
0x18005688b  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180056892  mov     rcx, rdi
0x180056895  mov     rax, [rax]
0x180056898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005689d  mov     ecx, eax; int
0x18005689f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800568a4  xor     edx, edx; Val
0x1800568a6  mov     r8d, 130h; Size
0x1800568ac  lea     rcx, [rsp+1A8h+var_158]; void *
0x1800568b1  call    memset_0
0x1800568b6  mov     rcx, [rsp+1A8h+var_170]
0x1800568bb  mov     rax, [rcx]
0x1800568be  lea     rdx, [rsp+1A8h+var_158]
0x1800568c3  mov     rax, [rax+40h]
0x1800568c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568cc  mov     ecx, eax; int
0x1800568ce  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800568d3  mov     rax, [rsp+1A8h+var_30]
0x1800568db  mov     [rbx], rax
0x1800568de  lea     r8, [rbx+28h]
0x1800568e2  mov     rdx, rbx
0x1800568e5  mov     rcx, [rbx+18h]
0x1800568e9  call    ?CreateAdapterFromLUID@VersionedDXCoreAdapterFactory@@QEAAXAEBU_LUID@@AEAV?$shared_ptr@VVersionedDXCoreAdapter@@@std@@@Z; VersionedDXCoreAdapterFactory::CreateAdapterFromLUID(_LUID const &,std::shared_ptr<VersionedDXCoreAdapter> &)
0x1800568ee  nop
0x1800568ef  mov     rcx, [rsp+1A8h+var_170]
0x1800568f4  test    rcx, rcx
0x1800568f7  jz      short loc_180056906
0x1800568f9  mov     rax, [rcx]
0x1800568fc  mov     rax, [rax+10h]
0x180056900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056905  nop
0x180056906  cmp     qword ptr [rbx+28h], 0
0x18005690b  jz      short loc_18005694A
0x18005690d  mov     rcx, [rsp+1A8h+ppFactory]
0x180056912  test    rcx, rcx
0x180056915  jz      short loc_180056924
0x180056917  mov     rax, [rcx]
0x18005691a  mov     rax, [rax+10h]
0x18005691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056923  nop
0x180056924  xor     eax, eax
0x180056926  mov     rcx, [rsp+1A8h+var_28]
0x18005692e  xor     rcx, rsp; StackCookie
0x180056931  call    __security_check_cookie
0x180056936  mov     rbx, [rsp+1A8h+arg_10]
0x18005693e  add     rsp, 190h
0x180056945  pop     r14
0x180056947  pop     rdi
0x180056948  pop     rsi
0x180056949  retn
0x18005694a  cmp     [rsp+1A8h+ppFactory], 0
0x180056950  jz      short loc_18005699D
0x180056952  xor     eax, eax
0x180056954  jmp     loc_180235398
0x180056959  xor     eax, eax
0x18005695b  jmp     loc_18005686A
0x180056960  mov     rax, [rcx]
0x180056963  mov     r9, rbx
0x180056966  xor     edx, edx
0x180056968  lea     r8d, [rdx+8]
0x18005696c  mov     rax, [rax+30h]
0x180056970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056975  mov     ecx, eax; int
0x180056977  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005697c  jmp     short loc_180056906
0x18005697e  mov     rcx, [rsp+1A8h+ppFactory]
0x180056983  mov     rax, [rcx]
0x180056986  xor     edx, edx
0x180056988  mov     rax, [rax+38h]
0x18005698c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056991  mov     ecx, eax; int
0x180056993  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180056998  jmp     loc_1800568A4
0x18005699d  lea     r8, [rsp+1A8h+ppFactory]; ppFactory
0x1800569a2  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x1800569a9  mov     ecx, 80000000h; Flags
0x1800569ae  call    cs:__imp_CreateDXGIFactory2
0x1800569b4  nop
0x1800569b5  jmp     loc_180235398
0x1800569ba  mov     eax, 8007000Eh
0x1800569bf  jmp     loc_180056926
0x1800569c4  mov     eax, 887A0004h
0x1800569c9  jmp     loc_180056926
0x180235398  mov     ecx, eax; int
0x18023539a  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18023539f  lea     rsi, [rbx+10h]
0x1802353a3  mov     r8, rsi
0x1802353a6  test    rdi, rdi
0x1802353a9  jz      loc_18023544C
0x1802353af  mov     rax, [rdi]
0x1802353b2  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x1802353b9  mov     rcx, rdi
0x1802353bc  mov     rax, [rax]
0x1802353bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802353c4  test    eax, eax
0x1802353c6  jns     loc_180235466
0x1802353cc  mov     [rsp+1A8h+var_170], 0
0x1802353d5  mov     rax, [rdi]
0x1802353d8  lea     r8, [rsp+1A8h+var_170]
0x1802353dd  lea     rdx, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x1802353e4  mov     rcx, rdi
0x1802353e7  mov     rax, [rax]
0x1802353ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802353ef  mov     ecx, eax; int
0x1802353f1  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1802353f6  mov     rcx, [rsp+1A8h+var_170]
0x1802353fb  mov     rax, [rcx]
0x1802353fe  mov     r9, rbx
0x180235401  xor     edx, edx
0x180235403  lea     r8d, [rdx+8]
0x180235407  mov     rax, [rax+30h]
0x18023540b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235410  mov     ecx, eax; int
0x180235412  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180235417  mov     rcx, [rsp+1A8h+ppFactory]
0x18023541c  mov     rax, [rcx]
0x18023541f  mov     r9, rsi
0x180235422  lea     r8, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180235429  mov     rdx, [rbx]
0x18023542c  mov     rax, [rax+0D0h]
0x180235433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235438  mov     ecx, eax; int
0x18023543a  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18023543f  nop
0x180235440  lea     rcx, [rsp+1A8h+var_170]
0x180235445  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18023544a  jmp     short loc_18023549E
0x18023544c  mov     rcx, [rsp+1A8h+ppFactory]
0x180235451  mov     rax, [rcx]
0x180235454  xor     edx, edx
0x180235456  mov     rax, [rax+38h]
0x18023545a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023545f  mov     ecx, eax; int
0x180235461  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180235466  xor     edx, edx; Val
0x180235468  mov     r8d, 130h; Size
0x18023546e  lea     rcx, [rsp+1A8h+var_158]; void *
0x180235473  call    memset_0
0x180235478  mov     rcx, [rsi]
0x18023547b  mov     rax, [rcx]
0x18023547e  lea     rdx, [rsp+1A8h+var_158]
0x180235483  mov     rax, [rax+40h]
0x180235487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023548c  mov     ecx, eax; int
0x18023548e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180235493  mov     rax, [rsp+1A8h+var_30]
0x18023549b  mov     [rbx], rax
0x18023549e  mov     rcx, [rsi]
0x1802354a1  mov     rax, [rcx]
0x1802354a4  lea     r8, [rbx+8]
0x1802354a8  lea     rdx, _GUID_7abb6563_02bc_47c4_8ef9_acc4795edbcf
0x1802354af  mov     rax, [rax]
0x1802354b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802354b7  mov     ecx, eax; int
0x1802354b9  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1802354be  nop
0x1802354bf  jmp     loc_18005690D
```
