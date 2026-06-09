# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)

- ea: `0x180031ed8`
- end: `0x180032052`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ`
- size: `378`
- prototype: `__int64(char *, const wchar_t *, ...)`
- caller_count: `35`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032b74`
- `0x180039edc`
- `0x18003b3f8`
- `0x18003b764`
- `0x18003bf94`
- `0x18003e91c`
- `0x18003f580`
- `0x180040400`
- `0x180041390`
- `0x180044a3c`
- `0x180044cd8`
- `0x1800450bc`
- `0x180045810`
- `0x1800473bc`
- `0x180047780`
- `0x180047b50`
- `0x180048b1c`
- `0x180049a44`
- `0x180049f94`
- `0x18004a334`
- `0x18004a664`
- `0x18004a7a4`
- `0x18004c440`
- `0x18004cfe8`
- `0x18004d360`
- `0x18004d82c`
- `0x18004d950`
- `0x18004ddb4`
- `0x18004e864`
- `0x180051dcc`
- `0x180053324`
- `0x1800557b8`
- `0x180056d60`
- `0x18005d2a8`
- `0x18005d674`

## callees

- `0x18000cfe8`
- `0x180031e78`
- `0x180031ed8`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x180031f0b`
- `msvcrt!_vscwprintf` at `0x180031f0b`
- `msvcrt!_vsnwprintf` at `0x180031f9b`
- `msvcrt!_vsnwprintf` at `0x180031f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003203d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003203d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031fd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031fd9`

## string_xrefs

- `0x180031f51`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180032026`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rdi
  _WORD *v5; // rbx
  __int64 v6; // rdx
  const char *v7; // r9
  char *v8; // rax
  unsigned int v9; // edi
  unsigned __int64 v10; // rsi
  int v11; // eax
  void *v12; // rsi
  DWORD LastError; // edi
  LPVOID pv; // [rsp+20h] [rbp-58h] BYREF
  char v16; // [rsp+28h] [rbp-50h] BYREF
  char v17; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v19; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+90h] [rbp+18h]
  __int64 v21; // [rsp+98h] [rbp+20h]
  va_list va1; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v19 = va_arg(va1, _QWORD);
  v21 = va_arg(va1, _QWORD);
  pv = 0;
  v4 = _vscwprintf(a2, va);
  v5 = 0;
  v8 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                 &pv,
                 v6,
                 v4,
                 v7);
  if ( &v16 != v8 )
  {
    v5 = *(_WORD **)v8;
    *(_QWORD *)v8 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      (int)pv);
    return v9;
  }
  v10 = v4 + 1;
  if ( v4 == -1 )
  {
    v9 = -2147024809;
    if ( !v10 )
    {
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)v9,
        (int)pv);
      CoTaskMemFree(v5);
      return v9;
    }
LABEL_23:
    *v5 = 0;
    goto LABEL_24;
  }
  if ( v10 > 0x7FFFFFFF )
  {
    v9 = -2147024809;
    goto LABEL_23;
  }
  v11 = _vsnwprintf(v5, v4, a2, va);
  if ( v11 < 0 || v11 > v4 )
  {
    v5[v4] = 0;
    v9 = -2147024774;
    if ( (v10 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      *v5 = 0;
    goto LABEL_24;
  }
  if ( v11 == v4 )
    v5[v4] = 0;
  if ( a1 == &v17 )
  {
    CoTaskMemFree(v5);
  }
  else
  {
    v12 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v12);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180031ed8  mov     rax, rsp
0x180031edb  mov     [rax+10h], rdx
0x180031edf  mov     [rax+18h], r8
0x180031ee3  mov     [rax+20h], r9
0x180031ee7  push    rbx
0x180031ee8  push    rbp
0x180031ee9  push    rsi
0x180031eea  push    rdi
0x180031eeb  push    r14
0x180031eed  push    r15
0x180031eef  sub     rsp, 48h
0x180031ef3  mov     rbp, rdx
0x180031ef6  mov     qword ptr [rax-58h], 0
0x180031efe  lea     r15, [rax+18h]
0x180031f02  mov     r14, rcx
0x180031f05  mov     rdx, r15; ArgList
0x180031f08  mov     rcx, rbp; Format
0x180031f0b  call    cs:__imp__vscwprintf
0x180031f11  movsxd  rdi, eax
0x180031f14  lea     rcx, [rsp+78h+pv]
0x180031f19  mov     r8, rdi
0x180031f1c  xor     ebx, ebx
0x180031f1e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180031f23  lea     rcx, [rsp+78h+var_50]
0x180031f28  cmp     rcx, rax
0x180031f2b  jz      short loc_180031F37
0x180031f2d  mov     rbx, [rax]
0x180031f30  mov     qword ptr [rax], 0
0x180031f37  mov     rcx, [rsp+78h+pv]; pv
0x180031f3c  test    rcx, rcx
0x180031f3f  jz      short loc_180031F47
0x180031f41  call    cs:__imp_CoTaskMemFree
0x180031f47  test    rbx, rbx
0x180031f4a  jnz     short loc_180031F6F
0x180031f4c  mov     rcx, [rsp+78h]; this
0x180031f51  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180031f58  mov     edi, 8007000Eh
0x180031f5d  mov     edx, 7CDh; void *
0x180031f62  mov     r9d, edi; char *
0x180031f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031f6a  jmp     loc_180032043
0x180031f6f  lea     rsi, [rdi+1]
0x180031f73  test    rsi, rsi
0x180031f76  jz      loc_180032012
0x180031f7c  cmp     rsi, 7FFFFFFFh
0x180031f83  jbe     short loc_180031F8F
0x180031f85  mov     edi, 80070057h
0x180031f8a  jmp     loc_18003201C
0x180031f8f  mov     r9, r15; Args
0x180031f92  mov     r8, rbp; Format
0x180031f95  mov     rdx, rdi; BufferCount
0x180031f98  mov     rcx, rbx; Buffer
0x180031f9b  call    cs:__imp__vsnwprintf
0x180031fa1  test    eax, eax
0x180031fa3  js      short loc_180031FF1
0x180031fa5  cdqe
0x180031fa7  cmp     rax, rdi
0x180031faa  ja      short loc_180031FF1
0x180031fac  jnz     short loc_180031FB4
0x180031fae  xor     eax, eax
0x180031fb0  mov     [rbx+rdi*2], ax
0x180031fb4  lea     rax, [rsp+78h+var_48]
0x180031fb9  cmp     r14, rax
0x180031fbc  jz      short loc_180031FE4
0x180031fbe  mov     rsi, [r14]
0x180031fc1  test    rsi, rsi
0x180031fc4  jz      short loc_180031FDF
0x180031fc6  call    cs:__imp_GetLastError
0x180031fcc  mov     rcx, rsi; pv
0x180031fcf  mov     edi, eax
0x180031fd1  call    cs:__imp_CoTaskMemFree
0x180031fd7  mov     ecx, edi; dwErrCode
0x180031fd9  call    cs:__imp_SetLastError
0x180031fdf  mov     [r14], rbx
0x180031fe2  jmp     short loc_180031FED
0x180031fe4  mov     rcx, rbx; pv
0x180031fe7  call    cs:__imp_CoTaskMemFree
0x180031fed  xor     edi, edi
0x180031fef  jmp     short loc_180032043
0x180031ff1  xor     eax, eax
0x180031ff3  mov     [rbx+rdi*2], ax
0x180031ff7  mov     rax, 7FFFFFFFFFFFFFFFh
0x180032001  mov     edi, 8007007Ah
0x180032006  test    rax, rsi
0x180032009  jbe     short loc_180032021
0x18003200b  xor     eax, eax
0x18003200d  mov     [rbx], ax
0x180032010  jmp     short loc_180032021
0x180032012  mov     edi, 80070057h
0x180032017  test    rsi, rsi
0x18003201a  jz      short loc_180032021
0x18003201c  xor     ecx, ecx
0x18003201e  mov     [rbx], cx
0x180032021  mov     rcx, [rsp+78h]; this
0x180032026  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003202d  mov     r9d, edi; char *
0x180032030  mov     edx, 7D1h; void *
0x180032035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003203a  mov     rcx, rbx; pv
0x18003203d  call    cs:__imp_CoTaskMemFree
0x180032043  mov     eax, edi
0x180032045  add     rsp, 48h
0x180032049  pop     r15
0x18003204b  pop     r14
0x18003204d  pop     rdi
0x18003204e  pop     rsi
0x18003204f  pop     rbp
0x180032050  pop     rbx
0x180032051  retn
```
