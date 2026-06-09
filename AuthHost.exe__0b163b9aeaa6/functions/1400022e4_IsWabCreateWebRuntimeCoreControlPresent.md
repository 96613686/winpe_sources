# IsWabCreateWebRuntimeCoreControlPresent

- ea: `0x1400022e4`
- end: `0x140002332`
- name: `IsWabCreateWebRuntimeCoreControlPresent`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ac0`
- `0x140006340`
- `0x140007cd4`

## callees

- `0x1400022e4`
- `0x140002ae6`

## pseudocode

```c
char IsWabCreateWebRuntimeCoreControlPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_14001D8B0 == 1 )
    return 1;
  if ( dword_14001D8B0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"NP", &v1) < 0 )
    return 0;
  result = v1;
  dword_14001D8B0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1400022e4  sub     rsp, 28h
0x1400022e8  mov     ecx, cs:dword_14001D8B0
0x1400022ee  sub     ecx, 1
0x1400022f1  jz      short loc_14000232B
0x1400022f3  cmp     ecx, 1
0x1400022f6  jz      short loc_140002327
0x1400022f8  lea     rdx, [rsp+28h+arg_0]
0x1400022fd  mov     [rsp+28h+arg_0], 0
0x140002302  lea     rcx, aNp; "NP"
0x140002309  call    ApiSetQueryApiSetPresence_0
0x14000230e  test    eax, eax
0x140002310  js      short loc_140002327
0x140002312  mov     al, [rsp+28h+arg_0]
0x140002316  mov     cl, al
0x140002318  neg     cl
0x14000231a  sbb     edx, edx
0x14000231c  add     edx, 2
0x14000231f  mov     cs:dword_14001D8B0, edx
0x140002325  jmp     short loc_14000232D
0x140002327  xor     al, al
0x140002329  jmp     short loc_14000232D
0x14000232b  mov     al, 1
0x14000232d  add     rsp, 28h
0x140002331  retn
```
