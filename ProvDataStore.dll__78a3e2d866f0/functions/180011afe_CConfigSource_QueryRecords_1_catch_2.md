# _CConfigSource::QueryRecords_::_1_::catch$2

- ea: `0x180011afe`
- end: `0x180011b37`
- name: `_CConfigSource::QueryRecords_::_1_::catch$2`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009fd8`

## pseudocode

```c
__int64 __fastcall CConfigSource::QueryRecords_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x14C,
                            (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastore.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180011afe  mov     [rsp+arg_8], rdx
0x180011b03  push    rbp
0x180011b04  sub     rsp, 30h
0x180011b08  mov     rbp, rdx
0x180011b0b  mov     rcx, [rbp+58h]; this
0x180011b0f  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011b16  mov     edx, 14Ch; void *
0x180011b1b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180011b20  mov     [rbp+80h], eax
0x180011b26  mov     rax, 0
0x180011b30  add     rsp, 30h
0x180011b34  pop     rbp
0x180011b35  retn
```
