# std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver,std::default_delete<NetSetup2::ClientDriver>>>>(std::unique_ptr<NetSetup2::ClientDriver,std::default_delete<NetSetup2::ClientDriver>> *,std::unique_ptr<NetSetup2::ClientDriver,std::default_delete<NetSetup2::ClientDriver>> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver,std::default_delete<NetSetup2::ClientDriver>>> &)

- ea: `0x180008380`
- end: `0x1800083b1`
- name: `??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000865c`
- `0x180008fb8`
- `0x1800094a4`
- `0x18000c5e0`
- `0x18000d878`
- `0x18001eb14`
- `0x180020384`
- `0x180022800`
- `0x18002d7d8`
- `0x18002d964`

## callees

- `0x180008380`
- `0x180008db0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(v3);
      v3 += 8;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180008380  cmp     rcx, rdx
0x180008383  jz      short locret_1800083B0
0x180008385  mov     [rsp+arg_0], rbx
0x18000838a  push    rdi
0x18000838b  sub     rsp, 20h
0x18000838f  mov     rdi, rdx
0x180008392  mov     rbx, rcx
0x180008395  mov     rcx, rbx
0x180008398  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x18000839d  add     rbx, 8
0x1800083a1  cmp     rbx, rdi
0x1800083a4  jnz     short loc_180008395
0x1800083a6  mov     rbx, [rsp+28h+arg_0]
0x1800083ab  add     rsp, 20h
0x1800083af  pop     rdi
0x1800083b0  retn
```
