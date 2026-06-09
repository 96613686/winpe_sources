# SrvWriteConsoleOutput

- ea: `0x140020630`
- end: `0x140020698`
- name: `SrvWriteConsoleOutput`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140020630`
- `0x1400215b0`
- `0x140021e10`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020687`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020687`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140020653`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140020653`

## pseudocode

```c
__int64 __fastcall SrvWriteConsoleOutput(__int64 a1)
{
  __int64 v1; // rdi
  int v4; // ebp

  v1 = *(_QWORD *)(a1 + 328);
  if ( !v1 )
    return 3221225480LL;
  RtlAcquireSRWLockExclusive(a1 + 48);
  v4 = CspWriteOutput(a1, v1 + 24);
  if ( v4 >= 0 && v1 == *(_QWORD *)(a1 + 96) )
    CspTriggerScreenRedraw(a1, a1 + 216, 0);
  RtlReleaseSRWLockExclusive(a1 + 48);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140020630  push    rbx
0x140020632  push    rbp
0x140020633  push    rsi
0x140020634  push    rdi
0x140020635  sub     rsp, 28h
0x140020639  mov     rdi, [rcx+148h]
0x140020640  mov     rbx, rcx
0x140020643  test    rdi, rdi
0x140020646  jnz     short loc_14002064F
0x140020648  mov     eax, 0C0000008h
0x14002064d  jmp     short loc_14002068F
0x14002064f  add     rcx, 30h ; '0'
0x140020653  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140020659  lea     rdx, [rdi+18h]
0x14002065d  mov     rcx, rbx
0x140020660  call    CspWriteOutput
0x140020665  mov     ebp, eax
0x140020667  test    eax, eax
0x140020669  js      short loc_140020683
0x14002066b  cmp     rdi, [rbx+60h]
0x14002066f  jnz     short loc_140020683
0x140020671  lea     rdx, [rbx+0D8h]
0x140020678  xor     r8d, r8d
0x14002067b  mov     rcx, rbx
0x14002067e  call    CspTriggerScreenRedraw
0x140020683  lea     rcx, [rbx+30h]
0x140020687  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14002068d  mov     eax, ebp
0x14002068f  add     rsp, 28h
0x140020693  pop     rdi
0x140020694  pop     rsi
0x140020695  pop     rbp
0x140020696  pop     rbx
0x140020697  retn
```
