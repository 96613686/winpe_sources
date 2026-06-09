# GetNewTaskFolder(Microsoft::WRL::ComPtr<ITaskService> const &)

- ea: `0x1800181c4`
- end: `0x18001822c`
- name: `?GetNewTaskFolder@@YA?AV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV?$ComPtr@UITaskService@@@23@@Z`
- size: `104`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cb18`

## callees

- `0x18000a7fc`
- `0x1800181c4`
- `0x18002a010`

## string_xrefs

- `0x18001821a`: `onecore\internal\shell\inc\taskutils.h`

## pseudocode

```c
_QWORD *__fastcall GetNewTaskFolder(_QWORD *a1, _QWORD *a2)
{
  int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)*a2 + 56LL))(*a2, 0, a1);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (int)"onecore\\internal\\shell\\inc\\taskutils.h",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800181c4  mov     [rsp+arg_0], rcx
0x1800181c9  push    rbx
0x1800181ca  sub     rsp, 30h
0x1800181ce  mov     rbx, rcx
0x1800181d1  mov     [rsp+38h+var_18], 0
0x1800181d9  mov     qword ptr [rcx], 0
0x1800181e0  mov     [rsp+38h+var_18], 1; int
0x1800181e8  mov     rcx, [rdx]
0x1800181eb  mov     rax, [rcx]
0x1800181ee  mov     [rsp+38h+arg_8], 0
0x1800181f7  mov     r8, rbx
0x1800181fa  xor     edx, edx
0x1800181fc  mov     rax, [rax+38h]
0x180018200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018205  mov     rcx, [rsp+38h]; this
0x18001820a  test    eax, eax
0x18001820c  js      short loc_180018217
0x18001820e  mov     rax, rbx
0x180018211  add     rsp, 30h
0x180018215  pop     rbx
0x180018216  retn
0x180018217  mov     r9d, eax; char *
0x18001821a  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x180018221  mov     edx, 24h ; '$'; void *
0x180018226  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
