# InitProcessStartTime(void)

- ea: `0x140001570`
- end: `0x1400015a8`
- name: `?InitProcessStartTime@@YA_NXZ`
- size: `56`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001560`

## callees

- `0x140001570`

## import_xrefs

- `MSVCP140!_Query_perf_counter` at `0x14000157f`
- `MSVCP140!_Query_perf_counter` at `0x14000157f`
- `MSVCP140!_Query_perf_frequency` at `0x140001576`
- `MSVCP140!_Query_perf_frequency` at `0x140001576`

## pseudocode

```c
char InitProcessStartTime(void)
{
  __int64 perf_frequency; // rbx
  __int64 perf_counter; // rax
  __int64 v2; // rax

  perf_frequency = _Query_perf_frequency();
  perf_counter = _Query_perf_counter();
  if ( perf_frequency == 10000000 )
  {
    v2 = 100 * perf_counter;
  }
  else
  {
    if ( perf_frequency == 24000000 )
    {
      ProcessStartTimeNanosecondsSinceEpoch = 1000000000 * (perf_counter / 24000000)
                                            + 1000000000 * (perf_counter % 24000000) / 24000000;
      return 1;
    }
    v2 = 1000000000 * (perf_counter / perf_frequency) + 1000000000 * (perf_counter % perf_frequency) / perf_frequency;
  }
  ProcessStartTimeNanosecondsSinceEpoch = v2;
  return 1;
}

```

## disassembly

```asm
0x140001570  push    rbx
0x140001572  sub     rsp, 20h
0x140001576  call    cs:__imp__Query_perf_frequency
0x14000157c  mov     rbx, rax
0x14000157f  call    cs:__imp__Query_perf_counter
0x140001585  mov     rcx, rax
0x140001588  cmp     rbx, 989680h
0x14000158f  jnz     loc_140002A30
0x140001595  imul    rax, rcx, 64h ; 'd'
0x140001599  mov     cs:?ProcessStartTimeNanosecondsSinceEpoch@@3_JA, rax; __int64 ProcessStartTimeNanosecondsSinceEpoch
0x1400015a0  mov     al, 1
0x1400015a2  add     rsp, 20h
0x1400015a6  pop     rbx
0x1400015a7  retn
0x140002a30  cmp     rbx, 16E3600h
0x140002a37  jnz     short loc_140002A99
0x140002a39  mov     r10, 0B2F4FC0794908CF3h
0x140002a43  mov     rax, r10
0x140002a46  imul    rcx
0x140002a49  mov     rax, r10
0x140002a4c  lea     r9, [rcx+rdx]
0x140002a50  sar     r9, 18h
0x140002a54  mov     r8, r9
0x140002a57  shr     r8, 3Fh
0x140002a5b  add     r9, r8
0x140002a5e  imul    r8, r9, 16E3600h
0x140002a65  sub     rcx, r8
0x140002a68  imul    r8, rcx, 3B9ACA00h
0x140002a6f  imul    r8
0x140002a72  imul    rax, r9, 3B9ACA00h
0x140002a79  add     rdx, r8
0x140002a7c  sar     rdx, 18h
0x140002a80  mov     rcx, rdx
0x140002a83  shr     rcx, 3Fh
0x140002a87  add     rcx, rdx
0x140002a8a  add     rcx, rax
0x140002a8d  mov     cs:?ProcessStartTimeNanosecondsSinceEpoch@@3_JA, rcx; __int64 ProcessStartTimeNanosecondsSinceEpoch
0x140002a94  jmp     loc_1400015A0
0x140002a99  cqo
0x140002a9b  idiv    rbx
0x140002a9e  mov     rcx, rax
0x140002aa1  imul    rax, rdx, 3B9ACA00h
0x140002aa8  imul    rcx, 3B9ACA00h
0x140002aaf  cqo
0x140002ab1  idiv    rbx
0x140002ab4  add     rax, rcx
0x140002ab7  jmp     loc_140001599
```
