# VfsCreateContextNormalize

- ea: `0x14000437c`
- end: `0x14000447c`
- name: `VfsCreateContextNormalize`
- size: `256`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400049b4`
- `0x14000502c`

## callees

- `0x14000437c`
- `0x140008aa8`
- `0x140008d50`
- `0x140010cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004436`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004460`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014997`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004436`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004460`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014997`

## pseudocode

```c
__int64 __fastcall VfsCreateContextNormalize(__int64 a1)
{
  __int64 v2; // rsi
  int RelativeNameByMapping; // ebx
  void *v4; // rcx
  UNICODE_STRING v6; // [rsp+38h] [rbp-70h] BYREF
  __int128 v7; // [rsp+48h] [rbp-60h] BYREF
  __m128i v8; // [rsp+58h] [rbp-50h] BYREF
  struct _UNICODE_STRING v9; // [rsp+68h] [rbp-40h] BYREF
  char v10; // [rsp+B0h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v8 = 0;
  v7 = 0;
  v6 = 0;
  v9 = 0;
  RelativeNameByMapping = VfsGetRelativeNameByMapping(v2, a1 + 32, 0, &v7);
  if ( RelativeNameByMapping >= 0 )
  {
    v8 = *(__m128i *)(a1 + 32);
    v8.m128i_i16[0] = _mm_cvtsi128_si32(v8) - v7;
    RelativeNameByMapping = VfsNormalizeFileName(*(_QWORD *)(a1 + 24), &v8, &v7, &v6, &v10);
    if ( RelativeNameByMapping >= 0 )
    {
      RelativeNameByMapping = VfsGenerateMappedName(v2, &v6, &v9);
      if ( RelativeNameByMapping >= 0 )
      {
        v4 = *(void **)(a1 + 64);
        if ( v4 )
        {
          ExFreePoolWithTag(v4, 0);
          *(_QWORD *)(a1 + 64) = 0;
        }
        *(struct _UNICODE_STRING *)(a1 + 56) = v9;
      }
    }
  }
  if ( v6.Buffer )
    ExFreePoolWithTag(v6.Buffer, 0);
  return (unsigned int)RelativeNameByMapping;
}

```

## disassembly

```asm
0x14000437c  mov     rax, rsp
0x14000437f  push    rbx
0x140004380  push    rsi
0x140004381  push    rdi
0x140004382  push    r14
0x140004384  sub     rsp, 88h
0x14000438b  mov     rdi, rcx
0x14000438e  mov     rsi, [rcx+10h]
0x140004392  xorps   xmm0, xmm0
0x140004395  movups  xmmword ptr [rax-50h], xmm0
0x140004399  xorps   xmm1, xmm1
0x14000439c  movups  xmmword ptr [rax-60h], xmm1
0x1400043a0  movups  xmmword ptr [rax-70h], xmm0
0x1400043a4  movups  xmmword ptr [rax-40h], xmm1
0x1400043a8  lea     r9, [rax-60h]
0x1400043ac  xor     r8d, r8d
0x1400043af  lea     rdx, [rcx+20h]
0x1400043b3  mov     rcx, rsi
0x1400043b6  call    VfsGetRelativeNameByMapping
0x1400043bb  mov     ebx, eax
0x1400043bd  mov     [rsp+0A8h+var_78], eax
0x1400043c1  test    eax, eax
0x1400043c3  js      loc_140004454
0x1400043c9  movups  xmm0, xmmword ptr [rdi+20h]
0x1400043cd  movups  [rsp+0A8h+var_50], xmm0
0x1400043d2  movd    eax, xmm0
0x1400043d6  sub     ax, word ptr [rsp+0A8h+var_60]
0x1400043db  mov     word ptr [rsp+0A8h+var_50], ax
0x1400043e0  lea     rax, [rsp+0A8h+arg_0]
0x1400043e8  mov     [rsp+0A8h+var_88], rax
0x1400043ed  lea     r9, [rsp+0A8h+var_70]
0x1400043f2  lea     r8, [rsp+0A8h+var_60]
0x1400043f7  lea     rdx, [rsp+0A8h+var_50]
0x1400043fc  mov     rcx, [rdi+18h]
0x140004400  call    VfsNormalizeFileName
0x140004405  mov     ebx, eax
0x140004407  mov     [rsp+0A8h+var_78], eax
0x14000440b  test    eax, eax
0x14000440d  js      short loc_140004454
0x14000440f  lea     r8, [rsp+0A8h+var_40]
0x140004414  lea     rdx, [rsp+0A8h+var_70]
0x140004419  mov     rcx, rsi
0x14000441c  call    VfsGenerateMappedName
0x140004421  mov     ebx, eax
0x140004423  mov     [rsp+0A8h+var_78], eax
0x140004427  test    eax, eax
0x140004429  js      short loc_140004454
0x14000442b  mov     rcx, [rdi+40h]; P
0x14000442f  test    rcx, rcx
0x140004432  jz      short loc_14000444A
0x140004434  xor     edx, edx; Tag
0x140004436  call    cs:__imp_ExFreePoolWithTag
0x14000443d  nop     dword ptr [rax+rax+00h]
0x140004442  mov     qword ptr [rdi+40h], 0
0x14000444a  movups  xmm0, [rsp+0A8h+var_40]
0x14000444f  movdqu  xmmword ptr [rdi+38h], xmm0
0x140004454  mov     rcx, [rsp+0A8h+P]; P
0x140004459  test    rcx, rcx
0x14000445c  jz      short loc_14000446C
0x14000445e  xor     edx, edx; Tag
0x140004460  call    cs:__imp_ExFreePoolWithTag
0x140004467  nop     dword ptr [rax+rax+00h]
0x14000446c  mov     eax, ebx
0x14000446e  add     rsp, 88h
0x140004475  pop     r14
0x140004477  pop     rdi
0x140004478  pop     rsi
0x140004479  pop     rbx
0x14000447a  retn
0x140014983  push    rbp
0x140014985  sub     rsp, 30h
0x140014989  mov     rbp, rdx
0x14001498c  mov     rcx, [rbp+40h]; P
0x140014990  test    rcx, rcx
0x140014993  jz      short loc_1400149A4
0x140014995  xor     edx, edx; Tag
0x140014997  call    cs:__imp_ExFreePoolWithTag
0x14001499e  nop     dword ptr [rax+rax+00h]
0x1400149a3  nop
0x1400149a4  add     rsp, 30h
0x1400149a8  pop     rbp
0x1400149a9  retn
```
