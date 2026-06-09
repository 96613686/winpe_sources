# CBlockListManager::_HandleBlockListElement(ushort const *,uint,IXmlReader *)

- ea: `0x1800faef0`
- end: `0x1800fb150`
- name: `?_HandleBlockListElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `608`
- prototype: `int(CBlockListManager *__hidden this, const unsigned __int16 *, unsigned int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fb7a0`

## callees

- `0x1800faef0`
- `0x1800fc83c`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800faf37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fafae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800faffe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb047`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800faf37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fafae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800faffe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800fb047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fb125`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fb07a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800fb07a`

## pseudocode

```c
__int64 __fastcall CBlockListManager::_HandleBlockListElement(
        CBlockListManager *this,
        const unsigned __int16 *a2,
        int a3,
        struct IXmlReader *a4)
{
  int v6; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT v8; // eax
  bool v9; // zf
  int v10; // r8d
  struct IXmlReaderVtbl *v11; // rax
  LPWSTR *p_pv; // rdx
  struct IXmlReaderVtbl *v13; // rax
  struct IXmlReaderVtbl *v14; // rax
  CBlockListManager *v15; // rcx
  CBlockListManager *v16; // rcx
  CBlockListManager *v17; // rcx
  unsigned __int16 *v19; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR pszStr1; // [rsp+28h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR psz[2]; // [rsp+40h] [rbp-10h] BYREF
  int nChar; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 || !a4 )
    return 2147942487LL;
  if ( a3 != 9 || StrCmpNICW(a2, L"blocklist", 9) )
    return (unsigned int)-2147019873;
  v6 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToFirstAttribute)(a4);
  if ( v6 )
    return (unsigned int)v6;
  pv = 0;
  v19 = 0;
  ppwsz = 0;
  while ( 1 )
  {
    lpVtbl = a4->lpVtbl;
    pszStr1 = 0;
    nChar = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, int *))lpVtbl->GetLocalName)(a4, &pszStr1, &nChar);
    v6 = -2147019873;
    v9 = v8 == 0;
    if ( v8 < 0 )
      goto LABEL_24;
    v10 = nChar;
    if ( nChar == 7 )
    {
      if ( !StrCmpNICW(pszStr1, L"version", 7) )
      {
        v11 = a4->lpVtbl;
        psz[0] = 0;
        v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v11->GetValue)(a4, psz, 0);
        v9 = v8 == 0;
        if ( v8 >= 0 )
        {
          p_pv = (LPWSTR *)&pv;
          goto LABEL_22;
        }
        goto LABEL_24;
      }
      v10 = nChar;
    }
    if ( v10 != 7 )
      goto LABEL_18;
    if ( StrCmpNICW(pszStr1, L"ttlhigh", 7) )
      break;
    v13 = a4->lpVtbl;
    psz[0] = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v13->GetValue)(a4, psz, 0);
    v9 = v8 == 0;
    if ( v8 >= 0 )
    {
      p_pv = &v19;
      goto LABEL_22;
    }
LABEL_24:
    if ( !v9 )
      goto LABEL_27;
  }
  v10 = nChar;
LABEL_18:
  if ( v10 == 6 && !StrCmpNICW(pszStr1, L"ttllow", 6) )
  {
    v14 = a4->lpVtbl;
    psz[0] = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v14->GetValue)(a4, psz, 0);
    v9 = v8 == 0;
    if ( v8 < 0 )
      goto LABEL_24;
    p_pv = &ppwsz;
LABEL_22:
    v8 = SHStrDupW(psz[0], p_pv);
    v9 = v8 == 0;
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToNextAttribute)(a4);
      v9 = v8 == 0;
    }
    goto LABEL_24;
  }
  v8 = -2147019873;
LABEL_27:
  v15 = 0;
  if ( v8 != 1 )
    v15 = (CBlockListManager *)(unsigned int)v8;
  if ( (int)v15 < 0 )
  {
    v6 = (int)v15;
  }
  else if ( pv )
  {
    if ( ppwsz )
    {
      if ( v19 )
      {
        v6 = CBlockListManager::_StringToULong(
               v15,
               (const unsigned __int16 *)pv,
               (unsigned int *)this + 148,
               0xFFFFFFFF);
        if ( v6 >= 0 )
        {
          v6 = CBlockListManager::_StringToULong(v16, ppwsz, (unsigned int *)this + 1, 0xFFFFFFFF);
          if ( v6 >= 0 )
            v6 = CBlockListManager::_StringToULong(v17, v19, (unsigned int *)this + 2, 0xFFFFFFFF);
        }
      }
    }
  }
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v19);
  v19 = 0;
  CoTaskMemFree(ppwsz);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800faef0  mov     [rsp-18h+arg_0], rbx
0x1800faef5  mov     [rsp-18h+arg_10], rsi
0x1800faefa  push    rbp
0x1800faefb  push    rdi
0x1800faefc  push    r14
0x1800faefe  mov     rbp, rsp
0x1800faf01  sub     rsp, 50h
0x1800faf05  xor     r14d, r14d
0x1800faf08  mov     rdi, r9
0x1800faf0b  mov     rax, rdx
0x1800faf0e  mov     rsi, rcx
0x1800faf11  test    rdx, rdx
0x1800faf14  jz      loc_1800FB136
0x1800faf1a  test    r9, r9
0x1800faf1d  jz      loc_1800FB136
0x1800faf23  cmp     r8d, 9
0x1800faf27  jnz     loc_1800FB12D
0x1800faf2d  lea     rdx, aBlocklist; "blocklist"
0x1800faf34  mov     rcx, rax; pszStr1
0x1800faf37  call    cs:__imp_StrCmpNICW
0x1800faf3d  test    eax, eax
0x1800faf3f  jnz     loc_1800FB12D
0x1800faf45  mov     rax, [rdi]
0x1800faf48  mov     rcx, rdi
0x1800faf4b  mov     rax, [rax+40h]
0x1800faf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf54  mov     ebx, eax
0x1800faf56  test    eax, eax
0x1800faf58  jnz     loc_1800FB132
0x1800faf5e  mov     [rbp+pv], r14
0x1800faf62  mov     [rbp+var_30], r14
0x1800faf66  mov     [rbp+ppwsz], r14
0x1800faf6a  mov     rax, [rdi]
0x1800faf6d  lea     r8, [rbp+nChar]
0x1800faf71  lea     rdx, [rbp+pszStr1]
0x1800faf75  mov     [rbp+pszStr1], r14
0x1800faf79  mov     rcx, rdi
0x1800faf7c  mov     [rbp+nChar], r14d
0x1800faf80  mov     rax, [rax+70h]
0x1800faf84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf89  mov     ebx, 8007139Fh
0x1800faf8e  test    eax, eax
0x1800faf90  js      loc_1800FB095
0x1800faf96  mov     r8d, [rbp+nChar]; nChar
0x1800faf9a  lea     eax, [r8+1]
0x1800faf9e  cmp     eax, 8
0x1800fafa1  jnz     short loc_1800FAFEA
0x1800fafa3  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fafa7  lea     rdx, aVersion_7; "version"
0x1800fafae  call    cs:__imp_StrCmpNICW
0x1800fafb4  test    eax, eax
0x1800fafb6  jnz     short loc_1800FAFE6
0x1800fafb8  mov     rax, [rdi]
0x1800fafbb  lea     rdx, [rbp+psz]
0x1800fafbf  xor     r8d, r8d
0x1800fafc2  mov     [rbp+psz], r14
0x1800fafc6  mov     rcx, rdi
0x1800fafc9  mov     rax, [rax+80h]
0x1800fafd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fafd5  test    eax, eax
0x1800fafd7  js      loc_1800FB095
0x1800fafdd  lea     rdx, [rbp+pv]
0x1800fafe1  jmp     loc_1800FB076
0x1800fafe6  mov     r8d, [rbp+nChar]; nChar
0x1800fafea  lea     eax, [r8+1]
0x1800fafee  cmp     eax, 8
0x1800faff1  jnz     short loc_1800FB033
0x1800faff3  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800faff7  lea     rdx, aTtlhigh; "ttlhigh"
0x1800faffe  call    cs:__imp_StrCmpNICW
0x1800fb004  test    eax, eax
0x1800fb006  jnz     short loc_1800FB02F
0x1800fb008  mov     rax, [rdi]
0x1800fb00b  lea     rdx, [rbp+psz]
0x1800fb00f  xor     r8d, r8d
0x1800fb012  mov     [rbp+psz], r14
0x1800fb016  mov     rcx, rdi
0x1800fb019  mov     rax, [rax+80h]
0x1800fb020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb025  test    eax, eax
0x1800fb027  js      short loc_1800FB095
0x1800fb029  lea     rdx, [rbp+var_30]
0x1800fb02d  jmp     short loc_1800FB076
0x1800fb02f  mov     r8d, [rbp+nChar]; nChar
0x1800fb033  lea     eax, [r8+1]
0x1800fb037  cmp     eax, 7
0x1800fb03a  jnz     short loc_1800FB09D
0x1800fb03c  mov     rcx, [rbp+pszStr1]; pszStr1
0x1800fb040  lea     rdx, aTtllow; "ttllow"
0x1800fb047  call    cs:__imp_StrCmpNICW
0x1800fb04d  test    eax, eax
0x1800fb04f  jnz     short loc_1800FB09D
0x1800fb051  mov     rax, [rdi]
0x1800fb054  lea     rdx, [rbp+psz]
0x1800fb058  xor     r8d, r8d
0x1800fb05b  mov     [rbp+psz], r14
0x1800fb05f  mov     rcx, rdi
0x1800fb062  mov     rax, [rax+80h]
0x1800fb069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb06e  test    eax, eax
0x1800fb070  js      short loc_1800FB095
0x1800fb072  lea     rdx, [rbp+ppwsz]; ppwsz
0x1800fb076  mov     rcx, [rbp+psz]; psz
0x1800fb07a  call    cs:__imp_SHStrDupW
0x1800fb080  test    eax, eax
0x1800fb082  js      short loc_1800FB095
0x1800fb084  mov     rax, [rdi]
0x1800fb087  mov     rcx, rdi
0x1800fb08a  mov     rax, [rax+48h]
0x1800fb08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb093  test    eax, eax
0x1800fb095  jz      loc_1800FAF6A
0x1800fb09b  jmp     short loc_1800FB09F
0x1800fb09d  mov     eax, ebx
0x1800fb09f  cmp     eax, 1
0x1800fb0a2  mov     ecx, r14d
0x1800fb0a5  cmovnz  ecx, eax; this
0x1800fb0a8  test    ecx, ecx
0x1800fb0aa  js      short loc_1800FB103
0x1800fb0ac  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800fb0b0  test    rdx, rdx
0x1800fb0b3  jz      short loc_1800FB105
0x1800fb0b5  cmp     [rbp+ppwsz], r14
0x1800fb0b9  jz      short loc_1800FB105
0x1800fb0bb  cmp     [rbp+var_30], r14
0x1800fb0bf  jz      short loc_1800FB105
0x1800fb0c1  lea     r8, [rsi+250h]; unsigned int *
0x1800fb0c8  or      r9d, 0FFFFFFFFh; unsigned int
0x1800fb0cc  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x1800fb0d1  mov     ebx, eax
0x1800fb0d3  test    eax, eax
0x1800fb0d5  js      short loc_1800FB105
0x1800fb0d7  mov     rdx, [rbp+ppwsz]; unsigned __int16 *
0x1800fb0db  lea     r8, [rsi+4]; unsigned int *
0x1800fb0df  or      r9d, 0FFFFFFFFh; unsigned int
0x1800fb0e3  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x1800fb0e8  mov     ebx, eax
0x1800fb0ea  test    eax, eax
0x1800fb0ec  js      short loc_1800FB105
0x1800fb0ee  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800fb0f2  lea     r8, [rsi+8]; unsigned int *
0x1800fb0f6  or      r9d, 0FFFFFFFFh; unsigned int
0x1800fb0fa  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x1800fb0ff  mov     ebx, eax
0x1800fb101  jmp     short loc_1800FB105
0x1800fb103  mov     ebx, ecx
0x1800fb105  mov     rcx, [rbp+pv]; pv
0x1800fb109  call    cs:__imp_CoTaskMemFree
0x1800fb10f  mov     rcx, [rbp+var_30]; pv
0x1800fb113  mov     [rbp+pv], r14
0x1800fb117  call    cs:__imp_CoTaskMemFree
0x1800fb11d  mov     rcx, [rbp+ppwsz]; pv
0x1800fb121  mov     [rbp+var_30], r14
0x1800fb125  call    cs:__imp_CoTaskMemFree
0x1800fb12b  jmp     short loc_1800FB132
0x1800fb12d  mov     ebx, 8007139Fh
0x1800fb132  mov     eax, ebx
0x1800fb134  jmp     short loc_1800FB13B
0x1800fb136  mov     eax, 80070057h
0x1800fb13b  lea     r11, [rsp+50h+var_s0]
0x1800fb140  mov     rbx, [r11+20h]
0x1800fb144  mov     rsi, [r11+30h]
0x1800fb148  mov     rsp, r11
0x1800fb14b  pop     r14
0x1800fb14d  pop     rdi
0x1800fb14e  pop     rbp
0x1800fb14f  retn
```
