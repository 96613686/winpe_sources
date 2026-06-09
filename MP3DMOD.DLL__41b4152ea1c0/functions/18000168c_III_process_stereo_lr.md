# III_process_stereo_lr

- ea: `0x18000168c`
- end: `0x1800016b7`
- name: `III_process_stereo_lr`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012d0`
- `0x180001f28`

## callees

- `0x18000168c`

## pseudocode

```c
__int64 __fastcall III_process_stereo_lr(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  __int64 result; // rax

  if ( a5 )
  {
    while ( a3 < a4 )
    {
      result = a3++;
      *(float *)(a1 + 4 * result) = (float)(*(float *)(a2 + 4 * result) + *(float *)(a1 + 4 * result)) * 0.5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000168c  cmp     [rsp+arg_20], 0
0x180001691  jnz     short loc_1800016B1
0x180001693  retn
0x180001694  movsxd  rax, r8d
0x180001697  inc     r8d
0x18000169a  movss   xmm0, dword ptr [rdx+rax*4]
0x18000169f  addss   xmm0, dword ptr [rcx+rax*4]
0x1800016a4  mulss   xmm0, cs:__real@3f000000
0x1800016ac  movss   dword ptr [rcx+rax*4], xmm0
0x1800016b1  cmp     r8d, r9d
0x1800016b4  jl      short loc_180001694
0x1800016b6  retn
```
