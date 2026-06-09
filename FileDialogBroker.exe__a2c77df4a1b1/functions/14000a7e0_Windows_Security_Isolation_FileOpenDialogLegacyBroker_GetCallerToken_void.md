# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetCallerToken(void)

- ea: `0x14000a7e0`
- end: `0x14000a81f`
- name: `?GetCallerToken@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAXXZ`
- size: `63`
- prototype: `void *__fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a7e0`

## string_xrefs

- `0x14000a802`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
void *__fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetCallerToken(
        Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ((*((_QWORD *)this + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v2);
  return (void *)*((_QWORD *)this + 16);
}

```

## disassembly

```asm
0x14000a7e0  sub     rsp, 28h
0x14000a7e4  mov     rdx, [rcx+80h]
0x14000a7eb  mov     r10, [rsp+28h]
0x14000a7f0  lea     rax, [rdx+1]
0x14000a7f4  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000a7fa  jnz     short loc_14000A817
0x14000a7fc  mov     r9d, 80070006h; char *
0x14000a802  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a809  mov     edx, 1AAh; void *
0x14000a80e  mov     rcx, r10; this
0x14000a811  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a817  mov     rax, rdx
0x14000a81a  add     rsp, 28h
0x14000a81e  retn
```
