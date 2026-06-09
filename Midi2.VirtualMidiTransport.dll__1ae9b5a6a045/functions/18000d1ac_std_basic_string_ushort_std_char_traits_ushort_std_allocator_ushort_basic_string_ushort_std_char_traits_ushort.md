# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000d1ac`
- end: `0x18000d273`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d8e8`
- `0x18000d9b4`
- `0x18000e0a4`
- `0x18000e840`
- `0x18000eae0`
- `0x18000ec98`
- `0x1800116e0`
- `0x1800117d8`
- `0x180011858`
- `0x180011918`
- `0x1800136f0`
- `0x180014830`
- `0x180014ab0`
- `0x1800159c8`
- `0x180016348`
- `0x180016740`
- `0x180016bec`
- `0x180017014`
- `0x180017670`
- `0x18001b094`
- `0x18001b1b0`
- `0x18001b770`
- `0x18001d680`

## callees

- `0x180004688`
- `0x18000cad0`
- `0x18000d1ac`
- `0x180011a4c`

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
0x18000d1ac  mov     [rsp+arg_8], rbx
0x18000d1b1  mov     [rsp+arg_10], rsi
0x18000d1b6  push    rdi
0x18000d1b7  sub     rsp, 20h
0x18000d1bb  mov     rsi, rdx
0x18000d1be  xorps   xmm0, xmm0
0x18000d1c1  movups  xmmword ptr [rcx], xmm0
0x18000d1c4  mov     qword ptr [rcx+10h], 0
0x18000d1cc  mov     rbx, rcx
0x18000d1cf  mov     qword ptr [rcx+18h], 0
0x18000d1d7  mov     rdi, [rdx+10h]
0x18000d1db  mov     edx, 7
0x18000d1e0  cmp     [rsi+18h], rdx
0x18000d1e4  jbe     short loc_18000D1E9
0x18000d1e6  mov     rsi, [rsi]
0x18000d1e9  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000d1f3  cmp     rdi, rax
0x18000d1f6  ja      short loc_18000D26D
0x18000d1f8  cmp     rdi, rdx
0x18000d1fb  ja      short loc_18000D20E
0x18000d1fd  mov     [rcx+10h], rdi
0x18000d201  mov     [rcx+18h], rdx
0x18000d205  movups  xmm0, xmmword ptr [rsi]
0x18000d208  movdqu  xmmword ptr [rcx], xmm0
0x18000d20c  jmp     short loc_18000D25A
0x18000d20e  mov     rcx, rdi
0x18000d211  or      rcx, rdx
0x18000d214  cmp     rcx, rax
0x18000d217  ja      short loc_18000D228
0x18000d219  mov     edx, 0Ah
0x18000d21e  mov     rax, rcx
0x18000d221  cmp     rcx, rdx
0x18000d224  cmovb   rax, rdx
0x18000d228  lea     rdx, [rsp+28h+arg_0]
0x18000d22d  mov     [rsp+28h+arg_0], rax
0x18000d232  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18000d237  mov     rcx, [rsp+28h+arg_0]
0x18000d23c  lea     r8, ds:2[rdi*2]; Size
0x18000d244  mov     [rbx+18h], rcx
0x18000d248  mov     rdx, rsi; Src
0x18000d24b  mov     rcx, rax; void *
0x18000d24e  mov     [rbx], rax
0x18000d251  mov     [rbx+10h], rdi
0x18000d255  call    memcpy_0
0x18000d25a  mov     rsi, [rsp+28h+arg_10]
0x18000d25f  mov     rax, rbx
0x18000d262  mov     rbx, [rsp+28h+arg_8]
0x18000d267  add     rsp, 20h
0x18000d26b  pop     rdi
0x18000d26c  retn
0x18000d26d  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
