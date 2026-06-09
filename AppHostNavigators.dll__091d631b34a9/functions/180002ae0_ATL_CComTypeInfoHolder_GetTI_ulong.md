# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180002ae0`
- end: `0x180002e27`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `839`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180002a14`
- `0x180002e44`
- `0x180002f48`

## callees

- `0x18000203c`
- `0x180002140`
- `0x180002170`
- `0x1800021a4`
- `0x18000234c`
- `0x18000239c`
- `0x1800023ec`
- `0x180002ae0`
- `0x180002fec`
- `0x180003134`
- `0x1800033a0`
- `0x180003ad4`
- `0x1800130a0`
- `0x180013160`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x180002bd2`
- `KERNEL32!GetModuleFileNameA` at `0x180002bd2`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002c85`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002c85`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180002cc3`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180002cc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  __int64 v6; // rcx
  WORD *v7; // rdx
  DWORD ModuleFileNameA; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rsi
  __int64 v13; // rax
  void *v14; // rsp
  WCHAR *v15; // rax
  const OLECHAR *v16; // rax
  int (__fastcall ***v17)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v18; // rsi
  __int64 v19; // rax
  struct ITypeInfo *v20; // rdx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  int (__fastcall ***v22)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp+8h] BYREF
  void (__fastcall ***v23)(_QWORD, GUID *, WCHAR *); // [rsp+40h] [rbp+10h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp+18h] BYREF
  char *v25; // [rsp+50h] [rbp+20h] BYREF
  char v26; // [rsp+58h] [rbp+28h]
  CHAR Filename[272]; // [rsp+60h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v25 = (char *)ATL::_pAtlModule + 24;
  v26 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v25);
  if ( NameCache < 0 )
    goto LABEL_44;
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_41;
  }
  pptlib = 0;
  v6 = *((_QWORD *)this + 1);
  if ( ATL::CAtlModule::m_libid.Data1 != *(_DWORD *)v6
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)(v6 + 4)
    || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)(v6 + 8)
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)(v6 + 12) )
  {
    v7 = (WORD *)((char *)this + 16);
LABEL_27:
    NameCache = LoadRegTypeLib((const GUID *const)v6, *v7, *((_WORD *)this + 9), lcid, &pptlib);
LABEL_28:
    if ( NameCache >= 0 )
    {
      v22 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    *(_QWORD *)this,
                    &v22);
      if ( NameCache >= 0 )
      {
        v17 = v22;
        *(_QWORD *)WideCharStr = v22;
        if ( v22 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v22)[1])(v22);
          v17 = v22;
        }
        v23 = 0;
        if ( (**v17)(v17, &GUID_00020412_0000_0000_c000_000000000046, &v23) >= 0
          && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(WideCharStr, v23) )
        {
          v18 = *(_QWORD *)WideCharStr;
          *(_QWORD *)WideCharStr = 0;
          if ( v23 )
            (**v23)(v23, &GUID_00020401_0000_0000_c000_000000000046, WideCharStr);
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = *(_QWORD *)WideCharStr;
        *(_QWORD *)WideCharStr = 0;
        *((_QWORD *)this + 3) = v19;
        ATL::AtlModuleAddTermFunc(
          (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                      & ((unsigned __int64)ATL::_pAtlModule + 8)),
          (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
          (unsigned __int64)this);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)WideCharStr);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    }
    goto LABEL_41;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_27;
  NameCache = -2147467259;
  ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x104u);
  if ( !ModuleFileNameA || ModuleFileNameA == 260 )
  {
LABEL_41:
    v20 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v20 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v20);
    }
    goto LABEL_44;
  }
  v22 = 0;
  v9 = -1;
  do
    ++v9;
  while ( Filename[v9] );
  *(_DWORD *)WideCharStr = v9 + 1;
  if ( (int)ATL::AtlMultiply<int>(WideCharStr) >= 0 )
  {
    v11 = *(int *)WideCharStr;
    v12 = (unsigned __int64)*(int *)WideCharStr >> 1;
    if ( *(int *)WideCharStr <= 1024
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)*(int *)WideCharStr, v10) )
    {
      v13 = v11 + 15;
      if ( v11 + 15 < v11 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
      v15 = WideCharStr;
    }
    else
    {
      v15 = (WCHAR *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(&v22, v11);
    }
    v16 = AtlA2WHelper(v15, Filename, v12, 3u);
    if ( v16 )
    {
      NameCache = LoadTypeLib(v16, &pptlib);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
      goto LABEL_28;
    }
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
  NameCache = -2147024882;
LABEL_44:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v25);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180002ae0  push    rbp
0x180002ae2  push    rdi
0x180002ae3  push    r14
0x180002ae5  sub     rsp, 180h
0x180002aec  lea     rbp, [rsp+30h]
0x180002af1  mov     [rbp+160h+arg_10], rbx
0x180002af8  mov     [rbp+160h+arg_18], rsi
0x180002aff  mov     rax, cs:__security_cookie
0x180002b06  xor     rax, rbp
0x180002b09  mov     [rbp+160h+var_20], rax
0x180002b10  mov     esi, edx
0x180002b12  mov     rbx, rcx
0x180002b15  xor     r14d, r14d
0x180002b18  cmp     [rcx+18h], r14
0x180002b1c  jz      short loc_180002B2B
0x180002b1e  cmp     [rcx+28h], r14
0x180002b22  jz      short loc_180002B2B
0x180002b24  xor     eax, eax
0x180002b26  jmp     loc_180002DFE
0x180002b2b  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002b32  add     rax, 18h
0x180002b36  mov     [rbp+160h+var_140], rax
0x180002b3a  mov     [rbp+160h+var_138], r14b
0x180002b3e  lea     rcx, [rbp+160h+var_140]
0x180002b42  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180002b47  mov     edi, eax
0x180002b49  test    eax, eax
0x180002b4b  js      loc_180002DF3
0x180002b51  cmp     [rbx+18h], r14
0x180002b55  jnz     loc_180002DD7
0x180002b5b  mov     [rbp+160h+pptlib], r14
0x180002b5f  mov     rcx, [rbx+8]; rguid
0x180002b63  mov     eax, [rcx]
0x180002b65  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180002b6b  jnz     loc_180002CAB
0x180002b71  mov     eax, [rcx+4]
0x180002b74  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180002b7a  jnz     loc_180002CAB
0x180002b80  mov     eax, [rcx+8]
0x180002b83  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180002b89  jnz     loc_180002CAB
0x180002b8f  mov     eax, [rcx+0Ch]
0x180002b92  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180002b98  jnz     loc_180002CAB
0x180002b9e  lea     rdx, [rbx+10h]
0x180002ba2  mov     eax, 0FFFFh
0x180002ba7  cmp     [rdx], ax
0x180002baa  jnz     loc_180002CAF
0x180002bb0  cmp     [rbx+12h], ax
0x180002bb4  jnz     loc_180002CAF
0x180002bba  mov     edi, 80004005h
0x180002bbf  mov     esi, 104h
0x180002bc4  mov     r8d, esi; nSize
0x180002bc7  lea     rdx, [rbp+160h+Filename]; lpFilename
0x180002bcb  mov     rcx, cs:hModule; hModule
0x180002bd2  call    cs:__imp_GetModuleFileNameA
0x180002bd8  test    eax, eax
0x180002bda  jz      loc_180002DDA
0x180002be0  cmp     eax, esi
0x180002be2  jz      loc_180002DDA
0x180002be8  mov     [rbp+160h+var_158], r14
0x180002bec  lea     rax, [rbp+160h+Filename]
0x180002bf0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002bf4  inc     rdx
0x180002bf7  cmp     [rax+rdx], r14b
0x180002bfb  jnz     short loc_180002BF4
0x180002bfd  inc     edx
0x180002bff  mov     dword ptr [rbp+160h+WideCharStr], edx
0x180002c02  lea     rcx, [rbp+160h+WideCharStr]
0x180002c06  call    ??$AtlMultiply@H@ATL@@YAJPEAHHH@Z; ATL::AtlMultiply<int>(int *,int,int)
0x180002c0b  test    eax, eax
0x180002c0d  js      loc_180002C98
0x180002c13  movsxd  rdi, dword ptr [rbp+160h+WideCharStr]
0x180002c17  mov     rsi, rdi
0x180002c1a  shr     rsi, 1
0x180002c1d  cmp     dword ptr [rbp+160h+WideCharStr], 400h
0x180002c24  jg      short loc_180002C58
0x180002c26  mov     rcx, rdi; this
0x180002c29  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180002c2e  test    al, al
0x180002c30  jz      short loc_180002C58
0x180002c32  lea     rax, [rdi+0Fh]
0x180002c36  cmp     rax, rdi
0x180002c39  ja      short loc_180002C45
0x180002c3b  mov     rax, 0FFFFFFFFFFFFFF0h
0x180002c45  and     rax, 0FFFFFFFFFFFFFFF0h
0x180002c49  call    _alloca_probe
0x180002c4e  sub     rsp, rax
0x180002c51  lea     rax, [rsp+190h+WideCharStr]
0x180002c56  jmp     short loc_180002C64
0x180002c58  mov     rdx, rdi
0x180002c5b  lea     rcx, [rbp+160h+var_158]
0x180002c5f  call    ?Allocate@?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180002c64  mov     r9d, 3; CodePage
0x180002c6a  mov     r8d, esi; cchWideChar
0x180002c6d  lea     rdx, [rbp+160h+Filename]; lpMultiByteStr
0x180002c71  mov     rcx, rax; lpWideCharStr
0x180002c74  call    ?AtlA2WHelper@@YAPEAGPEAGPEBDHI@Z; AtlA2WHelper(ushort *,char const *,int,uint)
0x180002c79  test    rax, rax
0x180002c7c  jz      short loc_180002C98
0x180002c7e  lea     rdx, [rbp+160h+pptlib]; pptlib
0x180002c82  mov     rcx, rax; szFile
0x180002c85  call    cs:__imp_LoadTypeLib
0x180002c8b  mov     edi, eax
0x180002c8d  lea     rcx, [rbp+160h+var_158]
0x180002c91  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180002c96  jmp     short loc_180002CCB
0x180002c98  lea     rcx, [rbp+160h+var_158]
0x180002c9c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180002ca1  mov     edi, 8007000Eh
0x180002ca6  jmp     loc_180002DF3
0x180002cab  lea     rdx, [rbx+10h]
0x180002caf  lea     rax, [rbp+160h+pptlib]
0x180002cb3  mov     [rsp+190h+var_170], rax; pptlib
0x180002cb8  mov     r9d, esi; lcid
0x180002cbb  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180002cc0  movzx   edx, word ptr [rdx]; wVerMajor
0x180002cc3  call    cs:__imp_LoadRegTypeLib
0x180002cc9  mov     edi, eax
0x180002ccb  test    edi, edi
0x180002ccd  js      loc_180002DDA
0x180002cd3  mov     [rbp+160h+var_158], r14
0x180002cd7  mov     rcx, [rbp+160h+pptlib]
0x180002cdb  mov     rax, [rcx]
0x180002cde  lea     r8, [rbp+160h+var_158]
0x180002ce2  mov     rdx, [rbx]
0x180002ce5  mov     rax, [rax+30h]
0x180002ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cee  mov     edi, eax
0x180002cf0  test    eax, eax
0x180002cf2  js      loc_180002DBB
0x180002cf8  mov     rcx, [rbp+160h+var_158]
0x180002cfc  mov     qword ptr [rbp+160h+WideCharStr], rcx
0x180002d00  test    rcx, rcx
0x180002d03  jz      short loc_180002D15
0x180002d05  mov     rax, [rcx]
0x180002d08  mov     rax, [rax+8]
0x180002d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d11  mov     rcx, [rbp+160h+var_158]
0x180002d15  mov     [rbp+160h+var_150], r14
0x180002d19  mov     rax, [rcx]
0x180002d1c  lea     r8, [rbp+160h+var_150]
0x180002d20  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180002d27  mov     rax, [rax]
0x180002d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2f  test    eax, eax
0x180002d31  js      short loc_180002D7F
0x180002d33  mov     rdx, [rbp+160h+var_150]
0x180002d37  lea     rcx, [rbp+160h+WideCharStr]
0x180002d3b  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180002d40  test    al, al
0x180002d42  jnz     short loc_180002D7F
0x180002d44  mov     rcx, [rbp+160h+var_150]
0x180002d48  mov     rsi, qword ptr [rbp+160h+WideCharStr]
0x180002d4c  mov     qword ptr [rbp+160h+WideCharStr], r14
0x180002d50  test    rcx, rcx
0x180002d53  jz      short loc_180002D6B
0x180002d55  mov     rax, [rcx]
0x180002d58  lea     r8, [rbp+160h+WideCharStr]
0x180002d5c  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180002d63  mov     rax, [rax]
0x180002d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6b  test    rsi, rsi
0x180002d6e  jz      short loc_180002D7F
0x180002d70  mov     rax, [rsi]
0x180002d73  mov     rcx, rsi
0x180002d76  mov     rax, [rax+10h]
0x180002d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7f  mov     rax, qword ptr [rbp+160h+WideCharStr]
0x180002d83  mov     qword ptr [rbp+160h+WideCharStr], r14
0x180002d87  mov     [rbx+18h], rax
0x180002d8b  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d92  lea     rcx, [rax+8]
0x180002d96  neg     rax
0x180002d99  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180002d9c  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180002d9f  mov     r8, rbx; unsigned __int64
0x180002da2  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180002da7  nop
0x180002da8  lea     rcx, [rbp+160h+var_150]
0x180002dac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002db1  nop
0x180002db2  lea     rcx, [rbp+160h+WideCharStr]
0x180002db6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002dbb  mov     rcx, [rbp+160h+pptlib]
0x180002dbf  mov     rax, [rcx]
0x180002dc2  mov     rax, [rax+10h]
0x180002dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcb  nop
0x180002dcc  lea     rcx, [rbp+160h+var_158]
0x180002dd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002dd5  jmp     short loc_180002DDA
0x180002dd7  mov     edi, r14d
0x180002dda  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180002dde  test    rdx, rdx
0x180002de1  jz      short loc_180002DF3
0x180002de3  cmp     [rbx+28h], r14
0x180002de7  jnz     short loc_180002DF3
0x180002de9  mov     rcx, rbx; this
0x180002dec  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180002df1  mov     edi, eax
0x180002df3  lea     rcx, [rbp+160h+var_140]
0x180002df7  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180002dfc  mov     eax, edi
0x180002dfe  mov     rcx, [rbp+160h+var_20]
0x180002e05  xor     rcx, rbp; StackCookie
0x180002e08  call    __security_check_cookie
0x180002e0d  mov     rbx, [rbp+160h+arg_10]
0x180002e14  mov     rsi, [rbp+160h+arg_18]
0x180002e1b  lea     rsp, [rbp+150h]
0x180002e22  pop     r14
0x180002e24  pop     rdi
0x180002e25  pop     rbp
0x180002e26  retn
```
