# std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)

- ea: `0x140006fa0`
- end: `0x140006fd0`
- name: `?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z`
- size: `48`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022ac`
- `0x1400023d0`
- `0x1400024d4`
- `0x140003330`

## callees

- `0x140006fa0`
- `0x140008ef4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( a2 != v4 )
  {
    if ( v4 )
      result = AiFree(v4);
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x140006fa0  mov     [rsp+arg_0], rbx
0x140006fa5  push    rdi
0x140006fa6  sub     rsp, 20h
0x140006faa  mov     rbx, rdx
0x140006fad  mov     rdi, rcx
0x140006fb0  mov     rcx, [rcx]
0x140006fb3  cmp     rdx, rcx
0x140006fb6  jz      short loc_140006FC5
0x140006fb8  test    rcx, rcx
0x140006fbb  jz      short loc_140006FC2
0x140006fbd  call    AiFree
0x140006fc2  mov     [rdi], rbx
0x140006fc5  mov     rbx, [rsp+28h+arg_0]
0x140006fca  add     rsp, 20h
0x140006fce  pop     rdi
0x140006fcf  retn
```
