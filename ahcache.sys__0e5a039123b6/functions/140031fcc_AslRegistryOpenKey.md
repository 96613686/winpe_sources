# AslRegistryOpenKey

- ea: `0x140031fcc`
- end: `0x140032041`
- name: `AslRegistryOpenKey`
- size: `117`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007450`
- `0x1400479a8`

## callees

- `0x14000447b`
- `0x140031fcc`
- `0x14003e364`
- `0x140055100`

## string_xrefs

- `0x140031ff8`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x140032009`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  inited = RtlInitUnicodeStringEx_0(&v8, a2);
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
0x140031fcc  mov     rax, rsp
0x140031fcf  mov     [rax+8], rbx
0x140031fd3  mov     [rax+10h], rsi
0x140031fd7  push    rdi
0x140031fd8  sub     rsp, 40h
0x140031fdc  mov     rsi, rcx
0x140031fdf  xorps   xmm0, xmm0
0x140031fe2  lea     rcx, [rax-18h]; DestinationString
0x140031fe6  mov     edi, r8d
0x140031fe9  movups  xmmword ptr [rax-18h], xmm0
0x140031fed  call    RtlInitUnicodeStringEx_0
0x140031ff2  mov     ebx, eax
0x140031ff4  test    eax, eax
0x140031ff6  jns     short loc_14003201C
0x140031ff8  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x140031fff  mov     [rsp+48h+var_28], eax
0x140032003  mov     r8d, 388h
0x140032009  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x140032010  mov     ecx, 1
0x140032015  call    AslLogCallPrintf
0x14003201a  jmp     short loc_14003202E
0x14003201c  mov     r8d, edi
0x14003201f  lea     rdx, [rsp+48h+var_18]
0x140032024  mov     rcx, rsi
0x140032027  call    AslRegistryOpenKey_UStr
0x14003202c  mov     ebx, eax
0x14003202e  mov     rsi, [rsp+48h+arg_8]
0x140032033  mov     eax, ebx
0x140032035  mov     rbx, [rsp+48h+arg_0]
0x14003203a  add     rsp, 40h
0x14003203e  pop     rdi
0x14003203f  retn
```
