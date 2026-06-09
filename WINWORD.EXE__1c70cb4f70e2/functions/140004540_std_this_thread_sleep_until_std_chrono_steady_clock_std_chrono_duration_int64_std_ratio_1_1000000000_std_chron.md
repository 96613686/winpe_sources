# std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)

- ea: `0x140004540`
- end: `0x1400045cc`
- name: `??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044dc`

## callees

- `0x140001540`
- `0x140002780`
- `0x140004540`

## pseudocode

```c
__int64 __fastcall std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
        _QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  while ( 1 )
  {
    std::chrono::steady_clock::now(&v5);
    result = v5;
    if ( *a1 == v5 || *a1 < v5 )
      break;
    v3 = *a1 - v5;
    if ( v3 <= 86400000000000LL )
    {
      v4 = v3 / 1000000;
      if ( 1000000 * (v3 / 1000000) < v3 )
        LODWORD(v4) = v4 + 1;
    }
    else
    {
      LODWORD(v4) = 86400000;
    }
    Thrd_sleep_for(v4);
  }
  return result;
}

```

## disassembly

```asm
0x140004540  mov     [rsp+arg_10], rbx
0x140004545  mov     [rsp+arg_18], rsi
0x14000454a  push    rdi
0x14000454b  sub     rsp, 20h
0x14000454f  mov     rbx, rcx
0x140004552  mov     rdi, 4E94914F0000h
0x14000455c  mov     rsi, 431BDE82D7B634DBh
0x140004566  lea     rcx, [rsp+28h+arg_0]
0x14000456b  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x140004570  mov     r8, [rbx]
0x140004573  mov     rax, [rsp+28h+arg_0]
0x140004578  cmp     r8, rax
0x14000457b  jz      short loc_1400045BC
0x14000457d  jl      short loc_1400045BC
0x14000457f  sub     r8, rax
0x140004582  cmp     r8, rdi
0x140004585  jz      short loc_140004590
0x140004587  jl      short loc_140004590
0x140004589  mov     edx, 5265C00h
0x14000458e  jmp     short loc_1400045B3
0x140004590  mov     rax, rsi
0x140004593  imul    r8
0x140004596  sar     rdx, 12h
0x14000459a  mov     rax, rdx
0x14000459d  shr     rax, 3Fh
0x1400045a1  add     rdx, rax
0x1400045a4  imul    rax, rdx, 0F4240h
0x1400045ab  cmp     rax, r8
0x1400045ae  jge     short loc_1400045B3
0x1400045b0  inc     rdx
0x1400045b3  mov     ecx, edx; dwMilliseconds
0x1400045b5  call    _Thrd_sleep_for
0x1400045ba  jmp     short loc_140004566
0x1400045bc  mov     rbx, [rsp+28h+arg_10]
0x1400045c1  mov     rsi, [rsp+28h+arg_18]
0x1400045c6  add     rsp, 20h
0x1400045ca  pop     rdi
0x1400045cb  retn
```
