# CCachedFolderItem::_UpdateProgressValues(void)

- ea: `0x18004e9f8`
- end: `0x18004ec7e`
- name: `?_UpdateProgressValues@CCachedFolderItem@@AEAAJXZ`
- size: `646`
- prototype: `__int64 __fastcall(CCachedFolderItem *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18004dcc0`
- `0x18004e420`
- `0x18004e500`
- `0x18004e954`

## callees

- `0x180009940`
- `0x18000a5e4`
- `0x18004e5a0`
- `0x18004e7a4`
- `0x18004e9f8`
- `0x180052912`
- `0x18005292a`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ea62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ec4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ea62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ec4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ea48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ebaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ea48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ebaa`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004eb40`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004ebf3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004eb40`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004ebf3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004eb4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ebe7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ebfc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004eb4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ebe7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004ebfc`
- `PROPSYS!InitPropVariantFromUInt32Vector` at `0x18004eb0d`
- `PROPSYS!InitPropVariantFromUInt32Vector` at `0x18004eb0d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ebb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ebcb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ebb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ebcb`

## pseudocode

```c
__int64 __fastcall CCachedFolderItem::_UpdateProgressValues(CCachedFolderItem *this)
{
  ULONG v2; // eax
  char v3; // cl
  int v4; // eax
  int v5; // eax
  CCachedFolderItem *v6; // rcx
  HRESULT inited; // r14d
  PROPVARIANT *v8; // rsi
  unsigned __int16 *v9; // rbx
  __int64 v10; // r15
  CCachedFolderItem *v11; // rcx
  OLECHAR *v12; // rcx
  bool v13; // cc
  bool v14; // zf
  unsigned __int16 *v16; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h]
  _BYTE v19[796]; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v20; // [rsp+35Ch] [rbp+25Ch] BYREF
  int v21; // [rsp+364h] [rbp+264h]
  int v22; // [rsp+368h] [rbp+268h]
  int v23; // [rsp+37Ch] [rbp+27Ch]
  ULONG v24; // [rsp+380h] [rbp+280h]
  ULONG v25; // [rsp+384h] [rbp+284h]
  ULONG prgn[2]; // [rsp+590h] [rbp+490h] BYREF
  int v27; // [rsp+598h] [rbp+498h]

  memset_0(v19, 0, 0x550u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  memcpy_0(v19, (char *)this + 64, 0x550u);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = v25;
  if ( !v25 )
    v2 = 100;
  if ( v21 )
  {
    v3 = 4;
  }
  else
  {
    v3 = 0;
    if ( v22 )
      v3 = 8;
  }
  if ( v23 == 11 )
  {
    v3 |= 1u;
    v2 = 0;
  }
  v18 = 0;
  prgn[1] = v24;
  *(_OWORD *)ppropvar = 0;
  if ( (v3 & 1) != 0 )
  {
    prgn[0] = 0;
    v4 = 1;
  }
  else
  {
    prgn[0] = v2;
    v4 = 0;
  }
  v27 = v4;
  if ( (v3 & 4) != 0 )
  {
    v5 = v4 | 4;
  }
  else
  {
    if ( (v3 & 8) == 0 )
      goto LABEL_17;
    v5 = v4 | 8;
  }
  v27 = v5;
LABEL_17:
  inited = InitPropVariantFromUInt32Vector(prgn, 3u, ppropvar);
  if ( inited >= 0 )
  {
    v8 = (PROPVARIANT *)operator new(0x18u);
    if ( v8 )
    {
      *(_OWORD *)v8 = 0;
      v8[2] = 0;
      inited = PropVariantCopy(v8, ppropvar);
      PropVariantClear(ppropvar);
      goto LABEL_22;
    }
    inited = -2147024882;
  }
  v8 = 0;
LABEL_22:
  v9 = 0;
  v10 = 0;
  v16 = 0;
  *(_QWORD *)prgn = 0;
  if ( inited >= 0 )
  {
    CCachedFolderItem::_FormatSyncState(v6, (const struct SYNCMGR_FOLDERITEMINFO *)v19, &v16, &v20);
    CCachedFolderItem::_GenerateSyncResultString(
      v11,
      (const struct SYNCMGR_FOLDERITEMINFO *)v19,
      (unsigned __int16 **)prgn);
    v9 = v16;
    v10 = *(_QWORD *)prgn;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  SysFreeString(*((BSTR *)this + 178));
  v12 = (OLECHAR *)*((_QWORD *)this + 179);
  *((_QWORD *)this + 178) = v9;
  SysFreeString(v12);
  *((_QWORD *)this + 179) = v10;
  if ( v8 )
  {
    PropVariantClear((PROPVARIANT *)this + 180);
    PropVariantCopy((PROPVARIANT *)this + 180, v8);
    PropVariantClear(v8);
    CZeroInitNew::operator delete(v8);
  }
  v13 = *((_DWORD *)this + 223) <= 2;
  *((_DWORD *)this + 366) = 1;
  if ( v13 )
    *((_DWORD *)this + 366) = 0;
  v14 = (*((_DWORD *)this + 214) & 0x200000) == 0;
  *((_DWORD *)this + 368) = *((unsigned __int8 *)this + 888);
  if ( !v14 )
    *((_DWORD *)this + 367) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18004e9f8  mov     [rsp-8+arg_8], rbx
0x18004e9fd  mov     [rsp-8+arg_10], rsi
0x18004ea02  push    rbp
0x18004ea03  push    rdi
0x18004ea04  push    r12
0x18004ea06  push    r14
0x18004ea08  push    r15
0x18004ea0a  lea     rbp, [rsp-4B0h]
0x18004ea12  sub     rsp, 5B0h
0x18004ea19  mov     rax, cs:__security_cookie
0x18004ea20  xor     rax, rsp
0x18004ea23  mov     [rbp+4D0h+var_30], rax
0x18004ea2a  mov     rdi, rcx
0x18004ea2d  mov     ebx, 550h
0x18004ea32  mov     r8d, ebx; Size
0x18004ea35  lea     rcx, [rsp+5D0h+var_590]; void *
0x18004ea3a  xor     edx, edx; Val
0x18004ea3c  call    memset_0
0x18004ea41  lea     r12, [rdi+18h]
0x18004ea45  mov     rcx, r12; lpCriticalSection
0x18004ea48  call    cs:__imp_EnterCriticalSection
0x18004ea4e  lea     rcx, [rsp+5D0h+var_590]; void *
0x18004ea53  mov     r8d, ebx; Size
0x18004ea56  lea     rdx, [rdi+40h]; Src
0x18004ea5a  call    memcpy_0
0x18004ea5f  mov     rcx, r12; lpCriticalSection
0x18004ea62  call    cs:__imp_LeaveCriticalSection
0x18004ea68  mov     eax, [rbp+4D0h+var_24C]
0x18004ea6e  mov     ecx, 64h ; 'd'
0x18004ea73  test    eax, eax
0x18004ea75  cmovz   eax, ecx
0x18004ea78  cmp     [rbp+4D0h+var_26C], 0
0x18004ea7f  lea     r8d, [rcx-5Ch]
0x18004ea83  jz      short loc_18004EA8B
0x18004ea85  lea     ecx, [r8-4]
0x18004ea89  jmp     short loc_18004EA97
0x18004ea8b  xor     ecx, ecx
0x18004ea8d  cmp     [rbp+4D0h+var_268], ecx
0x18004ea93  cmovnz  ecx, r8d
0x18004ea97  cmp     [rbp+4D0h+var_254], 0Bh
0x18004ea9e  jnz     short loc_18004EAA5
0x18004eaa0  or      ecx, 1
0x18004eaa3  xor     eax, eax
0x18004eaa5  xor     edx, edx
0x18004eaa7  xorps   xmm0, xmm0
0x18004eaaa  mov     [rsp+5D0h+var_598], rdx
0x18004eaaf  mov     edx, [rbp+4D0h+var_250]
0x18004eab5  mov     [rbp+4D0h+prgn+4], edx
0x18004eabb  movups  xmmword ptr [rsp+5D0h+ppropvar], xmm0
0x18004eac0  test    cl, 1
0x18004eac3  jz      short loc_18004EAD6
0x18004eac5  mov     [rbp+4D0h+prgn], 0
0x18004eacf  mov     eax, 1
0x18004ead4  jmp     short loc_18004EADE
0x18004ead6  mov     [rbp+4D0h+prgn], eax
0x18004eadc  xor     eax, eax
0x18004eade  mov     [rbp+4D0h+var_38], eax
0x18004eae4  test    cl, 4
0x18004eae7  jz      short loc_18004EAEE
0x18004eae9  or      eax, 4
0x18004eaec  jmp     short loc_18004EAF6
0x18004eaee  test    r8b, cl
0x18004eaf1  jz      short loc_18004EAFC
0x18004eaf3  or      eax, r8d
0x18004eaf6  mov     [rbp+4D0h+var_38], eax
0x18004eafc  lea     r8, [rsp+5D0h+ppropvar]; ppropvar
0x18004eb01  mov     edx, 3; cElems
0x18004eb06  lea     rcx, [rbp+4D0h+prgn]; prgn
0x18004eb0d  call    cs:__imp_InitPropVariantFromUInt32Vector
0x18004eb13  mov     r14d, eax
0x18004eb16  test    eax, eax
0x18004eb18  js      short loc_18004EB5C
0x18004eb1a  mov     ecx, 18h; unsigned __int64
0x18004eb1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004eb24  mov     rsi, rax
0x18004eb27  test    rax, rax
0x18004eb2a  jz      short loc_18004EB56
0x18004eb2c  xorps   xmm1, xmm1
0x18004eb2f  lea     rdx, [rsp+5D0h+ppropvar]; pvarSrc
0x18004eb34  xor     eax, eax
0x18004eb36  mov     rcx, rsi; pvarDest
0x18004eb39  movups  xmmword ptr [rsi], xmm1
0x18004eb3c  mov     [rsi+10h], rax
0x18004eb40  call    cs:__imp_PropVariantCopy
0x18004eb46  lea     rcx, [rsp+5D0h+ppropvar]; pvar
0x18004eb4b  mov     r14d, eax
0x18004eb4e  call    cs:__imp_PropVariantClear
0x18004eb54  jmp     short loc_18004EB5E
0x18004eb56  mov     r14d, 8007000Eh
0x18004eb5c  xor     esi, esi
0x18004eb5e  xor     ebx, ebx
0x18004eb60  xor     r15d, r15d
0x18004eb63  mov     [rsp+5D0h+var_5B0], rbx
0x18004eb68  mov     qword ptr [rbp+4D0h+prgn], r15
0x18004eb6f  test    r14d, r14d
0x18004eb72  js      short loc_18004EBA7
0x18004eb74  lea     r9, [rbp+4D0h+var_274]; struct _FILETIME *
0x18004eb7b  lea     r8, [rsp+5D0h+var_5B0]; unsigned __int16 **
0x18004eb80  lea     rdx, [rsp+5D0h+var_590]; struct SYNCMGR_FOLDERITEMINFO *
0x18004eb85  call    ?_FormatSyncState@CCachedFolderItem@@AEBAJAEBUSYNCMGR_FOLDERITEMINFO@@PEAPEAGPEAU_FILETIME@@@Z; CCachedFolderItem::_FormatSyncState(SYNCMGR_FOLDERITEMINFO const &,ushort * *,_FILETIME *)
0x18004eb8a  lea     r8, [rbp+4D0h+prgn]; unsigned __int16 **
0x18004eb91  lea     rdx, [rsp+5D0h+var_590]; struct SYNCMGR_FOLDERITEMINFO *
0x18004eb96  call    ?_GenerateSyncResultString@CCachedFolderItem@@AEAAJAEBUSYNCMGR_FOLDERITEMINFO@@PEAPEAG@Z; CCachedFolderItem::_GenerateSyncResultString(SYNCMGR_FOLDERITEMINFO const &,ushort * *)
0x18004eb9b  mov     rbx, [rsp+5D0h+var_5B0]
0x18004eba0  mov     r15, qword ptr [rbp+4D0h+prgn]
0x18004eba7  mov     rcx, r12; lpCriticalSection
0x18004ebaa  call    cs:__imp_EnterCriticalSection
0x18004ebb0  mov     rcx, [rdi+590h]; bstrString
0x18004ebb7  call    cs:__imp_SysFreeString
0x18004ebbd  mov     rcx, [rdi+598h]; bstrString
0x18004ebc4  mov     [rdi+590h], rbx
0x18004ebcb  call    cs:__imp_SysFreeString
0x18004ebd1  mov     [rdi+598h], r15
0x18004ebd8  test    rsi, rsi
0x18004ebdb  jz      short loc_18004EC0A
0x18004ebdd  lea     rbx, [rdi+5A0h]
0x18004ebe4  mov     rcx, rbx; pvar
0x18004ebe7  call    cs:__imp_PropVariantClear
0x18004ebed  mov     rdx, rsi; pvarSrc
0x18004ebf0  mov     rcx, rbx; pvarDest
0x18004ebf3  call    cs:__imp_PropVariantCopy
0x18004ebf9  mov     rcx, rsi; pvar
0x18004ebfc  call    cs:__imp_PropVariantClear
0x18004ec02  mov     rcx, rsi; lpMem
0x18004ec05  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18004ec0a  cmp     dword ptr [rdi+37Ch], 2
0x18004ec11  mov     ecx, 1
0x18004ec16  mov     [rdi+5B8h], ecx
0x18004ec1c  jg      short loc_18004EC28
0x18004ec1e  mov     dword ptr [rdi+5B8h], 0
0x18004ec28  test    dword ptr [rdi+358h], 200000h
0x18004ec32  movzx   eax, byte ptr [rdi+378h]
0x18004ec39  mov     [rdi+5C0h], eax
0x18004ec3f  jz      short loc_18004EC47
0x18004ec41  mov     [rdi+5BCh], ecx
0x18004ec47  mov     rcx, r12; lpCriticalSection
0x18004ec4a  call    cs:__imp_LeaveCriticalSection
0x18004ec50  mov     eax, r14d
0x18004ec53  mov     rcx, [rbp+4D0h+var_30]
0x18004ec5a  xor     rcx, rsp; StackCookie
0x18004ec5d  call    __security_check_cookie
0x18004ec62  lea     r11, [rsp+5D0h+var_20]
0x18004ec6a  mov     rbx, [r11+38h]
0x18004ec6e  mov     rsi, [r11+40h]
0x18004ec72  mov     rsp, r11
0x18004ec75  pop     r15
0x18004ec77  pop     r14
0x18004ec79  pop     r12
0x18004ec7b  pop     rdi
0x18004ec7c  pop     rbp
0x18004ec7d  retn
```
