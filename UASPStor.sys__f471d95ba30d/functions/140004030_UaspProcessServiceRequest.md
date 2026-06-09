# UaspProcessServiceRequest

- ea: `0x140004030`
- end: `0x140004060`
- name: `UaspProcessServiceRequest`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `storport!StorPortExtendedFunction` at `0x14000404e`
- `storport!StorPortExtendedFunction` at `0x14000404e`

## pseudocode

```c
__int64 __fastcall UaspProcessServiceRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  *(_QWORD *)(a2 + 56) = 0;
  *(_DWORD *)(a2 + 48) = 0;
  return StorPortExtendedFunction(7, a1, a2, a4);
}

```

## disassembly

```asm
0x140004030  sub     rsp, 28h
0x140004034  mov     qword ptr [rdx+38h], 0
0x14000403c  mov     r8, rdx
0x14000403f  mov     dword ptr [rdx+30h], 0
0x140004046  mov     rdx, rcx
0x140004049  mov     ecx, 7
0x14000404e  call    cs:__imp_StorPortExtendedFunction
0x140004055  nop     dword ptr [rax+rax+00h]
0x14000405a  add     rsp, 28h
0x14000405e  retn
```
