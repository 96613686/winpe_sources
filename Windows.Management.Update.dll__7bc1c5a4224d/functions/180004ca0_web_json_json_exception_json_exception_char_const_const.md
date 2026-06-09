# web::json::json_exception::json_exception(char const * const)

- ea: `0x180004ca0`
- end: `0x180004cd1`
- name: `??0json_exception@json@web@@QEAA@QEBD@Z`
- size: `49`
- prototype: `web::json::json_exception *__fastcall(web::json::json_exception *this, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005cf0`
- `0x180005d30`
- `0x180005dd0`
- `0x180005e30`
- `0x180005e70`

## callees

- `0x1800210bc`

## pseudocode

```c
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const char *a2)
{
  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  std::string::string((char *)this + 24, a2);
  return this;
}

```

## disassembly

```asm
0x180004ca0  mov     [rsp+arg_0], rcx
0x180004ca5  push    rbx
0x180004ca6  sub     rsp, 20h
0x180004caa  mov     rbx, rcx
0x180004cad  xorps   xmm0, xmm0
0x180004cb0  movups  xmmword ptr [rcx+8], xmm0
0x180004cb4  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x180004cbb  mov     [rcx], rax
0x180004cbe  add     rcx, 18h
0x180004cc2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180004cc7  nop
0x180004cc8  mov     rax, rbx
0x180004ccb  add     rsp, 20h
0x180004ccf  pop     rbx
0x180004cd0  retn
```
