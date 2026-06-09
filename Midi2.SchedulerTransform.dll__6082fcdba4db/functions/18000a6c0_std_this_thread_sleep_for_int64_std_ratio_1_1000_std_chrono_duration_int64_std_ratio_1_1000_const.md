# std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)

- ea: `0x18000a6c0`
- end: `0x18000a776`
- name: `??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000af80`
- `0x18000ba70`

## callees

- `0x180001bf0`
- `0x18000a6c0`
- `0x18000c2c4`

## pseudocode

```c
__int64 __fastcall std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(__int64 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  std::chrono::steady_clock::now(&v7);
  v2 = v7;
  if ( *a1 >= 1 )
  {
    v3 = 1000000 * *a1;
    if ( v7 >= 0x7FFFFFFFFFFFFFFFLL - v3 )
      v2 = 0x7FFFFFFFFFFFFFFFLL;
    else
      v2 = v3 + v7;
  }
  while ( 1 )
  {
    std::chrono::steady_clock::now(&v7);
    result = v7;
    if ( v2 == v7 || v2 < v7 )
      break;
    v5 = v2 - v7;
    if ( v2 - v7 < 0x4E94914F0001LL )
    {
      v6 = v5 / 1000000;
      if ( 1000000 * (v5 / 1000000) < v5 )
        LODWORD(v6) = v6 + 1;
    }
    else
    {
      LODWORD(v6) = 86400000;
    }
    Thrd_sleep_for(v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000a6c0  mov     [rsp+arg_10], rbx
0x18000a6c5  push    rdi
0x18000a6c6  sub     rsp, 20h
0x18000a6ca  mov     rdi, rcx
0x18000a6cd  lea     rcx, [rsp+28h+arg_0]
0x18000a6d2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18000a6d7  cmp     qword ptr [rdi], 1
0x18000a6db  mov     rbx, [rsp+28h+arg_0]
0x18000a6e0  jl      short loc_18000A706
0x18000a6e2  imul    rcx, [rdi], 0F4240h
0x18000a6e9  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18000a6f3  mov     rax, rdx
0x18000a6f6  sub     rax, rcx
0x18000a6f9  cmp     rbx, rax
0x18000a6fc  jge     short loc_18000A703
0x18000a6fe  add     rbx, rcx
0x18000a701  jmp     short loc_18000A706
0x18000a703  mov     rbx, rdx
0x18000a706  lea     rcx, [rsp+28h+arg_0]
0x18000a70b  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18000a710  mov     rax, [rsp+28h+arg_0]
0x18000a715  cmp     rbx, rax
0x18000a718  jz      short loc_18000A76B
0x18000a71a  jl      short loc_18000A76B
0x18000a71c  mov     rcx, rbx
0x18000a71f  sub     rcx, rax
0x18000a722  mov     rax, 4E94914F0001h
0x18000a72c  cmp     rcx, rax
0x18000a72f  jl      short loc_18000A738
0x18000a731  mov     edx, 5265C00h
0x18000a736  jmp     short loc_18000A762
0x18000a738  mov     rax, 431BDE82D7B634DBh
0x18000a742  imul    rcx
0x18000a745  sar     rdx, 12h
0x18000a749  mov     rax, rdx
0x18000a74c  shr     rax, 3Fh
0x18000a750  add     rdx, rax
0x18000a753  imul    rax, rdx, 0F4240h
0x18000a75a  cmp     rax, rcx
0x18000a75d  jge     short loc_18000A762
0x18000a75f  inc     rdx
0x18000a762  mov     ecx, edx; dwMilliseconds
0x18000a764  call    _Thrd_sleep_for
0x18000a769  jmp     short loc_18000A706
0x18000a76b  mov     rbx, [rsp+28h+arg_10]
0x18000a770  add     rsp, 20h
0x18000a774  pop     rdi
0x18000a775  retn
```
