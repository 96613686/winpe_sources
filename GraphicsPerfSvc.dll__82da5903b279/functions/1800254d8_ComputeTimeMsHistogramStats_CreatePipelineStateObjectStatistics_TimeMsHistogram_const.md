# ComputeTimeMsHistogramStats<CreatePipelineStateObjectStatistics>(TimeMsHistogram const &)

- ea: `0x1800254d8`
- end: `0x18002559c`
- name: `??$ComputeTimeMsHistogramStats@UCreatePipelineStateObjectStatistics@@@@YA?AUCreatePipelineStateObjectStatistics@@AEBVTimeMsHistogram@@@Z`
- size: `196`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800258a0`

## callees

- `0x1800047f0`
- `0x180004b41`
- `0x1800253cc`
- `0x1800254d8`

## pseudocode

```c
_QWORD *__fastcall ComputeTimeMsHistogramStats<CreatePipelineStateObjectStatistics>(_QWORD *a1, __int64 *a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int64 v7; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  memset_0(a1 + 5, 0, 0xA0u);
  if ( *((_DWORD *)a2 + 8) )
    v5 = *a2;
  else
    v5 = 0;
  a1[1] = v5;
  if ( *((_DWORD *)a2 + 8) )
    v6 = a2[1];
  else
    v6 = 0;
  a1[2] = v6;
  *a1 = *((unsigned int *)a2 + 8);
  if ( *((_DWORD *)a2 + 8) )
  {
    v7 = a2[2] / (unsigned __int64)*((unsigned int *)a2 + 8);
    v4 = a2[2] % (unsigned __int64)*((unsigned int *)a2 + 8);
  }
  else
  {
    v7 = 0;
  }
  a1[3] = v7;
  a1[4] = gpm::statistics::averages<unsigned __int64>::variance(a2 + 2, v4);
  memmove_0(a1 + 5, (const void *)a2[9], a2[10] - a2[9]);
  return a1;
}

```

## disassembly

```asm
0x1800254d8  mov     [rsp+arg_0], rbx
0x1800254dd  mov     [rsp+arg_8], rsi
0x1800254e2  push    rdi
0x1800254e3  sub     rsp, 20h
0x1800254e7  mov     rdi, rdx
0x1800254ea  mov     qword ptr [rcx], 0
0x1800254f1  mov     rbx, rcx
0x1800254f4  mov     qword ptr [rcx+8], 0
0x1800254fc  mov     qword ptr [rcx+10h], 0
0x180025504  xor     edx, edx; Val
0x180025506  mov     qword ptr [rcx+18h], 0
0x18002550e  mov     r8d, 0A0h; Size
0x180025514  mov     qword ptr [rcx+20h], 0
0x18002551c  add     rcx, 28h ; '('; void *
0x180025520  call    memset_0
0x180025525  cmp     dword ptr [rdi+20h], 0
0x180025529  jbe     short loc_180025530
0x18002552b  mov     rax, [rdi]
0x18002552e  jmp     short loc_180025532
0x180025530  xor     eax, eax
0x180025532  mov     [rbx+8], rax
0x180025536  cmp     dword ptr [rdi+20h], 0
0x18002553a  jbe     short loc_180025542
0x18002553c  mov     rax, [rdi+8]
0x180025540  jmp     short loc_180025544
0x180025542  xor     eax, eax
0x180025544  mov     [rbx+10h], rax
0x180025548  mov     eax, [rdi+20h]
0x18002554b  mov     [rbx], rax
0x18002554e  cmp     dword ptr [rdi+20h], 0
0x180025552  jz      short loc_180025562
0x180025554  mov     ecx, [rdi+20h]
0x180025557  xor     edx, edx
0x180025559  mov     rax, [rdi+10h]
0x18002555d  div     rcx
0x180025560  jmp     short loc_180025564
0x180025562  xor     eax, eax
0x180025564  lea     rcx, [rdi+10h]
0x180025568  mov     [rbx+18h], rax
0x18002556c  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x180025571  mov     [rbx+20h], rax
0x180025575  lea     rcx, [rbx+28h]; void *
0x180025579  mov     rdx, [rdi+48h]; Src
0x18002557d  mov     r8, [rdi+50h]
0x180025581  sub     r8, rdx; Size
0x180025584  call    memmove_0
0x180025589  mov     rsi, [rsp+28h+arg_8]
0x18002558e  mov     rax, rbx
0x180025591  mov     rbx, [rsp+28h+arg_0]
0x180025596  add     rsp, 20h
0x18002559a  pop     rdi
0x18002559b  retn
```
