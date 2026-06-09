# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18000f1d4`
- end: `0x18000f2a8`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `212`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180011080`
- `0x180028028`
- `0x180028df4`

## callees

- `0x18000f1d4`
- `0x180028bac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f243`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f28d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f243`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f27a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f27a`
- `ole32!CoTaskMemFree` at `0x18000f23b`
- `ole32!CoTaskMemFree` at `0x18000f285`
- `ole32!CoTaskMemFree` at `0x18000f23b`
- `ole32!CoTaskMemFree` at `0x18000f285`
- `ole32!CoTaskMemAlloc` at `0x18000f21f`
- `ole32!CoTaskMemAlloc` at `0x18000f21f`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        tson::input_archive *this,
        void **a2)
{
  LPVOID v4; // rax
  void *v5; // r14
  void *v6; // rbp
  DWORD LastError; // ebx
  void *v8; // rbp
  DWORD v9; // ebx
  void *v11; // [rsp+20h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-40h]
  char v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+31h] [rbp-37h]
  __int16 v15; // [rsp+35h] [rbp-33h]
  char v16; // [rsp+37h] [rbp-31h]

  v11 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  cb = 0;
  v13 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
  if ( cb )
  {
    v4 = CoTaskMemAlloc(cb);
    v5 = *a2;
    v6 = v4;
    if ( *a2 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v5);
      SetLastError(LastError);
    }
    *a2 = v6;
    if ( v6 )
    {
      v11 = v6;
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v8 = *a2;
  if ( *a2 )
  {
    v9 = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(v9);
  }
  *a2 = 0;
  return this;
}

```

## disassembly

```asm
0x18000f1d4  push    rbx
0x18000f1d6  push    rbp
0x18000f1d7  push    rsi
0x18000f1d8  push    rdi
0x18000f1d9  push    r14
0x18000f1db  sub     rsp, 40h
0x18000f1df  xor     eax, eax
0x18000f1e1  mov     [rsp+68h+var_48], 0
0x18000f1ea  mov     rsi, rdx
0x18000f1ed  mov     [rsp+68h+var_37], eax
0x18000f1f1  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18000f1f6  mov     [rsp+68h+var_33], ax
0x18000f1fb  mov     [rsp+68h+var_31], al
0x18000f1ff  mov     rdi, rcx
0x18000f202  mov     [rsp+68h+cb], 0
0x18000f20b  mov     [rsp+68h+var_38], 0
0x18000f210  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18000f215  mov     rcx, [rsp+68h+cb]; cb
0x18000f21a  test    rcx, rcx
0x18000f21d  jz      short loc_18000F272
0x18000f21f  call    cs:__imp_CoTaskMemAlloc
0x18000f225  mov     r14, [rsi]
0x18000f228  mov     rbp, rax
0x18000f22b  test    r14, r14
0x18000f22e  jz      short loc_18000F249
0x18000f230  call    cs:__imp_GetLastError
0x18000f236  mov     rcx, r14; pv
0x18000f239  mov     ebx, eax
0x18000f23b  call    cs:__imp_CoTaskMemFree
0x18000f241  mov     ecx, ebx; dwErrCode
0x18000f243  call    cs:__imp_SetLastError
0x18000f249  mov     [rsi], rbp
0x18000f24c  test    rbp, rbp
0x18000f24f  jz      short loc_18000F265
0x18000f251  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18000f256  mov     [rsp+68h+var_48], rbp
0x18000f25b  mov     rcx, rdi; this
0x18000f25e  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18000f263  jmp     short loc_18000F29A
0x18000f265  cmp     dword ptr [rdi+8], 0
0x18000f269  jl      short loc_18000F272
0x18000f26b  mov     dword ptr [rdi+8], 8007000Eh
0x18000f272  mov     rbp, [rsi]
0x18000f275  test    rbp, rbp
0x18000f278  jz      short loc_18000F293
0x18000f27a  call    cs:__imp_GetLastError
0x18000f280  mov     rcx, rbp; pv
0x18000f283  mov     ebx, eax
0x18000f285  call    cs:__imp_CoTaskMemFree
0x18000f28b  mov     ecx, ebx; dwErrCode
0x18000f28d  call    cs:__imp_SetLastError
0x18000f293  mov     qword ptr [rsi], 0
0x18000f29a  mov     rax, rdi
0x18000f29d  add     rsp, 40h
0x18000f2a1  pop     r14
0x18000f2a3  pop     rdi
0x18000f2a4  pop     rsi
0x18000f2a5  pop     rbp
0x18000f2a6  pop     rbx
0x18000f2a7  retn
```
