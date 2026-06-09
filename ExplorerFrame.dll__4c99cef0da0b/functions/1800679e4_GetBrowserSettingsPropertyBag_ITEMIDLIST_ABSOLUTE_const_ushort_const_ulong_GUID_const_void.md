# GetBrowserSettingsPropertyBag(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,_GUID const &,void * *)

- ea: `0x1800679e4`
- end: `0x180067cdd`
- name: `?GetBrowserSettingsPropertyBag@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGKAEBU_GUID@@PEAPEAX@Z`
- size: `761`
- prototype: `__int64 __usercall@<rax>(const struct _ITEMIDLIST_ABSOLUTE *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066f40`
- `0x1800d3158`
- `0x1800d31d0`

## callees

- `0x1800243b0`
- `0x1800679e4`
- `0x180067ce4`
- `0x1800688b0`
- `0x1800f3c00`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180067a41`
- `SHELL32!SHCreateItemFromIDList` at `0x180067a90`
- `SHELL32!SHCreateItemFromIDList` at `0x180067a41`
- `SHELL32!SHCreateItemFromIDList` at `0x180067a90`
- `SHELL32!SHGetPathFromIDListW` at `0x180067b8a`
- `SHELL32!SHGetPathFromIDListW` at `0x180067b8a`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x180067af3`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x180067af3`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x180067c5a`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x180067c5a`
- `SHLWAPI!PathIsUNCW` at `0x180067b9b`
- `SHLWAPI!PathIsUNCW` at `0x180067b9b`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180067ac9`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180067ac9`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x180067bcd`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x180067bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067ca5`

## pseudocode

```c
__int64 __fastcall GetBrowserSettingsPropertyBag(
        const ITEMIDLIST *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **a5)
{
  const ITEMIDLIST *v7; // rsi
  int v8; // ebx
  int v9; // r14d
  BOOL IsUNCW; // eax
  DWORD v11; // r8d
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  struct ITopViewAwareItem *v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v18; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v19; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v20[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v21[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszBagName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  ppv = 0;
  v19 = FOLDERTYPEID_Generic;
  v7 = a1;
  if ( SHCreateItemFromIDList(a1, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
  {
    GetShellFolderTypeFromItem((struct IShellItem *)ppv, &v19);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  ppv = 0;
  v18 = FOLDERTYPEID_Generic;
  if ( SHCreateItemFromIDList(v7, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
  {
    GetShellFolderTypeFromItem((struct IShellItem *)ppv, &v18);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  v8 = SHStringFromGUIDW(&v18, v21, 260);
  if ( v8 >= 0 )
  {
    v17 = 0;
    v8 = SHGetFolderTypeDescription(&v18, &GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80, &v17);
    if ( v8 >= 0 )
    {
      v9 = 0;
      LODWORD(ppv) = 0;
      if ( (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)v17 + 104LL))(v17, &ppv) >= 0 && (_DWORD)ppv == 1 )
      {
        v16 = 0;
        if ( (int)GetTopViewAwareItemFromIDList((const struct _ITEMIDLIST_ABSOLUTE *)v7, &v16) >= 0 )
        {
          v9 = 1;
          memset(v20, 0, sizeof(v20));
          v8 = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, _OWORD *))(*(_QWORD *)v16 + 24LL))(v16, v20);
          if ( v8 >= 0 )
          {
            v15 = 0;
            v8 = SHGetTopViewDescription(v20, &GUID_fe812157_522c_46cb_8d53_6efe3dce2c46, &v15);
            if ( v8 >= 0 )
            {
              pv = 0;
              v8 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 104LL))(v15, &pv);
              if ( v8 >= 0 )
              {
                v8 = StringCchCopyW(v21, 0x104u, (const unsigned __int16 *)pv);
                CoTaskMemFree(pv);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            }
          }
          (*(void (__fastcall **)(struct ITopViewAwareItem *))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v8 >= 0 )
      {
        if ( v9 )
          a3 = a3 & 0xFFFFFFF3 | 8;
        v8 = StringCchPrintfW(pszBagName, 0x104u, L"%s\\%s", L"Shell", v21);
        if ( v8 >= 0 )
        {
          IsUNCW = SHGetPathFromIDListW(v7, pszPath);
          if ( IsUNCW )
            IsUNCW = PathIsUNCW(pszPath);
          v11 = a3 | 0x20;
          if ( !IsUNCW )
            v11 = a3;
          if ( (v11 & 8) != 0 )
            v7 = 0;
          return (unsigned int)SHGetViewStatePropertyBag(v7, pszBagName, v11, a4, a5);
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800679e4  push    rbp
0x1800679e6  push    rbx
0x1800679e7  push    rsi
0x1800679e8  push    rdi
0x1800679e9  push    r12
0x1800679eb  push    r14
0x1800679ed  push    r15
0x1800679ef  lea     rbp, [rsp-5E0h]
0x1800679f7  sub     rsp, 6E0h
0x1800679fe  mov     rax, cs:__security_cookie
0x180067a05  xor     rax, rsp
0x180067a08  mov     [rbp+610h+var_40], rax
0x180067a0f  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x180067a16  mov     r12, [rbp+610h+arg_20]
0x180067a1d  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180067a24  mov     edi, r8d
0x180067a27  mov     [rsp+710h+ppv], 0
0x180067a30  lea     r8, [rsp+710h+ppv]; ppv
0x180067a35  mov     r15, r9
0x180067a38  movdqu  xmmword ptr [rsp+710h+var_6A8.Data1], xmm0
0x180067a3e  mov     rsi, rcx
0x180067a41  call    cs:__imp_SHCreateItemFromIDList
0x180067a47  test    eax, eax
0x180067a49  js      short loc_180067A6B
0x180067a4b  mov     rcx, [rsp+710h+ppv]; struct IShellItem *
0x180067a50  lea     rdx, [rsp+710h+var_6A8]; struct _GUID *
0x180067a55  call    ?GetShellFolderTypeFromItem@@YAJPEAUIShellItem@@PEAU_GUID@@@Z; GetShellFolderTypeFromItem(IShellItem *,_GUID *)
0x180067a5a  mov     rcx, [rsp+710h+ppv]
0x180067a5f  mov     rax, [rcx]
0x180067a62  mov     rax, [rax+10h]
0x180067a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a6b  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x180067a72  lea     r8, [rsp+710h+ppv]; ppv
0x180067a77  mov     [rsp+710h+ppv], 0
0x180067a80  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180067a87  mov     rcx, rsi; pidl
0x180067a8a  movdqu  xmmword ptr [rsp+710h+var_6B8.Data1], xmm0
0x180067a90  call    cs:__imp_SHCreateItemFromIDList
0x180067a96  test    eax, eax
0x180067a98  js      short loc_180067ABA
0x180067a9a  mov     rcx, [rsp+710h+ppv]; struct IShellItem *
0x180067a9f  lea     rdx, [rsp+710h+var_6B8]; struct _GUID *
0x180067aa4  call    ?GetShellFolderTypeFromItem@@YAJPEAUIShellItem@@PEAU_GUID@@@Z; GetShellFolderTypeFromItem(IShellItem *,_GUID *)
0x180067aa9  mov     rcx, [rsp+710h+ppv]
0x180067aae  mov     rax, [rcx]
0x180067ab1  mov     rax, [rax+10h]
0x180067ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067aba  mov     r8d, 104h
0x180067ac0  lea     rdx, [rbp+610h+var_670]
0x180067ac4  lea     rcx, [rsp+710h+var_6B8]
0x180067ac9  call    cs:__imp_SHStringFromGUIDW
0x180067acf  mov     ebx, eax
0x180067ad1  test    eax, eax
0x180067ad3  js      loc_180067BD5
0x180067ad9  lea     r8, [rsp+710h+var_6C0]
0x180067ade  mov     [rsp+710h+var_6C0], 0
0x180067ae7  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x180067aee  lea     rcx, [rsp+710h+var_6B8]
0x180067af3  call    cs:__imp_SHGetFolderTypeDescription
0x180067af9  mov     ebx, eax
0x180067afb  test    eax, eax
0x180067afd  js      loc_180067BD5
0x180067b03  mov     rcx, [rsp+710h+var_6C0]
0x180067b08  lea     rdx, [rsp+710h+ppv]
0x180067b0d  xor     r14d, r14d
0x180067b10  mov     dword ptr [rsp+710h+ppv], r14d
0x180067b15  mov     rax, [rcx]
0x180067b18  mov     rax, [rax+68h]
0x180067b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b21  test    eax, eax
0x180067b23  js      short loc_180067B30
0x180067b25  cmp     dword ptr [rsp+710h+ppv], 1
0x180067b2a  jz      loc_180067BF8
0x180067b30  mov     rcx, [rsp+710h+var_6C0]
0x180067b35  mov     rax, [rcx]
0x180067b38  mov     rax, [rax+10h]
0x180067b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b41  test    ebx, ebx
0x180067b43  js      loc_180067BD5
0x180067b49  test    r14d, r14d
0x180067b4c  jnz     loc_180067CD2
0x180067b52  lea     rax, [rbp+610h+var_670]
0x180067b56  mov     edx, 104h; unsigned __int64
0x180067b5b  lea     r9, pszBagName; "Shell"
0x180067b62  mov     [rsp+710h+var_6F0], rax
0x180067b67  lea     r8, aSS_0; "%s\\%s"
0x180067b6e  lea     rcx, [rbp+610h+pszBagName]; unsigned __int16 *
0x180067b75  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067b7a  mov     ebx, eax
0x180067b7c  test    eax, eax
0x180067b7e  js      short loc_180067BD5
0x180067b80  lea     rdx, [rbp+610h+pszPath]; pszPath
0x180067b87  mov     rcx, rsi; pidl
0x180067b8a  call    cs:__imp_SHGetPathFromIDListW
0x180067b90  test    eax, eax
0x180067b92  jz      short loc_180067BA1
0x180067b94  lea     rcx, [rbp+610h+pszPath]; pszPath
0x180067b9b  call    cs:__imp_PathIsUNCW
0x180067ba1  mov     r8d, edi
0x180067ba4  mov     [rsp+710h+var_6F0], r12; ppv
0x180067ba9  or      r8d, 20h
0x180067bad  lea     rdx, [rbp+610h+pszBagName]; pszBagName
0x180067bb4  test    eax, eax
0x180067bb6  mov     r9, r15; riid
0x180067bb9  mov     eax, 0
0x180067bbe  cmovz   r8d, edi; dwFlags
0x180067bc2  test    r8b, 8
0x180067bc6  cmovnz  rsi, rax
0x180067bca  mov     rcx, rsi; pidl
0x180067bcd  call    cs:__imp_SHGetViewStatePropertyBag
0x180067bd3  mov     ebx, eax
0x180067bd5  mov     eax, ebx
0x180067bd7  mov     rcx, [rbp+610h+var_40]
0x180067bde  xor     rcx, rsp; StackCookie
0x180067be1  call    __security_check_cookie
0x180067be6  add     rsp, 6E0h
0x180067bed  pop     r15
0x180067bef  pop     r14
0x180067bf1  pop     r12
0x180067bf3  pop     rdi
0x180067bf4  pop     rsi
0x180067bf5  pop     rbx
0x180067bf6  pop     rbp
0x180067bf7  retn
0x180067bf8  lea     rdx, [rsp+710h+var_6C8]; struct ITopViewAwareItem **
0x180067bfd  mov     [rsp+710h+var_6C8], r14
0x180067c02  mov     rcx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180067c05  call    ?GetTopViewAwareItemFromIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUITopViewAwareItem@@@Z; GetTopViewAwareItemFromIDList(_ITEMIDLIST_ABSOLUTE const *,ITopViewAwareItem * *)
0x180067c0a  test    eax, eax
0x180067c0c  js      loc_180067B30
0x180067c12  mov     rcx, [rsp+710h+var_6C8]
0x180067c17  lea     rdx, [rsp+710h+var_698]
0x180067c1c  xorps   xmm0, xmm0
0x180067c1f  mov     r14d, 1
0x180067c25  movups  [rsp+710h+var_698], xmm0
0x180067c2a  movups  [rbp+610h+var_688], xmm0
0x180067c2e  mov     rax, [rcx]
0x180067c31  mov     rax, [rax+18h]
0x180067c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c3a  mov     ebx, eax
0x180067c3c  test    eax, eax
0x180067c3e  js      short loc_180067CBC
0x180067c40  lea     r8, [rsp+710h+var_6D0]
0x180067c45  mov     [rsp+710h+var_6D0], 0
0x180067c4e  lea     rdx, _GUID_fe812157_522c_46cb_8d53_6efe3dce2c46
0x180067c55  lea     rcx, [rsp+710h+var_698]
0x180067c5a  call    cs:__imp_SHGetTopViewDescription
0x180067c60  mov     ebx, eax
0x180067c62  test    eax, eax
0x180067c64  js      short loc_180067CBC
0x180067c66  mov     rcx, [rsp+710h+var_6D0]
0x180067c6b  lea     rdx, [rsp+710h+pv]
0x180067c70  mov     [rsp+710h+pv], 0
0x180067c79  mov     rax, [rcx]
0x180067c7c  mov     rax, [rax+68h]
0x180067c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c85  mov     ebx, eax
0x180067c87  test    eax, eax
0x180067c89  js      short loc_180067CAB
0x180067c8b  mov     r8, [rsp+710h+pv]; unsigned __int16 *
0x180067c90  lea     rcx, [rbp+610h+var_670]; unsigned __int16 *
0x180067c94  mov     edx, 104h; unsigned __int64
0x180067c99  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180067c9e  mov     rcx, [rsp+710h+pv]; pv
0x180067ca3  mov     ebx, eax
0x180067ca5  call    cs:__imp_CoTaskMemFree
0x180067cab  mov     rcx, [rsp+710h+var_6D0]
0x180067cb0  mov     rax, [rcx]
0x180067cb3  mov     rax, [rax+10h]
0x180067cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cbc  mov     rcx, [rsp+710h+var_6C8]
0x180067cc1  mov     rax, [rcx]
0x180067cc4  mov     rax, [rax+10h]
0x180067cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ccd  jmp     loc_180067B30
0x180067cd2  and     edi, 0FFFFFFFBh
0x180067cd5  or      edi, 8
0x180067cd8  jmp     loc_180067B52
```
