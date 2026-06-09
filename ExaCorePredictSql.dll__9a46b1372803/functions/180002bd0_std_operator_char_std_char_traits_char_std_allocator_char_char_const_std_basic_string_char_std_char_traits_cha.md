# std::operator+<char,std::char_traits<char>,std::allocator<char>>(char const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &&)

- ea: `0x180002bd0`
- end: `0x180002c80`
- name: `??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@PEBD$$QEAV10@@Z`
- size: `176`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a00`

## callees

- `0x180002bd0`
- `0x180002f10`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180002c1d`
- `VCRUNTIME140!memmove` at `0x180002c1d`

## pseudocode

```c
_QWORD *__fastcall std::operator+<char>(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  bool v6; // cf

  v4 = std::string::insert(a3, a2, (__int64)a3, 0x29u);
  a1[3] = 15;
  v5 = v4;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( v4[3] >= 0x10u )
  {
    *a1 = *v4;
    *v4 = 0;
  }
  else if ( v4[2] != -1 )
  {
    memmove(a1, v4, v4[2] + 1LL);
  }
  a1[2] = v5[2];
  a1[3] = v5[3];
  v5[3] = 15;
  v6 = v5[3] < 0x10u;
  v5[2] = 0;
  if ( v6 )
    *(_BYTE *)v5 = 0;
  else
    *(_BYTE *)*v5 = 0;
  return a1;
}

```

## disassembly

```asm
0x180002bd0  mov     [rsp+arg_0], rbx
0x180002bd5  mov     [rsp+arg_8], rsi
0x180002bda  push    rdi
0x180002bdb  sub     rsp, 30h
0x180002bdf  xor     esi, esi
0x180002be1  mov     rdi, rcx
0x180002be4  mov     rcx, r8; void *
0x180002be7  mov     [rsp+38h+var_18], esi
0x180002beb  lea     r9d, [rsi+29h]
0x180002bef  call    ?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KPEBD0@Z; std::string::insert(unsigned __int64,char const *,unsigned __int64)
0x180002bf4  mov     qword ptr [rdi+18h], 0Fh
0x180002bfc  mov     rbx, rax
0x180002bff  mov     [rdi+10h], rsi
0x180002c03  mov     [rdi], sil
0x180002c06  cmp     qword ptr [rax+18h], 10h
0x180002c0b  jnb     short loc_180002C25
0x180002c0d  mov     r8, [rax+10h]
0x180002c11  add     r8, 1; Size
0x180002c15  jz      short loc_180002C2E
0x180002c17  mov     rdx, rax; Src
0x180002c1a  mov     rcx, rdi; void *
0x180002c1d  call    cs:__imp_memmove
0x180002c23  jmp     short loc_180002C2E
0x180002c25  mov     rax, [rax]
0x180002c28  mov     [rdi], rax
0x180002c2b  mov     [rbx], rsi
0x180002c2e  mov     rax, [rbx+10h]
0x180002c32  mov     [rdi+10h], rax
0x180002c36  mov     rax, [rbx+18h]
0x180002c3a  mov     [rdi+18h], rax
0x180002c3e  mov     qword ptr [rbx+18h], 0Fh
0x180002c46  cmp     qword ptr [rbx+18h], 10h
0x180002c4b  mov     [rbx+10h], rsi
0x180002c4f  jb      short loc_180002C6A
0x180002c51  mov     rax, [rbx]
0x180002c54  mov     [rax], sil
0x180002c57  mov     rax, rdi
0x180002c5a  mov     rbx, [rsp+38h+arg_0]
0x180002c5f  mov     rsi, [rsp+38h+arg_8]
0x180002c64  add     rsp, 30h
0x180002c68  pop     rdi
0x180002c69  retn
0x180002c6a  mov     [rbx], sil
0x180002c6d  mov     rax, rdi
0x180002c70  mov     rbx, [rsp+38h+arg_0]
0x180002c75  mov     rsi, [rsp+38h+arg_8]
0x180002c7a  add     rsp, 30h
0x180002c7e  pop     rdi
0x180002c7f  retn
```
