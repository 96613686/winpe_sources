# auippDeleteFFTCcsInfo

- ea: `0x18000a0ec`
- end: `0x18000a14e`
- name: `auippDeleteFFTCcsInfo`
- size: `98`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0a0`

## callees

- `0x18000a0ec`
- `0x1800124f8`
- `0x180017050`

## pseudocode

```c
void __fastcall auippDeleteFFTCcsInfo(_DWORD *Block)
{
  int v2; // edi
  int v3; // esi

  if ( Block )
  {
    if ( *((_QWORD *)Block + 1) )
    {
      v2 = 0;
      v3 = Block[1] - *Block + 1;
      if ( v3 > 0 )
      {
        do
        {
          if ( *(_QWORD *)(32LL * (unsigned int)v2 + *((_QWORD *)Block + 1)) )
            ippsFFTFree_R_32f();
          ++v2;
        }
        while ( v2 < v3 );
      }
    }
  }
  prvDeleteFFTInfo((void **)Block);
}

```

## disassembly

```asm
0x18000a0ec  mov     [rsp+arg_0], rbx
0x18000a0f1  mov     [rsp+arg_8], rsi
0x18000a0f6  push    rdi
0x18000a0f7  sub     rsp, 20h
0x18000a0fb  mov     rbx, rcx
0x18000a0fe  test    rcx, rcx
0x18000a101  jz      short loc_18000A130
0x18000a103  cmp     qword ptr [rcx+8], 0
0x18000a108  jz      short loc_18000A130
0x18000a10a  mov     esi, [rcx+4]
0x18000a10d  xor     edi, edi
0x18000a10f  sub     esi, [rcx]
0x18000a111  inc     esi
0x18000a113  test    esi, esi
0x18000a115  jle     short loc_18000A130
0x18000a117  mov     rax, [rbx+8]
0x18000a11b  mov     ecx, edi
0x18000a11d  shl     rcx, 5
0x18000a121  mov     rcx, [rcx+rax]
0x18000a125  test    rcx, rcx
0x18000a128  jnz     short loc_18000A147
0x18000a12a  inc     edi
0x18000a12c  cmp     edi, esi
0x18000a12e  jl      short loc_18000A117
0x18000a130  mov     rcx, rbx; Block
0x18000a133  mov     rbx, [rsp+28h+arg_0]
0x18000a138  mov     rsi, [rsp+28h+arg_8]
0x18000a13d  add     rsp, 20h
0x18000a141  pop     rdi
0x18000a142  jmp     prvDeleteFFTInfo
0x18000a147  call    ippsFFTFree_R_32f
0x18000a14c  jmp     short loc_18000A12A
```
