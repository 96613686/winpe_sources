# std::stack<Mso::Json::ParseState::Enum,std::deque<Mso::Json::ParseState::Enum,std::allocator<Mso::Json::ParseState::Enum>>>::push(Mso::Json::ParseState::Enum &&)

- ea: `0x18001d998`
- end: `0x18001da66`
- name: `?push@?$stack@W4Enum@ParseState@Json@Mso@@V?$deque@W4Enum@ParseState@Json@Mso@@V?$allocator@W4Enum@ParseState@Json@Mso@@@std@@@std@@@std@@QEAAX$$QEAW4Enum@ParseState@Json@Mso@@@Z`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c2b0`
- `0x18001c490`

## callees

- `0x18000ab0c`
- `0x18001d998`
- `0x18001da68`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001da10`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001da10`

## pseudocode

```c
__int64 __fastcall std::stack<enum Mso::Json::ParseState::Enum>::push(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rdi
  __int64 v7; // rsi
  void *v8; // rcx
  __int64 result; // rax

  v4 = *(_QWORD *)(a1 + 32);
  if ( ((*(_BYTE *)(a1 + 24) + (_BYTE)v4) & 3) == 0 && *(_QWORD *)(a1 + 16) <= (unsigned __int64)(v4 + 4) >> 2 )
    std::deque<enum Mso::Json::ParseState::Enum>::_Growmap(a1);
  v5 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) &= 4 * v5 - 1;
  v6 = *(_QWORD *)(a1 + 32) + *(_QWORD *)(a1 + 24);
  v7 = (v6 >> 2) & (v5 - 1);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v7) )
  {
    v8 = malloc(0x10u);
    if ( !v8 )
      std::_Xbad_alloc();
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v7) = v8;
  }
  result = *a2;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * ((v6 >> 2) & (*(_QWORD *)(a1 + 16) - 1LL))) + 4 * (v6 & 3)) = result;
  ++*(_QWORD *)(a1 + 32);
  return result;
}

```

## disassembly

```asm
0x18001d998  mov     rax, rsp
0x18001d99b  mov     [rax+8], rbx
0x18001d99f  mov     [rax+10h], rbp
0x18001d9a3  mov     [rax+18h], rsi
0x18001d9a7  mov     [rax+20h], rdi
0x18001d9ab  push    r14
0x18001d9ad  sub     rsp, 20h
0x18001d9b1  mov     rbx, rcx
0x18001d9b4  mov     r14, rdx
0x18001d9b7  mov     rcx, [rcx+20h]
0x18001d9bb  mov     al, cl
0x18001d9bd  add     al, [rbx+18h]
0x18001d9c0  test    al, 3
0x18001d9c2  jnz     short loc_18001D9DA
0x18001d9c4  lea     rax, [rcx+4]
0x18001d9c8  shr     rax, 2
0x18001d9cc  cmp     [rbx+10h], rax
0x18001d9d0  ja      short loc_18001D9DA
0x18001d9d2  mov     rcx, rbx
0x18001d9d5  call    ?_Growmap@?$deque@W4Enum@ParseState@Json@Mso@@V?$allocator@W4Enum@ParseState@Json@Mso@@@std@@@std@@AEAAX_K@Z; std::deque<Mso::Json::ParseState::Enum>::_Growmap(unsigned __int64)
0x18001d9da  mov     rdx, [rbx+10h]
0x18001d9de  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*4]
0x18001d9e6  and     [rbx+18h], rax
0x18001d9ea  lea     rsi, [rdx-1]
0x18001d9ee  mov     rdi, [rbx+18h]
0x18001d9f2  add     rdi, [rbx+20h]
0x18001d9f6  mov     rax, [rbx+8]
0x18001d9fa  mov     rbp, rdi
0x18001d9fd  shr     rbp, 2
0x18001da01  and     rsi, rbp
0x18001da04  cmp     qword ptr [rax+rsi*8], 0
0x18001da09  jnz     short loc_18001DA26
0x18001da0b  mov     ecx, 10h; Size
0x18001da10  call    cs:__imp_malloc
0x18001da16  mov     rcx, rax
0x18001da19  test    rax, rax
0x18001da1c  jz      short loc_18001DA60
0x18001da1e  mov     rax, [rbx+8]
0x18001da22  mov     [rax+rsi*8], rcx
0x18001da26  mov     rax, [rbx+10h]
0x18001da2a  and     edi, 3
0x18001da2d  mov     rcx, [rbx+8]
0x18001da31  dec     rax
0x18001da34  mov     rsi, [rsp+28h+arg_10]
0x18001da39  and     rax, rbp
0x18001da3c  mov     rbp, [rsp+28h+arg_8]
0x18001da41  mov     rcx, [rcx+rax*8]
0x18001da45  mov     eax, [r14]
0x18001da48  mov     [rcx+rdi*4], eax
0x18001da4b  inc     qword ptr [rbx+20h]
0x18001da4f  mov     rbx, [rsp+28h+arg_0]
0x18001da54  mov     rdi, [rsp+28h+arg_18]
0x18001da59  add     rsp, 20h
0x18001da5d  pop     r14
0x18001da5f  retn
0x18001da60  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
