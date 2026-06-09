# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000f0a4`
- end: `0x18000f16b`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ff50`
- `0x1800104a4`
- `0x180010848`
- `0x180011980`
- `0x180012dc0`
- `0x180013294`
- `0x18001338c`
- `0x18001340c`
- `0x1800134cc`
- `0x180015464`
- `0x180015660`
- `0x1800172d4`
- `0x18001742c`
- `0x180017c54`
- `0x180017e9c`
- `0x180018710`
- `0x18001bd50`
- `0x18001c74c`
- `0x18001cd54`
- `0x18001d188`
- `0x18001d454`
- `0x180020dc4`
- `0x18002bda8`
- `0x18002c0e0`
- `0x18002c41c`
- `0x18002c688`
- `0x18002c91c`
- `0x18002cab8`
- `0x18002cce0`

## callees

- `0x180004ff4`
- `0x18000df04`
- `0x18000f0a4`
- `0x18001393c`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  void *v7; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_OWORD *)a2;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(_OWORD **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    v6 = v4 | 7;
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( v6 < 0xA )
        v5 = 10;
    }
    v9 = v5;
    v7 = (void *)std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *(_QWORD *)(a1 + 24) = v9;
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 16) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *v2;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f0a4  mov     [rsp+arg_8], rbx
0x18000f0a9  mov     [rsp+arg_10], rsi
0x18000f0ae  push    rdi
0x18000f0af  sub     rsp, 20h
0x18000f0b3  mov     rsi, rdx
0x18000f0b6  xorps   xmm0, xmm0
0x18000f0b9  movups  xmmword ptr [rcx], xmm0
0x18000f0bc  mov     qword ptr [rcx+10h], 0
0x18000f0c4  mov     rbx, rcx
0x18000f0c7  mov     qword ptr [rcx+18h], 0
0x18000f0cf  mov     rdi, [rdx+10h]
0x18000f0d3  mov     edx, 7
0x18000f0d8  cmp     [rsi+18h], rdx
0x18000f0dc  jbe     short loc_18000F0E1
0x18000f0de  mov     rsi, [rsi]
0x18000f0e1  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000f0eb  cmp     rdi, rax
0x18000f0ee  ja      short loc_18000F165
0x18000f0f0  cmp     rdi, rdx
0x18000f0f3  ja      short loc_18000F106
0x18000f0f5  mov     [rcx+10h], rdi
0x18000f0f9  mov     [rcx+18h], rdx
0x18000f0fd  movups  xmm0, xmmword ptr [rsi]
0x18000f100  movdqu  xmmword ptr [rcx], xmm0
0x18000f104  jmp     short loc_18000F152
0x18000f106  mov     rcx, rdi
0x18000f109  or      rcx, rdx
0x18000f10c  cmp     rcx, rax
0x18000f10f  ja      short loc_18000F120
0x18000f111  mov     edx, 0Ah
0x18000f116  mov     rax, rcx
0x18000f119  cmp     rcx, rdx
0x18000f11c  cmovb   rax, rdx
0x18000f120  lea     rdx, [rsp+28h+arg_0]
0x18000f125  mov     [rsp+28h+arg_0], rax
0x18000f12a  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18000f12f  mov     rcx, [rsp+28h+arg_0]
0x18000f134  lea     r8, ds:2[rdi*2]; Size
0x18000f13c  mov     [rbx+18h], rcx
0x18000f140  mov     rdx, rsi; Src
0x18000f143  mov     rcx, rax; void *
0x18000f146  mov     [rbx], rax
0x18000f149  mov     [rbx+10h], rdi
0x18000f14d  call    memcpy_0
0x18000f152  mov     rsi, [rsp+28h+arg_10]
0x18000f157  mov     rax, rbx
0x18000f15a  mov     rbx, [rsp+28h+arg_8]
0x18000f15f  add     rsp, 20h
0x18000f163  pop     rdi
0x18000f164  retn
0x18000f165  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
