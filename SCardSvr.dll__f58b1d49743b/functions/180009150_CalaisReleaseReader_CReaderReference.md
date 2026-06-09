# CalaisReleaseReader(CReaderReference * *)

- ea: `0x180009150`
- end: `0x180009188`
- name: `?CalaisReleaseReader@@YAXPEAPEAVCReaderReference@@@Z`
- size: `56`
- prototype: `void __fastcall(CReaderProxy ***)`
- caller_count: `11`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006030`
- `0x18000a310`
- `0x1800331de`
- `0x180033211`
- `0x1800337f0`
- `0x1800339f0`
- `0x180033a50`
- `0x180033cf0`
- `0x180033da0`
- `0x18003432d`
- `0x180034609`

## callees

- `0x180009150`
- `0x180009190`
- `0x18001c370`

## pseudocode

```c
void __fastcall CalaisReleaseReader(CReaderProxy ***a1)
{
  CReaderProxy **v2; // rbx

  v2 = *a1;
  if ( *a1 )
  {
    CReaderProxy::Release(*v2);
    operator delete(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180009150  mov     [rsp+arg_0], rbx
0x180009155  push    rdi
0x180009156  sub     rsp, 20h
0x18000915a  mov     rdi, rcx
0x18000915d  mov     rbx, [rcx]
0x180009160  test    rbx, rbx
0x180009163  jz      short loc_18000917D
0x180009165  mov     rcx, [rbx]; this
0x180009168  call    ?Release@CReaderProxy@@QEAAXXZ; CReaderProxy::Release(void)
0x18000916d  nop
0x18000916e  mov     rcx, rbx; Block
0x180009171  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009176  mov     qword ptr [rdi], 0
0x18000917d  mov     rbx, [rsp+28h+arg_0]
0x180009182  add     rsp, 20h
0x180009186  pop     rdi
0x180009187  retn
```
