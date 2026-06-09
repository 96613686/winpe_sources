# AslRegistryOpenKey

- ea: `0x180036084`
- end: `0x1800360f9`
- name: `AslRegistryOpenKey`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180030054`
- `0x180030810`

## callees

- `0x18000f114`
- `0x18002d408`
- `0x180036084`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800360a5`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800360a5`

## string_xrefs

- `0x1800360b1`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x1800360c2`: `AslRegistryOpenKey`

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
0x180036084  mov     rax, rsp
0x180036087  mov     [rax+8], rbx
0x18003608b  mov     [rax+10h], rsi
0x18003608f  push    rdi
0x180036090  sub     rsp, 40h
0x180036094  mov     rsi, rcx
0x180036097  xorps   xmm0, xmm0
0x18003609a  lea     rcx, [rax-18h]; DestinationString
0x18003609e  mov     edi, r8d
0x1800360a1  movups  xmmword ptr [rax-18h], xmm0
0x1800360a5  call    cs:__imp_RtlInitUnicodeStringEx
0x1800360ab  mov     ebx, eax
0x1800360ad  test    eax, eax
0x1800360af  jns     short loc_1800360D5
0x1800360b1  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x1800360b8  mov     [rsp+48h+var_28], eax
0x1800360bc  mov     r8d, 388h
0x1800360c2  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x1800360c9  mov     ecx, 1
0x1800360ce  call    AslLogCallPrintf
0x1800360d3  jmp     short loc_1800360E7
0x1800360d5  mov     r8d, edi
0x1800360d8  lea     rdx, [rsp+48h+var_18]
0x1800360dd  mov     rcx, rsi
0x1800360e0  call    AslRegistryOpenKey_UStr
0x1800360e5  mov     ebx, eax
0x1800360e7  mov     rsi, [rsp+48h+arg_8]
0x1800360ec  mov     eax, ebx
0x1800360ee  mov     rbx, [rsp+48h+arg_0]
0x1800360f3  add     rsp, 40h
0x1800360f7  pop     rdi
0x1800360f8  retn
```
