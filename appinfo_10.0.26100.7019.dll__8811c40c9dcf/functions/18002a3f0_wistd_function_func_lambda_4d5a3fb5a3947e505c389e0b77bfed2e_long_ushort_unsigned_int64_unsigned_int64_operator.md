# wistd::__function::__func<_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18002a3f0`
- end: `0x18002a466`
- name: `??R?$__func@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x180018150`
- `0x18002a3f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002a41b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002a41b`

## string_xrefs

- `0x18002a438`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  DWORD FinalPathNameByHandleW; // eax
  const char *v7; // r9
  unsigned int v8; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(
                             **(HANDLE **)(a1 + 8),
                             *a2,
                             *a3,
                             **(_DWORD **)(a1 + 16) | **(_DWORD **)(a1 + 24));
  v8 = 0;
  *v5 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW )
  {
    if ( FinalPathNameByHandleW < v4 )
      *v5 = FinalPathNameByHandleW + 1LL;
  }
  else
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x36A,
                           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                           v7);
  }
  return v8;
}

```

## disassembly

```asm
0x18002a3f0  mov     [rsp+arg_0], rbx
0x18002a3f5  push    rdi
0x18002a3f6  sub     rsp, 20h
0x18002a3fa  mov     rax, [rcx+10h]
0x18002a3fe  mov     rbx, [r8]
0x18002a401  mov     r8, [rcx+18h]
0x18002a405  mov     rdi, [r9]
0x18002a408  mov     rcx, [rcx+8]
0x18002a40c  mov     rdx, [rdx]; lpszFilePath
0x18002a40f  mov     r9d, [r8]
0x18002a412  mov     r8d, ebx; cchFilePath
0x18002a415  or      r9d, [rax]; dwFlags
0x18002a418  mov     rcx, [rcx]; hFile
0x18002a41b  call    cs:__imp_GetFinalPathNameByHandleW
0x18002a422  nop     dword ptr [rax+rax+00h]
0x18002a427  mov     eax, eax
0x18002a429  xor     ecx, ecx
0x18002a42b  mov     [rdi], rax
0x18002a42e  test    rax, rax
0x18002a431  jnz     short loc_18002A44D
0x18002a433  mov     rcx, [rsp+28h]; this
0x18002a438  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a43f  mov     edx, 36Ah; void *
0x18002a444  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a449  mov     ecx, eax
0x18002a44b  jmp     short loc_18002A458
0x18002a44d  cmp     rax, rbx
0x18002a450  jnb     short loc_18002A458
0x18002a452  inc     rax
0x18002a455  mov     [rdi], rax
0x18002a458  mov     rbx, [rsp+28h+arg_0]
0x18002a45d  mov     eax, ecx
0x18002a45f  add     rsp, 20h
0x18002a463  pop     rdi
0x18002a464  retn
```
