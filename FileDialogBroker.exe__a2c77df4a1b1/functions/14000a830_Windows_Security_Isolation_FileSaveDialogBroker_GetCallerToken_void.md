# Windows::Security::Isolation::FileSaveDialogBroker::GetCallerToken(void)

- ea: `0x14000a830`
- end: `0x14000a86c`
- name: `?GetCallerToken@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAXXZ`
- size: `60`
- prototype: `void *__fastcall(Windows::Security::Isolation::FileSaveDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a830`

## string_xrefs

- `0x14000a84f`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
void *__fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetCallerToken(
        Windows::Security::Isolation::FileSaveDialogBroker *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v2);
  return (void *)*((_QWORD *)this + 14);
}

```

## disassembly

```asm
0x14000a830  sub     rsp, 28h
0x14000a834  mov     rdx, [rcx+70h]
0x14000a838  mov     r10, [rsp+28h]
0x14000a83d  lea     rax, [rdx+1]
0x14000a841  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000a847  jnz     short loc_14000A864
0x14000a849  mov     r9d, 80070006h; char *
0x14000a84f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a856  mov     edx, 117h; void *
0x14000a85b  mov     rcx, r10; this
0x14000a85e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a864  mov     rax, rdx
0x14000a867  add     rsp, 28h
0x14000a86b  retn
```
