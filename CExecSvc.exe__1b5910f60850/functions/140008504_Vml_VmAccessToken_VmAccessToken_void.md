# Vml::VmAccessToken::~VmAccessToken(void)

- ea: `0x140008504`
- end: `0x140008536`
- name: `??1VmAccessToken@Vml@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400224b0`
- `0x140022998`

## callees

- `0x140008504`
- `0x140009490`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008510`

## string_xrefs

- `0x140008524`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmAccessToken::~VmAccessToken(void **this)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *this;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1004,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v2);
  }
}

```

## disassembly

```asm
0x140008504  sub     rsp, 28h
0x140008508  mov     rcx, [rcx]; hObject
0x14000850b  test    rcx, rcx
0x14000850e  jz      short loc_14000851A
0x140008510  call    cs:__imp_CloseHandle
0x140008516  test    eax, eax
0x140008518  jz      short loc_14000851F
0x14000851a  add     rsp, 28h
0x14000851e  retn
0x14000851f  mov     rcx, [rsp+28h]; this
0x140008524  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000852b  mov     edx, 1004h; void *
0x140008530  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
