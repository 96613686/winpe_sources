# appv::shared::kernel::ThreadHandles<Streaming::PackageWriterTagInfo>::ResizeNoLock(ulong)

- ea: `0x1400069b8`
- end: `0x140006ada`
- name: `?ResizeNoLock@?$ThreadHandles@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJK@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006c08`

## callees

- `0x1400069b8`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006a45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006abd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006abd`
- `ntoskrnl!ExAllocatePool2` at `0x140006a0c`
- `ntoskrnl!ExAllocatePool2` at `0x140006a7e`
- `ntoskrnl!ExAllocatePool2` at `0x140006a0c`
- `ntoskrnl!ExAllocatePool2` at `0x140006a7e`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadHandles<Streaming::PackageWriterTagInfo>::ResizeNoLock(
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
    Pool2 = (void *)ExAllocatePool2(64, v6, 2003854963);
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
    v14 = (void *)ExAllocatePool2(64, v11, 2003854963);
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
0x1400069b8  push    rbx
0x1400069ba  push    rbp
0x1400069bb  push    rsi
0x1400069bc  push    rdi
0x1400069bd  push    r14
0x1400069bf  sub     rsp, 20h
0x1400069c3  mov     edi, edx
0x1400069c5  mov     rbx, rcx
0x1400069c8  cmp     [rcx+20h], edx
0x1400069cb  jnb     loc_140006ACC
0x1400069d1  cmp     byte ptr [rcx+28h], 0
0x1400069d5  jnz     short loc_1400069E1
0x1400069d7  mov     eax, 0C0000001h
0x1400069dc  jmp     loc_140006ACE
0x1400069e1  mov     ebp, [rcx+4]
0x1400069e4  lea     eax, ds:0[rdx*8]
0x1400069eb  cmp     eax, ebp
0x1400069ed  ja      short loc_1400069F3
0x1400069ef  mov     [rcx], eax
0x1400069f1  jmp     short loc_140006A51
0x1400069f3  mov     r14d, [rcx]
0x1400069f6  mov     r8d, 77706673h
0x1400069fc  mov     rsi, [rcx+8]
0x140006a00  mov     [rcx], eax
0x140006a02  mov     [rcx+4], eax
0x140006a05  mov     ecx, 40h ; '@'
0x140006a0a  mov     edx, eax
0x140006a0c  call    cs:__imp_ExAllocatePool2
0x140006a13  nop     dword ptr [rax+rax+00h]
0x140006a18  mov     [rbx+8], rax
0x140006a1c  test    rax, rax
0x140006a1f  jnz     short loc_140006A2D
0x140006a21  mov     [rbx], r14d
0x140006a24  mov     [rbx+4], ebp
0x140006a27  mov     [rbx+8], rsi
0x140006a2b  jmp     short loc_140006A9E
0x140006a2d  test    rsi, rsi
0x140006a30  jz      short loc_140006A51
0x140006a32  mov     r8, r14; Size
0x140006a35  mov     rdx, rsi; Src
0x140006a38  mov     rcx, rax; void *
0x140006a3b  call    memmove
0x140006a40  xor     edx, edx; Tag
0x140006a42  mov     rcx, rsi; P
0x140006a45  call    cs:__imp_ExFreePoolWithTag
0x140006a4c  nop     dword ptr [rax+rax+00h]
0x140006a51  mov     ebp, [rbx+14h]
0x140006a54  lea     eax, [rdi+rdi*2]
0x140006a57  shl     eax, 4
0x140006a5a  cmp     eax, ebp
0x140006a5c  ja      short loc_140006A63
0x140006a5e  mov     [rbx+10h], eax
0x140006a61  jmp     short loc_140006AC9
0x140006a63  mov     r14d, [rbx+10h]
0x140006a67  mov     ecx, 40h ; '@'
0x140006a6c  mov     rsi, [rbx+18h]
0x140006a70  mov     r8d, 77706673h
0x140006a76  mov     edx, eax
0x140006a78  mov     [rbx+10h], eax
0x140006a7b  mov     [rbx+14h], eax
0x140006a7e  call    cs:__imp_ExAllocatePool2
0x140006a85  nop     dword ptr [rax+rax+00h]
0x140006a8a  mov     [rbx+18h], rax
0x140006a8e  test    rax, rax
0x140006a91  jnz     short loc_140006AA5
0x140006a93  mov     [rbx+10h], r14d
0x140006a97  mov     [rbx+14h], ebp
0x140006a9a  mov     [rbx+18h], rsi
0x140006a9e  mov     eax, 0C000009Ah
0x140006aa3  jmp     short loc_140006ACE
0x140006aa5  test    rsi, rsi
0x140006aa8  jz      short loc_140006AC9
0x140006aaa  mov     r8, r14; Size
0x140006aad  mov     rdx, rsi; Src
0x140006ab0  mov     rcx, rax; void *
0x140006ab3  call    memmove
0x140006ab8  xor     edx, edx; Tag
0x140006aba  mov     rcx, rsi; P
0x140006abd  call    cs:__imp_ExFreePoolWithTag
0x140006ac4  nop     dword ptr [rax+rax+00h]
0x140006ac9  mov     [rbx+20h], edi
0x140006acc  xor     eax, eax
0x140006ace  add     rsp, 20h
0x140006ad2  pop     r14
0x140006ad4  pop     rdi
0x140006ad5  pop     rsi
0x140006ad6  pop     rbp
0x140006ad7  pop     rbx
0x140006ad8  retn
```
