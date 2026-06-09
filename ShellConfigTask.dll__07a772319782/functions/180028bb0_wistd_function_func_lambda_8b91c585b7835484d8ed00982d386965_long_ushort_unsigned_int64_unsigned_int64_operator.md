# wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180028bb0`
- end: `0x180028c12`
- name: `??R?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000aaf4`
- `0x180028bb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180028bd2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180028bd2`

## string_xrefs

- `0x180028be7`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
0x180028bb0  mov     [rsp+arg_0], rbx
0x180028bb5  push    rdi
0x180028bb6  sub     rsp, 20h
0x180028bba  mov     rbx, [r8]
0x180028bbd  mov     rax, rdx
0x180028bc0  mov     rcx, [rcx+8]
0x180028bc4  mov     edx, ebx; nBufferLength
0x180028bc6  mov     rdi, [r9]
0x180028bc9  xor     r9d, r9d; lpFilePart
0x180028bcc  mov     r8, [rax]; lpBuffer
0x180028bcf  mov     rcx, [rcx]; lpFileName
0x180028bd2  call    cs:__imp_GetFullPathNameW
0x180028bd8  mov     eax, eax
0x180028bda  mov     [rdi], rax
0x180028bdd  test    rax, rax
0x180028be0  jnz     short loc_180028BFA
0x180028be2  mov     rcx, [rsp+28h]; this
0x180028be7  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028bee  mov     edx, 0AAh; void *
0x180028bf3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028bf8  jmp     short loc_180028C07
0x180028bfa  cmp     rax, rbx
0x180028bfd  jnb     short loc_180028C05
0x180028bff  inc     rax
0x180028c02  mov     [rdi], rax
0x180028c05  xor     eax, eax
0x180028c07  mov     rbx, [rsp+28h+arg_0]
0x180028c0c  add     rsp, 20h
0x180028c10  pop     rdi
0x180028c11  retn
```
