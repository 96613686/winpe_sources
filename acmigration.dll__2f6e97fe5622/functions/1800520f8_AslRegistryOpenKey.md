# AslRegistryOpenKey

- ea: `0x1800520f8`
- end: `0x18005216d`
- name: `AslRegistryOpenKey`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18005a904`
- `0x18005b258`

## callees

- `0x1800520f8`
- `0x180052174`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180052119`
- `ntdll!RtlInitUnicodeStringEx` at `0x180052119`

## string_xrefs

- `0x180052125`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x180052136`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(void **a1, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  inited = RtlInitUnicodeStringEx(&v8, a2);
  v6 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryOpenKey_UStr(a1, &v8, a3);
  else
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  return v6;
}

```

## disassembly

```asm
0x1800520f8  mov     rax, rsp
0x1800520fb  mov     [rax+8], rbx
0x1800520ff  mov     [rax+10h], rsi
0x180052103  push    rdi
0x180052104  sub     rsp, 40h
0x180052108  mov     rsi, rcx
0x18005210b  xorps   xmm0, xmm0
0x18005210e  lea     rcx, [rax-18h]; DestinationString
0x180052112  mov     edi, r8d
0x180052115  movups  xmmword ptr [rax-18h], xmm0
0x180052119  call    cs:__imp_RtlInitUnicodeStringEx
0x18005211f  mov     ebx, eax
0x180052121  test    eax, eax
0x180052123  jns     short loc_180052149
0x180052125  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18005212c  mov     [rsp+48h+var_28], eax
0x180052130  mov     r8d, 388h
0x180052136  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18005213d  mov     ecx, 1
0x180052142  call    AslLogCallPrintf
0x180052147  jmp     short loc_18005215B
0x180052149  mov     r8d, edi
0x18005214c  lea     rdx, [rsp+48h+var_18]
0x180052151  mov     rcx, rsi
0x180052154  call    AslRegistryOpenKey_UStr
0x180052159  mov     ebx, eax
0x18005215b  mov     rsi, [rsp+48h+arg_8]
0x180052160  mov     eax, ebx
0x180052162  mov     rbx, [rsp+48h+arg_0]
0x180052167  add     rsp, 40h
0x18005216b  pop     rdi
0x18005216c  retn
```
