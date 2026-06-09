# IsDeleteDCPresent

- ea: `0x1800056ac`
- end: `0x1800056fa`
- name: `IsDeleteDCPresent`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001db0`
- `0x180002670`

## callees

- `0x1800056ac`
- `0x1800058d4`

## pseudocode

```c
char IsDeleteDCPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1805E07A8 == 1 )
    return 1;
  if ( dword_1805E07A8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_1805E07A8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800056ac  sub     rsp, 28h
0x1800056b0  mov     ecx, cs:dword_1805E07A8
0x1800056b6  sub     ecx, 1
0x1800056b9  jz      short loc_1800056F3
0x1800056bb  cmp     ecx, 1
0x1800056be  jz      short loc_1800056EF
0x1800056c0  lea     rdx, [rsp+28h+arg_0]
0x1800056c5  mov     [rsp+28h+arg_0], 0
0x1800056ca  lea     rcx, asc_1800AAC78; ">@"
0x1800056d1  call    ApiSetQueryApiSetPresence_0
0x1800056d6  test    eax, eax
0x1800056d8  js      short loc_1800056EF
0x1800056da  mov     al, [rsp+28h+arg_0]
0x1800056de  mov     cl, al
0x1800056e0  neg     cl
0x1800056e2  sbb     edx, edx
0x1800056e4  add     edx, 2
0x1800056e7  mov     cs:dword_1805E07A8, edx
0x1800056ed  jmp     short loc_1800056F5
0x1800056ef  xor     al, al
0x1800056f1  jmp     short loc_1800056F5
0x1800056f3  mov     al, 1
0x1800056f5  add     rsp, 28h
0x1800056f9  retn
```
