# _CommonUtil::CreateNewRefObject_MpConfigUtils::CSimpleMpConfig__::_1_::catch$1

- ea: `0x18000999f`
- end: `0x1800099c8`
- name: `_CommonUtil::CreateNewRefObject_MpConfigUtils::CSimpleMpConfig__::_1_::catch$1`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007cbc`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::CreateNewRefObject_MpConfigUtils::CSimpleMpConfig__::_1_::catch_1(
        CommonUtil *a1,
        const struct exception *a2)
{
  CommonUtil::HrFromStdException(a1, a2);
}

```

## disassembly

```asm
0x18000999f  mov     [rsp+arg_8], rdx
0x1800099a4  push    rbp
0x1800099a5  sub     rsp, 20h
0x1800099a9  mov     rbp, rdx
0x1800099ac  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@@@Z; CommonUtil::HrFromStdException(exception const &)
0x1800099b1  mov     [rbp+48h], eax
0x1800099b4  mov     [rbp+50h], eax
0x1800099b7  mov     rax, 0
0x1800099c1  add     rsp, 20h
0x1800099c5  pop     rbp
0x1800099c6  retn
```
