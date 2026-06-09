# std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>::~unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>(void)

- ea: `0x180008db0`
- end: `0x180008dda`
- name: `??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x180007bfc`
- `0x180007d80`
- `0x180007f00`
- `0x180008084`
- `0x180008380`
- `0x180029f54`
- `0x18002a0f8`
- `0x18002e99e`

## callees

- `0x180002b90`
- `0x180008d94`
- `0x180008db0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(_QWORD **a1)
{
  _QWORD *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v1 + 1);
    operator delete(v1, 0x28u);
  }
}

```

## disassembly

```asm
0x180008db0  push    rbx
0x180008db2  sub     rsp, 20h
0x180008db6  mov     rbx, [rcx]
0x180008db9  test    rbx, rbx
0x180008dbc  jz      short loc_180008DD4
0x180008dbe  lea     rcx, [rbx+8]
0x180008dc2  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x180008dc7  mov     edx, 28h ; '('; unsigned __int64
0x180008dcc  mov     rcx, rbx; void *
0x180008dcf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008dd4  add     rsp, 20h
0x180008dd8  pop     rbx
0x180008dd9  retn
```
