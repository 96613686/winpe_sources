# IsWerReportCreatePresent

- ea: `0x140006530`
- end: `0x14000657e`
- name: `IsWerReportCreatePresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f3a4`

## callees

- `0x140006530`
- `0x1400067c3`

## pseudocode

```c
char IsWerReportCreatePresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_140018380 == 1 )
    return 1;
  if ( dword_140018380 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_140018380 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140006530  sub     rsp, 28h
0x140006534  mov     ecx, cs:dword_140018380
0x14000653a  sub     ecx, 1
0x14000653d  jz      short loc_140006577
0x14000653f  cmp     ecx, 1
0x140006542  jz      short loc_140006573
0x140006544  lea     rdx, [rsp+28h+arg_0]
0x140006549  mov     [rsp+28h+arg_0], 0
0x14000654e  lea     rcx, asc_140011168; ">@"
0x140006555  call    ApiSetQueryApiSetPresence_0
0x14000655a  test    eax, eax
0x14000655c  js      short loc_140006573
0x14000655e  mov     al, [rsp+28h+arg_0]
0x140006562  mov     cl, al
0x140006564  neg     cl
0x140006566  sbb     edx, edx
0x140006568  add     edx, 2
0x14000656b  mov     cs:dword_140018380, edx
0x140006571  jmp     short loc_140006579
0x140006573  xor     al, al
0x140006575  jmp     short loc_140006579
0x140006577  mov     al, 1
0x140006579  add     rsp, 28h
0x14000657d  retn
```
