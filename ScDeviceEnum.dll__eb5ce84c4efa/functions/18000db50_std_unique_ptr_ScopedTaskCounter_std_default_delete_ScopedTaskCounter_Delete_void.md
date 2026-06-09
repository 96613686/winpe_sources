# std::unique_ptr<ScopedTaskCounter,std::default_delete<ScopedTaskCounter>>::_Delete(void)

- ea: `0x18000db50`
- end: `0x18000db73`
- name: `?_Delete@?$unique_ptr@VScopedTaskCounter@@U?$default_delete@VScopedTaskCounter@@@std@@@std@@AEAAXXZ`
- size: `35`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18000cad0`
- `0x18000cb00`
- `0x18000eabc`

## callees

- `0x180007bb4`
- `0x18000db50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000db67`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db67`

## pseudocode

```c
void __fastcall std::unique_ptr<ScopedTaskCounter>::_Delete(void **a1)
{
  void *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CTaskCounter::Decrement();
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000db50  push    rbx
0x18000db52  sub     rsp, 20h
0x18000db56  mov     rbx, [rcx]
0x18000db59  test    rbx, rbx
0x18000db5c  jz      short loc_18000DB6D
0x18000db5e  call    ?Decrement@CTaskCounter@@SAJXZ; CTaskCounter::Decrement(void)
0x18000db63  nop
0x18000db64  mov     rcx, rbx
0x18000db67  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000db6d  add     rsp, 20h
0x18000db71  pop     rbx
0x18000db72  retn
```
