# PrjfAllocateUnicodeString

- ea: `0x14003775c`
- end: `0x1400377bb`
- name: `PrjfAllocateUnicodeString`
- size: `95`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001658`
- `0x1400037e0`
- `0x140003a8c`
- `0x14000500c`
- `0x140006ca0`
- `0x1400083b0`
- `0x1400311b0`
- `0x1400368c4`
- `0x14003d2c8`
- `0x140040670`
- `0x140041a3c`
- `0x140041e28`
- `0x140042eac`
- `0x140043d88`
- `0x140044794`

## callees

- `0x14000b1d0`
- `0x14003775c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140037789`
- `ntoskrnl!ExAllocatePool2` at `0x140037789`

## pseudocode

```c
__int64 __fastcall PrjfAllocateUnicodeString(unsigned int a1, __int64 a2)
{
  __int64 Pool2; // rax

  if ( !*(_WORD *)(a2 + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  Pool2 = ExAllocatePool2(256, *(unsigned __int16 *)(a2 + 2), a1);
  *(_QWORD *)(a2 + 8) = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_WORD *)a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x14003775c  mov     [rsp+arg_0], rbx
0x140037761  mov     [rsp+arg_8], rsi
0x140037766  push    rdi
0x140037767  sub     rsp, 20h
0x14003776b  xor     esi, esi
0x14003776d  mov     rbx, rdx
0x140037770  mov     edi, ecx
0x140037772  cmp     [rdx+2], si
0x140037776  ja      short loc_14003777D
0x140037778  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003777d  movzx   edx, word ptr [rbx+2]
0x140037781  mov     r8d, edi
0x140037784  mov     ecx, 100h
0x140037789  call    cs:__imp_ExAllocatePool2
0x140037790  nop     dword ptr [rax+rax+00h]
0x140037795  mov     [rbx+8], rax
0x140037799  test    rax, rax
0x14003779c  jnz     short loc_1400377A5
0x14003779e  mov     eax, 0C000009Ah
0x1400377a3  jmp     short loc_1400377AA
0x1400377a5  mov     [rbx], si
0x1400377a8  mov     eax, esi
0x1400377aa  mov     rbx, [rsp+28h+arg_0]
0x1400377af  mov     rsi, [rsp+28h+arg_8]
0x1400377b4  add     rsp, 20h
0x1400377b8  pop     rdi
0x1400377b9  retn
```
