# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)

- ea: `0x1800183e0`
- end: `0x1800185b3`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ`
- size: `467`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f790`

## callees

- `0x180005d34`
- `0x180007804`
- `0x1800183e0`
- `0x18002f990`
- `0x180056222`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001851a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001858d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001851a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001858d`

## string_xrefs

- `0x180018472`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180018571`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 *v4; // r12
  int v5; // eax
  size_t v6; // rsi
  int v7; // eax
  unsigned int v8; // edi
  wchar_t *v9; // rcx
  wchar_t *v10; // rbx
  unsigned __int64 v11; // rbp
  int v12; // eax
  void *v13; // rsi
  DWORD LastError; // edi
  int Locale; // [rsp+20h] [rbp-78h]
  char v17; // [rsp+30h] [rbp-68h] BYREF
  wchar_t *Buffer; // [rsp+38h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  va_list va; // [rsp+B0h] [rbp+18h] BYREF

  va_start(va, a2);
  Buffer = 0;
  v4 = _local_stdio_printf_options();
  v5 = o___stdio_common_vswprintf_0(*v4 | 2, 0, 0, a2, 0, va);
  Buffer = 0;
  if ( v5 < 0 )
    v5 = -1;
  v6 = v5;
  v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
         &Buffer,
         0,
         v5);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77B,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v7,
      Locale);
    v9 = Buffer;
    if ( Buffer )
      goto LABEL_27;
    return v8;
  }
  v10 = Buffer;
  v11 = v6 + 1;
  if ( v6 == -1 || v11 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
    if ( v6 == -1 )
      goto LABEL_25;
  }
  else
  {
    v12 = o___stdio_common_vswprintf_0(*v4 | 1, Buffer, v6, a2, 0, va);
    if ( v12 < 0 )
      v12 = -1;
    if ( v12 >= 0 && v12 <= v6 )
    {
      if ( v12 == v6 )
        v10[v6] = 0;
      if ( a1 == &v17 )
      {
        if ( v10 )
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
      return 0;
    }
    v10[v6] = 0;
    v8 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) == 0 )
      goto LABEL_25;
  }
  *v10 = 0;
LABEL_25:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x77F,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)v8,
    Locale);
  if ( v10 )
  {
    v9 = v10;
LABEL_27:
    CoTaskMemFree(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x1800183e0  mov     r11, rsp
0x1800183e3  mov     [r11+10h], rdx
0x1800183e7  mov     [r11+18h], r8
0x1800183eb  mov     [r11+20h], r9
0x1800183ef  push    rbx
0x1800183f0  push    rbp
0x1800183f1  push    rsi
0x1800183f2  push    rdi
0x1800183f3  push    r12
0x1800183f5  push    r13
0x1800183f7  push    r14
0x1800183f9  push    r15
0x1800183fb  sub     rsp, 58h
0x1800183ff  mov     rax, cs:__security_cookie
0x180018406  xor     rax, rsp
0x180018409  mov     [rsp+98h+var_58], rax
0x18001840e  xor     r13d, r13d
0x180018411  lea     rbx, [r11+18h]
0x180018415  mov     [r11-60h], r13
0x180018419  mov     r15, rdx
0x18001841c  mov     r14, rcx
0x18001841f  call    __local_stdio_printf_options
0x180018424  mov     [rsp+98h+ArgList], rbx; ArgList
0x180018429  mov     r9, r15; Format
0x18001842c  xor     r8d, r8d; BufferCount
0x18001842f  mov     [rsp+98h+Locale], r13; int
0x180018434  xor     edx, edx; Buffer
0x180018436  mov     r12, rax
0x180018439  mov     rcx, [rax]
0x18001843c  or      rcx, 2; Options
0x180018440  call    _o___stdio_common_vswprintf_0
0x180018445  or      ecx, 0FFFFFFFFh
0x180018448  mov     [rsp+98h+Buffer], r13
0x18001844d  test    eax, eax
0x18001844f  cmovs   eax, ecx
0x180018452  xor     edx, edx
0x180018454  movsxd  rsi, eax
0x180018457  lea     rcx, [rsp+98h+Buffer]
0x18001845c  mov     r8, rsi
0x18001845f  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180018464  mov     edi, eax
0x180018466  test    eax, eax
0x180018468  jns     short loc_180018499
0x18001846a  mov     rcx, [rsp+98h]; this
0x180018472  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018479  mov     r9d, eax; char *
0x18001847c  mov     edx, 77Bh; void *
0x180018481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018486  mov     rcx, [rsp+98h+Buffer]
0x18001848b  test    rcx, rcx
0x18001848e  jz      loc_180018593
0x180018494  jmp     loc_18001858D
0x180018499  mov     rbx, [rsp+98h+Buffer]
0x18001849e  lea     rbp, [rsi+1]
0x1800184a2  test    rbp, rbp
0x1800184a5  jz      loc_18001855B
0x1800184ab  cmp     rbp, 7FFFFFFFh
0x1800184b2  ja      loc_18001855B
0x1800184b8  mov     rcx, [r12]
0x1800184bc  lea     rax, [rsp+98h+arg_10]
0x1800184c4  mov     [rsp+98h+ArgList], rax; ArgList
0x1800184c9  or      rcx, 1; Options
0x1800184cd  mov     r9, r15; Format
0x1800184d0  mov     [rsp+98h+Locale], r13; Locale
0x1800184d5  mov     r8, rsi; BufferCount
0x1800184d8  mov     rdx, rbx; Buffer
0x1800184db  call    _o___stdio_common_vswprintf_0
0x1800184e0  test    eax, eax
0x1800184e2  mov     ecx, 0FFFFFFFFh
0x1800184e7  cmovs   eax, ecx
0x1800184ea  test    eax, eax
0x1800184ec  js      short loc_180018540
0x1800184ee  movsxd  rcx, eax
0x1800184f1  cmp     rcx, rsi
0x1800184f4  ja      short loc_180018540
0x1800184f6  jnz     short loc_1800184FD
0x1800184f8  mov     [rbx+rsi*2], r13w
0x1800184fd  lea     rax, [rsp+98h+var_68]
0x180018502  cmp     r14, rax
0x180018505  jz      short loc_18001852D
0x180018507  mov     rsi, [r14]
0x18001850a  test    rsi, rsi
0x18001850d  jz      short loc_180018528
0x18001850f  call    cs:__imp_GetLastError
0x180018515  mov     rcx, rsi; pv
0x180018518  mov     edi, eax
0x18001851a  call    cs:__imp_CoTaskMemFree
0x180018520  mov     ecx, edi; dwErrCode
0x180018522  call    cs:__imp_SetLastError
0x180018528  mov     [r14], rbx
0x18001852b  jmp     short loc_18001853B
0x18001852d  test    rbx, rbx
0x180018530  jz      short loc_18001853B
0x180018532  mov     rcx, rbx; pv
0x180018535  call    cs:__imp_CoTaskMemFree
0x18001853b  mov     edi, r13d
0x18001853e  jmp     short loc_180018593
0x180018540  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001854a  mov     [rbx+rsi*2], r13w
0x18001854f  mov     edi, 8007007Ah
0x180018554  test    rax, rbp
0x180018557  jbe     short loc_180018569
0x180018559  jmp     short loc_180018565
0x18001855b  mov     edi, 80070057h
0x180018560  test    rbp, rbp
0x180018563  jz      short loc_180018569
0x180018565  mov     [rbx], r13w
0x180018569  mov     rcx, [rsp+98h]; this
0x180018571  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180018578  mov     r9d, edi; char *
0x18001857b  mov     edx, 77Fh; void *
0x180018580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018585  test    rbx, rbx
0x180018588  jz      short loc_180018593
0x18001858a  mov     rcx, rbx; pv
0x18001858d  call    cs:__imp_CoTaskMemFree
0x180018593  mov     eax, edi
0x180018595  mov     rcx, [rsp+98h+var_58]
0x18001859a  xor     rcx, rsp; StackCookie
0x18001859d  call    __security_check_cookie
0x1800185a2  add     rsp, 58h
0x1800185a6  pop     r15
0x1800185a8  pop     r14
0x1800185aa  pop     r13
0x1800185ac  pop     r12
0x1800185ae  pop     rdi
0x1800185af  pop     rsi
0x1800185b0  pop     rbp
0x1800185b1  pop     rbx
0x1800185b2  retn
```
