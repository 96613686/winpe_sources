# ABO_NODE::Create(ushort const *)

- ea: `0x180007080`
- end: `0x180007107`
- name: `?Create@ABO_NODE@@QEAAJPEBG@Z`
- size: `135`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004f98`
- `0x180007148`
- `0x180008050`
- `0x180010880`
- `0x180011dd0`
- `0x180012cb0`
- `0x180014b90`
- `0x1800259c0`
- `0x18002ac00`

## callees

- `0x180002990`
- `0x180007080`
- `0x180007110`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000709c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000709c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800070eb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800070eb`

## pseudocode

```c
__int64 __fastcall ABO_NODE::Create(ABO_NODE *this, const unsigned __int16 *a2)
{
  int v3; // edi
  _QWORD *v4; // rbx
  const unsigned __int16 *Str; // rax

  if ( a2 )
  {
    v3 = STRU::Copy((ABO_NODE *)((char *)this + 56), a2);
    if ( v3 >= 0 )
    {
      v4 = operator new(0x18u);
      if ( v4 )
      {
        v4[1] = 0;
        *v4 = &ABO_NODE_INDEX_KEY::`vftable';
        *((_DWORD *)v4 + 4) = 0;
      }
      else
      {
        v4 = 0;
      }
      *((_QWORD *)this + 14) = v4;
      if ( v4 )
      {
        Str = STRU::QueryStr((ABO_NODE *)((char *)this + 56));
        ABO_NODE_INDEX_KEY::Create((ABO_NODE_INDEX_KEY *)v4, Str);
      }
      else
      {
        return (unsigned int)-2147024888;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007080  push    rbx
0x180007082  push    rbp
0x180007083  push    rsi
0x180007084  push    rdi
0x180007085  sub     rsp, 28h
0x180007089  mov     rsi, rcx
0x18000708c  test    rdx, rdx
0x18000708f  jnz     short loc_180007098
0x180007091  mov     edi, 80070057h
0x180007096  jmp     short loc_1800070FC
0x180007098  add     rcx, 38h ; '8'
0x18000709c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800070a2  mov     edi, eax
0x1800070a4  test    eax, eax
0x1800070a6  js      short loc_1800070FC
0x1800070a8  mov     ecx, 18h; Size
0x1800070ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800070b2  mov     rbx, rax
0x1800070b5  test    rax, rax
0x1800070b8  jz      short loc_1800070D5
0x1800070ba  lea     rax, ??_7ABO_NODE_INDEX_KEY@@6B@; const ABO_NODE_INDEX_KEY::`vftable'
0x1800070c1  mov     qword ptr [rbx+8], 0
0x1800070c9  mov     [rbx], rax
0x1800070cc  mov     dword ptr [rbx+10h], 0
0x1800070d3  jmp     short loc_1800070D7
0x1800070d5  xor     ebx, ebx
0x1800070d7  mov     [rsi+70h], rbx
0x1800070db  test    rbx, rbx
0x1800070de  jnz     short loc_1800070E7
0x1800070e0  mov     edi, 80070008h
0x1800070e5  jmp     short loc_1800070FC
0x1800070e7  lea     rcx, [rsi+38h]
0x1800070eb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800070f1  mov     rdx, rax; unsigned __int16 *
0x1800070f4  mov     rcx, rbx; this
0x1800070f7  call    ?Create@ABO_NODE_INDEX_KEY@@QEAAJPEBG@Z; ABO_NODE_INDEX_KEY::Create(ushort const *)
0x1800070fc  mov     eax, edi
0x1800070fe  add     rsp, 28h
0x180007102  pop     rdi
0x180007103  pop     rsi
0x180007104  pop     rbp
0x180007105  pop     rbx
0x180007106  retn
```
