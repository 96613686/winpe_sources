# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x180008c00`
- end: `0x180008ccc`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180008a90`
- `0x180008b20`
- `0x180009208`
- `0x180009d10`

## callees

- `0x1800077d8`
- `0x180008c00`
- `0x18000b37c`
- `0x18000bd94`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::path::path(
        std::filesystem::path *this,
        const struct std::filesystem::path *a2)
{
  const struct std::filesystem::path *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  std::filesystem::path *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = this;
  v2 = a2;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v4 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const struct std::filesystem::path **)a2;
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
    v9 = (std::filesystem::path *)v5;
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *((_QWORD *)this + 3) = v9;
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 2) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *((_QWORD *)this + 2) = v4;
    *((_QWORD *)this + 3) = 7;
    *(_OWORD *)this = *(_OWORD *)v2;
  }
  return this;
}

```

## disassembly

```asm
0x180008c00  mov     [rsp+arg_8], rbx
0x180008c05  mov     [rsp+arg_10], rsi
0x180008c0a  mov     [rsp+arg_0], rcx
0x180008c0f  push    rdi
0x180008c10  sub     rsp, 20h
0x180008c14  mov     rsi, rdx
0x180008c17  xorps   xmm0, xmm0
0x180008c1a  movups  xmmword ptr [rcx], xmm0
0x180008c1d  mov     qword ptr [rcx+10h], 0
0x180008c25  mov     rbx, rcx
0x180008c28  mov     qword ptr [rcx+18h], 0
0x180008c30  mov     rdi, [rdx+10h]
0x180008c34  mov     edx, 7
0x180008c39  cmp     [rsi+18h], rdx
0x180008c3d  jbe     short loc_180008C42
0x180008c3f  mov     rsi, [rsi]
0x180008c42  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008c4c  cmp     rdi, rax
0x180008c4f  ja      short loc_180008CC6
0x180008c51  cmp     rdi, rdx
0x180008c54  ja      short loc_180008C67
0x180008c56  mov     [rcx+10h], rdi
0x180008c5a  mov     [rcx+18h], rdx
0x180008c5e  movups  xmm0, xmmword ptr [rsi]
0x180008c61  movdqu  xmmword ptr [rcx], xmm0
0x180008c65  jmp     short loc_180008CB3
0x180008c67  mov     rcx, rdi
0x180008c6a  or      rcx, rdx
0x180008c6d  cmp     rcx, rax
0x180008c70  ja      short loc_180008C81
0x180008c72  mov     edx, 0Ah
0x180008c77  mov     rax, rcx
0x180008c7a  cmp     rcx, rdx
0x180008c7d  cmovb   rax, rdx
0x180008c81  lea     rdx, [rsp+28h+arg_0]
0x180008c86  mov     [rsp+28h+arg_0], rax
0x180008c8b  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180008c90  mov     rcx, [rsp+28h+arg_0]
0x180008c95  lea     r8, ds:2[rdi*2]; Size
0x180008c9d  mov     [rbx+18h], rcx
0x180008ca1  mov     rdx, rsi; Src
0x180008ca4  mov     rcx, rax; void *
0x180008ca7  mov     [rbx], rax
0x180008caa  mov     [rbx+10h], rdi
0x180008cae  call    memcpy_0
0x180008cb3  mov     rsi, [rsp+28h+arg_10]
0x180008cb8  mov     rax, rbx
0x180008cbb  mov     rbx, [rsp+28h+arg_8]
0x180008cc0  add     rsp, 20h
0x180008cc4  pop     rdi
0x180008cc5  retn
0x180008cc6  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
