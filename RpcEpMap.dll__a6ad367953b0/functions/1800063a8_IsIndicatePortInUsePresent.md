# IsIndicatePortInUsePresent

- ea: `0x1800063a8`
- end: `0x1800063f6`
- name: `IsIndicatePortInUsePresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010b0`
- `0x1800018a0`
- `0x180002798`

## callees

- `0x1800063a8`
- `0x1800064dc`

## pseudocode

```c
char IsIndicatePortInUsePresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180013A7C == 1 )
    return 1;
  if ( dword_180013A7C == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"JL", &v1) < 0 )
    return 0;
  result = v1;
  dword_180013A7C = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800063a8  sub     rsp, 28h
0x1800063ac  mov     ecx, cs:dword_180013A7C
0x1800063b2  sub     ecx, 1
0x1800063b5  jz      short loc_1800063EF
0x1800063b7  cmp     ecx, 1
0x1800063ba  jz      short loc_1800063EB
0x1800063bc  lea     rdx, [rsp+28h+arg_0]
0x1800063c1  mov     [rsp+28h+arg_0], 0
0x1800063c6  lea     rcx, aJl; "JL"
0x1800063cd  call    ApiSetQueryApiSetPresence_0
0x1800063d2  test    eax, eax
0x1800063d4  js      short loc_1800063EB
0x1800063d6  mov     al, [rsp+28h+arg_0]
0x1800063da  mov     cl, al
0x1800063dc  neg     cl
0x1800063de  sbb     edx, edx
0x1800063e0  add     edx, 2
0x1800063e3  mov     cs:dword_180013A7C, edx
0x1800063e9  jmp     short loc_1800063F1
0x1800063eb  xor     al, al
0x1800063ed  jmp     short loc_1800063F1
0x1800063ef  mov     al, 1
0x1800063f1  add     rsp, 28h
0x1800063f5  retn
```
