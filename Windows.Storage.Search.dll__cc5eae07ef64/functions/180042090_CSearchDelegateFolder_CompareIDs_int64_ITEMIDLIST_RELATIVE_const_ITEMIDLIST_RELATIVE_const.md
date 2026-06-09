# CSearchDelegateFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180042090`
- end: `0x1800422b2`
- name: `?CompareIDs@CSearchDelegateFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `546`
- prototype: `int(CSearchDelegateFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180042090`
- `0x1800422b8`
- `0x1800423cc`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_StrRetToStrW` at `0x180042171`
- `SHCORE!__imp_StrRetToStrW` at `0x180042215`
- `SHCORE!__imp_StrRetToStrW` at `0x180042171`
- `SHCORE!__imp_StrRetToStrW` at `0x180042215`
- `Windows.Storage!ILFree` at `0x18004228d`
- `Windows.Storage!ILFree` at `0x180042296`
- `Windows.Storage!ILFree` at `0x18004228d`
- `Windows.Storage!ILFree` at `0x180042296`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18004211d`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x1800421c1`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18004211d`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x1800421c1`
- `Windows.Storage!ILCloneFirst` at `0x1800420bb`
- `Windows.Storage!ILCloneFirst` at `0x1800420d0`
- `Windows.Storage!ILCloneFirst` at `0x1800420bb`
- `Windows.Storage!ILCloneFirst` at `0x1800420d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042284`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004223e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004223e`

## pseudocode

```c
__int64 __fastcall CSearchDelegateFolder::CompareIDs(
        unsigned __int64 this,
        __int64 a2,
        const ITEMIDLIST *a3,
        const ITEMIDLIST *a4)
{
  unsigned int v7; // ebx
  LPITEMIDLIST v8; // r12
  LPITEMIDLIST v9; // rsi
  IShellFolder *v10; // rdi
  HRESULT v11; // r13d
  HRESULT v12; // r13d
  unsigned __int16 v13; // ax
  CSearchDelegateFolder *v14; // rcx
  unsigned __int16 v15; // ax
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v19; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppsz; // [rsp+48h] [rbp-B8h] BYREF
  STRRET pstr; // [rsp+50h] [rbp-B0h] BYREF

  v7 = 0;
  v8 = ILCloneFirst(a3);
  if ( v8 )
  {
    v9 = ILCloneFirst(a4);
    if ( v9 )
    {
      v10 = (IShellFolder *)(this & -(__int64)(this != 8));
      ppsz = 0;
      ppv = 0;
      pidl = 0;
      if ( SHBindToFolderIDListParent(v10, v8, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &pidl) >= 0 )
      {
        memset_0(&pstr, 0, sizeof(pstr));
        v11 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, _QWORD, STRRET *))(*(_QWORD *)ppv + 88LL))(
                ppv,
                pidl,
                0,
                &pstr);
        if ( v11 >= 0 )
          v11 = StrRetToStrW(&pstr, pidl, &ppsz);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v11 >= 0 )
        {
          v19 = 0;
          pidl = 0;
          ppv = 0;
          if ( SHBindToFolderIDListParent(
                 v10,
                 v9,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 (void **)&pidl,
                 (LPCITEMIDLIST *)&ppv) >= 0 )
          {
            memset_0(&pstr, 0, sizeof(pstr));
            v12 = (*(__int64 (__fastcall **)(LPCITEMIDLIST, void *, _QWORD, STRRET *))(*(_QWORD *)&pidl->mkid.cb + 88LL))(
                    pidl,
                    ppv,
                    0,
                    &pstr);
            if ( v12 >= 0 )
              v12 = StrRetToStrW(&pstr, (LPCITEMIDLIST)ppv, &v19);
            (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
            if ( v12 >= 0 )
            {
              v13 = StrCmpIW(ppsz, v19);
              v7 = v13;
              if ( !v13 )
              {
                v15 = CSearchDelegateFolder::_CompareSecondary(
                        v14,
                        (const struct _ITEMIDLIST_RELATIVE *)a3,
                        (const struct _ITEMIDLIST_RELATIVE *)a4);
                v7 = v15;
                if ( !v15 )
                  v7 = ILCompareRelIDs(v10, a3, a4, a2);
              }
              CoTaskMemFree(v19);
            }
          }
          CoTaskMemFree(ppsz);
        }
      }
      ILFree(v9);
    }
    ILFree(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180042090  mov     [rsp-8+arg_8], rdx
0x180042095  push    rbp
0x180042096  push    rbx
0x180042097  push    rsi
0x180042098  push    rdi
0x180042099  push    r12
0x18004209b  push    r13
0x18004209d  push    r14
0x18004209f  push    r15
0x1800420a1  lea     rbp, [rsp-68h]
0x1800420a6  sub     rsp, 168h
0x1800420ad  mov     r13, rcx
0x1800420b0  mov     r14, r9
0x1800420b3  mov     rcx, r8; pidl
0x1800420b6  mov     r15, r8
0x1800420b9  xor     ebx, ebx
0x1800420bb  call    cs:__imp_ILCloneFirst
0x1800420c1  mov     r12, rax
0x1800420c4  test    rax, rax
0x1800420c7  jz      loc_18004229C
0x1800420cd  mov     rcx, r14; pidl
0x1800420d0  call    cs:__imp_ILCloneFirst
0x1800420d6  mov     rsi, rax
0x1800420d9  test    rax, rax
0x1800420dc  jz      loc_180042293
0x1800420e2  lea     rax, [r13-8]
0x1800420e6  mov     rdx, r12; pidl
0x1800420e9  neg     rax
0x1800420ec  lea     r9, [rsp+1A0h+ppv]; ppv
0x1800420f1  lea     rax, [rsp+1A0h+pidl]
0x1800420f6  sbb     rdi, rdi
0x1800420f9  mov     [rsp+1A0h+ppidlLast], rax; ppidlLast
0x1800420fe  and     rdi, r13
0x180042101  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180042108  xor     r13d, r13d
0x18004210b  mov     rcx, rdi; psfRoot
0x18004210e  mov     [rsp+1A0h+ppsz], r13
0x180042113  mov     [rsp+1A0h+ppv], r13
0x180042118  mov     [rsp+1A0h+pidl], r13
0x18004211d  call    cs:__imp_SHBindToFolderIDListParent
0x180042123  test    eax, eax
0x180042125  js      loc_18004228A
0x18004212b  xor     edx, edx; Val
0x18004212d  lea     rcx, [rsp+1A0h+pstr]; void *
0x180042132  mov     r8d, 110h; Size
0x180042138  call    memset_0
0x18004213d  mov     rcx, [rsp+1A0h+ppv]
0x180042142  lea     r9, [rsp+1A0h+pstr]
0x180042147  mov     rdx, [rsp+1A0h+pidl]
0x18004214c  xor     r8d, r8d
0x18004214f  mov     rax, [rcx]
0x180042152  mov     rax, [rax+58h]
0x180042156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004215b  mov     r13d, eax
0x18004215e  test    eax, eax
0x180042160  js      short loc_18004217A
0x180042162  mov     rdx, [rsp+1A0h+pidl]; pidl
0x180042167  lea     r8, [rsp+1A0h+ppsz]; ppsz
0x18004216c  lea     rcx, [rsp+1A0h+pstr]; pstr
0x180042171  call    cs:__imp_StrRetToStrW
0x180042177  mov     r13d, eax
0x18004217a  mov     rcx, [rsp+1A0h+ppv]
0x18004217f  mov     rax, [rcx]
0x180042182  mov     rax, [rax+10h]
0x180042186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004218b  xor     eax, eax
0x18004218d  test    r13d, r13d
0x180042190  js      loc_18004228A
0x180042196  mov     [rsp+1A0h+var_160], rax
0x18004219b  lea     r9, [rsp+1A0h+pidl]; ppv
0x1800421a0  mov     [rsp+1A0h+pidl], rax
0x1800421a5  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800421ac  mov     [rsp+1A0h+ppv], rax
0x1800421b1  mov     rdx, rsi; pidl
0x1800421b4  lea     rax, [rsp+1A0h+ppv]
0x1800421b9  mov     rcx, rdi; psfRoot
0x1800421bc  mov     [rsp+1A0h+ppidlLast], rax; ppidlLast
0x1800421c1  call    cs:__imp_SHBindToFolderIDListParent
0x1800421c7  test    eax, eax
0x1800421c9  js      loc_18004227F
0x1800421cf  xor     edx, edx; Val
0x1800421d1  lea     rcx, [rsp+1A0h+pstr]; void *
0x1800421d6  mov     r8d, 110h; Size
0x1800421dc  call    memset_0
0x1800421e1  mov     rcx, [rsp+1A0h+pidl]
0x1800421e6  lea     r9, [rsp+1A0h+pstr]
0x1800421eb  mov     rdx, [rsp+1A0h+ppv]
0x1800421f0  xor     r8d, r8d
0x1800421f3  mov     rax, [rcx]
0x1800421f6  mov     rax, [rax+58h]
0x1800421fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421ff  mov     r13d, eax
0x180042202  test    eax, eax
0x180042204  js      short loc_18004221E
0x180042206  mov     rdx, [rsp+1A0h+ppv]; pidl
0x18004220b  lea     r8, [rsp+1A0h+var_160]; ppsz
0x180042210  lea     rcx, [rsp+1A0h+pstr]; pstr
0x180042215  call    cs:__imp_StrRetToStrW
0x18004221b  mov     r13d, eax
0x18004221e  mov     rcx, [rsp+1A0h+pidl]
0x180042223  mov     rax, [rcx]
0x180042226  mov     rax, [rax+10h]
0x18004222a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004222f  test    r13d, r13d
0x180042232  js      short loc_18004227F
0x180042234  mov     rdx, [rsp+1A0h+var_160]; psz2
0x180042239  mov     rcx, [rsp+1A0h+ppsz]; psz1
0x18004223e  call    cs:__imp_StrCmpIW
0x180042244  movzx   ebx, ax
0x180042247  test    ebx, ebx
0x180042249  jnz     short loc_180042274
0x18004224b  mov     r8, r14; struct _ITEMIDLIST_RELATIVE *
0x18004224e  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x180042251  call    ?_CompareSecondary@CSearchDelegateFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@0@Z; CSearchDelegateFolder::_CompareSecondary(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)
0x180042256  movzx   ebx, ax
0x180042259  test    ebx, ebx
0x18004225b  jnz     short loc_180042274
0x18004225d  mov     r9, [rbp+0A0h+arg_8]
0x180042264  mov     r8, r14
0x180042267  mov     rdx, r15
0x18004226a  mov     rcx, rdi
0x18004226d  call    ILCompareRelIDs
0x180042272  mov     ebx, eax
0x180042274  mov     rcx, [rsp+1A0h+var_160]; pv
0x180042279  call    cs:__imp_CoTaskMemFree
0x18004227f  mov     rcx, [rsp+1A0h+ppsz]; pv
0x180042284  call    cs:__imp_CoTaskMemFree
0x18004228a  mov     rcx, rsi; pidl
0x18004228d  call    cs:__imp_ILFree
0x180042293  mov     rcx, r12; pidl
0x180042296  call    cs:__imp_ILFree
0x18004229c  mov     eax, ebx
0x18004229e  add     rsp, 168h
0x1800422a5  pop     r15
0x1800422a7  pop     r14
0x1800422a9  pop     r13
0x1800422ab  pop     r12
0x1800422ad  pop     rdi
0x1800422ae  pop     rsi
0x1800422af  pop     rbx
0x1800422b0  pop     rbp
0x1800422b1  retn
```
