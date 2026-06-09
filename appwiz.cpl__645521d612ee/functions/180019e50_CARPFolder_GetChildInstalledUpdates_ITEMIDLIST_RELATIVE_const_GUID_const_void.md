# CARPFolder::_GetChildInstalledUpdates(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)

- ea: `0x180019e50`
- end: `0x180019f4e`
- name: `?_GetChildInstalledUpdates@CARPFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: `int(CARPFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180011de0`
- `0x1800136f0`

## callees

- `0x180008cf8`
- `0x18001732c`
- `0x180019e50`
- `0x180059010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180019f15`
- `SHELL32!__imp_ILFree` at `0x180019f15`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019e93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019e93`

## pseudocode

```c
__int64 __fastcall CARPFolder::_GetChildInstalledUpdates(
        CARPFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _GUID *a3,
        void **a4)
{
  LPVOID *ppv; // rdi
  HRESULT Instance; // ebx
  __int64 (__fastcall ***v10)(LPVOID, GUID *, _QWORD *); // rcx
  const struct _ITEMIDLIST_ABSOLUTE *v11; // rcx
  _QWORD v13[9]; // [rsp+30h] [rbp-48h] BYREF
  LPITEMIDLIST pidl; // [rsp+80h] [rbp+8h] BYREF

  ppv = (LPVOID *)((char *)this + 152);
  if ( *((_QWORD *)this + 19) )
    return (unsigned int)(**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))*ppv)(*ppv, a3, a4);
  Instance = CoCreateInstance(&CLSID_AppUpdateFolder, 0, 1u, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, ppv);
  if ( Instance >= 0 )
  {
    v10 = (__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))*ppv;
    v13[0] = 0;
    Instance = (**v10)(v10, &GUID_000214ea_0000_0000_c000_000000000046, v13);
    if ( Instance >= 0 )
    {
      v11 = (const struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)this + 15);
      pidl = 0;
      Instance = SHILCombine(v11, a2, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, LPITEMIDLIST))(*(_QWORD *)v13[0] + 32LL))(v13[0], pidl);
        ILFree(pidl);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
    if ( Instance >= 0 )
      return (unsigned int)(**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))*ppv)(*ppv, a3, a4);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180019e50  push    rbx
0x180019e52  push    rbp
0x180019e53  push    rsi
0x180019e54  push    rdi
0x180019e55  push    r14
0x180019e57  push    r15
0x180019e59  sub     rsp, 48h
0x180019e5d  lea     rdi, [rcx+98h]
0x180019e64  mov     r14, r9
0x180019e67  cmp     qword ptr [rdi], 0
0x180019e6b  mov     r15, r8
0x180019e6e  mov     rbp, rdx
0x180019e71  mov     rsi, rcx
0x180019e74  jnz     loc_180019F29
0x180019e7a  xor     edx, edx; pUnkOuter
0x180019e7c  mov     [rsp+78h+ppv], rdi; ppv
0x180019e81  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x180019e88  lea     rcx, CLSID_AppUpdateFolder; rclsid
0x180019e8f  lea     r8d, [rdx+1]; dwClsContext
0x180019e93  call    cs:__imp_CoCreateInstance
0x180019e99  mov     ebx, eax
0x180019e9b  test    eax, eax
0x180019e9d  js      loc_180019F3F
0x180019ea3  mov     rcx, [rdi]
0x180019ea6  lea     r8, [rsp+78h+var_48]
0x180019eab  mov     [rsp+78h+var_48], 0
0x180019eb4  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x180019ebb  mov     rax, [rcx]
0x180019ebe  mov     rax, [rax]
0x180019ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ec6  mov     ebx, eax
0x180019ec8  test    eax, eax
0x180019eca  js      short loc_180019F1B
0x180019ecc  mov     rcx, [rsi+78h]; struct _ITEMIDLIST_ABSOLUTE *
0x180019ed0  lea     r8, [rsp+78h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180019ed8  mov     rdx, rbp; struct _ITEMIDLIST_RELATIVE *
0x180019edb  mov     [rsp+78h+pidl], 0
0x180019ee7  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180019eec  mov     ebx, eax
0x180019eee  test    eax, eax
0x180019ef0  js      short loc_180019F1B
0x180019ef2  mov     rcx, [rsp+78h+var_48]
0x180019ef7  mov     rdx, [rsp+78h+pidl]
0x180019eff  mov     rax, [rcx]
0x180019f02  mov     rax, [rax+20h]
0x180019f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f0b  mov     rcx, [rsp+78h+pidl]; pidl
0x180019f13  mov     ebx, eax
0x180019f15  call    cs:__imp_ILFree
0x180019f1b  lea     rcx, [rsp+78h+var_48]
0x180019f20  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019f25  test    ebx, ebx
0x180019f27  js      short loc_180019F3F
0x180019f29  mov     rcx, [rdi]
0x180019f2c  mov     r8, r14
0x180019f2f  mov     rdx, r15
0x180019f32  mov     rax, [rcx]
0x180019f35  mov     rax, [rax]
0x180019f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f3d  mov     ebx, eax
0x180019f3f  mov     eax, ebx
0x180019f41  add     rsp, 48h
0x180019f45  pop     r15
0x180019f47  pop     r14
0x180019f49  pop     rdi
0x180019f4a  pop     rsi
0x180019f4b  pop     rbp
0x180019f4c  pop     rbx
0x180019f4d  retn
```
