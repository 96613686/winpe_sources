# std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>::push_back(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> &&)

- ea: `0x140006f14`
- end: `0x140006f99`
- name: `?push_back@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003330`

## callees

- `0x140006d30`
- `0x140006f14`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::push_back(
        _QWORD *a1,
        __int64 *a2)
{
  bool v4; // al
  __int64 v5; // rcx
  __int64 v6; // rdi
  _QWORD *v7; // rdx
  __int64 result; // rax
  _QWORD *v9; // rcx

  v4 = (unsigned __int64)a2 < a1[1] && *a1 <= (unsigned __int64)a2;
  v5 = a1[2];
  if ( v4 )
  {
    v6 = ((__int64)a2 - *a1) >> 3;
    if ( a1[1] == v5 )
      std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Reserve((__int64)a1);
    v7 = (_QWORD *)a1[1];
    result = *(_QWORD *)(*a1 + 8 * v6);
    *(_QWORD *)(*a1 + 8 * v6) = 0;
    *v7 = result;
  }
  else
  {
    if ( a1[1] == v5 )
      std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Reserve((__int64)a1);
    v9 = (_QWORD *)a1[1];
    result = *a2;
    *a2 = 0;
    *v9 = result;
  }
  a1[1] += 8LL;
  return result;
}

```

## disassembly

```asm
0x140006f14  mov     [rsp+arg_0], rbx
0x140006f19  push    rdi
0x140006f1a  sub     rsp, 20h
0x140006f1e  mov     rdi, rdx
0x140006f21  mov     rbx, rcx
0x140006f24  cmp     rdx, [rcx+8]
0x140006f28  jnb     short loc_140006F33
0x140006f2a  cmp     [rcx], rdx
0x140006f2d  ja      short loc_140006F33
0x140006f2f  mov     al, 1
0x140006f31  jmp     short loc_140006F35
0x140006f33  xor     al, al
0x140006f35  mov     rcx, [rcx+10h]
0x140006f39  test    al, al
0x140006f3b  jz      short loc_140006F6A
0x140006f3d  sub     rdi, [rbx]
0x140006f40  sar     rdi, 3
0x140006f44  cmp     [rbx+8], rcx
0x140006f48  jnz     short loc_140006F52
0x140006f4a  mov     rcx, rbx
0x140006f4d  call    ?_Reserve@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Reserve(unsigned __int64)
0x140006f52  mov     rcx, [rbx]
0x140006f55  mov     rdx, [rbx+8]
0x140006f59  mov     rax, [rcx+rdi*8]
0x140006f5d  mov     qword ptr [rcx+rdi*8], 0
0x140006f65  mov     [rdx], rax
0x140006f68  jmp     short loc_140006F89
0x140006f6a  cmp     [rbx+8], rcx
0x140006f6e  jnz     short loc_140006F78
0x140006f70  mov     rcx, rbx
0x140006f73  call    ?_Reserve@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Reserve(unsigned __int64)
0x140006f78  mov     rcx, [rbx+8]
0x140006f7c  mov     rax, [rdi]
0x140006f7f  mov     qword ptr [rdi], 0
0x140006f86  mov     [rcx], rax
0x140006f89  add     qword ptr [rbx+8], 8
0x140006f8e  mov     rbx, [rsp+28h+arg_0]
0x140006f93  add     rsp, 20h
0x140006f97  pop     rdi
0x140006f98  retn
```
