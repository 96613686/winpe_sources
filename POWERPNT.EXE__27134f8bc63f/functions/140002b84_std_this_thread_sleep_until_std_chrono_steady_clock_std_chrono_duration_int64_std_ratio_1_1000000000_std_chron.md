# std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)

- ea: `0x140002b84`
- end: `0x140002c10`
- name: `??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002c10`

## callees

- `0x140002910`
- `0x140002ac0`
- `0x140002b84`

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
0x140002b84  mov     [rsp+arg_10], rbx
0x140002b89  mov     [rsp+arg_18], rsi
0x140002b8e  push    rdi
0x140002b8f  sub     rsp, 20h
0x140002b93  mov     rbx, rcx
0x140002b96  mov     rdi, 4E94914F0000h
0x140002ba0  mov     rsi, 431BDE82D7B634DBh
0x140002baa  lea     rcx, [rsp+28h+arg_0]
0x140002baf  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x140002bb4  mov     r8, [rbx]
0x140002bb7  mov     rax, [rsp+28h+arg_0]
0x140002bbc  cmp     r8, rax
0x140002bbf  jz      short loc_140002C00
0x140002bc1  jl      short loc_140002C00
0x140002bc3  sub     r8, rax
0x140002bc6  cmp     r8, rdi
0x140002bc9  jz      short loc_140002BD4
0x140002bcb  jl      short loc_140002BD4
0x140002bcd  mov     edx, 5265C00h
0x140002bd2  jmp     short loc_140002BF7
0x140002bd4  mov     rax, rsi
0x140002bd7  imul    r8
0x140002bda  sar     rdx, 12h
0x140002bde  mov     rax, rdx
0x140002be1  shr     rax, 3Fh
0x140002be5  add     rdx, rax
0x140002be8  imul    rax, rdx, 0F4240h
0x140002bef  cmp     rax, r8
0x140002bf2  jge     short loc_140002BF7
0x140002bf4  inc     rdx
0x140002bf7  mov     ecx, edx; dwMilliseconds
0x140002bf9  call    _Thrd_sleep_for
0x140002bfe  jmp     short loc_140002BAA
0x140002c00  mov     rbx, [rsp+28h+arg_10]
0x140002c05  mov     rsi, [rsp+28h+arg_18]
0x140002c0a  add     rsp, 20h
0x140002c0e  pop     rdi
0x140002c0f  retn
```
