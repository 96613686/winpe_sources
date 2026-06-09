# wistd::__function::__func<_lambda_065b1782e7f1b5e3112f0bb3307328ee_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180028b30`
- end: `0x180028b9b`
- name: `??R?$__func@V_lambda_065b1782e7f1b5e3112f0bb3307328ee_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x18000aaf4`
- `0x180028b30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028b5b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028b5b`

## string_xrefs

- `0x180028b70`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_065b1782e7f1b5e3112f0bb3307328ee_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
0x180028b30  mov     [rsp+arg_0], rbx
0x180028b35  push    rdi
0x180028b36  sub     rsp, 20h
0x180028b3a  mov     rax, [rcx+10h]
0x180028b3e  mov     rbx, [r8]
0x180028b41  mov     r8, [rcx+18h]
0x180028b45  mov     rdi, [r9]
0x180028b48  mov     rcx, [rcx+8]
0x180028b4c  mov     rdx, [rdx]; lpszFilePath
0x180028b4f  mov     r9d, [r8]
0x180028b52  mov     r8d, ebx; cchFilePath
0x180028b55  or      r9d, [rax]; dwFlags
0x180028b58  mov     rcx, [rcx]; hFile
0x180028b5b  call    cs:__imp_GetFinalPathNameByHandleW
0x180028b61  mov     eax, eax
0x180028b63  mov     [rdi], rax
0x180028b66  test    rax, rax
0x180028b69  jnz     short loc_180028B83
0x180028b6b  mov     rcx, [rsp+28h]; this
0x180028b70  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028b77  mov     edx, 36Eh; void *
0x180028b7c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028b81  jmp     short loc_180028B90
0x180028b83  cmp     rax, rbx
0x180028b86  jnb     short loc_180028B8E
0x180028b88  inc     rax
0x180028b8b  mov     [rdi], rax
0x180028b8e  xor     eax, eax
0x180028b90  mov     rbx, [rsp+28h+arg_0]
0x180028b95  add     rsp, 20h
0x180028b99  pop     rdi
0x180028b9a  retn
```
