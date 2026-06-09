# wistd::__function::__func<_lambda_04af553ba9ebd5bc26243fae3d5304c2_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x1800133a0`
- end: `0x1800133f5`
- name: `??R?$__func@V_lambda_04af553ba9ebd5bc26243fae3d5304c2_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `85`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000970c`
- `0x1800133a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800133b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800133b5`

## string_xrefs

- `0x1800133ca`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_04af553ba9ebd5bc26243fae3d5304c2_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  UINT SystemDirectoryW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  SystemDirectoryW = GetSystemDirectoryW(*a2, *a3);
  *v5 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x230,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v7);
  if ( SystemDirectoryW < v4 )
    *v5 = SystemDirectoryW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x1800133a0  mov     [rsp+arg_0], rbx
0x1800133a5  push    rdi
0x1800133a6  sub     rsp, 20h
0x1800133aa  mov     rbx, [r8]
0x1800133ad  mov     rcx, [rdx]; lpBuffer
0x1800133b0  mov     edx, ebx; uSize
0x1800133b2  mov     rdi, [r9]
0x1800133b5  call    cs:__imp_GetSystemDirectoryW
0x1800133bb  mov     eax, eax
0x1800133bd  mov     [rdi], rax
0x1800133c0  test    rax, rax
0x1800133c3  jnz     short loc_1800133DD
0x1800133c5  mov     rcx, [rsp+28h]; this
0x1800133ca  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800133d1  mov     edx, 230h; void *
0x1800133d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800133db  jmp     short loc_1800133EA
0x1800133dd  cmp     rax, rbx
0x1800133e0  jnb     short loc_1800133E8
0x1800133e2  inc     rax
0x1800133e5  mov     [rdi], rax
0x1800133e8  xor     eax, eax
0x1800133ea  mov     rbx, [rsp+28h+arg_0]
0x1800133ef  add     rsp, 20h
0x1800133f3  pop     rdi
0x1800133f4  retn
```
