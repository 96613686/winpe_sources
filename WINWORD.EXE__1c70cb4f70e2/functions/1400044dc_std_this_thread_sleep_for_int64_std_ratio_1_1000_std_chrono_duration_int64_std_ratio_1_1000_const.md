# std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)

- ea: `0x1400044dc`
- end: `0x14000453f`
- name: `??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400045d0`
- `0x1400052b0`

## callees

- `0x140001540`
- `0x1400044dc`
- `0x140004540`

## pseudocode

```c
__int64 __fastcall std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  std::chrono::steady_clock::now(&v4);
  v2 = *a1;
  if ( *a1 > 0 )
  {
    if ( v4 >= 0x7FFFFFFFFFFFFFFFLL - 1000000 * v2 )
      v4 = 0x7FFFFFFFFFFFFFFFLL;
    else
      v4 += 1000000 * v2;
  }
  return std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(&v4);
}

```

## disassembly

```asm
0x1400044dc  push    rbx
0x1400044de  sub     rsp, 20h
0x1400044e2  mov     rbx, rcx
0x1400044e5  lea     rcx, [rsp+28h+arg_0]
0x1400044ea  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1400044ef  mov     rcx, [rbx]
0x1400044f2  mov     rax, [rsp+28h+arg_0]
0x1400044f7  mov     [rsp+28h+arg_0], rax
0x1400044fc  test    rcx, rcx
0x1400044ff  jz      short loc_14000452F
0x140004501  js      short loc_14000452F
0x140004503  imul    rdx, rcx, 0F4240h
0x14000450a  mov     r8, 7FFFFFFFFFFFFFFFh
0x140004514  mov     rcx, r8
0x140004517  sub     rcx, rdx
0x14000451a  cmp     rax, rcx
0x14000451d  jge     short loc_14000452A
0x14000451f  lea     rcx, [rdx+rax]
0x140004523  mov     [rsp+28h+arg_0], rcx
0x140004528  jmp     short loc_14000452F
0x14000452a  mov     [rsp+28h+arg_0], r8
0x14000452f  lea     rcx, [rsp+28h+arg_0]
0x140004534  call    ??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x140004539  add     rsp, 20h
0x14000453d  pop     rbx
0x14000453e  retn
```
