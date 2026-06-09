# CEnhancedStorageFolder::CreateItemFromData(ushort const *,ushort const *,ulong,int,int,_ITEMIDLIST * *)

- ea: `0x180002c60`
- end: `0x180002e6d`
- name: `?CreateItemFromData@CEnhancedStorageFolder@@QEAAJPEBG0KHHPEAPEFAU_ITEMIDLIST@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(CEnhancedStorageFolder *this, const unsigned __int16 *, const unsigned __int16 *, __int64, int, int, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002610`

## callees

- `0x180002c60`
- `0x1800064cc`
- `0x18000684c`
- `0x1800097f8`
- `0x18000c010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180002ce6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180002ce6`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::CreateItemFromData(
        CEnhancedStorageFolder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        int a6,
        struct _ITEMIDLIST **a7)
{
  HRESULT v10; // eax
  int ItemID; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v15; // r9
  void *ppv; // [rsp+20h] [rbp-68h] BYREF
  _DWORD v17[4]; // [rsp+28h] [rbp-60h] BYREF
  __int128 v18; // [rsp+38h] [rbp-50h] BYREF
  __int64 v19; // [rsp+48h] [rbp-40h]

  v17[0] = 4;
  v17[1] = a5;
  v17[2] = a6;
  ppv = 0;
  v18 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, a4);
  v10 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  ItemID = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_10;
    v13 = 34;
    goto LABEL_8;
  }
  LOWORD(v18) = 31;
  *((_QWORD *)&v18 + 1) = a2;
  v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
          ppv,
          &PKEY_ParsingName,
          &v18);
  ItemID = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_10;
    v13 = 35;
    goto LABEL_8;
  }
  LOWORD(v18) = 31;
  *((_QWORD *)&v18 + 1) = a3;
  v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
          ppv,
          &PKEY_ItemNameDisplay,
          &v18);
  ItemID = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_10;
    v13 = 36;
LABEL_8:
    WPP_SF_d(v12[2], v13, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, (unsigned int)v10);
LABEL_9:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_d(v12[2], 38, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, (unsigned int)ItemID);
    goto LABEL_13;
  }
  ItemID = CItemIDFactory<_ITEMID,1450709556>::s_CreateItemID(v17, ppv, a7, *((_QWORD *)this + 1));
  if ( ItemID < 0 )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6cd5398725ca392462ef447cc6ada768_Traceguids, v15);
LABEL_13:
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)ItemID;
}

```

## disassembly

```asm
0x180002c60  push    rbx
0x180002c62  push    rbp
0x180002c63  push    rsi
0x180002c64  push    rdi
0x180002c65  push    r14
0x180002c67  push    r15
0x180002c69  sub     rsp, 58h
0x180002c6d  mov     rbp, r8
0x180002c70  mov     rsi, rdx
0x180002c73  mov     rdi, rcx
0x180002c76  mov     [rsp+88h+var_60], 4
0x180002c7e  mov     eax, [rsp+88h+arg_20]
0x180002c85  mov     [rsp+88h+var_5C], eax
0x180002c89  mov     eax, [rsp+88h+arg_28]
0x180002c90  mov     [rsp+88h+var_58], eax
0x180002c94  mov     [rsp+88h+ppv], 0
0x180002c9d  xorps   xmm0, xmm0
0x180002ca0  xor     eax, eax
0x180002ca2  movups  [rsp+88h+var_50], xmm0
0x180002ca7  mov     [rsp+88h+var_40], rax
0x180002cac  lea     r14, WPP_GLOBAL_Control
0x180002cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cba  cmp     rcx, r14
0x180002cbd  jz      short loc_180002CDA
0x180002cbf  test    byte ptr [rcx+1Ch], 20h
0x180002cc3  jz      short loc_180002CDA
0x180002cc5  mov     edx, 21h ; '!'
0x180002cca  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002cd1  mov     rcx, [rcx+10h]
0x180002cd5  call    WPP_SF_
0x180002cda  lea     rdx, [rsp+88h+ppv]; ppv
0x180002cdf  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180002ce6  call    cs:__imp_PSCreateMemoryPropertyStore
0x180002cec  mov     ebx, eax
0x180002cee  test    eax, eax
0x180002cf0  jns     short loc_180002D6D
0x180002cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cf9  cmp     rcx, r14
0x180002cfc  jz      short loc_180002D47
0x180002cfe  test    byte ptr [rcx+1Ch], 2
0x180002d02  jz      short loc_180002D23
0x180002d04  mov     edx, 22h ; '"'
0x180002d09  mov     r9d, eax
0x180002d0c  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002d13  mov     rcx, [rcx+10h]
0x180002d17  call    WPP_SF_d
0x180002d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d23  cmp     rcx, r14
0x180002d26  jz      short loc_180002D47
0x180002d28  test    byte ptr [rcx+1Ch], 2
0x180002d2c  jz      short loc_180002D47
0x180002d2e  mov     edx, 26h ; '&'
0x180002d33  mov     r9d, ebx
0x180002d36  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002d3d  mov     rcx, [rcx+10h]
0x180002d41  call    WPP_SF_d
0x180002d46  nop
0x180002d47  mov     rcx, [rsp+88h+ppv]
0x180002d4c  test    rcx, rcx
0x180002d4f  jz      short loc_180002D5E
0x180002d51  mov     rax, [rcx]
0x180002d54  mov     rax, [rax+10h]
0x180002d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d5d  nop
0x180002d5e  mov     eax, ebx
0x180002d60  add     rsp, 58h
0x180002d64  pop     r15
0x180002d66  pop     r14
0x180002d68  pop     rdi
0x180002d69  pop     rsi
0x180002d6a  pop     rbp
0x180002d6b  pop     rbx
0x180002d6c  retn
0x180002d6d  mov     r15d, 1Fh
0x180002d73  mov     word ptr [rsp+88h+var_50], r15w
0x180002d79  mov     qword ptr [rsp+88h+var_50+8], rsi
0x180002d7e  mov     rcx, [rsp+88h+ppv]
0x180002d83  mov     rax, [rcx]
0x180002d86  lea     r8, [rsp+88h+var_50]
0x180002d8b  lea     rdx, PKEY_ParsingName
0x180002d92  mov     rax, [rax+30h]
0x180002d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9b  mov     ebx, eax
0x180002d9d  test    eax, eax
0x180002d9f  jns     short loc_180002DC1
0x180002da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002da8  cmp     rcx, r14
0x180002dab  jz      short loc_180002D47
0x180002dad  test    byte ptr [rcx+1Ch], 2
0x180002db1  jz      loc_180002D23
0x180002db7  mov     edx, 23h ; '#'
0x180002dbc  jmp     loc_180002D09
0x180002dc1  mov     word ptr [rsp+88h+var_50], r15w
0x180002dc7  mov     qword ptr [rsp+88h+var_50+8], rbp
0x180002dcc  mov     rcx, [rsp+88h+ppv]
0x180002dd1  mov     rax, [rcx]
0x180002dd4  lea     r8, [rsp+88h+var_50]
0x180002dd9  lea     rdx, PKEY_ItemNameDisplay
0x180002de0  mov     rax, [rax+30h]
0x180002de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de9  mov     ebx, eax
0x180002deb  test    eax, eax
0x180002ded  jns     short loc_180002E13
0x180002def  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df6  cmp     rcx, r14
0x180002df9  jz      loc_180002D47
0x180002dff  test    byte ptr [rcx+1Ch], 2
0x180002e03  jz      loc_180002D23
0x180002e09  mov     edx, 24h ; '$'
0x180002e0e  jmp     loc_180002D09
0x180002e13  mov     r9, [rdi+8]
0x180002e17  mov     r8, [rsp+88h+arg_30]
0x180002e1f  mov     rdx, [rsp+88h+ppv]
0x180002e24  lea     rcx, [rsp+88h+var_60]
0x180002e29  call    ?s_CreateItemID@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMID@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z; CItemIDFactory<_ITEMID,1450709556>::s_CreateItemID(_ITEMID const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)
0x180002e2e  mov     ebx, eax
0x180002e30  test    eax, eax
0x180002e32  js      loc_180002D1C
0x180002e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3f  cmp     rcx, r14
0x180002e42  jz      loc_180002D47
0x180002e48  test    byte ptr [rcx+1Ch], 20h
0x180002e4c  jz      loc_180002D47
0x180002e52  mov     edx, 25h ; '%'
0x180002e57  lea     r8, WPP_6cd5398725ca392462ef447cc6ada768_Traceguids
0x180002e5e  mov     rcx, [rcx+10h]
0x180002e62  call    WPP_SF_
0x180002e67  jmp     loc_180002D47
```
