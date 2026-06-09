# BasePrivate::New(unsigned __int64,bool)

- ea: `0x180002650`
- end: `0x1800026b9`
- name: `?New@BasePrivate@@YAPEAX_K_N@Z`
- size: `105`
- prototype: `void *__fastcall(size_t Size, unsigned __int64, bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004554`
- `0x180005744`
- `0x180005874`
- `0x1800059a4`
- `0x180005ad4`

## callees

- `0x18000212a`
- `0x180002420`
- `0x180002650`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000268f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000268f`

## pseudocode

```c
void *__fastcall BasePrivate::New(size_t Size, char a2)
{
  size_t v2; // rdi
  void (__fastcall *v4)(size_t); // rsi
  int v5; // edx
  void *v6; // rbx

  v2 = 1;
  if ( Size )
    v2 = Size;
  while ( 1 )
  {
    v6 = malloc(v2);
    if ( v6 )
      break;
    v4 = (void (__fastcall *)(size_t))o__set_new_handler_0(0);
    o__set_new_handler_0(v4);
    if ( !v4 )
    {
      if ( a2 )
        ATL::BaseAtlThrow((BasePrivate *)0x8007000ELL, v5);
      return v6;
    }
    v4(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x180002650  push    rbx
0x180002652  push    rbp
0x180002653  push    rsi
0x180002654  push    rdi
0x180002655  sub     rsp, 28h
0x180002659  test    rcx, rcx
0x18000265c  mov     edi, 1
0x180002661  mov     bpl, dl
0x180002664  cmovnz  rdi, rcx
0x180002668  jmp     short loc_18000268C
0x18000266a  xor     ecx, ecx
0x18000266c  call    _o__set_new_handler_0
0x180002671  mov     rcx, rax
0x180002674  mov     rsi, rax
0x180002677  call    _o__set_new_handler_0
0x18000267c  test    rsi, rsi
0x18000267f  jz      short loc_1800026A9
0x180002681  mov     rcx, rdi
0x180002684  mov     rax, rsi
0x180002687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268c  mov     rcx, rdi; Size
0x18000268f  call    cs:__imp_malloc
0x180002695  mov     rbx, rax
0x180002698  test    rax, rax
0x18000269b  jz      short loc_18000266A
0x18000269d  mov     rax, rbx
0x1800026a0  add     rsp, 28h
0x1800026a4  pop     rdi
0x1800026a5  pop     rsi
0x1800026a6  pop     rbp
0x1800026a7  pop     rbx
0x1800026a8  retn
0x1800026a9  test    bpl, bpl
0x1800026ac  jz      short loc_18000269D
0x1800026ae  mov     ecx, 8007000Eh; int
0x1800026b3  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
