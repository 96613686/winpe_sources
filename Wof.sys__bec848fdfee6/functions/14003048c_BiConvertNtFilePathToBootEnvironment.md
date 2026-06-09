# BiConvertNtFilePathToBootEnvironment

- ea: `0x14003048c`
- end: `0x140030572`
- name: `BiConvertNtFilePathToBootEnvironment`
- size: `230`
- prototype: `__int64 __fastcall(__int64, unsigned int, _WORD *, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002fce8`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x14002fce8`
- `0x14003048c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400304eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400304eb`

## pseudocode

```c
__int64 __fastcall BiConvertNtFilePathToBootEnvironment(
        __int64 a1,
        unsigned int a2,
        _WORD *a3,
        unsigned int a4,
        _QWORD *a5)
{
  int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // esi
  unsigned int v9; // ebp
  _DWORD *Pool2; // rax
  _DWORD *v11; // rbx
  void *Src; // [rsp+20h] [rbp-38h] BYREF

  Src = 0;
  v6 = BiConvertNtDeviceToBootEnvironment(a1, a2, a4, &Src);
  if ( v6 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
    v9 = v8 + *((_DWORD *)Src + 2) + 12;
    Pool2 = (_DWORD *)ExAllocatePool2(258, v9, 1262764866);
    v11 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = 1;
      Pool2[2] = 5;
      Pool2[1] = v9;
      memmove(Pool2 + 3, Src, *((unsigned int *)Src + 2));
      memmove((char *)v11 + *((unsigned int *)Src + 2) + 12, a3, v8);
      *a5 = v11;
      v6 = 0;
    }
    else
    {
      v6 = -1073741670;
    }
  }
  if ( Src )
    ExFreePoolWithTag_0(Src, 0x4B444342u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003048c  push    rbx
0x14003048e  push    rbp
0x14003048f  push    rsi
0x140030490  push    rdi
0x140030491  push    r14
0x140030493  sub     rsp, 30h
0x140030497  mov     eax, r9d
0x14003049a  mov     rdi, r8
0x14003049d  xor     r14d, r14d
0x1400304a0  lea     r9, [rsp+58h+Src]
0x1400304a5  mov     r8d, eax
0x1400304a8  mov     [rsp+58h+Src], r14
0x1400304ad  call    BiConvertNtDeviceToBootEnvironment
0x1400304b2  mov     ebx, eax
0x1400304b4  test    eax, eax
0x1400304b6  js      loc_140030550
0x1400304bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400304c0  inc     rax
0x1400304c3  cmp     [rdi+rax*2], r14w
0x1400304c8  jnz     short loc_1400304C0
0x1400304ca  lea     esi, ds:2[rax*2]
0x1400304d1  mov     ecx, 102h
0x1400304d6  mov     rax, [rsp+58h+Src]
0x1400304db  mov     r8d, 4B444342h
0x1400304e1  mov     ebp, [rax+8]
0x1400304e4  add     ebp, 0Ch
0x1400304e7  add     ebp, esi
0x1400304e9  mov     edx, ebp
0x1400304eb  call    cs:__imp_ExAllocatePool2
0x1400304f2  nop     dword ptr [rax+rax+00h]
0x1400304f7  mov     rbx, rax
0x1400304fa  test    rax, rax
0x1400304fd  jnz     short loc_140030506
0x1400304ff  mov     ebx, 0C000009Ah
0x140030504  jmp     short loc_140030550
0x140030506  mov     dword ptr [rax], 1
0x14003050c  lea     rcx, [rax+0Ch]; void *
0x140030510  mov     dword ptr [rax+8], 5
0x140030517  mov     [rax+4], ebp
0x14003051a  mov     rdx, [rsp+58h+Src]; Src
0x14003051f  mov     r8d, [rdx+8]; Size
0x140030523  call    memmove
0x140030528  mov     rax, [rsp+58h+Src]
0x14003052d  mov     rdx, rdi; Src
0x140030530  mov     r8d, esi; Size
0x140030533  mov     ecx, [rax+8]
0x140030536  add     rcx, 0Ch
0x14003053a  add     rcx, rbx; void *
0x14003053d  call    memmove
0x140030542  mov     rax, [rsp+58h+arg_20]
0x14003054a  mov     [rax], rbx
0x14003054d  mov     ebx, r14d
0x140030550  mov     rcx, [rsp+58h+Src]; P
0x140030555  test    rcx, rcx
0x140030558  jz      short loc_140030564
0x14003055a  mov     edx, 4B444342h; Tag
0x14003055f  call    ExFreePoolWithTag_0
0x140030564  mov     eax, ebx
0x140030566  add     rsp, 30h
0x14003056a  pop     r14
0x14003056c  pop     rdi
0x14003056d  pop     rsi
0x14003056e  pop     rbp
0x14003056f  pop     rbx
0x140030570  retn
```
