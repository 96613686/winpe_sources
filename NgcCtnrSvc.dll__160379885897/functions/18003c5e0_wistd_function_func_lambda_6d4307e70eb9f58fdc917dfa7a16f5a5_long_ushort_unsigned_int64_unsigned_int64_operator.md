# wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18003c5e0`
- end: `0x18003c63c`
- name: `??R?$__func@V_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180022e68`
- `0x18003c5e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003c5f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003c5f5`

## string_xrefs

- `0x18003c610`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v7);
  if ( SystemDirectoryW < v4 )
    *v5 = SystemDirectoryW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18003c5e0  mov     [rsp+arg_0], rbx
0x18003c5e5  push    rdi
0x18003c5e6  sub     rsp, 20h
0x18003c5ea  mov     rbx, [r8]
0x18003c5ed  mov     rcx, [rdx]; lpBuffer
0x18003c5f0  mov     edx, ebx; uSize
0x18003c5f2  mov     rdi, [r9]
0x18003c5f5  call    cs:__imp_GetSystemDirectoryW
0x18003c5fc  nop     dword ptr [rax+rax+00h]
0x18003c601  mov     eax, eax
0x18003c603  mov     [rdi], rax
0x18003c606  test    rax, rax
0x18003c609  jnz     short loc_18003C623
0x18003c60b  mov     rcx, [rsp+28h]; this
0x18003c610  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c617  mov     edx, 230h; void *
0x18003c61c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c621  jmp     short loc_18003C630
0x18003c623  cmp     rax, rbx
0x18003c626  jnb     short loc_18003C62E
0x18003c628  inc     rax
0x18003c62b  mov     [rdi], rax
0x18003c62e  xor     eax, eax
0x18003c630  mov     rbx, [rsp+28h+arg_0]
0x18003c635  add     rsp, 20h
0x18003c639  pop     rdi
0x18003c63a  retn
```
