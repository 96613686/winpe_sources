# wistd::__function::__func<_lambda_c9e6b286004cfa29dd84f46700aaa2e8_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000c230`
- end: `0x18000c2a0`
- name: `??R?$__func@V_lambda_c9e6b286004cfa29dd84f46700aaa2e8_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c230`
- `0x1800166ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c262`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000c258`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000c258`

## string_xrefs

- `0x18000c272`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_c9e6b286004cfa29dd84f46700aaa2e8_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
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
0x18000c230  push    rbx
0x18000c232  sub     rsp, 20h
0x18000c236  mov     eax, [r8]
0x18000c239  mov     r10, rdx
0x18000c23c  mov     rdx, [rcx+10h]
0x18000c240  mov     rcx, [rcx+8]
0x18000c244  mov     rbx, [r9]
0x18000c247  lea     r9, [rsp+28h+dwSize]; lpdwSize
0x18000c24c  mov     r8, [r10]; lpExeName
0x18000c24f  mov     [rsp+28h+dwSize], eax
0x18000c253  mov     rcx, [rcx]; hProcess
0x18000c256  mov     edx, [rdx]; dwFlags
0x18000c258  call    cs:__imp_QueryFullProcessImageNameW
0x18000c25e  test    eax, eax
0x18000c260  jnz     short loc_18000C28E
0x18000c262  call    cs:__imp_GetLastError
0x18000c268  cmp     eax, 7Ah ; 'z'
0x18000c26b  jz      short loc_18000C285
0x18000c26d  mov     rcx, [rsp+28h]; this
0x18000c272  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c279  mov     edx, 1B9h; void *
0x18000c27e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c283  jmp     short loc_18000C29A
0x18000c285  mov     eax, [rsp+28h+dwSize]
0x18000c289  add     rax, rax
0x18000c28c  jmp     short loc_18000C295
0x18000c28e  mov     eax, [rsp+28h+dwSize]
0x18000c292  inc     rax
0x18000c295  mov     [rbx], rax
0x18000c298  xor     eax, eax
0x18000c29a  add     rsp, 20h
0x18000c29e  pop     rbx
0x18000c29f  retn
```
