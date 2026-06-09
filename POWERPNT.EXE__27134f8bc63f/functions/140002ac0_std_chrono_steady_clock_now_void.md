# std::chrono::steady_clock::now(void)

- ea: `0x140002ac0`
- end: `0x140002b82`
- name: `?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b84`
- `0x140002c10`

## callees

- `0x140002ac0`

## import_xrefs

- `MSVCP140!_Query_perf_counter` at `0x140002ad6`
- `MSVCP140!_Query_perf_counter` at `0x140002ad6`
- `MSVCP140!_Query_perf_frequency` at `0x140002acd`
- `MSVCP140!_Query_perf_frequency` at `0x140002acd`

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
LABEL_6:
    *a1 = v4;
    return a1;
  }
  if ( perf_frequency != 24000000 )
  {
    v4 = 1000000000 * (perf_counter / perf_frequency) + 1000000000 * (perf_counter % perf_frequency) / perf_frequency;
    goto LABEL_6;
  }
  *a1 = 1000000000 * (perf_counter / 24000000) + 1000000000 * (perf_counter % 24000000) / 24000000;
  return a1;
}

```

## disassembly

```asm
0x140002ac0  mov     [rsp+arg_0], rbx
0x140002ac5  push    rdi
0x140002ac6  sub     rsp, 20h
0x140002aca  mov     rbx, rcx
0x140002acd  call    cs:__imp__Query_perf_frequency
0x140002ad3  mov     rdi, rax
0x140002ad6  call    cs:__imp__Query_perf_counter
0x140002adc  mov     r9, rax
0x140002adf  cmp     rdi, 989680h
0x140002ae6  jnz     short loc_140002AF1
0x140002ae8  imul    rax, r9, 64h ; 'd'
0x140002aec  jmp     loc_140002B71
0x140002af1  cmp     rdi, 16E3600h
0x140002af8  jnz     short loc_140002B53
0x140002afa  mov     r10, 0B2F4FC0794908CF3h
0x140002b04  mov     rax, r10
0x140002b07  imul    r9
0x140002b0a  mov     rax, r10
0x140002b0d  lea     r8, [r9+rdx]
0x140002b11  sar     r8, 18h
0x140002b15  mov     rcx, r8
0x140002b18  shr     rcx, 3Fh
0x140002b1c  add     r8, rcx
0x140002b1f  imul    rcx, r8, 16E3600h
0x140002b26  sub     r9, rcx
0x140002b29  imul    rcx, r9, 3B9ACA00h
0x140002b30  imul    rcx
0x140002b33  add     rdx, rcx
0x140002b36  sar     rdx, 18h
0x140002b3a  mov     rax, rdx
0x140002b3d  shr     rax, 3Fh
0x140002b41  add     rdx, rax
0x140002b44  imul    rax, r8, 3B9ACA00h
0x140002b4b  add     rdx, rax
0x140002b4e  mov     [rbx], rdx
0x140002b51  jmp     short loc_140002B74
0x140002b53  cqo
0x140002b55  idiv    rdi
0x140002b58  mov     rcx, rax
0x140002b5b  imul    rax, rdx, 3B9ACA00h
0x140002b62  imul    rcx, 3B9ACA00h
0x140002b69  cqo
0x140002b6b  idiv    rdi
0x140002b6e  add     rax, rcx
0x140002b71  mov     [rbx], rax
0x140002b74  mov     rax, rbx
0x140002b77  mov     rbx, [rsp+28h+arg_0]
0x140002b7c  add     rsp, 20h
0x140002b80  pop     rdi
0x140002b81  retn
```
