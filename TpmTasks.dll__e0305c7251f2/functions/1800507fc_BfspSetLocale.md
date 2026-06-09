# BfspSetLocale

- ea: `0x1800507fc`
- end: `0x18005088b`
- name: `BfspSetLocale`
- size: `143`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e544`
- `0x18004eb2c`
- `0x18004ede8`
- `0x18004f244`

## callees

- `0x18004cdd4`
- `0x1800507fc`

## import_xrefs

- `bcd!BcdSetElementData` at `0x18005084e`
- `bcd!BcdSetElementData` at `0x18005084e`
- `bcd!BcdCloseObject` at `0x180050878`
- `bcd!BcdCloseObject` at `0x180050878`
- `bcd!BcdOpenObject` at `0x180050812`
- `bcd!BcdOpenObject` at `0x180050812`

## pseudocode

```c
__int64 __fastcall BfspSetLocale(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  int v5; // eax
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v2 = BcdOpenObject(a1, a2, &v7);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)qword_1800A4548 + v4) );
    v5 = BcdSetElementData(v7, 301989893, qword_1800A4548, (unsigned int)(2 * v4 + 2));
    v3 = v5;
    if ( v5 < 0 )
      BfspLogMessage(4, L"Failed to set locale data. Status = [%x]", (unsigned int)v5);
  }
  else
  {
    BfspLogMessage(4, L"Failed to get handle to BCD object. Status = [%x]", (unsigned int)v2);
  }
  if ( v7 )
    BcdCloseObject(v7);
  return v3;
}

```

## disassembly

```asm
0x1800507fc  mov     [rsp+arg_0], rbx
0x180050801  push    rdi
0x180050802  sub     rsp, 20h
0x180050806  xor     edi, edi
0x180050808  lea     r8, [rsp+28h+arg_10]
0x18005080d  mov     [rsp+28h+arg_10], rdi
0x180050812  call    cs:__imp_BcdOpenObject
0x180050818  mov     ebx, eax
0x18005081a  test    eax, eax
0x18005081c  jns     short loc_180050827
0x18005081e  lea     rdx, aFailedToGetHan_2; "Failed to get handle to BCD object. Sta"...
0x180050825  jmp     short loc_180050861
0x180050827  mov     r8, cs:qword_1800A4548
0x18005082e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180050832  inc     r9
0x180050835  cmp     [r8+r9*2], di
0x18005083a  jnz     short loc_180050832
0x18005083c  mov     rcx, [rsp+28h+arg_10]
0x180050841  lea     r9d, ds:2[r9*2]
0x180050849  mov     edx, 12000005h
0x18005084e  call    cs:__imp_BcdSetElementData
0x180050854  mov     ebx, eax
0x180050856  test    eax, eax
0x180050858  jns     short loc_18005086E
0x18005085a  lea     rdx, aFailedToSetLoc; "Failed to set locale data. Status = [%x"...
0x180050861  mov     r8d, eax
0x180050864  mov     ecx, 4
0x180050869  call    BfspLogMessage
0x18005086e  mov     rcx, [rsp+28h+arg_10]
0x180050873  test    rcx, rcx
0x180050876  jz      short loc_18005087E
0x180050878  call    cs:__imp_BcdCloseObject
0x18005087e  mov     eax, ebx
0x180050880  mov     rbx, [rsp+28h+arg_0]
0x180050885  add     rsp, 20h
0x180050889  pop     rdi
0x18005088a  retn
```
