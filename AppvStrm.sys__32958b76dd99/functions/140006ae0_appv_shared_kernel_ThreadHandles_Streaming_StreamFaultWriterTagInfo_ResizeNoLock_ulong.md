# appv::shared::kernel::ThreadHandles<Streaming::StreamFaultWriterTagInfo>::ResizeNoLock(ulong)

- ea: `0x140006ae0`
- end: `0x140006c02`
- name: `?ResizeNoLock@?$ThreadHandles@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006fe0`

## callees

- `0x140006ae0`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006b6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006be5`
- `ntoskrnl!ExAllocatePool2` at `0x140006b34`
- `ntoskrnl!ExAllocatePool2` at `0x140006ba6`
- `ntoskrnl!ExAllocatePool2` at `0x140006b34`
- `ntoskrnl!ExAllocatePool2` at `0x140006ba6`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadHandles<Streaming::StreamFaultWriterTagInfo>::ResizeNoLock(
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
    Pool2 = (void *)ExAllocatePool2(64, v6, 2003199603);
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
    v14 = (void *)ExAllocatePool2(64, v11, 2003199603);
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
0x140006ae0  push    rbx
0x140006ae2  push    rbp
0x140006ae3  push    rsi
0x140006ae4  push    rdi
0x140006ae5  push    r14
0x140006ae7  sub     rsp, 20h
0x140006aeb  mov     edi, edx
0x140006aed  mov     rbx, rcx
0x140006af0  cmp     [rcx+20h], edx
0x140006af3  jnb     loc_140006BF4
0x140006af9  cmp     byte ptr [rcx+28h], 0
0x140006afd  jnz     short loc_140006B09
0x140006aff  mov     eax, 0C0000001h
0x140006b04  jmp     loc_140006BF6
0x140006b09  mov     ebp, [rcx+4]
0x140006b0c  lea     eax, ds:0[rdx*8]
0x140006b13  cmp     eax, ebp
0x140006b15  ja      short loc_140006B1B
0x140006b17  mov     [rcx], eax
0x140006b19  jmp     short loc_140006B79
0x140006b1b  mov     r14d, [rcx]
0x140006b1e  mov     r8d, 77666673h
0x140006b24  mov     rsi, [rcx+8]
0x140006b28  mov     [rcx], eax
0x140006b2a  mov     [rcx+4], eax
0x140006b2d  mov     ecx, 40h ; '@'
0x140006b32  mov     edx, eax
0x140006b34  call    cs:__imp_ExAllocatePool2
0x140006b3b  nop     dword ptr [rax+rax+00h]
0x140006b40  mov     [rbx+8], rax
0x140006b44  test    rax, rax
0x140006b47  jnz     short loc_140006B55
0x140006b49  mov     [rbx], r14d
0x140006b4c  mov     [rbx+4], ebp
0x140006b4f  mov     [rbx+8], rsi
0x140006b53  jmp     short loc_140006BC6
0x140006b55  test    rsi, rsi
0x140006b58  jz      short loc_140006B79
0x140006b5a  mov     r8, r14; Size
0x140006b5d  mov     rdx, rsi; Src
0x140006b60  mov     rcx, rax; void *
0x140006b63  call    memmove
0x140006b68  xor     edx, edx; Tag
0x140006b6a  mov     rcx, rsi; P
0x140006b6d  call    cs:__imp_ExFreePoolWithTag
0x140006b74  nop     dword ptr [rax+rax+00h]
0x140006b79  mov     ebp, [rbx+14h]
0x140006b7c  lea     eax, [rdi+rdi*2]
0x140006b7f  shl     eax, 4
0x140006b82  cmp     eax, ebp
0x140006b84  ja      short loc_140006B8B
0x140006b86  mov     [rbx+10h], eax
0x140006b89  jmp     short loc_140006BF1
0x140006b8b  mov     r14d, [rbx+10h]
0x140006b8f  mov     ecx, 40h ; '@'
0x140006b94  mov     rsi, [rbx+18h]
0x140006b98  mov     r8d, 77666673h
0x140006b9e  mov     edx, eax
0x140006ba0  mov     [rbx+10h], eax
0x140006ba3  mov     [rbx+14h], eax
0x140006ba6  call    cs:__imp_ExAllocatePool2
0x140006bad  nop     dword ptr [rax+rax+00h]
0x140006bb2  mov     [rbx+18h], rax
0x140006bb6  test    rax, rax
0x140006bb9  jnz     short loc_140006BCD
0x140006bbb  mov     [rbx+10h], r14d
0x140006bbf  mov     [rbx+14h], ebp
0x140006bc2  mov     [rbx+18h], rsi
0x140006bc6  mov     eax, 0C000009Ah
0x140006bcb  jmp     short loc_140006BF6
0x140006bcd  test    rsi, rsi
0x140006bd0  jz      short loc_140006BF1
0x140006bd2  mov     r8, r14; Size
0x140006bd5  mov     rdx, rsi; Src
0x140006bd8  mov     rcx, rax; void *
0x140006bdb  call    memmove
0x140006be0  xor     edx, edx; Tag
0x140006be2  mov     rcx, rsi; P
0x140006be5  call    cs:__imp_ExFreePoolWithTag
0x140006bec  nop     dword ptr [rax+rax+00h]
0x140006bf1  mov     [rbx+20h], edi
0x140006bf4  xor     eax, eax
0x140006bf6  add     rsp, 20h
0x140006bfa  pop     r14
0x140006bfc  pop     rdi
0x140006bfd  pop     rsi
0x140006bfe  pop     rbp
0x140006bff  pop     rbx
0x140006c00  retn
```
