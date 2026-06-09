# appv::shared::kernel::ThreadHandles<Streaming::FlushRequestTagInfo>::ResizeNoLock(ulong)

- ea: `0x140004378`
- end: `0x14000449a`
- name: `?ResizeNoLock@?$ThreadHandles@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400044a0`

## callees

- `0x140004378`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004405`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000447d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004405`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000447d`
- `ntoskrnl!ExAllocatePool2` at `0x1400043cc`
- `ntoskrnl!ExAllocatePool2` at `0x14000443e`
- `ntoskrnl!ExAllocatePool2` at `0x1400043cc`
- `ntoskrnl!ExAllocatePool2` at `0x14000443e`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadHandles<Streaming::FlushRequestTagInfo>::ResizeNoLock(
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
    Pool2 = (void *)ExAllocatePool2(64, v6, 1718773363);
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
    v14 = (void *)ExAllocatePool2(64, v11, 1718773363);
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
0x140004378  push    rbx
0x14000437a  push    rbp
0x14000437b  push    rsi
0x14000437c  push    rdi
0x14000437d  push    r14
0x14000437f  sub     rsp, 20h
0x140004383  mov     edi, edx
0x140004385  mov     rbx, rcx
0x140004388  cmp     [rcx+20h], edx
0x14000438b  jnb     loc_14000448C
0x140004391  cmp     byte ptr [rcx+28h], 0
0x140004395  jnz     short loc_1400043A1
0x140004397  mov     eax, 0C0000001h
0x14000439c  jmp     loc_14000448E
0x1400043a1  mov     ebp, [rcx+4]
0x1400043a4  lea     eax, ds:0[rdx*8]
0x1400043ab  cmp     eax, ebp
0x1400043ad  ja      short loc_1400043B3
0x1400043af  mov     [rcx], eax
0x1400043b1  jmp     short loc_140004411
0x1400043b3  mov     r14d, [rcx]
0x1400043b6  mov     r8d, 66726673h
0x1400043bc  mov     rsi, [rcx+8]
0x1400043c0  mov     [rcx], eax
0x1400043c2  mov     [rcx+4], eax
0x1400043c5  mov     ecx, 40h ; '@'
0x1400043ca  mov     edx, eax
0x1400043cc  call    cs:__imp_ExAllocatePool2
0x1400043d3  nop     dword ptr [rax+rax+00h]
0x1400043d8  mov     [rbx+8], rax
0x1400043dc  test    rax, rax
0x1400043df  jnz     short loc_1400043ED
0x1400043e1  mov     [rbx], r14d
0x1400043e4  mov     [rbx+4], ebp
0x1400043e7  mov     [rbx+8], rsi
0x1400043eb  jmp     short loc_14000445E
0x1400043ed  test    rsi, rsi
0x1400043f0  jz      short loc_140004411
0x1400043f2  mov     r8, r14; Size
0x1400043f5  mov     rdx, rsi; Src
0x1400043f8  mov     rcx, rax; void *
0x1400043fb  call    memmove
0x140004400  xor     edx, edx; Tag
0x140004402  mov     rcx, rsi; P
0x140004405  call    cs:__imp_ExFreePoolWithTag
0x14000440c  nop     dword ptr [rax+rax+00h]
0x140004411  mov     ebp, [rbx+14h]
0x140004414  lea     eax, [rdi+rdi*2]
0x140004417  shl     eax, 4
0x14000441a  cmp     eax, ebp
0x14000441c  ja      short loc_140004423
0x14000441e  mov     [rbx+10h], eax
0x140004421  jmp     short loc_140004489
0x140004423  mov     r14d, [rbx+10h]
0x140004427  mov     ecx, 40h ; '@'
0x14000442c  mov     rsi, [rbx+18h]
0x140004430  mov     r8d, 66726673h
0x140004436  mov     edx, eax
0x140004438  mov     [rbx+10h], eax
0x14000443b  mov     [rbx+14h], eax
0x14000443e  call    cs:__imp_ExAllocatePool2
0x140004445  nop     dword ptr [rax+rax+00h]
0x14000444a  mov     [rbx+18h], rax
0x14000444e  test    rax, rax
0x140004451  jnz     short loc_140004465
0x140004453  mov     [rbx+10h], r14d
0x140004457  mov     [rbx+14h], ebp
0x14000445a  mov     [rbx+18h], rsi
0x14000445e  mov     eax, 0C000009Ah
0x140004463  jmp     short loc_14000448E
0x140004465  test    rsi, rsi
0x140004468  jz      short loc_140004489
0x14000446a  mov     r8, r14; Size
0x14000446d  mov     rdx, rsi; Src
0x140004470  mov     rcx, rax; void *
0x140004473  call    memmove
0x140004478  xor     edx, edx; Tag
0x14000447a  mov     rcx, rsi; P
0x14000447d  call    cs:__imp_ExFreePoolWithTag
0x140004484  nop     dword ptr [rax+rax+00h]
0x140004489  mov     [rbx+20h], edi
0x14000448c  xor     eax, eax
0x14000448e  add     rsp, 20h
0x140004492  pop     r14
0x140004494  pop     rdi
0x140004495  pop     rsi
0x140004496  pop     rbp
0x140004497  pop     rbx
0x140004498  retn
```
