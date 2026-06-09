# _anonymous_namespace_::NtPathFromWin32

- ea: `0x18002a568`
- end: `0x18002a5ce`
- name: `_anonymous_namespace_::NtPathFromWin32`
- size: `102`
- prototype: `_OWORD *__fastcall(_OWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x18002a568`
- `0x180047b74`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002a59a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002a59a`

## string_xrefs

- `0x18002a5b2`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
_OWORD *__fastcall anonymous_namespace_::NtPathFromWin32(_OWORD *a1, __int64 a2)
{
  int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(a2, a1, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      (const char *)(unsigned int)v3,
      1);
  return a1;
}

```

## disassembly

```asm
0x18002a568  mov     [rsp+arg_0], rcx
0x18002a56d  push    rbx
0x18002a56e  sub     rsp, 30h
0x18002a572  mov     rax, rdx
0x18002a575  mov     rbx, rcx
0x18002a578  mov     [rsp+38h+var_18], 0
0x18002a580  xorps   xmm0, xmm0
0x18002a583  movups  xmmword ptr [rcx], xmm0
0x18002a586  mov     [rsp+38h+var_18], 1; int
0x18002a58e  xor     r9d, r9d
0x18002a591  xor     r8d, r8d
0x18002a594  mov     rdx, rcx
0x18002a597  mov     rcx, rax
0x18002a59a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002a5a1  nop     dword ptr [rax+rax+00h]
0x18002a5a6  test    eax, eax
0x18002a5a8  jns     short loc_18002A5C4
0x18002a5aa  mov     rcx, [rsp+38h]; this
0x18002a5af  mov     r9d, eax; char *
0x18002a5b2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a5b9  mov     edx, 129h; void *
0x18002a5be  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002a5c4  mov     rax, rbx
0x18002a5c7  add     rsp, 30h
0x18002a5cb  pop     rbx
0x18002a5cc  retn
```
