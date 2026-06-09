# CNetworkExplorerFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x180003c90`
- end: `0x18000400a`
- name: `?GetDisplayNameOf@CNetworkExplorerFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `890`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c90`
- `0x180004010`
- `0x180004cf4`
- `0x180004e60`
- `0x180005210`
- `0x180006584`
- `0x18000f0a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003f76`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003f76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e31`
- `SHLWAPI!SHStrDupW` at `0x180003dde`
- `SHLWAPI!SHStrDupW` at `0x180003dde`
- `SHELL32!SHGetNameFromIDList` at `0x180003e0b`
- `SHELL32!SHGetNameFromIDList` at `0x180003e0b`
- `SHELL32!SHBindToFolderIDListParent` at `0x180003fb2`
- `SHELL32!SHBindToFolderIDListParent` at `0x180003fb2`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180003f43`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180003f43`
- `PROPSYS!PropVariantToStringAlloc` at `0x180003f69`
- `PROPSYS!PropVariantToStringAlloc` at `0x180003f69`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetDisplayNameOf(
        IShellFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  CNetworkExplorerFolder *v8; // rcx
  CNetworkExplorerFolder *v9; // rcx
  unsigned __int64 v10; // rax
  HRESULT Name; // ebx
  __int64 v12; // rdx
  __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rcx
  unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // rax
  const WCHAR *v19; // rcx
  const ITEMIDLIST *lpVtbl; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  const wchar_t *v25; // r8
  bool v26; // zf
  __int64 v27; // rax
  unsigned __int16 *v28; // rdx
  unsigned __int16 *v29; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT ppropvar; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33[264]; // [rsp+60h] [rbp-A0h] BYREF

  v8 = (const struct _ITEMID_CHILD *)((char *)a2 + *(unsigned __int16 *)a2);
  if ( v8 && *(_WORD *)v8 )
  {
    pv = 0;
    ppidlLast = 0;
    if ( this == (IShellFolder *)32 )
      this = 0;
    Name = SHBindToFolderIDListParent(
             this,
             (LPCITEMIDLIST)a2,
             &GUID_000214e6_0000_0000_c000_000000000046,
             &pv,
             &ppidlLast);
    if ( Name >= 0 )
    {
      Name = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, struct _STRRET *))(*(_QWORD *)pv + 88LL))(
               pv,
               ppidlLast,
               a3,
               a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
  }
  else
  {
    if ( (a3 & 0x8000) == 0 )
    {
      pv = 0;
      Name = CNetworkExplorerFolder::_GetName(v8, a2, (unsigned __int16 **)&pv);
      if ( Name < 0 )
        return (unsigned int)Name;
      v19 = (const WCHAR *)pv;
      goto LABEL_20;
    }
    v33[0] = 0;
    if ( (unsigned int)CNetworkExplorerFolder::_IsComputer(v8, a2) )
    {
      pv = 0;
      v10 = *(unsigned __int16 *)a2;
      Name = -2147024809;
      memset(&ppropvar, 0, sizeof(ppropvar));
      if ( (unsigned int)v10 >= 0x12 && *(_DWORD *)((char *)a2 + 6) == 999534523 )
      {
        v12 = *((unsigned __int16 *)a2 + 5);
        if ( v10 >= v12 + 18 )
        {
          if ( (_WORD)v12 )
          {
            if ( a2 != (const struct _ITEMID_CHILD *)-18LL )
            {
              Name = PSGetPropertyFromPropertyStorage(
                       (const struct _ITEMID_CHILD *)((char *)a2 + 18),
                       v12,
                       &PKEY_ItemNameDisplay,
                       &ppropvar);
              if ( Name >= 0 )
              {
                if ( ppropvar.vt )
                {
                  Name = PropVariantToStringAlloc(&ppropvar, (PWSTR *)&pv);
                  PropVariantClear(&ppropvar);
                }
                else
                {
                  Name = -2147023288;
                }
              }
            }
          }
        }
      }
      if ( Name >= 0 )
      {
        v13 = 2147483646;
        v14 = L"\\\\";
        v15 = 260;
        v16 = v33;
        do
        {
          if ( !v13 )
            break;
          if ( !*v14 )
            break;
          *v16++ = *v14++;
          --v13;
          --v15;
        }
        while ( v15 );
        v17 = v16 - 1;
        Name = -2147024774;
        if ( v15 )
        {
          v17 = v16;
          Name = 0;
        }
        *v17 = 0;
        if ( !v15 )
          goto LABEL_16;
        goto LABEL_27;
      }
    }
    else
    {
      if ( (a3 & 0x4000) != 0 )
        return (unsigned int)-2147467259;
      if ( (a3 & 1) != 0 )
        goto LABEL_55;
      lpVtbl = (const ITEMIDLIST *)this[9].lpVtbl;
      pv = 0;
      Name = SHGetNameFromIDList(lpVtbl, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pv);
      if ( Name >= 0 )
      {
        Name = StringCchCopyW(v33, v21, (const unsigned __int16 *)pv);
        if ( Name >= 0 )
        {
          v22 = 260;
          v23 = v33;
          do
          {
            if ( !*v23 )
              break;
            ++v23;
            --v22;
          }
          while ( v22 );
          Name = -2147024809;
          if ( v22 )
            Name = 0;
          v24 = 260 - v22;
          if ( v22 )
          {
            v25 = L"\\";
            v26 = v24 == 260;
            v27 = 2147483646;
            v28 = &v33[v24];
            if ( !v26 )
            {
              do
              {
                if ( !v27 )
                  break;
                if ( !*v25 )
                  break;
                *v28++ = *v25++;
                --v27;
                --v22;
              }
              while ( v22 );
            }
            v29 = v28 - 1;
            Name = -2147024774;
            if ( v22 )
            {
              v29 = v28;
              Name = 0;
            }
            *v29 = 0;
          }
        }
        CoTaskMemFree(pv);
        if ( Name >= 0 )
        {
LABEL_55:
          pv = 0;
          Name = CNetworkExplorerFolder::_GetFIID(v9, a2, (unsigned __int16 **)&pv);
          if ( Name >= 0 )
          {
LABEL_27:
            Name = StringCchCatW(v33, 0x104u, (const unsigned __int16 *)pv);
            if ( Name < 0 )
              goto LABEL_16;
            v19 = v33;
LABEL_20:
            a4->uType = 0;
            Name = SHStrDupW(v19, &a4->pOleStr);
LABEL_16:
            CoTaskMemFree(pv);
          }
        }
      }
    }
  }
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x180003c90  push    rbp
0x180003c92  push    rbx
0x180003c93  push    rsi
0x180003c94  push    rdi
0x180003c95  push    r14
0x180003c97  push    r15
0x180003c99  lea     rbp, [rsp-188h]
0x180003ca1  sub     rsp, 288h
0x180003ca8  mov     rax, cs:__security_cookie
0x180003caf  xor     rax, rsp
0x180003cb2  mov     [rbp+1B0h+var_40], rax
0x180003cb9  mov     rbx, rcx
0x180003cbc  mov     r15, r9
0x180003cbf  movzx   ecx, word ptr [rdx]
0x180003cc2  mov     esi, r8d
0x180003cc5  mov     rdi, rdx
0x180003cc8  add     rcx, rdx; this
0x180003ccb  jz      short loc_180003CD7
0x180003ccd  cmp     word ptr [rcx], 0
0x180003cd1  jnz     loc_180003F81
0x180003cd7  xor     r14d, r14d
0x180003cda  bt      esi, 0Fh
0x180003cde  jnb     loc_180003DBD
0x180003ce4  mov     [rsp+2B0h+var_250], r14w
0x180003cea  call    ?_IsComputer@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CNetworkExplorerFolder::_IsComputer(_ITEMIDLIST_RELATIVE const *)
0x180003cef  test    eax, eax
0x180003cf1  jz      loc_180003DE8
0x180003cf7  xor     eax, eax
0x180003cf9  mov     [rsp+2B0h+pv], r14
0x180003cfe  mov     qword ptr [rsp+2B0h+ppropvar+10h], rax
0x180003d03  xorps   xmm0, xmm0
0x180003d06  movzx   eax, word ptr [rdi]
0x180003d09  mov     ebx, 80070057h
0x180003d0e  movups  xmmword ptr [rsp+2B0h+ppropvar], xmm0
0x180003d13  cmp     eax, 12h
0x180003d16  jb      short loc_180003D32
0x180003d18  cmp     dword ptr [rdi+6], 3B93AFBBh
0x180003d1f  jnz     short loc_180003D32
0x180003d21  movzx   edx, word ptr [rdi+0Ah]; cb
0x180003d25  lea     rcx, [rdx+12h]
0x180003d29  cmp     rax, rcx
0x180003d2c  jnb     loc_180003F21
0x180003d32  test    ebx, ebx
0x180003d34  js      short loc_180003D9C
0x180003d36  mov     eax, 7FFFFFFEh
0x180003d3b  lea     r8, asc_180012D04; "\\\\"
0x180003d42  mov     ecx, 104h
0x180003d47  lea     r9, [rsp+2B0h+var_250]
0x180003d4c  nop     dword ptr [rax+00h]
0x180003d50  test    rax, rax
0x180003d53  jz      short loc_180003D73
0x180003d55  movzx   edx, word ptr [r8]
0x180003d59  test    dx, dx
0x180003d5c  jz      short loc_180003D73
0x180003d5e  mov     [r9], dx
0x180003d62  add     r8, 2
0x180003d66  add     r9, 2
0x180003d6a  dec     rax
0x180003d6d  sub     rcx, 1
0x180003d71  jnz     short loc_180003D50
0x180003d73  test    rcx, rcx
0x180003d76  lea     rax, [r9-2]
0x180003d7a  mov     ebx, 8007007Ah
0x180003d7f  cmovnz  rax, r9
0x180003d83  cmovnz  ebx, r14d
0x180003d87  mov     [rax], r14w
0x180003d8b  jnz     loc_180003E5B
0x180003d91  mov     rcx, [rsp+2B0h+pv]; pv
0x180003d96  call    cs:__imp_CoTaskMemFree
0x180003d9c  mov     eax, ebx
0x180003d9e  mov     rcx, [rbp+1B0h+var_40]
0x180003da5  xor     rcx, rsp; StackCookie
0x180003da8  call    __security_check_cookie
0x180003dad  add     rsp, 288h
0x180003db4  pop     r15
0x180003db6  pop     r14
0x180003db8  pop     rdi
0x180003db9  pop     rsi
0x180003dba  pop     rbx
0x180003dbb  pop     rbp
0x180003dbc  retn
0x180003dbd  lea     r8, [rsp+2B0h+pv]; unsigned __int16 **
0x180003dc2  mov     [rsp+2B0h+pv], r14
0x180003dc7  call    ?_GetName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetName(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x180003dcc  mov     ebx, eax
0x180003dce  test    eax, eax
0x180003dd0  js      short loc_180003D9C
0x180003dd2  mov     rcx, [rsp+2B0h+pv]; psz
0x180003dd7  lea     rdx, [r15+8]; ppwsz
0x180003ddb  mov     [r15], r14d
0x180003dde  call    cs:__imp_SHStrDupW
0x180003de4  mov     ebx, eax
0x180003de6  jmp     short loc_180003D91
0x180003de8  bt      esi, 0Eh
0x180003dec  jb      loc_180004000
0x180003df2  test    sil, 1
0x180003df6  jnz     short loc_180003E3F
0x180003df8  mov     rcx, [rbx+48h]; pidl
0x180003dfc  lea     r8, [rsp+2B0h+pv]; ppszName
0x180003e01  mov     edx, 80028000h; sigdnName
0x180003e06  mov     [rsp+2B0h+pv], r14
0x180003e0b  call    cs:__imp_SHGetNameFromIDList
0x180003e11  mov     ebx, eax
0x180003e13  test    eax, eax
0x180003e15  js      short loc_180003D9C
0x180003e17  mov     r8, [rsp+2B0h+pv]; unsigned __int16 *
0x180003e1c  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180003e21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003e26  mov     ebx, eax
0x180003e28  test    eax, eax
0x180003e2a  jns     short loc_180003E83
0x180003e2c  mov     rcx, [rsp+2B0h+pv]; pv
0x180003e31  call    cs:__imp_CoTaskMemFree
0x180003e37  test    ebx, ebx
0x180003e39  js      loc_180003D9C
0x180003e3f  lea     r8, [rsp+2B0h+pv]; unsigned __int16 **
0x180003e44  mov     [rsp+2B0h+pv], r14
0x180003e49  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180003e4c  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x180003e51  mov     ebx, eax
0x180003e53  test    eax, eax
0x180003e55  js      loc_180003D9C
0x180003e5b  mov     r8, [rsp+2B0h+pv]; unsigned __int16 *
0x180003e60  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180003e65  mov     edx, 104h; unsigned __int64
0x180003e6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e6f  mov     ebx, eax
0x180003e71  test    eax, eax
0x180003e73  js      loc_180003D91
0x180003e79  lea     rcx, [rsp+2B0h+var_250]
0x180003e7e  jmp     loc_180003DD7
0x180003e83  mov     ecx, 104h
0x180003e88  lea     rax, [rsp+2B0h+var_250]
0x180003e8d  nop     dword ptr [rax]
0x180003e90  cmp     [rax], r14w
0x180003e94  jz      short loc_180003EA0
0x180003e96  add     rax, 2
0x180003e9a  sub     rcx, 1
0x180003e9e  jnz     short loc_180003E90
0x180003ea0  test    rcx, rcx
0x180003ea3  mov     ebx, 80070057h
0x180003ea8  mov     edx, 104h
0x180003ead  cmovnz  ebx, r14d
0x180003eb1  sub     rdx, rcx
0x180003eb4  test    rcx, rcx
0x180003eb7  cmovz   rdx, r14
0x180003ebb  jz      loc_180003E2C
0x180003ec1  mov     ecx, 104h
0x180003ec6  lea     r8, asc_180012D70; "\\"
0x180003ecd  sub     rcx, rdx
0x180003ed0  mov     eax, 7FFFFFFEh
0x180003ed5  lea     rdx, [rsp+rdx*2+2B0h+var_250]
0x180003eda  jz      short loc_180003F04
0x180003edc  nop     dword ptr [rax+00h]
0x180003ee0  test    rax, rax
0x180003ee3  jz      short loc_180003F04
0x180003ee5  movzx   r9d, word ptr [r8]
0x180003ee9  test    r9w, r9w
0x180003eed  jz      short loc_180003F04
0x180003eef  mov     [rdx], r9w
0x180003ef3  add     r8, 2
0x180003ef7  add     rdx, 2
0x180003efb  dec     rax
0x180003efe  sub     rcx, 1
0x180003f02  jnz     short loc_180003EE0
0x180003f04  test    rcx, rcx
0x180003f07  lea     rax, [rdx-2]
0x180003f0b  mov     ebx, 8007007Ah
0x180003f10  cmovnz  rax, rdx
0x180003f14  cmovnz  ebx, r14d
0x180003f18  mov     [rax], r14w
0x180003f1c  jmp     loc_180003E2C
0x180003f21  test    dx, dx
0x180003f24  jz      loc_180003D32
0x180003f2a  lea     rcx, [rdi+12h]; psps
0x180003f2e  test    rcx, rcx
0x180003f31  jz      loc_180003D32
0x180003f37  lea     r9, [rsp+2B0h+ppropvar]; ppropvar
0x180003f3c  lea     r8, PKEY_ItemNameDisplay; rpkey
0x180003f43  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180003f49  mov     ebx, eax
0x180003f4b  test    eax, eax
0x180003f4d  js      loc_180003D32
0x180003f53  cmp     word ptr [rsp+2B0h+ppropvar], r14w
0x180003f59  jz      loc_180003FF6
0x180003f5f  lea     rdx, [rsp+2B0h+pv]; ppszOut
0x180003f64  lea     rcx, [rsp+2B0h+ppropvar]; propvar
0x180003f69  call    cs:__imp_PropVariantToStringAlloc
0x180003f6f  lea     rcx, [rsp+2B0h+ppropvar]; pvar
0x180003f74  mov     ebx, eax
0x180003f76  call    cs:__imp_PropVariantClear
0x180003f7c  jmp     loc_180003D32
0x180003f81  xor     r14d, r14d
0x180003f84  lea     rax, [rbx-20h]
0x180003f88  test    rax, rax
0x180003f8b  mov     [rsp+2B0h+pv], r14
0x180003f90  lea     rax, [rsp+2B0h+var_278]
0x180003f95  mov     [rsp+2B0h+var_278], r14
0x180003f9a  cmovz   rbx, r14
0x180003f9e  mov     [rsp+2B0h+ppidlLast], rax; ppidlLast
0x180003fa3  mov     rcx, rbx; psfRoot
0x180003fa6  lea     r9, [rsp+2B0h+pv]; ppv
0x180003fab  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180003fb2  call    cs:__imp_SHBindToFolderIDListParent
0x180003fb8  mov     ebx, eax
0x180003fba  test    eax, eax
0x180003fbc  js      loc_180003D9C
0x180003fc2  mov     rcx, [rsp+2B0h+pv]
0x180003fc7  mov     r9, r15
0x180003fca  mov     rdx, [rsp+2B0h+var_278]
0x180003fcf  mov     r8d, esi
0x180003fd2  mov     rax, [rcx]
0x180003fd5  mov     rax, [rax+58h]
0x180003fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fde  mov     rcx, [rsp+2B0h+pv]
0x180003fe3  mov     ebx, eax
0x180003fe5  mov     rax, [rcx]
0x180003fe8  mov     rax, [rax+10h]
0x180003fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff1  jmp     loc_180003D9C
0x180003ff6  mov     ebx, 80070648h
0x180003ffb  jmp     loc_180003D32
0x180004000  mov     ebx, 80004005h
0x180004005  jmp     loc_180003D9C
```
