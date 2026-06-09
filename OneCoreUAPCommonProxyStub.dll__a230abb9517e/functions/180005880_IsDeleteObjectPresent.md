# IsDeleteObjectPresent

- ea: `0x180005880`
- end: `0x1800058ce`
- name: `IsDeleteObjectPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a500`

## callees

- `0x180005880`
- `0x1800058d4`

## pseudocode

```c
char IsDeleteObjectPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1805E07D8 == 1 )
    return 1;
  if ( dword_1805E07D8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"FH", &v1) < 0 )
    return 0;
  result = v1;
  dword_1805E07D8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180005880  sub     rsp, 28h
0x180005884  mov     ecx, cs:dword_1805E07D8
0x18000588a  sub     ecx, 1
0x18000588d  jz      short loc_1800058C7
0x18000588f  cmp     ecx, 1
0x180005892  jz      short loc_1800058C3
0x180005894  lea     rdx, [rsp+28h+arg_0]
0x180005899  mov     [rsp+28h+arg_0], 0
0x18000589e  lea     rcx, aFh; "FH"
0x1800058a5  call    ApiSetQueryApiSetPresence_0
0x1800058aa  test    eax, eax
0x1800058ac  js      short loc_1800058C3
0x1800058ae  mov     al, [rsp+28h+arg_0]
0x1800058b2  mov     cl, al
0x1800058b4  neg     cl
0x1800058b6  sbb     edx, edx
0x1800058b8  add     edx, 2
0x1800058bb  mov     cs:dword_1805E07D8, edx
0x1800058c1  jmp     short loc_1800058C9
0x1800058c3  xor     al, al
0x1800058c5  jmp     short loc_1800058C9
0x1800058c7  mov     al, 1
0x1800058c9  add     rsp, 28h
0x1800058cd  retn
```
