# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180003e28`
- end: `0x18000409a`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `626`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003d44`
- `0x1800040a0`
- `0x180004110`
- `0x180004180`
- `0x180004320`
- `0x1800043d0`
- `0x180004480`

## callees

- `0x180002808`
- `0x180003060`
- `0x180003e28`
- `0x1800045c4`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180003ef6`
- `KERNEL32!GetModuleFileNameW` at `0x180003ef6`
- `KERNEL32!LeaveCriticalSection` at `0x180004070`
- `KERNEL32!LeaveCriticalSection` at `0x180004070`
- `KERNEL32!EnterCriticalSection` at `0x180003e7d`
- `KERNEL32!EnterCriticalSection` at `0x180003e7d`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180003f19`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180003f19`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180003f3a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180003f3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  __int64 v6; // rcx
  WORD *v7; // rdx
  int NameCache; // edi
  DWORD ModuleFileNameW; // eax
  HRESULT v10; // eax
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // rax
  struct ITypeInfo *v13; // rdx
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v17[1] = (char *)ATL::_pAtlModule + 24;
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
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[1])(v16);
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
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[0] + 16LL))(v17[0]);
        if ( v14 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v16 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
    }
    goto LABEL_30;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_15;
  NameCache = -2147467259;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x180003e28  mov     [rsp-8+arg_10], rbx
0x180003e2d  push    rbp
0x180003e2e  push    rsi
0x180003e2f  push    rdi
0x180003e30  lea     rbp, [rsp-180h]
0x180003e38  sub     rsp, 280h
0x180003e3f  mov     rax, cs:__security_cookie
0x180003e46  xor     rax, rsp
0x180003e49  mov     [rbp+190h+var_20], rax
0x180003e50  mov     edi, edx
0x180003e52  mov     rbx, rcx
0x180003e55  cmp     qword ptr [rcx+18h], 0
0x180003e5a  jz      short loc_180003E6A
0x180003e5c  cmp     qword ptr [rcx+28h], 0
0x180003e61  jz      short loc_180003E6A
0x180003e63  xor     eax, eax
0x180003e65  jmp     loc_180004078
0x180003e6a  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003e71  add     rsi, 18h
0x180003e75  mov     [rsp+290h+var_240], rsi
0x180003e7a  mov     rcx, rsi; lpCriticalSection
0x180003e7d  call    cs:__imp_EnterCriticalSection
0x180003e83  mov     [rsp+290h+var_238], 1
0x180003e88  cmp     qword ptr [rbx+18h], 0
0x180003e8d  jnz     loc_180004051
0x180003e93  mov     [rsp+290h+pptlib], 0
0x180003e9c  mov     rcx, [rbx+8]; rguid
0x180003ea0  mov     eax, [rcx]
0x180003ea2  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180003ea8  jnz     short loc_180003F21
0x180003eaa  mov     eax, [rcx+4]
0x180003ead  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180003eb3  jnz     short loc_180003F21
0x180003eb5  mov     eax, [rcx+8]
0x180003eb8  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180003ebe  jnz     short loc_180003F21
0x180003ec0  mov     eax, [rcx+0Ch]
0x180003ec3  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180003ec9  jnz     short loc_180003F21
0x180003ecb  lea     rdx, [rbx+10h]
0x180003ecf  mov     eax, 0FFFFh
0x180003ed4  cmp     [rdx], ax
0x180003ed7  jnz     short loc_180003F25
0x180003ed9  cmp     [rbx+12h], ax
0x180003edd  jnz     short loc_180003F25
0x180003edf  mov     edi, 80004005h
0x180003ee4  mov     r8d, 104h; nSize
0x180003eea  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180003eef  mov     rcx, cs:hInstance; hModule
0x180003ef6  call    cs:__imp_GetModuleFileNameW
0x180003efc  test    eax, eax
0x180003efe  jz      loc_180004053
0x180003f04  cmp     eax, 104h
0x180003f09  jz      loc_180004053
0x180003f0f  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180003f14  lea     rcx, [rsp+290h+Filename]; szFile
0x180003f19  call    cs:__imp_LoadTypeLib
0x180003f1f  jmp     short loc_180003F40
0x180003f21  lea     rdx, [rbx+10h]
0x180003f25  lea     rax, [rsp+290h+pptlib]
0x180003f2a  mov     [rsp+290h+var_270], rax; pptlib
0x180003f2f  mov     r9d, edi; lcid
0x180003f32  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180003f37  movzx   edx, word ptr [rdx]; wVerMajor
0x180003f3a  call    cs:__imp_LoadRegTypeLib
0x180003f40  mov     edi, eax
0x180003f42  test    eax, eax
0x180003f44  js      loc_180004053
0x180003f4a  mov     [rsp+290h+var_250], 0
0x180003f53  mov     rcx, [rsp+290h+pptlib]
0x180003f58  mov     rax, [rcx]
0x180003f5b  lea     r8, [rsp+290h+var_250]
0x180003f60  mov     rdx, [rbx]
0x180003f63  mov     rax, [rax+30h]
0x180003f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6c  mov     edi, eax
0x180003f6e  test    eax, eax
0x180003f70  js      loc_180004026
0x180003f76  mov     rcx, [rsp+290h+var_250]
0x180003f7b  mov     [rsp+290h+var_260], rcx
0x180003f80  test    rcx, rcx
0x180003f83  jz      short loc_180003F96
0x180003f85  mov     rax, [rcx]
0x180003f88  mov     rax, [rax+8]
0x180003f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f91  mov     rcx, [rsp+290h+var_250]
0x180003f96  mov     [rsp+290h+var_248], 0
0x180003f9f  mov     rax, [rcx]
0x180003fa2  lea     r8, [rsp+290h+var_248]
0x180003fa7  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180003fae  mov     rax, [rax]
0x180003fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb6  test    eax, eax
0x180003fb8  js      short loc_180003FC9
0x180003fba  lea     rdx, [rsp+290h+var_248]
0x180003fbf  lea     rcx, [rsp+290h+var_260]
0x180003fc4  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x180003fc9  mov     rax, [rsp+290h+var_260]
0x180003fce  mov     [rsp+290h+var_260], 0
0x180003fd7  mov     [rbx+18h], rax
0x180003fdb  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003fe2  lea     rcx, [rax+8]
0x180003fe6  neg     rax
0x180003fe9  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180003fec  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180003fef  mov     r8, rbx; unsigned __int64
0x180003ff2  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180003ff7  nop
0x180003ff8  mov     rcx, [rsp+290h+var_248]
0x180003ffd  test    rcx, rcx
0x180004000  jz      short loc_18000400F
0x180004002  mov     rax, [rcx]
0x180004005  mov     rax, [rax+10h]
0x180004009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000400e  nop
0x18000400f  mov     rcx, [rsp+290h+var_260]
0x180004014  test    rcx, rcx
0x180004017  jz      short loc_180004026
0x180004019  mov     rax, [rcx]
0x18000401c  mov     rax, [rax+10h]
0x180004020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004025  nop
0x180004026  mov     rcx, [rsp+290h+pptlib]
0x18000402b  mov     rax, [rcx]
0x18000402e  mov     rax, [rax+10h]
0x180004032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004037  nop
0x180004038  mov     rcx, [rsp+290h+var_250]
0x18000403d  test    rcx, rcx
0x180004040  jz      short loc_18000404F
0x180004042  mov     rax, [rcx]
0x180004045  mov     rax, [rax+10h]
0x180004049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000404e  nop
0x18000404f  jmp     short loc_180004053
0x180004051  xor     edi, edi
0x180004053  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180004057  test    rdx, rdx
0x18000405a  jz      short loc_18000406D
0x18000405c  cmp     qword ptr [rbx+28h], 0
0x180004061  jnz     short loc_18000406D
0x180004063  mov     rcx, rbx; this
0x180004066  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000406b  mov     edi, eax
0x18000406d  mov     rcx, rsi; lpCriticalSection
0x180004070  call    cs:__imp_LeaveCriticalSection
0x180004076  mov     eax, edi
0x180004078  mov     rcx, [rbp+190h+var_20]
0x18000407f  xor     rcx, rsp; StackCookie
0x180004082  call    __security_check_cookie
0x180004087  mov     rbx, [rsp+290h+arg_10]
0x18000408f  add     rsp, 280h
0x180004096  pop     rdi
0x180004097  pop     rsi
0x180004098  pop     rbp
0x180004099  retn
```
