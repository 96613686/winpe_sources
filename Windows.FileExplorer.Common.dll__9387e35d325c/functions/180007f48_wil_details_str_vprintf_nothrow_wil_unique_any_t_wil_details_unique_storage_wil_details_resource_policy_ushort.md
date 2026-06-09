# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x180007f48`
- end: `0x1800080cc`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d028`

## callees

- `0x1800077c8`
- `0x180007900`
- `0x180007f48`
- `0x180031f34`
- `0x180038750`
- `0x1800387a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000805e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000805e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007f7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008069`

## string_xrefs

- `0x180008033`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000807e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        int *a1,
        const wchar_t *a2,
        va_list *a3)
{
  int v6; // eax
  const char *v7; // r9
  size_t v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  unsigned __int64 v11; // rsi
  int v12; // eax
  void *v13; // rsi
  unsigned int v15; // ebx
  __int64 v16; // rdx
  DWORD LastError; // ebx
  int v18; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  wchar_t *v20; // [rsp+88h] [rbp+20h] BYREF

  v6 = vscwprintf(a2, *a3);
  v8 = v6;
  if ( v6 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  v9 = (wchar_t *)CoTaskMemAlloc(2LL * v6 + 2);
  v20 = v9;
  v10 = v9;
  if ( !v9 )
  {
    v15 = -2147024882;
    v16 = 1997;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v15,
      v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v20);
    return v15;
  }
  v11 = v8 + 1;
  *v9 = 0;
  v9[v8] = 0;
  if ( v8 == -1 )
  {
    v15 = -2147024809;
    if ( !v11 )
    {
LABEL_23:
      v16 = 2001;
      goto LABEL_15;
    }
LABEL_22:
    *v10 = 0;
    goto LABEL_23;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v15 = -2147024809;
    goto LABEL_22;
  }
  v12 = vsnwprintf(v9, v8, a2, *a3);
  if ( v12 < 0 || v12 > v8 )
  {
    v10[v8] = 0;
    v15 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
      goto LABEL_23;
    goto LABEL_22;
  }
  if ( v12 == v8 )
    v10[v8] = 0;
  v20 = 0;
  if ( a1 == &v18 )
  {
    CoTaskMemFree(v10);
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
    *(_QWORD *)a1 = v10;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v20);
  return 0;
}

```

## disassembly

```asm
0x180007f48  push    rbx
0x180007f4a  push    rbp
0x180007f4b  push    rsi
0x180007f4c  push    rdi
0x180007f4d  push    r14
0x180007f4f  push    r15
0x180007f51  sub     rsp, 38h
0x180007f55  mov     rbp, rdx
0x180007f58  mov     r14, rcx
0x180007f5b  mov     rdx, [r8]; ArgList
0x180007f5e  mov     rcx, rbp; Format
0x180007f61  mov     r15, r8
0x180007f64  call    _vscwprintf
0x180007f69  movsxd  rbx, eax
0x180007f6c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180007f70  jz      loc_180008079
0x180007f76  lea     rcx, ds:2[rbx*2]; cb
0x180007f7e  call    cs:__imp_CoTaskMemAlloc
0x180007f84  mov     [rsp+68h+arg_18], rax
0x180007f8c  mov     rdi, rax
0x180007f8f  test    rax, rax
0x180007f92  jz      loc_180008024
0x180007f98  xor     ecx, ecx
0x180007f9a  lea     rsi, [rbx+1]
0x180007f9e  mov     [rax], cx
0x180007fa1  mov     [rax+rbx*2], cx
0x180007fa5  test    rsi, rsi
0x180007fa8  jz      loc_1800080B3
0x180007fae  cmp     rsi, 7FFFFFFFh
0x180007fb5  ja      loc_180008090
0x180007fbb  mov     r9, [r15]; Args
0x180007fbe  mov     r8, rbp; Format
0x180007fc1  mov     rdx, rbx; BufferCount
0x180007fc4  mov     rcx, rax; Buffer
0x180007fc7  call    _vsnwprintf
0x180007fcc  test    eax, eax
0x180007fce  js      loc_180008097
0x180007fd4  cdqe
0x180007fd6  cmp     rax, rbx
0x180007fd9  ja      loc_180008097
0x180007fdf  jnz     short loc_180007FE7
0x180007fe1  xor     eax, eax
0x180007fe3  mov     [rdi+rbx*2], ax
0x180007fe7  lea     rax, [rsp+68h+var_48]
0x180007fec  mov     [rsp+68h+arg_18], 0
0x180007ff8  cmp     r14, rax
0x180007ffb  jz      short loc_180008053
0x180007ffd  mov     rsi, [r14]
0x180008000  test    rsi, rsi
0x180008003  jnz     short loc_18000805E
0x180008005  mov     [r14], rdi
0x180008008  lea     rcx, [rsp+68h+arg_18]; void *
0x180008010  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180008015  xor     eax, eax
0x180008017  add     rsp, 38h
0x18000801b  pop     r15
0x18000801d  pop     r14
0x18000801f  pop     rdi
0x180008020  pop     rsi
0x180008021  pop     rbp
0x180008022  pop     rbx
0x180008023  retn
0x180008024  mov     ebx, 8007000Eh
0x180008029  mov     edx, 7CDh; void *
0x18000802e  mov     rcx, [rsp+68h]; this
0x180008033  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000803a  mov     r9d, ebx; char *
0x18000803d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008042  lea     rcx, [rsp+68h+arg_18]; void *
0x18000804a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18000804f  mov     eax, ebx
0x180008051  jmp     short loc_180008017
0x180008053  mov     rcx, rdi; pv
0x180008056  call    cs:__imp_CoTaskMemFree
0x18000805c  jmp     short loc_180008008
0x18000805e  call    cs:__imp_GetLastError
0x180008064  mov     rcx, rsi; pv
0x180008067  mov     ebx, eax
0x180008069  call    cs:__imp_CoTaskMemFree
0x18000806f  mov     ecx, ebx; dwErrCode
0x180008071  call    cs:__imp_SetLastError
0x180008077  jmp     short loc_180008005
0x180008079  mov     rcx, [rsp+68h]; this
0x18000807e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008085  mov     edx, 0F89h; void *
0x18000808a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008090  mov     ebx, 80070057h
0x180008095  jmp     short loc_1800080BD
0x180008097  xor     eax, eax
0x180008099  mov     [rdi+rbx*2], ax
0x18000809d  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800080a7  mov     ebx, 8007007Ah
0x1800080ac  test    rax, rsi
0x1800080af  ja      short loc_1800080BD
0x1800080b1  jmp     short loc_1800080C2
0x1800080b3  mov     ebx, 80070057h
0x1800080b8  test    rsi, rsi
0x1800080bb  jz      short loc_1800080C2
0x1800080bd  xor     eax, eax
0x1800080bf  mov     [rdi], ax
0x1800080c2  mov     edx, 7D1h
0x1800080c7  jmp     loc_18000802E
```
