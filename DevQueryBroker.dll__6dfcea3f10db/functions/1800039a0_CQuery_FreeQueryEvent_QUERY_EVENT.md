# CQuery::FreeQueryEvent(_QUERY_EVENT *)

- ea: `0x1800039a0`
- end: `0x180003a5b`
- name: `?FreeQueryEvent@CQuery@@SAXPEAU_QUERY_EVENT@@@Z`
- size: `187`
- prototype: `void __fastcall(void **Block)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bfc`
- `0x180003a64`
- `0x180003da4`

## callees

- `0x1800039a0`

## import_xrefs

- `msvcrt!free` at `0x1800039dd`
- `msvcrt!free` at `0x180003a03`
- `msvcrt!free` at `0x180003a1a`
- `msvcrt!free` at `0x180003a33`
- `msvcrt!free` at `0x180003a3c`
- `msvcrt!free` at `0x180003a45`
- `msvcrt!free` at `0x1800039dd`
- `msvcrt!free` at `0x180003a03`
- `msvcrt!free` at `0x180003a1a`
- `msvcrt!free` at `0x180003a33`
- `msvcrt!free` at `0x180003a3c`
- `msvcrt!free` at `0x180003a45`

## pseudocode

```c
void __fastcall CQuery::FreeQueryEvent(void **Block)
{
  _QWORD *v1; // rdx
  void *v3; // rcx
  _QWORD *v4; // rcx
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( Block )
  {
    v1 = *Block;
    if ( *Block )
    {
      if ( *(_DWORD *)v1 == 1 || (unsigned int)(*(_DWORD *)v1 - 2) <= 1 )
      {
        v3 = (void *)v1[2];
        if ( v3 )
          free(v3);
        v4 = *Block;
        if ( *((_DWORD *)*Block + 6) )
        {
          v5 = 0;
          do
          {
            v6 = *(void **)(v4[4] + 48 * v5 + 40);
            if ( v6 )
              free(v6);
            v7 = *(void **)(*((_QWORD *)*Block + 4) + 48 * v5 + 24);
            if ( v7 )
              free(v7);
            v4 = *Block;
            v5 = (unsigned int)(v5 + 1);
          }
          while ( (unsigned int)v5 < *((_DWORD *)*Block + 6) );
        }
        v8 = (void *)v4[4];
        if ( v8 )
          free(v8);
      }
      free(*Block);
    }
    free(Block);
  }
}

```

## disassembly

```asm
0x1800039a0  test    rcx, rcx
0x1800039a3  jz      locret_180003A5A
0x1800039a9  mov     [rsp+arg_0], rbx
0x1800039ae  mov     [rsp+arg_8], rsi
0x1800039b3  push    rdi
0x1800039b4  sub     rsp, 20h
0x1800039b8  mov     rdx, [rcx]
0x1800039bb  mov     rbx, rcx
0x1800039be  test    rdx, rdx
0x1800039c1  jz      short loc_180003A42
0x1800039c3  mov     ecx, [rdx]
0x1800039c5  sub     ecx, 1
0x1800039c8  jz      short loc_1800039D4
0x1800039ca  sub     ecx, 1
0x1800039cd  jz      short loc_1800039D4
0x1800039cf  cmp     ecx, 1
0x1800039d2  jnz     short loc_180003A39
0x1800039d4  mov     rcx, [rdx+10h]; Block
0x1800039d8  test    rcx, rcx
0x1800039db  jz      short loc_1800039E3
0x1800039dd  call    cs:__imp_free
0x1800039e3  mov     rcx, [rbx]
0x1800039e6  cmp     dword ptr [rcx+18h], 0
0x1800039ea  jbe     short loc_180003A2A
0x1800039ec  xor     edi, edi
0x1800039ee  mov     rax, [rcx+20h]
0x1800039f2  lea     rsi, [rdi+rdi*2]
0x1800039f6  add     rsi, rsi
0x1800039f9  mov     rcx, [rax+rsi*8+28h]; Block
0x1800039fe  test    rcx, rcx
0x180003a01  jz      short loc_180003A09
0x180003a03  call    cs:__imp_free
0x180003a09  mov     rax, [rbx]
0x180003a0c  mov     rcx, [rax+20h]
0x180003a10  mov     rcx, [rcx+rsi*8+18h]; Block
0x180003a15  test    rcx, rcx
0x180003a18  jz      short loc_180003A20
0x180003a1a  call    cs:__imp_free
0x180003a20  mov     rcx, [rbx]
0x180003a23  inc     edi
0x180003a25  cmp     edi, [rcx+18h]
0x180003a28  jb      short loc_1800039EE
0x180003a2a  mov     rcx, [rcx+20h]; Block
0x180003a2e  test    rcx, rcx
0x180003a31  jz      short loc_180003A39
0x180003a33  call    cs:__imp_free
0x180003a39  mov     rcx, [rbx]; Block
0x180003a3c  call    cs:__imp_free
0x180003a42  mov     rcx, rbx; Block
0x180003a45  call    cs:__imp_free
0x180003a4b  mov     rbx, [rsp+28h+arg_0]
0x180003a50  mov     rsi, [rsp+28h+arg_8]
0x180003a55  add     rsp, 20h
0x180003a59  pop     rdi
0x180003a5a  retn
```
