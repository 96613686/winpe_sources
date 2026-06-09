# IsGetDIBitsPresent

- ea: `0x18000578c`
- end: `0x1800057da`
- name: `IsGetDIBitsPresent`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002130`
- `0x180002670`
- `0x180002b5c`

## callees

- `0x18000578c`
- `0x1800058d4`

## pseudocode

```c
char IsGetDIBitsPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1805E07C0 == 1 )
    return 1;
  if ( dword_1805E07C0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0((__int64)L"46", (__int64)&v1) < 0 )
    return 0;
  result = v1;
  dword_1805E07C0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000578c  sub     rsp, 28h
0x180005790  mov     ecx, cs:dword_1805E07C0
0x180005796  sub     ecx, 1
0x180005799  jz      short loc_1800057D3
0x18000579b  cmp     ecx, 1
0x18000579e  jz      short loc_1800057CF
0x1800057a0  lea     rdx, [rsp+28h+arg_0]
0x1800057a5  mov     [rsp+28h+arg_0], 0
0x1800057aa  lea     rcx, a46; "46"
0x1800057b1  call    ApiSetQueryApiSetPresence_0
0x1800057b6  test    eax, eax
0x1800057b8  js      short loc_1800057CF
0x1800057ba  mov     al, [rsp+28h+arg_0]
0x1800057be  mov     cl, al
0x1800057c0  neg     cl
0x1800057c2  sbb     edx, edx
0x1800057c4  add     edx, 2
0x1800057c7  mov     cs:dword_1805E07C0, edx
0x1800057cd  jmp     short loc_1800057D5
0x1800057cf  xor     al, al
0x1800057d1  jmp     short loc_1800057D5
0x1800057d3  mov     al, 1
0x1800057d5  add     rsp, 28h
0x1800057d9  retn
```
