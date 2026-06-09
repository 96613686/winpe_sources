# std::unique_ptr<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>,std::default_delete<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>>>::~unique_ptr<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>,std::default_delete<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>>>(void)

- ea: `0x180008d94`
- end: `0x180008daa`
- name: `??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `24`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008db0`
- `0x1800092bc`
- `0x18000c5e0`
- `0x180012190`
- `0x180013af4`
- `0x1800193d4`
- `0x18001aad4`
- `0x18001ac78`
- `0x18001cd80`
- `0x18001de84`
- `0x18001e3a8`
- `0x18001e828`
- `0x18001ea44`
- `0x18001f2e4`
- `0x180020384`
- `0x1800207bc`
- `0x180021350`
- `0x18002266c`
- `0x180022fd4`
- `0x180023650`
- `0x180023af4`
- `0x18002a400`
- `0x18002a48c`
- `0x18002bc40`

## callees

- `0x180008d94`
- `0x1800095d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<std::vector<NetSetup2::Property>>::operator()();
  return result;
}

```

## disassembly

```asm
0x180008d94  sub     rsp, 28h
0x180008d98  mov     rdx, [rcx]
0x180008d9b  test    rdx, rdx
0x180008d9e  jz      short loc_180008DA5
0x180008da0  call    ??R?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@std@@QEBAXPEAV?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@1@@Z; std::default_delete<std::vector<NetSetup2::Property>>::operator()(std::vector<NetSetup2::Property> *)
0x180008da5  add     rsp, 28h
0x180008da9  retn
```
