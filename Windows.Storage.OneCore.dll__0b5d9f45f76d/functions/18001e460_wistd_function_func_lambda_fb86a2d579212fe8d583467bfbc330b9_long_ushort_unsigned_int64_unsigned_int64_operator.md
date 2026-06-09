# wistd::__function::__func<_lambda_fb86a2d579212fe8d583467bfbc330b9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18001e460`
- end: `0x18001e4c2`
- name: `??R?$__func@V_lambda_fb86a2d579212fe8d583467bfbc330b9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007f8c`
- `0x18001e460`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e482`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e482`

## string_xrefs

- `0x18001e497`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wistd::__function::__func<_lambda_fb86a2d579212fe8d583467bfbc330b9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
             v7);
  if ( FullPathNameW < v4 )
    *v5 = FullPathNameW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x18001e460  mov     [rsp+arg_0], rbx
0x18001e465  push    rdi
0x18001e466  sub     rsp, 20h
0x18001e46a  mov     rbx, [r8]
0x18001e46d  mov     rax, rdx
0x18001e470  mov     rcx, [rcx+8]
0x18001e474  mov     edx, ebx; nBufferLength
0x18001e476  mov     rdi, [r9]
0x18001e479  xor     r9d, r9d; lpFilePart
0x18001e47c  mov     r8, [rax]; lpBuffer
0x18001e47f  mov     rcx, [rcx]; lpFileName
0x18001e482  call    cs:__imp_GetFullPathNameW
0x18001e488  mov     eax, eax
0x18001e48a  mov     [rdi], rax
0x18001e48d  test    rax, rax
0x18001e490  jnz     short loc_18001E4AA
0x18001e492  mov     rcx, [rsp+28h]; this
0x18001e497  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e49e  mov     edx, 0AAh; void *
0x18001e4a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e4a8  jmp     short loc_18001E4B7
0x18001e4aa  cmp     rax, rbx
0x18001e4ad  jnb     short loc_18001E4B5
0x18001e4af  inc     rax
0x18001e4b2  mov     [rdi], rax
0x18001e4b5  xor     eax, eax
0x18001e4b7  mov     rbx, [rsp+28h+arg_0]
0x18001e4bc  add     rsp, 20h
0x18001e4c0  pop     rdi
0x18001e4c1  retn
```
