# std::filesystem::path::path(std::filesystem::path const &)

- ea: `0x1400084c4`
- end: `0x140008590`
- name: `??0path@filesystem@std@@QEAA@AEBV012@@Z`
- size: `204`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, const struct std::filesystem::path *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140008354`
- `0x1400083e4`
- `0x140008a04`
- `0x140009390`

## callees

- `0x140007020`
- `0x1400084c4`
- `0x14000a2ac`
- `0x14000ad14`

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
0x1400084c4  mov     [rsp+arg_8], rbx
0x1400084c9  mov     [rsp+arg_10], rsi
0x1400084ce  mov     [rsp+arg_0], rcx
0x1400084d3  push    rdi
0x1400084d4  sub     rsp, 20h
0x1400084d8  mov     rsi, rdx
0x1400084db  xorps   xmm0, xmm0
0x1400084de  movups  xmmword ptr [rcx], xmm0
0x1400084e1  mov     qword ptr [rcx+10h], 0
0x1400084e9  mov     rbx, rcx
0x1400084ec  mov     qword ptr [rcx+18h], 0
0x1400084f4  mov     rdi, [rdx+10h]
0x1400084f8  mov     edx, 7
0x1400084fd  cmp     [rsi+18h], rdx
0x140008501  jbe     short loc_140008506
0x140008503  mov     rsi, [rsi]
0x140008506  mov     rax, 7FFFFFFFFFFFFFFEh
0x140008510  cmp     rdi, rax
0x140008513  ja      short loc_14000858A
0x140008515  cmp     rdi, rdx
0x140008518  ja      short loc_14000852B
0x14000851a  mov     [rcx+10h], rdi
0x14000851e  mov     [rcx+18h], rdx
0x140008522  movups  xmm0, xmmword ptr [rsi]
0x140008525  movdqu  xmmword ptr [rcx], xmm0
0x140008529  jmp     short loc_140008577
0x14000852b  mov     rcx, rdi
0x14000852e  or      rcx, rdx
0x140008531  cmp     rcx, rax
0x140008534  ja      short loc_140008545
0x140008536  mov     edx, 0Ah
0x14000853b  mov     rax, rcx
0x14000853e  cmp     rcx, rdx
0x140008541  cmovb   rax, rdx
0x140008545  lea     rdx, [rsp+28h+arg_0]
0x14000854a  mov     [rsp+28h+arg_0], rax
0x14000854f  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140008554  mov     rcx, [rsp+28h+arg_0]
0x140008559  lea     r8, ds:2[rdi*2]; Size
0x140008561  mov     [rbx+18h], rcx
0x140008565  mov     rdx, rsi; Src
0x140008568  mov     rcx, rax; void *
0x14000856b  mov     [rbx], rax
0x14000856e  mov     [rbx+10h], rdi
0x140008572  call    memcpy_0
0x140008577  mov     rsi, [rsp+28h+arg_10]
0x14000857c  mov     rax, rbx
0x14000857f  mov     rbx, [rsp+28h+arg_8]
0x140008584  add     rsp, 20h
0x140008588  pop     rdi
0x140008589  retn
0x14000858a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
