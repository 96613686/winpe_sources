# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18002545c`
- end: `0x180025642`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180029348`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18000ab14`
- `0x18002545c`
- `0x180026d18`
- `0x180028c18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025560`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800255d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025560`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800255d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002554d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002554d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002550c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002557a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002550c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002557a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800255ec`

## string_xrefs

- `0x180025603`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 result; // rax
  void *v5; // rbx
  unsigned __int64 v6; // rax
  char *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // r15
  char *v10; // rsi
  void *v11; // r12
  DWORD LastError; // edi
  int v13; // edi
  void *v14; // rsi
  DWORD v15; // edi
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-D8h] BYREF
  char v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  memset_0(v20, 0, sizeof(v20));
  *(_QWORD *)v16 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v20, 256, v16);
  if ( (int)result >= 0 )
  {
    v5 = 0;
    v6 = *(_QWORD *)v16;
    if ( *(_QWORD *)v16 > 0x100u )
    {
      while ( 1 )
      {
        v9 = v6;
        v10 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &hMem,
                        0,
                        v6 - 1);
        if ( &v18 != v10 )
        {
          v11 = *(void **)v10;
          if ( v5 )
          {
            LastError = GetLastError();
            LocalFree(v5);
            SetLastError(LastError);
          }
          v5 = v11;
          *(_QWORD *)v10 = 0;
        }
        if ( hMem )
          LocalFree(hMem);
        if ( !v5 )
          break;
        v13 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v5, v9, v16);
        if ( v13 < 0 )
        {
          LocalFree(v5);
          return (unsigned int)v13;
        }
        v6 = *(_QWORD *)v16;
        if ( *(_QWORD *)v16 <= v9 )
          goto LABEL_18;
      }
      v8 = 378;
      goto LABEL_26;
    }
    v7 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                   &hMem,
                   v20,
                   *(_QWORD *)v16 - 1LL);
    if ( &v18 != v7 )
    {
      v5 = *(void **)v7;
      *(_QWORD *)v7 = 0;
    }
    if ( hMem )
      LocalFree(hMem);
    if ( !v5 )
    {
      v8 = 367;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)0x8007000ELL,
        v16[0]);
      return 2147942414LL;
    }
LABEL_18:
    if ( a1 == &v19 )
    {
      LocalFree(v5);
    }
    else
    {
      v14 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        v15 = GetLastError();
        LocalFree(v14);
        SetLastError(v15);
      }
      *(_QWORD *)a1 = v5;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002545c  mov     [rsp-8+arg_10], rbx
0x180025461  push    rbp
0x180025462  push    rsi
0x180025463  push    rdi
0x180025464  push    r12
0x180025466  push    r13
0x180025468  push    r14
0x18002546a  push    r15
0x18002546c  lea     rbp, [rsp-150h]
0x180025474  sub     rsp, 250h
0x18002547b  mov     rax, cs:__security_cookie
0x180025482  xor     rax, rsp
0x180025485  mov     [rbp+180h+var_40], rax
0x18002548c  mov     r13, rdx
0x18002548f  mov     r14, rcx
0x180025492  xor     edx, edx; Val
0x180025494  mov     r8d, 200h; Size
0x18002549a  lea     rcx, [rsp+280h+var_240]; void *
0x18002549f  call    memset_0
0x1800254a4  mov     qword ptr [rsp+280h+var_260], 0; int
0x1800254ad  lea     r9, [rsp+280h+var_260]
0x1800254b2  mov     edi, 100h
0x1800254b7  mov     r8d, edi
0x1800254ba  lea     rdx, [rsp+280h+var_240]
0x1800254bf  mov     rcx, r13
0x1800254c2  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800254c7  test    eax, eax
0x1800254c9  js      loc_180025618
0x1800254cf  xor     ebx, ebx
0x1800254d1  mov     rax, qword ptr [rsp+280h+var_260]
0x1800254d6  cmp     rax, rdi
0x1800254d9  ja      short loc_180025525
0x1800254db  lea     r8, [rax-1]
0x1800254df  lea     rdx, [rsp+280h+var_240]
0x1800254e4  lea     rcx, [rsp+280h+hMem]
0x1800254e9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800254ee  lea     rcx, [rsp+280h+var_250]
0x1800254f3  cmp     rcx, rax
0x1800254f6  jz      short loc_180025502
0x1800254f8  mov     rbx, [rax]
0x1800254fb  mov     qword ptr [rax], 0
0x180025502  mov     rcx, [rsp+280h+hMem]; hMem
0x180025507  test    rcx, rcx
0x18002550a  jz      short loc_180025512
0x18002550c  call    cs:__imp_LocalFree
0x180025512  test    rbx, rbx
0x180025515  jnz     loc_1800255AC
0x18002551b  mov     edx, 16Fh
0x180025520  jmp     loc_1800255FB
0x180025525  mov     r15, rax
0x180025528  lea     r8, [rax-1]
0x18002552c  xor     edx, edx
0x18002552e  lea     rcx, [rsp+280h+hMem]
0x180025533  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180025538  mov     rsi, rax
0x18002553b  lea     rax, [rsp+280h+var_250]
0x180025540  cmp     rax, rsi
0x180025543  jz      short loc_180025570
0x180025545  mov     r12, [rsi]
0x180025548  test    rbx, rbx
0x18002554b  jz      short loc_180025566
0x18002554d  call    cs:__imp_GetLastError
0x180025553  mov     edi, eax
0x180025555  mov     rcx, rbx; hMem
0x180025558  call    cs:__imp_LocalFree
0x18002555e  mov     ecx, edi; dwErrCode
0x180025560  call    cs:__imp_SetLastError
0x180025566  mov     rbx, r12
0x180025569  mov     qword ptr [rsi], 0
0x180025570  mov     rcx, [rsp+280h+hMem]; hMem
0x180025575  test    rcx, rcx
0x180025578  jz      short loc_180025580
0x18002557a  call    cs:__imp_LocalFree
0x180025580  test    rbx, rbx
0x180025583  jz      short loc_1800255F6
0x180025585  lea     r9, [rsp+280h+var_260]
0x18002558a  mov     r8, r15
0x18002558d  mov     rdx, rbx
0x180025590  mov     rcx, r13
0x180025593  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180025598  mov     edi, eax
0x18002559a  test    eax, eax
0x18002559c  js      short loc_1800255E9
0x18002559e  mov     rax, qword ptr [rsp+280h+var_260]
0x1800255a3  cmp     rax, r15
0x1800255a6  ja      loc_180025525
0x1800255ac  lea     rax, [rsp+280h+var_248]
0x1800255b1  cmp     r14, rax
0x1800255b4  jz      short loc_1800255DC
0x1800255b6  mov     rsi, [r14]
0x1800255b9  test    rsi, rsi
0x1800255bc  jz      short loc_1800255D7
0x1800255be  call    cs:__imp_GetLastError
0x1800255c4  mov     edi, eax
0x1800255c6  mov     rcx, rsi; hMem
0x1800255c9  call    cs:__imp_LocalFree
0x1800255cf  mov     ecx, edi; dwErrCode
0x1800255d1  call    cs:__imp_SetLastError
0x1800255d7  mov     [r14], rbx
0x1800255da  jmp     short loc_1800255E5
0x1800255dc  mov     rcx, rbx; hMem
0x1800255df  call    cs:__imp_LocalFree
0x1800255e5  xor     eax, eax
0x1800255e7  jmp     short loc_180025618
0x1800255e9  mov     rcx, rbx; hMem
0x1800255ec  call    cs:__imp_LocalFree
0x1800255f2  mov     eax, edi
0x1800255f4  jmp     short loc_180025618
0x1800255f6  mov     edx, 17Ah; void *
0x1800255fb  mov     ebx, 8007000Eh
0x180025600  mov     r9d, ebx; char *
0x180025603  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002560a  mov     rcx, [rbp+188h]; this
0x180025611  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025616  mov     eax, ebx
0x180025618  mov     rcx, [rbp+180h+var_40]
0x18002561f  xor     rcx, rsp; StackCookie
0x180025622  call    __security_check_cookie
0x180025627  mov     rbx, [rsp+280h+arg_10]
0x18002562f  add     rsp, 250h
0x180025636  pop     r15
0x180025638  pop     r14
0x18002563a  pop     r13
0x18002563c  pop     r12
0x18002563e  pop     rdi
0x18002563f  pop     rsi
0x180025640  pop     rbp
0x180025641  retn
```
