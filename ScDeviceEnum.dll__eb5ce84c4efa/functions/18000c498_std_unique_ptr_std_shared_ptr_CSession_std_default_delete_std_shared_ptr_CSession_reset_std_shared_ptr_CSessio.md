# std::unique_ptr<std::shared_ptr<CSession>,std::default_delete<std::shared_ptr<CSession>>>::reset(std::shared_ptr<CSession> *)

- ea: `0x18000c498`
- end: `0x18000c4c0`
- name: `?reset@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@QEAAXPEAV?$shared_ptr@VCSession@@@2@@Z`
- size: `40`
- prototype: `void __fastcall(_QWORD **, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b4a0`
- `0x18000bb00`

## callees

- `0x18000bedc`
- `0x18000c498`

## pseudocode

```c
void __fastcall std::unique_ptr<std::shared_ptr<CSession>>::reset(_QWORD **a1, _QWORD *a2)
{
  if ( a2 != *a1 )
  {
    std::unique_ptr<std::shared_ptr<CSession>>::_Delete(a1);
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x18000c498  mov     [rsp+arg_0], rbx
0x18000c49d  push    rdi
0x18000c49e  sub     rsp, 20h
0x18000c4a2  mov     rdi, rdx
0x18000c4a5  mov     rbx, rcx
0x18000c4a8  cmp     rdx, [rcx]
0x18000c4ab  jz      short loc_18000C4B5
0x18000c4ad  call    ?_Delete@?$unique_ptr@V?$shared_ptr@VCSession@@@std@@U?$default_delete@V?$shared_ptr@VCSession@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::shared_ptr<CSession>>::_Delete(void)
0x18000c4b2  mov     [rbx], rdi
0x18000c4b5  mov     rbx, [rsp+28h+arg_0]
0x18000c4ba  add     rsp, 20h
0x18000c4be  pop     rdi
0x18000c4bf  retn
```
