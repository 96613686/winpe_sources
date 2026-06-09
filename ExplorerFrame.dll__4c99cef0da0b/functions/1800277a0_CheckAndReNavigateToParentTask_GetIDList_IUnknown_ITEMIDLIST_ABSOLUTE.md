# CheckAndReNavigateToParentTask::_GetIDList(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x1800277a0`
- end: `0x1800279f9`
- name: `?_GetIDList@CheckAndReNavigateToParentTask@@AEAAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `601`
- prototype: `int(CheckAndReNavigateToParentTask *__hidden this, struct IUnknown *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027bd8`

## callees

- `0x180023354`
- `0x1800277a0`
- `0x1800903fc`
- `0x1800b1578`
- `0x1800dfc14`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180027977`
- `SHCORE!IUnknown_QueryService` at `0x180027977`
- `SHELL32!SHGetNameFromIDList` at `0x180027896`
- `SHELL32!SHGetNameFromIDList` at `0x180027896`
- `SHELL32!SHGetIDListFromObject` at `0x1800279b4`
- `SHELL32!SHGetIDListFromObject` at `0x1800279b4`
- `SHELL32!__imp_ILRemoveLastID` at `0x180027870`
- `SHELL32!__imp_ILRemoveLastID` at `0x18002791f`
- `SHELL32!__imp_ILRemoveLastID` at `0x180027870`
- `SHELL32!__imp_ILRemoveLastID` at `0x18002791f`
- `SHELL32!__imp_ILClone` at `0x1800277f0`
- `SHELL32!__imp_ILClone` at `0x18002783c`
- `SHELL32!__imp_ILClone` at `0x1800277f0`
- `SHELL32!__imp_ILClone` at `0x18002783c`
- `SHELL32!__imp_ILIsEqual` at `0x1800277d5`
- `SHELL32!__imp_ILIsEqual` at `0x1800277d5`
- `SHELL32!__imp_ILFindChild` at `0x180027816`
- `SHELL32!__imp_ILFindChild` at `0x180027816`
- `SHELL32!__imp_ILFree` at `0x18002782a`
- `SHELL32!__imp_ILFree` at `0x1800278a5`
- `SHELL32!__imp_ILFree` at `0x1800279ce`
- `SHELL32!__imp_ILFree` at `0x18002782a`
- `SHELL32!__imp_ILFree` at `0x1800278a5`
- `SHELL32!__imp_ILFree` at `0x1800279ce`
- `SHELL32!__imp_SHValidateUNC` at `0x18002793f`
- `SHELL32!__imp_SHValidateUNC` at `0x18002793f`
- `SHLWAPI!PathIsUNCW` at `0x1800278c6`
- `SHLWAPI!PathIsUNCW` at `0x1800278c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800278da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800278da`

## pseudocode

```c
__int64 __fastcall CheckAndReNavigateToParentTask::_GetIDList(
        CheckAndReNavigateToParentTask *this,
        struct IUnknown *a2,
        struct _ITEMIDLIST_ABSOLUTE **a3)
{
  LPCITEMIDLIST *v3; // r14
  const ITEMIDLIST *v5; // rdx
  const ITEMIDLIST *v7; // rcx
  BOOL v9; // eax
  const struct _ITEMIDLIST_RELATIVE *v10; // rcx
  LPITEMIDLIST v11; // rbx
  HRESULT v12; // edi
  LPITEMIDLIST v13; // rax
  void *ppvOut; // [rsp+20h] [rbp-10h] BYREF
  PWSTR ppszName; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp+50h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp+58h] BYREF

  v3 = (LPCITEMIDLIST *)((char *)this + 8);
  *a3 = 0;
  v5 = (const ITEMIDLIST *)*((_QWORD *)this + 2);
  v7 = (const ITEMIDLIST *)*((_QWORD *)this + 1);
  ppszName = 0;
  v9 = ILIsEqual(v7, v5);
  v10 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    v12 = SHILClone(v10, (struct _ITEMIDLIST_RELATIVE **)&ppszName);
    if ( (*(_DWORD *)this == 16 || *(_DWORD *)this == 4) && !IsNotifiedItemValid(*((LPCITEMIDLIST *)this + 2)) )
    {
      v11 = (LPITEMIDLIST)ppszName;
      ILRemoveLastID((LPITEMIDLIST)ppszName);
    }
    else
    {
      v11 = (LPITEMIDLIST)ppszName;
    }
LABEL_13:
    if ( v12 >= 0 )
    {
LABEL_14:
      ppszName = 0;
      v12 = SHGetNameFromIDList(v11, SIGDN_DESKTOPABSOLUTEPARSING, &ppszName);
      if ( v12 >= 0 )
      {
        if ( !PathIsUNCW(ppszName) || SHValidateUNC(0, ppszName, 2u) )
        {
          *a3 = (struct _ITEMIDLIST_ABSOLUTE *)v11;
          v11 = 0;
        }
        else
        {
          v12 = SHILCloneFirst((const struct _ITEMIDLIST_RELATIVE *)v11, a3);
          if ( v12 >= 0 )
          {
            ppvOut = 0;
            if ( IUnknown_QueryService(
                   a2,
                   (const GUID *const)&SID_STopLevelBrowser,
                   &GUID_9536ca39_1acb_4ae6_ad27_2403d04ca28f,
                   &ppvOut) >= 0 )
            {
              punk = 0;
              if ( (*(int (__fastcall **)(void *, GUID *, IUnknown **))(*(_QWORD *)ppvOut + 32LL))(
                     ppvOut,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     &punk) >= 0 )
              {
                ppidl = 0;
                if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
                {
                  Pidl_Set(v3, ppidl);
                  ILFree(ppidl);
                }
                ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            }
          }
        }
        CoTaskMemFree(ppszName);
      }
      ILFree(v11);
    }
  }
  else
  {
    if ( !v10 )
      return (unsigned int)-2147024809;
    v11 = ILClone((LPCITEMIDLIST)v10);
    v12 = v11 == 0 ? 0x8007000E : 0;
    if ( v11 )
    {
      if ( (v13 = ILFindChild(*((LPITEMIDLIST *)this + 2), *v3)) == 0
        || !v13->mkid.cb
        || ((ILFree(v11), !*v3)
          ? (v12 = -2147024809, v11 = 0)
          : (LPITEMIDLIST)(v11 = ILClone(*v3), v12 = v11 == 0 ? 0x8007000E : 0),
            v12 >= 0) )
      {
        if ( !IsNotifiedItemValid(v11) )
        {
          while ( v11 && v11->mkid.cb )
          {
            ILRemoveLastID(v11);
            if ( IsNotifiedItemValid(v11) )
              goto LABEL_13;
          }
        }
        goto LABEL_14;
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800277a0  mov     [rsp-38h+arg_8], rbx
0x1800277a5  push    rbp
0x1800277a6  push    rsi
0x1800277a7  push    rdi
0x1800277a8  push    r12
0x1800277aa  push    r13
0x1800277ac  push    r14
0x1800277ae  push    r15
0x1800277b0  mov     rbp, rsp
0x1800277b3  sub     rsp, 30h
0x1800277b7  xor     r13d, r13d
0x1800277ba  lea     r14, [rcx+8]
0x1800277be  mov     [r8], r13
0x1800277c1  mov     r12, rdx
0x1800277c4  mov     rdx, [rcx+10h]; pidl2
0x1800277c8  mov     rsi, rcx
0x1800277cb  mov     rcx, [r14]; pidl1
0x1800277ce  mov     r15, r8
0x1800277d1  mov     [rbp+ppszName], r13
0x1800277d5  call    cs:__imp_ILIsEqual
0x1800277db  mov     rcx, [rsi+10h]; struct _ITEMIDLIST_RELATIVE *
0x1800277df  test    eax, eax
0x1800277e1  jnz     loc_1800278F6
0x1800277e7  test    rcx, rcx
0x1800277ea  jz      loc_1800278EF
0x1800277f0  call    cs:__imp_ILClone
0x1800277f6  mov     rbx, rax
0x1800277f9  neg     rax
0x1800277fc  sbb     edi, edi
0x1800277fe  not     edi
0x180027800  and     edi, 8007000Eh
0x180027806  test    rbx, rbx
0x180027809  jz      loc_1800278AB
0x18002780f  mov     rdx, [r14]; pidlChild
0x180027812  mov     rcx, [rsi+10h]; pidlParent
0x180027816  call    cs:__imp_ILFindChild
0x18002781c  test    rax, rax
0x18002781f  jz      short loc_180027856
0x180027821  cmp     [rax], r13w
0x180027825  jz      short loc_180027856
0x180027827  mov     rcx, rbx; pidl
0x18002782a  call    cs:__imp_ILFree
0x180027830  mov     rcx, [r14]; pidl
0x180027833  test    rcx, rcx
0x180027836  jz      loc_1800278E2
0x18002783c  call    cs:__imp_ILClone
0x180027842  mov     rbx, rax
0x180027845  neg     rax
0x180027848  sbb     edi, edi
0x18002784a  not     edi
0x18002784c  and     edi, 8007000Eh
0x180027852  test    edi, edi
0x180027854  js      short loc_1800278AB
0x180027856  mov     rcx, rbx; pidl
0x180027859  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18002785e  test    al, al
0x180027860  jnz     short loc_180027886
0x180027862  test    rbx, rbx
0x180027865  jz      short loc_180027886
0x180027867  cmp     [rbx], r13w
0x18002786b  jz      short loc_180027886
0x18002786d  mov     rcx, rbx; pidl
0x180027870  call    cs:__imp_ILRemoveLastID
0x180027876  mov     rcx, rbx; pidl
0x180027879  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18002787e  test    al, al
0x180027880  jz      short loc_180027862
0x180027882  test    edi, edi
0x180027884  js      short loc_1800278AB
0x180027886  lea     r8, [rbp+ppszName]; ppszName
0x18002788a  mov     [rbp+ppszName], r13
0x18002788e  mov     edx, 80028000h; sigdnName
0x180027893  mov     rcx, rbx; pidl
0x180027896  call    cs:__imp_SHGetNameFromIDList
0x18002789c  mov     edi, eax
0x18002789e  test    eax, eax
0x1800278a0  jns     short loc_1800278C2
0x1800278a2  mov     rcx, rbx; pidl
0x1800278a5  call    cs:__imp_ILFree
0x1800278ab  mov     rbx, [rsp+30h+arg_8]
0x1800278b0  mov     eax, edi
0x1800278b2  add     rsp, 30h
0x1800278b6  pop     r15
0x1800278b8  pop     r14
0x1800278ba  pop     r13
0x1800278bc  pop     r12
0x1800278be  pop     rdi
0x1800278bf  pop     rsi
0x1800278c0  pop     rbp
0x1800278c1  retn
0x1800278c2  mov     rcx, [rbp+ppszName]; pszPath
0x1800278c6  call    cs:__imp_PathIsUNCW
0x1800278cc  test    eax, eax
0x1800278ce  jnz     short loc_180027933
0x1800278d0  mov     [r15], rbx
0x1800278d3  mov     rbx, r13
0x1800278d6  mov     rcx, [rbp+ppszName]; pv
0x1800278da  call    cs:__imp_CoTaskMemFree
0x1800278e0  jmp     short loc_1800278A2
0x1800278e2  mov     edi, 80070057h
0x1800278e7  mov     rbx, r13
0x1800278ea  jmp     loc_180027852
0x1800278ef  mov     edi, 80070057h
0x1800278f4  jmp     short loc_1800278AB
0x1800278f6  lea     rdx, [rbp+ppszName]; struct _ITEMIDLIST_RELATIVE **
0x1800278fa  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1800278ff  cmp     dword ptr [rsi], 10h
0x180027902  mov     edi, eax
0x180027904  jz      short loc_18002790B
0x180027906  cmp     dword ptr [rsi], 4
0x180027909  jnz     short loc_18002792A
0x18002790b  mov     rcx, [rsi+10h]; pidl
0x18002790f  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x180027914  test    al, al
0x180027916  jnz     short loc_18002792A
0x180027918  mov     rbx, [rbp+ppszName]
0x18002791c  mov     rcx, rbx; pidl
0x18002791f  call    cs:__imp_ILRemoveLastID
0x180027925  jmp     loc_180027882
0x18002792a  mov     rbx, [rbp+ppszName]
0x18002792e  jmp     loc_180027882
0x180027933  mov     rdx, [rbp+ppszName]; pszFile
0x180027937  mov     r8d, 2; fConnect
0x18002793d  xor     ecx, ecx; hwndOwner
0x18002793f  call    cs:__imp_SHValidateUNC
0x180027945  test    eax, eax
0x180027947  jnz     short loc_1800278D0
0x180027949  mov     rdx, r15; struct _ITEMID_CHILD **
0x18002794c  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x18002794f  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x180027954  mov     edi, eax
0x180027956  test    eax, eax
0x180027958  js      loc_1800278D6
0x18002795e  lea     r9, [rbp+ppvOut]; ppvOut
0x180027962  mov     [rbp+ppvOut], r13
0x180027966  lea     r8, _GUID_9536ca39_1acb_4ae6_ad27_2403d04ca28f; riid
0x18002796d  mov     rcx, r12; punk
0x180027970  lea     rdx, SID_STopLevelBrowser; guidService
0x180027977  call    cs:__imp_IUnknown_QueryService
0x18002797d  test    eax, eax
0x18002797f  js      loc_1800278D6
0x180027985  mov     rcx, [rbp+ppvOut]
0x180027989  lea     r8, [rbp+punk]
0x18002798d  mov     [rbp+punk], r13
0x180027991  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180027998  mov     rax, [rcx]
0x18002799b  mov     rax, [rax+20h]
0x18002799f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279a4  test    eax, eax
0x1800279a6  js      short loc_1800279E4
0x1800279a8  mov     rcx, [rbp+punk]; punk
0x1800279ac  lea     rdx, [rbp+ppidl]; ppidl
0x1800279b0  mov     [rbp+ppidl], r13
0x1800279b4  call    cs:__imp_SHGetIDListFromObject
0x1800279ba  test    eax, eax
0x1800279bc  js      short loc_1800279D4
0x1800279be  mov     rdx, [rbp+ppidl]
0x1800279c2  mov     rcx, r14
0x1800279c5  call    Pidl_Set
0x1800279ca  mov     rcx, [rbp+ppidl]; pidl
0x1800279ce  call    cs:__imp_ILFree
0x1800279d4  mov     rcx, [rbp+punk]
0x1800279d8  mov     rax, [rcx]
0x1800279db  mov     rax, [rax+10h]
0x1800279df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279e4  mov     rcx, [rbp+ppvOut]
0x1800279e8  mov     rax, [rcx]
0x1800279eb  mov     rax, [rax+10h]
0x1800279ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279f4  jmp     loc_1800278D6
```
