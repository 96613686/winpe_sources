# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1800177b4`
- end: `0x180017a55`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `673`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800176b4`
- `0x180017a94`
- `0x180017d28`

## callees

- `0x18000e380`
- `0x18000e490`
- `0x180013f48`
- `0x180014204`
- `0x180015978`
- `0x1800177b4`
- `0x180017dcc`
- `0x180017e64`
- `0x1800180e8`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x1800178a4`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800178a4`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800178d8`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800178d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017878`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017878`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  struct ITypeInfo *v10; // rdx
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B8h] BYREF
  char *v15; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A8h]
  __int64 v17; // [rsp+68h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+78h] [rbp-90h] BYREF

  v17 = -2;
  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  LOBYTE(v16) = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15);
  if ( NameCache >= 0 )
  {
    NameCache = -2147467259;
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
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = (__int64)v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, (__int64 *)&v11);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            v9 = (__int64)v11;
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
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1800177b4  mov     rax, rsp
0x1800177b7  push    rbp
0x1800177b8  push    rsi
0x1800177b9  push    rdi
0x1800177ba  lea     rbp, [rax-1A8h]
0x1800177c1  sub     rsp, 290h
0x1800177c8  mov     [rsp+2A0h+var_240], 0FFFFFFFFFFFFFFFEh
0x1800177d1  mov     [rax+18h], rbx
0x1800177d5  mov     rax, cs:__security_cookie
0x1800177dc  xor     rax, rsp
0x1800177df  mov     [rbp+1A0h+var_20], rax
0x1800177e6  mov     esi, edx
0x1800177e8  mov     rbx, rcx
0x1800177eb  cmp     qword ptr [rcx+18h], 0
0x1800177f0  jz      short loc_180017800
0x1800177f2  cmp     qword ptr [rcx+28h], 0
0x1800177f7  jz      short loc_180017800
0x1800177f9  xor     eax, eax
0x1800177fb  jmp     loc_180017A32
0x180017800  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180017807  add     rax, 18h
0x18001780b  mov     [rsp+2A0h+var_250], rax
0x180017810  mov     byte ptr [rsp+2A0h+var_248], 0
0x180017815  lea     rcx, [rsp+2A0h+var_250]
0x18001781a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001781f  mov     edi, eax
0x180017821  test    eax, eax
0x180017823  js      loc_180017A26
0x180017829  mov     edi, 80004005h
0x18001782e  cmp     qword ptr [rbx+18h], 0
0x180017833  jnz     loc_180017A0A
0x180017839  and     [rsp+2A0h+pptlib], 0
0x18001783f  mov     rdx, [rbx+8]
0x180017843  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x18001784a  call    InlineIsEqualGUID
0x18001784f  test    eax, eax
0x180017851  jz      short loc_1800178BE
0x180017853  mov     eax, 0FFFFh
0x180017858  cmp     [rbx+10h], ax
0x18001785c  jnz     short loc_1800178BE
0x18001785e  cmp     [rbx+12h], ax
0x180017862  jnz     short loc_1800178BE
0x180017864  mov     esi, 104h
0x180017869  mov     r8d, esi; nSize
0x18001786c  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x180017871  mov     rcx, cs:hModule; hModule
0x180017878  call    cs:__imp_GetModuleFileNameW
0x18001787f  nop     dword ptr [rax+rax+00h]
0x180017884  test    eax, eax
0x180017886  jz      loc_180017A0C
0x18001788c  cmp     eax, esi
0x18001788e  jz      loc_180017A0C
0x180017894  and     [rsp+2A0h+var_268], 0
0x18001789a  lea     rdx, [rsp+2A0h+pptlib]; pptlib
0x18001789f  lea     rcx, [rsp+2A0h+Filename]; szFile
0x1800178a4  call    cs:__imp_LoadTypeLib
0x1800178ab  nop     dword ptr [rax+rax+00h]
0x1800178b0  mov     edi, eax
0x1800178b2  lea     rcx, [rsp+2A0h+var_268]
0x1800178b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800178bc  jmp     short loc_1800178E6
0x1800178be  lea     rax, [rsp+2A0h+pptlib]
0x1800178c3  mov     [rsp+20h], rax; pptlib
0x1800178c8  mov     r9d, esi; lcid
0x1800178cb  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x1800178d0  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x1800178d4  mov     rcx, [rbx+8]; rguid
0x1800178d8  call    cs:__imp_LoadRegTypeLib
0x1800178df  nop     dword ptr [rax+rax+00h]
0x1800178e4  mov     edi, eax
0x1800178e6  test    edi, edi
0x1800178e8  js      loc_180017A0C
0x1800178ee  and     [rsp+2A0h+var_268], 0
0x1800178f4  mov     rcx, [rsp+2A0h+pptlib]
0x1800178f9  mov     rax, [rcx]
0x1800178fc  lea     r8, [rsp+2A0h+var_268]
0x180017901  mov     rdx, [rbx]
0x180017904  mov     rax, [rax+30h]
0x180017908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001790d  mov     edi, eax
0x18001790f  test    eax, eax
0x180017911  js      loc_1800179EC
0x180017917  mov     rcx, [rsp+2A0h+var_268]
0x18001791c  mov     [rsp+2A0h+var_270], rcx
0x180017921  test    rcx, rcx
0x180017924  jz      short loc_180017937
0x180017926  mov     rax, [rcx]
0x180017929  mov     rax, [rax+8]
0x18001792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017932  mov     rcx, [rsp+2A0h+var_268]
0x180017937  and     [rsp+2A0h+var_260], 0
0x18001793d  mov     rax, [rcx]
0x180017940  lea     r8, [rsp+2A0h+var_260]
0x180017945  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18001794c  mov     rax, [rax]
0x18001794f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017954  test    eax, eax
0x180017956  js      short loc_1800179AB
0x180017958  mov     rdx, [rsp+2A0h+var_260]
0x18001795d  lea     rcx, [rsp+2A0h+var_270]
0x180017962  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180017967  test    al, al
0x180017969  jnz     short loc_1800179AB
0x18001796b  mov     rsi, [rsp+2A0h+var_270]
0x180017970  and     [rsp+2A0h+var_270], 0
0x180017976  mov     rcx, [rsp+2A0h+var_260]
0x18001797b  test    rcx, rcx
0x18001797e  jz      short loc_180017997
0x180017980  mov     rax, [rcx]
0x180017983  lea     r8, [rsp+2A0h+var_270]
0x180017988  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x18001798f  mov     rax, [rax]
0x180017992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017997  test    rsi, rsi
0x18001799a  jz      short loc_1800179AB
0x18001799c  mov     rax, [rsi]
0x18001799f  mov     rcx, rsi
0x1800179a2  mov     rax, [rax+10h]
0x1800179a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ab  mov     rax, [rsp+2A0h+var_270]
0x1800179b0  and     [rsp+2A0h+var_270], 0
0x1800179b6  mov     [rbx+18h], rax
0x1800179ba  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800179c1  lea     rcx, [rax+8]
0x1800179c5  neg     rax
0x1800179c8  sbb     rdx, rdx; void (*)(unsigned __int64)
0x1800179cb  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x1800179ce  mov     r8, rbx; unsigned __int64
0x1800179d1  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x1800179d6  nop
0x1800179d7  lea     rcx, [rsp+2A0h+var_260]
0x1800179dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800179e1  nop
0x1800179e2  lea     rcx, [rsp+2A0h+var_270]
0x1800179e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800179ec  mov     rcx, [rsp+2A0h+pptlib]
0x1800179f1  mov     rax, [rcx]
0x1800179f4  mov     rax, [rax+10h]
0x1800179f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179fd  nop
0x1800179fe  lea     rcx, [rsp+2A0h+var_268]
0x180017a03  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017a08  jmp     short loc_180017A0C
0x180017a0a  xor     edi, edi
0x180017a0c  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180017a10  test    rdx, rdx
0x180017a13  jz      short loc_180017A26
0x180017a15  cmp     qword ptr [rbx+28h], 0
0x180017a1a  jnz     short loc_180017A26
0x180017a1c  mov     rcx, rbx; this
0x180017a1f  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180017a24  mov     edi, eax
0x180017a26  lea     rcx, [rsp+2A0h+var_250]
0x180017a2b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180017a30  mov     eax, edi
0x180017a32  mov     rcx, [rbp+1A0h+var_20]
0x180017a39  xor     rcx, rsp; StackCookie
0x180017a3c  call    __security_check_cookie
0x180017a41  mov     rbx, [rsp+2A0h+arg_10]
0x180017a49  add     rsp, 290h
0x180017a50  pop     rdi
0x180017a51  pop     rsi
0x180017a52  pop     rbp
0x180017a53  retn
```
