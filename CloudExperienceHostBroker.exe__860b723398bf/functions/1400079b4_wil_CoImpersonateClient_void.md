# wil::CoImpersonateClient(void)

- ea: `0x1400079b4`
- end: `0x1400079ed`
- name: `?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ`
- size: `57`
- prototype: `_BYTE *__fastcall(_BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008ed0`

## callees

- `0x1400079b4`
- `0x14000923c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400079bd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400079bd`

## string_xrefs

- `0x1400079cc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_BYTE *__fastcall wil::CoImpersonateClient(_BYTE *a1)
{
  HRESULT v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14B1,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v4);
  *a1 = 1;
  return a1;
}

```

## disassembly

```asm
0x1400079b4  push    rbx
0x1400079b6  sub     rsp, 30h
0x1400079ba  mov     rbx, rcx
0x1400079bd  call    cs:__imp_CoImpersonateClient
0x1400079c3  test    eax, eax
0x1400079c5  jns     short loc_1400079E1
0x1400079c7  mov     rcx, [rsp+38h]; this
0x1400079cc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400079d3  mov     r9d, eax; char *
0x1400079d6  mov     edx, 14B1h; void *
0x1400079db  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400079e1  mov     byte ptr [rbx], 1
0x1400079e4  mov     rax, rbx
0x1400079e7  add     rsp, 30h
0x1400079eb  pop     rbx
0x1400079ec  retn
```
