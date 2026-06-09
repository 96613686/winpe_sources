# wil::CoImpersonateClient(void)

- ea: `0x180027cb4`
- end: `0x180027ced`
- name: `?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035450`
- `0x1800356cc`
- `0x180035798`

## callees

- `0x18001cfb4`
- `0x180027cb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027cbd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180027cbd`

## string_xrefs

- `0x180027cd8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_BYTE *__fastcall wil::CoImpersonateClient(_BYTE *a1)
{
  HRESULT v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v4);
  *a1 = 1;
  return a1;
}

```

## disassembly

```asm
0x180027cb4  push    rbx
0x180027cb6  sub     rsp, 30h
0x180027cba  mov     rbx, rcx
0x180027cbd  call    cs:__imp_CoImpersonateClient
0x180027cc3  test    eax, eax
0x180027cc5  js      short loc_180027CD3
0x180027cc7  mov     byte ptr [rbx], 1
0x180027cca  mov     rax, rbx
0x180027ccd  add     rsp, 30h
0x180027cd1  pop     rbx
0x180027cd2  retn
0x180027cd3  mov     rcx, [rsp+38h]; this
0x180027cd8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027cdf  mov     r9d, eax; char *
0x180027ce2  mov     edx, 14B1h; void *
0x180027ce7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
