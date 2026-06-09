# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x1800203e0`
- end: `0x18002054e`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `366`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056d8c`

## callees

- `0x1800203e0`
- `0x180051492`
- `0x180051524`
- `0x180056c06`
- `0x180058ac4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002051a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002051a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002053b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002053b`

## string_xrefs

- `0x1800204fe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rbx
  __int64 v7; // r15
  SIZE_T v8; // r14
  char *v9; // rax
  char *v10; // rdi
  size_t v11; // rbx
  void *v12; // rbp
  __int64 result; // rax
  __int64 v14; // rax
  char *v15; // rbx
  DWORD LastError; // ebx
  char v17; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v14 = a3;
    v15 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v14 = 0x7FFFFFFF;
    for ( ; v14; --v14 )
    {
      if ( !*(_WORD *)v15 )
        break;
      v15 += 2;
    }
    v6 = (v15 - a2) >> 1;
  }
  else
  {
    v6 = a3;
  }
  if ( a3 == -1 )
    a3 = v6;
  v7 = 2 * a3;
  v8 = 2 * a3 + 2;
  v9 = (char *)CoTaskMemAlloc(v8);
  v10 = v9;
  if ( v9 )
  {
    if ( a2 )
    {
      v11 = 2 * v6;
      if ( v11 )
      {
        if ( v8 < v11 )
        {
          memset_0(v9, 0, v8);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v9, a2, v11);
        }
      }
      *(_WORD *)&v10[v11] = 0;
    }
    else
    {
      *(_WORD *)v9 = 0;
    }
    *(_WORD *)&v10[v7] = 0;
  }
  if ( a1 == &v17 )
  {
    if ( v10 )
      CoTaskMemFree(v10);
  }
  else
  {
    v12 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v12);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v10;
  }
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x1800203e0  push    rbp
0x1800203e2  push    rsi
0x1800203e3  sub     rsp, 38h
0x1800203e7  mov     rbp, rdx
0x1800203ea  mov     rsi, rcx
0x1800203ed  test    rdx, rdx
0x1800203f0  jz      loc_1800204EF
0x1800203f6  mov     [rsp+48h+arg_0], rbx
0x1800203fb  mov     [rsp+48h+arg_8], rdi
0x180020400  mov     [rsp+48h+arg_10], r14
0x180020405  mov     [rsp+48h+var_18], r15
0x18002040a  test    rbp, rbp
0x18002040d  jnz     loc_1800204AD
0x180020413  mov     rbx, r8
0x180020416  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002041a  cmovz   r8, rbx
0x18002041e  lea     r15, [r8+r8]
0x180020422  lea     r14, [r15+2]
0x180020426  mov     rcx, r14; cb
0x180020429  call    cs:__imp_CoTaskMemAlloc
0x18002042f  mov     rdi, rax
0x180020432  test    rax, rax
0x180020435  jz      short loc_180020465
0x180020437  test    rbp, rbp
0x18002043a  jz      short loc_1800204A6
0x18002043c  add     rbx, rbx
0x18002043f  jz      short loc_180020458
0x180020441  mov     rcx, rax; void *
0x180020444  cmp     r14, rbx
0x180020447  jb      loc_180020510
0x18002044d  mov     r8, rbx; Size
0x180020450  mov     rdx, rbp; Src
0x180020453  call    memcpy_0
0x180020458  xor     eax, eax
0x18002045a  mov     [rbx+rdi], ax
0x18002045e  xor     eax, eax
0x180020460  mov     [r15+rdi], ax
0x180020465  mov     r15, [rsp+48h+var_18]
0x18002046a  lea     rax, [rsp+48h+var_28]
0x18002046f  mov     r14, [rsp+48h+arg_10]
0x180020474  cmp     rsi, rax
0x180020477  jz      short loc_1800204DF
0x180020479  mov     rbp, [rsi]
0x18002047c  test    rbp, rbp
0x18002047f  jnz     loc_180020530
0x180020485  mov     [rsi], rdi
0x180020488  mov     rdi, [rsp+48h+arg_8]
0x18002048d  xor     eax, eax
0x18002048f  cmp     [rsi], rax
0x180020492  mov     ecx, 8007000Eh
0x180020497  mov     rbx, [rsp+48h+arg_0]
0x18002049c  cmovz   eax, ecx
0x18002049f  add     rsp, 38h
0x1800204a3  pop     rsi
0x1800204a4  pop     rbp
0x1800204a5  retn
0x1800204a6  xor     eax, eax
0x1800204a8  mov     [rdi], ax
0x1800204ab  jmp     short loc_18002045E
0x1800204ad  mov     ecx, 7FFFFFFFh
0x1800204b2  mov     rax, r8
0x1800204b5  cmp     r8, rcx
0x1800204b8  mov     rbx, rbp
0x1800204bb  cmovnb  rax, rcx
0x1800204bf  test    rax, rax
0x1800204c2  jz      short loc_1800204D4
0x1800204c4  cmp     word ptr [rbx], 0
0x1800204c8  jz      short loc_1800204D4
0x1800204ca  add     rbx, 2
0x1800204ce  sub     rax, 1
0x1800204d2  jnz     short loc_1800204C4
0x1800204d4  sub     rbx, rbp
0x1800204d7  sar     rbx, 1
0x1800204da  jmp     loc_180020416
0x1800204df  test    rdi, rdi
0x1800204e2  jz      short loc_180020488
0x1800204e4  mov     rcx, rdi; pv
0x1800204e7  call    cs:__imp_CoTaskMemFree
0x1800204ed  jmp     short loc_180020488
0x1800204ef  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800204f3  jnz     loc_1800203F6
0x1800204f9  mov     rcx, [rsp+48h]; this
0x1800204fe  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020505  mov     edx, 0F89h; void *
0x18002050a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180020510  mov     r8, r14; Size
0x180020513  xor     edx, edx; Val
0x180020515  call    memset_0
0x18002051a  call    cs:__imp__o__errno
0x180020520  mov     dword ptr [rax], 22h ; '"'
0x180020526  call    _invalid_parameter_noinfo
0x18002052b  jmp     loc_180020458
0x180020530  call    cs:__imp_GetLastError
0x180020536  mov     rcx, rbp; pv
0x180020539  mov     ebx, eax
0x18002053b  call    cs:__imp_CoTaskMemFree
0x180020541  mov     ecx, ebx; dwErrCode
0x180020543  call    cs:__imp_SetLastError
0x180020549  jmp     loc_180020485
```
