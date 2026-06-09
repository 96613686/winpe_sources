# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1400069fc`
- end: `0x140006c92`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400066c4`
- `0x140006e74`
- `0x140007438`

## callees

- `0x140003340`
- `0x140003418`
- `0x1400035c8`
- `0x140004e94`
- `0x1400069fc`
- `0x1400074dc`
- `0x1400076a0`
- `0x140007900`
- `0x14000c828`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140006ab9`
- `KERNEL32!GetModuleFileNameW` at `0x140006ab9`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140006ae2`
- `OLEAUT32!__imp_LoadTypeLib` at `0x140006ae2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140006b10`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140006b10`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rsi
  _QWORD *v9; // rax
  struct ITypeInfo *v10; // rdx
  _QWORD *v11; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  v16 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15);
  if ( NameCache >= 0 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((_QWORD *)this + 1))
        || *((_WORD *)this + 8) != 0xFFFF
        || *((_WORD *)this + 9) != 0xFFFF )
      {
        NameCache = LoadRegTypeLib(
                      *((const GUID *const *)this + 1),
                      *((_WORD *)this + 8),
                      *((_WORD *)this + 9),
                      lcid,
                      &pptlib);
LABEL_13:
        if ( NameCache >= 0 )
        {
          v12 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = v12;
            if ( v12 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v12 + 8LL))(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (*(int (__fastcall **)(_QWORD *, GUID *, _QWORD))*v7)(
                   v7,
                   &GUID_00020412_0000_0000_c000_000000000046,
                   &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = (__int64)v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, &v11);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            v9 = v11;
            v11 = 0;
            *((_QWORD *)this + 3) = v9;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v12 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v12);
        goto LABEL_13;
      }
    }
LABEL_26:
    v10 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v10 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v10);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1400069fc  mov     [rsp-8+arg_10], rbx
0x140006a01  push    rbp
0x140006a02  push    rsi
0x140006a03  push    rdi
0x140006a04  lea     rbp, [rsp-180h]
0x140006a0c  sub     rsp, 280h
0x140006a13  mov     rax, cs:__security_cookie
0x140006a1a  xor     rax, rsp
0x140006a1d  mov     [rbp+190h+var_20], rax
0x140006a24  mov     esi, edx
0x140006a26  mov     rbx, rcx
0x140006a29  cmp     qword ptr [rcx+18h], 0
0x140006a2e  jz      short loc_140006A3E
0x140006a30  cmp     qword ptr [rcx+28h], 0
0x140006a35  jz      short loc_140006A3E
0x140006a37  xor     eax, eax
0x140006a39  jmp     loc_140006C70
0x140006a3e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140006a45  add     rax, 18h
0x140006a49  mov     [rsp+290h+var_240], rax
0x140006a4e  mov     [rsp+290h+var_238], 0
0x140006a53  lea     rcx, [rsp+290h+var_240]
0x140006a58  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x140006a5d  mov     edi, eax
0x140006a5f  test    eax, eax
0x140006a61  js      loc_140006C64
0x140006a67  cmp     qword ptr [rbx+18h], 0
0x140006a6c  jnz     loc_140006C48
0x140006a72  mov     [rsp+290h+pptlib], 0
0x140006a7b  mov     rdx, [rbx+8]
0x140006a7f  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x140006a86  call    InlineIsEqualGUID
0x140006a8b  test    eax, eax
0x140006a8d  jz      short loc_140006AF6
0x140006a8f  mov     eax, 0FFFFh
0x140006a94  cmp     [rbx+10h], ax
0x140006a98  jnz     short loc_140006AF6
0x140006a9a  cmp     [rbx+12h], ax
0x140006a9e  jnz     short loc_140006AF6
0x140006aa0  mov     edi, 80004005h
0x140006aa5  mov     esi, 104h
0x140006aaa  mov     r8d, esi; nSize
0x140006aad  lea     rdx, [rsp+290h+Filename]; lpFilename
0x140006ab2  mov     rcx, cs:hModule; hModule
0x140006ab9  call    cs:__imp_GetModuleFileNameW
0x140006abf  test    eax, eax
0x140006ac1  jz      loc_140006C4A
0x140006ac7  cmp     eax, esi
0x140006ac9  jz      loc_140006C4A
0x140006acf  mov     [rsp+290h+var_258], 0
0x140006ad8  lea     rdx, [rsp+290h+pptlib]; pptlib
0x140006add  lea     rcx, [rsp+290h+Filename]; szFile
0x140006ae2  call    cs:__imp_LoadTypeLib
0x140006ae8  mov     edi, eax
0x140006aea  lea     rcx, [rsp+290h+var_258]
0x140006aef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140006af4  jmp     short loc_140006B18
0x140006af6  lea     rax, [rsp+290h+pptlib]
0x140006afb  mov     [rsp+290h+var_270], rax; pptlib
0x140006b00  mov     r9d, esi; lcid
0x140006b03  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x140006b08  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x140006b0c  mov     rcx, [rbx+8]; rguid
0x140006b10  call    cs:__imp_LoadRegTypeLib
0x140006b16  mov     edi, eax
0x140006b18  test    edi, edi
0x140006b1a  js      loc_140006C4A
0x140006b20  mov     [rsp+290h+var_258], 0
0x140006b29  mov     rcx, [rsp+290h+pptlib]
0x140006b2e  mov     rax, [rcx]
0x140006b31  lea     r8, [rsp+290h+var_258]
0x140006b36  mov     rdx, [rbx]
0x140006b39  mov     rax, [rax+30h]
0x140006b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b42  mov     edi, eax
0x140006b44  test    eax, eax
0x140006b46  js      loc_140006C2A
0x140006b4c  mov     rcx, [rsp+290h+var_258]
0x140006b51  mov     [rsp+290h+var_260], rcx
0x140006b56  test    rcx, rcx
0x140006b59  jz      short loc_140006B6C
0x140006b5b  mov     rax, [rcx]
0x140006b5e  mov     rax, [rax+8]
0x140006b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b67  mov     rcx, [rsp+290h+var_258]
0x140006b6c  mov     [rsp+290h+var_250], 0
0x140006b75  mov     rax, [rcx]
0x140006b78  lea     r8, [rsp+290h+var_250]
0x140006b7d  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x140006b84  mov     rax, [rax]
0x140006b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b8c  test    eax, eax
0x140006b8e  js      short loc_140006BE6
0x140006b90  mov     rdx, [rsp+290h+var_250]
0x140006b95  lea     rcx, [rsp+290h+var_260]
0x140006b9a  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x140006b9f  test    al, al
0x140006ba1  jnz     short loc_140006BE6
0x140006ba3  mov     rcx, [rsp+290h+var_250]
0x140006ba8  mov     rsi, [rsp+290h+var_260]
0x140006bad  mov     [rsp+290h+var_260], 0
0x140006bb6  test    rcx, rcx
0x140006bb9  jz      short loc_140006BD2
0x140006bbb  mov     rax, [rcx]
0x140006bbe  lea     r8, [rsp+290h+var_260]
0x140006bc3  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x140006bca  mov     rax, [rax]
0x140006bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bd2  test    rsi, rsi
0x140006bd5  jz      short loc_140006BE6
0x140006bd7  mov     rax, [rsi]
0x140006bda  mov     rcx, rsi
0x140006bdd  mov     rax, [rax+10h]
0x140006be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006be6  mov     rax, [rsp+290h+var_260]
0x140006beb  mov     [rsp+290h+var_260], 0
0x140006bf4  mov     [rbx+18h], rax
0x140006bf8  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140006bff  lea     rcx, [rax+8]
0x140006c03  neg     rax
0x140006c06  sbb     rdx, rdx; void (*)(unsigned __int64)
0x140006c09  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x140006c0c  mov     r8, rbx; unsigned __int64
0x140006c0f  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x140006c14  nop
0x140006c15  lea     rcx, [rsp+290h+var_250]
0x140006c1a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140006c1f  nop
0x140006c20  lea     rcx, [rsp+290h+var_260]
0x140006c25  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140006c2a  mov     rcx, [rsp+290h+pptlib]
0x140006c2f  mov     rax, [rcx]
0x140006c32  mov     rax, [rax+10h]
0x140006c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c3b  nop
0x140006c3c  lea     rcx, [rsp+290h+var_258]
0x140006c41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140006c46  jmp     short loc_140006C4A
0x140006c48  xor     edi, edi
0x140006c4a  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x140006c4e  test    rdx, rdx
0x140006c51  jz      short loc_140006C64
0x140006c53  cmp     qword ptr [rbx+28h], 0
0x140006c58  jnz     short loc_140006C64
0x140006c5a  mov     rcx, rbx; this
0x140006c5d  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x140006c62  mov     edi, eax
0x140006c64  lea     rcx, [rsp+290h+var_240]
0x140006c69  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x140006c6e  mov     eax, edi
0x140006c70  mov     rcx, [rbp+190h+var_20]
0x140006c77  xor     rcx, rsp; StackCookie
0x140006c7a  call    __security_check_cookie
0x140006c7f  mov     rbx, [rsp+290h+arg_10]
0x140006c87  add     rsp, 280h
0x140006c8e  pop     rdi
0x140006c8f  pop     rsi
0x140006c90  pop     rbp
0x140006c91  retn
```
