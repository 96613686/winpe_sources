# IsCreateWindowExWPresent

- ea: `0x14000267c`
- end: `0x1400026ca`
- name: `IsCreateWindowExWPresent`
- size: `78`
- prototype: `char()`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003714`
- `0x140003920`
- `0x140003cf8`

## callees

- `0x14000267c`
- `0x1400028b9`

## pseudocode

```c
char IsCreateWindowExWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_14000C7E0 == 1 )
    return 1;
  if ( dword_14000C7E0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_14000C7E0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x14000267c  sub     rsp, 28h
0x140002680  mov     ecx, cs:dword_14000C7E0
0x140002686  sub     ecx, 1
0x140002689  jz      short loc_1400026C3
0x14000268b  cmp     ecx, 1
0x14000268e  jz      short loc_1400026BF
0x140002690  lea     rdx, [rsp+28h+arg_0]
0x140002695  mov     [rsp+28h+arg_0], 0
0x14000269a  lea     rcx, asc_140006A98; ">@"
0x1400026a1  call    ApiSetQueryApiSetPresence_0
0x1400026a6  test    eax, eax
0x1400026a8  js      short loc_1400026BF
0x1400026aa  mov     al, [rsp+28h+arg_0]
0x1400026ae  mov     cl, al
0x1400026b0  neg     cl
0x1400026b2  sbb     edx, edx
0x1400026b4  add     edx, 2
0x1400026b7  mov     cs:dword_14000C7E0, edx
0x1400026bd  jmp     short loc_1400026C5
0x1400026bf  xor     al, al
0x1400026c1  jmp     short loc_1400026C5
0x1400026c3  mov     al, 1
0x1400026c5  add     rsp, 28h
0x1400026c9  retn
```
