# Crashdump_Endpoint_PrepareForHibernate

- ea: `0x140054554`
- end: `0x140054619`
- name: `Crashdump_Endpoint_PrepareForHibernate`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140055778`

## callees

- `0x140054554`
- `0x140054930`
- `0x1400549fc`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054572`
- `ntoskrnl!DbgPrintEx` at `0x1400545d3`
- `ntoskrnl!DbgPrintEx` at `0x1400545ff`
- `ntoskrnl!DbgPrintEx` at `0x140054572`
- `ntoskrnl!DbgPrintEx` at `0x1400545d3`
- `ntoskrnl!DbgPrintEx` at `0x1400545ff`

## string_xrefs

- `0x1400545c2`: `XHCIDUMP: Crashdump_Endpoint_StopEndpoint failed with error 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Endpoint_PrepareForHibernate(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Endpoint_PrepareForHibernate: begin\n");
  memset(*(void **)(a1 + 88), 0, *(unsigned int *)(a1 + 96));
  memset(*(void **)(a1 + 112), 0, *(unsigned int *)(a1 + 120));
  *(_QWORD *)(a1 + 168) = 1;
  *(_DWORD *)(a1 + 160) = 0;
  v2 = Crashdump_Endpoint_StopEndpoint(a1);
  v3 = v2;
  if ( v2 >= 0 )
    v3 = Crashdump_Endpoint_SetDequeuePointer(a1);
  else
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Endpoint_StopEndpoint failed with error 0x%X\n", v2);
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Endpoint_PrepareForHibernate: end 0x%X\n", v3);
  return v3;
}

```

## disassembly

```asm
0x140054554  mov     [rsp+arg_0], rbx
0x140054559  push    rdi
0x14005455a  sub     rsp, 20h
0x14005455e  mov     rdi, rcx
0x140054561  lea     r8, aXhcidumpCrashd_78; "XHCIDUMP: Crashdump_Endpoint_PrepareFor"...
0x140054568  mov     ecx, 93h; ComponentId
0x14005456d  mov     edx, 3; Level
0x140054572  call    cs:__imp_DbgPrintEx
0x140054579  nop     dword ptr [rax+rax+00h]
0x14005457e  mov     r8d, [rdi+60h]; Size
0x140054582  xor     edx, edx; Val
0x140054584  mov     rcx, [rdi+58h]; void *
0x140054588  call    memset
0x14005458d  mov     r8d, [rdi+78h]; Size
0x140054591  xor     edx, edx; Val
0x140054593  mov     rcx, [rdi+70h]; void *
0x140054597  call    memset
0x14005459c  mov     rcx, rdi
0x14005459f  mov     qword ptr [rdi+0A8h], 1
0x1400545aa  mov     dword ptr [rdi+0A0h], 0
0x1400545b4  call    Crashdump_Endpoint_StopEndpoint
0x1400545b9  mov     ebx, eax
0x1400545bb  test    eax, eax
0x1400545bd  jns     short loc_1400545E1
0x1400545bf  mov     r9d, eax
0x1400545c2  lea     r8, aXhcidumpCrashd_4; "XHCIDUMP: Crashdump_Endpoint_StopEndpoi"...
0x1400545c9  mov     edx, 1; Level
0x1400545ce  mov     ecx, 93h; ComponentId
0x1400545d3  call    cs:__imp_DbgPrintEx
0x1400545da  nop     dword ptr [rax+rax+00h]
0x1400545df  jmp     short loc_1400545EB
0x1400545e1  mov     rcx, rdi
0x1400545e4  call    Crashdump_Endpoint_SetDequeuePointer
0x1400545e9  mov     ebx, eax
0x1400545eb  mov     r9d, ebx
0x1400545ee  lea     r8, aXhcidumpCrashd_28; "XHCIDUMP: Crashdump_Endpoint_PrepareFor"...
0x1400545f5  mov     edx, 3; Level
0x1400545fa  mov     ecx, 93h; ComponentId
0x1400545ff  call    cs:__imp_DbgPrintEx
0x140054606  nop     dword ptr [rax+rax+00h]
0x14005460b  mov     eax, ebx
0x14005460d  mov     rbx, [rsp+28h+arg_0]
0x140054612  add     rsp, 20h
0x140054616  pop     rdi
0x140054617  retn
```
