# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180025648`
- end: `0x18002582e`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029348`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18000ab14`
- `0x18001233c`
- `0x180025648`
- `0x180028c18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002574c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002574c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800256f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800256f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800257d8`

## string_xrefs

- `0x1800257ef`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
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
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
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
        v10 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &pv,
                        0,
                        v6 - 1);
        if ( &v18 != v10 )
        {
          v11 = *(void **)v10;
          if ( v5 )
          {
            LastError = GetLastError();
            CoTaskMemFree(v5);
            SetLastError(LastError);
          }
          v5 = v11;
          *(_QWORD *)v10 = 0;
        }
        if ( pv )
          CoTaskMemFree(pv);
        if ( !v5 )
          break;
        v13 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v5, v9, v16);
        if ( v13 < 0 )
        {
          CoTaskMemFree(v5);
          return (unsigned int)v13;
        }
        v6 = *(_QWORD *)v16;
        if ( *(_QWORD *)v16 <= v9 )
          goto LABEL_18;
      }
      v8 = 378;
      goto LABEL_26;
    }
    v7 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                   &pv,
                   v20,
                   *(_QWORD *)v16 - 1LL);
    if ( &v18 != v7 )
    {
      v5 = *(void **)v7;
      *(_QWORD *)v7 = 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
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
      CoTaskMemFree(v5);
    }
    else
    {
      v14 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        v15 = GetLastError();
        CoTaskMemFree(v14);
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
0x180025648  mov     [rsp-8+arg_10], rbx
0x18002564d  push    rbp
0x18002564e  push    rsi
0x18002564f  push    rdi
0x180025650  push    r12
0x180025652  push    r13
0x180025654  push    r14
0x180025656  push    r15
0x180025658  lea     rbp, [rsp-150h]
0x180025660  sub     rsp, 250h
0x180025667  mov     rax, cs:__security_cookie
0x18002566e  xor     rax, rsp
0x180025671  mov     [rbp+180h+var_40], rax
0x180025678  mov     r13, rdx
0x18002567b  mov     r14, rcx
0x18002567e  xor     edx, edx; Val
0x180025680  mov     r8d, 200h; Size
0x180025686  lea     rcx, [rsp+280h+var_240]; void *
0x18002568b  call    memset_0
0x180025690  mov     qword ptr [rsp+280h+var_260], 0; int
0x180025699  lea     r9, [rsp+280h+var_260]
0x18002569e  mov     edi, 100h
0x1800256a3  mov     r8d, edi
0x1800256a6  lea     rdx, [rsp+280h+var_240]
0x1800256ab  mov     rcx, r13
0x1800256ae  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800256b3  test    eax, eax
0x1800256b5  js      loc_180025804
0x1800256bb  xor     ebx, ebx
0x1800256bd  mov     rax, qword ptr [rsp+280h+var_260]
0x1800256c2  cmp     rax, rdi
0x1800256c5  ja      short loc_180025711
0x1800256c7  lea     r8, [rax-1]
0x1800256cb  lea     rdx, [rsp+280h+var_240]
0x1800256d0  lea     rcx, [rsp+280h+pv]
0x1800256d5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800256da  lea     rcx, [rsp+280h+var_250]
0x1800256df  cmp     rcx, rax
0x1800256e2  jz      short loc_1800256EE
0x1800256e4  mov     rbx, [rax]
0x1800256e7  mov     qword ptr [rax], 0
0x1800256ee  mov     rcx, [rsp+280h+pv]; pv
0x1800256f3  test    rcx, rcx
0x1800256f6  jz      short loc_1800256FE
0x1800256f8  call    cs:__imp_CoTaskMemFree
0x1800256fe  test    rbx, rbx
0x180025701  jnz     loc_180025798
0x180025707  mov     edx, 16Fh
0x18002570c  jmp     loc_1800257E7
0x180025711  mov     r15, rax
0x180025714  lea     r8, [rax-1]
0x180025718  xor     edx, edx
0x18002571a  lea     rcx, [rsp+280h+pv]
0x18002571f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180025724  mov     rsi, rax
0x180025727  lea     rax, [rsp+280h+var_250]
0x18002572c  cmp     rax, rsi
0x18002572f  jz      short loc_18002575C
0x180025731  mov     r12, [rsi]
0x180025734  test    rbx, rbx
0x180025737  jz      short loc_180025752
0x180025739  call    cs:__imp_GetLastError
0x18002573f  mov     edi, eax
0x180025741  mov     rcx, rbx; pv
0x180025744  call    cs:__imp_CoTaskMemFree
0x18002574a  mov     ecx, edi; dwErrCode
0x18002574c  call    cs:__imp_SetLastError
0x180025752  mov     rbx, r12
0x180025755  mov     qword ptr [rsi], 0
0x18002575c  mov     rcx, [rsp+280h+pv]; pv
0x180025761  test    rcx, rcx
0x180025764  jz      short loc_18002576C
0x180025766  call    cs:__imp_CoTaskMemFree
0x18002576c  test    rbx, rbx
0x18002576f  jz      short loc_1800257E2
0x180025771  lea     r9, [rsp+280h+var_260]
0x180025776  mov     r8, r15
0x180025779  mov     rdx, rbx
0x18002577c  mov     rcx, r13
0x18002577f  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180025784  mov     edi, eax
0x180025786  test    eax, eax
0x180025788  js      short loc_1800257D5
0x18002578a  mov     rax, qword ptr [rsp+280h+var_260]
0x18002578f  cmp     rax, r15
0x180025792  ja      loc_180025711
0x180025798  lea     rax, [rsp+280h+var_248]
0x18002579d  cmp     r14, rax
0x1800257a0  jz      short loc_1800257C8
0x1800257a2  mov     rsi, [r14]
0x1800257a5  test    rsi, rsi
0x1800257a8  jz      short loc_1800257C3
0x1800257aa  call    cs:__imp_GetLastError
0x1800257b0  mov     edi, eax
0x1800257b2  mov     rcx, rsi; pv
0x1800257b5  call    cs:__imp_CoTaskMemFree
0x1800257bb  mov     ecx, edi; dwErrCode
0x1800257bd  call    cs:__imp_SetLastError
0x1800257c3  mov     [r14], rbx
0x1800257c6  jmp     short loc_1800257D1
0x1800257c8  mov     rcx, rbx; pv
0x1800257cb  call    cs:__imp_CoTaskMemFree
0x1800257d1  xor     eax, eax
0x1800257d3  jmp     short loc_180025804
0x1800257d5  mov     rcx, rbx; pv
0x1800257d8  call    cs:__imp_CoTaskMemFree
0x1800257de  mov     eax, edi
0x1800257e0  jmp     short loc_180025804
0x1800257e2  mov     edx, 17Ah; void *
0x1800257e7  mov     ebx, 8007000Eh
0x1800257ec  mov     r9d, ebx; char *
0x1800257ef  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800257f6  mov     rcx, [rbp+188h]; this
0x1800257fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025802  mov     eax, ebx
0x180025804  mov     rcx, [rbp+180h+var_40]
0x18002580b  xor     rcx, rsp; StackCookie
0x18002580e  call    __security_check_cookie
0x180025813  mov     rbx, [rsp+280h+arg_10]
0x18002581b  add     rsp, 250h
0x180025822  pop     r15
0x180025824  pop     r14
0x180025826  pop     r13
0x180025828  pop     r12
0x18002582a  pop     rdi
0x18002582b  pop     rsi
0x18002582c  pop     rbp
0x18002582d  retn
```
