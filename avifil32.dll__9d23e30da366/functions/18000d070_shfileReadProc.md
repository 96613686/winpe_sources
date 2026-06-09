# shfileReadProc

- ea: `0x18000d070`
- end: `0x18000d0d3`
- name: `shfileReadProc`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d070`
- `0x180014880`

## import_xrefs

- `WINMM!mmioSeek` at `0x18000d0a4`
- `WINMM!mmioSeek` at `0x18000d0a4`

## pseudocode

```c
__int64 __fastcall shfileReadProc(__int64 a1, LONG a2, unsigned int a3, char *a4)
{
  __int64 v4; // rax
  LONG v8; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 )
  {
    *(_DWORD *)(v4 + 372) = a2;
    v8 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 372LL);
  }
  else
  {
    v8 = mmioSeek(*(HMMIO *)(a1 + 8), a2, 0);
  }
  if ( v8 == -1 )
    return 0xFFFFFFFFLL;
  if ( shfileRead(a1, a4, a3) != a3 )
    return (unsigned int)-1;
  return a3;
}

```

## disassembly

```asm
0x18000d070  push    rbx
0x18000d072  push    rbp
0x18000d073  push    rsi
0x18000d074  push    rdi
0x18000d075  sub     rsp, 28h
0x18000d079  mov     rax, [rcx+10h]
0x18000d07d  mov     rsi, r9
0x18000d080  mov     edi, r8d
0x18000d083  mov     rbx, rcx
0x18000d086  test    rax, rax
0x18000d089  jz      short loc_18000D09D
0x18000d08b  mov     [rax+174h], edx
0x18000d091  mov     rax, [rcx+10h]
0x18000d095  mov     eax, [rax+174h]
0x18000d09b  jmp     short loc_18000D0AA
0x18000d09d  mov     rcx, [rcx+8]; hmmio
0x18000d0a1  xor     r8d, r8d; iOrigin
0x18000d0a4  call    cs:__imp_mmioSeek
0x18000d0aa  or      ebp, 0FFFFFFFFh
0x18000d0ad  cmp     eax, ebp
0x18000d0af  jz      short loc_18000D0C8
0x18000d0b1  mov     r8d, edi
0x18000d0b4  mov     rdx, rsi
0x18000d0b7  mov     rcx, rbx
0x18000d0ba  call    shfileRead
0x18000d0bf  cmp     eax, edi
0x18000d0c1  cmovnz  edi, ebp
0x18000d0c4  mov     eax, edi
0x18000d0c6  jmp     short loc_18000D0CA
0x18000d0c8  mov     eax, ebp
0x18000d0ca  add     rsp, 28h
0x18000d0ce  pop     rdi
0x18000d0cf  pop     rsi
0x18000d0d0  pop     rbp
0x18000d0d1  pop     rbx
0x18000d0d2  retn
```
