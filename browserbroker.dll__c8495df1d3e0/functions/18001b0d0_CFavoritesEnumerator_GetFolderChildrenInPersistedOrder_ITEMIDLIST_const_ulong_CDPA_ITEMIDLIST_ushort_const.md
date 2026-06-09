# CFavoritesEnumerator::GetFolderChildrenInPersistedOrder(_ITEMIDLIST const *,ulong,CDPA<_ITEMIDLIST> *,ushort const *)

- ea: `0x18001b0d0`
- end: `0x18001b25e`
- name: `?GetFolderChildrenInPersistedOrder@CFavoritesEnumerator@@AEAAJPEFBU_ITEMIDLIST@@KPEAV?$CDPA@$$CFAU_ITEMIDLIST@@@@PEBG@Z`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b470`

## callees

- `0x180002ce0`
- `0x180006cc4`
- `0x18001550c`
- `0x180015544`
- `0x18001b0d0`
- `0x1800250f0`

## import_xrefs

- `iertutil!__imp_DPA_Create` at `0x18001b161`
- `iertutil!__imp_DPA_Create` at `0x18001b161`
- `iertutil!__imp_DPA_GetPtr` at `0x18001b193`
- `iertutil!__imp_DPA_GetPtr` at `0x18001b193`
- `iertutil!__imp_DPA_InsertPtr` at `0x18001b1f4`
- `iertutil!__imp_DPA_InsertPtr` at `0x18001b1f4`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18001b1df`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x18001b1df`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001b1ca`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001b1ca`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001b206`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001b20e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001b206`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001b20e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFavoritesEnumerator::GetFolderChildrenInPersistedOrder(
        __int64 a1,
        struct _ITEMIDLIST *a2,
        char a3,
        HDPA *a4,
        unsigned __int16 *a5)
{
  int FavoritesFolderOrder; // r15d
  HDPA v8; // rax
  int i; // esi
  int v10; // eax
  _QWORD *Ptr; // rax
  ITEMIDLIST *v12; // rdi
  HDPA hdpa; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST pidl[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  v15 = 0;
  hdpa = 0;
  FavoritesFolderOrder = GetFavoritesFolderOrder(a2, a5);
  if ( FavoritesFolderOrder >= 0 )
  {
    v8 = DPA_Create(4);
    *a4 = v8;
    if ( v8 )
    {
      for ( i = 0; ; ++i )
      {
        v10 = hdpa ? *(_DWORD *)hdpa : 0;
        if ( i >= v10 )
          break;
        Ptr = DPA_GetPtr(hdpa, i);
        if ( Ptr )
        {
          pidl[0] = 0;
          if ( (int)SHFullIDListFromFolderAndRelativeItem(v15, *Ptr, pidl) >= 0 )
          {
            v12 = (ITEMIDLIST *)pidl[0];
            if ( SHGetPathFromIDListW(pidl[0], pszPath)
              && ((a3 & 4) == 0 || PathIsDirectoryW(pszPath))
              && DPA_InsertPtr(*a4, 0x7FFFFFFF, v12) != -1 )
            {
              v12 = 0;
            }
            ILFree(v12);
          }
          ILFree(0);
        }
      }
    }
    CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::DestroyCallback(&hdpa);
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v15);
  return (unsigned int)FavoritesFolderOrder;
}

```

## disassembly

```asm
0x18001b0d0  mov     [rsp-8+arg_0], rbx
0x18001b0d5  mov     [rsp-8+arg_10], rsi
0x18001b0da  push    rbp
0x18001b0db  push    rdi
0x18001b0dc  push    r12
0x18001b0de  push    r14
0x18001b0e0  push    r15
0x18001b0e2  lea     rbp, [rsp-170h]
0x18001b0ea  sub     rsp, 270h
0x18001b0f1  mov     rax, cs:__security_cookie
0x18001b0f8  xor     rax, rsp
0x18001b0fb  mov     [rbp+190h+var_30], rax
0x18001b102  mov     r14, r9
0x18001b105  mov     r12d, r8d
0x18001b108  mov     rcx, rdx; struct _ITEMIDLIST *
0x18001b10b  mov     r10, [rbp+190h+arg_20]
0x18001b112  mov     [rsp+290h+var_258], 0
0x18001b11b  mov     [rsp+290h+hdpa], 0
0x18001b124  mov     r9d, r8d
0x18001b127  and     r9d, 1
0x18001b12b  shl     r9d, 6
0x18001b12f  mov     edx, r9d
0x18001b132  or      edx, 20h
0x18001b135  test    r8b, 2
0x18001b139  cmovz   edx, r9d
0x18001b13d  mov     [rsp+290h+var_270], r10; unsigned __int16 *
0x18001b142  lea     r9, [rsp+290h+hdpa]
0x18001b147  lea     r8, [rsp+290h+var_258]
0x18001b14c  call    ?GetFavoritesFolderOrder@@YAJPEFBU_ITEMIDLIST@@KPEAPEAUIShellFolder@@PEAV?$CDPA@U__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@@@PEBG@Z; GetFavoritesFolderOrder(_ITEMIDLIST const *,ulong,IShellFolder * *,CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001> *,ushort const *)
0x18001b151  mov     r15d, eax
0x18001b154  test    eax, eax
0x18001b156  js      loc_18001B226
0x18001b15c  mov     ecx, 4; cItemGrow
0x18001b161  call    cs:__imp_DPA_Create
0x18001b167  mov     [r14], rax
0x18001b16a  test    rax, rax
0x18001b16d  jz      loc_18001B21B
0x18001b173  xor     esi, esi
0x18001b175  mov     rbx, [rsp+290h+hdpa]
0x18001b17a  test    rbx, rbx
0x18001b17d  jz      short loc_18001B183
0x18001b17f  mov     eax, [rbx]
0x18001b181  jmp     short loc_18001B185
0x18001b183  xor     eax, eax
0x18001b185  cmp     esi, eax
0x18001b187  jge     loc_18001B21B
0x18001b18d  movsxd  rdx, esi; i
0x18001b190  mov     rcx, rbx; hdpa
0x18001b193  call    cs:__imp_DPA_GetPtr
0x18001b199  test    rax, rax
0x18001b19c  jz      short loc_18001B214
0x18001b19e  mov     [rsp+290h+pidl], 0
0x18001b1a7  lea     r8, [rsp+290h+pidl]
0x18001b1ac  mov     rdx, [rax]
0x18001b1af  mov     rcx, [rsp+290h+var_258]
0x18001b1b4  call    SHFullIDListFromFolderAndRelativeItem
0x18001b1b9  test    eax, eax
0x18001b1bb  js      short loc_18001B20C
0x18001b1bd  lea     rdx, [rsp+290h+pszPath]; pszPath
0x18001b1c2  mov     rdi, [rsp+290h+pidl]
0x18001b1c7  mov     rcx, rdi; pidl
0x18001b1ca  call    cs:__imp_SHGetPathFromIDListW
0x18001b1d0  test    eax, eax
0x18001b1d2  jz      short loc_18001B203
0x18001b1d4  test    r12b, 4
0x18001b1d8  jz      short loc_18001B1E9
0x18001b1da  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18001b1df  call    cs:__imp_PathIsDirectoryW
0x18001b1e5  test    eax, eax
0x18001b1e7  jz      short loc_18001B203
0x18001b1e9  mov     r8, rdi; p
0x18001b1ec  mov     edx, 7FFFFFFFh; i
0x18001b1f1  mov     rcx, [r14]; hdpa
0x18001b1f4  call    cs:__imp_DPA_InsertPtr
0x18001b1fa  xor     edx, edx
0x18001b1fc  cmp     eax, 0FFFFFFFFh
0x18001b1ff  cmovnz  rdi, rdx
0x18001b203  mov     rcx, rdi; pidl
0x18001b206  call    cs:__imp_ILFree
0x18001b20c  xor     ecx, ecx; pidl
0x18001b20e  call    cs:__imp_ILFree
0x18001b214  inc     esi
0x18001b216  jmp     loc_18001B17A
0x18001b21b  lea     rcx, [rsp+290h+hdpa]
0x18001b220  call    ?DestroyCallback@?$CDPA@U__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@@@QEAAXP6AHPEAU__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@PEAX@Z1@Z; CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001>::DestroyCallback(int (*)(__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *,void *),void *)
0x18001b225  nop
0x18001b226  lea     rcx, [rsp+290h+var_258]
0x18001b22b  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001b230  mov     eax, r15d
0x18001b233  mov     rcx, [rbp+190h+var_30]
0x18001b23a  xor     rcx, rsp; StackCookie
0x18001b23d  call    __security_check_cookie
0x18001b242  lea     r11, [rsp+290h+var_20]
0x18001b24a  mov     rbx, [r11+30h]
0x18001b24e  mov     rsi, [r11+40h]
0x18001b252  mov     rsp, r11
0x18001b255  pop     r15
0x18001b257  pop     r14
0x18001b259  pop     r12
0x18001b25b  pop     rdi
0x18001b25c  pop     rbp
0x18001b25d  retn
```
