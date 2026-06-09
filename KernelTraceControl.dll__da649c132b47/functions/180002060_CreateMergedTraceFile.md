# CreateMergedTraceFile

- ea: `0x180002060`
- end: `0x180002105`
- name: `CreateMergedTraceFile`
- size: `165`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002060`
- `0x180004b5c`

## pseudocode

```c
__int64 __fastcall CreateMergedTraceFile(int a1, int a2, int a3, int a4)
{
  int *v5; // r10
  int v6; // r9d
  __int64 v7; // r11
  __int64 result; // rax

  v5 = &dword_18002BF84;
  v6 = 0;
  v7 = 14;
  do
  {
    if ( (a4 & *(v5 - 1)) == *(v5 - 1) )
      v6 |= *v5;
    v5 += 2;
    --v7;
  }
  while ( v7 );
  LODWORD(result) = MergeEtlExWithErrorContext(a3, a2, a1, v6);
  if ( (int)result >= 0 )
    return 0;
  if ( (result & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)result;
  if ( (result & 0xFFFFF000) == 0x8004E000 )
    return (result & 0x40) != 0 ? -2144862190 : 1306;
  return 1287;
}

```

## disassembly

```asm
0x180002060  mov     [rsp+arg_0], rbx
0x180002065  push    rdi
0x180002066  sub     rsp, 50h
0x18000206a  mov     ebx, r9d
0x18000206d  lea     r10, dword_18002BF84
0x180002074  xor     r9d, r9d
0x180002077  mov     edi, r8d
0x18000207a  lea     r11d, [r9+0Eh]
0x18000207e  mov     eax, [r10-4]
0x180002082  and     eax, ebx
0x180002084  cmp     eax, [r10-4]
0x180002088  jnz     short loc_18000208D
0x18000208a  or      r9d, [r10]
0x18000208d  add     r10, 8
0x180002091  sub     r11, 1
0x180002095  jnz     short loc_18000207E
0x180002097  and     [rsp+58h+var_18], r11d
0x18000209c  lea     rax, [rsp+58h+var_18]
0x1800020a1  mov     r8, rcx
0x1800020a4  mov     [rsp+58h+var_30], rax
0x1800020a9  mov     ecx, edi
0x1800020ab  call    MergeEtlExWithErrorContext
0x1800020b0  mov     ecx, eax
0x1800020b2  test    eax, eax
0x1800020b4  js      short loc_1800020C3
0x1800020b6  mov     eax, [rsp+58h+var_18]
0x1800020ba  neg     eax
0x1800020bc  sbb     eax, eax
0x1800020be  and     eax, 7Ah
0x1800020c1  jmp     short loc_1800020FA
0x1800020c3  and     eax, 1FFF0000h
0x1800020c8  cmp     eax, 70000h
0x1800020cd  jnz     short loc_1800020D4
0x1800020cf  movzx   eax, cx
0x1800020d2  jmp     short loc_1800020FA
0x1800020d4  mov     eax, ecx
0x1800020d6  and     eax, 0FFFFF000h
0x1800020db  cmp     eax, 8004E000h
0x1800020e0  jnz     short loc_1800020F5
0x1800020e2  and     cl, 40h
0x1800020e5  neg     cl
0x1800020e7  sbb     eax, eax
0x1800020e9  and     eax, 8027FAF8h
0x1800020ee  add     eax, 51Ah
0x1800020f3  jmp     short loc_1800020FA
0x1800020f5  mov     eax, 507h
0x1800020fa  mov     rbx, [rsp+58h+arg_0]
0x1800020ff  add     rsp, 50h
0x180002103  pop     rdi
0x180002104  retn
```
