# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140003670`
- end: `0x1400036d2`
- name: `??R?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003670`
- `0x140006224`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003692`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003692`

## string_xrefs

- `0x1400036a7`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x140003670  mov     [rsp+arg_0], rbx
0x140003675  push    rdi
0x140003676  sub     rsp, 20h
0x14000367a  mov     rbx, [r8]
0x14000367d  mov     rax, rdx
0x140003680  mov     rcx, [rcx+8]
0x140003684  mov     edx, ebx; nBufferLength
0x140003686  mov     rdi, [r9]
0x140003689  xor     r9d, r9d; lpFilePart
0x14000368c  mov     r8, [rax]; lpBuffer
0x14000368f  mov     rcx, [rcx]; lpFileName
0x140003692  call    cs:__imp_GetFullPathNameW
0x140003698  mov     eax, eax
0x14000369a  mov     [rdi], rax
0x14000369d  test    rax, rax
0x1400036a0  jnz     short loc_1400036BA
0x1400036a2  mov     rcx, [rsp+28h]; this
0x1400036a7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400036ae  mov     edx, 0AAh; void *
0x1400036b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400036b8  jmp     short loc_1400036C7
0x1400036ba  cmp     rax, rbx
0x1400036bd  jnb     short loc_1400036C5
0x1400036bf  inc     rax
0x1400036c2  mov     [rdi], rax
0x1400036c5  xor     eax, eax
0x1400036c7  mov     rbx, [rsp+28h+arg_0]
0x1400036cc  add     rsp, 20h
0x1400036d0  pop     rdi
0x1400036d1  retn
```
