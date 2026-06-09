# IsUMgrQueryUserContextPresent

- ea: `0x1800024c4`
- end: `0x180002512`
- name: `IsUMgrQueryUserContextPresent`
- size: `78`
- prototype: `char()`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054b0`
- `0x180005830`
- `0x180005880`

## callees

- `0x1800024c4`
- `0x1800026ac`

## pseudocode

```c
char IsUMgrQueryUserContextPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800118B8 == 1 )
    return 1;
  if ( dword_1800118B8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800118B8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800024c4  sub     rsp, 28h
0x1800024c8  mov     ecx, cs:dword_1800118B8
0x1800024ce  sub     ecx, 1
0x1800024d1  jz      short loc_18000250B
0x1800024d3  cmp     ecx, 1
0x1800024d6  jz      short loc_180002507
0x1800024d8  lea     rdx, [rsp+28h+arg_0]
0x1800024dd  mov     [rsp+28h+arg_0], 0
0x1800024e2  lea     rcx, aBd; "BD"
0x1800024e9  call    ApiSetQueryApiSetPresence_0
0x1800024ee  test    eax, eax
0x1800024f0  js      short loc_180002507
0x1800024f2  mov     al, [rsp+28h+arg_0]
0x1800024f6  mov     cl, al
0x1800024f8  neg     cl
0x1800024fa  sbb     edx, edx
0x1800024fc  add     edx, 2
0x1800024ff  mov     cs:dword_1800118B8, edx
0x180002505  jmp     short loc_18000250D
0x180002507  xor     al, al
0x180002509  jmp     short loc_18000250D
0x18000250b  mov     al, 1
0x18000250d  add     rsp, 28h
0x180002511  retn
```
