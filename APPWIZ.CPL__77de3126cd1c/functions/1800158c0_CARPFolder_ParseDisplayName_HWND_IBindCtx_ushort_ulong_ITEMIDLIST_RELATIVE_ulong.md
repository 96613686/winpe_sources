# CARPFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800158c0`
- end: `0x180015ac6`
- name: `?ParseDisplayName@CARPFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `518`
- prototype: `int(CARPFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180008cf8`
- `0x1800158c0`
- `0x18001a0f8`
- `0x18001b000`
- `0x18005165c`
- `0x1800516dc`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180015991`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180015991`
- `SHLWAPI!StrChrW` at `0x180015957`
- `SHLWAPI!StrChrW` at `0x180015957`
- `SHLWAPI!__imp_StrCmpICW` at `0x180015970`
- `SHLWAPI!__imp_StrCmpICW` at `0x180015970`

## pseudocode

```c
__int64 __fastcall CARPFolder::ParseDisplayName(
        CARPFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  int ItemID; // ebx
  BOOL v10; // ebx
  const unsigned __int16 *v11; // rdx
  CARPFolder *v12; // rcx
  __int64 v13; // r8
  int v14; // edi
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rbx
  int v17; // esi
  int v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  void *v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v22[536]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *((_DWORD *)this + 32) )
  {
    return (unsigned int)-2147467263;
  }
  else if ( a6 )
  {
    *a6 = 0;
    ItemID = -2147024809;
    if ( a5 )
      *a5 = 0;
    if ( a4 && !StrChrW(a4, 0x5Cu) && !StrCmpICW(a4, L"::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}") )
    {
      v10 = 0;
      ppv = 0;
      v14 = 1;
      if ( PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
      {
        v19[0] = 0;
        if ( (int)CARPFolder::_GetIconInfo(v12, v11, v13, v22, v19) >= 0
          && (int)IPropertyStore_SetString(ppv, PKEY_IconPath, v22) >= 0 )
        {
          v10 = (int)IPropertyStore_SetInt(ppv, v15, (unsigned int)v19[0]) >= 0;
        }
      }
      memset_0(v22, 0, 0x424u);
      *(_DWORD *)&v22[2] = 3;
      if ( v10 )
      {
        v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))ppv;
        v21 = ppv;
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
        v17 = 0;
      }
      else
      {
        v16 = 0;
        *(_QWORD *)v19 = 0;
        v14 = 0;
        v17 = 2;
      }
      ItemID = CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(v22, v16, (__int64 *)a6, *((_QWORD *)this + 13));
      if ( v17 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v19);
      if ( v14 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      if ( ItemID >= 0 && a7 )
        ItemID = (*(__int64 (__fastcall **)(CARPFolder *, __int64, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(*(_QWORD *)this + 72LL))(
                   this,
                   1,
                   a6,
                   a7);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)ItemID;
}

```

## disassembly

```asm
0x1800158c0  mov     [rsp-8+arg_8], rbx
0x1800158c5  mov     [rsp-8+arg_10], rsi
0x1800158ca  push    rbp
0x1800158cb  push    rdi
0x1800158cc  push    r12
0x1800158ce  push    r14
0x1800158d0  push    r15
0x1800158d2  lea     rbp, [rsp-390h]
0x1800158da  sub     rsp, 490h
0x1800158e1  mov     rax, cs:__security_cookie
0x1800158e8  xor     rax, rsp
0x1800158eb  mov     [rbp+3B0h+var_30], rax
0x1800158f2  cmp     dword ptr [rcx+80h], 0
0x1800158f9  mov     rdi, r9
0x1800158fc  mov     rax, [rbp+3B0h+arg_20]
0x180015903  mov     r15, rcx
0x180015906  mov     r14, [rbp+3B0h+arg_28]
0x18001590d  mov     r12, [rbp+3B0h+arg_30]
0x180015914  jz      short loc_180015920
0x180015916  mov     ebx, 80004001h
0x18001591b  jmp     loc_180015A99
0x180015920  test    r14, r14
0x180015923  jnz     short loc_18001592F
0x180015925  mov     ebx, 80004003h
0x18001592a  jmp     loc_180015A99
0x18001592f  mov     qword ptr [r14], 0
0x180015936  mov     ebx, 80070057h
0x18001593b  test    rax, rax
0x18001593e  jz      short loc_180015946
0x180015940  mov     dword ptr [rax], 0
0x180015946  test    rdi, rdi
0x180015949  jz      loc_180015A99
0x18001594f  mov     edx, 5Ch ; '\'; wMatch
0x180015954  mov     rcx, rdi; pszStart
0x180015957  call    cs:__imp_StrChrW
0x18001595d  test    rax, rax
0x180015960  jnz     loc_180015A99
0x180015966  lea     rdx, pszMore; "::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd"...
0x18001596d  mov     rcx, rdi; pszStr1
0x180015970  call    cs:__imp_StrCmpICW
0x180015976  test    eax, eax
0x180015978  jnz     loc_180015A99
0x18001597e  xor     ebx, ebx
0x180015980  lea     rdx, [rsp+4B0h+ppv]; ppv
0x180015985  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001598c  mov     [rsp+4B0h+ppv], rbx
0x180015991  call    cs:__imp_PSCreateMemoryPropertyStore
0x180015997  lea     edi, [rbx+1]
0x18001599a  test    eax, eax
0x18001599c  js      short loc_1800159E8
0x18001599e  lea     rax, [rsp+4B0h+var_480]
0x1800159a3  mov     [rsp+4B0h+var_480], ebx
0x1800159a7  lea     r9, [rsp+4B0h+var_460]; unsigned __int16 *
0x1800159ac  mov     [rsp+4B0h+var_490], rax; int *
0x1800159b1  call    ?_GetIconInfo@CARPFolder@@AEAAJPEBGIPEAGPEAH@Z; CARPFolder::_GetIconInfo(ushort const *,uint,ushort *,int *)
0x1800159b6  test    eax, eax
0x1800159b8  js      short loc_1800159E8
0x1800159ba  mov     rcx, [rsp+4B0h+ppv]
0x1800159bf  lea     r8, [rsp+4B0h+var_460]
0x1800159c4  lea     rdx, PKEY_IconPath
0x1800159cb  call    IPropertyStore_SetString
0x1800159d0  test    eax, eax
0x1800159d2  js      short loc_1800159E8
0x1800159d4  mov     r8d, [rsp+4B0h+var_480]
0x1800159d9  mov     rcx, [rsp+4B0h+ppv]
0x1800159de  call    IPropertyStore_SetInt
0x1800159e3  test    eax, eax
0x1800159e5  cmovns  ebx, edi
0x1800159e8  xor     edx, edx; Val
0x1800159ea  lea     rcx, [rsp+4B0h+var_460]; void *
0x1800159ef  mov     r8d, 424h; Size
0x1800159f5  call    memset_0
0x1800159fa  mov     [rsp+4B0h+var_45C], 3
0x180015a02  test    ebx, ebx
0x180015a04  jz      short loc_180015A28
0x180015a06  mov     rbx, [rsp+4B0h+ppv]
0x180015a0b  mov     [rsp+4B0h+var_470], rbx
0x180015a10  test    rbx, rbx
0x180015a13  jz      short loc_180015A24
0x180015a15  mov     rax, [rbx]
0x180015a18  mov     rcx, rbx
0x180015a1b  mov     rax, [rax+8]
0x180015a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a24  xor     esi, esi
0x180015a26  jmp     short loc_180015A38
0x180015a28  xor     ebx, ebx
0x180015a2a  mov     qword ptr [rsp+4B0h+var_480], 0
0x180015a33  xor     edi, edi
0x180015a35  lea     esi, [rbx+2]
0x180015a38  mov     r9, [r15+68h]
0x180015a3c  lea     rcx, [rsp+4B0h+var_460]
0x180015a41  mov     r8, r14
0x180015a44  mov     rdx, rbx
0x180015a47  call    ?s_CreateItemID@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAJPEFBUtagARPITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(tagARPITEM const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x180015a4c  mov     ebx, eax
0x180015a4e  test    esi, esi
0x180015a50  jz      short loc_180015A5C
0x180015a52  lea     rcx, [rsp+4B0h+var_480]
0x180015a57  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015a5c  test    edi, edi
0x180015a5e  jz      short loc_180015A6A
0x180015a60  lea     rcx, [rsp+4B0h+var_470]
0x180015a65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015a6a  test    ebx, ebx
0x180015a6c  js      short loc_180015A8F
0x180015a6e  test    r12, r12
0x180015a71  jz      short loc_180015A8F
0x180015a73  mov     rax, [r15]
0x180015a76  mov     r9, r12
0x180015a79  mov     r8, r14
0x180015a7c  mov     edx, 1
0x180015a81  mov     rcx, r15
0x180015a84  mov     rax, [rax+48h]
0x180015a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a8d  mov     ebx, eax
0x180015a8f  lea     rcx, [rsp+4B0h+ppv]
0x180015a94  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015a99  mov     eax, ebx
0x180015a9b  mov     rcx, [rbp+3B0h+var_30]
0x180015aa2  xor     rcx, rsp; StackCookie
0x180015aa5  call    __security_check_cookie
0x180015aaa  lea     r11, [rsp+4B0h+var_20]
0x180015ab2  mov     rbx, [r11+38h]
0x180015ab6  mov     rsi, [r11+40h]
0x180015aba  mov     rsp, r11
0x180015abd  pop     r15
0x180015abf  pop     r14
0x180015ac1  pop     r12
0x180015ac3  pop     rdi
0x180015ac4  pop     rbp
0x180015ac5  retn
```
