# IsPostThreadMessageWPresent

- ea: `0x180011690`
- end: `0x1800116de`
- name: `IsPostThreadMessageWPresent`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c570`
- `0x18000dd90`
- `0x18001d130`
- `0x18001f11c`

## callees

- `0x180011690`
- `0x1800119c1`

## pseudocode

```c
char IsPostThreadMessageWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18002C500 == 1 )
    return 1;
  if ( dword_18002C500 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"@B", &v1) < 0 )
    return 0;
  result = v1;
  dword_18002C500 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180011690  sub     rsp, 28h
0x180011694  mov     ecx, cs:dword_18002C500
0x18001169a  sub     ecx, 1
0x18001169d  jz      short loc_1800116D7
0x18001169f  cmp     ecx, 1
0x1800116a2  jz      short loc_1800116D3
0x1800116a4  lea     rdx, [rsp+28h+arg_0]
0x1800116a9  mov     [rsp+28h+arg_0], 0
0x1800116ae  lea     rcx, aB; "@B"
0x1800116b5  call    ApiSetQueryApiSetPresence_0
0x1800116ba  test    eax, eax
0x1800116bc  js      short loc_1800116D3
0x1800116be  mov     al, [rsp+28h+arg_0]
0x1800116c2  mov     cl, al
0x1800116c4  neg     cl
0x1800116c6  sbb     edx, edx
0x1800116c8  add     edx, 2
0x1800116cb  mov     cs:dword_18002C500, edx
0x1800116d1  jmp     short loc_1800116D9
0x1800116d3  xor     al, al
0x1800116d5  jmp     short loc_1800116D9
0x1800116d7  mov     al, 1
0x1800116d9  add     rsp, 28h
0x1800116dd  retn
```
