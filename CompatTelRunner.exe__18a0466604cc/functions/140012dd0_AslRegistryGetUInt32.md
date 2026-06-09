# AslRegistryGetUInt32

- ea: `0x140012dd0`
- end: `0x140012e4c`
- name: `AslRegistryGetUInt32`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400150e8`

## callees

- `0x140012dd0`
- `0x140012e54`
- `0x1400151b0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140012df8`
- `ntdll!RtlInitUnicodeStringEx` at `0x140012df8`

## string_xrefs

- `0x140012e15`: `AslRegistryGetUInt32`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(__int64 a1, __int64 a2)
{
  NTSTATUS inited; // eax
  unsigned int v5; // ebx
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  inited = RtlInitUnicodeStringEx(&v7, L"LogFlags");
  v5 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryGetUInt32_UStr(a1, a2, &v7);
  else
    AslLogCallPrintf(1, "AslRegistryGetUInt32", 1148, "RtlInitUnicodeStringEx failed [%x]", inited);
  return v5;
}

```

## disassembly

```asm
0x140012dd0  mov     rax, rsp
0x140012dd3  mov     [rax+8], rbx
0x140012dd7  mov     [rax+10h], rsi
0x140012ddb  push    rdi
0x140012ddc  sub     rsp, 40h
0x140012de0  mov     rdi, rdx
0x140012de3  mov     rsi, rcx
0x140012de6  xorps   xmm0, xmm0
0x140012de9  lea     rdx, aLogflags; "LogFlags"
0x140012df0  lea     rcx, [rax-18h]; DestinationString
0x140012df4  movups  xmmword ptr [rax-18h], xmm0
0x140012df8  call    cs:__imp_RtlInitUnicodeStringEx
0x140012dfe  mov     ebx, eax
0x140012e00  test    eax, eax
0x140012e02  jns     short loc_140012E28
0x140012e04  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x140012e0b  mov     [rsp+48h+var_28], eax
0x140012e0f  mov     r8d, 47Ch
0x140012e15  lea     rdx, aAslregistryget_2; "AslRegistryGetUInt32"
0x140012e1c  mov     ecx, 1
0x140012e21  call    AslLogCallPrintf
0x140012e26  jmp     short loc_140012E3A
0x140012e28  lea     r8, [rsp+48h+var_18]
0x140012e2d  mov     rdx, rdi
0x140012e30  mov     rcx, rsi
0x140012e33  call    AslRegistryGetUInt32_UStr
0x140012e38  mov     ebx, eax
0x140012e3a  mov     rsi, [rsp+48h+arg_8]
0x140012e3f  mov     eax, ebx
0x140012e41  mov     rbx, [rsp+48h+arg_0]
0x140012e46  add     rsp, 40h
0x140012e4a  pop     rdi
0x140012e4b  retn
```
