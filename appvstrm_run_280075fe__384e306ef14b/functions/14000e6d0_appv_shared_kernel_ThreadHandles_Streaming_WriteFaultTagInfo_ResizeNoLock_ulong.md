# appv::shared::kernel::ThreadHandles<Streaming::WriteFaultTagInfo>::ResizeNoLock(ulong)

- ea: `0x14000e6d0`
- end: `0x14000e7f2`
- name: `?ResizeNoLock@?$ThreadHandles@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ebd0`

## callees

- `0x14000e6d0`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e75d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e75d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7d5`
- `ntoskrnl!ExAllocatePool2` at `0x14000e724`
- `ntoskrnl!ExAllocatePool2` at `0x14000e796`
- `ntoskrnl!ExAllocatePool2` at `0x14000e724`
- `ntoskrnl!ExAllocatePool2` at `0x14000e796`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadHandles<Streaming::WriteFaultTagInfo>::ResizeNoLock(
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
    Pool2 = (void *)ExAllocatePool2(64, v6, 1886873203);
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
    v14 = (void *)ExAllocatePool2(64, v11, 1886873203);
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
0x14000e6d0  push    rbx
0x14000e6d2  push    rbp
0x14000e6d3  push    rsi
0x14000e6d4  push    rdi
0x14000e6d5  push    r14
0x14000e6d7  sub     rsp, 20h
0x14000e6db  mov     edi, edx
0x14000e6dd  mov     rbx, rcx
0x14000e6e0  cmp     [rcx+20h], edx
0x14000e6e3  jnb     loc_14000E7E4
0x14000e6e9  cmp     byte ptr [rcx+28h], 0
0x14000e6ed  jnz     short loc_14000E6F9
0x14000e6ef  mov     eax, 0C0000001h
0x14000e6f4  jmp     loc_14000E7E6
0x14000e6f9  mov     ebp, [rcx+4]
0x14000e6fc  lea     eax, ds:0[rdx*8]
0x14000e703  cmp     eax, ebp
0x14000e705  ja      short loc_14000E70B
0x14000e707  mov     [rcx], eax
0x14000e709  jmp     short loc_14000E769
0x14000e70b  mov     r14d, [rcx]
0x14000e70e  mov     r8d, 70776673h
0x14000e714  mov     rsi, [rcx+8]
0x14000e718  mov     [rcx], eax
0x14000e71a  mov     [rcx+4], eax
0x14000e71d  mov     ecx, 40h ; '@'
0x14000e722  mov     edx, eax
0x14000e724  call    cs:__imp_ExAllocatePool2
0x14000e72b  nop     dword ptr [rax+rax+00h]
0x14000e730  mov     [rbx+8], rax
0x14000e734  test    rax, rax
0x14000e737  jnz     short loc_14000E745
0x14000e739  mov     [rbx], r14d
0x14000e73c  mov     [rbx+4], ebp
0x14000e73f  mov     [rbx+8], rsi
0x14000e743  jmp     short loc_14000E7B6
0x14000e745  test    rsi, rsi
0x14000e748  jz      short loc_14000E769
0x14000e74a  mov     r8, r14; Size
0x14000e74d  mov     rdx, rsi; Src
0x14000e750  mov     rcx, rax; void *
0x14000e753  call    memmove
0x14000e758  xor     edx, edx; Tag
0x14000e75a  mov     rcx, rsi; P
0x14000e75d  call    cs:__imp_ExFreePoolWithTag
0x14000e764  nop     dword ptr [rax+rax+00h]
0x14000e769  mov     ebp, [rbx+14h]
0x14000e76c  lea     eax, [rdi+rdi*2]
0x14000e76f  shl     eax, 4
0x14000e772  cmp     eax, ebp
0x14000e774  ja      short loc_14000E77B
0x14000e776  mov     [rbx+10h], eax
0x14000e779  jmp     short loc_14000E7E1
0x14000e77b  mov     r14d, [rbx+10h]
0x14000e77f  mov     ecx, 40h ; '@'
0x14000e784  mov     rsi, [rbx+18h]
0x14000e788  mov     r8d, 70776673h
0x14000e78e  mov     edx, eax
0x14000e790  mov     [rbx+10h], eax
0x14000e793  mov     [rbx+14h], eax
0x14000e796  call    cs:__imp_ExAllocatePool2
0x14000e79d  nop     dword ptr [rax+rax+00h]
0x14000e7a2  mov     [rbx+18h], rax
0x14000e7a6  test    rax, rax
0x14000e7a9  jnz     short loc_14000E7BD
0x14000e7ab  mov     [rbx+10h], r14d
0x14000e7af  mov     [rbx+14h], ebp
0x14000e7b2  mov     [rbx+18h], rsi
0x14000e7b6  mov     eax, 0C000009Ah
0x14000e7bb  jmp     short loc_14000E7E6
0x14000e7bd  test    rsi, rsi
0x14000e7c0  jz      short loc_14000E7E1
0x14000e7c2  mov     r8, r14; Size
0x14000e7c5  mov     rdx, rsi; Src
0x14000e7c8  mov     rcx, rax; void *
0x14000e7cb  call    memmove
0x14000e7d0  xor     edx, edx; Tag
0x14000e7d2  mov     rcx, rsi; P
0x14000e7d5  call    cs:__imp_ExFreePoolWithTag
0x14000e7dc  nop     dword ptr [rax+rax+00h]
0x14000e7e1  mov     [rbx+20h], edi
0x14000e7e4  xor     eax, eax
0x14000e7e6  add     rsp, 20h
0x14000e7ea  pop     r14
0x14000e7ec  pop     rdi
0x14000e7ed  pop     rsi
0x14000e7ee  pop     rbp
0x14000e7ef  pop     rbx
0x14000e7f0  retn
```
