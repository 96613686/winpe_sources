# CommonUtil::MpCommonConfigGetHook(CommonUtil::IMpCommonConfigHook * *)

- ea: `0x1400024c0`
- end: `0x1400024e5`
- name: `?MpCommonConfigGetHook@CommonUtil@@YAXPEAPEAUIMpCommonConfigHook@1@@Z`
- size: `37`
- prototype: `void __fastcall(CommonUtil *__hidden this, struct CommonUtil::IMpCommonConfigHook **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400051d0`

## callees

- `0x140002d42`
- `0x140024c40`

## pseudocode

```c
void __fastcall CommonUtil::MpCommonConfigGetHook(CommonUtil *this, struct CommonUtil::IMpCommonConfigHook **a2)
{
  __int64 v3; // rax

  v3 = MpUtilsExportFunctions_0(this, a2);
  (*(void (__fastcall **)(CommonUtil *))(v3 + 232))(this);
}

```

## disassembly

```asm
0x1400024c0  push    rbx
0x1400024c2  sub     rsp, 20h
0x1400024c6  mov     rbx, rcx
0x1400024c9  call    MpUtilsExportFunctions_0
0x1400024ce  mov     rcx, rbx
0x1400024d1  mov     rax, [rax+0E8h]
0x1400024d8  call    cs:__guard_dispatch_icall_fptr
0x1400024de  nop
0x1400024df  add     rsp, 20h
0x1400024e3  pop     rbx
0x1400024e4  retn
```
