# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000fc68`
- end: `0x18000fee4`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `636`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f0e0`
- `0x18000f944`
- `0x18000fef0`
- `0x18000ff60`
- `0x18000ffd0`
- `0x180010040`
- `0x1800100b0`
- `0x180010250`
- `0x180010300`
- `0x1800103b0`
- `0x180010460`
- `0x180010510`

## callees

- `0x1800026f0`
- `0x18000c36c`
- `0x18000d7a8`
- `0x18000fc68`
- `0x180010d14`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000fd40`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000fd40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000feba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000feba`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000fd63`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000fd63`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000fd84`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000fd84`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  __int64 v6; // rcx
  WORD *v7; // rdx
  int NameCache; // edi
  DWORD ModuleFileNameW; // eax
  HRESULT v10; // eax
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD); // rcx
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // rax
  struct ITypeInfo *v13; // rdx
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+40h] [rbp-C8h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD); // [rsp+48h] [rbp-C0h] BYREF
  void (__fastcall ***v17[3])(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-B8h] BYREF
  char v18; // [rsp+68h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+78h] [rbp-90h] BYREF

  v17[1] = (void (__fastcall ***)(_QWORD, GUID *, __int64))-2LL;
  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v17[2] = (void (__fastcall ***)(_QWORD, GUID *, __int64))((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v18 = 1;
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_30;
  }
  pptlib = 0;
  v6 = *((_QWORD *)this + 1);
  if ( ATL::CAtlModule::m_libid.Data1 != *(_DWORD *)v6
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)(v6 + 4)
    || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)(v6 + 8)
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)(v6 + 12) )
  {
    v7 = (WORD *)((char *)this + 16);
LABEL_15:
    v10 = LoadRegTypeLib((const GUID *const)v6, *v7, *((_WORD *)this + 9), lcid, &pptlib);
LABEL_16:
    NameCache = v10;
    if ( v10 >= 0 )
    {
      v16 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    *(_QWORD *)this,
                    &v16);
      if ( NameCache >= 0 )
      {
        v11 = v16;
        v14 = v16;
        if ( v16 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v16)[1])(v16);
          v11 = v16;
        }
        v17[0] = 0;
        if ( (**v11)(v11, &GUID_00020412_0000_0000_c000_000000000046, v17) >= 0 )
          ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v14, v17);
        v12 = v14;
        v14 = 0;
        *((_QWORD *)this + 3) = v12;
        ATL::AtlModuleAddTermFunc(
          (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                      & ((unsigned __int64)ATL::_pAtlModule + 8)),
          (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
          (unsigned __int64)this);
        if ( v17[0] )
          (*((void (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64)))*v17[0] + 2))(v17[0]);
        if ( v14 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[2])(v14);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v16 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v16)[2])(v16);
    }
    goto LABEL_30;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_15;
  NameCache = -2147467259;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( ModuleFileNameW && ModuleFileNameW != 260 )
  {
    v10 = LoadTypeLib(Filename, &pptlib);
    goto LABEL_16;
  }
LABEL_30:
  v13 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v13 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v13);
  }
  LeaveCriticalSection(v5);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18000fc68  mov     rax, rsp
0x18000fc6b  push    rbp
0x18000fc6c  push    rsi
0x18000fc6d  push    rdi
0x18000fc6e  lea     rbp, [rax-1A8h]
0x18000fc75  sub     rsp, 290h
0x18000fc7c  mov     [rsp+2A0h+var_250], 0FFFFFFFFFFFFFFFEh
0x18000fc85  mov     [rax+18h], rbx
0x18000fc89  mov     rax, cs:__security_cookie
0x18000fc90  xor     rax, rsp
0x18000fc93  mov     [rbp+1A0h+var_20], rax
0x18000fc9a  mov     edi, edx
0x18000fc9c  mov     rbx, rcx
0x18000fc9f  cmp     qword ptr [rcx+18h], 0
0x18000fca4  jz      short loc_18000FCB4
0x18000fca6  cmp     qword ptr [rcx+28h], 0
0x18000fcab  jz      short loc_18000FCB4
0x18000fcad  xor     eax, eax
0x18000fcaf  jmp     loc_18000FEC2
0x18000fcb4  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000fcbb  add     rsi, 18h
0x18000fcbf  mov     qword ptr [rsp+2A0h+var_248], rsi
0x18000fcc4  mov     rcx, rsi; lpCriticalSection
0x18000fcc7  call    cs:__imp_EnterCriticalSection
0x18000fccd  mov     [rsp+2A0h+var_240], 1
0x18000fcd2  cmp     qword ptr [rbx+18h], 0
0x18000fcd7  jnz     loc_18000FE9B
0x18000fcdd  mov     [rsp+2A0h+pptlib], 0
0x18000fce6  mov     rcx, [rbx+8]; rguid
0x18000fcea  mov     eax, [rcx]
0x18000fcec  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000fcf2  jnz     short loc_18000FD6B
0x18000fcf4  mov     eax, [rcx+4]
0x18000fcf7  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000fcfd  jnz     short loc_18000FD6B
0x18000fcff  mov     eax, [rcx+8]
0x18000fd02  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000fd08  jnz     short loc_18000FD6B
0x18000fd0a  mov     eax, [rcx+0Ch]
0x18000fd0d  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000fd13  jnz     short loc_18000FD6B
0x18000fd15  lea     rdx, [rbx+10h]
0x18000fd19  mov     eax, 0FFFFh
0x18000fd1e  cmp     [rdx], ax
0x18000fd21  jnz     short loc_18000FD6F
0x18000fd23  cmp     [rbx+12h], ax
0x18000fd27  jnz     short loc_18000FD6F
0x18000fd29  mov     edi, 80004005h
0x18000fd2e  mov     r8d, 104h; nSize
0x18000fd34  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x18000fd39  mov     rcx, cs:hModule; hModule
0x18000fd40  call    cs:__imp_GetModuleFileNameW
0x18000fd46  test    eax, eax
0x18000fd48  jz      loc_18000FE9D
0x18000fd4e  cmp     eax, 104h
0x18000fd53  jz      loc_18000FE9D
0x18000fd59  lea     rdx, [rsp+2A0h+pptlib]; pptlib
0x18000fd5e  lea     rcx, [rsp+2A0h+Filename]; szFile
0x18000fd63  call    cs:__imp_LoadTypeLib
0x18000fd69  jmp     short loc_18000FD8A
0x18000fd6b  lea     rdx, [rbx+10h]
0x18000fd6f  lea     rax, [rsp+2A0h+pptlib]
0x18000fd74  mov     [rsp+20h], rax; pptlib
0x18000fd79  mov     r9d, edi; lcid
0x18000fd7c  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18000fd81  movzx   edx, word ptr [rdx]; wVerMajor
0x18000fd84  call    cs:__imp_LoadRegTypeLib
0x18000fd8a  mov     edi, eax
0x18000fd8c  test    eax, eax
0x18000fd8e  js      loc_18000FE9D
0x18000fd94  mov     [rsp+2A0h+var_260], 0
0x18000fd9d  mov     rcx, [rsp+2A0h+pptlib]
0x18000fda2  mov     rax, [rcx]
0x18000fda5  lea     r8, [rsp+2A0h+var_260]
0x18000fdaa  mov     rdx, [rbx]
0x18000fdad  mov     rax, [rax+30h]
0x18000fdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb6  mov     edi, eax
0x18000fdb8  test    eax, eax
0x18000fdba  js      loc_18000FE70
0x18000fdc0  mov     rcx, [rsp+2A0h+var_260]
0x18000fdc5  mov     [rsp+2A0h+var_270], rcx
0x18000fdca  test    rcx, rcx
0x18000fdcd  jz      short loc_18000FDE0
0x18000fdcf  mov     rax, [rcx]
0x18000fdd2  mov     rax, [rax+8]
0x18000fdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fddb  mov     rcx, [rsp+2A0h+var_260]
0x18000fde0  mov     [rsp+2A0h+var_258], 0
0x18000fde9  mov     rax, [rcx]
0x18000fdec  lea     r8, [rsp+2A0h+var_258]
0x18000fdf1  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000fdf8  mov     rax, [rax]
0x18000fdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe00  test    eax, eax
0x18000fe02  js      short loc_18000FE13
0x18000fe04  lea     rdx, [rsp+2A0h+var_258]
0x18000fe09  lea     rcx, [rsp+2A0h+var_270]
0x18000fe0e  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x18000fe13  mov     rax, [rsp+2A0h+var_270]
0x18000fe18  mov     [rsp+2A0h+var_270], 0
0x18000fe21  mov     [rbx+18h], rax
0x18000fe25  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000fe2c  lea     rcx, [rax+8]
0x18000fe30  neg     rax
0x18000fe33  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18000fe36  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18000fe39  mov     r8, rbx; unsigned __int64
0x18000fe3c  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000fe41  nop
0x18000fe42  mov     rcx, [rsp+2A0h+var_258]
0x18000fe47  test    rcx, rcx
0x18000fe4a  jz      short loc_18000FE59
0x18000fe4c  mov     rax, [rcx]
0x18000fe4f  mov     rax, [rax+10h]
0x18000fe53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe58  nop
0x18000fe59  mov     rcx, [rsp+2A0h+var_270]
0x18000fe5e  test    rcx, rcx
0x18000fe61  jz      short loc_18000FE70
0x18000fe63  mov     rax, [rcx]
0x18000fe66  mov     rax, [rax+10h]
0x18000fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe6f  nop
0x18000fe70  mov     rcx, [rsp+2A0h+pptlib]
0x18000fe75  mov     rax, [rcx]
0x18000fe78  mov     rax, [rax+10h]
0x18000fe7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe81  nop
0x18000fe82  mov     rcx, [rsp+2A0h+var_260]
0x18000fe87  test    rcx, rcx
0x18000fe8a  jz      short loc_18000FE99
0x18000fe8c  mov     rax, [rcx]
0x18000fe8f  mov     rax, [rax+10h]
0x18000fe93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe98  nop
0x18000fe99  jmp     short loc_18000FE9D
0x18000fe9b  xor     edi, edi
0x18000fe9d  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18000fea1  test    rdx, rdx
0x18000fea4  jz      short loc_18000FEB7
0x18000fea6  cmp     qword ptr [rbx+28h], 0
0x18000feab  jnz     short loc_18000FEB7
0x18000fead  mov     rcx, rbx; this
0x18000feb0  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000feb5  mov     edi, eax
0x18000feb7  mov     rcx, rsi; lpCriticalSection
0x18000feba  call    cs:__imp_LeaveCriticalSection
0x18000fec0  mov     eax, edi
0x18000fec2  mov     rcx, [rbp+1A0h+var_20]
0x18000fec9  xor     rcx, rsp; StackCookie
0x18000fecc  call    __security_check_cookie
0x18000fed1  mov     rbx, [rsp+2A0h+arg_10]
0x18000fed9  add     rsp, 290h
0x18000fee0  pop     rdi
0x18000fee1  pop     rsi
0x18000fee2  pop     rbp
0x18000fee3  retn
```
