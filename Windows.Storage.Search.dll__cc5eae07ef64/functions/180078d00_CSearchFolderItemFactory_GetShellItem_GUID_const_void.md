# CSearchFolderItemFactory::GetShellItem(_GUID const &,void * *)

- ea: `0x180078d00`
- end: `0x180078f62`
- name: `?GetShellItem@CSearchFolderItemFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `610`
- prototype: `int(CSearchFolderItemFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180078b20`

## callees

- `0x180005bf0`
- `0x18000e450`
- `0x180035860`
- `0x18003c4c0`
- `0x180040c30`
- `0x180042b90`
- `0x180071dc0`
- `0x180072cf4`
- `0x180078d00`
- `0x18007dcf0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180078e3d`
- `SHCORE!SHStrDupW` at `0x180078e3d`
- `Windows.Storage!ILFree` at `0x180078f25`
- `Windows.Storage!ILFree` at `0x180078f25`
- `Windows.Storage!SHCreateShellItemArrayFromShellItem` at `0x180078da4`
- `Windows.Storage!SHCreateShellItemArrayFromShellItem` at `0x180078da4`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180078f18`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180078f18`

## pseudocode

```c
__int64 __fastcall CSearchFolderItemFactory::GetShellItem(
        CSearchFolderItemFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, _BYTE *); // rcx
  GUID v7; // xmm0
  int SingleVisibleInList; // ebx
  __int128 v9; // xmm0
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _BYTE *); // rcx
  const WCHAR *v11; // rcx
  struct _DSA *v12; // rcx
  PVOID ItemPtr; // rax
  struct _DSA *v14; // rcx
  __int64 v15; // rcx
  IShellItem *psi[2]; // [rsp+20h] [rbp-A9h] BYREF
  struct IAutoListDescription *v18[2]; // [rsp+30h] [rbp-99h] BYREF
  _BYTE v19[8]; // [rsp+40h] [rbp-89h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-81h] BYREF
  __int128 v21; // [rsp+50h] [rbp-79h]
  int v22; // [rsp+60h] [rbp-69h]
  int v23; // [rsp+6Ch] [rbp-5Dh]
  int v24; // [rsp+70h] [rbp-59h]
  __int128 v25; // [rsp+7Ch] [rbp-4Dh]
  int v26; // [rsp+8Ch] [rbp-3Dh]
  int v27; // [rsp+94h] [rbp-35h]
  PVOID v28; // [rsp+98h] [rbp-31h]
  int v29; // [rsp+A0h] [rbp-29h]
  PVOID v30; // [rsp+A8h] [rbp-21h]
  _BYTE v31[8]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v32[8]; // [rsp+B8h] [rbp-11h] BYREF
  _BYTE v33[8]; // [rsp+C0h] [rbp-9h] BYREF
  void *ppv; // [rsp+C8h] [rbp-1h] BYREF
  _BYTE v35[32]; // [rsp+D0h] [rbp+7h] BYREF

  *a3 = 0;
  memset_0(v19, 0, 0xB0u);
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, _BYTE *))*((_QWORD *)this + 13);
  if ( v6 )
  {
    SingleVisibleInList = (**v6)(v6, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v33);
  }
  else
  {
    psi[0] = 0;
    if ( (unsigned int)IsMSSearchEnabled(0, 0) )
      v7 = GUID_238dff6e_1240_41d4_b991_534014880670;
    else
      v7 = GUID_4f800859_0bd6_4e63_bbdc_38d3b616ca48;
    *(GUID *)v18 = v7;
    SingleVisibleInList = SHCreateAutoListWithID(v18, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, psi);
    if ( SingleVisibleInList < 0 )
      return (unsigned int)SingleVisibleInList;
    SingleVisibleInList = SHCreateShellItemArrayFromShellItem(psi[0], &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &ppv);
    ((void (__fastcall *)(IShellItem *))psi[0]->lpVtbl->Release)(psi[0]);
  }
  if ( SingleVisibleInList >= 0 )
  {
    v9 = *(_OWORD *)((char *)this + 72);
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, _BYTE *))*((_QWORD *)this + 7);
    v23 = *((_DWORD *)this + 12);
    v24 = *((_DWORD *)this + 13);
    v26 = *((_DWORD *)this + 22);
    v25 = v9;
    v21 = *((_OWORD *)this + 2);
    if ( !v10
      || (v22 |= 0x40u,
          SingleVisibleInList = (**v10)(v10, &GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9, v31),
          SingleVisibleInList >= 0) )
    {
      v11 = (const WCHAR *)*((_QWORD *)this + 3);
      if ( v11 )
        SHStrDupW(v11, &ppwsz);
      v12 = (struct _DSA *)*((_QWORD *)this + 8);
      if ( v12 && *(_DWORD *)v12 )
      {
        v29 = *(_DWORD *)v12;
        ItemPtr = g_pfn_DSA_GetItemPtr(v12, 0);
        v22 |= 0x80u;
        v30 = ItemPtr;
      }
      v14 = (struct _DSA *)*((_QWORD *)this + 12);
      if ( v14 && *(_DWORD *)v14 )
      {
        v27 = *(_DWORD *)v14;
        v28 = g_pfn_DSA_GetItemPtr(v14, 0);
      }
      v15 = *((_QWORD *)this + 14);
      if ( !v15
        || (SingleVisibleInList = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 112LL))(v15, v35),
            SingleVisibleInList >= 0) )
      {
        SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v32);
        if ( SingleVisibleInList >= 0 )
        {
          v18[0] = 0;
          SingleVisibleInList = CAutoList::s_CreateInstance(
                                  (const struct AUTOLISTINIT *)v19,
                                  0,
                                  &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                  (void **)v18);
          if ( SingleVisibleInList >= 0 )
          {
            psi[0] = 0;
            SingleVisibleInList = SHCreateSearchIDListFromAutoList(v18[0], 0, (LPITEMIDLIST *)psi);
            if ( SingleVisibleInList >= 0 )
            {
              SingleVisibleInList = SHCreateItemFromIDList((LPCITEMIDLIST)psi[0], a2, a3);
              ILFree((LPITEMIDLIST)psi[0]);
            }
            (*(void (__fastcall **)(struct IAutoListDescription *))(*(_QWORD *)v18[0] + 16LL))(v18[0]);
          }
        }
      }
    }
    ClearAutoListInit((struct AUTOLISTINIT *)v19);
  }
  return (unsigned int)SingleVisibleInList;
}

```

## disassembly

```asm
0x180078d00  push    rbp
0x180078d02  push    rbx
0x180078d03  push    rsi
0x180078d04  push    rdi
0x180078d05  push    r14
0x180078d07  lea     rbp, [rsp-37h]
0x180078d0c  sub     rsp, 100h
0x180078d13  mov     rax, cs:__security_cookie
0x180078d1a  xor     rax, rsp
0x180078d1d  mov     [rbp+57h+var_30], rax
0x180078d21  mov     rsi, r8
0x180078d24  mov     qword ptr [r8], 0
0x180078d2b  mov     r14, rdx
0x180078d2e  mov     rdi, rcx
0x180078d31  xor     edx, edx; Val
0x180078d33  lea     rcx, [rsp+120h+var_E0]; void *
0x180078d38  mov     r8d, 0B0h; Size
0x180078d3e  call    memset_0
0x180078d43  mov     rcx, [rdi+68h]
0x180078d47  test    rcx, rcx
0x180078d4a  jnz     short loc_180078DBF
0x180078d4c  xor     edx, edx
0x180078d4e  mov     [rsp+120h+psi], rcx
0x180078d53  call    IsMSSearchEnabled
0x180078d58  xor     edx, edx
0x180078d5a  lea     r9, [rsp+120h+psi]
0x180078d5f  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180078d66  lea     rcx, [rsp+120h+var_F0]
0x180078d6b  test    eax, eax
0x180078d6d  jnz     short loc_180078D78
0x180078d6f  movups  xmm0, xmmword ptr cs:_GUID_4f800859_0bd6_4e63_bbdc_38d3b616ca48.Data1
0x180078d76  jmp     short loc_180078D7F
0x180078d78  movups  xmm0, xmmword ptr cs:_GUID_238dff6e_1240_41d4_b991_534014880670.Data1
0x180078d7f  movdqu  xmmword ptr [rsp+120h+var_F0], xmm0
0x180078d85  call    SHCreateAutoListWithID
0x180078d8a  mov     ebx, eax
0x180078d8c  test    eax, eax
0x180078d8e  js      loc_180078F46
0x180078d94  mov     rcx, [rsp+120h+psi]; psi
0x180078d99  lea     r8, [rbp+57h+ppv]; ppv
0x180078d9d  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180078da4  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x180078daa  mov     rcx, [rsp+120h+psi]
0x180078daf  mov     ebx, eax
0x180078db1  mov     rax, [rcx]
0x180078db4  mov     rax, [rax+10h]
0x180078db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dbd  jmp     short loc_180078DD7
0x180078dbf  mov     rax, [rcx]
0x180078dc2  lea     r8, [rbp+57h+var_60]
0x180078dc6  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180078dcd  mov     rax, [rax]
0x180078dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dd5  mov     ebx, eax
0x180078dd7  test    ebx, ebx
0x180078dd9  js      loc_180078F46
0x180078ddf  movups  xmm0, xmmword ptr [rdi+48h]
0x180078de3  mov     eax, [rdi+30h]
0x180078de6  mov     rcx, [rdi+38h]
0x180078dea  mov     [rbp+57h+var_B4], eax
0x180078ded  mov     eax, [rdi+34h]
0x180078df0  mov     [rbp+57h+var_B0], eax
0x180078df3  mov     eax, [rdi+58h]
0x180078df6  mov     [rbp+57h+var_94], eax
0x180078df9  movups  [rbp+57h+var_A4], xmm0
0x180078dfd  movups  xmm0, xmmword ptr [rdi+20h]
0x180078e01  movdqu  [rbp+57h+var_D0], xmm0
0x180078e06  test    rcx, rcx
0x180078e09  jz      short loc_180078E2F
0x180078e0b  or      [rbp+57h+var_C0], 40h
0x180078e0f  lea     r8, [rbp+57h+var_70]
0x180078e13  mov     rax, [rcx]
0x180078e16  lea     rdx, _GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9
0x180078e1d  mov     rax, [rax]
0x180078e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e25  mov     ebx, eax
0x180078e27  test    eax, eax
0x180078e29  js      loc_180078F3C
0x180078e2f  mov     rcx, [rdi+18h]; psz
0x180078e33  test    rcx, rcx
0x180078e36  jz      short loc_180078E43
0x180078e38  lea     rdx, [rsp+120h+ppwsz]; ppwsz
0x180078e3d  call    cs:__imp_SHStrDupW
0x180078e43  mov     rcx, [rdi+40h]; hdsa
0x180078e47  test    rcx, rcx
0x180078e4a  jz      short loc_180078E67
0x180078e4c  cmp     dword ptr [rcx], 0
0x180078e4f  jz      short loc_180078E67
0x180078e51  mov     eax, [rcx]
0x180078e53  xor     edx, edx; i
0x180078e55  mov     [rbp+57h+var_80], eax
0x180078e58  call    cs:g_pfn_DSA_GetItemPtr
0x180078e5e  bts     [rbp+57h+var_C0], 7
0x180078e63  mov     [rbp+57h+var_78], rax
0x180078e67  mov     rcx, [rdi+60h]; hdsa
0x180078e6b  test    rcx, rcx
0x180078e6e  jz      short loc_180078E86
0x180078e70  cmp     dword ptr [rcx], 0
0x180078e73  jz      short loc_180078E86
0x180078e75  mov     eax, [rcx]
0x180078e77  xor     edx, edx; i
0x180078e79  mov     [rbp+57h+var_8C], eax
0x180078e7c  call    cs:g_pfn_DSA_GetItemPtr
0x180078e82  mov     [rbp+57h+var_88], rax
0x180078e86  mov     rcx, [rdi+70h]
0x180078e8a  test    rcx, rcx
0x180078e8d  jz      short loc_180078EA9
0x180078e8f  mov     rax, [rcx]
0x180078e92  lea     rdx, [rbp+57h+var_50]
0x180078e96  mov     rax, [rax+70h]
0x180078e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e9f  mov     ebx, eax
0x180078ea1  test    eax, eax
0x180078ea3  js      loc_180078F3C
0x180078ea9  lea     r8, [rbp+57h+var_68]
0x180078ead  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180078eb4  lea     rcx, aItem; "item"
0x180078ebb  call    CreateSingleVisibleInList
0x180078ec0  mov     ebx, eax
0x180078ec2  test    eax, eax
0x180078ec4  js      short loc_180078F3C
0x180078ec6  lea     r9, [rsp+120h+var_F0]; void **
0x180078ecb  mov     [rsp+120h+var_F0], 0
0x180078ed4  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x180078edb  xor     edx, edx; struct ICompositionProcessor *
0x180078edd  lea     rcx, [rsp+120h+var_E0]; struct AUTOLISTINIT *
0x180078ee2  call    ?s_CreateInstance@CAutoList@@SAJPEBUAUTOLISTINIT@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CAutoList::s_CreateInstance(AUTOLISTINIT const *,ICompositionProcessor *,_GUID const &,void * *)
0x180078ee7  mov     ebx, eax
0x180078ee9  test    eax, eax
0x180078eeb  js      short loc_180078F3C
0x180078eed  mov     rcx, [rsp+120h+var_F0]; struct IAutoListDescription *
0x180078ef2  lea     r8, [rsp+120h+psi]
0x180078ef7  xor     edx, edx
0x180078ef9  mov     [rsp+120h+psi], 0
0x180078f02  call    SHCreateSearchIDListFromAutoList
0x180078f07  mov     ebx, eax
0x180078f09  test    eax, eax
0x180078f0b  js      short loc_180078F2B
0x180078f0d  mov     rcx, [rsp+120h+psi]; pidl
0x180078f12  mov     r8, rsi; ppv
0x180078f15  mov     rdx, r14; riid
0x180078f18  call    cs:__imp_SHCreateItemFromIDList
0x180078f1e  mov     rcx, [rsp+120h+psi]; pidl
0x180078f23  mov     ebx, eax
0x180078f25  call    cs:__imp_ILFree
0x180078f2b  mov     rcx, [rsp+120h+var_F0]
0x180078f30  mov     rax, [rcx]
0x180078f33  mov     rax, [rax+10h]
0x180078f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f3c  lea     rcx, [rsp+120h+var_E0]; struct AUTOLISTINIT *
0x180078f41  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180078f46  mov     eax, ebx
0x180078f48  mov     rcx, [rbp+57h+var_30]
0x180078f4c  xor     rcx, rsp; StackCookie
0x180078f4f  call    __security_check_cookie
0x180078f54  add     rsp, 100h
0x180078f5b  pop     r14
0x180078f5d  pop     rdi
0x180078f5e  pop     rsi
0x180078f5f  pop     rbx
0x180078f60  pop     rbp
0x180078f61  retn
```
