# CSyncDelegateFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x180046420`
- end: `0x18004658e`
- name: `?GetDetailsEx@CSyncDelegateFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `366`
- prototype: `int(CSyncDelegateFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b310`
- `0x180012e54`
- `0x1800133b0`
- `0x1800134dc`
- `0x18002f314`
- `0x180046420`
- `0x18004f2a8`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800464eb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800464eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004653b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004653b`
- `OLEAUT32!__imp_VariantInit` at `0x18004644d`
- `OLEAUT32!__imp_VariantInit` at `0x18004644d`

## pseudocode

```c
__int64 __fastcall CSyncDelegateFolder::GetDetailsEx(
        unsigned __int64 this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v11; // rax
  HRESULT Instance; // ebx
  LPVOID *ppv; // rax
  _QWORD v15[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  VariantInit(a4);
  if ( a3->pid == 10 )
  {
    v8 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
      v8 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
    if ( !v8 )
      return (unsigned int)GetNameDetails(this & -(__int64)(this != 8), a3, a2, a4);
  }
  if ( a3->pid == 24 )
  {
    v9 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ParsingName.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ParsingName.fmtid.Data1 )
      v9 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ParsingName.fmtid.Data4;
    if ( !v9 )
      return (unsigned int)GetNameDetails(this & -(__int64)(this != 8), a3, a2, a4);
    goto LABEL_18;
  }
  if ( a3->pid != 4 )
    goto LABEL_18;
  v11 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_InfoTip.fmtid.Data1 )
    v11 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_InfoTip.fmtid.Data4;
  if ( v11 )
  {
LABEL_18:
    ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(v15);
    ppv = (LPVOID *)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(v15);
    Instance = CoCreateInstance((const IID *const)(this + 72), 0, 1u, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, ppv);
    if ( Instance >= 0 )
      Instance = (*(__int64 (__fastcall **)(_QWORD, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *))(*(_QWORD *)v15[0] + 136LL))(
                   v15[0],
                   a2,
                   a3,
                   a4);
    ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)v15);
    return (unsigned int)Instance;
  }
  if ( LoadStringW(g_hmodThisDll, *(_DWORD *)(this + 92), Buffer, 260) )
    return (unsigned int)InitVariantFromString(Buffer, a4);
  Instance = ResultFromKnownLastError();
  if ( Instance >= 0 )
    return (unsigned int)InitVariantFromString(Buffer, a4);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180046420  push    rbx
0x180046422  push    rbp
0x180046423  push    rsi
0x180046424  push    rdi
0x180046425  sub     rsp, 268h
0x18004642c  mov     rax, cs:__security_cookie
0x180046433  xor     rax, rsp
0x180046436  mov     [rsp+288h+var_38], rax
0x18004643e  mov     rbx, rcx
0x180046441  mov     rsi, r9
0x180046444  mov     rcx, r9; pvarg
0x180046447  mov     rdi, r8
0x18004644a  mov     rbp, rdx
0x18004644d  call    cs:__imp_VariantInit
0x180046453  cmp     dword ptr [rdi+10h], 0Ah
0x180046457  jnz     short loc_180046475
0x180046459  mov     rax, [rdi]
0x18004645c  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180046463  jnz     short loc_180046470
0x180046465  mov     rax, [rdi+8]
0x180046469  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x180046470  test    rax, rax
0x180046473  jz      short loc_180046497
0x180046475  cmp     dword ptr [rdi+10h], 18h
0x180046479  jnz     short loc_1800464B4
0x18004647b  mov     rax, [rdi]
0x18004647e  sub     rax, qword ptr cs:PKEY_ParsingName.fmtid.Data1
0x180046485  jnz     short loc_180046492
0x180046487  mov     rax, [rdi+8]
0x18004648b  sub     rax, qword ptr cs:PKEY_ParsingName.fmtid.Data4
0x180046492  test    rax, rax
0x180046495  jnz     short loc_180046511
0x180046497  lea     rax, [rbx-8]
0x18004649b  mov     r9, rsi
0x18004649e  neg     rax
0x1800464a1  mov     r8, rbp
0x1800464a4  mov     rdx, rdi
0x1800464a7  sbb     rcx, rcx
0x1800464aa  and     rcx, rbx
0x1800464ad  call    GetNameDetails
0x1800464b2  jmp     short loc_18004650D
0x1800464b4  cmp     dword ptr [rdi+10h], 4
0x1800464b8  jnz     short loc_180046511
0x1800464ba  mov     rax, [rdi]
0x1800464bd  sub     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data1
0x1800464c4  jnz     short loc_1800464D1
0x1800464c6  mov     rax, [rdi+8]
0x1800464ca  sub     rax, qword ptr cs:PKEY_PropList_InfoTip.fmtid.Data4
0x1800464d1  test    rax, rax
0x1800464d4  jnz     short loc_180046511
0x1800464d6  mov     edx, [rbx+5Ch]; uID
0x1800464d9  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x1800464de  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800464e5  mov     r9d, 104h; cchBufferMax
0x1800464eb  call    cs:__imp_LoadStringW
0x1800464f1  test    eax, eax
0x1800464f3  jnz     short loc_180046500
0x1800464f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800464fa  mov     ebx, eax
0x1800464fc  test    eax, eax
0x1800464fe  js      short loc_180046570
0x180046500  mov     rdx, rsi; struct tagVARIANT *
0x180046503  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x180046508  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18004650d  mov     ebx, eax
0x18004650f  jmp     short loc_180046570
0x180046511  lea     rcx, [rsp+288h+var_258]; void *
0x180046516  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x18004651b  lea     rcx, [rsp+288h+var_258]; void *
0x180046520  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180046525  xor     edx, edx; pUnkOuter
0x180046527  mov     [rsp+288h+ppv], rax; ppv
0x18004652c  lea     rcx, [rbx+48h]; rclsid
0x180046530  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x180046537  lea     r8d, [rdx+1]; dwClsContext
0x18004653b  call    cs:__imp_CoCreateInstance
0x180046541  mov     ebx, eax
0x180046543  test    eax, eax
0x180046545  js      short loc_180046566
0x180046547  mov     rcx, [rsp+288h+var_258]
0x18004654c  mov     r9, rsi
0x18004654f  mov     r8, rdi
0x180046552  mov     rdx, rbp
0x180046555  mov     rax, [rcx]
0x180046558  mov     rax, [rax+88h]
0x18004655f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046564  mov     ebx, eax
0x180046566  lea     rcx, [rsp+288h+var_258]
0x18004656b  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180046570  mov     eax, ebx
0x180046572  mov     rcx, [rsp+288h+var_38]
0x18004657a  xor     rcx, rsp; StackCookie
0x18004657d  call    __security_check_cookie
0x180046582  add     rsp, 268h
0x180046589  pop     rdi
0x18004658a  pop     rsi
0x18004658b  pop     rbp
0x18004658c  pop     rbx
0x18004658d  retn
```
