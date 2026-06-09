# std::vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>::push_back(std::tr1::shared_ptr<IRegistryKey> &&)

- ea: `0x1800211a8`
- end: `0x180021215`
- name: `?push_back@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAAX$$QEAV?$shared_ptr@VIRegistryKey@@@tr1@2@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800207f0`
- `0x1800219d0`

## callees

- `0x1800201ec`
- `0x18002101c`
- `0x1800211a8`

## pseudocode

```c
__int64 __fastcall std::vector<std::tr1::shared_ptr<IRegistryKey>>::push_back(
        unsigned __int64 *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  bool v4; // al
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdi
  __int64 result; // rax

  v2 = a2;
  v4 = a2 < a1[1] && *a1 <= a2;
  v5 = a1[2];
  if ( v4 )
  {
    v6 = a2 - *a1;
    if ( a1[1] == v5 )
      std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Reserve(a1);
    v2 = *a1 + (v6 & 0xFFFFFFFFFFFFFFF0uLL);
  }
  else if ( a1[1] == v5 )
  {
    std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Reserve(a1);
  }
  result = std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(a1[1], v2);
  a1[1] += 16LL;
  return result;
}

```

## disassembly

```asm
0x1800211a8  mov     [rsp+arg_0], rbx
0x1800211ad  push    rdi
0x1800211ae  sub     rsp, 20h
0x1800211b2  mov     rdi, rdx
0x1800211b5  mov     rbx, rcx
0x1800211b8  cmp     rdx, [rcx+8]
0x1800211bc  jnb     short loc_1800211C7
0x1800211be  cmp     [rcx], rdx
0x1800211c1  ja      short loc_1800211C7
0x1800211c3  mov     al, 1
0x1800211c5  jmp     short loc_1800211C9
0x1800211c7  xor     al, al
0x1800211c9  mov     rcx, [rcx+10h]
0x1800211cd  test    al, al
0x1800211cf  jz      short loc_1800211EB
0x1800211d1  sub     rdi, [rbx]
0x1800211d4  cmp     [rbx+8], rcx
0x1800211d8  jnz     short loc_1800211E2
0x1800211da  mov     rcx, rbx
0x1800211dd  call    ?_Reserve@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@IEAAX_K@Z; std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Reserve(unsigned __int64)
0x1800211e2  and     rdi, 0FFFFFFFFFFFFFFF0h
0x1800211e6  add     rdi, [rbx]
0x1800211e9  jmp     short loc_1800211F9
0x1800211eb  cmp     [rbx+8], rcx
0x1800211ef  jnz     short loc_1800211F9
0x1800211f1  mov     rcx, rbx
0x1800211f4  call    ?_Reserve@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@IEAAX_K@Z; std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Reserve(unsigned __int64)
0x1800211f9  mov     rcx, [rbx+8]
0x1800211fd  mov     rdx, rdi
0x180021200  call    ??0?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@$$QEAV012@@Z; std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(std::tr1::shared_ptr<IRegistryKey> &&)
0x180021205  add     qword ptr [rbx+8], 10h
0x18002120a  mov     rbx, [rsp+28h+arg_0]
0x18002120f  add     rsp, 20h
0x180021213  pop     rdi
0x180021214  retn
```
