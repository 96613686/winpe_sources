# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &> &&)

- ea: `0x180072094`
- end: `0x1800721ad`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `281`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007cd78`

## callees

- `0x180072094`
- `0x18007cc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007216c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007216c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007212f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007218b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007212f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007218b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007217d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007217d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800720f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800720f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>>(
        tson::input_archive *this,
        __int64 a2)
{
  char v3; // r8
  void **v4; // rsi
  LPVOID v5; // rbp
  void *v6; // r14
  DWORD LastError; // ebx
  void *v8; // rbp
  DWORD v9; // ebx
  LPVOID v11; // [rsp+28h] [rbp-40h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]
  char v13; // [rsp+38h] [rbp-30h]
  int v14; // [rsp+39h] [rbp-2Fh]
  __int16 v15; // [rsp+3Dh] [rbp-2Bh]
  char v16; // [rsp+3Fh] [rbp-29h]

  v3 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v3;
  v4 = *(void ***)(a2 + 16);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  tson::input_archive::loadValue(this, (struct tson::string_tag *)&v11);
  if ( v12 )
  {
    v5 = CoTaskMemAlloc(2 * v12);
    v6 = *v4;
    if ( *v4 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *v4 = v5;
    if ( v5 )
    {
      v11 = v5;
      tson::input_archive::loadValue(this, (struct tson::string_tag *)&v11);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v8 = *v4;
  if ( *v4 )
  {
    v9 = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(v9);
  }
  *v4 = 0;
  return this;
}

```

## disassembly

```asm
0x180072094  mov     r11, rsp
0x180072097  push    rbx
0x180072098  push    rbp
0x180072099  push    rsi
0x18007209a  push    rdi
0x18007209b  push    r14
0x18007209d  sub     rsp, 40h
0x1800720a1  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x1800720a9  mov     rdi, rcx
0x1800720ac  mov     r8b, [rdx+8]
0x1800720b0  mov     rax, [rdx]
0x1800720b3  mov     [rcx+10h], rax
0x1800720b7  mov     [rcx+18h], r8b
0x1800720bb  mov     rsi, [rdx+10h]
0x1800720bf  mov     qword ptr [r11-40h], 0
0x1800720c7  mov     qword ptr [r11-38h], 0
0x1800720cf  mov     [rsp+68h+var_30], 0
0x1800720d4  xor     eax, eax
0x1800720d6  mov     [rsp+68h+var_2F], eax
0x1800720da  mov     [rsp+68h+var_2B], ax
0x1800720df  mov     [rsp+68h+var_29], al
0x1800720e3  lea     rdx, [r11-40h]; struct tson::string_tag *
0x1800720e7  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x1800720ec  mov     rcx, [rsp+68h+var_38]
0x1800720f1  test    rcx, rcx
0x1800720f4  jz      short loc_180072164
0x1800720f6  add     rcx, rcx; cb
0x1800720f9  call    cs:__imp_CoTaskMemAlloc
0x180072100  nop     dword ptr [rax+rax+00h]
0x180072105  mov     rbp, rax
0x180072108  mov     r14, [rsi]
0x18007210b  test    r14, r14
0x18007210e  jz      short loc_18007213B
0x180072110  call    cs:__imp_GetLastError
0x180072117  nop     dword ptr [rax+rax+00h]
0x18007211c  mov     ebx, eax
0x18007211e  mov     rcx, r14; pv
0x180072121  call    cs:__imp_CoTaskMemFree
0x180072128  nop     dword ptr [rax+rax+00h]
0x18007212d  mov     ecx, ebx; dwErrCode
0x18007212f  call    cs:__imp_SetLastError
0x180072136  nop     dword ptr [rax+rax+00h]
0x18007213b  mov     [rsi], rbp
0x18007213e  test    rbp, rbp
0x180072141  jz      short loc_180072157
0x180072143  mov     [rsp+68h+var_40], rbp
0x180072148  lea     rdx, [rsp+68h+var_40]; struct tson::string_tag *
0x18007214d  mov     rcx, rdi; this
0x180072150  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180072155  jmp     short loc_18007219E
0x180072157  cmp     dword ptr [rdi+8], 0
0x18007215b  jl      short loc_180072164
0x18007215d  mov     dword ptr [rdi+8], 8007000Eh
0x180072164  mov     rbp, [rsi]
0x180072167  test    rbp, rbp
0x18007216a  jz      short loc_180072197
0x18007216c  call    cs:__imp_GetLastError
0x180072173  nop     dword ptr [rax+rax+00h]
0x180072178  mov     ebx, eax
0x18007217a  mov     rcx, rbp; pv
0x18007217d  call    cs:__imp_CoTaskMemFree
0x180072184  nop     dword ptr [rax+rax+00h]
0x180072189  mov     ecx, ebx; dwErrCode
0x18007218b  call    cs:__imp_SetLastError
0x180072192  nop     dword ptr [rax+rax+00h]
0x180072197  mov     qword ptr [rsi], 0
0x18007219e  mov     rax, rdi
0x1800721a1  add     rsp, 40h
0x1800721a5  pop     r14
0x1800721a7  pop     rdi
0x1800721a8  pop     rsi
0x1800721a9  pop     rbp
0x1800721aa  pop     rbx
0x1800721ab  retn
```
