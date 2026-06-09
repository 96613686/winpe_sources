# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000ea00`
- end: `0x18000ea62`
- name: `??R?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ea00`
- `0x180010f34`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000ea22`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000ea22`

## string_xrefs

- `0x18000ea37`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
0x18000ea00  mov     [rsp+arg_0], rbx
0x18000ea05  push    rdi
0x18000ea06  sub     rsp, 20h
0x18000ea0a  mov     rbx, [r8]
0x18000ea0d  mov     rax, rdx
0x18000ea10  mov     rcx, [rcx+8]
0x18000ea14  mov     edx, ebx; nBufferLength
0x18000ea16  mov     rdi, [r9]
0x18000ea19  xor     r9d, r9d; lpFilePart
0x18000ea1c  mov     r8, [rax]; lpBuffer
0x18000ea1f  mov     rcx, [rcx]; lpFileName
0x18000ea22  call    cs:__imp_GetFullPathNameW
0x18000ea28  mov     eax, eax
0x18000ea2a  mov     [rdi], rax
0x18000ea2d  test    rax, rax
0x18000ea30  jnz     short loc_18000EA4A
0x18000ea32  mov     rcx, [rsp+28h]; this
0x18000ea37  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ea3e  mov     edx, 0AAh; void *
0x18000ea43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ea48  jmp     short loc_18000EA57
0x18000ea4a  cmp     rax, rbx
0x18000ea4d  jnb     short loc_18000EA55
0x18000ea4f  inc     rax
0x18000ea52  mov     [rdi], rax
0x18000ea55  xor     eax, eax
0x18000ea57  mov     rbx, [rsp+28h+arg_0]
0x18000ea5c  add     rsp, 20h
0x18000ea60  pop     rdi
0x18000ea61  retn
```
