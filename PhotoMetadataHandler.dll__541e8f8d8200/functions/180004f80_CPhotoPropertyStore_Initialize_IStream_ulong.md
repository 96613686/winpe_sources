# CPhotoPropertyStore::Initialize(IStream *,ulong)

- ea: `0x180004f80`
- end: `0x1800052a1`
- name: `?Initialize@CPhotoPropertyStore@@UEAAJPEAUIStream@@K@Z`
- size: `801`
- prototype: `int(CPhotoPropertyStore *__hidden this, struct IStream *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004d50`
- `0x180004f80`
- `0x1800052a8`
- `0x1800052d8`
- `0x180005328`
- `0x180005360`
- `0x1800110b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005171`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004fb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005041`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005041`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPhotoPropertyStore::Initialize(CPhotoPropertyStore *this, struct IStream *a2, int a3)
{
  int v3; // r12d
  CPhotoPropertyStore *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r15
  const struct _GUID *v7; // rcx
  unsigned __int64 v8; // r8
  _DWORD *v9; // r14
  struct IStream **v10; // rbx
  int v11; // esi
  struct IWICBitmapDecoder *v12; // rcx
  struct IWICBitmapDecoder *v13; // rsi
  struct IWICBitmapDecoder *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  struct IStream **v18; // [rsp+30h] [rbp-58h]
  LPVOID ppv; // [rsp+38h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+40h] [rbp-48h]
  _DWORD *v22; // [rsp+48h] [rbp-40h]
  struct IWICBitmapDecoder *v27; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a3;
  v5 = this;
  ppv = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v21 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v8 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v8 )
    ShellPrivateTraceEvent(v7, 2u, v8, 1u);
  v9 = (_DWORD *)((char *)v5 + 176);
  v22 = (_DWORD *)((char *)v5 + 176);
  v10 = (struct IStream **)((char *)v5 + 136);
  if ( *((_DWORD *)v5 + 44) )
  {
    v11 = -2147023649;
LABEL_11:
    ATL::CComPtrBase<IStream>::Release(v10);
    ATL::CComPtrBase<IWICComponentFactory>::Release((char *)v5 + 144);
    *(GUID *)((char *)v5 + 156) = GUID_NULL;
    *((_DWORD *)v5 + 43) = 0;
    *((_DWORD *)v5 + 38) = 0;
    CMetadataContainer::Uninitialize((CPhotoPropertyStore *)((char *)v5 + 200));
    *v9 = 0;
    if ( v11 >= 0 )
      v11 = -2147467259;
    goto LABEL_27;
  }
  if ( *v10 != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
    if ( *v10 )
      ((void (__fastcall *)(struct IStream *))(*v10)->lpVtbl->Release)(*v10);
    *v10 = a2;
  }
  v18 = (struct IStream **)((char *)v5 + 136);
  *((_DWORD *)v5 + 38) = v3;
  v11 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v11 < 0 )
    goto LABEL_11;
  v27 = 0;
  v11 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))(*v10)->lpVtbl->Seek)(*v10, 0, 0, 0);
  if ( v11 < 0 )
    goto LABEL_11;
  v27 = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, _QWORD, _QWORD, struct IWICBitmapDecoder **))(*(_QWORD *)ppv + 32LL))(
          ppv,
          *v10,
          0,
          0,
          &v27);
  if ( v11 >= 0 )
  {
    v14 = v27;
    if ( *((struct IWICBitmapDecoder **)v5 + 18) != v27 )
    {
      v13 = v27;
      if ( v27 )
      {
        ((void (*)(void))v27->lpVtbl->AddRef)();
        v14 = v27;
      }
      v15 = *((_QWORD *)v5 + 18);
      if ( v15 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(*((_QWORD *)v5 + 18));
        v14 = v27;
      }
      *((_QWORD *)v5 + 18) = v13;
      v18 = (struct IStream **)((char *)v5 + 136);
    }
    if ( ((int (__fastcall *)(struct IWICBitmapDecoder *, __int64))v14->lpVtbl->GetContainerFormat)(
           v14,
           (__int64)v5 + 156) >= 0 )
    {
      *((_DWORD *)v5 + 43) = 0;
      try
      {
        *((_DWORD *)v5 + 43) = CContainerMasks::LookupContainerMask((const struct _GUID *)((char *)v5 + 156));
      }
      catch ( ATL::CAtlException )
      {
        *((_DWORD *)this + 43) = 0;
        v5 = this;
        v3 = a3;
        v6 = v21;
        v9 = v22;
        v10 = v18;
      }
    }
    v11 = CMetadataContainer::Initialize((CPhotoPropertyStore *)((char *)v5 + 200), *v10, v3, v27);
    if ( v11 >= 0 )
      *v9 = 1;
  }
  v12 = v27;
  if ( v27 )
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v27->lpVtbl->Release)(v27);
  if ( v11 < 0 || !*v9 )
    goto LABEL_11;
LABEL_27:
  v16 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v16 )
    ShellPrivateTraceEvent((const struct _GUID *)v12, 2u, v16, 2u);
  LeaveCriticalSection(v6);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004f80  mov     [rsp+arg_10], r8d
0x180004f85  mov     [rsp+arg_0], rcx
0x180004f8a  push    rbx
0x180004f8b  push    rsi
0x180004f8c  push    rdi
0x180004f8d  push    r12
0x180004f8f  push    r13
0x180004f91  push    r14
0x180004f93  push    r15
0x180004f95  sub     rsp, 50h
0x180004f99  mov     r12d, r8d
0x180004f9c  mov     rsi, rdx
0x180004f9f  mov     rdi, rcx
0x180004fa2  xor     r13d, r13d
0x180004fa5  mov     [rsp+88h+var_50], r13
0x180004faa  lea     r15, [rcx+60h]
0x180004fae  mov     [rsp+88h+var_48], r15
0x180004fb3  mov     rcx, r15; lpCriticalSection
0x180004fb6  call    cs:__imp_EnterCriticalSection
0x180004fbc  mov     rax, cs:WPP_GLOBAL_Control
0x180004fc3  mov     r8, [rax+38h]; unsigned __int64
0x180004fc7  test    r8, r8
0x180004fca  jnz     loc_18000524B
0x180004fd0  lea     r14, [rdi+0B0h]
0x180004fd7  mov     [rsp+88h+var_40], r14
0x180004fdc  lea     rbx, [rdi+88h]
0x180004fe3  cmp     dword ptr [r14], 0
0x180004fe7  jnz     loc_18000525D
0x180004fed  cmp     [rbx], rsi
0x180004ff0  jz      short loc_180005015
0x180004ff2  test    rsi, rsi
0x180004ff5  jz      short loc_180005006
0x180004ff7  mov     rax, [rsi]
0x180004ffa  mov     rcx, rsi
0x180004ffd  mov     rax, [rax+8]
0x180005001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005006  mov     rcx, [rbx]
0x180005009  test    rcx, rcx
0x18000500c  jnz     loc_18000521E
0x180005012  mov     [rbx], rsi
0x180005015  mov     [rsp+88h+var_58], rbx
0x18000501a  mov     [rdi+98h], r12d
0x180005021  lea     rax, [rsp+88h+var_50]
0x180005026  mov     [rsp+88h+ppv], rax; ppv
0x18000502b  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005032  xor     edx, edx; pUnkOuter
0x180005034  mov     r8d, 1; dwClsContext
0x18000503a  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005041  call    cs:__imp_CoCreateInstance
0x180005047  mov     esi, eax
0x180005049  test    eax, eax
0x18000504b  jns     loc_1800051A1
0x180005051  mov     rcx, rbx
0x180005054  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x180005059  lea     rcx, [rdi+90h]
0x180005060  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x180005065  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000506c  movups  xmmword ptr [rdi+9Ch], xmm0
0x180005073  mov     [rdi+0ACh], r13d
0x18000507a  mov     [rdi+98h], r13d
0x180005081  lea     rcx, [rdi+0C8h]; this
0x180005088  call    ?Uninitialize@CMetadataContainer@@QEAAJXZ; CMetadataContainer::Uninitialize(void)
0x18000508d  mov     [r14], r13d
0x180005090  mov     eax, 80004005h
0x180005095  test    esi, esi
0x180005097  cmovns  esi, eax
0x18000509a  jmp     loc_18000515A
0x18000509f  mov     rsi, rcx
0x1800050a2  test    rcx, rcx
0x1800050a5  jz      short loc_1800050BB
0x1800050a7  mov     rax, [rcx]
0x1800050aa  mov     rax, [rax+8]
0x1800050ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b3  mov     rcx, [rsp+88h+arg_18]
0x1800050bb  mov     rdx, [rdi+90h]
0x1800050c2  test    rdx, rdx
0x1800050c5  jnz     loc_18000522F
0x1800050cb  mov     [rdi+90h], rsi
0x1800050d2  mov     [rsp+88h+var_58], rbx
0x1800050d7  mov     rax, [rcx]
0x1800050da  lea     rdx, [rdi+9Ch]
0x1800050e1  mov     rax, [rax+28h]
0x1800050e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ea  test    eax, eax
0x1800050ec  js      short loc_180005107
0x1800050ee  mov     [rdi+0ACh], r13d
0x1800050f5  lea     rcx, [rdi+9Ch]; struct _GUID *
0x1800050fc  call    ?LookupContainerMask@CContainerMasks@@SAKAEBU_GUID@@@Z; CContainerMasks::LookupContainerMask(_GUID const &)
0x180005101  mov     [rdi+0ACh], eax
0x180005107  lea     rcx, [rdi+0C8h]; this
0x18000510e  mov     r9, [rsp+88h+arg_18]; struct IWICBitmapDecoder *
0x180005116  mov     r8d, r12d; unsigned int
0x180005119  mov     rdx, [rbx]; struct IStream *
0x18000511c  call    ?Initialize@CMetadataContainer@@QEAAJPEAUIStream@@KPEAUIWICBitmapDecoder@@@Z; CMetadataContainer::Initialize(IStream *,ulong,IWICBitmapDecoder *)
0x180005121  mov     esi, eax
0x180005123  test    eax, eax
0x180005125  js      short loc_18000512E
0x180005127  mov     dword ptr [r14], 1
0x18000512e  mov     rcx, [rsp+88h+arg_18]
0x180005136  test    rcx, rcx
0x180005139  jz      short loc_180005148
0x18000513b  mov     rax, [rcx]
0x18000513e  mov     rax, [rax+10h]
0x180005142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005147  nop
0x180005148  test    esi, esi
0x18000514a  js      loc_180005051
0x180005150  cmp     dword ptr [r14], 0
0x180005154  jz      loc_180005051
0x18000515a  mov     rax, cs:WPP_GLOBAL_Control
0x180005161  mov     r8, [rax+38h]; unsigned __int64
0x180005165  test    r8, r8
0x180005168  jnz     loc_18000528E
0x18000516e  mov     rcx, r15; lpCriticalSection
0x180005171  call    cs:__imp_LeaveCriticalSection
0x180005177  nop
0x180005178  mov     rcx, [rsp+88h+var_50]
0x18000517d  test    rcx, rcx
0x180005180  jz      short loc_18000518F
0x180005182  mov     rax, [rcx]
0x180005185  mov     rax, [rax+10h]
0x180005189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518e  nop
0x18000518f  mov     eax, esi
0x180005191  add     rsp, 50h
0x180005195  pop     r15
0x180005197  pop     r14
0x180005199  pop     r13
0x18000519b  pop     r12
0x18000519d  pop     rdi
0x18000519e  pop     rsi
0x18000519f  pop     rbx
0x1800051a0  retn
0x1800051a1  mov     [rsp+88h+arg_18], r13
0x1800051a9  mov     rcx, [rbx]
0x1800051ac  mov     rax, [rcx]
0x1800051af  xor     r9d, r9d
0x1800051b2  xor     r8d, r8d
0x1800051b5  mov     rdx, r13
0x1800051b8  mov     rax, [rax+28h]
0x1800051bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c1  mov     esi, eax
0x1800051c3  test    eax, eax
0x1800051c5  js      loc_180005051
0x1800051cb  mov     [rsp+88h+arg_18], r13
0x1800051d3  mov     rcx, [rsp+88h+var_50]
0x1800051d8  mov     rax, [rcx]
0x1800051db  lea     rdx, [rsp+88h+arg_18]
0x1800051e3  mov     [rsp+88h+ppv], rdx
0x1800051e8  xor     r9d, r9d
0x1800051eb  xor     r8d, r8d
0x1800051ee  mov     rdx, [rbx]
0x1800051f1  mov     rax, [rax+20h]
0x1800051f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051fa  mov     esi, eax
0x1800051fc  test    eax, eax
0x1800051fe  js      loc_18000512E
0x180005204  mov     rcx, [rsp+88h+arg_18]
0x18000520c  cmp     [rdi+90h], rcx
0x180005213  jnz     loc_18000509F
0x180005219  jmp     loc_1800050D7
0x18000521e  mov     rax, [rcx]
0x180005221  mov     rax, [rax+10h]
0x180005225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522a  jmp     loc_180005012
0x18000522f  mov     rax, [rdx]
0x180005232  mov     rcx, rdx
0x180005235  mov     rax, [rax+10h]
0x180005239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523e  mov     rcx, [rsp+88h+arg_18]
0x180005246  jmp     loc_1800050CB
0x18000524b  mov     r9b, 1; unsigned __int8
0x18000524e  mov     edx, 2; unsigned int
0x180005253  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180005258  jmp     loc_180004FD0
0x18000525d  mov     esi, 800704DFh
0x180005262  jmp     loc_180005051
0x180005267  xor     r13d, r13d
0x18000526a  mov     rdi, [rsp+88h+arg_0]
0x180005272  mov     r12d, [rsp+88h+arg_10]
0x18000527a  mov     r15, [rsp+88h+var_48]
0x18000527f  mov     r14, [rsp+88h+var_40]
0x180005284  mov     rbx, [rsp+88h+var_58]
0x180005289  jmp     loc_180005107
0x18000528e  mov     r9b, 2; unsigned __int8
0x180005291  mov     edx, 2; unsigned int
0x180005296  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000529b  jmp     loc_18000516E
```
