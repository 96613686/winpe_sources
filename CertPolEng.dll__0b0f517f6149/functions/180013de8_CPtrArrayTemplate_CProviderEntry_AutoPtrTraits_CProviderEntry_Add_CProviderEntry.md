# CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::Add(CProviderEntry *)

- ea: `0x180013de8`
- end: `0x180013e21`
- name: `?Add@?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAAHPEAVCProviderEntry@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800043d0`

## callees

- `0x180013de8`
- `0x180013e28`

## pseudocode

```c
__int64 __fastcall CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::Add(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = CDynamicArray<CProviderEntry *>::AllocRangeAtPos(a1, *(unsigned int *)(a1 + 8));
  if ( result )
  {
    result = 1;
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a1 + 8) - 1)) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180013de8  mov     [rsp+arg_0], rbx
0x180013ded  push    rdi
0x180013dee  sub     rsp, 20h
0x180013df2  mov     rdi, rdx
0x180013df5  mov     rbx, rcx
0x180013df8  mov     edx, [rcx+8]
0x180013dfb  call    ?AllocRangeAtPos@?$CDynamicArray@PEAVCProviderEntry@@@@QEAAPEAPEAVCProviderEntry@@KK@Z; CDynamicArray<CProviderEntry *>::AllocRangeAtPos(ulong,ulong)
0x180013e00  test    rax, rax
0x180013e03  jz      short loc_180013E16
0x180013e05  mov     edx, [rbx+8]
0x180013e08  mov     eax, 1
0x180013e0d  mov     rcx, [rbx]
0x180013e10  sub     edx, eax
0x180013e12  mov     [rcx+rdx*8], rdi
0x180013e16  mov     rbx, [rsp+28h+arg_0]
0x180013e1b  add     rsp, 20h
0x180013e1f  pop     rdi
0x180013e20  retn
```
