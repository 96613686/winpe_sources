# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180071ec4`
- end: `0x180071fca`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800738b0`
- `0x18007bf34`
- `0x18007cd78`

## callees

- `0x180071ec4`
- `0x18007cb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071f89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071fa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071fa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071f9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180071f16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
tson::input_archive *__fastcall tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        tson::input_archive *this,
        void **a2)
{
  LPVOID v4; // rbp
  void *v5; // r14
  DWORD LastError; // ebx
  void *v7; // rbp
  DWORD v8; // ebx
  LPVOID v10; // [rsp+28h] [rbp-40h] BYREF
  SIZE_T cb; // [rsp+30h] [rbp-38h]
  char v12; // [rsp+38h] [rbp-30h]
  int v13; // [rsp+39h] [rbp-2Fh]
  __int16 v14; // [rsp+3Dh] [rbp-2Bh]
  char v15; // [rsp+3Fh] [rbp-29h]

  v10 = 0;
  cb = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v10);
  if ( cb )
  {
    v4 = CoTaskMemAlloc(cb);
    v5 = *a2;
    if ( *a2 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v5);
      SetLastError(LastError);
    }
    *a2 = v4;
    if ( v4 )
    {
      v10 = v4;
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v10);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v7 = *a2;
  if ( *a2 )
  {
    v8 = GetLastError();
    CoTaskMemFree(v7);
    SetLastError(v8);
  }
  *a2 = 0;
  return this;
}

```

## disassembly

```asm
0x180071ec4  mov     rax, rsp
0x180071ec7  push    rbx
0x180071ec8  push    rbp
0x180071ec9  push    rsi
0x180071eca  push    rdi
0x180071ecb  push    r14
0x180071ecd  sub     rsp, 40h
0x180071ed1  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180071ed9  mov     rsi, rdx
0x180071edc  mov     rdi, rcx
0x180071edf  mov     qword ptr [rax-40h], 0
0x180071ee7  mov     qword ptr [rax-38h], 0
0x180071eef  mov     byte ptr [rax-30h], 0
0x180071ef3  xor     eax, eax
0x180071ef5  mov     [rsp+68h+var_2F], eax
0x180071ef9  mov     [rsp+68h+var_2B], ax
0x180071efe  mov     [rsp+68h+var_29], al
0x180071f02  lea     rdx, [rsp+68h+var_40]; struct tson::ansistring_tag *
0x180071f07  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180071f0c  mov     rcx, [rsp+68h+cb]; cb
0x180071f11  test    rcx, rcx
0x180071f14  jz      short loc_180071F81
0x180071f16  call    cs:__imp_CoTaskMemAlloc
0x180071f1d  nop     dword ptr [rax+rax+00h]
0x180071f22  mov     rbp, rax
0x180071f25  mov     r14, [rsi]
0x180071f28  test    r14, r14
0x180071f2b  jz      short loc_180071F58
0x180071f2d  call    cs:__imp_GetLastError
0x180071f34  nop     dword ptr [rax+rax+00h]
0x180071f39  mov     ebx, eax
0x180071f3b  mov     rcx, r14; pv
0x180071f3e  call    cs:__imp_CoTaskMemFree
0x180071f45  nop     dword ptr [rax+rax+00h]
0x180071f4a  mov     ecx, ebx; dwErrCode
0x180071f4c  call    cs:__imp_SetLastError
0x180071f53  nop     dword ptr [rax+rax+00h]
0x180071f58  mov     [rsi], rbp
0x180071f5b  test    rbp, rbp
0x180071f5e  jz      short loc_180071F74
0x180071f60  mov     [rsp+68h+var_40], rbp
0x180071f65  lea     rdx, [rsp+68h+var_40]; struct tson::ansistring_tag *
0x180071f6a  mov     rcx, rdi; this
0x180071f6d  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180071f72  jmp     short loc_180071FBB
0x180071f74  cmp     dword ptr [rdi+8], 0
0x180071f78  jl      short loc_180071F81
0x180071f7a  mov     dword ptr [rdi+8], 8007000Eh
0x180071f81  mov     rbp, [rsi]
0x180071f84  test    rbp, rbp
0x180071f87  jz      short loc_180071FB4
0x180071f89  call    cs:__imp_GetLastError
0x180071f90  nop     dword ptr [rax+rax+00h]
0x180071f95  mov     ebx, eax
0x180071f97  mov     rcx, rbp; pv
0x180071f9a  call    cs:__imp_CoTaskMemFree
0x180071fa1  nop     dword ptr [rax+rax+00h]
0x180071fa6  mov     ecx, ebx; dwErrCode
0x180071fa8  call    cs:__imp_SetLastError
0x180071faf  nop     dword ptr [rax+rax+00h]
0x180071fb4  mov     qword ptr [rsi], 0
0x180071fbb  mov     rax, rdi
0x180071fbe  add     rsp, 40h
0x180071fc2  pop     r14
0x180071fc4  pop     rdi
0x180071fc5  pop     rsi
0x180071fc6  pop     rbp
0x180071fc7  pop     rbx
0x180071fc8  retn
```
