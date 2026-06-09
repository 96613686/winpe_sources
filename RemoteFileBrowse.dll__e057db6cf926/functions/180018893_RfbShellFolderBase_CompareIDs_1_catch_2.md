# _RfbShellFolderBase::CompareIDs_::_1_::catch$2

- ea: `0x180018893`
- end: `0x1800188c9`
- name: `_RfbShellFolderBase::CompareIDs_::_1_::catch$2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800070ac`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::CompareIDs_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x259,
                            (int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180018893  mov     [rsp+arg_8], rdx
0x180018898  push    rbp
0x180018899  sub     rsp, 30h
0x18001889d  mov     rbp, rdx
0x1800188a0  mov     rcx, [rbp+68h]; this
0x1800188a4  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x1800188ab  mov     edx, 259h; void *
0x1800188b0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800188b5  mov     [rbp+70h], eax
0x1800188b8  mov     rax, 0
0x1800188c2  add     rsp, 30h
0x1800188c6  pop     rbp
0x1800188c7  retn
```
