# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x1800326e0`
- end: `0x180032841`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060464`

## callees

- `0x1800326e0`
- `0x18005f4c0`
- `0x18006ca26`
- `0x18006cad0`
- `0x18009b79c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003280c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003280c`
- `KERNEL32!SetLastError` at `0x180032835`
- `KERNEL32!SetLastError` at `0x180032835`
- `KERNEL32!GetLastError` at `0x180032822`
- `KERNEL32!GetLastError` at `0x180032822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800327e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003282d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800327e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003282d`

## string_xrefs

- `0x18003270a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // r15
  __int64 v8; // rax
  char *i; // rdi
  __int64 v10; // rdi
  _WORD *v11; // rax
  _WORD *v12; // rbx
  size_t v13; // rdi
  void *v14; // rsi
  __int64 result; // rax
  DWORD LastError; // edi
  char v17; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  if ( a2 )
  {
    v8 = a3;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( i = a2; v8; --v8 )
    {
      if ( !*(_WORD *)i )
        break;
      i += 2;
    }
    v10 = (i - a2) >> 1;
  }
  else
  {
    v10 = a3;
  }
  if ( a3 == -1 )
    v4 = v10;
  v11 = CoTaskMemAlloc(2 * v4 + 2);
  v12 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v13 = 2 * v10;
      if ( v13 )
      {
        if ( 2 * v4 + 2 < v13 )
        {
          memset_0(v11, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v11, a2, v13);
        }
      }
      v12[v13 / 2] = 0;
    }
    else
    {
      *v11 = 0;
    }
    v12[v4] = 0;
  }
  if ( a1 != &v17 )
  {
    v14 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v14);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v12;
    v12 = 0;
  }
  if ( v12 )
    CoTaskMemFree(v12);
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x1800326e0  push    rbx
0x1800326e2  push    rbp
0x1800326e3  push    rsi
0x1800326e4  push    rdi
0x1800326e5  push    r14
0x1800326e7  push    r15
0x1800326e9  sub     rsp, 38h
0x1800326ed  mov     r15, r8
0x1800326f0  mov     rbp, rdx
0x1800326f3  mov     r14, rcx
0x1800326f6  test    rdx, rdx
0x1800326f9  jz      loc_1800327E9
0x1800326ff  xor     al, al
0x180032701  mov     rcx, [rsp+68h]; this
0x180032706  test    al, al
0x180032708  jz      short loc_18003271C
0x18003270a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180032711  mov     edx, 0F89h; void *
0x180032716  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003271c  test    rbp, rbp
0x18003271f  jz      loc_1800327FA
0x180032725  mov     rax, r15
0x180032728  mov     ecx, 7FFFFFFFh
0x18003272d  cmp     r15, rcx
0x180032730  cmovnb  rax, rcx
0x180032734  mov     rdi, rbp
0x180032737  test    rax, rax
0x18003273a  jz      short loc_180032750
0x18003273c  nop     dword ptr [rax+00h]
0x180032740  cmp     word ptr [rdi], 0
0x180032744  jz      short loc_180032750
0x180032746  add     rdi, 2
0x18003274a  sub     rax, 1
0x18003274e  jnz     short loc_180032740
0x180032750  sub     rdi, rbp
0x180032753  sar     rdi, 1
0x180032756  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18003275a  cmovz   r15, rdi
0x18003275e  lea     rsi, ds:2[r15*2]
0x180032766  mov     rcx, rsi; cb
0x180032769  call    cs:__imp_CoTaskMemAlloc
0x18003276f  mov     rbx, rax
0x180032772  test    rax, rax
0x180032775  jz      short loc_1800327A1
0x180032777  test    rbp, rbp
0x18003277a  jz      short loc_1800327D7
0x18003277c  add     rdi, rdi
0x18003277f  jz      short loc_180032794
0x180032781  mov     rcx, rax; void *
0x180032784  cmp     rsi, rdi
0x180032787  jb      short loc_180032802
0x180032789  mov     r8, rdi; Size
0x18003278c  mov     rdx, rbp; Src
0x18003278f  call    memcpy_0
0x180032794  xor     eax, eax
0x180032796  mov     [rdi+rbx], ax
0x18003279a  xor     eax, eax
0x18003279c  mov     [rbx+r15*2], ax
0x1800327a1  lea     rax, [rsp+68h+var_48]
0x1800327a6  cmp     r14, rax
0x1800327a9  jz      short loc_1800327B8
0x1800327ab  mov     rsi, [r14]
0x1800327ae  test    rsi, rsi
0x1800327b1  jnz     short loc_180032822
0x1800327b3  mov     [r14], rbx
0x1800327b6  xor     ebx, ebx
0x1800327b8  test    rbx, rbx
0x1800327bb  jnz     short loc_1800327DE
0x1800327bd  xor     eax, eax
0x1800327bf  mov     ecx, 8007000Eh
0x1800327c4  cmp     [r14], rax
0x1800327c7  cmovz   eax, ecx
0x1800327ca  add     rsp, 38h
0x1800327ce  pop     r15
0x1800327d0  pop     r14
0x1800327d2  pop     rdi
0x1800327d3  pop     rsi
0x1800327d4  pop     rbp
0x1800327d5  pop     rbx
0x1800327d6  retn
0x1800327d7  xor     eax, eax
0x1800327d9  mov     [rbx], ax
0x1800327dc  jmp     short loc_18003279A
0x1800327de  mov     rcx, rbx; pv
0x1800327e1  call    cs:__imp_CoTaskMemFree
0x1800327e7  jmp     short loc_1800327BD
0x1800327e9  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800327ed  jnz     loc_1800326FF
0x1800327f3  mov     al, 1
0x1800327f5  jmp     loc_180032701
0x1800327fa  mov     rdi, r15
0x1800327fd  jmp     loc_180032756
0x180032802  mov     r8, rsi; Size
0x180032805  xor     edx, edx; Val
0x180032807  call    memset_0
0x18003280c  call    cs:__imp__o__errno
0x180032812  mov     dword ptr [rax], 22h ; '"'
0x180032818  call    _invalid_parameter_noinfo
0x18003281d  jmp     loc_180032794
0x180032822  call    cs:__imp_GetLastError
0x180032828  mov     edi, eax
0x18003282a  mov     rcx, rsi; pv
0x18003282d  call    cs:__imp_CoTaskMemFree
0x180032833  mov     ecx, edi; dwErrCode
0x180032835  call    cs:__imp_SetLastError
0x18003283b  nop
0x18003283c  jmp     loc_1800327B3
```
