# GetShellFolderTypeFromItem(IShellItem *,_GUID *)

- ea: `0x1800bc310`
- end: `0x1800bc605`
- name: `?GetShellFolderTypeFromItem@@YAJPEAUIShellItem@@PEAU_GUID@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(IUnknown *punk, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800bd480`

## callees

- `0x1800486e0`
- `0x18006d81c`
- `0x180071dc0`
- `0x1800bc26c`
- `0x1800bc310`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800bc482`
- `Windows.Storage!ILFree` at `0x1800bc589`
- `Windows.Storage!ILFree` at `0x1800bc482`
- `Windows.Storage!ILFree` at `0x1800bc589`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800bc3d3`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800bc3d3`
- `Windows.Storage!__imp_SHGetFolderTypeFromCanonicalName` at `0x1800bc464`
- `Windows.Storage!__imp_SHGetFolderTypeFromCanonicalName` at `0x1800bc464`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1800bc40d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1800bc40d`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800bc432`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800bc450`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800bc432`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800bc450`

## pseudocode

```c
__int64 __fastcall GetShellFolderTypeFromItem(IUnknown *punk, struct _GUID *a2)
{
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT Str; // ebx
  struct IUnknownVtbl *v6; // rax
  enum tagPERCEIVED PerceivedType; // esi
  GUID v8; // xmm0
  IPropertyBag *propBag; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR value[264]; // [rsp+70h] [rbp-90h] BYREF

  lpVtbl = punk->lpVtbl;
  v12 = 0;
  if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl[1].QueryInterface)(
         punk,
         0,
         &BHID_SFViewObject,
         &GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb,
         &v12) < 0 )
    goto LABEL_31;
  memset(v13, 0, sizeof(v13));
  Str = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v12 + 24LL))(v12, v13);
  if ( Str >= 0 )
    *a2 = (struct _GUID)v13[0];
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( Str < 0 )
  {
LABEL_31:
    ppidl = 0;
    if ( SHGetIDListFromObject(punk, &ppidl) < 0 )
      goto LABEL_32;
    propBag = 0;
    Str = SHGetViewStatePropertyBag(ppidl, L"Shell", 5u, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&propBag);
    if ( Str >= 0 )
    {
      if ( PSPropertyBag_ReadStr(propBag, L"FolderType", value, 260) >= 0
        || (Str = PSPropertyBag_ReadStr(propBag, L"SniffedFolderType", value, 260), Str >= 0) )
      {
        Str = SHGetFolderTypeFromCanonicalName(value, a2);
      }
      ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
    }
    ILFree(ppidl);
    if ( Str < 0 )
    {
LABEL_32:
      v6 = punk->lpVtbl;
      propBag = 0;
      if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, IPropertyBag **))v6[1].QueryInterface)(
             punk,
             0,
             &BHID_SFObject,
             &GUID_000214e6_0000_0000_c000_000000000046,
             &propBag) < 0 )
        goto LABEL_17;
      ppidl = 0;
      if ( ((__int64 (__fastcall *)(IPropertyBag *, GUID *, LPITEMIDLIST *))propBag->lpVtbl->QueryInterface)(
             propBag,
             &GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48,
             &ppidl) < 0
        || (Str = (*(__int64 (__fastcall **)(LPITEMIDLIST, struct _GUID *))(*(_QWORD *)&ppidl->mkid.cb + 24LL))(
                    ppidl,
                    a2),
            (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl),
            Str < 0) )
      {
        Str = GetShellFolderTypeFromRegistry((struct IShellFolder *)propBag, a2);
      }
      ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
      if ( Str < 0 )
      {
LABEL_17:
        propBag = 0;
        ppidl = 0;
        if ( (int)GetParentAndChildIDListFromItem(punk, &GUID_000214e6_0000_0000_c000_000000000046, &propBag, &ppidl) >= 0 )
        {
          Str = 0;
          PerceivedType = GetPerceivedType((struct IShellFolder *)propBag, (const struct _ITEMID_CHILD *)ppidl);
          ILFree(ppidl);
          ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
          switch ( PerceivedType )
          {
            case PERCEIVED_TYPE_FOLDER:
              v8 = FOLDERTYPEID_Generic;
              goto LABEL_25;
            case PERCEIVED_TYPE_IMAGE:
              v8 = FOLDERTYPEID_Pictures;
              goto LABEL_25;
            case PERCEIVED_TYPE_AUDIO:
              v8 = FOLDERTYPEID_Music;
              goto LABEL_25;
            case PERCEIVED_TYPE_DOCUMENT:
              v8 = FOLDERTYPEID_Documents;
LABEL_25:
              *a2 = v8;
              return (unsigned int)Str;
          }
        }
        return (unsigned int)-2147467259;
      }
    }
  }
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x1800bc310  mov     [rsp-8+arg_10], rbx
0x1800bc315  push    rbp
0x1800bc316  push    rsi
0x1800bc317  push    rdi
0x1800bc318  lea     rbp, [rsp-190h]
0x1800bc320  sub     rsp, 290h
0x1800bc327  mov     rax, cs:__security_cookie
0x1800bc32e  xor     rax, rsp
0x1800bc331  mov     [rbp+1A0h+var_20], rax
0x1800bc338  mov     rax, [rcx]
0x1800bc33b  lea     r9, _GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb
0x1800bc342  mov     rsi, rcx
0x1800bc345  mov     [rsp+2A0h+var_260], 0
0x1800bc34e  lea     rcx, [rsp+2A0h+var_260]
0x1800bc353  mov     rdi, rdx
0x1800bc356  mov     [rsp+2A0h+ppv], rcx
0x1800bc35b  lea     r8, BHID_SFViewObject
0x1800bc362  mov     rax, [rax+18h]
0x1800bc366  xor     edx, edx
0x1800bc368  mov     rcx, rsi
0x1800bc36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc370  test    eax, eax
0x1800bc372  js      short loc_1800BC3C2
0x1800bc374  mov     rcx, [rsp+2A0h+var_260]
0x1800bc379  lea     rdx, [rsp+2A0h+var_258]
0x1800bc37e  xorps   xmm0, xmm0
0x1800bc381  movups  [rsp+2A0h+var_258], xmm0
0x1800bc386  movups  [rsp+2A0h+var_248], xmm0
0x1800bc38b  mov     rax, [rcx]
0x1800bc38e  mov     rax, [rax+18h]
0x1800bc392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc397  mov     ebx, eax
0x1800bc399  test    eax, eax
0x1800bc39b  js      short loc_1800BC3A6
0x1800bc39d  movups  xmm0, [rsp+2A0h+var_258]
0x1800bc3a2  movdqu  xmmword ptr [rdi], xmm0
0x1800bc3a6  mov     rdx, [rsp+2A0h+var_260]
0x1800bc3ab  mov     rcx, [rdx]
0x1800bc3ae  mov     rax, [rcx+10h]
0x1800bc3b2  mov     rcx, rdx
0x1800bc3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc3ba  test    ebx, ebx
0x1800bc3bc  jns     loc_1800BC5E1
0x1800bc3c2  lea     rdx, [rsp+2A0h+ppidl]; ppidl
0x1800bc3c7  mov     [rsp+2A0h+ppidl], 0
0x1800bc3d0  mov     rcx, rsi; punk
0x1800bc3d3  call    cs:__imp_SHGetIDListFromObject
0x1800bc3d9  test    eax, eax
0x1800bc3db  js      loc_1800BC490
0x1800bc3e1  mov     rcx, [rsp+2A0h+ppidl]; pidl
0x1800bc3e6  lea     rax, [rsp+2A0h+propBag]
0x1800bc3eb  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800bc3f2  mov     [rsp+2A0h+ppv], rax; ppv
0x1800bc3f7  mov     r8d, 5; dwFlags
0x1800bc3fd  mov     [rsp+2A0h+propBag], 0
0x1800bc406  lea     rdx, pszBagName; "Shell"
0x1800bc40d  call    cs:__imp_SHGetViewStatePropertyBag
0x1800bc413  mov     ebx, eax
0x1800bc415  test    eax, eax
0x1800bc417  js      short loc_1800BC47D
0x1800bc419  mov     rcx, [rsp+2A0h+propBag]; propBag
0x1800bc41e  lea     r8, [rsp+2A0h+value]; value
0x1800bc423  mov     ebx, 104h
0x1800bc428  lea     rdx, aFoldertype; "FolderType"
0x1800bc42f  mov     r9d, ebx; characterCount
0x1800bc432  call    cs:__imp_PSPropertyBag_ReadStr
0x1800bc438  test    eax, eax
0x1800bc43a  jns     short loc_1800BC45C
0x1800bc43c  mov     rcx, [rsp+2A0h+propBag]; propBag
0x1800bc441  lea     r8, [rsp+2A0h+value]; value
0x1800bc446  mov     r9d, ebx; characterCount
0x1800bc449  lea     rdx, aSniffedfoldert; "SniffedFolderType"
0x1800bc450  call    cs:__imp_PSPropertyBag_ReadStr
0x1800bc456  mov     ebx, eax
0x1800bc458  test    eax, eax
0x1800bc45a  js      short loc_1800BC46C
0x1800bc45c  mov     rdx, rdi
0x1800bc45f  lea     rcx, [rsp+2A0h+value]
0x1800bc464  call    cs:__imp_SHGetFolderTypeFromCanonicalName
0x1800bc46a  mov     ebx, eax
0x1800bc46c  mov     rcx, [rsp+2A0h+propBag]
0x1800bc471  mov     rax, [rcx]
0x1800bc474  mov     rax, [rax+10h]
0x1800bc478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc47d  mov     rcx, [rsp+2A0h+ppidl]; pidl
0x1800bc482  call    cs:__imp_ILFree
0x1800bc488  test    ebx, ebx
0x1800bc48a  jns     loc_1800BC5E1
0x1800bc490  mov     rax, [rsi]
0x1800bc493  lea     rcx, [rsp+2A0h+propBag]
0x1800bc498  mov     [rsp+2A0h+ppv], rcx
0x1800bc49d  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800bc4a4  lea     r8, BHID_SFObject
0x1800bc4ab  mov     [rsp+2A0h+propBag], 0
0x1800bc4b4  xor     edx, edx
0x1800bc4b6  mov     rcx, rsi
0x1800bc4b9  mov     rax, [rax+18h]
0x1800bc4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc4c2  test    eax, eax
0x1800bc4c4  js      short loc_1800BC542
0x1800bc4c6  mov     rcx, [rsp+2A0h+propBag]
0x1800bc4cb  lea     r8, [rsp+2A0h+ppidl]
0x1800bc4d0  mov     [rsp+2A0h+ppidl], 0
0x1800bc4d9  lea     rdx, _GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48
0x1800bc4e0  mov     rax, [rcx]
0x1800bc4e3  mov     rax, [rax]
0x1800bc4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc4eb  test    eax, eax
0x1800bc4ed  js      short loc_1800BC51A
0x1800bc4ef  mov     rcx, [rsp+2A0h+ppidl]
0x1800bc4f4  mov     rdx, rdi
0x1800bc4f7  mov     rax, [rcx]
0x1800bc4fa  mov     rax, [rax+18h]
0x1800bc4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc503  mov     rcx, [rsp+2A0h+ppidl]
0x1800bc508  mov     ebx, eax
0x1800bc50a  mov     rax, [rcx]
0x1800bc50d  mov     rax, [rax+10h]
0x1800bc511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc516  test    ebx, ebx
0x1800bc518  jns     short loc_1800BC529
0x1800bc51a  mov     rcx, [rsp+2A0h+propBag]; struct IShellFolder *
0x1800bc51f  mov     rdx, rdi; struct _GUID *
0x1800bc522  call    ?GetShellFolderTypeFromRegistry@@YAJPEAUIShellFolder@@PEAU_GUID@@@Z; GetShellFolderTypeFromRegistry(IShellFolder *,_GUID *)
0x1800bc527  mov     ebx, eax
0x1800bc529  mov     rcx, [rsp+2A0h+propBag]
0x1800bc52e  mov     rax, [rcx]
0x1800bc531  mov     rax, [rax+10h]
0x1800bc535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc53a  test    ebx, ebx
0x1800bc53c  jns     loc_1800BC5E1
0x1800bc542  lea     r9, [rsp+2A0h+ppidl]
0x1800bc547  mov     [rsp+2A0h+propBag], 0
0x1800bc550  lea     r8, [rsp+2A0h+propBag]
0x1800bc555  mov     [rsp+2A0h+ppidl], 0
0x1800bc55e  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800bc565  mov     rcx, rsi
0x1800bc568  call    GetParentAndChildIDListFromItem
0x1800bc56d  test    eax, eax
0x1800bc56f  js      short loc_1800BC5DC
0x1800bc571  mov     rdx, [rsp+2A0h+ppidl]; struct _ITEMID_CHILD *
0x1800bc576  xor     ebx, ebx
0x1800bc578  mov     rcx, [rsp+2A0h+propBag]; struct IShellFolder *
0x1800bc57d  call    ?GetPerceivedType@@YA?AW4tagPERCEIVED@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@@Z; GetPerceivedType(IShellFolder *,_ITEMID_CHILD const *)
0x1800bc582  mov     rcx, [rsp+2A0h+ppidl]; pidl
0x1800bc587  mov     esi, eax
0x1800bc589  call    cs:__imp_ILFree
0x1800bc58f  mov     rcx, [rsp+2A0h+propBag]
0x1800bc594  mov     rdx, [rcx]
0x1800bc597  mov     rax, [rdx+10h]
0x1800bc59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5a0  cmp     esi, 0FFFFFFFFh
0x1800bc5a3  jz      short loc_1800BC5D3
0x1800bc5a5  cmp     esi, 2
0x1800bc5a8  jz      short loc_1800BC5C6
0x1800bc5aa  cmp     esi, 3
0x1800bc5ad  jz      short loc_1800BC5BD
0x1800bc5af  cmp     esi, 6
0x1800bc5b2  jnz     short loc_1800BC5DC
0x1800bc5b4  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Documents.Data1
0x1800bc5bb  jmp     short loc_1800BC5CD
0x1800bc5bd  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Music.Data1
0x1800bc5c4  jmp     short loc_1800BC5CD
0x1800bc5c6  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Pictures.Data1
0x1800bc5cd  movdqu  xmmword ptr [rdi], xmm0
0x1800bc5d1  jmp     short loc_1800BC5E1
0x1800bc5d3  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x1800bc5da  jmp     short loc_1800BC5CD
0x1800bc5dc  mov     ebx, 80004005h
0x1800bc5e1  mov     eax, ebx
0x1800bc5e3  mov     rcx, [rbp+1A0h+var_20]
0x1800bc5ea  xor     rcx, rsp; StackCookie
0x1800bc5ed  call    __security_check_cookie
0x1800bc5f2  mov     rbx, [rsp+2A0h+arg_10]
0x1800bc5fa  add     rsp, 290h
0x1800bc601  pop     rdi
0x1800bc602  pop     rsi
0x1800bc603  pop     rbp
0x1800bc604  retn
```
