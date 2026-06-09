# LoadTopView(ITopViewAwareItem *,ushort const *,TOPVIEWKEY *)

- ea: `0x1800f0b0c`
- end: `0x1800f0e0a`
- name: `?LoadTopView@@YAJPEAUITopViewAwareItem@@PEBGPEAUTOPVIEWKEY@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(struct ITopViewAwareItem *, const unsigned __int16 *, struct TOPVIEWKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008fa14`
- `0x1801fffa0`

## callees

- `0x1800f0b0c`
- `0x18013f7d0`
- `0x1801912c8`
- `0x180195ca8`
- `0x1801fce60`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x1800f0b6f`
- `SHELL32!SHGetIDListFromObject` at `0x1800f0b6f`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800f0c36`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800f0d2f`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800f0c36`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800f0d2f`
- `SHELL32!__imp_ILFree` at `0x1800f0bf2`
- `SHELL32!__imp_ILFree` at `0x1800f0bf2`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x1800f0ccc`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x1800f0ccc`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1800f0ba7`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1800f0ba7`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800f0ca4`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800f0ca4`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800f0bcc`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800f0de5`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800f0bcc`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1800f0de5`

## pseudocode

```c
__int64 __fastcall LoadTopView(struct ITopViewAwareItem *a1, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 v3; // rax
  HRESULT Str; // ebx
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rax
  DWORD v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  IPropertyBag *propBag; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR value[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR psz[40]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = *(_QWORD *)a1;
  punk = 0;
  Str = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, IUnknown **))(v3 + 48))(a1, &punk);
  if ( Str >= 0 )
  {
    ppidl = 0;
    Str = SHGetIDListFromObject(punk, &ppidl);
    if ( Str >= 0 )
    {
      propBag = 0;
      Str = SHGetViewStatePropertyBag(
              ppidl,
              L"Shell",
              5u,
              &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
              (void **)&propBag);
      if ( Str >= 0 )
      {
        Str = PSPropertyBag_ReadStr(propBag, L"TV_FolderType", value, 39);
        if ( Str >= 0 )
        {
          Str = SHCLSIDFromString(value, a3);
          if ( Str >= 0 )
          {
            *(_QWORD *)v10 = 0;
            if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, DWORD *))punk->lpVtbl[1].QueryInterface)(
                   punk,
                   0,
                   &BHID_SFObject,
                   &GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48,
                   v10) >= 0 )
            {
              v15 = 0;
              if ( (*(int (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v10 + 24LL))(*(_QWORD *)v10, &v15) >= 0 )
              {
                v9 = v15 - *(_QWORD *)&a3->Data1;
                if ( (_QWORD)v15 == *(_QWORD *)&a3->Data1 )
                  v9 = *((_QWORD *)&v15 + 1) - *(_QWORD *)a3->Data4;
                if ( v9 )
                  Str = -2147467259;
              }
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 16LL))(*(_QWORD *)v10);
            }
            if ( Str >= 0 )
            {
              Str = PSPropertyBag_ReadStr(propBag, L"TV_TopViewID", psz, 39);
              if ( Str >= 0 )
              {
                Str = SHCLSIDFromString(psz, a3 + 1);
                if ( Str >= 0 )
                {
                  *(_QWORD *)v10 = 0;
                  if ( (int)GetRootLibraryFromItemOrSearch((struct IShellItem *)punk) < 0 )
                    goto LABEL_14;
                  if ( !LibraryHasEnabledTopView(a3 + 1, *(struct IShellItem **)v10) )
                    Str = -2147467259;
                  (*(void (**)(void))(**(_QWORD **)v10 + 16LL))();
                  if ( Str >= 0 )
                  {
LABEL_14:
                    v10[0] = 0;
                    Str = PSPropertyBag_ReadDWORD(propBag, L"TV_TopViewVersion", v10);
                    if ( Str >= 0 )
                    {
                      *(_QWORD *)&v15 = 0;
                      Str = SHGetTopViewDescription(a3, &GUID_fe812157_522c_46cb_8d53_6efe3dce2c46, &v15);
                      if ( Str >= 0 )
                      {
                        v11 = 0;
                        Str = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v15 + 176LL))(v15, &v11);
                        if ( Str >= 0 && v10[0] != v11 )
                          ClearViewSettingsForTopView(a1, v8, (const struct TOPVIEWKEY *)a3);
                        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v15);
                      }
                    }
                  }
                }
              }
            }
          }
        }
        ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
      }
      ILFree(ppidl);
    }
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  }
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x1800f0b0c  mov     [rsp-8+arg_8], rbx
0x1800f0b11  push    rbp
0x1800f0b12  push    rsi
0x1800f0b13  push    rdi
0x1800f0b14  push    r12
0x1800f0b16  push    r14
0x1800f0b18  lea     rbp, [rsp-20h]
0x1800f0b1d  sub     rsp, 120h
0x1800f0b24  mov     rax, cs:__security_cookie
0x1800f0b2b  xor     rax, rsp
0x1800f0b2e  mov     [rbp+40h+var_30], rax
0x1800f0b32  mov     rax, [rcx]
0x1800f0b35  lea     rdx, [rsp+140h+punk]
0x1800f0b3a  mov     rdi, r8
0x1800f0b3d  mov     [rsp+140h+punk], 0
0x1800f0b46  mov     r14, rcx
0x1800f0b49  mov     rax, [rax+30h]
0x1800f0b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0b52  mov     ebx, eax
0x1800f0b54  test    eax, eax
0x1800f0b56  js      loc_1800F0C09
0x1800f0b5c  mov     rcx, [rsp+140h+punk]; punk
0x1800f0b61  lea     rdx, [rsp+140h+ppidl]; ppidl
0x1800f0b66  mov     [rsp+140h+ppidl], 0
0x1800f0b6f  call    cs:__imp_SHGetIDListFromObject
0x1800f0b75  mov     ebx, eax
0x1800f0b77  test    eax, eax
0x1800f0b79  js      short loc_1800F0BF8
0x1800f0b7b  mov     rcx, [rsp+140h+ppidl]; pidl
0x1800f0b80  lea     rax, [rsp+140h+propBag]
0x1800f0b85  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800f0b8c  mov     [rsp+140h+ppv], rax; ppv
0x1800f0b91  mov     r8d, 5; dwFlags
0x1800f0b97  mov     [rsp+140h+propBag], 0
0x1800f0ba0  lea     rdx, pszBagName; "Shell"
0x1800f0ba7  call    cs:__imp_SHGetViewStatePropertyBag
0x1800f0bad  mov     ebx, eax
0x1800f0baf  test    eax, eax
0x1800f0bb1  js      short loc_1800F0BED
0x1800f0bb3  mov     rcx, [rsp+140h+propBag]; propBag
0x1800f0bb8  lea     r8, [rsp+140h+value]; value
0x1800f0bbd  mov     esi, 27h ; '''
0x1800f0bc2  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1800f0bc9  mov     r9d, esi; characterCount
0x1800f0bcc  call    cs:__imp_PSPropertyBag_ReadStr
0x1800f0bd2  mov     ebx, eax
0x1800f0bd4  test    eax, eax
0x1800f0bd6  jns     loc_1800F0D27
0x1800f0bdc  mov     rcx, [rsp+140h+propBag]
0x1800f0be1  mov     rax, [rcx]
0x1800f0be4  mov     rax, [rax+10h]
0x1800f0be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0bed  mov     rcx, [rsp+140h+ppidl]; pidl
0x1800f0bf2  call    cs:__imp_ILFree
0x1800f0bf8  mov     rcx, [rsp+140h+punk]
0x1800f0bfd  mov     rax, [rcx]
0x1800f0c00  mov     rax, [rax+10h]
0x1800f0c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0c09  mov     eax, ebx
0x1800f0c0b  mov     rcx, [rbp+40h+var_30]
0x1800f0c0f  xor     rcx, rsp; StackCookie
0x1800f0c12  call    __security_check_cookie
0x1800f0c17  mov     rbx, [rsp+140h+arg_8]
0x1800f0c1f  add     rsp, 120h
0x1800f0c26  pop     r14
0x1800f0c28  pop     r12
0x1800f0c2a  pop     rdi
0x1800f0c2b  pop     rsi
0x1800f0c2c  pop     rbp
0x1800f0c2d  retn
0x1800f0c2e  lea     rdx, [rdi+10h]; pclsid
0x1800f0c32  lea     rcx, [rbp+40h+psz]; psz
0x1800f0c36  call    cs:__imp_SHCLSIDFromString
0x1800f0c3c  mov     ebx, eax
0x1800f0c3e  test    eax, eax
0x1800f0c40  js      short loc_1800F0BDC
0x1800f0c42  mov     rcx, [rsp+140h+punk]; struct IShellItem *
0x1800f0c47  lea     rdx, [rsp+140h+var_110]
0x1800f0c4c  mov     qword ptr [rsp+140h+var_110], 0
0x1800f0c55  call    GetRootLibraryFromItemOrSearch
0x1800f0c5a  test    eax, eax
0x1800f0c5c  js      short loc_1800F0C8B
0x1800f0c5e  mov     rdx, qword ptr [rsp+140h+var_110]; struct IShellItem *
0x1800f0c63  lea     rcx, [rdi+10h]; struct _GUID *
0x1800f0c67  call    ?LibraryHasEnabledTopView@@YAHAEBU_GUID@@PEAUIShellItem@@@Z; LibraryHasEnabledTopView(_GUID const &,IShellItem *)
0x1800f0c6c  mov     rcx, qword ptr [rsp+140h+var_110]
0x1800f0c71  test    eax, eax
0x1800f0c73  cmovz   ebx, r12d
0x1800f0c77  mov     rax, [rcx]
0x1800f0c7a  mov     rax, [rax+10h]
0x1800f0c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0c83  test    ebx, ebx
0x1800f0c85  js      loc_1800F0BDC
0x1800f0c8b  mov     rcx, [rsp+140h+propBag]; propBag
0x1800f0c90  lea     r8, [rsp+140h+var_110]; value
0x1800f0c95  lea     rdx, aTvTopviewversi; "TV_TopViewVersion"
0x1800f0c9c  mov     [rsp+140h+var_110], 0
0x1800f0ca4  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1800f0caa  mov     ebx, eax
0x1800f0cac  test    eax, eax
0x1800f0cae  js      loc_1800F0BDC
0x1800f0cb4  lea     r8, [rsp+140h+var_E8]
0x1800f0cb9  mov     qword ptr [rsp+140h+var_E8], 0
0x1800f0cc2  lea     rdx, _GUID_fe812157_522c_46cb_8d53_6efe3dce2c46
0x1800f0cc9  mov     rcx, rdi
0x1800f0ccc  call    cs:__imp_SHGetTopViewDescription
0x1800f0cd2  mov     ebx, eax
0x1800f0cd4  test    eax, eax
0x1800f0cd6  js      loc_1800F0BDC
0x1800f0cdc  mov     rcx, qword ptr [rsp+140h+var_E8]
0x1800f0ce1  lea     rdx, [rsp+140h+var_108]
0x1800f0ce6  mov     [rsp+140h+var_108], 0
0x1800f0cee  mov     rax, [rcx]
0x1800f0cf1  mov     rax, [rax+0B0h]
0x1800f0cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0cfd  mov     ebx, eax
0x1800f0cff  test    eax, eax
0x1800f0d01  js      short loc_1800F0D11
0x1800f0d03  mov     eax, [rsp+140h+var_108]
0x1800f0d07  cmp     [rsp+140h+var_110], eax
0x1800f0d0b  jnz     loc_1800F0DFA
0x1800f0d11  mov     rcx, qword ptr [rsp+140h+var_E8]
0x1800f0d16  mov     rax, [rcx]
0x1800f0d19  mov     rax, [rax+10h]
0x1800f0d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d22  jmp     loc_1800F0BDC
0x1800f0d27  mov     rdx, rdi; pclsid
0x1800f0d2a  lea     rcx, [rsp+140h+value]; psz
0x1800f0d2f  call    cs:__imp_SHCLSIDFromString
0x1800f0d35  mov     ebx, eax
0x1800f0d37  test    eax, eax
0x1800f0d39  js      loc_1800F0BDC
0x1800f0d3f  mov     rcx, [rsp+140h+punk]
0x1800f0d44  lea     rdx, [rsp+140h+var_110]
0x1800f0d49  mov     qword ptr [rsp+140h+var_110], 0
0x1800f0d52  lea     r9, _GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48
0x1800f0d59  mov     [rsp+140h+ppv], rdx
0x1800f0d5e  lea     r8, BHID_SFObject
0x1800f0d65  xor     edx, edx
0x1800f0d67  mov     rax, [rcx]
0x1800f0d6a  mov     rax, [rax+18h]
0x1800f0d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d73  mov     r12d, 80004005h
0x1800f0d79  test    eax, eax
0x1800f0d7b  js      short loc_1800F0DCA
0x1800f0d7d  mov     rcx, qword ptr [rsp+140h+var_110]
0x1800f0d82  lea     rdx, [rsp+140h+var_E8]
0x1800f0d87  xorps   xmm0, xmm0
0x1800f0d8a  movups  [rsp+140h+var_E8], xmm0
0x1800f0d8f  mov     rax, [rcx]
0x1800f0d92  mov     rax, [rax+18h]
0x1800f0d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0d9b  test    eax, eax
0x1800f0d9d  js      short loc_1800F0DB9
0x1800f0d9f  mov     rax, qword ptr [rsp+140h+var_E8]
0x1800f0da4  sub     rax, [rdi]
0x1800f0da7  jnz     short loc_1800F0DB2
0x1800f0da9  mov     rax, qword ptr [rsp+140h+var_E8+8]
0x1800f0dae  sub     rax, [rdi+8]
0x1800f0db2  test    rax, rax
0x1800f0db5  cmovnz  ebx, r12d
0x1800f0db9  mov     rcx, qword ptr [rsp+140h+var_110]
0x1800f0dbe  mov     rax, [rcx]
0x1800f0dc1  mov     rax, [rax+10h]
0x1800f0dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0dca  test    ebx, ebx
0x1800f0dcc  js      loc_1800F0BDC
0x1800f0dd2  mov     rcx, [rsp+140h+propBag]; propBag
0x1800f0dd7  lea     r8, [rbp+40h+psz]; value
0x1800f0ddb  mov     r9d, esi; characterCount
0x1800f0dde  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1800f0de5  call    cs:__imp_PSPropertyBag_ReadStr
0x1800f0deb  mov     ebx, eax
0x1800f0ded  test    eax, eax
0x1800f0def  js      loc_1800F0BDC
0x1800f0df5  jmp     loc_1800F0C2E
0x1800f0dfa  mov     r8, rdi; struct TOPVIEWKEY *
0x1800f0dfd  mov     rcx, r14; struct ITopViewAwareItem *
0x1800f0e00  call    ?ClearViewSettingsForTopView@@YAXPEAUITopViewAwareItem@@PEBGAEBUTOPVIEWKEY@@@Z; ClearViewSettingsForTopView(ITopViewAwareItem *,ushort const *,TOPVIEWKEY const &)
0x1800f0e05  jmp     loc_1800F0D11
```
