# CNetworkExplorerFolder::_OpenHKeyForItemIcon(_ITEMID_CHILD const *,HKEY__ * *)

- ea: `0x180001b54`
- end: `0x180001c77`
- name: `?_OpenHKeyForItemIcon@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUHKEY__@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003950`

## callees

- `0x180001b54`
- `0x180002720`
- `0x180002d2c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001c5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180001c5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c14`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180001bc4`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180001bc4`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_OpenHKeyForItemIcon(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        HKEY *a3)
{
  HRESULT PropertyFromIDList; // ebx
  __int64 v5; // rbx
  HKEY v6; // rax
  PROPVARIANT pvar; // [rsp+20h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF
  void *ppv; // [rsp+60h] [rbp+20h] BYREF

  hKey = (HKEY)this;
  *a3 = 0;
  memset(&pvar, 0, sizeof(pvar));
  PropertyFromIDList = CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(
                         a2,
                         &PKEY_PNPX_CompatibleTypes,
                         &pvar);
  if ( PropertyFromIDList < 0 )
    return (unsigned int)PropertyFromIDList;
  if ( pvar.vt != 4127 )
  {
    PropertyFromIDList = -2147024809;
    goto LABEL_17;
  }
  ppv = 0;
  PropertyFromIDList = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, &ppv);
  if ( PropertyFromIDList < 0 )
    goto LABEL_17;
  v5 = 0;
  hKey = 0;
  if ( !pvar.lVal )
    goto LABEL_14;
  while ( 1 )
  {
    if ( (int)CNetworkExplorerFolder::s_OpenRegistry(*(const unsigned __int16 **)&pvar.bstrblobVal.pData[8 * v5], &hKey) < 0 )
    {
      v6 = hKey;
      goto LABEL_9;
    }
    if ( !(*(unsigned int (__fastcall **)(void *, HKEY))(*(_QWORD *)ppv + 32LL))(ppv, hKey) )
      break;
    RegCloseKey(hKey);
    v6 = 0;
    hKey = 0;
LABEL_9:
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= pvar.lVal )
      goto LABEL_12;
  }
  v6 = hKey;
LABEL_12:
  if ( v6 )
  {
    PropertyFromIDList = 0;
    *a3 = v6;
    goto LABEL_15;
  }
LABEL_14:
  PropertyFromIDList = -2147467259;
LABEL_15:
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_17:
  PropVariantClear(&pvar);
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x180001b54  mov     [rsp-8+arg_8], rbx
0x180001b59  mov     [rsp-8+arg_18], rdi
0x180001b5e  mov     [rsp-8+hKey], rcx
0x180001b63  push    rbp
0x180001b64  mov     rbp, rsp
0x180001b67  sub     rsp, 40h
0x180001b6b  xor     ecx, ecx
0x180001b6d  mov     qword ptr [r8], 0
0x180001b74  mov     rax, rdx
0x180001b77  mov     qword ptr [rbp+pvar+10h], rcx
0x180001b7b  mov     rdi, r8
0x180001b7e  lea     rdx, PKEY_PNPX_CompatibleTypes
0x180001b85  xorps   xmm0, xmm0
0x180001b88  lea     r8, [rbp+pvar]
0x180001b8c  mov     rcx, rax
0x180001b8f  movups  xmmword ptr [rbp+pvar], xmm0
0x180001b93  call    ?GetPropertyFromIDList@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180001b98  mov     ebx, eax
0x180001b9a  test    eax, eax
0x180001b9c  js      loc_180001C65
0x180001ba2  mov     eax, 101Fh
0x180001ba7  cmp     ax, word ptr [rbp+pvar]
0x180001bab  jnz     loc_180001C56
0x180001bb1  lea     rdx, [rbp+ppv]; ppv
0x180001bb5  mov     [rbp+ppv], 0
0x180001bbd  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x180001bc4  call    cs:__imp_SHCreateDefaultExtractIcon
0x180001bca  mov     ebx, eax
0x180001bcc  test    eax, eax
0x180001bce  js      loc_180001C5B
0x180001bd4  xor     ebx, ebx
0x180001bd6  mov     [rbp+hKey], 0
0x180001bde  cmp     dword ptr [rbp+pvar+8], ebx
0x180001be1  jbe     short loc_180001C3F
0x180001be3  mov     rcx, qword ptr [rbp+pvar+10h]
0x180001be7  lea     rdx, [rbp+hKey]; HKEY *
0x180001beb  mov     rcx, [rcx+rbx*8]; unsigned __int16 *
0x180001bef  call    ?s_OpenRegistry@CNetworkExplorerFolder@@CAJPEBGPEAPEAUHKEY__@@@Z; CNetworkExplorerFolder::s_OpenRegistry(ushort const *,HKEY__ * *)
0x180001bf4  test    eax, eax
0x180001bf6  js      short loc_180001C22
0x180001bf8  mov     rcx, [rbp+ppv]
0x180001bfc  mov     rdx, [rbp+hKey]
0x180001c00  mov     rax, [rcx]
0x180001c03  mov     rax, [rax+20h]
0x180001c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c0c  test    eax, eax
0x180001c0e  jz      short loc_180001C2F
0x180001c10  mov     rcx, [rbp+hKey]; hKey
0x180001c14  call    cs:__imp_RegCloseKey
0x180001c1a  xor     eax, eax
0x180001c1c  mov     [rbp+hKey], rax
0x180001c20  jmp     short loc_180001C26
0x180001c22  mov     rax, [rbp+hKey]
0x180001c26  inc     ebx
0x180001c28  cmp     ebx, dword ptr [rbp+pvar+8]
0x180001c2b  jb      short loc_180001BE3
0x180001c2d  jmp     short loc_180001C33
0x180001c2f  mov     rax, [rbp+hKey]
0x180001c33  test    rax, rax
0x180001c36  jz      short loc_180001C3F
0x180001c38  xor     ebx, ebx
0x180001c3a  mov     [rdi], rax
0x180001c3d  jmp     short loc_180001C44
0x180001c3f  mov     ebx, 80004005h
0x180001c44  mov     rcx, [rbp+ppv]
0x180001c48  mov     rax, [rcx]
0x180001c4b  mov     rax, [rax+10h]
0x180001c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c54  jmp     short loc_180001C5B
0x180001c56  mov     ebx, 80070057h
0x180001c5b  lea     rcx, [rbp+pvar]; pvar
0x180001c5f  call    cs:__imp_PropVariantClear
0x180001c65  mov     rdi, [rsp+40h+arg_18]
0x180001c6a  mov     eax, ebx
0x180001c6c  mov     rbx, [rsp+40h+arg_8]
0x180001c71  add     rsp, 40h
0x180001c75  pop     rbp
0x180001c76  retn
```
