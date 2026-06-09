# std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(void * *)

- ea: `0x140007010`
- end: `0x140007038`
- name: `?reset@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@QEAAXPEAPEAX@Z`
- size: `40`
- prototype: `BOOL __fastcall(HANDLE **, HANDLE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006000`
- `0x140006154`
- `0x1400064f8`

## callees

- `0x140006858`
- `0x140007010`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(HANDLE **a1, HANDLE *a2)
{
  BOOL result; // eax

  if ( a2 != *a1 )
  {
    result = std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(a1);
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x140007010  mov     [rsp+arg_0], rbx
0x140007015  push    rdi
0x140007016  sub     rsp, 20h
0x14000701a  mov     rdi, rdx
0x14000701d  mov     rbx, rcx
0x140007020  cmp     rdx, [rcx]
0x140007023  jz      short loc_14000702D
0x140007025  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x14000702a  mov     [rbx], rdi
0x14000702d  mov     rbx, [rsp+28h+arg_0]
0x140007032  add     rsp, 20h
0x140007036  pop     rdi
0x140007037  retn
```
