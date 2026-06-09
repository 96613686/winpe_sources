# Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(ushort const *,ushort * *)

- ea: `0x180006e78`
- end: `0x180007071`
- name: `?ConvertFullIdentifierToProviderIdentifier@SyncRootHelpers@Internal@Windows@@YAJPEBGPEAPEAG@Z`
- size: `505`
- prototype: `int(Windows::Internal::SyncRootHelpers *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000593c`
- `0x1800353dc`
- `0x18006052c`

## callees

- `0x180006e78`
- `0x1800077c8`
- `0x1800077ec`
- `0x180007900`
- `0x180038708`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007010`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180006f26`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180006f26`

## string_xrefs

- `0x180006ec2`: `onecoreuap\internal\shell\inc\private\sharedstoragesources\SyncRootCommon.h`
- `0x180006ffb`: `onecoreuap\internal\shell\inc\private\sharedstoragesources\SyncRootCommon.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(
        Windows::Internal::SyncRootHelpers *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int64 v4; // rbx
  WCHAR *v5; // rbp
  __int64 v7; // r10
  WCHAR *v8; // rcx
  PWSTR v9; // rax
  unsigned __int64 v10; // rsi
  WCHAR *v11; // rdx
  unsigned int v12; // edi
  const WCHAR *v13; // rax
  unsigned __int64 v14; // r8
  WCHAR *v15; // r9
  __int64 v16; // rcx
  WCHAR v17; // r10
  __int64 v18; // rsi
  bool v19; // cf
  int v20; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)a2 = 0;
  if ( !this )
    return 0;
  v4 = -1;
  wil::make_cotaskmem_string_nothrow((wil *)&pv, (const unsigned __int16 *)this, 0xFFFFFFFFFFFFFFFFuLL);
  v5 = (WCHAR *)pv;
  if ( !pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\SyncRootCommon.h",
      (const char *)0x8007000ELL,
      v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pv);
    return 2147942414LL;
  }
  v9 = StrChrW((PCWSTR)pv, 0x21u);
  if ( v9 )
    *v9 = 0;
  do
    ++v4;
  while ( v5[v4] );
  *(_QWORD *)a2 = 0;
  v10 = v4 + 1;
  if ( v4 + 1 >= v4 && is_mul_ok(v10, 2u) )
  {
    v11 = (WCHAR *)CoTaskMemAlloc(2 * v10);
    *(_QWORD *)a2 = v11;
    v12 = v11 == 0 ? 0x8007000E : 0;
    if ( v11 )
    {
      if ( v10 > 0x7FFFFFFF )
        goto LABEL_33;
      if ( v4 < 0x7FFFFFFF )
      {
        v13 = v5;
        if ( !v5 )
        {
          v13 = &String1;
          v4 = 0;
        }
        if ( v10 )
        {
          v14 = v10;
          v15 = v11;
          v16 = 0;
          do
          {
            if ( !v4 )
              break;
            v17 = *v13;
            if ( !*v13 )
              break;
            ++v13;
            *v15++ = v17;
            --v4;
            ++v16;
            --v14;
          }
          while ( v14 );
          v7 = v16 - 1;
          if ( v14 )
            v7 = v16;
          v8 = v15 - 1;
          if ( v14 )
            v8 = v15;
          *v8 = 0;
          if ( v14 )
          {
            v19 = v10 == v7;
            v18 = v10 - v7;
            if ( !v19 && v18 != 1 && (unsigned __int64)(2 * v18) > 2 )
              memset_0(&v11[v7 + 1], 0, 2 * v18 - 2);
          }
        }
        goto LABEL_9;
      }
      if ( v4 != -1 )
LABEL_33:
        *v11 = 0;
LABEL_9:
      CoTaskMemFree(v5);
      return 0;
    }
  }
  else
  {
    v12 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x34,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\sharedstoragesources\\SyncRootCommon.h",
    (const char *)v12,
    v20);
  CoTaskMemFree(v5);
  return v12;
}

```

## disassembly

```asm
0x180006e78  mov     [rsp+arg_8], rbx
0x180006e7d  mov     [rsp+arg_10], rbp
0x180006e82  push    rsi
0x180006e83  push    rdi
0x180006e84  push    r14; int
0x180006e86  sub     rsp, 20h
0x180006e8a  mov     rdi, rdx
0x180006e8d  xor     r14d, r14d
0x180006e90  mov     [rdx], r14
0x180006e93  test    rcx, rcx
0x180006e96  jz      short loc_180006F09
0x180006e98  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006e9c  mov     r8, rbx; unsigned __int64
0x180006e9f  mov     rdx, rcx; unsigned __int16 *
0x180006ea2  lea     rcx, [rsp+38h+pv]; this
0x180006ea7  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180006eac  nop
0x180006ead  mov     rbp, [rsp+38h+pv]
0x180006eb2  test    rbp, rbp
0x180006eb5  jnz     short loc_180006F1E
0x180006eb7  mov     rcx, [rsp+38h]; this
0x180006ebc  mov     r9d, 8007000Eh; char *
0x180006ec2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180006ec9  lea     edx, [rbx+2Eh]; void *
0x180006ecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ed1  nop
0x180006ed2  lea     rcx, [rsp+38h+pv]; void *
0x180006ed7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180006edc  mov     eax, 8007000Eh
0x180006ee1  jmp     short loc_180006F0B
0x180006ee3  lea     r10, [rcx-1]
0x180006ee7  test    r8, r8
0x180006eea  cmovnz  r10, rcx
0x180006eee  lea     rcx, [r9-2]
0x180006ef2  cmovnz  rcx, r9
0x180006ef6  mov     [rcx], r14w
0x180006efa  jnz     loc_18000701D
0x180006f00  mov     rcx, rbp; pv
0x180006f03  call    cs:__imp_CoTaskMemFree
0x180006f09  xor     eax, eax
0x180006f0b  mov     rbx, [rsp+38h+arg_8]
0x180006f10  mov     rbp, [rsp+38h+arg_10]
0x180006f15  add     rsp, 20h
0x180006f19  pop     r14
0x180006f1b  pop     rdi
0x180006f1c  pop     rsi
0x180006f1d  retn
0x180006f1e  mov     edx, 21h ; '!'; wMatch
0x180006f23  mov     rcx, rbp; pszStart
0x180006f26  call    cs:__imp_StrChrW
0x180006f2c  test    rax, rax
0x180006f2f  jz      short loc_180006F35
0x180006f31  mov     [rax], r14w
0x180006f35  inc     rbx
0x180006f38  cmp     [rbp+rbx*2+0], r14w
0x180006f3e  jnz     short loc_180006F35
0x180006f40  mov     [rdi], r14
0x180006f43  lea     rsi, [rbx+1]
0x180006f47  cmp     rsi, rbx
0x180006f4a  jb      loc_180006FEE
0x180006f50  mov     eax, 2
0x180006f55  mul     rsi
0x180006f58  test    rdx, rdx
0x180006f5b  jnz     loc_180006FEE
0x180006f61  mov     rcx, rax; cb
0x180006f64  call    cs:__imp_CoTaskMemAlloc
0x180006f6a  mov     rdx, rax
0x180006f6d  mov     [rdi], rax
0x180006f70  mov     rcx, rax
0x180006f73  neg     rcx
0x180006f76  sbb     edi, edi
0x180006f78  not     edi
0x180006f7a  and     edi, 8007000Eh
0x180006f80  test    rax, rax
0x180006f83  jz      short loc_180006FF3
0x180006f85  mov     eax, 7FFFFFFFh
0x180006f8a  cmp     rsi, rax
0x180006f8d  ja      loc_180007067
0x180006f93  cmp     rbx, rax
0x180006f96  jnb     loc_18000705E
0x180006f9c  mov     rax, rbp
0x180006f9f  test    rbp, rbp
0x180006fa2  jz      loc_18000704F
0x180006fa8  test    rsi, rsi
0x180006fab  jz      loc_180006F00
0x180006fb1  mov     r8, rsi
0x180006fb4  mov     r9, rdx
0x180006fb7  mov     rcx, r14
0x180006fba  test    rbx, rbx
0x180006fbd  jz      loc_180006EE3
0x180006fc3  movzx   r10d, word ptr [rax]
0x180006fc7  test    r10w, r10w
0x180006fcb  jz      loc_180006EE3
0x180006fd1  add     rax, 2
0x180006fd5  mov     [r9], r10w
0x180006fd9  add     r9, 2
0x180006fdd  dec     rbx
0x180006fe0  inc     rcx
0x180006fe3  sub     r8, 1
0x180006fe7  jnz     short loc_180006FBA
0x180006fe9  jmp     loc_180006EE3
0x180006fee  mov     edi, 80070216h
0x180006ff3  mov     rcx, [rsp+38h]; this
0x180006ff8  mov     r9d, edi; char *
0x180006ffb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180007002  mov     edx, 34h ; '4'; void *
0x180007007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000700c  nop
0x18000700d  mov     rcx, rbp; pv
0x180007010  call    cs:__imp_CoTaskMemFree
0x180007016  mov     eax, edi
0x180007018  jmp     loc_180006F0B
0x18000701d  sub     rsi, r10
0x180007020  cmp     rsi, 1
0x180007024  jbe     loc_180006F00
0x18000702a  lea     r8, [rsi+rsi]
0x18000702e  cmp     r8, 2
0x180007032  jbe     loc_180006F00
0x180007038  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000703c  inc     r10
0x18000703f  lea     rcx, [rdx+r10*2]; void *
0x180007043  xor     edx, edx; Val
0x180007045  call    memset_0
0x18000704a  jmp     loc_180006F00
0x18000704f  lea     rax, String1
0x180007056  mov     rbx, r14
0x180007059  jmp     loc_180006FA8
0x18000705e  test    rsi, rsi
0x180007061  jz      loc_180006F00
0x180007067  mov     [rdx], r14w
0x18000706b  jmp     loc_180006F00
```
