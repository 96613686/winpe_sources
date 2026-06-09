# xml_exception::~xml_exception(void)

- ea: `0x140011b08`
- end: `0x140011b24`
- name: `??1xml_exception@@UEAA@XZ`
- size: `28`
- prototype: `void __fastcall(xml_exception *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140011bb0`

## callees

- `0x14000a034`

## pseudocode

```c
void __fastcall xml_exception::~xml_exception(xml_exception *this)
{
  *(_QWORD *)this = &xml_exception::`vftable';
  Sharp::Util::standard_exception::~standard_exception(this);
}

```

## disassembly

```asm
0x140011b08  mov     [rsp+arg_0], rcx
0x140011b0d  sub     rsp, 28h
0x140011b11  lea     rax, ??_7xml_exception@@6B@; const xml_exception::`vftable'
0x140011b18  mov     [rcx], rax
0x140011b1b  add     rsp, 28h
0x140011b1f  jmp     ??1standard_exception@Util@Sharp@@UEAA@XZ; Sharp::Util::standard_exception::~standard_exception(void)
```
