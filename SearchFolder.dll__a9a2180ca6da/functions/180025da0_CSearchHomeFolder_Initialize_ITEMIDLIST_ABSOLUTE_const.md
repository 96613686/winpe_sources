# CSearchHomeFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180025da0`
- end: `0x180025fa3`
- name: `?Initialize@CSearchHomeFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `515`
- prototype: `int(CSearchHomeFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800113b4`
- `0x180011f3c`
- `0x180025da0`
- `0x180026470`
- `0x1800267ac`
- `0x18003bc20`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180025f3d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180025f3d`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180025ed1`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180025ed1`
- `SHELL32!__imp_ILFree` at `0x180025dc3`
- `SHELL32!__imp_ILFree` at `0x180025dc3`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoListWithID` at `0x180025eb4`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoListWithID` at `0x180025eb4`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x180025e61`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x180025e61`

## pseudocode

```c
__int64 __fastcall CSearchHomeFolder::Initialize(CSearchHomeFolder *this, const struct _ITEMIDLIST_ABSOLUTE *a2)
{
  int HiddenSearchContext; // ebx
  _QWORD *v5; // rsi
  IUnknown **v6; // r14
  IUnknown *v7; // rbx
  int v8; // ecx
  struct IFolderWithSearchRoot *v9; // rcx
  struct IFolderWithSearchRoot *v10; // rcx
  GUID v12; // [rsp+30h] [rbp-10h] BYREF
  struct IFolderWithSearchRoot *v13; // [rsp+70h] [rbp+30h] BYREF
  IUnknown *punk; // [rsp+80h] [rbp+40h] BYREF

  ILFree(*((LPITEMIDLIST *)this + 9));
  HiddenSearchContext = SHILClone(a2, (struct _ITEMIDLIST_RELATIVE **)this + 9);
  if ( HiddenSearchContext >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 104);
    if ( !*((_DWORD *)this + 21) || !*v5 )
    {
      SafeRelease<IShellItemArray>((__int64 *)this + 11);
      SafeRelease<IShellItemArray>((__int64 *)this + 13);
      v6 = (IUnknown **)((char *)this + 96);
      SafeRelease<IShellItemArray>((__int64 *)this + 12);
      punk = 0;
      HiddenSearchContext = GetHiddenSearchContext((__int64)a2, &punk, (IUnknown **)this + 13, (IUnknown **)this + 12);
      if ( HiddenSearchContext >= 0 )
      {
        v7 = punk;
        if ( !punk && !*v5 && *v6 == punk )
        {
          v8 = *((_DWORD *)this + 20);
          if ( !v8 )
          {
            v8 = ((unsigned int)IsMSSearchEnabled(0, 0) != 0) + 1;
            *((_DWORD *)this + 20) = v8;
          }
          if ( v8 == 1 )
          {
            HiddenSearchContext = s_GetStartMenuFilesScope(0, (_QWORD *)this + 13);
            if ( HiddenSearchContext >= 0 )
              *((_DWORD *)this + 21) = 1;
          }
          else
          {
            v12 = GUID_238dff6e_1240_41d4_b991_534014880670;
            HiddenSearchContext = SHCreateAutoListWithID(
                                    &v12,
                                    0,
                                    &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                    (char *)this + 88);
            if ( HiddenSearchContext >= 0 )
              HiddenSearchContext = SHCreateShellItemArrayFromShellItem(
                                      *((IShellItem **)this + 11),
                                      &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                      (void **)this + 12);
          }
LABEL_26:
          SafeRelease<IShellItemArray>((__int64 *)&punk);
          return (unsigned int)HiddenSearchContext;
        }
        v9 = 0;
        v13 = 0;
        if ( punk )
        {
          HiddenSearchContext = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, struct IFolderWithSearchRoot **))punk->lpVtbl[1].QueryInterface)(
                                  punk,
                                  0,
                                  &BHID_SFViewObject,
                                  &GUID_dc0ac42a_141e_4876_9c43_824829440de0,
                                  &v13);
          if ( HiddenSearchContext < 0 )
          {
LABEL_24:
            v10 = v13;
            v13 = 0;
            if ( v10 )
              (*(void (__fastcall **)(struct IFolderWithSearchRoot *))(*(_QWORD *)v10 + 16LL))(v10);
            goto LABEL_26;
          }
          v7 = punk;
          v9 = v13;
        }
        if ( !v9
          || (*(int (__fastcall **)(struct IFolderWithSearchRoot *, char *))(*(_QWORD *)v9 + 32LL))(
               v9,
               (char *)this + 88) < 0 )
        {
          IUnknown_Set((IUnknown **)this + 11, v7);
        }
        HiddenSearchContext = 0;
        if ( !*v5 && !*v6 )
          HiddenSearchContext = CSearchHomeFolder::_SetScopeAndSubQueries(
                                  (CSearchHomeFolder *)((char *)this - 8),
                                  (struct IShellItem *)punk,
                                  v13);
        goto LABEL_24;
      }
    }
  }
  return (unsigned int)HiddenSearchContext;
}

```

## disassembly

```asm
0x180025da0  mov     [rsp-28h+arg_8], rbx
0x180025da5  mov     [rsp-28h+arg_18], rsi
0x180025daa  push    rbp
0x180025dab  push    rdi
0x180025dac  push    r12
0x180025dae  push    r14
0x180025db0  push    r15
0x180025db2  mov     rbp, rsp
0x180025db5  sub     rsp, 40h
0x180025db9  mov     rdi, rcx
0x180025dbc  mov     r12, rdx
0x180025dbf  mov     rcx, [rcx+48h]; pidl
0x180025dc3  call    cs:__imp_ILFree
0x180025dc9  lea     rdx, [rdi+48h]; struct _ITEMIDLIST_RELATIVE **
0x180025dcd  mov     rcx, r12; struct _ITEMIDLIST_RELATIVE *
0x180025dd0  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180025dd5  mov     ebx, eax
0x180025dd7  test    eax, eax
0x180025dd9  js      loc_180025F88
0x180025ddf  cmp     dword ptr [rdi+54h], 0
0x180025de3  lea     rsi, [rdi+68h]
0x180025de7  jz      short loc_180025DF3
0x180025de9  cmp     qword ptr [rsi], 0
0x180025ded  jnz     loc_180025F88
0x180025df3  lea     r15, [rdi+58h]
0x180025df7  mov     rcx, r15
0x180025dfa  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180025dff  mov     rcx, rsi
0x180025e02  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180025e07  lea     r14, [rdi+60h]
0x180025e0b  mov     rcx, r14
0x180025e0e  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180025e13  mov     r9, r14
0x180025e16  mov     [rbp+punk], 0
0x180025e1e  mov     r8, rsi
0x180025e21  lea     rdx, [rbp+punk]
0x180025e25  mov     rcx, r12
0x180025e28  call    GetHiddenSearchContext
0x180025e2d  mov     ebx, eax
0x180025e2f  test    eax, eax
0x180025e31  js      loc_180025F88
0x180025e37  mov     rbx, [rbp+punk]
0x180025e3b  test    rbx, rbx
0x180025e3e  jnz     loc_180025EDE
0x180025e44  cmp     [rsi], rbx
0x180025e47  jnz     loc_180025EDE
0x180025e4d  cmp     [r14], rbx
0x180025e50  jnz     loc_180025EDE
0x180025e56  mov     ecx, [rdi+50h]
0x180025e59  test    ecx, ecx
0x180025e5b  jnz     short loc_180025E73
0x180025e5d  xor     edx, edx
0x180025e5f  xor     ecx, ecx
0x180025e61  call    cs:__imp_IsMSSearchEnabled
0x180025e67  xor     ecx, ecx
0x180025e69  test    eax, eax
0x180025e6b  setnz   cl
0x180025e6e  inc     ecx
0x180025e70  mov     [rdi+50h], ecx
0x180025e73  cmp     ecx, 1
0x180025e76  jnz     short loc_180025E98
0x180025e78  mov     rdx, rsi
0x180025e7b  xor     ecx, ecx
0x180025e7d  call    s_GetStartMenuFilesScope
0x180025e82  mov     ebx, eax
0x180025e84  test    eax, eax
0x180025e86  js      loc_180025F7F
0x180025e8c  mov     dword ptr [rdi+54h], 1
0x180025e93  jmp     loc_180025F7F
0x180025e98  movups  xmm0, xmmword ptr cs:_GUID_238dff6e_1240_41d4_b991_534014880670.Data1
0x180025e9f  mov     r9, r15
0x180025ea2  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180025ea9  xor     edx, edx
0x180025eab  lea     rcx, [rbp+var_10]
0x180025eaf  movdqu  [rbp+var_10], xmm0
0x180025eb4  call    cs:__imp_SHCreateAutoListWithID
0x180025eba  mov     ebx, eax
0x180025ebc  test    eax, eax
0x180025ebe  js      loc_180025F7F
0x180025ec4  mov     rcx, [r15]; psi
0x180025ec7  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180025ece  mov     r8, r14; ppv
0x180025ed1  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x180025ed7  mov     ebx, eax
0x180025ed9  jmp     loc_180025F7F
0x180025ede  xor     ecx, ecx
0x180025ee0  mov     [rbp+arg_0], rcx
0x180025ee4  test    rbx, rbx
0x180025ee7  jz      short loc_180025F1F
0x180025ee9  mov     rax, [rbx]
0x180025eec  lea     rcx, [rbp+arg_0]
0x180025ef0  mov     [rsp+40h+var_20], rcx
0x180025ef5  lea     r9, _GUID_dc0ac42a_141e_4876_9c43_824829440de0
0x180025efc  lea     r8, BHID_SFViewObject
0x180025f03  xor     edx, edx
0x180025f05  mov     rcx, rbx
0x180025f08  mov     rax, [rax+18h]
0x180025f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f11  mov     ebx, eax
0x180025f13  test    eax, eax
0x180025f15  js      short loc_180025F62
0x180025f17  mov     rbx, [rbp+punk]
0x180025f1b  mov     rcx, [rbp+arg_0]
0x180025f1f  test    rcx, rcx
0x180025f22  jz      short loc_180025F37
0x180025f24  mov     rax, [rcx]
0x180025f27  mov     rdx, r15
0x180025f2a  mov     rax, [rax+20h]
0x180025f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f33  test    eax, eax
0x180025f35  jns     short loc_180025F43
0x180025f37  mov     rdx, rbx; punk
0x180025f3a  mov     rcx, r15; ppunk
0x180025f3d  call    cs:__imp_IUnknown_Set
0x180025f43  xor     ebx, ebx
0x180025f45  cmp     [rsi], rbx
0x180025f48  jnz     short loc_180025F62
0x180025f4a  cmp     [r14], rbx
0x180025f4d  jnz     short loc_180025F62
0x180025f4f  mov     r8, [rbp+arg_0]; struct IFolderWithSearchRoot *
0x180025f53  lea     rcx, [rdi-8]; this
0x180025f57  mov     rdx, [rbp+punk]; struct IShellItem *
0x180025f5b  call    ?_SetScopeAndSubQueries@CSearchHomeFolder@@AEAAJPEAUIShellItem@@PEAUIFolderWithSearchRoot@@@Z; CSearchHomeFolder::_SetScopeAndSubQueries(IShellItem *,IFolderWithSearchRoot *)
0x180025f60  mov     ebx, eax
0x180025f62  mov     rcx, [rbp+arg_0]
0x180025f66  mov     [rbp+arg_0], 0
0x180025f6e  test    rcx, rcx
0x180025f71  jz      short loc_180025F7F
0x180025f73  mov     rax, [rcx]
0x180025f76  mov     rax, [rax+10h]
0x180025f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f7f  lea     rcx, [rbp+punk]
0x180025f83  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180025f88  lea     r11, [rsp+40h+var_s0]
0x180025f8d  mov     eax, ebx
0x180025f8f  mov     rbx, [r11+38h]
0x180025f93  mov     rsi, [r11+48h]
0x180025f97  mov     rsp, r11
0x180025f9a  pop     r15
0x180025f9c  pop     r14
0x180025f9e  pop     r12
0x180025fa0  pop     rdi
0x180025fa1  pop     rbp
0x180025fa2  retn
```
