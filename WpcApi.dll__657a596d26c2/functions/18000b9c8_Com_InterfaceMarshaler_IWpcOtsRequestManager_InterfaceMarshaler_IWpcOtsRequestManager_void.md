# Com::InterfaceMarshaler<IWpcOtsRequestManager>::~InterfaceMarshaler<IWpcOtsRequestManager>(void)

- ea: `0x18000b9c8`
- end: `0x18000b9f8`
- name: `??1?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d140`

## callees

- `0x18000b9c8`
- `0x18000bbac`
- `0x180022e90`

## pseudocode

```c
__int64 __fastcall Com::InterfaceMarshaler<IWpcOtsRequestManager>::~InterfaceMarshaler<IWpcOtsRequestManager>(
        _QWORD *a1)
{
  _QWORD *v1; // rbx

  try
  {
    v1 = a1;
    if ( a1[1] != *a1 )
      Com::ReleaseMarshalData();
  }
  catch ( std::exception )
  {
    v1 = a1;
  }
  v1 = a1;
}

```

## disassembly

```asm
0x18000b9c8  mov     [rsp+arg_0], rcx
0x18000b9cd  push    rbx
0x18000b9ce  sub     rsp, 20h
0x18000b9d2  mov     rbx, rcx
0x18000b9d5  mov     rax, [rcx+8]
0x18000b9d9  cmp     rax, [rcx]
0x18000b9dc  jz      short loc_18000B9E4
0x18000b9de  call    ?ReleaseMarshalData@Com@@YAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Com::ReleaseMarshalData(std::vector<uchar> const &)
0x18000b9e3  nop
0x18000b9e4  jmp     short loc_18000B9EB
0x18000b9e6  mov     rbx, [rsp+28h+arg_0]
0x18000b9eb  mov     rcx, rbx
0x18000b9ee  add     rsp, 20h
0x18000b9f2  pop     rbx
0x18000b9f3  jmp     ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
```
