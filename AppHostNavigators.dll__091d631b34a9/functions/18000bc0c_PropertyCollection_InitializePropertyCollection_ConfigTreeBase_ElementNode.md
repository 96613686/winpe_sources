# PropertyCollection::InitializePropertyCollection(ConfigTreeBase *,ElementNode *)

- ea: `0x18000bc0c`
- end: `0x18000beb8`
- name: `?InitializePropertyCollection@PropertyCollection@@AEAAXPEAVConfigTreeBase@@PEAVElementNode@@@Z`
- size: `684`
- prototype: `void(PropertyCollection *__hidden this, struct ConfigTreeBase *, struct ElementNode *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b2e8`

## callees

- `0x180001194`
- `0x1800021a4`
- `0x18000573c`
- `0x180007aac`
- `0x18000a60c`
- `0x18000a72c`
- `0x18000bc0c`
- `0x18000dc48`
- `0x180011240`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000bd15`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd15`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PropertyCollection::InitializePropertyCollection(
        PropertyCollection *this,
        ConfigSystemContext **a2,
        struct IUnknown *a3)
{
  bool v6; // bl
  int v7; // eax
  int v8; // eax
  struct IUnknown **v9; // r14
  unsigned int i; // esi
  __int64 v11; // rax
  int v12; // ebx
  struct IUnknown **v13; // rax
  struct IUnknown **v14; // rdi
  struct IUnknown *v15; // rbx
  int v16; // eax
  struct IUnknown *v17; // [rsp+20h] [rbp-60h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-58h] BYREF
  __int64 v19; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown **v21; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v23; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+D0h] [rbp+50h] BYREF
  struct IUnknown **pExceptionObject; // [rsp+D8h] [rbp+58h] BYREF

  v19 = 0;
  ((void (__fastcall *)(struct IUnknown *, ConfigSystemContext **, __int64 *))a3->lpVtbl[4].Release)(a3, a2, &v19);
  v6 = Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(&v19);
  v18 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v19 + 40LL))(v19, &v18);
  if ( v7 < 0 && !v6 )
  {
    LODWORD(pExceptionObject) = v7;
    throw (long *)&pExceptionObject;
  }
  if ( v18 )
  {
    v24 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v18 + 24))(v18, &v24);
    if ( v8 < 0 )
    {
      LODWORD(pExceptionObject) = v8;
      throw (long *)&pExceptionObject;
    }
    v9 = 0;
    for ( i = 0; i < v24; ++i )
    {
      v17 = 0;
      v11 = *v18;
      pvarg.vt = 19;
      pvarg.lVal = i;
      v23 = pvarg;
      v12 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IUnknown **))(v11 + 32))(v18, &v23, &v17);
      VariantClear(&pvarg);
      if ( v12 < 0 )
      {
        LODWORD(pExceptionObject) = v12;
        throw (long *)&pExceptionObject;
      }
      if ( (!Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(&v17)
         || !ConfigSystemContext::IsWritableConfigSystem(a2[3]))
        && (*((unsigned __int8 (__fastcall **)(ConfigSystemContext **, struct IUnknown *))*a2 + 3))(a2, v17) )
      {
        v13 = (struct IUnknown **)operator new(0x40u);
        v14 = v13;
        pExceptionObject = v13;
        if ( v13 )
        {
          *((_DWORD *)v13 + 2) = -1;
          *((_DWORD *)v13 + 3) = 0;
          v13[2] = 0;
          v13[3] = 0;
          *v13 = (struct IUnknown *)&PropertyNode::`vftable';
          v13[4] = 0;
          v13[5] = 0;
          v13[6] = 0;
          v13[7] = 0;
        }
        else
        {
          v14 = 0;
        }
        v21 = v14;
        if ( !v14 )
        {
          LODWORD(pExceptionObject) = -2147024882;
          throw (long *)&pExceptionObject;
        }
        v15 = v17;
        v20 = 0;
        v16 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 **))v17->lpVtbl[1].QueryInterface)(v17, &v20);
        if ( v16 < 0 )
        {
          LODWORD(pExceptionObject) = v16;
          throw (long *)&pExceptionObject;
        }
        NavigationNodeBase::Initialize((NavigationNodeBase *)v14, (struct NavigationTreeBase *)a2, v20);
        v14[7] = a3;
        if ( v14[5] != v15 )
          ATL::AtlComPtrAssign(v14 + 5, v15);
        ScopedBSTR::Reset((ScopedBSTR *)&v20);
        *((_DWORD *)v14 + 2) = i;
        if ( v9 )
        {
          ScopedPtr<PropertyNode>::Reset(v9 + 6);
          v9[6] = (struct IUnknown *)v14;
          v21 = 0;
        }
        else
        {
          v21 = 0;
          ScopedPtr<PropertyNode>::Reset(this);
          *(_QWORD *)this = v14;
        }
        ScopedPtr<PropertyNode>::Reset(&v21);
        v9 = v14;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
}

```

## disassembly

```asm
0x18000bc0c  mov     [rsp-38h+arg_0], rbx
0x18000bc11  push    rbp
0x18000bc12  push    rsi
0x18000bc13  push    rdi
0x18000bc14  push    r12
0x18000bc16  push    r13
0x18000bc18  push    r14
0x18000bc1a  push    r15
0x18000bc1c  mov     rbp, rsp
0x18000bc1f  sub     rsp, 80h
0x18000bc26  mov     r13, r8
0x18000bc29  mov     r15, rdx
0x18000bc2c  mov     r12, rcx
0x18000bc2f  mov     [rbp+var_50], 0
0x18000bc37  mov     rax, [r8]
0x18000bc3a  lea     r8, [rbp+var_50]
0x18000bc3e  mov     rcx, r13
0x18000bc41  mov     rax, [rax+70h]
0x18000bc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4a  lea     rcx, [rbp+var_50]
0x18000bc4e  call    ??$IsAppHostObjectBackedByExtension@UIAppHostElementSchema@@V?$CComPtr@UIAppHostElement@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostElement@@@ATL@@@Z; Helpers::IsAppHostObjectBackedByExtension<IAppHostElementSchema,ATL::CComPtr<IAppHostElement>>(ATL::CComPtr<IAppHostElement> &)
0x18000bc53  mov     bl, al
0x18000bc55  mov     [rbp+var_58], 0
0x18000bc5d  mov     rcx, [rbp+var_50]
0x18000bc61  mov     rdx, [rcx]
0x18000bc64  mov     rax, [rdx+28h]
0x18000bc68  lea     rdx, [rbp+var_58]
0x18000bc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc71  test    eax, eax
0x18000bc73  jns     short loc_18000BC8D
0x18000bc75  test    bl, bl
0x18000bc77  jnz     short loc_18000BC8D
0x18000bc79  mov     dword ptr [rbp+pExceptionObject], eax
0x18000bc7c  lea     rdx, _TI1J; pThrowInfo
0x18000bc83  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bc87  call    _CxxThrowException_0
0x18000bc8d  mov     rcx, [rbp+var_58]
0x18000bc91  xor     ebx, ebx
0x18000bc93  test    rcx, rcx
0x18000bc96  jz      loc_18000BE8A
0x18000bc9c  mov     [rbp+arg_10], ebx
0x18000bc9f  mov     rax, [rcx]
0x18000bca2  lea     rdx, [rbp+arg_10]
0x18000bca6  mov     rax, [rax+18h]
0x18000bcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcaf  test    eax, eax
0x18000bcb1  jns     short loc_18000BCC7
0x18000bcb3  mov     dword ptr [rbp+pExceptionObject], eax
0x18000bcb6  lea     rdx, _TI1J; pThrowInfo
0x18000bcbd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bcc1  call    _CxxThrowException_0
0x18000bcc7  mov     r14, rbx
0x18000bcca  mov     esi, ebx
0x18000bccc  cmp     esi, [rbp+arg_10]
0x18000bccf  jnb     loc_18000BE8A
0x18000bcd5  mov     [rbp+var_60], rbx
0x18000bcd9  mov     rcx, [rbp+var_58]
0x18000bcdd  mov     rax, [rcx]
0x18000bce0  mov     edx, 13h
0x18000bce5  mov     word ptr [rbp+pvarg], dx
0x18000bce9  mov     dword ptr [rbp+pvarg+8], esi
0x18000bcec  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000bcf0  movaps  [rbp+var_20], xmm0
0x18000bcf4  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000bcf9  movsd   [rbp+var_10], xmm1
0x18000bcfe  lea     r8, [rbp+var_60]
0x18000bd02  lea     rdx, [rbp+var_20]
0x18000bd06  mov     rax, [rax+20h]
0x18000bd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd0f  mov     ebx, eax
0x18000bd11  lea     rcx, [rbp+pvarg]; pvarg
0x18000bd15  call    cs:__imp_VariantClear
0x18000bd1b  test    ebx, ebx
0x18000bd1d  js      loc_18000BE76
0x18000bd23  lea     rcx, [rbp+var_60]
0x18000bd27  call    ??$IsAppHostObjectBackedByExtension@UIAppHostPropertySchema@@V?$CComPtr@UIAppHostProperty@@@ATL@@@Helpers@@SA_NAEAV?$CComPtr@UIAppHostProperty@@@ATL@@@Z; Helpers::IsAppHostObjectBackedByExtension<IAppHostPropertySchema,ATL::CComPtr<IAppHostProperty>>(ATL::CComPtr<IAppHostProperty> &)
0x18000bd2c  xor     ebx, ebx
0x18000bd2e  test    al, al
0x18000bd30  jz      short loc_18000BD44
0x18000bd32  mov     rcx, [r15+18h]; this
0x18000bd36  call    ?IsWritableConfigSystem@ConfigSystemContext@@QEAA_NXZ; ConfigSystemContext::IsWritableConfigSystem(void)
0x18000bd3b  test    al, al
0x18000bd3d  jz      short loc_18000BD44
0x18000bd3f  jmp     loc_18000BE3A
0x18000bd44  mov     rax, [r15]
0x18000bd47  mov     rdx, [rbp+var_60]
0x18000bd4b  mov     rcx, r15
0x18000bd4e  mov     rax, [rax+18h]
0x18000bd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd57  test    al, al
0x18000bd59  jz      short loc_18000BD3F
0x18000bd5b  mov     ecx, 40h ; '@'; Size
0x18000bd60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bd65  mov     rdi, rax
0x18000bd68  mov     [rbp+pExceptionObject], rax
0x18000bd6c  test    rax, rax
0x18000bd6f  jz      short loc_18000BD9F
0x18000bd71  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18000bd78  mov     [rax+0Ch], ebx
0x18000bd7b  mov     [rax+10h], rbx
0x18000bd7f  mov     [rax+18h], rbx
0x18000bd83  lea     rax, ??_7PropertyNode@@6B@; const PropertyNode::`vftable'
0x18000bd8a  mov     [rdi], rax
0x18000bd8d  mov     [rdi+20h], rbx
0x18000bd91  mov     [rdi+28h], rbx
0x18000bd95  mov     [rdi+30h], rbx
0x18000bd99  mov     [rdi+38h], rbx
0x18000bd9d  jmp     short loc_18000BDA2
0x18000bd9f  mov     rdi, rbx
0x18000bda2  mov     [rbp+var_40], rdi
0x18000bda6  test    rdi, rdi
0x18000bda9  jz      loc_18000BE5E
0x18000bdaf  mov     rbx, [rbp+var_60]
0x18000bdb3  mov     [rbp+var_48], 0
0x18000bdbb  mov     rax, [rbx]
0x18000bdbe  lea     rdx, [rbp+var_48]
0x18000bdc2  mov     rcx, rbx
0x18000bdc5  mov     rax, [rax+18h]
0x18000bdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdce  test    eax, eax
0x18000bdd0  js      short loc_18000BE4A
0x18000bdd2  mov     r8, [rbp+var_48]; unsigned __int16 *
0x18000bdd6  mov     rdx, r15; struct NavigationTreeBase *
0x18000bdd9  mov     rcx, rdi; this
0x18000bddc  call    ?Initialize@NavigationNodeBase@@IEAAXPEAVNavigationTreeBase@@PEBG@Z; NavigationNodeBase::Initialize(NavigationTreeBase *,ushort const *)
0x18000bde1  mov     [rdi+38h], r13
0x18000bde5  lea     rcx, [rdi+28h]; struct IUnknown **
0x18000bde9  cmp     [rcx], rbx
0x18000bdec  jz      short loc_18000BDF7
0x18000bdee  mov     rdx, rbx; struct IUnknown *
0x18000bdf1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000bdf6  nop
0x18000bdf7  lea     rcx, [rbp+var_48]; this
0x18000bdfb  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000be00  mov     [rdi+8], esi
0x18000be03  xor     ebx, ebx
0x18000be05  test    r14, r14
0x18000be08  jz      short loc_18000BE1D
0x18000be0a  lea     rcx, [r14+30h]
0x18000be0e  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000be13  mov     [r14+30h], rdi
0x18000be17  mov     [rbp+var_40], rbx
0x18000be1b  jmp     short loc_18000BE2D
0x18000be1d  mov     [rbp+var_40], rbx
0x18000be21  mov     rcx, r12
0x18000be24  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000be29  mov     [r12], rdi
0x18000be2d  lea     rcx, [rbp+var_40]
0x18000be31  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000be36  nop
0x18000be37  mov     r14, rdi
0x18000be3a  lea     rcx, [rbp+var_60]
0x18000be3e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be43  inc     esi
0x18000be45  jmp     loc_18000BCCC
0x18000be4a  mov     dword ptr [rbp+pExceptionObject], eax
0x18000be4d  lea     rdx, _TI1J; pThrowInfo
0x18000be54  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be58  call    _CxxThrowException_0
0x18000be5e  mov     dword ptr [rbp+pExceptionObject], 8007000Eh
0x18000be65  lea     rdx, _TI1J; pThrowInfo
0x18000be6c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be70  call    _CxxThrowException_0
0x18000be76  mov     dword ptr [rbp+pExceptionObject], ebx
0x18000be79  lea     rdx, _TI1J; pThrowInfo
0x18000be80  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be84  call    _CxxThrowException_0
0x18000be8a  lea     rcx, [rbp+var_58]
0x18000be8e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be93  nop
0x18000be94  lea     rcx, [rbp+var_50]
0x18000be98  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be9d  mov     rbx, [rsp+80h+arg_0]
0x18000bea5  add     rsp, 80h
0x18000beac  pop     r15
0x18000beae  pop     r14
0x18000beb0  pop     r13
0x18000beb2  pop     r12
0x18000beb4  pop     rdi
0x18000beb5  pop     rsi
0x18000beb6  pop     rbp
0x18000beb7  retn
```
