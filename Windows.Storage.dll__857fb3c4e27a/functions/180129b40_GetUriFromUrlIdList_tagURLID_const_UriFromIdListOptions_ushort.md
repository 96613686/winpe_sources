# GetUriFromUrlIdList(tagURLID const *,UriFromIdListOptions,ushort * *)

- ea: `0x180129b40`
- end: `0x180129d95`
- name: `?GetUriFromUrlIdList@@YAJPEFBUtagURLID@@W4UriFromIdListOptions@@PEAPEAG@Z`
- size: `597`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801296f0`
- `0x18012a104`
- `0x18018e450`
- `0x1802979c8`
- `0x1802da200`
- `0x1802e3980`
- `0x1802edb58`
- `0x18032d380`
- `0x1805f6d68`

## callees

- `0x18001b390`
- `0x1800432f0`
- `0x180129b40`
- `0x180129da0`
- `0x180257940`
- `0x1802d99a4`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180129cda`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x1806476bd`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x180129cda`
- `api-ms-win-core-url-l1-1-0!UrlCombineW` at `0x1806476bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129ca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806476ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806476f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129b9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129ca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806476ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1806476f4`
- `SHCORE!__imp_ualstrcpynW` at `0x180129bc1`
- `SHCORE!__imp_ualstrcpynW` at `0x180129bc1`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180129d81`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180129d81`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUriFromUrlIdList(unsigned __int16 *a1, int a2, _QWORD *a3)
{
  unsigned __int64 v6; // rsi
  void **cotaskmem_string_nothrow; // rax
  void *v8; // rbx
  char v9; // al
  WCHAR **v11; // rax
  WCHAR *v12; // r15
  HRESULT v13; // eax
  unsigned int v14; // edi
  WCHAR *v15; // r15
  HRESULT v16; // eax
  unsigned int v17; // r12d
  DWORD dwFlags; // [rsp+20h] [rbp-78h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-78h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-78h]
  LPVOID v21[3]; // [rsp+30h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = ((unsigned __int64)*a1 - 6) >> 1;
  cotaskmem_string_nothrow = (void **)wil::make_cotaskmem_string_nothrow((wil *)&pv, 0, v6);
  v8 = *cotaskmem_string_nothrow;
  v21[1] = *cotaskmem_string_nothrow;
  *cotaskmem_string_nothrow = 0;
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    return 2147942414LL;
  }
  v9 = *((_BYTE *)a1 + 3);
  if ( v9 )
  {
    if ( v9 == (char)0x80 )
      ualstrcpynW(v8, a1 + 4, (unsigned int)v6);
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      0,
      v6);
    v15 = (WCHAR *)pv;
    if ( !pv )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
        (const char *)0x8007000ELL,
        dwFlags);
      CoTaskMemFree(v8);
      return 2147942414LL;
    }
    StringCchCopyA((char *)pv, v6, (const char *)a1 + 8);
    SHAnsiToUnicode((PCSTR)v8, v15, v6);
    CoTaskMemFree(v15);
  }
  if ( !a2 )
  {
LABEL_8:
    *a3 = v8;
    return 0;
  }
  LODWORD(pv) = v6;
  v11 = (WCHAR **)wil::make_cotaskmem_string_nothrow((wil *)v21, 0, v6);
  v12 = *v11;
  v21[2] = *v11;
  *v11 = 0;
  if ( v21[0] )
    CoTaskMemFree(v21[0]);
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    CoTaskMemFree(v8);
    return 2147942414LL;
  }
  if ( (unsigned int)ILGetHiddenStringW(a1, 3203334146LL, v12, (unsigned int)v6) )
  {
    v16 = UrlCombineW((PCWSTR)v8, v12, (PWSTR)v8, (DWORD *)&pv, 0);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsb);
      CoTaskMemFree(v12);
      CoTaskMemFree(v8);
      return v17;
    }
    LODWORD(pv) = v6;
  }
  if ( a2 != 1
    || !(unsigned int)ILGetHiddenStringW(a1, 3203334145LL, v12, (unsigned int)v6)
    || (v13 = UrlCombineW((PCWSTR)v8, v12, (PWSTR)v8, (DWORD *)&pv, 0), v14 = v13, v13 >= 0) )
  {
    CoTaskMemFree(v12);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19B,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\internetfolder\\internetfolder.cpp",
    (const char *)(unsigned int)v13,
    dwFlagsa);
  CoTaskMemFree(v12);
  CoTaskMemFree(v8);
  return v14;
}

```

## disassembly

```asm
0x180129b40  mov     [rsp+arg_8], rbx
0x180129b45  push    rbp
0x180129b46  push    rsi
0x180129b47  push    rdi
0x180129b48  push    r12
0x180129b4a  push    r13
0x180129b4c  push    r14
0x180129b4e  push    r15
0x180129b50  sub     rsp, 60h
0x180129b54  mov     rax, cs:__security_cookie
0x180129b5b  xor     rax, rsp
0x180129b5e  mov     [rsp+98h+var_48], rax
0x180129b63  mov     r14, r8
0x180129b66  mov     ebp, edx
0x180129b68  mov     rdi, rcx
0x180129b6b  movzx   esi, word ptr [rcx]
0x180129b6e  sub     rsi, 6
0x180129b72  shr     rsi, 1
0x180129b75  mov     r8, rsi; unsigned __int64
0x180129b78  xor     edx, edx; unsigned __int16 *
0x180129b7a  lea     rcx, [rsp+98h+pv]; this
0x180129b7f  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180129b84  mov     rbx, [rax]
0x180129b87  mov     [rsp+98h+var_60], rbx
0x180129b8c  xor     r13d, r13d
0x180129b8f  mov     [rax], r13
0x180129b92  mov     rcx, [rsp+98h+pv]; pv
0x180129b97  test    rcx, rcx
0x180129b9a  jz      short loc_180129BA2
0x180129b9c  call    cs:__imp_CoTaskMemFree
0x180129ba2  test    rbx, rbx
0x180129ba5  jz      short loc_180129BF5
0x180129ba7  movzx   eax, byte ptr [rdi+3]
0x180129bab  test    al, al
0x180129bad  jz      loc_180129D1D
0x180129bb3  cmp     al, 80h
0x180129bb5  jnz     short loc_180129BC7
0x180129bb7  mov     r8d, esi
0x180129bba  lea     rdx, [rdi+8]
0x180129bbe  mov     rcx, rbx
0x180129bc1  call    cs:__imp_ualstrcpynW
0x180129bc7  test    ebp, ebp
0x180129bc9  jnz     short loc_180129C1C
0x180129bcb  mov     [r14], rbx
0x180129bce  xor     eax, eax
0x180129bd0  mov     rcx, [rsp+98h+var_48]
0x180129bd5  xor     rcx, rsp; StackCookie
0x180129bd8  call    __security_check_cookie
0x180129bdd  mov     rbx, [rsp+98h+arg_8]
0x180129be5  add     rsp, 60h
0x180129be9  pop     r15
0x180129beb  pop     r14
0x180129bed  pop     r13
0x180129bef  pop     r12
0x180129bf1  pop     rdi
0x180129bf2  pop     rsi
0x180129bf3  pop     rbp
0x180129bf4  retn
0x180129bf5  mov     rcx, [rsp+98h]; this
0x180129bfd  mov     r9d, 8007000Eh; char *
0x180129c03  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180129c0a  mov     edx, 17Eh; void *
0x180129c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129c14  nop
0x180129c15  mov     eax, 8007000Eh
0x180129c1a  jmp     short loc_180129BD0
0x180129c1c  mov     dword ptr [rsp+98h+pv], esi
0x180129c20  mov     r8, rsi; unsigned __int64
0x180129c23  xor     edx, edx; unsigned __int16 *
0x180129c25  lea     rcx, [rsp+98h+var_68]; this
0x180129c2a  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180129c2f  mov     r15, [rax]
0x180129c32  mov     [rsp+98h+var_58], r15
0x180129c37  mov     [rax], r13
0x180129c3a  mov     rcx, [rsp+98h+var_68]; pv
0x180129c3f  test    rcx, rcx
0x180129c42  jz      short loc_180129C4A
0x180129c44  call    cs:__imp_CoTaskMemFree
0x180129c4a  test    r15, r15
0x180129c4d  jz      short loc_180129C7D
0x180129c4f  mov     r9d, esi
0x180129c52  mov     r8, r15
0x180129c55  mov     edx, 0BEEF0002h
0x180129c5a  mov     rcx, rdi
0x180129c5d  call    ?ILGetHiddenStringW@@YAHPEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@PEAGK@Z; ILGetHiddenStringW(_ITEMIDLIST_RELATIVE const *,IDLHID,ushort *,ulong)
0x180129c62  test    eax, eax
0x180129c64  jnz     loc_1806476AA
0x180129c6a  cmp     ebp, 1
0x180129c6d  jz      short loc_180129CB0
0x180129c6f  mov     rcx, r15; pv
0x180129c72  call    cs:__imp_CoTaskMemFree
0x180129c78  jmp     loc_180129BCB
0x180129c7d  mov     rcx, [rsp+98h]; this
0x180129c85  mov     r9d, 8007000Eh; char *
0x180129c8b  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180129c92  mov     edx, 191h; void *
0x180129c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129c9c  nop
0x180129c9d  mov     rcx, rbx; pv
0x180129ca0  call    cs:__imp_CoTaskMemFree
0x180129ca6  mov     eax, 8007000Eh
0x180129cab  jmp     loc_180129BD0
0x180129cb0  mov     r9d, esi
0x180129cb3  mov     r8, r15
0x180129cb6  mov     edx, 0BEEF0001h
0x180129cbb  mov     rcx, rdi
0x180129cbe  call    ?ILGetHiddenStringW@@YAHPEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@PEAGK@Z; ILGetHiddenStringW(_ITEMIDLIST_RELATIVE const *,IDLHID,ushort *,ulong)
0x180129cc3  test    eax, eax
0x180129cc5  jz      short loc_180129C6F
0x180129cc7  mov     [rsp+98h+dwFlags], r13d; int
0x180129ccc  lea     r9, [rsp+98h+pv]; pcchCombined
0x180129cd1  mov     r8, rbx; pszCombined
0x180129cd4  mov     rdx, r15; pszRelative
0x180129cd7  mov     rcx, rbx; pszBase
0x180129cda  call    cs:__imp_UrlCombineW
0x180129ce0  mov     edi, eax
0x180129ce2  test    eax, eax
0x180129ce4  jns     short loc_180129C6F
0x180129ce6  mov     rcx, [rsp+98h]; this
0x180129cee  mov     r9d, eax; char *
0x180129cf1  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180129cf8  mov     edx, 19Bh; void *
0x180129cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129d02  nop
0x180129d03  mov     rcx, r15; pv
0x180129d06  call    cs:__imp_CoTaskMemFree
0x180129d0c  nop
0x180129d0d  mov     rcx, rbx; pv
0x180129d10  call    cs:__imp_CoTaskMemFree
0x180129d16  mov     eax, edi
0x180129d18  jmp     loc_180129BD0
0x180129d1d  mov     r8, rsi
0x180129d20  xor     edx, edx
0x180129d22  lea     rcx, [rsp+98h+pv]
0x180129d27  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180129d2c  mov     r15, [rsp+98h+pv]
0x180129d31  test    r15, r15
0x180129d34  jnz     short loc_180129D69
0x180129d36  mov     rcx, [rsp+98h]; this
0x180129d3e  mov     r9d, 8007000Eh; char *
0x180129d44  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x180129d4b  mov     edx, 183h; void *
0x180129d50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129d55  nop
0x180129d56  mov     rcx, rbx; pv
0x180129d59  call    cs:__imp_CoTaskMemFree
0x180129d5f  mov     eax, 8007000Eh
0x180129d64  jmp     loc_180129BD0
0x180129d69  lea     r8, [rdi+8]; char *
0x180129d6d  mov     rdx, rsi; unsigned __int64
0x180129d70  mov     rcx, r15; char *
0x180129d73  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180129d78  mov     r8d, esi; cwchBuf
0x180129d7b  mov     rdx, r15; pwszDst
0x180129d7e  mov     rcx, rbx; pszSrc
0x180129d81  call    cs:__imp_SHAnsiToUnicode
0x180129d87  mov     rcx, r15; pv
0x180129d8a  call    cs:__imp_CoTaskMemFree
0x180129d90  jmp     loc_180129BC7
0x1806476aa  mov     [rsp+98h+dwFlags], r13d; int
0x1806476af  lea     r9, [rsp+98h+pv]; pcchCombined
0x1806476b4  mov     r8, rbx; pszCombined
0x1806476b7  mov     rdx, r15; pszRelative
0x1806476ba  mov     rcx, rbx; pszBase
0x1806476bd  call    cs:__imp_UrlCombineW
0x1806476c3  mov     r12d, eax
0x1806476c6  test    eax, eax
0x1806476c8  jns     short loc_180647702
0x1806476ca  mov     rcx, [rsp+98h]; this
0x1806476d2  mov     r9d, eax; char *
0x1806476d5  lea     r8, aOnecoreuapShel_154; "onecoreuap\\shell\\windows.storage\\int"...
0x1806476dc  mov     edx, 195h; void *
0x1806476e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1806476e6  nop
0x1806476e7  mov     rcx, r15; pv
0x1806476ea  call    cs:__imp_CoTaskMemFree
0x1806476f0  nop
0x1806476f1  mov     rcx, rbx; pv
0x1806476f4  call    cs:__imp_CoTaskMemFree
0x1806476fa  mov     eax, r12d
0x1806476fd  jmp     loc_180129BD0
0x180647702  mov     dword ptr [rsp+98h+pv], esi
0x180647706  jmp     loc_180129C6A
```
