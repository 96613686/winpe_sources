# CNetworkExplorerFolder::_AssocCreate(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180002b48`
- end: `0x180002d23`
- name: `?_AssocCreate@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `475`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003950`

## callees

- `0x1800026f0`
- `0x180002720`
- `0x180002a90`
- `0x180002b48`
- `0x180002d2c`
- `0x180004010`
- `0x18000f076`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002d02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cda`
- `SHELL32!AssocCreateForClasses` at `0x180002bb2`
- `SHELL32!AssocCreateForClasses` at `0x180002cc2`
- `SHELL32!AssocCreateForClasses` at `0x180002bb2`
- `SHELL32!AssocCreateForClasses` at `0x180002cc2`

## string_xrefs

- `0x180002c8f`: `Common`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_AssocCreate(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT PropertyFromIDList; // ebx
  unsigned __int64 v8; // r14
  ASSOCIATIONELEMENT *v9; // rax
  ASSOCIATIONELEMENT *v10; // rsi
  __int64 v11; // rdi
  __int64 i; // rbx
  HKEY v13; // rax
  __int64 v14; // rcx
  HKEY v15; // rax
  __int64 v16; // rcx
  __int64 j; // r14
  ASSOCIATIONELEMENT rgClasses; // [rsp+20h] [rbp-30h] BYREF
  int v20; // [rsp+38h] [rbp-18h]
  __int128 v21; // [rsp+40h] [rbp-10h]
  HKEY v22; // [rsp+80h] [rbp+30h] BYREF

  v22 = (HKEY)this;
  *a4 = 0;
  if ( (unsigned int)CNetworkExplorerFolder::_IsComputer(this, a2) )
  {
    rgClasses.hkClass = 0;
    rgClasses.ac = ASSOCCLASS_PROGID_STR;
    rgClasses.pszClass = L"NetServer";
    v20 = 8;
    v21 = 0;
    return (unsigned int)AssocCreateForClasses(&rgClasses, 2u, a3, a4);
  }
  else
  {
    memset(&rgClasses, 0, sizeof(rgClasses));
    PropertyFromIDList = CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(
                           a2,
                           &PKEY_PNPX_CompatibleTypes,
                           &rgClasses);
    if ( PropertyFromIDList >= 0 )
    {
      if ( LOWORD(rgClasses.ac) == 4127 )
      {
        v8 = (unsigned int)(LODWORD(rgClasses.hkClass) + 1);
        v9 = (ASSOCIATIONELEMENT *)operator new(saturated_mul(v8, 0x18u));
        v10 = v9;
        if ( v9 )
        {
          memset_0(v9, 0, 24 * v8);
          v11 = 0;
          for ( i = 0; (unsigned int)i < LODWORD(rgClasses.hkClass); i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= (unsigned int)v8 )
              break;
            v22 = 0;
            if ( CNetworkExplorerFolder::s_OpenRegistry(*(const unsigned __int16 **)&rgClasses.pszClass[4 * i], &v22) >= 0 )
            {
              v13 = v22;
              v14 = v11;
              v10[v14].ac = ASSOCCLASS_APP_KEY;
              v11 = (unsigned int)(v11 + 1);
              v10[v14].hkClass = v13;
            }
          }
          PropertyFromIDList = 0;
          if ( (unsigned int)v11 < (unsigned int)v8 )
          {
            v22 = 0;
            PropertyFromIDList = CNetworkExplorerFolder::s_OpenRegistry(L"Common", &v22);
            if ( PropertyFromIDList >= 0 )
            {
              v15 = v22;
              v16 = v11;
              LODWORD(v11) = v11 + 1;
              v10[v16].ac = ASSOCCLASS_APP_KEY;
              v10[v16].hkClass = v15;
              PropertyFromIDList = AssocCreateForClasses(v10, v11, a3, a4);
            }
            for ( j = 0; (unsigned int)j < (unsigned int)v11; j = (unsigned int)(j + 1) )
              RegCloseKey(v10[j].hkClass);
          }
          operator delete(v10);
        }
        else
        {
          PropertyFromIDList = -2147024882;
        }
      }
      else
      {
        PropertyFromIDList = -2147024809;
      }
      PropVariantClear((PROPVARIANT *)&rgClasses);
    }
  }
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x180002b48  mov     [rsp-28h+arg_8], rbx
0x180002b4d  mov     [rsp-28h+arg_10], rsi
0x180002b52  mov     [rsp-28h+arg_0], rcx
0x180002b57  push    rbp
0x180002b58  push    rdi
0x180002b59  push    r12
0x180002b5b  push    r14
0x180002b5d  push    r15
0x180002b5f  mov     rbp, rsp
0x180002b62  sub     rsp, 50h
0x180002b66  mov     r15, r9
0x180002b69  mov     qword ptr [r9], 0
0x180002b70  mov     r12, r8
0x180002b73  mov     rbx, rdx
0x180002b76  call    ?_IsComputer@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CNetworkExplorerFolder::_IsComputer(_ITEMIDLIST_RELATIVE const *)
0x180002b7b  xorps   xmm0, xmm0
0x180002b7e  test    eax, eax
0x180002b80  jz      short loc_180002BBF
0x180002b82  mov     edx, 2; cClasses
0x180002b87  mov     [rbp+rgClasses.hkClass], 0
0x180002b8f  lea     rax, aNetserver; "NetServer"
0x180002b96  mov     [rbp+rgClasses.ac], edx
0x180002b99  mov     r9, r15; ppv
0x180002b9c  mov     [rbp+rgClasses.pszClass], rax
0x180002ba0  mov     r8, r12; riid
0x180002ba3  mov     [rbp+var_18], 8
0x180002baa  lea     rcx, [rbp+rgClasses]; rgClasses
0x180002bae  movups  [rbp+var_10], xmm0
0x180002bb2  call    cs:__imp_AssocCreateForClasses
0x180002bb8  mov     ebx, eax
0x180002bba  jmp     loc_180002D08
0x180002bbf  xor     eax, eax
0x180002bc1  lea     r8, [rbp+rgClasses]
0x180002bc5  lea     rdx, PKEY_PNPX_CompatibleTypes
0x180002bcc  mov     [rbp+rgClasses.pszClass], rax
0x180002bd0  mov     rcx, rbx
0x180002bd3  movups  xmmword ptr [rbp+rgClasses.ac], xmm0
0x180002bd7  call    ?GetPropertyFromIDList@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180002bdc  mov     ebx, eax
0x180002bde  test    eax, eax
0x180002be0  js      loc_180002D08
0x180002be6  mov     eax, 101Fh
0x180002beb  cmp     ax, word ptr [rbp+rgClasses.ac]
0x180002bef  jnz     loc_180002CF9
0x180002bf5  mov     r14d, dword ptr [rbp+rgClasses.hkClass]
0x180002bf9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002c00  inc     r14d
0x180002c03  mov     eax, 18h
0x180002c08  mov     ebx, r14d
0x180002c0b  mul     rbx
0x180002c0e  cmovb   rax, rcx
0x180002c12  mov     rcx, rax; unsigned __int64
0x180002c15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c1a  mov     rsi, rax
0x180002c1d  test    rax, rax
0x180002c20  jz      loc_180002CF2
0x180002c26  lea     r8, [r14+r14*2]
0x180002c2a  xor     edx, edx; Val
0x180002c2c  shl     r8, 3; Size
0x180002c30  mov     rcx, rax; void *
0x180002c33  call    memset_0
0x180002c38  xor     edi, edi
0x180002c3a  xor     ebx, ebx
0x180002c3c  cmp     dword ptr [rbp+rgClasses.hkClass], ebx
0x180002c3f  jbe     short loc_180002C80
0x180002c41  cmp     ebx, r14d
0x180002c44  jnb     short loc_180002C80
0x180002c46  mov     rcx, [rbp+rgClasses.pszClass]
0x180002c4a  lea     rdx, [rbp+arg_0]; HKEY *
0x180002c4e  mov     [rbp+arg_0], 0
0x180002c56  mov     rcx, [rcx+rbx*8]; unsigned __int16 *
0x180002c5a  call    ?s_OpenRegistry@CNetworkExplorerFolder@@CAJPEBGPEAPEAUHKEY__@@@Z; CNetworkExplorerFolder::s_OpenRegistry(ushort const *,HKEY__ * *)
0x180002c5f  test    eax, eax
0x180002c61  js      short loc_180002C79
0x180002c63  mov     rax, [rbp+arg_0]
0x180002c67  lea     rcx, [rdi+rdi*2]
0x180002c6b  mov     dword ptr [rsi+rcx*8], 5
0x180002c72  inc     edi
0x180002c74  mov     [rsi+rcx*8+8], rax
0x180002c79  inc     ebx
0x180002c7b  cmp     ebx, dword ptr [rbp+rgClasses.hkClass]
0x180002c7e  jb      short loc_180002C41
0x180002c80  xor     ebx, ebx
0x180002c82  cmp     edi, r14d
0x180002c85  jnb     short loc_180002CE8
0x180002c87  lea     rdx, [rbp+arg_0]; HKEY *
0x180002c8b  mov     [rbp+arg_0], rbx
0x180002c8f  lea     rcx, aCommon; "Common"
0x180002c96  call    ?s_OpenRegistry@CNetworkExplorerFolder@@CAJPEBGPEAPEAUHKEY__@@@Z; CNetworkExplorerFolder::s_OpenRegistry(ushort const *,HKEY__ * *)
0x180002c9b  mov     ebx, eax
0x180002c9d  test    eax, eax
0x180002c9f  js      short loc_180002CCA
0x180002ca1  mov     rax, [rbp+arg_0]
0x180002ca5  lea     rcx, [rdi+rdi*2]
0x180002ca9  inc     edi
0x180002cab  mov     dword ptr [rsi+rcx*8], 5
0x180002cb2  mov     [rsi+rcx*8+8], rax
0x180002cb7  mov     edx, edi; cClasses
0x180002cb9  mov     rcx, rsi; rgClasses
0x180002cbc  mov     r9, r15; ppv
0x180002cbf  mov     r8, r12; riid
0x180002cc2  call    cs:__imp_AssocCreateForClasses
0x180002cc8  mov     ebx, eax
0x180002cca  xor     r14d, r14d
0x180002ccd  test    edi, edi
0x180002ccf  jz      short loc_180002CE8
0x180002cd1  lea     rcx, [r14+r14*2]
0x180002cd5  mov     rcx, [rsi+rcx*8+8]; hKey
0x180002cda  call    cs:__imp_RegCloseKey
0x180002ce0  inc     r14d
0x180002ce3  cmp     r14d, edi
0x180002ce6  jb      short loc_180002CD1
0x180002ce8  mov     rcx, rsi; lpMem
0x180002ceb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002cf0  jmp     short loc_180002CFE
0x180002cf2  mov     ebx, 8007000Eh
0x180002cf7  jmp     short loc_180002CFE
0x180002cf9  mov     ebx, 80070057h
0x180002cfe  lea     rcx, [rbp+rgClasses]; pvar
0x180002d02  call    cs:__imp_PropVariantClear
0x180002d08  lea     r11, [rsp+50h+var_s0]
0x180002d0d  mov     eax, ebx
0x180002d0f  mov     rbx, [r11+38h]
0x180002d13  mov     rsi, [r11+40h]
0x180002d17  mov     rsp, r11
0x180002d1a  pop     r15
0x180002d1c  pop     r14
0x180002d1e  pop     r12
0x180002d20  pop     rdi
0x180002d21  pop     rbp
0x180002d22  retn
```
