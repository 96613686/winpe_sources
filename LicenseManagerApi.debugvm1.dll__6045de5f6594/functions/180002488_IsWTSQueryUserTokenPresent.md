# IsWTSQueryUserTokenPresent

- ea: `0x180002488`
- end: `0x1800024d6`
- name: `IsWTSQueryUserTokenPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f060`

## callees

- `0x180002488`
- `0x1800029df`

## pseudocode

```c
char IsWTSQueryUserTokenPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001A488 == 1 )
    return 1;
  if ( dword_18001A488 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"DF", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001A488 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180002488  sub     rsp, 28h
0x18000248c  mov     ecx, cs:dword_18001A488
0x180002492  sub     ecx, 1
0x180002495  jz      short loc_1800024CF
0x180002497  cmp     ecx, 1
0x18000249a  jz      short loc_1800024CB
0x18000249c  lea     rdx, [rsp+28h+arg_0]
0x1800024a1  mov     [rsp+28h+arg_0], 0
0x1800024a6  lea     rcx, aDf; "DF"
0x1800024ad  call    ApiSetQueryApiSetPresence_0
0x1800024b2  test    eax, eax
0x1800024b4  js      short loc_1800024CB
0x1800024b6  mov     al, [rsp+28h+arg_0]
0x1800024ba  mov     cl, al
0x1800024bc  neg     cl
0x1800024be  sbb     edx, edx
0x1800024c0  add     edx, 2
0x1800024c3  mov     cs:dword_18001A488, edx
0x1800024c9  jmp     short loc_1800024D1
0x1800024cb  xor     al, al
0x1800024cd  jmp     short loc_1800024D1
0x1800024cf  mov     al, 1
0x1800024d1  add     rsp, 28h
0x1800024d5  retn
```
