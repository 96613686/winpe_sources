# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x180006048`
- end: `0x180006142`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012254`

## callees

- `0x1800033d0`
- `0x180005ffc`
- `0x180006048`
- `0x180006218`
- `0x18000773c`
- `0x18001e0b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006127`

## string_xrefs

- `0x180006094`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800060e5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        va_list *a3)
{
  __int64 v6; // rbp
  int v7; // eax
  unsigned __int16 **v8; // r8
  unsigned __int64 *v9; // r9
  unsigned int v10; // ebx
  void *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+78h] [rbp+20h] BYREF

  v6 = vscwprintf(a2, *a3);
  pv = 0;
  v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &pv,
         0,
         v6);
  v10 = v7;
  if ( v7 >= 0 )
  {
    v12 = pv;
    v13 = StringCchVPrintfExW((STRSAFE_LPWSTR)pv, v6 + 1, v8, v9, v15, a2, *a3);
    v14 = v13;
    if ( v13 >= 0 )
    {
      pv = v12;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        a1,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v13,
        v16);
      if ( v12 )
        CoTaskMemFree(v12);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v7,
      v15);
    if ( pv )
      CoTaskMemFree(pv);
    return v10;
  }
}

```

## disassembly

```asm
0x180006048  mov     [rsp+arg_0], rbx
0x18000604d  mov     [rsp+arg_8], rbp
0x180006052  push    rsi
0x180006053  push    rdi
0x180006054  push    r14
0x180006056  sub     rsp, 40h
0x18000605a  mov     rsi, rdx
0x18000605d  mov     r14, rcx
0x180006060  mov     rdx, [r8]; ArgList
0x180006063  mov     rcx, rsi; Format
0x180006066  mov     rdi, r8
0x180006069  call    _vscwprintf
0x18000606e  movsxd  rbp, eax
0x180006071  lea     rcx, [rsp+58h+pv]
0x180006076  mov     r8, rbp
0x180006079  mov     [rsp+58h+pv], 0
0x180006082  xor     edx, edx
0x180006084  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006089  mov     ebx, eax
0x18000608b  test    eax, eax
0x18000608d  jns     short loc_1800060BC
0x18000608f  mov     rcx, [rsp+58h]; this
0x180006094  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000609b  mov     r9d, eax; char *
0x18000609e  mov     edx, 7CDh; void *
0x1800060a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060a8  mov     rcx, [rsp+58h+pv]; pv
0x1800060ad  test    rcx, rcx
0x1800060b0  jz      short loc_1800060B8
0x1800060b2  call    cs:__imp_CoTaskMemFree
0x1800060b8  mov     eax, ebx
0x1800060ba  jmp     short loc_18000612F
0x1800060bc  mov     rax, [rdi]
0x1800060bf  lea     rdx, [rbp+1]; unsigned __int64
0x1800060c3  mov     rbx, [rsp+58h+pv]
0x1800060c8  mov     [rsp+58h+var_28], rax; char *
0x1800060cd  mov     rcx, rbx; pszDest
0x1800060d0  mov     [rsp+58h+var_30], rsi; unsigned __int16 *
0x1800060d5  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x1800060da  mov     edi, eax
0x1800060dc  test    eax, eax
0x1800060de  jns     short loc_18000610B
0x1800060e0  mov     rcx, [rsp+58h]; this
0x1800060e5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800060ec  mov     r9d, eax; char *
0x1800060ef  mov     edx, 7D1h; void *
0x1800060f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060f9  test    rbx, rbx
0x1800060fc  jz      short loc_180006107
0x1800060fe  mov     rcx, rbx; pv
0x180006101  call    cs:__imp_CoTaskMemFree
0x180006107  mov     eax, edi
0x180006109  jmp     short loc_18000612F
0x18000610b  lea     rdx, [rsp+58h+pv]
0x180006110  mov     [rsp+58h+pv], rbx
0x180006115  mov     rcx, r14
0x180006118  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000611d  mov     rcx, [rsp+58h+pv]; pv
0x180006122  test    rcx, rcx
0x180006125  jz      short loc_18000612D
0x180006127  call    cs:__imp_CoTaskMemFree
0x18000612d  xor     eax, eax
0x18000612f  mov     rbx, [rsp+58h+arg_0]
0x180006134  mov     rbp, [rsp+58h+arg_8]
0x180006139  add     rsp, 40h
0x18000613d  pop     r14
0x18000613f  pop     rdi
0x180006140  pop     rsi
0x180006141  retn
```
