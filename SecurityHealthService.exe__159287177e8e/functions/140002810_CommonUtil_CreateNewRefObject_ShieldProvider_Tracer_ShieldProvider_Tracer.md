# CommonUtil::CreateNewRefObject<ShieldProvider::Tracer>(ShieldProvider::Tracer * *)

- ea: `0x140002810`
- end: `0x1400028b1`
- name: `??$CreateNewRefObject@VTracer@ShieldProvider@@@CommonUtil@@YAJPEAPEAVTracer@ShieldProvider@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400028b8`

## callees

- `0x14000162c`
- `0x14000202c`
- `0x140002810`

## pseudocode

```c
__int64 __fastcall CommonUtil::CreateNewRefObject<ShieldProvider::Tracer>(_QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi

  v2 = operator new(0xAB8u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v2[2] = 0;
  *(_QWORD *)v2 = &ShieldProvider::Tracer::`vftable';
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_BYTE *)v2 + 48) = 0;
  memset_0((char *)v2 + 49, 0, 0xA78u);
  *((_QWORD *)v3 + 342) = 0;
  if ( v3[2] )
    _InterlockedIncrement(v3 + 2);
  else
    v3[2] = 1;
  *a1 = v3;
  return 0;
}

```

## disassembly

```asm
0x140002810  mov     [rsp+arg_0], rbx
0x140002815  mov     [rsp+arg_18], rsi
0x14000281a  push    rdi
0x14000281b  sub     rsp, 30h
0x14000281f  mov     rsi, rcx
0x140002822  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002829  mov     ecx, 0AB8h; unsigned __int64
0x14000282e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140002833  mov     rdi, rax
0x140002836  xor     ebx, ebx
0x140002838  test    rax, rax
0x14000283b  jz      short loc_14000288C
0x14000283d  mov     [rax+8], ebx
0x140002840  lea     rax, ??_7Tracer@ShieldProvider@@6B@; const ShieldProvider::Tracer::`vftable'
0x140002847  mov     [rdi], rax
0x14000284a  mov     [rdi+10h], rbx
0x14000284e  mov     [rdi+18h], rbx
0x140002852  mov     [rdi+28h], rbx
0x140002856  mov     [rdi+30h], bl
0x140002859  lea     rcx, [rdi+31h]; void *
0x14000285d  xor     edx, edx; Val
0x14000285f  mov     r8d, 0A78h; Size
0x140002865  call    memset_0
0x14000286a  mov     [rdi+0AB0h], rbx
0x140002871  mov     eax, [rdi+8]
0x140002874  test    eax, eax
0x140002876  jnz     short loc_140002881
0x140002878  mov     dword ptr [rdi+8], 1
0x14000287f  jmp     short loc_140002885
0x140002881  lock inc dword ptr [rdi+8]
0x140002885  mov     [rsi], rdi
0x140002888  xor     eax, eax
0x14000288a  jmp     short loc_1400028A0
0x14000288c  mov     eax, 8007000Eh
0x140002891  jmp     short loc_1400028A0
0x140002893  xor     ebx, ebx
0x140002895  cmp     [rsp+38h+arg_8], ebx
0x140002899  cmovl   ebx, [rsp+38h+arg_10]
0x14000289e  mov     eax, ebx
0x1400028a0  mov     rbx, [rsp+38h+arg_0]
0x1400028a5  mov     rsi, [rsp+38h+arg_18]
0x1400028aa  add     rsp, 30h
0x1400028ae  pop     rdi
0x1400028af  retn
```
