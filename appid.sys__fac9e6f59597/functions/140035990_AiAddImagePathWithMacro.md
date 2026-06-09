# AiAddImagePathWithMacro

- ea: `0x140035990`
- end: `0x140035b5a`
- name: `AiAddImagePathWithMacro`
- size: `458`
- prototype: `__int64 __fastcall(__int64, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140037ac0`

## callees

- `0x140006c40`
- `0x140032a50`
- `0x140035990`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035aee`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140035ac9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140035ac9`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400359c7`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400359c7`

## pseudocode

```c
__int64 __fastcall AiAddImagePathWithMacro(__int64 a1, UNICODE_STRING *a2)
{
  unsigned int v5; // eax
  unsigned __int64 v6; // rcx
  int v7; // ebp
  void *v8; // rax
  void *v9; // rbx
  _QWORD *v10; // rsi
  void *v11; // rcx
  unsigned int v12; // ebp
  PVOID *p_Buffer; // r14
  unsigned int v14; // ecx
  __int64 v15; // r9
  __int64 v16; // rdx
  _WORD *v17; // r8

  if ( !a2->Length )
    return 3221225485LL;
  RtlUpcaseUnicodeString(a2, a2, 0);
  v5 = *(_DWORD *)(a1 + 120);
  if ( *(_DWORD *)(a1 + 116) == v5 )
  {
    v6 = 2LL * v5;
    if ( v6 > 0xFFFFFFFF )
      return 3221225621LL;
    v7 = 2 * v5;
    v8 = (void *)AiAlloc(16LL * (unsigned int)v6);
    v9 = v8;
    if ( !v8 )
      return 3221225495LL;
    v10 = (_QWORD *)(a1 + 128);
    memmove(v8, *(const void **)(a1 + 128), 16LL * *(unsigned int *)(a1 + 116));
    v11 = *(void **)(a1 + 128);
    if ( v11 != (void *)(a1 + 136) && v11 )
      ExFreePoolWithTag(v11, 0);
    *(_DWORD *)(a1 + 120) = v7;
    *v10 = v9;
  }
  else
  {
    v10 = (_QWORD *)(a1 + 128);
  }
  v12 = 0;
  p_Buffer = (PVOID *)&a2->Buffer;
  while ( 1 )
  {
    v14 = *(_DWORD *)(a1 + 116);
    if ( v12 >= v14 )
      goto LABEL_28;
    p_Buffer = (PVOID *)&a2->Buffer;
    v10 = (_QWORD *)(a1 + 128);
    v15 = *(_QWORD *)(a1 + 128);
    v16 = 16LL * v12;
    v17 = *(_WORD **)(v15 + v16 + 8);
    if ( *a2->Buffer == 37 )
    {
      if ( *v17 != 37 )
        goto LABEL_27;
    }
    else if ( *v17 == 37 )
    {
      goto LABEL_22;
    }
    if ( *(_WORD *)(v16 + v15) > a2->Length )
    {
      v10 = (_QWORD *)(a1 + 128);
LABEL_27:
      memmove((void *)(v15 + 16LL * (v12 + 1)), (const void *)(v15 + v16), 16LL * (v14 - v12));
LABEL_28:
      *(UNICODE_STRING *)(*v10 + 16LL * v12) = *a2;
      *p_Buffer = 0;
      ++*(_DWORD *)(a1 + 116);
      return 0;
    }
    if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(v16 + v15), 0) )
      break;
    v10 = (_QWORD *)(a1 + 128);
LABEL_22:
    ++v12;
  }
  if ( *p_Buffer )
    ExFreePoolWithTag(*p_Buffer, 0);
  *p_Buffer = 0;
  return 0;
}

```

## disassembly

```asm
0x140035990  push    rdi
0x140035992  push    r15
0x140035994  sub     rsp, 28h
0x140035998  cmp     word ptr [rdx], 0
0x14003599c  mov     r15, rdx
0x14003599f  mov     rdi, rcx
0x1400359a2  jnz     short loc_1400359B2
0x1400359a4  mov     eax, 0C000000Dh
0x1400359a9  add     rsp, 28h
0x1400359ad  pop     r15
0x1400359af  pop     rdi
0x1400359b0  retn
0x1400359b2  mov     [rsp+38h+arg_0], rbx
0x1400359b7  xor     r8d, r8d; AllocateDestinationString
0x1400359ba  mov     [rsp+38h+arg_8], rbp
0x1400359bf  mov     rcx, r15; DestinationString
0x1400359c2  mov     [rsp+38h+arg_10], rsi
0x1400359c7  call    cs:__imp_RtlUpcaseUnicodeString
0x1400359ce  nop     dword ptr [rax+rax+00h]
0x1400359d3  mov     eax, [rdi+78h]
0x1400359d6  cmp     [rdi+74h], eax
0x1400359d9  jnz     short loc_140035A57
0x1400359db  mov     ecx, eax
0x1400359dd  mov     eax, 0FFFFFFFFh
0x1400359e2  add     rcx, rcx
0x1400359e5  cmp     rcx, rax
0x1400359e8  ja      short loc_140035A4D
0x1400359ea  mov     ebp, ecx
0x1400359ec  mov     ecx, ecx
0x1400359ee  shl     rcx, 4
0x1400359f2  call    AiAlloc
0x1400359f7  mov     rbx, rax
0x1400359fa  test    rax, rax
0x1400359fd  jnz     short loc_140035A09
0x1400359ff  mov     eax, 0C0000017h
0x140035a04  jmp     loc_140035B42
0x140035a09  mov     r8d, [rdi+74h]
0x140035a0d  lea     rsi, [rdi+80h]
0x140035a14  mov     rdx, [rsi]; Src
0x140035a17  mov     rcx, rbx; void *
0x140035a1a  shl     r8, 4; Size
0x140035a1e  call    memmove
0x140035a23  mov     rcx, [rsi]; P
0x140035a26  lea     rax, [rdi+88h]
0x140035a2d  cmp     rcx, rax
0x140035a30  jz      short loc_140035A45
0x140035a32  test    rcx, rcx
0x140035a35  jz      short loc_140035A45
0x140035a37  xor     edx, edx; Tag
0x140035a39  call    cs:__imp_ExFreePoolWithTag
0x140035a40  nop     dword ptr [rax+rax+00h]
0x140035a45  mov     [rdi+78h], ebp
0x140035a48  mov     [rsi], rbx
0x140035a4b  jmp     short loc_140035A5E
0x140035a4d  mov     eax, 0C0000095h
0x140035a52  jmp     loc_140035B42
0x140035a57  lea     rsi, [rdi+80h]
0x140035a5e  mov     [rsp+38h+arg_18], r12
0x140035a63  xor     r12d, r12d
0x140035a66  mov     [rsp+38h+var_18], r14
0x140035a6b  mov     ebp, r12d
0x140035a6e  lea     r14, [r15+8]
0x140035a72  mov     ecx, [rdi+74h]
0x140035a75  mov     ebx, ebp
0x140035a77  cmp     ebp, ecx
0x140035a79  jnb     loc_140035B21
0x140035a7f  mov     rax, [r15+8]
0x140035a83  lea     r14, [r15+8]
0x140035a87  mov     edx, ebx
0x140035a89  lea     rsi, [rdi+80h]
0x140035a90  mov     r9, [rsi]
0x140035a93  shl     rdx, 4
0x140035a97  cmp     word ptr [rax], 25h ; '%'
0x140035a9b  mov     r8, [r9+rdx+8]
0x140035aa0  jnz     short loc_140035AAB
0x140035aa2  cmp     word ptr [r8], 25h ; '%'
0x140035aa7  jz      short loc_140035AB2
0x140035aa9  jmp     short loc_140035B06
0x140035aab  cmp     word ptr [r8], 25h ; '%'
0x140035ab0  jz      short loc_140035AE0
0x140035ab2  movzx   eax, word ptr [r15]
0x140035ab6  lea     r10, [rdx+r9]
0x140035aba  cmp     [r10], ax
0x140035abe  ja      short loc_140035AFF
0x140035ac0  xor     r8d, r8d; CaseInSensitive
0x140035ac3  mov     rdx, r10; String2
0x140035ac6  mov     rcx, r15; String1
0x140035ac9  call    cs:__imp_RtlEqualUnicodeString
0x140035ad0  nop     dword ptr [rax+rax+00h]
0x140035ad5  test    al, al
0x140035ad7  jnz     short loc_140035AE4
0x140035ad9  lea     rsi, [rdi+80h]
0x140035ae0  inc     ebp
0x140035ae2  jmp     short loc_140035A72
0x140035ae4  mov     rcx, [r14]; P
0x140035ae7  test    rcx, rcx
0x140035aea  jz      short loc_140035AFA
0x140035aec  xor     edx, edx; Tag
0x140035aee  call    cs:__imp_ExFreePoolWithTag
0x140035af5  nop     dword ptr [rax+rax+00h]
0x140035afa  mov     [r14], r12
0x140035afd  jmp     short loc_140035B35
0x140035aff  lea     rsi, [rdi+80h]
0x140035b06  sub     ecx, ebp
0x140035b08  add     rdx, r9; Src
0x140035b0b  mov     r8d, ecx
0x140035b0e  lea     ecx, [rbp+1]
0x140035b11  shl     rcx, 4
0x140035b15  add     rcx, r9; void *
0x140035b18  shl     r8, 4; Size
0x140035b1c  call    memmove
0x140035b21  movups  xmm0, xmmword ptr [r15]
0x140035b25  mov     rax, [rsi]
0x140035b28  add     rbx, rbx
0x140035b2b  movups  xmmword ptr [rax+rbx*8], xmm0
0x140035b2f  mov     [r14], r12
0x140035b32  inc     dword ptr [rdi+74h]
0x140035b35  mov     r14, [rsp+38h+var_18]
0x140035b3a  mov     eax, r12d
0x140035b3d  mov     r12, [rsp+38h+arg_18]
0x140035b42  mov     rbp, [rsp+38h+arg_8]
0x140035b47  mov     rbx, [rsp+38h+arg_0]
0x140035b4c  mov     rsi, [rsp+38h+arg_10]
0x140035b51  add     rsp, 28h
0x140035b55  pop     r15
0x140035b57  pop     rdi
0x140035b58  retn
```
