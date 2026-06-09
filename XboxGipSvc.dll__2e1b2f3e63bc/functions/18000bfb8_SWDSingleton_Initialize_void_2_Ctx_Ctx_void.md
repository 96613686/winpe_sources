# `SWDSingleton::Initialize(void)'::`2'::Ctx::~Ctx(void)

- ea: `0x18000bfb8`
- end: `0x18000bfeb`
- name: `??1Ctx@?1??Initialize@SWDSingleton@@AEAAJXZ@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001174b`

## callees

- `0x180009260`
- `0x18000bfb8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bfc5`

## string_xrefs

- `0x18000bfd9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall `SWDSingleton::Initialize'::`2'::Ctx::~Ctx(__int64 a1)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)(a1 + 8);
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v2);
  }
}

```

## disassembly

```asm
0x18000bfb8  sub     rsp, 28h
0x18000bfbc  mov     rcx, [rcx+8]; hObject
0x18000bfc0  test    rcx, rcx
0x18000bfc3  jz      short loc_18000BFCF
0x18000bfc5  call    cs:__imp_CloseHandle
0x18000bfcb  test    eax, eax
0x18000bfcd  jz      short loc_18000BFD4
0x18000bfcf  add     rsp, 28h
0x18000bfd3  retn
0x18000bfd4  mov     rcx, [rsp+28h]; this
0x18000bfd9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bfe0  mov     edx, 0A0Bh; void *
0x18000bfe5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
