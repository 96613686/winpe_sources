# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18001b920`
- end: `0x18001b982`
- name: `??R?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800089c4`
- `0x18001b920`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b942`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b942`

## string_xrefs

- `0x18001b957`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  DWORD FullPathNameW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  FullPathNameW = GetFullPathNameW(**(LPCWSTR **)(a1 + 8), *a3, *a2, 0);
  *v5 = FullPathNameW;
  if ( !FullPathNameW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAA,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             v7);
  if ( FullPathNameW < v4 )
    *v5 = FullPathNameW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18001b920  mov     [rsp+arg_0], rbx
0x18001b925  push    rdi
0x18001b926  sub     rsp, 20h
0x18001b92a  mov     rbx, [r8]
0x18001b92d  mov     rax, rdx
0x18001b930  mov     rcx, [rcx+8]
0x18001b934  mov     edx, ebx; nBufferLength
0x18001b936  mov     rdi, [r9]
0x18001b939  xor     r9d, r9d; lpFilePart
0x18001b93c  mov     r8, [rax]; lpBuffer
0x18001b93f  mov     rcx, [rcx]; lpFileName
0x18001b942  call    cs:__imp_GetFullPathNameW
0x18001b948  mov     eax, eax
0x18001b94a  mov     [rdi], rax
0x18001b94d  test    rax, rax
0x18001b950  jnz     short loc_18001B96A
0x18001b952  mov     rcx, [rsp+28h]; this
0x18001b957  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b95e  mov     edx, 0AAh; void *
0x18001b963  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b968  jmp     short loc_18001B977
0x18001b96a  cmp     rax, rbx
0x18001b96d  jnb     short loc_18001B975
0x18001b96f  inc     rax
0x18001b972  mov     [rdi], rax
0x18001b975  xor     eax, eax
0x18001b977  mov     rbx, [rsp+28h+arg_0]
0x18001b97c  add     rsp, 20h
0x18001b980  pop     rdi
0x18001b981  retn
```
