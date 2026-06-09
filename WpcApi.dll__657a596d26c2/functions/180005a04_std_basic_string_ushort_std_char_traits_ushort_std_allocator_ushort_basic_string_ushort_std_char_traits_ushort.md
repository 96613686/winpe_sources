# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180005a04`
- end: `0x180005acb`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `35`
- callee_count: `4`
- tags: ``

## callers

- `0x180002a70`
- `0x180002af0`
- `0x180002b70`
- `0x180002bf0`
- `0x180002c70`
- `0x180002cf0`
- `0x180006ee0`
- `0x18000a01c`
- `0x18000b808`
- `0x18000bc98`
- `0x18000bdd0`
- `0x18000c414`
- `0x18000d150`
- `0x180010488`
- `0x180014480`
- `0x180014c24`
- `0x180014d98`
- `0x180015a54`
- `0x180015ca4`
- `0x180015d60`
- `0x1800165f0`
- `0x180016974`
- `0x180016bfc`
- `0x18001757c`
- `0x180017ee0`
- `0x1800183a4`
- `0x1800184e8`
- `0x180018a70`
- `0x180018d94`
- `0x18001cad0`
- `0x180024814`
- `0x180024b1c`
- `0x180026404`
- `0x1800264e0`
- `0x180028e1c`

## callees

- `0x18000490d`
- `0x1800058d8`
- `0x180005a04`
- `0x18000a998`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
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
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, &v9);
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
0x180005a04  mov     [rsp+arg_8], rbx
0x180005a09  mov     [rsp+arg_10], rsi
0x180005a0e  push    rdi
0x180005a0f  sub     rsp, 20h
0x180005a13  mov     rsi, rdx
0x180005a16  xorps   xmm0, xmm0
0x180005a19  movups  xmmword ptr [rcx], xmm0
0x180005a1c  mov     qword ptr [rcx+10h], 0
0x180005a24  mov     rbx, rcx
0x180005a27  mov     qword ptr [rcx+18h], 0
0x180005a2f  mov     rdi, [rdx+10h]
0x180005a33  mov     edx, 7
0x180005a38  cmp     [rsi+18h], rdx
0x180005a3c  jbe     short loc_180005A41
0x180005a3e  mov     rsi, [rsi]
0x180005a41  mov     rax, 7FFFFFFFFFFFFFFEh
0x180005a4b  cmp     rdi, rax
0x180005a4e  ja      short loc_180005AC5
0x180005a50  cmp     rdi, rdx
0x180005a53  ja      short loc_180005A66
0x180005a55  mov     [rcx+10h], rdi
0x180005a59  mov     [rcx+18h], rdx
0x180005a5d  movups  xmm0, xmmword ptr [rsi]
0x180005a60  movdqu  xmmword ptr [rcx], xmm0
0x180005a64  jmp     short loc_180005AB2
0x180005a66  mov     rcx, rdi
0x180005a69  or      rcx, rdx
0x180005a6c  cmp     rcx, rax
0x180005a6f  ja      short loc_180005A80
0x180005a71  mov     edx, 0Ah
0x180005a76  mov     rax, rcx
0x180005a79  cmp     rcx, rdx
0x180005a7c  cmovb   rax, rdx
0x180005a80  lea     rdx, [rsp+28h+arg_0]
0x180005a85  mov     [rsp+28h+arg_0], rax
0x180005a8a  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180005a8f  mov     rcx, [rsp+28h+arg_0]
0x180005a94  lea     r8, ds:2[rdi*2]; Size
0x180005a9c  mov     [rbx+18h], rcx
0x180005aa0  mov     rdx, rsi; Src
0x180005aa3  mov     rcx, rax; void *
0x180005aa6  mov     [rbx], rax
0x180005aa9  mov     [rbx+10h], rdi
0x180005aad  call    memcpy_0
0x180005ab2  mov     rsi, [rsp+28h+arg_10]
0x180005ab7  mov     rax, rbx
0x180005aba  mov     rbx, [rsp+28h+arg_8]
0x180005abf  add     rsp, 20h
0x180005ac3  pop     rdi
0x180005ac4  retn
0x180005ac5  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
