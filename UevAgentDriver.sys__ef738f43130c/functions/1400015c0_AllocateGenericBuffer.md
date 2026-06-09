# AllocateGenericBuffer

- ea: `0x1400015c0`
- end: `0x140001645`
- name: `AllocateGenericBuffer`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400016ac`
- `0x14000a84c`
- `0x14000a900`
- `0x14000b908`
- `0x14000c1bc`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x1400015c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400015f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400015f4`

## pseudocode

```c
__int64 __fastcall AllocateGenericBuffer(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 Pool2; // rax
  unsigned int v6; // ebx

  DbgTrace(3, "UevFilter.AllocateGenericBuffer: Entry\n");
  if ( a3 )
  {
    Pool2 = ExAllocatePool2(256, a2, 1719035253);
    *a3 = Pool2;
    v6 = Pool2 == 0 ? 0xC000009A : 0;
  }
  else
  {
    DbgTraceErr("UevFilter.AllocateGenericBuffer: Invalid parameter specified\n");
    v6 = -1073741811;
  }
  DbgTraceFrmt(3, "UevFilter.AllocateGenericBuffer: Exit, status = 0x%X\n", v6);
  return v6;
}

```

## disassembly

```asm
0x1400015c0  mov     [rsp+arg_0], rbx
0x1400015c5  push    rdi
0x1400015c6  sub     rsp, 20h
0x1400015ca  mov     rdi, rdx
0x1400015cd  mov     ecx, 3
0x1400015d2  lea     rdx, aUevfilterAlloc_5; "UevFilter.AllocateGenericBuffer: Entry"...
0x1400015d9  mov     rbx, r8
0x1400015dc  call    DbgTrace
0x1400015e1  test    rbx, rbx
0x1400015e4  jz      short loc_140001612
0x1400015e6  mov     r8d, 66766575h
0x1400015ec  mov     rdx, rdi
0x1400015ef  mov     ecx, 100h
0x1400015f4  call    cs:__imp_ExAllocatePool2
0x1400015fb  nop     dword ptr [rax+rax+00h]
0x140001600  mov     [rbx], rax
0x140001603  neg     rax
0x140001606  sbb     ebx, ebx
0x140001608  not     ebx
0x14000160a  and     ebx, 0C000009Ah
0x140001610  jmp     short loc_140001623
0x140001612  lea     rcx, Format; "UevFilter.AllocateGenericBuffer: Invali"...
0x140001619  call    DbgTraceErr
0x14000161e  mov     ebx, 0C000000Dh
0x140001623  mov     r8d, ebx
0x140001626  lea     rdx, aUevfilterAlloc_0; "UevFilter.AllocateGenericBuffer: Exit, "...
0x14000162d  mov     ecx, 3
0x140001632  call    DbgTraceFrmt
0x140001637  mov     eax, ebx
0x140001639  mov     rbx, [rsp+28h+arg_0]
0x14000163e  add     rsp, 20h
0x140001642  pop     rdi
0x140001643  retn
```
