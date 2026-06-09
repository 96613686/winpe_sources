# appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::ResizeNoLock(ulong)

- ea: `0x14000e5a8`
- end: `0x14000e6ca`
- name: `?ResizeNoLock@?$ThreadHandles@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e7f8`

## callees

- `0x14000e5a8`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e635`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000e5fc`
- `ntoskrnl!ExAllocatePool2` at `0x14000e66e`
- `ntoskrnl!ExAllocatePool2` at `0x14000e5fc`
- `ntoskrnl!ExAllocatePool2` at `0x14000e66e`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::ResizeNoLock(
        unsigned int *a1,
        unsigned int a2)
{
  unsigned int v5; // ebp
  unsigned int v6; // eax
  size_t v7; // r14
  void *v8; // rsi
  void *Pool2; // rax
  unsigned int v10; // ebp
  unsigned int v11; // eax
  size_t v12; // r14
  void *v13; // rsi
  void *v14; // rax

  if ( a1[8] >= a2 )
    return 0;
  if ( !*((_BYTE *)a1 + 40) )
    return 3221225473LL;
  v5 = a1[1];
  v6 = 8 * a2;
  if ( 8 * a2 > v5 )
  {
    v7 = *a1;
    v8 = (void *)*((_QWORD *)a1 + 1);
    *a1 = v6;
    a1[1] = v6;
    Pool2 = (void *)ExAllocatePool2(64, v6, 1886611059);
    *((_QWORD *)a1 + 1) = Pool2;
    if ( !Pool2 )
    {
      *a1 = v7;
      a1[1] = v5;
      *((_QWORD *)a1 + 1) = v8;
      return 3221225626LL;
    }
    if ( v8 )
    {
      memmove(Pool2, v8, v7);
      ExFreePoolWithTag(v8, 0);
    }
  }
  else
  {
    *a1 = v6;
  }
  v10 = a1[5];
  v11 = 48 * a2;
  if ( 48 * a2 > v10 )
  {
    v12 = a1[4];
    v13 = (void *)*((_QWORD *)a1 + 3);
    a1[4] = v11;
    a1[5] = v11;
    v14 = (void *)ExAllocatePool2(64, v11, 1886611059);
    *((_QWORD *)a1 + 3) = v14;
    if ( v14 )
    {
      if ( v13 )
      {
        memmove(v14, v13, v12);
        ExFreePoolWithTag(v13, 0);
      }
      goto LABEL_17;
    }
    a1[4] = v12;
    a1[5] = v10;
    *((_QWORD *)a1 + 3) = v13;
    return 3221225626LL;
  }
  a1[4] = v11;
LABEL_17:
  a1[8] = a2;
  return 0;
}

```

## disassembly

```asm
0x14000e5a8  push    rbx
0x14000e5aa  push    rbp
0x14000e5ab  push    rsi
0x14000e5ac  push    rdi
0x14000e5ad  push    r14
0x14000e5af  sub     rsp, 20h
0x14000e5b3  mov     edi, edx
0x14000e5b5  mov     rbx, rcx
0x14000e5b8  cmp     [rcx+20h], edx
0x14000e5bb  jnb     loc_14000E6BC
0x14000e5c1  cmp     byte ptr [rcx+28h], 0
0x14000e5c5  jnz     short loc_14000E5D1
0x14000e5c7  mov     eax, 0C0000001h
0x14000e5cc  jmp     loc_14000E6BE
0x14000e5d1  mov     ebp, [rcx+4]
0x14000e5d4  lea     eax, ds:0[rdx*8]
0x14000e5db  cmp     eax, ebp
0x14000e5dd  ja      short loc_14000E5E3
0x14000e5df  mov     [rcx], eax
0x14000e5e1  jmp     short loc_14000E641
0x14000e5e3  mov     r14d, [rcx]
0x14000e5e6  mov     r8d, 70736673h
0x14000e5ec  mov     rsi, [rcx+8]
0x14000e5f0  mov     [rcx], eax
0x14000e5f2  mov     [rcx+4], eax
0x14000e5f5  mov     ecx, 40h ; '@'
0x14000e5fa  mov     edx, eax
0x14000e5fc  call    cs:__imp_ExAllocatePool2
0x14000e603  nop     dword ptr [rax+rax+00h]
0x14000e608  mov     [rbx+8], rax
0x14000e60c  test    rax, rax
0x14000e60f  jnz     short loc_14000E61D
0x14000e611  mov     [rbx], r14d
0x14000e614  mov     [rbx+4], ebp
0x14000e617  mov     [rbx+8], rsi
0x14000e61b  jmp     short loc_14000E68E
0x14000e61d  test    rsi, rsi
0x14000e620  jz      short loc_14000E641
0x14000e622  mov     r8, r14; Size
0x14000e625  mov     rdx, rsi; Src
0x14000e628  mov     rcx, rax; void *
0x14000e62b  call    memmove
0x14000e630  xor     edx, edx; Tag
0x14000e632  mov     rcx, rsi; P
0x14000e635  call    cs:__imp_ExFreePoolWithTag
0x14000e63c  nop     dword ptr [rax+rax+00h]
0x14000e641  mov     ebp, [rbx+14h]
0x14000e644  lea     eax, [rdi+rdi*2]
0x14000e647  shl     eax, 4
0x14000e64a  cmp     eax, ebp
0x14000e64c  ja      short loc_14000E653
0x14000e64e  mov     [rbx+10h], eax
0x14000e651  jmp     short loc_14000E6B9
0x14000e653  mov     r14d, [rbx+10h]
0x14000e657  mov     ecx, 40h ; '@'
0x14000e65c  mov     rsi, [rbx+18h]
0x14000e660  mov     r8d, 70736673h
0x14000e666  mov     edx, eax
0x14000e668  mov     [rbx+10h], eax
0x14000e66b  mov     [rbx+14h], eax
0x14000e66e  call    cs:__imp_ExAllocatePool2
0x14000e675  nop     dword ptr [rax+rax+00h]
0x14000e67a  mov     [rbx+18h], rax
0x14000e67e  test    rax, rax
0x14000e681  jnz     short loc_14000E695
0x14000e683  mov     [rbx+10h], r14d
0x14000e687  mov     [rbx+14h], ebp
0x14000e68a  mov     [rbx+18h], rsi
0x14000e68e  mov     eax, 0C000009Ah
0x14000e693  jmp     short loc_14000E6BE
0x14000e695  test    rsi, rsi
0x14000e698  jz      short loc_14000E6B9
0x14000e69a  mov     r8, r14; Size
0x14000e69d  mov     rdx, rsi; Src
0x14000e6a0  mov     rcx, rax; void *
0x14000e6a3  call    memmove
0x14000e6a8  xor     edx, edx; Tag
0x14000e6aa  mov     rcx, rsi; P
0x14000e6ad  call    cs:__imp_ExFreePoolWithTag
0x14000e6b4  nop     dword ptr [rax+rax+00h]
0x14000e6b9  mov     [rbx+20h], edi
0x14000e6bc  xor     eax, eax
0x14000e6be  add     rsp, 20h
0x14000e6c2  pop     r14
0x14000e6c4  pop     rdi
0x14000e6c5  pop     rsi
0x14000e6c6  pop     rbp
0x14000e6c7  pop     rbx
0x14000e6c8  retn
```
