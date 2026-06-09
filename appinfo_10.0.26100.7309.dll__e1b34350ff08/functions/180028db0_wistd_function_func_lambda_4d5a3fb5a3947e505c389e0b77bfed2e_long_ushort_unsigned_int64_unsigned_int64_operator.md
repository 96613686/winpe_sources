# wistd::__function::__func<_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180028db0`
- end: `0x180028e26`
- name: `??R?$__func@V_lambda_4d5a3fb5a3947e505c389e0b77bfed2e_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x180018400`
- `0x180028db0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028ddb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180028ddb`

## string_xrefs

- `0x180028df8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x180028db0  mov     [rsp+arg_0], rbx
0x180028db5  push    rdi
0x180028db6  sub     rsp, 20h
0x180028dba  mov     rax, [rcx+10h]
0x180028dbe  mov     rbx, [r8]
0x180028dc1  mov     r8, [rcx+18h]
0x180028dc5  mov     rdi, [r9]
0x180028dc8  mov     rcx, [rcx+8]
0x180028dcc  mov     rdx, [rdx]; lpszFilePath
0x180028dcf  mov     r9d, [r8]
0x180028dd2  mov     r8d, ebx; cchFilePath
0x180028dd5  or      r9d, [rax]; dwFlags
0x180028dd8  mov     rcx, [rcx]; hFile
0x180028ddb  call    cs:__imp_GetFinalPathNameByHandleW
0x180028de2  nop     dword ptr [rax+rax+00h]
0x180028de7  mov     eax, eax
0x180028de9  xor     ecx, ecx
0x180028deb  mov     [rdi], rax
0x180028dee  test    rax, rax
0x180028df1  jnz     short loc_180028E0D
0x180028df3  mov     rcx, [rsp+28h]; this
0x180028df8  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028dff  mov     edx, 36Ah; void *
0x180028e04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028e09  mov     ecx, eax
0x180028e0b  jmp     short loc_180028E18
0x180028e0d  cmp     rax, rbx
0x180028e10  jnb     short loc_180028E18
0x180028e12  inc     rax
0x180028e15  mov     [rdi], rax
0x180028e18  mov     rbx, [rsp+28h+arg_0]
0x180028e1d  mov     eax, ecx
0x180028e1f  add     rsp, 20h
0x180028e23  pop     rdi
0x180028e24  retn
```
