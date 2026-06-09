# wistd::__function::__func<_lambda_b727b7dc3a79984c737ea01e3c3a200c_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140009f60`
- end: `0x140009fd0`
- name: `??R?$__func@V_lambda_b727b7dc3a79984c737ea01e3c3a200c_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, WCHAR **, DWORD *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140009f60`
- `0x1400136dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140009f92`
- `KERNEL32!GetLastError` at `0x140009f92`
- `KERNEL32!QueryFullProcessImageNameW` at `0x140009f88`
- `KERNEL32!QueryFullProcessImageNameW` at `0x140009f88`

## string_xrefs

- `0x140009fa2`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_b727b7dc3a79984c737ea01e3c3a200c_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        WCHAR **a2,
        DWORD *a3,
        __int64 **a4)
{
  DWORD v4; // eax
  DWORD *v6; // rdx
  HANDLE *v7; // rcx
  __int64 *v8; // rbx
  WCHAR *v9; // r8
  const char *v10; // r9
  __int64 v12; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD dwSize; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a3;
  v6 = *(DWORD **)(a1 + 16);
  v7 = *(HANDLE **)(a1 + 8);
  v8 = *a4;
  v9 = *a2;
  dwSize = v4;
  if ( QueryFullProcessImageNameW(*v7, *v6, v9, &dwSize) )
  {
    v12 = dwSize + 1LL;
  }
  else
  {
    if ( GetLastError() != 122 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1B9,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
               v10);
    v12 = 2LL * dwSize;
  }
  *v8 = v12;
  return 0;
}

```

## disassembly

```asm
0x140009f60  push    rbx
0x140009f62  sub     rsp, 20h
0x140009f66  mov     eax, [r8]
0x140009f69  mov     r10, rdx
0x140009f6c  mov     rdx, [rcx+10h]
0x140009f70  mov     rcx, [rcx+8]
0x140009f74  mov     rbx, [r9]
0x140009f77  lea     r9, [rsp+28h+dwSize]; lpdwSize
0x140009f7c  mov     r8, [r10]; lpExeName
0x140009f7f  mov     [rsp+28h+dwSize], eax
0x140009f83  mov     rcx, [rcx]; hProcess
0x140009f86  mov     edx, [rdx]; dwFlags
0x140009f88  call    cs:__imp_QueryFullProcessImageNameW
0x140009f8e  test    eax, eax
0x140009f90  jnz     short loc_140009FBE
0x140009f92  call    cs:__imp_GetLastError
0x140009f98  cmp     eax, 7Ah ; 'z'
0x140009f9b  jz      short loc_140009FB5
0x140009f9d  mov     rcx, [rsp+28h]; this
0x140009fa2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009fa9  mov     edx, 1B9h; void *
0x140009fae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009fb3  jmp     short loc_140009FCA
0x140009fb5  mov     eax, [rsp+28h+dwSize]
0x140009fb9  add     rax, rax
0x140009fbc  jmp     short loc_140009FC5
0x140009fbe  mov     eax, [rsp+28h+dwSize]
0x140009fc2  inc     rax
0x140009fc5  mov     [rbx], rax
0x140009fc8  xor     eax, eax
0x140009fca  add     rsp, 20h
0x140009fce  pop     rbx
0x140009fcf  retn
```
