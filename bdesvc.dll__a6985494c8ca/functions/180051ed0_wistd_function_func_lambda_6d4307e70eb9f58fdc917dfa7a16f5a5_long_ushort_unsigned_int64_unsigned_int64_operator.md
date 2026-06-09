# wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180051ed0`
- end: `0x180051f2c`
- name: `??R?$__func@V_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, unsigned __int64 *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002b610`
- `0x180051ed0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180051ee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180051ee5`

## string_xrefs

- `0x180051f00`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_6d4307e70eb9f58fdc917dfa7a16f5a5_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  UINT SystemDirectoryW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  SystemDirectoryW = GetSystemDirectoryW(*a2, *a3);
  *v5 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x230,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v7);
  if ( SystemDirectoryW < v4 )
    *v5 = SystemDirectoryW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x180051ed0  mov     [rsp+arg_0], rbx
0x180051ed5  push    rdi
0x180051ed6  sub     rsp, 20h
0x180051eda  mov     rbx, [r8]
0x180051edd  mov     rcx, [rdx]; lpBuffer
0x180051ee0  mov     edx, ebx; uSize
0x180051ee2  mov     rdi, [r9]
0x180051ee5  call    cs:__imp_GetSystemDirectoryW
0x180051eec  nop     dword ptr [rax+rax+00h]
0x180051ef1  mov     eax, eax
0x180051ef3  mov     [rdi], rax
0x180051ef6  test    rax, rax
0x180051ef9  jnz     short loc_180051F13
0x180051efb  mov     rcx, [rsp+28h]; this
0x180051f00  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051f07  mov     edx, 230h; void *
0x180051f0c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051f11  jmp     short loc_180051F20
0x180051f13  cmp     rax, rbx
0x180051f16  jnb     short loc_180051F1E
0x180051f18  inc     rax
0x180051f1b  mov     [rdi], rax
0x180051f1e  xor     eax, eax
0x180051f20  mov     rbx, [rsp+28h+arg_0]
0x180051f25  add     rsp, 20h
0x180051f29  pop     rdi
0x180051f2a  retn
```
