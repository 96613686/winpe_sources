# VfsAllocateCopyBuffer

- ea: `0x140002228`
- end: `0x1400022ad`
- name: `VfsAllocateCopyBuffer`
- size: `133`
- prototype: `__int64 __fastcall(__int64 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400022b4`

## callees

- `0x140002228`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000225c`
- `ntoskrnl!ExAllocatePool2` at `0x14000227d`
- `ntoskrnl!ExAllocatePool2` at `0x14000225c`
- `ntoskrnl!ExAllocatePool2` at `0x14000227d`

## pseudocode

```c
__int64 __fastcall VfsAllocateCopyBuffer(__int64 *a1, int *a2)
{
  int v4; // ebx
  __int64 Pool2; // rax
  __int64 result; // rax

  *a1 = 0;
  *a2 = 0;
  v4 = 0x4000;
  Pool2 = ExAllocatePool2(64, 0x4000, 1883457110);
  if ( !Pool2 )
  {
    v4 = 4096;
    Pool2 = ExAllocatePool2(64, 4096, 1883457110);
    if ( !Pool2 )
      return 3221225626LL;
  }
  *a1 = Pool2;
  result = 0;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x140002228  mov     [rsp+arg_0], rbx
0x14000222d  mov     [rsp+arg_8], rsi
0x140002232  push    rdi
0x140002233  sub     rsp, 20h
0x140002237  mov     qword ptr [rcx], 0
0x14000223e  mov     rdi, rdx
0x140002241  mov     dword ptr [rdx], 0
0x140002247  mov     rsi, rcx
0x14000224a  mov     ebx, 4000h
0x14000224f  mov     r8d, 70434656h
0x140002255  mov     edx, ebx
0x140002257  mov     ecx, 40h ; '@'
0x14000225c  call    cs:__imp_ExAllocatePool2
0x140002263  nop     dword ptr [rax+rax+00h]
0x140002268  test    rax, rax
0x14000226b  jnz     short loc_140002295
0x14000226d  mov     edx, 1000h
0x140002272  lea     ecx, [rax+40h]
0x140002275  mov     r8d, 70434656h
0x14000227b  mov     ebx, edx
0x14000227d  call    cs:__imp_ExAllocatePool2
0x140002284  nop     dword ptr [rax+rax+00h]
0x140002289  test    rax, rax
0x14000228c  jnz     short loc_140002295
0x14000228e  mov     eax, 0C000009Ah
0x140002293  jmp     short loc_14000229C
0x140002295  mov     [rsi], rax
0x140002298  xor     eax, eax
0x14000229a  mov     [rdi], ebx
0x14000229c  mov     rbx, [rsp+28h+arg_0]
0x1400022a1  mov     rsi, [rsp+28h+arg_8]
0x1400022a6  add     rsp, 20h
0x1400022aa  pop     rdi
0x1400022ab  retn
```
