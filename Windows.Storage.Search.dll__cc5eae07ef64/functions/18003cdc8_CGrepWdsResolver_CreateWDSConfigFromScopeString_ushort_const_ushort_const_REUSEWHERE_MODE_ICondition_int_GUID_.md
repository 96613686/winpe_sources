# CGrepWdsResolver::_CreateWDSConfigFromScopeString(ushort const *,ushort const *,REUSEWHERE_MODE,ICondition *,int *,_GUID const &,void * *)

- ea: `0x18003cdc8`
- end: `0x18003cf6f`
- name: `?_CreateWDSConfigFromScopeString@CGrepWdsResolver@@AEAAJPEBG0W4REUSEWHERE_MODE@@PEAUICondition@@PEAHAEBU_GUID@@PEAPEAX@Z`
- size: `423`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct ICondition *, _DWORD *, struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800616c0`
- `0x1800996c0`
- `0x1800999a0`

## callees

- `0x18003cd04`
- `0x18003cdc8`
- `0x18003cf78`
- `0x18003e03c`
- `0x18003e5a0`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ceb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cf17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ceb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cf17`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ce9d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ce9d`

## string_xrefs

- `0x18003ce85`: `DoNotComputeExpensiveProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGrepWdsResolver::_CreateWDSConfigFromScopeString(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        struct ICondition *a5,
        _DWORD *a6,
        struct _GUID *a7,
        void **a8)
{
  int PropertyStoreForWDS; // ebx
  const wchar_t *v11; // rdx
  const unsigned __int16 *v12; // rdx
  HKEY v13; // rcx
  CGrepWdsResolver *v14; // rcx
  struct ICondition *v16; // [rsp+20h] [rbp-50h]
  struct INamedPropertyStore *v17; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]

  *a8 = 0;
  *a6 = 0;
  v17 = 0;
  PropertyStoreForWDS = CGrepWdsResolver::_CreatePropertyStoreForWDS(
                          (CGrepWdsResolver *)a1,
                          a1 + 30,
                          a3,
                          a2,
                          (const struct _GUID *)v16,
                          (void **)&v17);
  if ( PropertyStoreForWDS >= 0 )
  {
    if ( (unsigned int)(a4 - 1) > 1 )
      goto LABEL_8;
    *(_OWORD *)pvar = 0;
    v20 = 0;
    LOWORD(pvar[0]) = 11;
    LOWORD(pvar[1]) = -1;
    PropertyStoreForWDS = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))v17->lpVtbl->SetNamedValue)(
                            v17,
                            L"SkipInternalReuse",
                            pvar);
    if ( PropertyStoreForWDS >= 0 )
    {
      v11 = L"DoNotComputeExpensiveProperties";
      if ( a4 == 2 )
        v11 = L"WinRTDataModel";
      PropertyStoreForWDS = ((__int64 (__fastcall *)(struct INamedPropertyStore *, const wchar_t *, PROPVARIANT *))v17->lpVtbl->SetNamedValue)(
                              v17,
                              v11,
                              pvar);
    }
    PropVariantClear(pvar);
    if ( PropertyStoreForWDS >= 0 )
    {
LABEL_8:
      pv = 0;
      CoTaskMemFree(0);
      PropertyStoreForWDS = CGrepWdsResolver::_GenerateMergeId((CGrepWdsResolver *)a1, L"WDS", (unsigned __int16 **)&pv);
      if ( PropertyStoreForWDS >= 0 )
      {
        *(_OWORD *)pvar = 0;
        PropertyStoreForWDS = GetExtensionClassId(v13, v12, L"CollatorDataSource", (struct _GUID *)pvar);
        if ( PropertyStoreForWDS >= 0 )
        {
          PropertyStoreForWDS = CGrepWdsResolver::_CreateConfig(
                                  v14,
                                  (const struct _GUID *)pvar,
                                  (const unsigned __int16 *)pv,
                                  v17,
                                  a5,
                                  a7,
                                  a8);
          if ( PropertyStoreForWDS >= 0 )
            *a6 = 1;
        }
      }
      CoTaskMemFree(pv);
    }
  }
  if ( v17 )
    ((void (__fastcall *)(struct INamedPropertyStore *))v17->lpVtbl->Release)(v17);
  return (unsigned int)PropertyStoreForWDS;
}

```

## disassembly

```asm
0x18003cdc8  mov     [rsp-38h+arg_18], rbx
0x18003cdcd  push    rbp
0x18003cdce  push    rsi
0x18003cdcf  push    rdi
0x18003cdd0  push    r12
0x18003cdd2  push    r13
0x18003cdd4  push    r14
0x18003cdd6  push    r15
0x18003cdd8  mov     rbp, rsp
0x18003cddb  sub     rsp, 70h
0x18003cddf  mov     rax, cs:__security_cookie
0x18003cde6  xor     rax, rsp
0x18003cde9  mov     [rbp+var_8], rax
0x18003cded  mov     edi, r9d
0x18003cdf0  mov     r9, rdx; unsigned __int16 *
0x18003cdf3  mov     r14, rcx
0x18003cdf6  mov     r12, [rbp+arg_20]
0x18003cdfa  mov     rsi, [rbp+arg_28]
0x18003cdfe  mov     r13, [rbp+arg_30]
0x18003ce02  mov     r15, [rbp+arg_38]
0x18003ce06  xor     eax, eax
0x18003ce08  mov     [r15], rax
0x18003ce0b  mov     [rsi], eax
0x18003ce0d  mov     [rbp+var_30], rax
0x18003ce11  lea     rdx, [rcx+3Ch]; unsigned __int16 *
0x18003ce15  lea     rax, [rbp+var_30]
0x18003ce19  mov     [rsp+70h+var_48], rax; void **
0x18003ce1e  call    ?_CreatePropertyStoreForWDS@CGrepWdsResolver@@AEAAJPEBG00AEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_CreatePropertyStoreForWDS(ushort const *,ushort const *,ushort const *,_GUID const &,void * *)
0x18003ce23  mov     ebx, eax
0x18003ce25  test    eax, eax
0x18003ce27  js      loc_18003CF1E
0x18003ce2d  lea     eax, [rdi-1]
0x18003ce30  cmp     eax, 1
0x18003ce33  ja      short loc_18003CEA7
0x18003ce35  xorps   xmm0, xmm0
0x18003ce38  xor     eax, eax
0x18003ce3a  movups  xmmword ptr [rbp+pvar], xmm0
0x18003ce3e  mov     [rbp+var_10], rax
0x18003ce42  mov     eax, 0Bh
0x18003ce47  mov     word ptr [rbp+pvar], ax
0x18003ce4b  or      eax, 0FFFFFFFFh
0x18003ce4e  mov     word ptr [rbp+pvar+8], ax
0x18003ce52  mov     rcx, [rbp+var_30]
0x18003ce56  mov     rax, [rcx]
0x18003ce59  lea     r8, [rbp+pvar]
0x18003ce5d  lea     rdx, aSkipinternalre; "SkipInternalReuse"
0x18003ce64  mov     rax, [rax+20h]
0x18003ce68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce6d  mov     ebx, eax
0x18003ce6f  test    eax, eax
0x18003ce71  js      short loc_18003CE99
0x18003ce73  mov     rcx, [rbp+var_30]
0x18003ce77  lea     r8, [rbp+pvar]
0x18003ce7b  mov     rax, [rcx]
0x18003ce7e  mov     rax, [rax+20h]
0x18003ce82  cmp     edi, 2
0x18003ce85  lea     rdx, aDonotcomputeex; "DoNotComputeExpensiveProperties"
0x18003ce8c  jz      loc_18003CF5A
0x18003ce92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce97  mov     ebx, eax
0x18003ce99  lea     rcx, [rbp+pvar]; pvar
0x18003ce9d  call    cs:__imp_PropVariantClear
0x18003cea3  test    ebx, ebx
0x18003cea5  js      short loc_18003CF1E
0x18003cea7  mov     [rbp+pv], 0
0x18003ceaf  xor     ecx, ecx; pv
0x18003ceb1  call    cs:__imp_CoTaskMemFree
0x18003ceb7  lea     r8, [rbp+pv]; unsigned __int16 **
0x18003cebb  lea     rdx, aWds; "WDS"
0x18003cec2  mov     rcx, r14; this
0x18003cec5  call    ?_GenerateMergeId@CGrepWdsResolver@@AEAAJPEAGPEAPEAG@Z; CGrepWdsResolver::_GenerateMergeId(ushort *,ushort * *)
0x18003ceca  mov     ebx, eax
0x18003cecc  test    eax, eax
0x18003cece  js      short loc_18003CF13
0x18003ced0  xorps   xmm0, xmm0
0x18003ced3  movups  xmmword ptr [rbp+pvar], xmm0
0x18003ced7  lea     r9, [rbp+pvar]; struct _GUID *
0x18003cedb  lea     r8, aCollatordataso; "CollatorDataSource"
0x18003cee2  call    ?GetExtensionClassId@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z; GetExtensionClassId(HKEY__ *,ushort const *,ushort const *,_GUID *)
0x18003cee7  mov     ebx, eax
0x18003cee9  test    eax, eax
0x18003ceeb  js      short loc_18003CF13
0x18003ceed  mov     [rsp+70h+var_40], r15; void **
0x18003cef2  mov     [rsp+70h+var_48], r13; struct _GUID *
0x18003cef7  mov     [rsp+70h+var_50], r12; struct ICondition *
0x18003cefc  mov     r9, [rbp+var_30]; struct INamedPropertyStore *
0x18003cf00  mov     r8, [rbp+pv]; unsigned __int16 *
0x18003cf04  lea     rdx, [rbp+pvar]; struct _GUID *
0x18003cf08  call    ?_CreateConfig@CGrepWdsResolver@@AEAAJAEBU_GUID@@PEBGPEAUINamedPropertyStore@@PEAUICondition@@0PEAPEAX@Z; CGrepWdsResolver::_CreateConfig(_GUID const &,ushort const *,INamedPropertyStore *,ICondition *,_GUID const &,void * *)
0x18003cf0d  mov     ebx, eax
0x18003cf0f  test    eax, eax
0x18003cf11  jns     short loc_18003CF66
0x18003cf13  mov     rcx, [rbp+pv]; pv
0x18003cf17  call    cs:__imp_CoTaskMemFree
0x18003cf1d  nop
0x18003cf1e  mov     rcx, [rbp+var_30]
0x18003cf22  test    rcx, rcx
0x18003cf25  jz      short loc_18003CF34
0x18003cf27  mov     rax, [rcx]
0x18003cf2a  mov     rax, [rax+10h]
0x18003cf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf33  nop
0x18003cf34  mov     eax, ebx
0x18003cf36  mov     rcx, [rbp+var_8]
0x18003cf3a  xor     rcx, rsp; StackCookie
0x18003cf3d  call    __security_check_cookie
0x18003cf42  mov     rbx, [rsp+70h+arg_18]
0x18003cf4a  add     rsp, 70h
0x18003cf4e  pop     r15
0x18003cf50  pop     r14
0x18003cf52  pop     r13
0x18003cf54  pop     r12
0x18003cf56  pop     rdi
0x18003cf57  pop     rsi
0x18003cf58  pop     rbp
0x18003cf59  retn
0x18003cf5a  lea     rdx, aWinrtdatamodel; "WinRTDataModel"
0x18003cf61  jmp     loc_18003CE92
0x18003cf66  mov     dword ptr [rsi], 1
0x18003cf6c  jmp     short loc_18003CF13
```
