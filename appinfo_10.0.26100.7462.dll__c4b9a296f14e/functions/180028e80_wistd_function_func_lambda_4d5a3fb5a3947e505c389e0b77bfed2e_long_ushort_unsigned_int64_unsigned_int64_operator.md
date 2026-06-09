# wistd::__function::__func<_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180028e80`
- end: `0x180028ef6`
- name: `??R?$__func@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x180018400`
- `0x180028e80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028eab`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028eab`

## string_xrefs

- `0x180028ec8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x180028e80  mov     [rsp+arg_0], rbx
0x180028e85  push    rdi
0x180028e86  sub     rsp, 20h
0x180028e8a  mov     rax, [rcx+10h]
0x180028e8e  mov     rbx, [r8]
0x180028e91  mov     r8, [rcx+18h]
0x180028e95  mov     rdi, [r9]
0x180028e98  mov     rcx, [rcx+8]
0x180028e9c  mov     rdx, [rdx]; lpszFilePath
0x180028e9f  mov     r9d, [r8]
0x180028ea2  mov     r8d, ebx; cchFilePath
0x180028ea5  or      r9d, [rax]; dwFlags
0x180028ea8  mov     rcx, [rcx]; hFile
0x180028eab  call    cs:__imp_GetFinalPathNameByHandleW
0x180028eb2  nop     dword ptr [rax+rax+00h]
0x180028eb7  mov     eax, eax
0x180028eb9  xor     ecx, ecx
0x180028ebb  mov     [rdi], rax
0x180028ebe  test    rax, rax
0x180028ec1  jnz     short loc_180028EDD
0x180028ec3  mov     rcx, [rsp+28h]; this
0x180028ec8  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028ecf  mov     edx, 36Ah; void *
0x180028ed4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028ed9  mov     ecx, eax
0x180028edb  jmp     short loc_180028EE8
0x180028edd  cmp     rax, rbx
0x180028ee0  jnb     short loc_180028EE8
0x180028ee2  inc     rax
0x180028ee5  mov     [rdi], rax
0x180028ee8  mov     rbx, [rsp+28h+arg_0]
0x180028eed  mov     eax, ecx
0x180028eef  add     rsp, 20h
0x180028ef3  pop     rdi
0x180028ef4  retn
```
