# tip2::details::shared_data<0,0,0>::log(char const *)

- ea: `0x180022f50`
- end: `0x180022fe9`
- name: `?log@?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAAXPEBD@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180022ff0`

## callees

- `0x180010728`
- `0x18001360c`
- `0x18001666c`
- `0x180022f50`
- `0x180023234`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180022f79`
- `OLE32!CoTaskMemAlloc` at `0x180022f79`

## string_xrefs

- `0x180022fd7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::log(__int64 a1, _BYTE *a2, __int64 a3, const char *a4)
{
  rsize_t v6; // rbx
  _BYTE *v7; // rax
  _BYTE *v8; // rbp
  char v9; // bl
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v11; // [rsp+60h] [rbp+8h] BYREF

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = CoTaskMemAlloc(v6 + 1);
  v8 = v7;
  if ( v7 )
  {
    memcpy_s(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  v11 = v8;
  v9 = tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::push_back(
         a1 + 96,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v11);
  if ( !v9 )
    *(_DWORD *)(a1 + 64) |= 0x100000u;
}

```

## disassembly

```asm
0x180022f50  push    rbx
0x180022f52  push    rbp
0x180022f53  push    rsi
0x180022f54  push    rdi
0x180022f55  push    r14
0x180022f57  push    r15
0x180022f59  sub     rsp, 28h
0x180022f5d  mov     rsi, rdx
0x180022f60  mov     rdi, rcx
0x180022f63  test    rdx, rdx
0x180022f66  jz      short loc_180022FD2
0x180022f68  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022f6c  inc     rbx
0x180022f6f  cmp     byte ptr [rdx+rbx], 0
0x180022f73  jnz     short loc_180022F6C
0x180022f75  lea     rcx, [rbx+1]; cb
0x180022f79  call    cs:__imp_CoTaskMemAlloc
0x180022f7f  mov     rbp, rax
0x180022f82  test    rax, rax
0x180022f85  jz      short loc_180022F9D
0x180022f87  mov     r9, rbx; SourceSize
0x180022f8a  lea     rdx, [rbx+1]; DestinationSize
0x180022f8e  mov     r8, rsi; Source
0x180022f91  mov     rcx, rax; Destination
0x180022f94  call    memcpy_s
0x180022f99  mov     byte ptr [rbx+rbp], 0
0x180022f9d  lea     rdx, [rsp+58h+arg_0]
0x180022fa2  mov     [rsp+58h+arg_0], rbp
0x180022fa7  lea     rcx, [rdi+60h]
0x180022fab  call    ?push_back@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::push_back(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &&)
0x180022fb0  lea     rcx, [rsp+58h+arg_0]
0x180022fb5  mov     bl, al
0x180022fb7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022fbc  test    bl, bl
0x180022fbe  jnz     short loc_180022FC5
0x180022fc0  bts     dword ptr [rdi+40h], 14h
0x180022fc5  add     rsp, 28h
0x180022fc9  pop     r15
0x180022fcb  pop     r14
0x180022fcd  pop     rdi
0x180022fce  pop     rsi
0x180022fcf  pop     rbp
0x180022fd0  pop     rbx
0x180022fd1  retn
0x180022fd2  mov     rcx, [rsp+58h]; this
0x180022fd7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022fde  mov     edx, 0FBDh; void *
0x180022fe3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
