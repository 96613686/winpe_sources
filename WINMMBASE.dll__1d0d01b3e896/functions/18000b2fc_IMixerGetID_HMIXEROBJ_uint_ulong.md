# IMixerGetID(HMIXEROBJ__ *,uint *,ulong)

- ea: `0x18000b2fc`
- end: `0x18000b35e`
- name: `?IMixerGetID@@YAIPEAUHMIXEROBJ__@@PEAIK@Z`
- size: `98`
- prototype: `unsigned int __fastcall(HMIXEROBJ uDeviceID, unsigned int *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a8c`
- `0x18000a960`
- `0x18000af80`
- `0x18000b090`
- `0x18000b800`
- `0x180010220`
- `0x18001ac80`

## callees

- `0x18000b2fc`
- `0x18000b364`
- `0x180019c9c`

## pseudocode

```c
__int64 __fastcall IMixerGetID(HMIXEROBJ uDeviceID, unsigned int *a2, unsigned int a3)
{
  unsigned int IDFromEndpoint; // ebx

  if ( (a3 & 0xFFFFFFF) != 0 )
    return 10;
  if ( !a2 )
    return 11;
  *a2 = -1;
  IDFromEndpoint = IMixerGetIDFromEndpoint(uDeviceID, a2, a3);
  if ( IDFromEndpoint == 6 && !IMixerGetIDFromMatchingCaps(uDeviceID, a2, a3) )
    return 0;
  return IDFromEndpoint;
}

```

## disassembly

```asm
0x18000b2fc  push    rbx
0x18000b2fe  push    rbp
0x18000b2ff  push    rsi
0x18000b300  push    rdi
0x18000b301  sub     rsp, 28h
0x18000b305  mov     esi, r8d
0x18000b308  mov     rdi, rdx
0x18000b30b  mov     rbp, rcx
0x18000b30e  test    r8d, 0FFFFFFFh
0x18000b315  jnz     short loc_18000B340
0x18000b317  test    rdx, rdx
0x18000b31a  jz      short loc_18000B339
0x18000b31c  mov     dword ptr [rdx], 0FFFFFFFFh
0x18000b322  call    ?IMixerGetIDFromEndpoint@@YAIPEAUHMIXEROBJ__@@PEAIK@Z; IMixerGetIDFromEndpoint(HMIXEROBJ__ *,uint *,ulong)
0x18000b327  mov     ebx, eax
0x18000b329  cmp     eax, 6
0x18000b32c  jz      short loc_18000B347
0x18000b32e  mov     eax, ebx
0x18000b330  add     rsp, 28h
0x18000b334  pop     rdi
0x18000b335  pop     rsi
0x18000b336  pop     rbp
0x18000b337  pop     rbx
0x18000b338  retn
0x18000b339  mov     eax, 0Bh
0x18000b33e  jmp     short loc_18000B330
0x18000b340  mov     eax, 0Ah
0x18000b345  jmp     short loc_18000B330
0x18000b347  mov     r8d, esi; unsigned int
0x18000b34a  mov     rdx, rdi; unsigned int *
0x18000b34d  mov     rcx, rbp; uDeviceID
0x18000b350  call    ?IMixerGetIDFromMatchingCaps@@YAIPEAUHMIXEROBJ__@@PEAIK@Z; IMixerGetIDFromMatchingCaps(HMIXEROBJ__ *,uint *,ulong)
0x18000b355  xor     ecx, ecx
0x18000b357  test    eax, eax
0x18000b359  cmovz   ebx, ecx
0x18000b35c  jmp     short loc_18000B32E
```
