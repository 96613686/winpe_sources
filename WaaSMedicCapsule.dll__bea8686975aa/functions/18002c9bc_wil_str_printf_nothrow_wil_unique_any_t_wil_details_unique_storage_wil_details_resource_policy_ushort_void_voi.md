# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)

- ea: `0x18002c9bc`
- end: `0x18002cb31`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ceac`
- `0x18003f550`

## callees

- `0x180004720`
- `0x180004774`
- `0x180009a54`
- `0x18002c9bc`
- `0x18002dd7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002caa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002caa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cb1a`

## string_xrefs

- `0x18002ca1c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002cafe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        ...)
{
  size_t v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  wchar_t *v7; // rcx
  wchar_t *v8; // rdi
  unsigned __int64 v9; // rbp
  int v10; // eax
  void *v11; // rsi
  DWORD LastError; // ebx
  wchar_t *Buffer; // [rsp+20h] [rbp-48h] BYREF
  char v15; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  v4 = vscwprintf(a2, va);
  Buffer = 0;
  v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &Buffer,
         0,
         v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v5,
      (int)Buffer);
    v7 = Buffer;
    if ( Buffer )
      goto LABEL_24;
    return v6;
  }
  v8 = Buffer;
  v9 = v4 + 1;
  if ( v4 == -1 )
  {
    v6 = -2147024809;
  }
  else
  {
    if ( v9 <= 0x7FFFFFFF )
    {
      v10 = vsnwprintf(Buffer, v4, a2, va);
      if ( v10 >= 0 && v10 <= v4 )
      {
        if ( v10 == v4 )
          v8[v4] = 0;
        if ( a1 == &v15 )
        {
          if ( v8 )
            CoTaskMemFree(v8);
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
          *(_QWORD *)a1 = v8;
        }
        return 0;
      }
      v6 = -2147024774;
      v8[v4] = 0;
      if ( (v9 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
        goto LABEL_22;
    }
    else
    {
      v6 = -2147024809;
    }
    *v8 = 0;
  }
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7D1,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)v6,
    (int)Buffer);
  if ( v8 )
  {
    v7 = v8;
LABEL_24:
    CoTaskMemFree(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18002c9bc  mov     rax, rsp
0x18002c9bf  mov     [rax+10h], rdx
0x18002c9c3  mov     [rax+18h], r8
0x18002c9c7  mov     [rax+20h], r9
0x18002c9cb  push    rbx
0x18002c9cc  push    rbp
0x18002c9cd  push    rsi
0x18002c9ce  push    rdi
0x18002c9cf  push    r12
0x18002c9d1  push    r14
0x18002c9d3  push    r15
0x18002c9d5  sub     rsp, 30h
0x18002c9d9  mov     r15, rdx
0x18002c9dc  mov     qword ptr [rax-48h], 0
0x18002c9e4  lea     r12, [rax+18h]
0x18002c9e8  mov     r14, rcx
0x18002c9eb  mov     rdx, r12; ArgList
0x18002c9ee  mov     rcx, r15; Format
0x18002c9f1  call    _vscwprintf
0x18002c9f6  movsxd  rsi, eax
0x18002c9f9  lea     rcx, [rsp+68h+Buffer]
0x18002c9fe  mov     r8, rsi
0x18002ca01  mov     [rsp+68h+Buffer], 0; int
0x18002ca0a  xor     edx, edx
0x18002ca0c  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18002ca11  mov     ebx, eax
0x18002ca13  test    eax, eax
0x18002ca15  jns     short loc_18002CA43
0x18002ca17  mov     rcx, [rsp+68h]; this
0x18002ca1c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ca23  mov     r9d, eax; char *
0x18002ca26  mov     edx, 7CDh; void *
0x18002ca2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca30  mov     rcx, [rsp+68h+Buffer]
0x18002ca35  test    rcx, rcx
0x18002ca38  jz      loc_18002CB20
0x18002ca3e  jmp     loc_18002CB1A
0x18002ca43  mov     rdi, [rsp+68h+Buffer]
0x18002ca48  lea     rbp, [rsi+1]
0x18002ca4c  test    rbp, rbp
0x18002ca4f  jz      loc_18002CAEA
0x18002ca55  cmp     rbp, 7FFFFFFFh
0x18002ca5c  jbe     short loc_18002CA68
0x18002ca5e  mov     ebx, 80070057h
0x18002ca63  jmp     loc_18002CAF4
0x18002ca68  mov     r9, r12; Args
0x18002ca6b  mov     r8, r15; Format
0x18002ca6e  mov     rdx, rsi; BufferCount
0x18002ca71  mov     rcx, rdi; Buffer
0x18002ca74  call    _vsnwprintf
0x18002ca79  test    eax, eax
0x18002ca7b  js      short loc_18002CACE
0x18002ca7d  cdqe
0x18002ca7f  cmp     rax, rsi
0x18002ca82  ja      short loc_18002CACE
0x18002ca84  jnz     short loc_18002CA8C
0x18002ca86  xor     eax, eax
0x18002ca88  mov     [rdi+rsi*2], ax
0x18002ca8c  lea     rax, [rsp+68h+var_40]
0x18002ca91  cmp     r14, rax
0x18002ca94  jz      short loc_18002CABC
0x18002ca96  mov     rsi, [r14]
0x18002ca99  test    rsi, rsi
0x18002ca9c  jz      short loc_18002CAB7
0x18002ca9e  call    cs:__imp_GetLastError
0x18002caa4  mov     rcx, rsi; pv
0x18002caa7  mov     ebx, eax
0x18002caa9  call    cs:__imp_CoTaskMemFree
0x18002caaf  mov     ecx, ebx; dwErrCode
0x18002cab1  call    cs:__imp_SetLastError
0x18002cab7  mov     [r14], rdi
0x18002caba  jmp     short loc_18002CACA
0x18002cabc  test    rdi, rdi
0x18002cabf  jz      short loc_18002CACA
0x18002cac1  mov     rcx, rdi; pv
0x18002cac4  call    cs:__imp_CoTaskMemFree
0x18002caca  xor     ebx, ebx
0x18002cacc  jmp     short loc_18002CB20
0x18002cace  xor     eax, eax
0x18002cad0  mov     ebx, 8007007Ah
0x18002cad5  mov     [rdi+rsi*2], ax
0x18002cad9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002cae3  test    rax, rbp
0x18002cae6  jbe     short loc_18002CAF9
0x18002cae8  jmp     short loc_18002CAF4
0x18002caea  mov     ebx, 80070057h
0x18002caef  test    rbp, rbp
0x18002caf2  jz      short loc_18002CAF9
0x18002caf4  xor     eax, eax
0x18002caf6  mov     [rdi], ax
0x18002caf9  mov     rcx, [rsp+68h]; this
0x18002cafe  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cb05  mov     r9d, ebx; char *
0x18002cb08  mov     edx, 7D1h; void *
0x18002cb0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cb12  test    rdi, rdi
0x18002cb15  jz      short loc_18002CB20
0x18002cb17  mov     rcx, rdi; pv
0x18002cb1a  call    cs:__imp_CoTaskMemFree
0x18002cb20  mov     eax, ebx
0x18002cb22  add     rsp, 30h
0x18002cb26  pop     r15
0x18002cb28  pop     r14
0x18002cb2a  pop     r12
0x18002cb2c  pop     rdi
0x18002cb2d  pop     rsi
0x18002cb2e  pop     rbp
0x18002cb2f  pop     rbx
0x18002cb30  retn
```
