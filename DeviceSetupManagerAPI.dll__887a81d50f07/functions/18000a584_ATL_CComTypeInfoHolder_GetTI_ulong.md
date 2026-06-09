# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000a584`
- end: `0x18000a7f6`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `626`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a3a4`
- `0x18000a800`
- `0x18000a890`
- `0x18000bf50`
- `0x18000bfc0`

## callees

- `0x1800017c0`
- `0x180009d60`
- `0x180009ff0`
- `0x18000a584`
- `0x18000acd8`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a652`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7cc`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000a675`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000a675`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000a696`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000a696`

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
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v17[2])(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-B8h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v17[1] = (void (__fastcall ***)(_QWORD, GUID *, __int64))((char *)ATL::_pAtlModule + 24);
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
0x18000a584  mov     [rsp-8+arg_10], rbx
0x18000a589  push    rbp
0x18000a58a  push    rsi
0x18000a58b  push    rdi
0x18000a58c  lea     rbp, [rsp-180h]
0x18000a594  sub     rsp, 280h
0x18000a59b  mov     rax, cs:__security_cookie
0x18000a5a2  xor     rax, rsp
0x18000a5a5  mov     [rbp+190h+var_20], rax
0x18000a5ac  mov     edi, edx
0x18000a5ae  mov     rbx, rcx
0x18000a5b1  cmp     qword ptr [rcx+18h], 0
0x18000a5b6  jz      short loc_18000A5C6
0x18000a5b8  cmp     qword ptr [rcx+28h], 0
0x18000a5bd  jz      short loc_18000A5C6
0x18000a5bf  xor     eax, eax
0x18000a5c1  jmp     loc_18000A7D4
0x18000a5c6  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a5cd  add     rsi, 18h
0x18000a5d1  mov     [rsp+290h+var_240], rsi
0x18000a5d6  mov     rcx, rsi; lpCriticalSection
0x18000a5d9  call    cs:__imp_EnterCriticalSection
0x18000a5df  mov     [rsp+290h+var_238], 1
0x18000a5e4  cmp     qword ptr [rbx+18h], 0
0x18000a5e9  jnz     loc_18000A7AD
0x18000a5ef  mov     [rsp+290h+pptlib], 0
0x18000a5f8  mov     rcx, [rbx+8]; rguid
0x18000a5fc  mov     eax, [rcx]
0x18000a5fe  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000a604  jnz     short loc_18000A67D
0x18000a606  mov     eax, [rcx+4]
0x18000a609  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000a60f  jnz     short loc_18000A67D
0x18000a611  mov     eax, [rcx+8]
0x18000a614  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000a61a  jnz     short loc_18000A67D
0x18000a61c  mov     eax, [rcx+0Ch]
0x18000a61f  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18000a625  jnz     short loc_18000A67D
0x18000a627  lea     rdx, [rbx+10h]
0x18000a62b  mov     eax, 0FFFFh
0x18000a630  cmp     [rdx], ax
0x18000a633  jnz     short loc_18000A681
0x18000a635  cmp     [rbx+12h], ax
0x18000a639  jnz     short loc_18000A681
0x18000a63b  mov     edi, 80004005h
0x18000a640  mov     r8d, 104h; nSize
0x18000a646  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18000a64b  mov     rcx, cs:hModule; hModule
0x18000a652  call    cs:__imp_GetModuleFileNameW
0x18000a658  test    eax, eax
0x18000a65a  jz      loc_18000A7AF
0x18000a660  cmp     eax, 104h
0x18000a665  jz      loc_18000A7AF
0x18000a66b  lea     rdx, [rsp+290h+pptlib]; pptlib
0x18000a670  lea     rcx, [rsp+290h+Filename]; szFile
0x18000a675  call    cs:__imp_LoadTypeLib
0x18000a67b  jmp     short loc_18000A69C
0x18000a67d  lea     rdx, [rbx+10h]
0x18000a681  lea     rax, [rsp+290h+pptlib]
0x18000a686  mov     [rsp+290h+var_270], rax; pptlib
0x18000a68b  mov     r9d, edi; lcid
0x18000a68e  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18000a693  movzx   edx, word ptr [rdx]; wVerMajor
0x18000a696  call    cs:__imp_LoadRegTypeLib
0x18000a69c  mov     edi, eax
0x18000a69e  test    eax, eax
0x18000a6a0  js      loc_18000A7AF
0x18000a6a6  mov     [rsp+290h+var_250], 0
0x18000a6af  mov     rcx, [rsp+290h+pptlib]
0x18000a6b4  mov     rax, [rcx]
0x18000a6b7  lea     r8, [rsp+290h+var_250]
0x18000a6bc  mov     rdx, [rbx]
0x18000a6bf  mov     rax, [rax+30h]
0x18000a6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c8  mov     edi, eax
0x18000a6ca  test    eax, eax
0x18000a6cc  js      loc_18000A782
0x18000a6d2  mov     rcx, [rsp+290h+var_250]
0x18000a6d7  mov     [rsp+290h+var_260], rcx
0x18000a6dc  test    rcx, rcx
0x18000a6df  jz      short loc_18000A6F2
0x18000a6e1  mov     rax, [rcx]
0x18000a6e4  mov     rax, [rax+8]
0x18000a6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ed  mov     rcx, [rsp+290h+var_250]
0x18000a6f2  mov     [rsp+290h+var_248], 0
0x18000a6fb  mov     rax, [rcx]
0x18000a6fe  lea     r8, [rsp+290h+var_248]
0x18000a703  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000a70a  mov     rax, [rax]
0x18000a70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a712  test    eax, eax
0x18000a714  js      short loc_18000A725
0x18000a716  lea     rdx, [rsp+290h+var_248]
0x18000a71b  lea     rcx, [rsp+290h+var_260]
0x18000a720  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x18000a725  mov     rax, [rsp+290h+var_260]
0x18000a72a  mov     [rsp+290h+var_260], 0
0x18000a733  mov     [rbx+18h], rax
0x18000a737  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a73e  lea     rcx, [rax+8]
0x18000a742  neg     rax
0x18000a745  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18000a748  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18000a74b  mov     r8, rbx; unsigned __int64
0x18000a74e  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000a753  nop
0x18000a754  mov     rcx, [rsp+290h+var_248]
0x18000a759  test    rcx, rcx
0x18000a75c  jz      short loc_18000A76B
0x18000a75e  mov     rax, [rcx]
0x18000a761  mov     rax, [rax+10h]
0x18000a765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a76a  nop
0x18000a76b  mov     rcx, [rsp+290h+var_260]
0x18000a770  test    rcx, rcx
0x18000a773  jz      short loc_18000A782
0x18000a775  mov     rax, [rcx]
0x18000a778  mov     rax, [rax+10h]
0x18000a77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a781  nop
0x18000a782  mov     rcx, [rsp+290h+pptlib]
0x18000a787  mov     rax, [rcx]
0x18000a78a  mov     rax, [rax+10h]
0x18000a78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a793  nop
0x18000a794  mov     rcx, [rsp+290h+var_250]
0x18000a799  test    rcx, rcx
0x18000a79c  jz      short loc_18000A7AB
0x18000a79e  mov     rax, [rcx]
0x18000a7a1  mov     rax, [rax+10h]
0x18000a7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7aa  nop
0x18000a7ab  jmp     short loc_18000A7AF
0x18000a7ad  xor     edi, edi
0x18000a7af  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18000a7b3  test    rdx, rdx
0x18000a7b6  jz      short loc_18000A7C9
0x18000a7b8  cmp     qword ptr [rbx+28h], 0
0x18000a7bd  jnz     short loc_18000A7C9
0x18000a7bf  mov     rcx, rbx; this
0x18000a7c2  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000a7c7  mov     edi, eax
0x18000a7c9  mov     rcx, rsi; lpCriticalSection
0x18000a7cc  call    cs:__imp_LeaveCriticalSection
0x18000a7d2  mov     eax, edi
0x18000a7d4  mov     rcx, [rbp+190h+var_20]
0x18000a7db  xor     rcx, rsp; StackCookie
0x18000a7de  call    __security_check_cookie
0x18000a7e3  mov     rbx, [rsp+290h+arg_10]
0x18000a7eb  add     rsp, 280h
0x18000a7f2  pop     rdi
0x18000a7f3  pop     rsi
0x18000a7f4  pop     rbp
0x18000a7f5  retn
```
