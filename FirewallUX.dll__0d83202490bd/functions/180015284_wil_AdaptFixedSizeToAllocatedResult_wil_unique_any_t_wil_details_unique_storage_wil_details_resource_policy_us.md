# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180015284`
- end: `0x180015474`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017db0`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x180009544`
- `0x18000a938`
- `0x180015284`
- `0x18001a8bc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001540e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153d6`

## string_xrefs

- `0x180015420`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
        char *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  unsigned __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  void *v9; // rbx
  unsigned __int64 v10; // rdi
  __int64 v11; // rcx
  int v12; // esi
  void *v13; // rsi
  DWORD LastError; // edi
  int v15; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 *v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[256]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  pv = 0;
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v18 = &v17;
  v19 = 128;
  v20 = (unsigned __int64 *)v22;
  v4 = *(_QWORD *)(a2 + 112);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  result = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v4 + 32LL))(
             v4,
             &v20,
             &v19,
             &v18);
  if ( (int)result >= 0 )
  {
    v6 = v17;
    if ( v17 > 0x80 )
    {
      while ( 1 )
      {
        v10 = v6;
        v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v6 - 1);
        if ( v7 < 0 )
        {
          v8 = 378;
          goto LABEL_22;
        }
        v20 = &v17;
        v19 = v10;
        v9 = pv;
        v18 = (unsigned __int64 *)pv;
        v11 = *(_QWORD *)(a2 + 112);
        if ( !v11 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v11 + 32LL))(
                v11,
                &v18,
                &v19,
                &v20);
        if ( v12 < 0 )
          break;
        v6 = v17;
        if ( v17 <= v10 )
          goto LABEL_11;
      }
      if ( v9 )
        CoTaskMemFree(v9);
      return (unsigned int)v12;
    }
    else
    {
      v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &pv,
             v22,
             v17 - 1);
      if ( v7 >= 0 )
      {
        v9 = pv;
LABEL_11:
        if ( a1 == &v21 )
        {
          if ( v9 )
            CoTaskMemFree(v9);
        }
        else
        {
          v13 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            LastError = GetLastError();
            CoTaskMemFree(v13);
            SetLastError(LastError);
          }
          *(_QWORD *)a1 = v9;
        }
        return 0;
      }
      else
      {
        v8 = 367;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
          (const char *)(unsigned int)v7,
          v15);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015284  mov     [rsp-8+arg_10], rbx
0x180015289  push    rbp
0x18001528a  push    rsi
0x18001528b  push    rdi
0x18001528c  push    r14
0x18001528e  push    r15
0x180015290  lea     rbp, [rsp-70h]
0x180015295  sub     rsp, 170h
0x18001529c  mov     rax, cs:__security_cookie
0x1800152a3  xor     rax, rsp
0x1800152a6  mov     [rbp+90h+var_30], rax
0x1800152aa  mov     r15, rdx
0x1800152ad  mov     r14, rcx
0x1800152b0  mov     [rsp+190h+pv], 0
0x1800152b9  xor     edx, edx; Val
0x1800152bb  mov     r8d, 100h; Size
0x1800152c1  lea     rcx, [rsp+190h+var_130]; void *
0x1800152c6  call    memset_0
0x1800152cb  mov     [rsp+190h+var_158], 0
0x1800152d4  lea     rax, [rsp+190h+var_158]
0x1800152d9  mov     [rsp+190h+var_150], rax
0x1800152de  mov     ebx, 80h
0x1800152e3  mov     [rsp+190h+var_148], rbx
0x1800152e8  lea     rax, [rsp+190h+var_130]
0x1800152ed  mov     [rsp+190h+var_140], rax
0x1800152f2  mov     rcx, [r15+70h]; this
0x1800152f6  test    rcx, rcx
0x1800152f9  jz      loc_18001546E
0x1800152ff  mov     rax, [rcx]
0x180015302  lea     r9, [rsp+190h+var_150]
0x180015307  lea     r8, [rsp+190h+var_148]
0x18001530c  lea     rdx, [rsp+190h+var_140]
0x180015311  mov     rax, [rax+20h]
0x180015315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001531a  test    eax, eax
0x18001531c  js      loc_180015445
0x180015322  mov     rax, [rsp+190h+var_158]
0x180015327  cmp     rax, rbx
0x18001532a  ja      short loc_180015356
0x18001532c  lea     r8, [rax-1]
0x180015330  lea     rdx, [rsp+190h+var_130]
0x180015335  lea     rcx, [rsp+190h+pv]
0x18001533a  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18001533f  mov     ebx, eax
0x180015341  test    eax, eax
0x180015343  jns     short loc_18001534F
0x180015345  mov     edx, 16Fh
0x18001534a  jmp     loc_18001541D
0x18001534f  mov     rbx, [rsp+190h+pv]
0x180015354  jmp     short loc_1800153C4
0x180015356  mov     rdi, rax
0x180015359  lea     r8, [rax-1]
0x18001535d  xor     edx, edx
0x18001535f  lea     rcx, [rsp+190h+pv]
0x180015364  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180015369  mov     ebx, eax
0x18001536b  test    eax, eax
0x18001536d  js      loc_180015418
0x180015373  lea     rax, [rsp+190h+var_158]
0x180015378  mov     [rsp+190h+var_140], rax
0x18001537d  mov     [rsp+190h+var_148], rdi
0x180015382  mov     rbx, [rsp+190h+pv]
0x180015387  mov     [rsp+190h+var_150], rbx
0x18001538c  mov     rcx, [r15+70h]; this
0x180015390  test    rcx, rcx
0x180015393  jz      loc_180015468
0x180015399  mov     rax, [rcx]
0x18001539c  lea     r9, [rsp+190h+var_140]
0x1800153a1  lea     r8, [rsp+190h+var_148]
0x1800153a6  lea     rdx, [rsp+190h+var_150]
0x1800153ab  mov     rax, [rax+20h]
0x1800153af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153b4  mov     esi, eax
0x1800153b6  test    eax, eax
0x1800153b8  js      short loc_180015406
0x1800153ba  mov     rax, [rsp+190h+var_158]
0x1800153bf  cmp     rax, rdi
0x1800153c2  ja      short loc_180015356
0x1800153c4  lea     rax, [rsp+190h+var_138]
0x1800153c9  cmp     r14, rax
0x1800153cc  jz      short loc_1800153F4
0x1800153ce  mov     rsi, [r14]
0x1800153d1  test    rsi, rsi
0x1800153d4  jz      short loc_1800153EF
0x1800153d6  call    cs:__imp_GetLastError
0x1800153dc  mov     edi, eax
0x1800153de  mov     rcx, rsi; pv
0x1800153e1  call    cs:__imp_CoTaskMemFree
0x1800153e7  mov     ecx, edi; dwErrCode
0x1800153e9  call    cs:__imp_SetLastError
0x1800153ef  mov     [r14], rbx
0x1800153f2  jmp     short loc_180015402
0x1800153f4  test    rbx, rbx
0x1800153f7  jz      short loc_180015402
0x1800153f9  mov     rcx, rbx; pv
0x1800153fc  call    cs:__imp_CoTaskMemFree
0x180015402  xor     eax, eax
0x180015404  jmp     short loc_180015445
0x180015406  test    rbx, rbx
0x180015409  jz      short loc_180015414
0x18001540b  mov     rcx, rbx; pv
0x18001540e  call    cs:__imp_CoTaskMemFree
0x180015414  mov     eax, esi
0x180015416  jmp     short loc_180015445
0x180015418  mov     edx, 17Ah; void *
0x18001541d  mov     r9d, ebx; char *
0x180015420  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015427  mov     rcx, [rbp+98h]; this
0x18001542e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015433  mov     rcx, [rsp+190h+pv]; pv
0x180015438  test    rcx, rcx
0x18001543b  jz      short loc_180015443
0x18001543d  call    cs:__imp_CoTaskMemFree
0x180015443  mov     eax, ebx
0x180015445  mov     rcx, [rbp+90h+var_30]
0x180015449  xor     rcx, rsp; StackCookie
0x18001544c  call    __security_check_cookie
0x180015451  mov     rbx, [rsp+190h+arg_10]
0x180015459  add     rsp, 170h
0x180015460  pop     r15
0x180015462  pop     r14
0x180015464  pop     rdi
0x180015465  pop     rsi
0x180015466  pop     rbp
0x180015467  retn
0x180015468  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001546e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
