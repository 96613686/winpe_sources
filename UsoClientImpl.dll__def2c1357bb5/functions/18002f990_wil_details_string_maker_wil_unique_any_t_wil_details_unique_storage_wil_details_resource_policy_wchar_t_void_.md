# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x18002f990`
- end: `0x18002fae7`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `343`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800183e0`
- `0x18002e0c8`
- `0x18002fb54`

## callees

- `0x18002f990`
- `0x180033f14`
- `0x18005629a`
- `0x18005631e`
- `0x18005c660`
- `0x18005ca20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fa9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fa0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fa0d`

## string_xrefs

- `0x18002fad5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDB5,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
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
    *(_QWORD *)a1 = v11;
  }
  return *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18002f990  mov     rax, rsp
0x18002f993  mov     [rax+8], rbx
0x18002f997  mov     [rax+10h], rbp
0x18002f99b  mov     [rax+18h], rsi
0x18002f99f  mov     [rax+20h], rdi
0x18002f9a3  push    r12
0x18002f9a5  push    r14
0x18002f9a7  push    r15
0x18002f9a9  sub     rsp, 30h
0x18002f9ad  xor     r12d, r12d
0x18002f9b0  mov     rsi, r8
0x18002f9b3  mov     rbp, rdx
0x18002f9b6  mov     r14, rcx
0x18002f9b9  test    rdx, rdx
0x18002f9bc  jnz     short loc_18002F9C8
0x18002f9be  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002f9c2  jz      loc_18002FAD0
0x18002f9c8  mov     rbx, rsi
0x18002f9cb  test    rbp, rbp
0x18002f9ce  jz      short loc_18002F9FA
0x18002f9d0  mov     eax, 7FFFFFFFh
0x18002f9d5  mov     rbx, rbp
0x18002f9d8  cmp     rsi, rax
0x18002f9db  cmovb   rax, rsi
0x18002f9df  test    rax, rax
0x18002f9e2  jz      short loc_18002F9F4
0x18002f9e4  cmp     [rbx], r12w
0x18002f9e8  jz      short loc_18002F9F4
0x18002f9ea  add     rbx, 2
0x18002f9ee  sub     rax, 1
0x18002f9f2  jnz     short loc_18002F9E4
0x18002f9f4  sub     rbx, rbp
0x18002f9f7  sar     rbx, 1
0x18002f9fa  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002f9fe  cmovz   rsi, rbx
0x18002fa02  lea     r15, ds:2[rsi*2]
0x18002fa0a  mov     rcx, r15; cb
0x18002fa0d  call    cs:__imp_CoTaskMemAlloc
0x18002fa13  mov     rdi, rax
0x18002fa16  test    rax, rax
0x18002fa19  jz      short loc_18002FA64
0x18002fa1b  test    rbp, rbp
0x18002fa1e  jz      short loc_18002FA5B
0x18002fa20  add     rbx, rbx
0x18002fa23  jz      short loc_18002FA54
0x18002fa25  mov     rcx, rax; void *
0x18002fa28  cmp     r15, rbx
0x18002fa2b  jb      short loc_18002FA3A
0x18002fa2d  mov     r8, rbx; Size
0x18002fa30  mov     rdx, rbp; Src
0x18002fa33  call    memmove
0x18002fa38  jmp     short loc_18002FA54
0x18002fa3a  mov     r8, r15; Size
0x18002fa3d  xor     edx, edx; Val
0x18002fa3f  call    memset
0x18002fa44  call    _o__errno_0
0x18002fa49  mov     dword ptr [rax], 22h ; '"'
0x18002fa4f  call    _invalid_parameter_noinfo
0x18002fa54  mov     [rbx+rdi], r12w
0x18002fa59  jmp     short loc_18002FA5F
0x18002fa5b  mov     [rax], r12w
0x18002fa5f  mov     [rdi+rsi*2], r12w
0x18002fa64  lea     rax, [rsp+48h+var_28]
0x18002fa69  cmp     r14, rax
0x18002fa6c  jz      short loc_18002FA94
0x18002fa6e  mov     rsi, [r14]
0x18002fa71  test    rsi, rsi
0x18002fa74  jz      short loc_18002FA8F
0x18002fa76  call    cs:__imp_GetLastError
0x18002fa7c  mov     rcx, rsi; pv
0x18002fa7f  mov     ebx, eax
0x18002fa81  call    cs:__imp_CoTaskMemFree
0x18002fa87  mov     ecx, ebx; dwErrCode
0x18002fa89  call    cs:__imp_SetLastError
0x18002fa8f  mov     [r14], rdi
0x18002fa92  jmp     short loc_18002FAA2
0x18002fa94  test    rdi, rdi
0x18002fa97  jz      short loc_18002FAA2
0x18002fa99  mov     rcx, rdi; pv
0x18002fa9c  call    cs:__imp_CoTaskMemFree
0x18002faa2  mov     rax, [r14]
0x18002faa5  mov     rbx, [rsp+48h+arg_0]
0x18002faaa  neg     rax
0x18002faad  mov     rbp, [rsp+48h+arg_8]
0x18002fab2  mov     rsi, [rsp+48h+arg_10]
0x18002fab7  sbb     eax, eax
0x18002fab9  mov     rdi, [rsp+48h+arg_18]
0x18002fabe  not     eax
0x18002fac0  and     eax, 8007000Eh
0x18002fac5  add     rsp, 30h
0x18002fac9  pop     r15
0x18002facb  pop     r14
0x18002facd  pop     r12
0x18002facf  retn
0x18002fad0  mov     rcx, [rsp+48h]; this
0x18002fad5  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002fadc  mov     edx, 0DB5h; void *
0x18002fae1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
