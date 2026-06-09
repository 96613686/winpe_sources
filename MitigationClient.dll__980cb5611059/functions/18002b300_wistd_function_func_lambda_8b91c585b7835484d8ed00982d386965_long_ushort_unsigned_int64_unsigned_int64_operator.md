# wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18002b300`
- end: `0x18002b362`
- name: `??R?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001206c`
- `0x18002b300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b322`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b322`

## string_xrefs

- `0x18002b337`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

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
0x18002b300  mov     [rsp+arg_0], rbx
0x18002b305  push    rdi
0x18002b306  sub     rsp, 20h
0x18002b30a  mov     rbx, [r8]
0x18002b30d  mov     rax, rdx
0x18002b310  mov     rcx, [rcx+8]
0x18002b314  mov     edx, ebx; nBufferLength
0x18002b316  mov     rdi, [r9]
0x18002b319  xor     r9d, r9d; lpFilePart
0x18002b31c  mov     r8, [rax]; lpBuffer
0x18002b31f  mov     rcx, [rcx]; lpFileName
0x18002b322  call    cs:__imp_GetFullPathNameW
0x18002b328  mov     eax, eax
0x18002b32a  mov     [rdi], rax
0x18002b32d  test    rax, rax
0x18002b330  jnz     short loc_18002B34A
0x18002b332  mov     rcx, [rsp+28h]; this
0x18002b337  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b33e  mov     edx, 0AAh; void *
0x18002b343  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b348  jmp     short loc_18002B357
0x18002b34a  cmp     rax, rbx
0x18002b34d  jnb     short loc_18002B355
0x18002b34f  inc     rax
0x18002b352  mov     [rdi], rax
0x18002b355  xor     eax, eax
0x18002b357  mov     rbx, [rsp+28h+arg_0]
0x18002b35c  add     rsp, 20h
0x18002b360  pop     rdi
0x18002b361  retn
```
