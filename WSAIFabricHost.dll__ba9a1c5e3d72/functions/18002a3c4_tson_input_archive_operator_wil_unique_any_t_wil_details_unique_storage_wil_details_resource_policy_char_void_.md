# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18002a3c4`
- end: `0x18002a498`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `212`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e69c`
- `0x18004e4d0`
- `0x1800515dc`

## callees

- `0x18002a3c4`
- `0x180051394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a46a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a47d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a47d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a475`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18002a3c4  push    rbx
0x18002a3c6  push    rbp
0x18002a3c7  push    rsi
0x18002a3c8  push    rdi
0x18002a3c9  push    r14
0x18002a3cb  sub     rsp, 40h
0x18002a3cf  xor     eax, eax
0x18002a3d1  mov     [rsp+68h+var_48], 0
0x18002a3da  mov     rsi, rdx
0x18002a3dd  mov     [rsp+68h+var_37], eax
0x18002a3e1  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18002a3e6  mov     [rsp+68h+var_33], ax
0x18002a3eb  mov     [rsp+68h+var_31], al
0x18002a3ef  mov     rdi, rcx
0x18002a3f2  mov     [rsp+68h+cb], 0
0x18002a3fb  mov     [rsp+68h+var_38], 0
0x18002a400  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18002a405  mov     rcx, [rsp+68h+cb]; cb
0x18002a40a  test    rcx, rcx
0x18002a40d  jz      short loc_18002A462
0x18002a40f  call    cs:__imp_CoTaskMemAlloc
0x18002a415  mov     r14, [rsi]
0x18002a418  mov     rbp, rax
0x18002a41b  test    r14, r14
0x18002a41e  jz      short loc_18002A439
0x18002a420  call    cs:__imp_GetLastError
0x18002a426  mov     rcx, r14; pv
0x18002a429  mov     ebx, eax
0x18002a42b  call    cs:__imp_CoTaskMemFree
0x18002a431  mov     ecx, ebx; dwErrCode
0x18002a433  call    cs:__imp_SetLastError
0x18002a439  mov     [rsi], rbp
0x18002a43c  test    rbp, rbp
0x18002a43f  jz      short loc_18002A455
0x18002a441  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18002a446  mov     [rsp+68h+var_48], rbp
0x18002a44b  mov     rcx, rdi; this
0x18002a44e  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18002a453  jmp     short loc_18002A48A
0x18002a455  cmp     dword ptr [rdi+8], 0
0x18002a459  jl      short loc_18002A462
0x18002a45b  mov     dword ptr [rdi+8], 8007000Eh
0x18002a462  mov     rbp, [rsi]
0x18002a465  test    rbp, rbp
0x18002a468  jz      short loc_18002A483
0x18002a46a  call    cs:__imp_GetLastError
0x18002a470  mov     rcx, rbp; pv
0x18002a473  mov     ebx, eax
0x18002a475  call    cs:__imp_CoTaskMemFree
0x18002a47b  mov     ecx, ebx; dwErrCode
0x18002a47d  call    cs:__imp_SetLastError
0x18002a483  mov     qword ptr [rsi], 0
0x18002a48a  mov     rax, rdi
0x18002a48d  add     rsp, 40h
0x18002a491  pop     r14
0x18002a493  pop     rdi
0x18002a494  pop     rsi
0x18002a495  pop     rbp
0x18002a496  pop     rbx
0x18002a497  retn
```
