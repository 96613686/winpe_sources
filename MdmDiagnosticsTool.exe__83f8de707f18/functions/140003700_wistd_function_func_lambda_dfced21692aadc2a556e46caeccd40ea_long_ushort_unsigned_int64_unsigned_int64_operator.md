# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140003700`
- end: `0x140003769`
- name: `??R?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003700`
- `0x1400065c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003722`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003722`

## string_xrefs

- `0x14000373d`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
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
0x140003700  mov     [rsp+arg_0], rbx
0x140003705  push    rdi
0x140003706  sub     rsp, 20h
0x14000370a  mov     rbx, [r8]
0x14000370d  mov     rax, rdx
0x140003710  mov     rcx, [rcx+8]
0x140003714  mov     edx, ebx; nBufferLength
0x140003716  mov     rdi, [r9]
0x140003719  xor     r9d, r9d; lpFilePart
0x14000371c  mov     r8, [rax]; lpBuffer
0x14000371f  mov     rcx, [rcx]; lpFileName
0x140003722  call    cs:__imp_GetFullPathNameW
0x140003729  nop     dword ptr [rax+rax+00h]
0x14000372e  mov     eax, eax
0x140003730  mov     [rdi], rax
0x140003733  test    rax, rax
0x140003736  jnz     short loc_140003750
0x140003738  mov     rcx, [rsp+28h]; this
0x14000373d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003744  mov     edx, 0AAh; void *
0x140003749  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000374e  jmp     short loc_14000375D
0x140003750  cmp     rax, rbx
0x140003753  jnb     short loc_14000375B
0x140003755  inc     rax
0x140003758  mov     [rdi], rax
0x14000375b  xor     eax, eax
0x14000375d  mov     rbx, [rsp+28h+arg_0]
0x140003762  add     rsp, 20h
0x140003766  pop     rdi
0x140003767  retn
```
