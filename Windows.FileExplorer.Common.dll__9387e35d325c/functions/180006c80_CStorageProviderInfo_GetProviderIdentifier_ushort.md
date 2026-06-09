# CStorageProviderInfo::GetProviderIdentifier(ushort * *)

- ea: `0x180006c80`
- end: `0x180006e6f`
- name: `?GetProviderIdentifier@CStorageProviderInfo@@UEAAJPEAPEAG@Z`
- size: `495`
- prototype: `int(CStorageProviderInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006c80`
- `0x1800077c8`
- `0x1800077ec`
- `0x180007900`
- `0x180038708`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006da5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006da5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006de5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180006cce`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180006cce`

## string_xrefs

- `0x180006dd0`: `onecoreuap\internal\shell\inc\private\sharedstoragesources\SyncRootCommon.h`
- `0x180006df8`: `onecoreuap\internal\shell\inc\private\sharedstoragesources\SyncRootCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderInfo::GetProviderIdentifier(CStorageProviderInfo *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rdx
  unsigned __int64 v4; // rdi
  WCHAR *v5; // rbp
  PWSTR v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rdx
  unsigned int v9; // ebx
  const WCHAR *v10; // rax
  unsigned __int64 v11; // r8
  unsigned __int16 *v12; // r9
  __int64 v13; // rcx
  WCHAR v14; // r10
  __int64 v15; // r10
  unsigned __int16 *v16; // rcx
  __int64 v18; // rsi
  bool v19; // cf
  int v20; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR pszStart; // [rsp+40h] [rbp+8h] BYREF

  v3 = (const unsigned __int16 *)*((_QWORD *)this + 12);
  *a2 = 0;
  if ( !v3 )
    return 0;
  v4 = -1;
  wil::make_cotaskmem_string_nothrow((wil *)&pszStart, v3, 0xFFFFFFFFFFFFFFFFuLL);
  v5 = (WCHAR *)pszStart;
  if ( !pszStart )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\SyncRootCommon.h",
      (const char *)0x8007000ELL,
      v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszStart);
    return (unsigned int)-2147024882;
  }
  v6 = StrChrW(pszStart, 0x21u);
  if ( v6 )
    *v6 = 0;
  do
    ++v4;
  while ( v5[v4] );
  *a2 = 0;
  v7 = v4 + 1;
  if ( v4 + 1 < v4 || !is_mul_ok(v7, 2u) )
  {
    v9 = -2147024362;
    goto LABEL_27;
  }
  v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
  *a2 = v8;
  v9 = v8 == 0 ? 0x8007000E : 0;
  if ( !v8 )
  {
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\SyncRootCommon.h",
      (const char *)v9,
      v20);
    CoTaskMemFree(v5);
    return v9;
  }
  if ( v7 > 0x7FFFFFFF )
    goto LABEL_33;
  if ( v4 < 0x7FFFFFFF )
  {
    v10 = v5;
    if ( !v5 )
    {
      v10 = &String1;
      v4 = 0;
    }
    if ( v7 )
    {
      v11 = v7;
      v12 = v8;
      v13 = 0;
      do
      {
        if ( !v4 )
          break;
        v14 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v12++ = v14;
        --v4;
        ++v13;
        --v11;
      }
      while ( v11 );
      v15 = v13 - 1;
      if ( v11 )
        v15 = v13;
      v16 = v12 - 1;
      if ( v11 )
        v16 = v12;
      *v16 = 0;
      if ( v11 )
      {
        v19 = v7 == v15;
        v18 = v7 - v15;
        if ( !v19 && v18 != 1 && (unsigned __int64)(2 * v18) > 2 )
          memset_0(&v8[v15 + 1], 0, 2 * v18 - 2);
      }
    }
    goto LABEL_23;
  }
  if ( v4 != -1 )
LABEL_33:
    *v8 = 0;
LABEL_23:
  CoTaskMemFree(v5);
  return 0;
}

```

## disassembly

```asm
0x180006c80  mov     [rsp+arg_8], rbx
0x180006c85  mov     [rsp+arg_10], rbp
0x180006c8a  push    rsi
0x180006c8b  push    rdi
0x180006c8c  push    r14; int
0x180006c8e  sub     rsp, 20h
0x180006c92  mov     rbx, rdx
0x180006c95  mov     rdx, [rcx+60h]; unsigned __int16 *
0x180006c99  xor     r14d, r14d
0x180006c9c  mov     [rbx], r14
0x180006c9f  test    rdx, rdx
0x180006ca2  jz      loc_180006DAB
0x180006ca8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006cac  mov     r8, rdi; unsigned __int64
0x180006caf  lea     rcx, [rsp+38h+pszStart]; this
0x180006cb4  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180006cb9  nop
0x180006cba  mov     rbp, [rsp+38h+pszStart]
0x180006cbf  test    rbp, rbp
0x180006cc2  jz      loc_180006DED
0x180006cc8  lea     edx, [rdi+22h]; wMatch
0x180006ccb  mov     rcx, rbp; pszStart
0x180006cce  call    cs:__imp_StrChrW
0x180006cd4  test    rax, rax
0x180006cd7  jz      short loc_180006CDD
0x180006cd9  mov     [rax], r14w
0x180006cdd  inc     rdi
0x180006ce0  cmp     [rbp+rdi*2+0], r14w
0x180006ce6  jnz     short loc_180006CDD
0x180006ce8  mov     [rbx], r14
0x180006ceb  lea     rsi, [rdi+1]
0x180006cef  cmp     rsi, rdi
0x180006cf2  jb      loc_180006DC3
0x180006cf8  mov     eax, 2
0x180006cfd  mul     rsi
0x180006d00  test    rdx, rdx
0x180006d03  jnz     loc_180006DC3
0x180006d09  mov     rcx, rax; cb
0x180006d0c  call    cs:__imp_CoTaskMemAlloc
0x180006d12  mov     rdx, rax
0x180006d15  mov     [rbx], rax
0x180006d18  mov     rcx, rax
0x180006d1b  neg     rcx
0x180006d1e  sbb     ebx, ebx
0x180006d20  not     ebx
0x180006d22  and     ebx, 8007000Eh
0x180006d28  test    rax, rax
0x180006d2b  jz      loc_180006DC8
0x180006d31  mov     eax, 7FFFFFFFh
0x180006d36  cmp     rsi, rax
0x180006d39  ja      loc_180006E65
0x180006d3f  cmp     rdi, rax
0x180006d42  jnb     loc_180006E5C
0x180006d48  mov     rax, rbp
0x180006d4b  test    rbp, rbp
0x180006d4e  jz      loc_180006E4D
0x180006d54  test    rsi, rsi
0x180006d57  jz      short loc_180006DA2
0x180006d59  mov     r8, rsi
0x180006d5c  mov     r9, rdx
0x180006d5f  mov     rcx, r14
0x180006d62  test    rdi, rdi
0x180006d65  jz      short loc_180006D89
0x180006d67  movzx   r10d, word ptr [rax]
0x180006d6b  test    r10w, r10w
0x180006d6f  jz      short loc_180006D89
0x180006d71  add     rax, 2
0x180006d75  mov     [r9], r10w
0x180006d79  add     r9, 2
0x180006d7d  dec     rdi
0x180006d80  inc     rcx
0x180006d83  sub     r8, 1
0x180006d87  jnz     short loc_180006D62
0x180006d89  lea     r10, [rcx-1]
0x180006d8d  test    r8, r8
0x180006d90  cmovnz  r10, rcx
0x180006d94  lea     rcx, [r9-2]
0x180006d98  cmovnz  rcx, r9
0x180006d9c  mov     [rcx], r14w
0x180006da0  jnz     short loc_180006E1B
0x180006da2  mov     rcx, rbp; pv
0x180006da5  call    cs:__imp_CoTaskMemFree
0x180006dab  mov     ebx, r14d
0x180006dae  mov     eax, ebx
0x180006db0  mov     rbx, [rsp+38h+arg_8]
0x180006db5  mov     rbp, [rsp+38h+arg_10]
0x180006dba  add     rsp, 20h
0x180006dbe  pop     r14
0x180006dc0  pop     rdi
0x180006dc1  pop     rsi
0x180006dc2  retn
0x180006dc3  mov     ebx, 80070216h
0x180006dc8  mov     rcx, [rsp+38h]; this
0x180006dcd  mov     r9d, ebx; char *
0x180006dd0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180006dd7  mov     edx, 34h ; '4'; void *
0x180006ddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006de1  nop
0x180006de2  mov     rcx, rbp; pv
0x180006de5  call    cs:__imp_CoTaskMemFree
0x180006deb  jmp     short loc_180006DAE
0x180006ded  mov     rcx, [rsp+38h]; this
0x180006df2  mov     r9d, 8007000Eh; char *
0x180006df8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180006dff  mov     edx, 2Dh ; '-'; void *
0x180006e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e09  nop
0x180006e0a  lea     rcx, [rsp+38h+pszStart]; void *
0x180006e0f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180006e14  mov     ebx, 8007000Eh
0x180006e19  jmp     short loc_180006DAE
0x180006e1b  sub     rsi, r10
0x180006e1e  cmp     rsi, 1
0x180006e22  jbe     loc_180006DA2
0x180006e28  lea     r8, [rsi+rsi]
0x180006e2c  cmp     r8, 2
0x180006e30  jbe     loc_180006DA2
0x180006e36  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180006e3a  inc     r10
0x180006e3d  lea     rcx, [rdx+r10*2]; void *
0x180006e41  xor     edx, edx; Val
0x180006e43  call    memset_0
0x180006e48  jmp     loc_180006DA2
0x180006e4d  lea     rax, String1
0x180006e54  mov     rdi, r14
0x180006e57  jmp     loc_180006D54
0x180006e5c  test    rsi, rsi
0x180006e5f  jz      loc_180006DA2
0x180006e65  mov     [rdx], r14w
0x180006e69  jmp     loc_180006DA2
```
