# CPhotoPropertyStore::Initialize(IStream *,ulong)

- ea: `0x180005080`
- end: `0x1800053b4`
- name: `?Initialize@CPhotoPropertyStore@@UEAAJPEAUIStream@@K@Z`
- size: `820`
- prototype: `__int64 __fastcall(CPhotoPropertyStore *this, struct IStream *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004fc0`
- `0x180005080`
- `0x1800053bc`
- `0x1800053ec`
- `0x180005440`
- `0x180005470`
- `0x18001186c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000527d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000527d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005147`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005147`

## pseudocode

```c
__int64 __fastcall CPhotoPropertyStore::Initialize(CPhotoPropertyStore *this, struct IStream *a2, unsigned int a3)
{
  unsigned int v3; // r12d
  CPhotoPropertyStore *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r15
  const struct _GUID *v7; // rcx
  unsigned __int64 v8; // r8
  _DWORD *v9; // r14
  struct IStream **v10; // rbx
  HRESULT v11; // esi
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
    if ( ((int (__fastcall *)(struct IWICBitmapDecoder *, char *))v14->lpVtbl->GetContainerFormat)(
           v14,
           (char *)v5 + 156) >= 0 )
    {
      *((_DWORD *)v5 + 43) = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        *((_DWORD *)v5 + 43) = CContainerMasks::LookupContainerMask((const struct _GUID *)((char *)v5 + 156));
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', 0) )
        {
          *((_DWORD *)this + 43) = 0;
          v5 = this;
          v3 = a3;
          v6 = v21;
          v9 = v22;
          v10 = v18;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000537A);
        }
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
0x180005080  mov     [rsp+arg_10], r8d
0x180005085  mov     [rsp+arg_0], rcx
0x18000508a  push    rbx
0x18000508b  push    rsi
0x18000508c  push    rdi
0x18000508d  push    r12
0x18000508f  push    r13
0x180005091  push    r14
0x180005093  push    r15
0x180005095  sub     rsp, 50h
0x180005099  mov     r12d, r8d
0x18000509c  mov     rsi, rdx
0x18000509f  mov     rdi, rcx
0x1800050a2  xor     r13d, r13d
0x1800050a5  mov     [rsp+88h+var_50], r13
0x1800050aa  lea     r15, [rcx+60h]
0x1800050ae  mov     [rsp+88h+var_48], r15
0x1800050b3  mov     rcx, r15; lpCriticalSection
0x1800050b6  call    cs:__imp_EnterCriticalSection
0x1800050bd  nop     dword ptr [rax+rax+00h]
0x1800050c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800050c9  mov     r8, [rax+38h]; unsigned __int64
0x1800050cd  test    r8, r8
0x1800050d0  jnz     loc_18000535E
0x1800050d6  lea     r14, [rdi+0B0h]
0x1800050dd  mov     [rsp+88h+var_40], r14
0x1800050e2  lea     rbx, [rdi+88h]
0x1800050e9  cmp     dword ptr [r14], 0
0x1800050ed  jnz     loc_180005370
0x1800050f3  cmp     [rbx], rsi
0x1800050f6  jz      short loc_18000511B
0x1800050f8  test    rsi, rsi
0x1800050fb  jz      short loc_18000510C
0x1800050fd  mov     rax, [rsi]
0x180005100  mov     rcx, rsi
0x180005103  mov     rax, [rax+8]
0x180005107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510c  mov     rcx, [rbx]
0x18000510f  test    rcx, rcx
0x180005112  jnz     loc_180005331
0x180005118  mov     [rbx], rsi
0x18000511b  mov     [rsp+88h+var_58], rbx
0x180005120  mov     [rdi+98h], r12d
0x180005127  lea     rax, [rsp+88h+var_50]
0x18000512c  mov     [rsp+88h+ppv], rax; ppv
0x180005131  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005138  xor     edx, edx; pUnkOuter
0x18000513a  mov     r8d, 1; dwClsContext
0x180005140  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005147  call    cs:__imp_CoCreateInstance
0x18000514e  nop     dword ptr [rax+rax+00h]
0x180005153  mov     esi, eax
0x180005155  test    eax, eax
0x180005157  jns     loc_1800052B4
0x18000515d  mov     rcx, rbx
0x180005160  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x180005165  lea     rcx, [rdi+90h]
0x18000516c  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x180005171  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180005178  movups  xmmword ptr [rdi+9Ch], xmm0
0x18000517f  mov     [rdi+0ACh], r13d
0x180005186  mov     [rdi+98h], r13d
0x18000518d  lea     rcx, [rdi+0C8h]; this
0x180005194  call    ?Uninitialize@CMetadataContainer@@QEAAJXZ; CMetadataContainer::Uninitialize(void)
0x180005199  mov     [r14], r13d
0x18000519c  mov     eax, 80004005h
0x1800051a1  test    esi, esi
0x1800051a3  cmovns  esi, eax
0x1800051a6  jmp     loc_180005266
0x1800051ab  mov     rsi, rcx
0x1800051ae  test    rcx, rcx
0x1800051b1  jz      short loc_1800051C7
0x1800051b3  mov     rax, [rcx]
0x1800051b6  mov     rax, [rax+8]
0x1800051ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bf  mov     rcx, [rsp+88h+arg_18]
0x1800051c7  mov     rdx, [rdi+90h]
0x1800051ce  test    rdx, rdx
0x1800051d1  jnz     loc_180005342
0x1800051d7  mov     [rdi+90h], rsi
0x1800051de  mov     [rsp+88h+var_58], rbx
0x1800051e3  mov     rax, [rcx]
0x1800051e6  lea     rdx, [rdi+9Ch]
0x1800051ed  mov     rax, [rax+28h]
0x1800051f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f6  test    eax, eax
0x1800051f8  js      short loc_180005213
0x1800051fa  mov     [rdi+0ACh], r13d
0x180005201  lea     rcx, [rdi+9Ch]; struct _GUID *
0x180005208  call    ?LookupContainerMask@CContainerMasks@@SAKAEBU_GUID@@@Z; CContainerMasks::LookupContainerMask(_GUID const &)
0x18000520d  mov     [rdi+0ACh], eax
0x180005213  lea     rcx, [rdi+0C8h]; this
0x18000521a  mov     r9, [rsp+88h+arg_18]; struct IWICBitmapDecoder *
0x180005222  mov     r8d, r12d; unsigned int
0x180005225  mov     rdx, [rbx]; struct IStream *
0x180005228  call    ?Initialize@CMetadataContainer@@QEAAJPEAUIStream@@KPEAUIWICBitmapDecoder@@@Z; CMetadataContainer::Initialize(IStream *,ulong,IWICBitmapDecoder *)
0x18000522d  mov     esi, eax
0x18000522f  test    eax, eax
0x180005231  js      short loc_18000523A
0x180005233  mov     dword ptr [r14], 1
0x18000523a  mov     rcx, [rsp+88h+arg_18]
0x180005242  test    rcx, rcx
0x180005245  jz      short loc_180005254
0x180005247  mov     rax, [rcx]
0x18000524a  mov     rax, [rax+10h]
0x18000524e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005253  nop
0x180005254  test    esi, esi
0x180005256  js      loc_18000515D
0x18000525c  cmp     dword ptr [r14], 0
0x180005260  jz      loc_18000515D
0x180005266  mov     rax, cs:WPP_GLOBAL_Control
0x18000526d  mov     r8, [rax+38h]; unsigned __int64
0x180005271  test    r8, r8
0x180005274  jnz     loc_1800053A1
0x18000527a  mov     rcx, r15; lpCriticalSection
0x18000527d  call    cs:__imp_LeaveCriticalSection
0x180005284  nop     dword ptr [rax+rax+00h]
0x180005289  nop
0x18000528a  mov     rcx, [rsp+88h+var_50]
0x18000528f  test    rcx, rcx
0x180005292  jz      short loc_1800052A1
0x180005294  mov     rax, [rcx]
0x180005297  mov     rax, [rax+10h]
0x18000529b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a0  nop
0x1800052a1  mov     eax, esi
0x1800052a3  add     rsp, 50h
0x1800052a7  pop     r15
0x1800052a9  pop     r14
0x1800052ab  pop     r13
0x1800052ad  pop     r12
0x1800052af  pop     rdi
0x1800052b0  pop     rsi
0x1800052b1  pop     rbx
0x1800052b2  retn
0x1800052b4  mov     [rsp+88h+arg_18], r13
0x1800052bc  mov     rcx, [rbx]
0x1800052bf  mov     rax, [rcx]
0x1800052c2  xor     r9d, r9d
0x1800052c5  xor     r8d, r8d
0x1800052c8  mov     rdx, r13
0x1800052cb  mov     rax, [rax+28h]
0x1800052cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d4  mov     esi, eax
0x1800052d6  test    eax, eax
0x1800052d8  js      loc_18000515D
0x1800052de  mov     [rsp+88h+arg_18], r13
0x1800052e6  mov     rcx, [rsp+88h+var_50]
0x1800052eb  mov     rax, [rcx]
0x1800052ee  lea     rdx, [rsp+88h+arg_18]
0x1800052f6  mov     [rsp+88h+ppv], rdx
0x1800052fb  xor     r9d, r9d
0x1800052fe  xor     r8d, r8d
0x180005301  mov     rdx, [rbx]
0x180005304  mov     rax, [rax+20h]
0x180005308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000530d  mov     esi, eax
0x18000530f  test    eax, eax
0x180005311  js      loc_18000523A
0x180005317  mov     rcx, [rsp+88h+arg_18]
0x18000531f  cmp     [rdi+90h], rcx
0x180005326  jnz     loc_1800051AB
0x18000532c  jmp     loc_1800051E3
0x180005331  mov     rax, [rcx]
0x180005334  mov     rax, [rax+10h]
0x180005338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533d  jmp     loc_180005118
0x180005342  mov     rax, [rdx]
0x180005345  mov     rcx, rdx
0x180005348  mov     rax, [rax+10h]
0x18000534c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005351  mov     rcx, [rsp+88h+arg_18]
0x180005359  jmp     loc_1800051D7
0x18000535e  mov     r9b, 1; unsigned __int8
0x180005361  mov     edx, 2; unsigned int
0x180005366  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000536b  jmp     loc_1800050D6
0x180005370  mov     esi, 800704DFh
0x180005375  jmp     loc_18000515D
0x18000537a  xor     r13d, r13d
0x18000537d  mov     rdi, [rsp+88h+arg_0]
0x180005385  mov     r12d, [rsp+88h+arg_10]
0x18000538d  mov     r15, [rsp+88h+var_48]
0x180005392  mov     r14, [rsp+88h+var_40]
0x180005397  mov     rbx, [rsp+88h+var_58]
0x18000539c  jmp     loc_180005213
0x1800053a1  mov     r9b, 2; unsigned __int8
0x1800053a4  mov     edx, 2; unsigned int
0x1800053a9  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800053ae  jmp     loc_18000527A
```
