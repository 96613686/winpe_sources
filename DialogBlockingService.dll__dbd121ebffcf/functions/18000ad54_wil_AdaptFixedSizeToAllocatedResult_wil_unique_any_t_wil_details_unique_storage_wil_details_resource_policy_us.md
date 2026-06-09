# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18000ad54`
- end: `0x18000af9f`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b680`

## callees

- `0x180001620`
- `0x1800020d0`
- `0x180006804`
- `0x180007d0c`
- `0x18000ad54`
- `0x18000b020`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0f`

## string_xrefs

- `0x18000af54`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  void *v6; // rbx
  unsigned __int64 v7; // rax
  char *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 *v10; // r15
  char *v11; // rsi
  void *v12; // r12
  DWORD LastError; // edi
  __int64 v14; // rcx
  int v15; // edi
  void *v16; // rsi
  DWORD v17; // edi
  int v18; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  char v23; // [rsp+50h] [rbp-B0h] BYREF
  void *v24; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[512]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset_0(v26, 0, sizeof(v26));
  v20 = 0;
  v21 = &v20;
  v22 = 256;
  pv = v26;
  v4 = *(_QWORD *)(a2 + 112);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  result = (*(__int64 (__fastcall **)(__int64, LPVOID *, __int64 *, unsigned __int64 **))(*(_QWORD *)v4 + 32LL))(
             v4,
             &pv,
             &v22,
             &v21);
  if ( (int)result >= 0 )
  {
    v6 = 0;
    v7 = v20;
    if ( v20 > 0x100 )
    {
      while ( 1 )
      {
        v10 = (unsigned __int64 *)v7;
        v11 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &pv,
                        0,
                        v7 - 1);
        if ( &v23 != v11 )
        {
          v12 = *(void **)v11;
          if ( v6 )
          {
            LastError = GetLastError();
            CoTaskMemFree(v6);
            SetLastError(LastError);
          }
          v6 = v12;
          *(_QWORD *)v11 = 0;
        }
        if ( pv )
          CoTaskMemFree(pv);
        if ( !v6 )
          break;
        v22 = (__int64)&v20;
        v21 = v10;
        v24 = v6;
        v14 = *(_QWORD *)(a2 + 112);
        if ( !v14 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v15 = (*(__int64 (__fastcall **)(__int64, void **, unsigned __int64 **, __int64 *))(*(_QWORD *)v14 + 32LL))(
                v14,
                &v24,
                &v21,
                &v22);
        if ( v15 < 0 )
        {
          CoTaskMemFree(v6);
          return (unsigned int)v15;
        }
        v7 = v20;
        if ( v20 <= (unsigned __int64)v10 )
          goto LABEL_20;
      }
      v9 = 378;
      goto LABEL_28;
    }
    v8 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                   &pv,
                   v26,
                   v20 - 1);
    if ( &v23 != v8 )
    {
      v6 = *(void **)v8;
      *(_QWORD *)v8 = 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v6 )
    {
      v9 = 367;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)0x8007000ELL,
        v18);
      return 2147942414LL;
    }
LABEL_20:
    if ( a1 == &v25 )
    {
      CoTaskMemFree(v6);
    }
    else
    {
      v16 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        v17 = GetLastError();
        CoTaskMemFree(v16);
        SetLastError(v17);
      }
      *(_QWORD *)a1 = v6;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad54  mov     [rsp-8+arg_10], rbx
0x18000ad59  push    rbp
0x18000ad5a  push    rsi
0x18000ad5b  push    rdi
0x18000ad5c  push    r12
0x18000ad5e  push    r13
0x18000ad60  push    r14
0x18000ad62  push    r15
0x18000ad64  lea     rbp, [rsp-180h]
0x18000ad6c  sub     rsp, 280h
0x18000ad73  mov     rax, cs:__security_cookie
0x18000ad7a  xor     rax, rsp
0x18000ad7d  mov     [rbp+1B0h+var_40], rax
0x18000ad84  mov     r13, rdx
0x18000ad87  mov     r14, rcx
0x18000ad8a  xor     edx, edx; Val
0x18000ad8c  mov     r8d, 200h; Size
0x18000ad92  lea     rcx, [rsp+2B0h+var_240]; void *
0x18000ad97  call    memset_0
0x18000ad9c  mov     [rsp+2B0h+var_278], 0
0x18000ada5  lea     rax, [rsp+2B0h+var_278]
0x18000adaa  mov     [rsp+2B0h+var_270], rax
0x18000adaf  mov     edi, 100h
0x18000adb4  mov     [rsp+2B0h+var_268], rdi
0x18000adb9  lea     rax, [rsp+2B0h+var_240]
0x18000adbe  mov     [rsp+2B0h+pv], rax
0x18000adc3  mov     rcx, [r13+70h]; this
0x18000adc7  test    rcx, rcx
0x18000adca  jz      loc_18000AF99
0x18000add0  mov     rax, [rcx]
0x18000add3  lea     r9, [rsp+2B0h+var_270]
0x18000add8  lea     r8, [rsp+2B0h+var_268]
0x18000addd  lea     rdx, [rsp+2B0h+pv]
0x18000ade2  mov     rax, [rax+20h]
0x18000ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adeb  test    eax, eax
0x18000aded  js      loc_18000AF69
0x18000adf3  xor     ebx, ebx
0x18000adf5  mov     rax, [rsp+2B0h+var_278]
0x18000adfa  cmp     rax, rdi
0x18000adfd  ja      short loc_18000AE49
0x18000adff  lea     r8, [rax-1]
0x18000ae03  lea     rdx, [rsp+2B0h+var_240]
0x18000ae08  lea     rcx, [rsp+2B0h+pv]
0x18000ae0d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000ae12  lea     rcx, [rsp+2B0h+var_260]
0x18000ae17  cmp     rcx, rax
0x18000ae1a  jz      short loc_18000AE26
0x18000ae1c  mov     rbx, [rax]
0x18000ae1f  mov     qword ptr [rax], 0
0x18000ae26  mov     rcx, [rsp+2B0h+pv]; pv
0x18000ae2b  test    rcx, rcx
0x18000ae2e  jz      short loc_18000AE36
0x18000ae30  call    cs:__imp_CoTaskMemFree
0x18000ae36  test    rbx, rbx
0x18000ae39  jnz     loc_18000AEFD
0x18000ae3f  mov     edx, 16Fh
0x18000ae44  jmp     loc_18000AF4C
0x18000ae49  mov     r15, rax
0x18000ae4c  lea     r8, [rax-1]
0x18000ae50  xor     edx, edx
0x18000ae52  lea     rcx, [rsp+2B0h+pv]
0x18000ae57  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000ae5c  mov     rsi, rax
0x18000ae5f  lea     rax, [rsp+2B0h+var_260]
0x18000ae64  cmp     rax, rsi
0x18000ae67  jz      short loc_18000AE94
0x18000ae69  mov     r12, [rsi]
0x18000ae6c  test    rbx, rbx
0x18000ae6f  jz      short loc_18000AE8A
0x18000ae71  call    cs:__imp_GetLastError
0x18000ae77  mov     edi, eax
0x18000ae79  mov     rcx, rbx; pv
0x18000ae7c  call    cs:__imp_CoTaskMemFree
0x18000ae82  mov     ecx, edi; dwErrCode
0x18000ae84  call    cs:__imp_SetLastError
0x18000ae8a  mov     rbx, r12
0x18000ae8d  mov     qword ptr [rsi], 0
0x18000ae94  mov     rcx, [rsp+2B0h+pv]; pv
0x18000ae99  test    rcx, rcx
0x18000ae9c  jz      short loc_18000AEA4
0x18000ae9e  call    cs:__imp_CoTaskMemFree
0x18000aea4  test    rbx, rbx
0x18000aea7  jz      loc_18000AF47
0x18000aead  lea     rax, [rsp+2B0h+var_278]
0x18000aeb2  mov     [rsp+2B0h+var_268], rax
0x18000aeb7  mov     [rsp+2B0h+var_270], r15
0x18000aebc  mov     [rsp+2B0h+var_258], rbx
0x18000aec1  mov     rcx, [r13+70h]; this
0x18000aec5  test    rcx, rcx
0x18000aec8  jz      loc_18000AF93
0x18000aece  mov     rax, [rcx]
0x18000aed1  lea     r9, [rsp+2B0h+var_268]
0x18000aed6  lea     r8, [rsp+2B0h+var_270]
0x18000aedb  lea     rdx, [rsp+2B0h+var_258]
0x18000aee0  mov     rax, [rax+20h]
0x18000aee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee9  mov     edi, eax
0x18000aeeb  test    eax, eax
0x18000aeed  js      short loc_18000AF3A
0x18000aeef  mov     rax, [rsp+2B0h+var_278]
0x18000aef4  cmp     rax, r15
0x18000aef7  ja      loc_18000AE49
0x18000aefd  lea     rax, [rsp+2B0h+var_250]
0x18000af02  cmp     r14, rax
0x18000af05  jz      short loc_18000AF2D
0x18000af07  mov     rsi, [r14]
0x18000af0a  test    rsi, rsi
0x18000af0d  jz      short loc_18000AF28
0x18000af0f  call    cs:__imp_GetLastError
0x18000af15  mov     edi, eax
0x18000af17  mov     rcx, rsi; pv
0x18000af1a  call    cs:__imp_CoTaskMemFree
0x18000af20  mov     ecx, edi; dwErrCode
0x18000af22  call    cs:__imp_SetLastError
0x18000af28  mov     [r14], rbx
0x18000af2b  jmp     short loc_18000AF36
0x18000af2d  mov     rcx, rbx; pv
0x18000af30  call    cs:__imp_CoTaskMemFree
0x18000af36  xor     eax, eax
0x18000af38  jmp     short loc_18000AF69
0x18000af3a  mov     rcx, rbx; pv
0x18000af3d  call    cs:__imp_CoTaskMemFree
0x18000af43  mov     eax, edi
0x18000af45  jmp     short loc_18000AF69
0x18000af47  mov     edx, 17Ah; void *
0x18000af4c  mov     ebx, 8007000Eh
0x18000af51  mov     r9d, ebx; char *
0x18000af54  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000af5b  mov     rcx, [rbp+1B8h]; this
0x18000af62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af67  mov     eax, ebx
0x18000af69  mov     rcx, [rbp+1B0h+var_40]
0x18000af70  xor     rcx, rsp; StackCookie
0x18000af73  call    __security_check_cookie
0x18000af78  mov     rbx, [rsp+2B0h+arg_10]
0x18000af80  add     rsp, 280h
0x18000af87  pop     r15
0x18000af89  pop     r14
0x18000af8b  pop     r13
0x18000af8d  pop     r12
0x18000af8f  pop     rdi
0x18000af90  pop     rsi
0x18000af91  pop     rbp
0x18000af92  retn
0x18000af93  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000af99  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
