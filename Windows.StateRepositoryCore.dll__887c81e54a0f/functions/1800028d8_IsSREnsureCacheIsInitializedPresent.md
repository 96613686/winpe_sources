# IsSREnsureCacheIsInitializedPresent

- ea: `0x1800028d8`
- end: `0x180002926`
- name: `IsSREnsureCacheIsInitializedPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d8b0`

## callees

- `0x1800028d8`
- `0x180002bfa`

## pseudocode

```c
char IsSREnsureCacheIsInitializedPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180018330 == 1 )
    return 1;
  if ( dword_180018330 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"np", &v1) < 0 )
    return 0;
  result = v1;
  dword_180018330 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800028d8  sub     rsp, 28h
0x1800028dc  mov     ecx, cs:dword_180018330
0x1800028e2  sub     ecx, 1
0x1800028e5  jz      short loc_18000291F
0x1800028e7  cmp     ecx, 1
0x1800028ea  jz      short loc_18000291B
0x1800028ec  lea     rdx, [rsp+28h+arg_0]
0x1800028f1  mov     [rsp+28h+arg_0], 0
0x1800028f6  lea     rcx, aNp; "np"
0x1800028fd  call    ApiSetQueryApiSetPresence_0
0x180002902  test    eax, eax
0x180002904  js      short loc_18000291B
0x180002906  mov     al, [rsp+28h+arg_0]
0x18000290a  mov     cl, al
0x18000290c  neg     cl
0x18000290e  sbb     edx, edx
0x180002910  add     edx, 2
0x180002913  mov     cs:dword_180018330, edx
0x180002919  jmp     short loc_180002921
0x18000291b  xor     al, al
0x18000291d  jmp     short loc_180002921
0x18000291f  mov     al, 1
0x180002921  add     rsp, 28h
0x180002925  retn
```
