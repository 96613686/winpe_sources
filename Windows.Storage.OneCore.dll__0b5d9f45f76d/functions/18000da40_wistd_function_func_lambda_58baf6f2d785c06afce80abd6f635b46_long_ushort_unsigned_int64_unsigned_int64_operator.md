# wistd::__function::__func<_lambda_58baf6f2d785c06afce80abd6f635b46_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000da40`
- end: `0x18000daab`
- name: `??R?$__func@V_lambda_58baf6f2d785c06afce80abd6f635b46_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `107`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x180007f8c`
- `0x18000da40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000da6b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000da6b`

## string_xrefs

- `0x18000da80`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wistd::__function::__func<_lambda_58baf6f2d785c06afce80abd6f635b46_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  DWORD FinalPathNameByHandleW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(
                             **(HANDLE **)(a1 + 8),
                             *a2,
                             *a3,
                             **(_DWORD **)(a1 + 16) | **(_DWORD **)(a1 + 24));
  *v5 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x36E,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
             v7);
  if ( FinalPathNameByHandleW < v4 )
    *v5 = FinalPathNameByHandleW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18000da40  mov     [rsp+arg_0], rbx
0x18000da45  push    rdi
0x18000da46  sub     rsp, 20h
0x18000da4a  mov     rax, [rcx+10h]
0x18000da4e  mov     rbx, [r8]
0x18000da51  mov     r8, [rcx+18h]
0x18000da55  mov     rdi, [r9]
0x18000da58  mov     rcx, [rcx+8]
0x18000da5c  mov     rdx, [rdx]; lpszFilePath
0x18000da5f  mov     r9d, [r8]
0x18000da62  mov     r8d, ebx; cchFilePath
0x18000da65  or      r9d, [rax]; dwFlags
0x18000da68  mov     rcx, [rcx]; hFile
0x18000da6b  call    cs:__imp_GetFinalPathNameByHandleW
0x18000da71  mov     eax, eax
0x18000da73  mov     [rdi], rax
0x18000da76  test    rax, rax
0x18000da79  jnz     short loc_18000DA93
0x18000da7b  mov     rcx, [rsp+28h]; this
0x18000da80  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000da87  mov     edx, 36Eh; void *
0x18000da8c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000da91  jmp     short loc_18000DAA0
0x18000da93  cmp     rax, rbx
0x18000da96  jnb     short loc_18000DA9E
0x18000da98  inc     rax
0x18000da9b  mov     [rdi], rax
0x18000da9e  xor     eax, eax
0x18000daa0  mov     rbx, [rsp+28h+arg_0]
0x18000daa5  add     rsp, 20h
0x18000daa9  pop     rdi
0x18000daaa  retn
```
