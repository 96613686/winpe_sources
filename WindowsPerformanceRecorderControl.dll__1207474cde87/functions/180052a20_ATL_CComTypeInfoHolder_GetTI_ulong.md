# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180052a20`
- end: `0x180052cc0`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `672`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180052834`
- `0x180052ee4`
- `0x180053318`

## callees

- `0x180027850`
- `0x180040a04`
- `0x1800462a0`
- `0x18004ece0`
- `0x180050f70`
- `0x180051a28`
- `0x180052a20`
- `0x1800533bc`
- `0x180053680`
- `0x1800538f0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180052ae7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180052ae7`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180052b10`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180052b10`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180052b3e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180052b3e`

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
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((const struct _GUID **)this + 1))
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
0x180052a20  mov     rax, rsp
0x180052a23  push    rbp
0x180052a24  push    rsi
0x180052a25  push    rdi
0x180052a26  lea     rbp, [rax-1A8h]
0x180052a2d  sub     rsp, 290h
0x180052a34  mov     [rsp+2A0h+var_240], 0FFFFFFFFFFFFFFFEh
0x180052a3d  mov     [rax+18h], rbx
0x180052a41  mov     rax, cs:__security_cookie
0x180052a48  xor     rax, rsp
0x180052a4b  mov     [rbp+1A0h+var_20], rax
0x180052a52  mov     esi, edx
0x180052a54  mov     rbx, rcx
0x180052a57  cmp     qword ptr [rcx+18h], 0
0x180052a5c  jz      short loc_180052A6C
0x180052a5e  cmp     qword ptr [rcx+28h], 0
0x180052a63  jz      short loc_180052A6C
0x180052a65  xor     eax, eax
0x180052a67  jmp     loc_180052C9E
0x180052a6c  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180052a73  add     rax, 18h
0x180052a77  mov     [rsp+2A0h+var_250], rax
0x180052a7c  mov     byte ptr [rsp+2A0h+var_248], 0
0x180052a81  lea     rcx, [rsp+2A0h+var_250]
0x180052a86  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180052a8b  mov     edi, eax
0x180052a8d  test    eax, eax
0x180052a8f  js      loc_180052C92
0x180052a95  cmp     qword ptr [rbx+18h], 0
0x180052a9a  jnz     loc_180052C76
0x180052aa0  mov     [rsp+2A0h+pptlib], 0
0x180052aa9  mov     rdx, [rbx+8]; struct _GUID *
0x180052aad  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x180052ab4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180052ab9  test    eax, eax
0x180052abb  jz      short loc_180052B24
0x180052abd  mov     eax, 0FFFFh
0x180052ac2  cmp     [rbx+10h], ax
0x180052ac6  jnz     short loc_180052B24
0x180052ac8  cmp     [rbx+12h], ax
0x180052acc  jnz     short loc_180052B24
0x180052ace  mov     edi, 80004005h
0x180052ad3  mov     esi, 104h
0x180052ad8  mov     r8d, esi; nSize
0x180052adb  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x180052ae0  mov     rcx, cs:hModule; hModule
0x180052ae7  call    cs:__imp_GetModuleFileNameW
0x180052aed  test    eax, eax
0x180052aef  jz      loc_180052C78
0x180052af5  cmp     eax, esi
0x180052af7  jz      loc_180052C78
0x180052afd  mov     [rsp+2A0h+var_268], 0
0x180052b06  lea     rdx, [rsp+2A0h+pptlib]; pptlib
0x180052b0b  lea     rcx, [rsp+2A0h+Filename]; szFile
0x180052b10  call    cs:__imp_LoadTypeLib
0x180052b16  mov     edi, eax
0x180052b18  lea     rcx, [rsp+2A0h+var_268]
0x180052b1d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180052b22  jmp     short loc_180052B46
0x180052b24  lea     rax, [rsp+2A0h+pptlib]
0x180052b29  mov     [rsp+20h], rax; pptlib
0x180052b2e  mov     r9d, esi; lcid
0x180052b31  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180052b36  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x180052b3a  mov     rcx, [rbx+8]; rguid
0x180052b3e  call    cs:__imp_LoadRegTypeLib
0x180052b44  mov     edi, eax
0x180052b46  test    edi, edi
0x180052b48  js      loc_180052C78
0x180052b4e  mov     [rsp+2A0h+var_268], 0
0x180052b57  mov     rcx, [rsp+2A0h+pptlib]
0x180052b5c  mov     rax, [rcx]
0x180052b5f  lea     r8, [rsp+2A0h+var_268]
0x180052b64  mov     rdx, [rbx]
0x180052b67  mov     rax, [rax+30h]
0x180052b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b70  mov     edi, eax
0x180052b72  test    eax, eax
0x180052b74  js      loc_180052C58
0x180052b7a  mov     rcx, [rsp+2A0h+var_268]
0x180052b7f  mov     [rsp+2A0h+var_270], rcx
0x180052b84  test    rcx, rcx
0x180052b87  jz      short loc_180052B9A
0x180052b89  mov     rax, [rcx]
0x180052b8c  mov     rax, [rax+8]
0x180052b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b95  mov     rcx, [rsp+2A0h+var_268]
0x180052b9a  mov     [rsp+2A0h+var_260], 0
0x180052ba3  mov     rax, [rcx]
0x180052ba6  lea     r8, [rsp+2A0h+var_260]
0x180052bab  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180052bb2  mov     rax, [rax]
0x180052bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052bba  test    eax, eax
0x180052bbc  js      short loc_180052C14
0x180052bbe  mov     rdx, [rsp+2A0h+var_260]
0x180052bc3  lea     rcx, [rsp+2A0h+var_270]
0x180052bc8  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180052bcd  test    al, al
0x180052bcf  jnz     short loc_180052C14
0x180052bd1  mov     rcx, [rsp+2A0h+var_260]
0x180052bd6  mov     rsi, [rsp+2A0h+var_270]
0x180052bdb  mov     [rsp+2A0h+var_270], 0
0x180052be4  test    rcx, rcx
0x180052be7  jz      short loc_180052C00
0x180052be9  mov     rax, [rcx]
0x180052bec  lea     r8, [rsp+2A0h+var_270]
0x180052bf1  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180052bf8  mov     rax, [rax]
0x180052bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c00  test    rsi, rsi
0x180052c03  jz      short loc_180052C14
0x180052c05  mov     rax, [rsi]
0x180052c08  mov     rcx, rsi
0x180052c0b  mov     rax, [rax+10h]
0x180052c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c14  mov     rax, [rsp+2A0h+var_270]
0x180052c19  mov     [rsp+2A0h+var_270], 0
0x180052c22  mov     [rbx+18h], rax
0x180052c26  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180052c2d  lea     rcx, [rax+8]
0x180052c31  neg     rax
0x180052c34  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180052c37  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180052c3a  mov     r8, rbx; unsigned __int64
0x180052c3d  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180052c42  nop
0x180052c43  lea     rcx, [rsp+2A0h+var_260]
0x180052c48  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052c4d  nop
0x180052c4e  lea     rcx, [rsp+2A0h+var_270]
0x180052c53  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052c58  mov     rcx, [rsp+2A0h+pptlib]
0x180052c5d  mov     rax, [rcx]
0x180052c60  mov     rax, [rax+10h]
0x180052c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c69  nop
0x180052c6a  lea     rcx, [rsp+2A0h+var_268]
0x180052c6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052c74  jmp     short loc_180052C78
0x180052c76  xor     edi, edi
0x180052c78  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180052c7c  test    rdx, rdx
0x180052c7f  jz      short loc_180052C92
0x180052c81  cmp     qword ptr [rbx+28h], 0
0x180052c86  jnz     short loc_180052C92
0x180052c88  mov     rcx, rbx; this
0x180052c8b  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180052c90  mov     edi, eax
0x180052c92  lea     rcx, [rsp+2A0h+var_250]
0x180052c97  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180052c9c  mov     eax, edi
0x180052c9e  mov     rcx, [rbp+1A0h+var_20]
0x180052ca5  xor     rcx, rsp; StackCookie
0x180052ca8  call    __security_check_cookie
0x180052cad  mov     rbx, [rsp+2A0h+arg_10]
0x180052cb5  add     rsp, 290h
0x180052cbc  pop     rdi
0x180052cbd  pop     rsi
0x180052cbe  pop     rbp
0x180052cbf  retn
```
