# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)

- ea: `0x180034d7c`
- end: `0x180034f27`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ`
- size: `427`
- prototype: ``
- caller_count: `35`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035b2c`
- `0x18003d52c`
- `0x18003ead0`
- `0x18003ee78`
- `0x18003f6f8`
- `0x1800422cc`
- `0x180043000`
- `0x180043fb4`
- `0x18004501c`
- `0x180048920`
- `0x180048bd8`
- `0x180048fe8`
- `0x1800497a4`
- `0x18004b408`
- `0x18004b7d4`
- `0x18004bbc4`
- `0x18004cbe4`
- `0x18004db50`
- `0x18004e0e0`
- `0x18004e4b0`
- `0x18004e7f4`
- `0x18004e944`
- `0x1800506a4`
- `0x18005125c`
- `0x1800515f0`
- `0x180051ae0`
- `0x180051c10`
- `0x18005207c`
- `0x180052b48`
- `0x1800561b8`
- `0x180057830`
- `0x180059d58`
- `0x18005b444`
- `0x180061eb8`
- `0x1800622c0`

## callees

- `0x18000d3dc`
- `0x180034d14`
- `0x180034d7c`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x180034daf`
- `msvcrt!_vscwprintf` at `0x180034daf`
- `msvcrt!_vsnwprintf` at `0x180034e4b`
- `msvcrt!_vsnwprintf` at `0x180034e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034eaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034eaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034e9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034e9b`

## string_xrefs

- `0x180034e01`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034ef4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        ...)
{
  size_t v4; // rdi
  _WORD *v5; // rbx
  __int64 v6; // rdx
  char *v7; // rax
  unsigned int v8; // edi
  unsigned __int64 v9; // rsi
  int v10; // eax
  void *v11; // rsi
  DWORD LastError; // edi
  LPVOID pv; // [rsp+20h] [rbp-58h] BYREF
  char v15; // [rsp+28h] [rbp-50h] BYREF
  char v16; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  pv = 0;
  v4 = _vscwprintf(a2, va);
  v5 = 0;
  v7 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                 &pv,
                 v6,
                 v4);
  if ( &v15 != v7 )
  {
    v5 = *(_WORD **)v7;
    *(_QWORD *)v7 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      (int)pv);
    return v8;
  }
  v9 = v4 + 1;
  if ( v4 == -1 )
  {
    v8 = -2147024809;
    if ( !v9 )
    {
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)v8,
        (int)pv);
      CoTaskMemFree(v5);
      return v8;
    }
LABEL_23:
    *v5 = 0;
    goto LABEL_24;
  }
  if ( v9 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
    goto LABEL_23;
  }
  v10 = _vsnwprintf(v5, v4, a2, va);
  if ( v10 < 0 || v10 > v4 )
  {
    v5[v4] = 0;
    v8 = -2147024774;
    if ( (v9 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      *v5 = 0;
    goto LABEL_24;
  }
  if ( v10 == v4 )
    v5[v4] = 0;
  if ( a1 == &v16 )
  {
    CoTaskMemFree(v5);
  }
  else
  {
    v11 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v11);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180034d7c  mov     rax, rsp
0x180034d7f  mov     [rax+10h], rdx
0x180034d83  mov     [rax+18h], r8
0x180034d87  mov     [rax+20h], r9
0x180034d8b  push    rbx
0x180034d8c  push    rbp
0x180034d8d  push    rsi
0x180034d8e  push    rdi
0x180034d8f  push    r14
0x180034d91  push    r15
0x180034d93  sub     rsp, 48h
0x180034d97  mov     rbp, rdx
0x180034d9a  mov     qword ptr [rax-58h], 0
0x180034da2  lea     r15, [rax+18h]
0x180034da6  mov     r14, rcx
0x180034da9  mov     rdx, r15; ArgList
0x180034dac  mov     rcx, rbp; Format
0x180034daf  call    cs:__imp__vscwprintf
0x180034db6  nop     dword ptr [rax+rax+00h]
0x180034dbb  movsxd  rdi, eax
0x180034dbe  lea     rcx, [rsp+78h+pv]
0x180034dc3  mov     r8, rdi
0x180034dc6  xor     ebx, ebx
0x180034dc8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180034dcd  lea     rcx, [rsp+78h+var_50]
0x180034dd2  cmp     rcx, rax
0x180034dd5  jz      short loc_180034DE1
0x180034dd7  mov     rbx, [rax]
0x180034dda  mov     qword ptr [rax], 0
0x180034de1  mov     rcx, [rsp+78h+pv]; pv
0x180034de6  test    rcx, rcx
0x180034de9  jz      short loc_180034DF7
0x180034deb  call    cs:__imp_CoTaskMemFree
0x180034df2  nop     dword ptr [rax+rax+00h]
0x180034df7  test    rbx, rbx
0x180034dfa  jnz     short loc_180034E1F
0x180034dfc  mov     rcx, [rsp+78h]; this
0x180034e01  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034e08  mov     edi, 8007000Eh
0x180034e0d  mov     edx, 7CDh; void *
0x180034e12  mov     r9d, edi; char *
0x180034e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e1a  jmp     loc_180034F17
0x180034e1f  lea     rsi, [rdi+1]
0x180034e23  test    rsi, rsi
0x180034e26  jz      loc_180034EE0
0x180034e2c  cmp     rsi, 7FFFFFFFh
0x180034e33  jbe     short loc_180034E3F
0x180034e35  mov     edi, 80070057h
0x180034e3a  jmp     loc_180034EEA
0x180034e3f  mov     r9, r15; Args
0x180034e42  mov     r8, rbp; Format
0x180034e45  mov     rdx, rdi; BufferCount
0x180034e48  mov     rcx, rbx; Buffer
0x180034e4b  call    cs:__imp__vsnwprintf
0x180034e52  nop     dword ptr [rax+rax+00h]
0x180034e57  test    eax, eax
0x180034e59  js      short loc_180034EBF
0x180034e5b  cdqe
0x180034e5d  cmp     rax, rdi
0x180034e60  ja      short loc_180034EBF
0x180034e62  jnz     short loc_180034E6A
0x180034e64  xor     eax, eax
0x180034e66  mov     [rbx+rdi*2], ax
0x180034e6a  lea     rax, [rsp+78h+var_48]
0x180034e6f  cmp     r14, rax
0x180034e72  jz      short loc_180034EAC
0x180034e74  mov     rsi, [r14]
0x180034e77  test    rsi, rsi
0x180034e7a  jz      short loc_180034EA7
0x180034e7c  call    cs:__imp_GetLastError
0x180034e83  nop     dword ptr [rax+rax+00h]
0x180034e88  mov     rcx, rsi; pv
0x180034e8b  mov     edi, eax
0x180034e8d  call    cs:__imp_CoTaskMemFree
0x180034e94  nop     dword ptr [rax+rax+00h]
0x180034e99  mov     ecx, edi; dwErrCode
0x180034e9b  call    cs:__imp_SetLastError
0x180034ea2  nop     dword ptr [rax+rax+00h]
0x180034ea7  mov     [r14], rbx
0x180034eaa  jmp     short loc_180034EBB
0x180034eac  mov     rcx, rbx; pv
0x180034eaf  call    cs:__imp_CoTaskMemFree
0x180034eb6  nop     dword ptr [rax+rax+00h]
0x180034ebb  xor     edi, edi
0x180034ebd  jmp     short loc_180034F17
0x180034ebf  xor     eax, eax
0x180034ec1  mov     [rbx+rdi*2], ax
0x180034ec5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180034ecf  mov     edi, 8007007Ah
0x180034ed4  test    rax, rsi
0x180034ed7  jbe     short loc_180034EEF
0x180034ed9  xor     eax, eax
0x180034edb  mov     [rbx], ax
0x180034ede  jmp     short loc_180034EEF
0x180034ee0  mov     edi, 80070057h
0x180034ee5  test    rsi, rsi
0x180034ee8  jz      short loc_180034EEF
0x180034eea  xor     ecx, ecx
0x180034eec  mov     [rbx], cx
0x180034eef  mov     rcx, [rsp+78h]; this
0x180034ef4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034efb  mov     r9d, edi; char *
0x180034efe  mov     edx, 7D1h; void *
0x180034f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034f08  mov     rcx, rbx; pv
0x180034f0b  call    cs:__imp_CoTaskMemFree
0x180034f12  nop     dword ptr [rax+rax+00h]
0x180034f17  mov     eax, edi
0x180034f19  add     rsp, 48h
0x180034f1d  pop     r15
0x180034f1f  pop     r14
0x180034f21  pop     rdi
0x180034f22  pop     rsi
0x180034f23  pop     rbp
0x180034f24  pop     rbx
0x180034f25  retn
```
