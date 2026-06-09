# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch$44

- ea: `0x140011728`
- end: `0x140011758`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch$44`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000d588`

## pseudocode

```c
__int64 __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::catch_44(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 280), (void *)0x158, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x140011728  mov     [rsp+arg_8], rdx
0x14001172d  push    rbp
0x14001172e  sub     rsp, 30h
0x140011732  mov     rbp, rdx
0x140011735  mov     rcx, [rbp+118h]; this
0x14001173c  mov     edx, 158h; void *
0x140011741  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140011746  nop
0x140011747  mov     rax, 0
0x140011751  add     rsp, 30h
0x140011755  pop     rbp
0x140011756  retn
```
