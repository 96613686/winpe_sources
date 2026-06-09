# AsyncPipe::WriteCallback(std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x14000dd04`
- end: `0x14000dde8`
- name: `?WriteCallback@AsyncPipe@@AEAAXPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `228`
- prototype: `void __fastcall(__int64, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000d6c0`

## callees

- `0x1400016c4`
- `0x1400016d0`
- `0x140003594`
- `0x14000dbbc`
- `0x14000dd04`
- `0x14000dfc4`

## pseudocode

```c
void __fastcall AsyncPipe::WriteCallback(__int64 a1, char **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rsi
  __int64 v7; // rbp

  if ( *(_QWORD *)(a1 + 24) == -1 )
  {
    if ( a2 )
    {
      std::vector<unsigned char>::~vector<unsigned char>(a2);
      operator delete(a2);
    }
  }
  else if ( *(_QWORD *)(a1 + 1464) )
  {
    v3 = a1 + 48;
    v4 = *(_QWORD *)(a1 + 80);
    if ( ((*(_BYTE *)(v3 + 24) + (_BYTE)v4) & 1) == 0 && *(_QWORD *)(v3 + 16) <= (unsigned __int64)(v4 + 2) >> 1 )
      std::deque<std::vector<unsigned char> *,std::allocator<std::vector<unsigned char> *>>::_Growmap(v3);
    v5 = *(_QWORD *)(v3 + 16);
    *(_QWORD *)(v3 + 24) &= 2 * v5 - 1;
    v6 = *(_QWORD *)(v3 + 32) + *(_QWORD *)(v3 + 24);
    v7 = (v6 >> 1) & (v5 - 1);
    if ( !*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8 * v7) )
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 8 * v7) = operator new(0x10u);
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8 * ((v6 >> 1) & (*(_QWORD *)(v3 + 16) - 1LL))) + 8 * (v6 & 1)) = a2;
    ++*(_QWORD *)(v3 + 32);
  }
  else
  {
    *(_QWORD *)(a1 + 1464) = a2;
    AsyncPipe::StartWrite((char *)a1);
  }
}

```

## disassembly

```asm
0x14000dd04  push    rbx
0x14000dd06  push    rbp
0x14000dd07  push    rsi
0x14000dd08  push    rdi
0x14000dd09  push    r14
0x14000dd0b  sub     rsp, 20h
0x14000dd0f  cmp     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x14000dd14  mov     rdi, rdx
0x14000dd17  jnz     short loc_14000DD3C
0x14000dd19  test    rdx, rdx
0x14000dd1c  jz      loc_14000DDDD
0x14000dd22  mov     rcx, rdx
0x14000dd25  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14000dd2a  mov     edx, 18h
0x14000dd2f  mov     rcx, rdi; Block
0x14000dd32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd37  jmp     loc_14000DDDD
0x14000dd3c  cmp     qword ptr [rcx+5B8h], 0
0x14000dd44  jz      loc_14000DDD1
0x14000dd4a  lea     rbx, [rcx+30h]
0x14000dd4e  mov     rcx, [rbx+20h]
0x14000dd52  mov     al, cl
0x14000dd54  add     al, [rbx+18h]
0x14000dd57  test    al, 1
0x14000dd59  jnz     short loc_14000DD70
0x14000dd5b  lea     rax, [rcx+2]
0x14000dd5f  shr     rax, 1
0x14000dd62  cmp     [rbx+10h], rax
0x14000dd66  ja      short loc_14000DD70
0x14000dd68  mov     rcx, rbx
0x14000dd6b  call    ?_Growmap@?$deque@PEAV?$vector@EV?$allocator@E@std@@@std@@V?$allocator@PEAV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>::_Growmap(unsigned __int64)
0x14000dd70  mov     rdx, [rbx+10h]
0x14000dd74  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x14000dd7c  and     [rbx+18h], rax
0x14000dd80  lea     rbp, [rdx-1]
0x14000dd84  mov     rsi, [rbx+18h]
0x14000dd88  add     rsi, [rbx+20h]
0x14000dd8c  mov     rax, [rbx+8]
0x14000dd90  mov     r14, rsi
0x14000dd93  shr     r14, 1
0x14000dd96  and     rbp, r14
0x14000dd99  cmp     qword ptr [rax+rbp*8], 0
0x14000dd9e  jnz     short loc_14000DDB2
0x14000dda0  mov     ecx, 10h; Size
0x14000dda5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ddaa  mov     rcx, [rbx+8]
0x14000ddae  mov     [rcx+rbp*8], rax
0x14000ddb2  mov     rcx, [rbx+10h]
0x14000ddb6  and     esi, 1
0x14000ddb9  mov     rax, [rbx+8]
0x14000ddbd  dec     rcx
0x14000ddc0  and     rcx, r14; pv
0x14000ddc3  mov     rax, [rax+rcx*8]
0x14000ddc7  mov     [rax+rsi*8], rdi
0x14000ddcb  inc     qword ptr [rbx+20h]
0x14000ddcf  jmp     short loc_14000DDDD
0x14000ddd1  mov     [rcx+5B8h], rdi
0x14000ddd8  call    ?StartWrite@AsyncPipe@@AEAAXXZ; AsyncPipe::StartWrite(void)
0x14000dddd  add     rsp, 20h
0x14000dde1  pop     r14
0x14000dde3  pop     rdi
0x14000dde4  pop     rsi
0x14000dde5  pop     rbp
0x14000dde6  pop     rbx
0x14000dde7  retn
```
