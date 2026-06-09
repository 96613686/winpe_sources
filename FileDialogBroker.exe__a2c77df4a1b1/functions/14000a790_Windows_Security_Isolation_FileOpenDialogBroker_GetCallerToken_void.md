# Windows::Security::Isolation::FileOpenDialogBroker::GetCallerToken(void)

- ea: `0x14000a790`
- end: `0x14000a7cc`
- name: `?GetCallerToken@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAXXZ`
- size: `60`
- prototype: `void *__fastcall(Windows::Security::Isolation::FileOpenDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a790`

## string_xrefs

- `0x14000a7af`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
void *__fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetCallerToken(
        Windows::Security::Isolation::FileOpenDialogBroker *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v2);
  return (void *)*((_QWORD *)this + 14);
}

```

## disassembly

```asm
0x14000a790  sub     rsp, 28h
0x14000a794  mov     rdx, [rcx+70h]
0x14000a798  mov     r10, [rsp+28h]
0x14000a79d  lea     rax, [rdx+1]
0x14000a7a1  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000a7a7  jnz     short loc_14000A7C4
0x14000a7a9  mov     r9d, 80070006h; char *
0x14000a7af  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a7b6  mov     edx, 86h; void *
0x14000a7bb  mov     rcx, r10; this
0x14000a7be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a7c4  mov     rax, rdx
0x14000a7c7  add     rsp, 28h
0x14000a7cb  retn
```
