# std::chrono::steady_clock::now(void)

- ea: `0x140001540`
- end: `0x140001581`
- name: `?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ`
- size: `65`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001050`
- `0x1400044dc`
- `0x140004540`

## callees

- `0x140001540`

## import_xrefs

- `MSVCP140!_Query_perf_frequency` at `0x14000154d`
- `MSVCP140!_Query_perf_frequency` at `0x14000154d`
- `MSVCP140!_Query_perf_counter` at `0x140001556`
- `MSVCP140!_Query_perf_counter` at `0x140001556`

## pseudocode

```c
__int64 *__fastcall std::chrono::steady_clock::now(__int64 *a1)
{
  __int64 perf_frequency; // rdi
  __int64 perf_counter; // rax
  __int64 v4; // rax

  perf_frequency = _Query_perf_frequency();
  perf_counter = _Query_perf_counter();
  if ( perf_frequency == 10000000 )
  {
    v4 = 100 * perf_counter;
  }
  else
  {
    if ( perf_frequency == 24000000 )
    {
      *a1 = 1000000000 * (perf_counter / 24000000) + 1000000000 * (perf_counter % 24000000) / 24000000;
      return a1;
    }
    v4 = 1000000000 * (perf_counter / perf_frequency) + 1000000000 * (perf_counter % perf_frequency) / perf_frequency;
  }
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x140001540  mov     [rsp+arg_0], rbx
0x140001545  push    rdi
0x140001546  sub     rsp, 20h
0x14000154a  mov     rbx, rcx
0x14000154d  call    cs:__imp__Query_perf_frequency
0x140001553  mov     rdi, rax
0x140001556  call    cs:__imp__Query_perf_counter
0x14000155c  mov     r9, rax
0x14000155f  cmp     rdi, 989680h
0x140001566  jnz     loc_1400033A5
0x14000156c  imul    rax, r9, 64h ; 'd'
0x140001570  mov     [rbx], rax
0x140001573  mov     rax, rbx
0x140001576  mov     rbx, [rsp+28h+arg_0]
0x14000157b  add     rsp, 20h
0x14000157f  pop     rdi
0x140001580  retn
0x1400033a5  cmp     rdi, 16E3600h
0x1400033ac  jnz     short loc_14000340A
0x1400033ae  mov     r10, 0B2F4FC0794908CF3h
0x1400033b8  mov     rax, r10
0x1400033bb  imul    r9
0x1400033be  mov     rax, r10
0x1400033c1  lea     r8, [r9+rdx]
0x1400033c5  sar     r8, 18h
0x1400033c9  mov     rcx, r8
0x1400033cc  shr     rcx, 3Fh
0x1400033d0  add     r8, rcx
0x1400033d3  imul    rcx, r8, 16E3600h
0x1400033da  sub     r9, rcx
0x1400033dd  imul    rcx, r9, 3B9ACA00h
0x1400033e4  imul    rcx
0x1400033e7  add     rdx, rcx
0x1400033ea  sar     rdx, 18h
0x1400033ee  mov     rax, rdx
0x1400033f1  shr     rax, 3Fh
0x1400033f5  add     rdx, rax
0x1400033f8  imul    rax, r8, 3B9ACA00h
0x1400033ff  add     rdx, rax
0x140003402  mov     [rbx], rdx
0x140003405  jmp     loc_140001573
0x14000340a  cqo
0x14000340c  idiv    rdi
0x14000340f  mov     rcx, rax
0x140003412  imul    rax, rdx, 3B9ACA00h
0x140003419  imul    rcx, 3B9ACA00h
0x140003420  cqo
0x140003422  idiv    rdi
0x140003425  add     rax, rcx
0x140003428  jmp     loc_140001570
```
