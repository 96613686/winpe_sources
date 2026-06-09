# CopyUnicodeStringToBuffer(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)

- ea: `0x14000a490`
- end: `0x14000a559`
- name: `?CopyUnicodeStringToBuffer@@YAJPEBU_UNICODE_STRING@@00PEAU1@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005db4`
- `0x1400127dc`
- `0x140015648`
- `0x140015ff0`

## callees

- `0x14000a490`
- `0x14000b620`
- `0x14000b70c`

## import_xrefs

- `msvcrt!realloc` at `0x14000a4f0`
- `msvcrt!realloc` at `0x14000a4f0`

## pseudocode

```c
__int64 __fastcall CopyUnicodeStringToBuffer(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        void **a5)
{
  int Length; // r8d
  int v10; // ecx
  unsigned int v11; // ebp
  void *v13; // rax

  if ( a1 )
    Length = a1->Length;
  else
    Length = 0;
  if ( a3 )
    v10 = a3->Length;
  else
    v10 = 0;
  v11 = Length + v10 + a2->Length;
  if ( v11 > 0xFFFE )
    return 2147942487LL;
  if ( a4->MaximumLength < v11 )
  {
    v13 = realloc(*a5, v11);
    if ( !v13 )
      return 2147942414LL;
    *a5 = v13;
    a4->Length = 0;
    a4->MaximumLength = v11;
    a4->Buffer = (PWSTR)*a5;
  }
  if ( a1 )
  {
    RtlUnicodeStringCopy(a4, a1);
    RtlUnicodeStringCat(a4, a2);
  }
  else
  {
    RtlUnicodeStringCopy(a4, a2);
  }
  if ( a3 )
    RtlUnicodeStringCat(a4, a3);
  return 0;
}

```

## disassembly

```asm
0x14000a490  push    rbx
0x14000a492  push    rbp
0x14000a493  push    rsi
0x14000a494  push    rdi
0x14000a495  push    r14
0x14000a497  push    r15
0x14000a499  sub     rsp, 28h
0x14000a49d  mov     rbx, r9
0x14000a4a0  mov     rdi, r8
0x14000a4a3  mov     r14, rdx
0x14000a4a6  mov     rsi, rcx
0x14000a4a9  test    rcx, rcx
0x14000a4ac  jz      short loc_14000A4B4
0x14000a4ae  movzx   r8d, word ptr [rcx]
0x14000a4b2  jmp     short loc_14000A4B7
0x14000a4b4  xor     r8d, r8d
0x14000a4b7  test    rdi, rdi
0x14000a4ba  jz      short loc_14000A4C1
0x14000a4bc  movzx   ecx, word ptr [rdi]
0x14000a4bf  jmp     short loc_14000A4C3
0x14000a4c1  xor     ecx, ecx
0x14000a4c3  movzx   ebp, word ptr [rdx]
0x14000a4c6  add     ebp, ecx
0x14000a4c8  add     ebp, r8d
0x14000a4cb  cmp     ebp, 0FFFEh
0x14000a4d1  jbe     short loc_14000A4DA
0x14000a4d3  mov     eax, 80070057h
0x14000a4d8  jmp     short loc_14000A54C
0x14000a4da  movzx   eax, word ptr [r9+2]
0x14000a4df  cmp     eax, ebp
0x14000a4e1  jnb     short loc_14000A50E
0x14000a4e3  mov     r15, [rsp+58h+arg_20]
0x14000a4eb  mov     edx, ebp; Size
0x14000a4ed  mov     rcx, [r15]; Block
0x14000a4f0  call    cs:__imp_realloc
0x14000a4f6  test    rax, rax
0x14000a4f9  jz      short loc_14000A52B
0x14000a4fb  mov     [r15], rax
0x14000a4fe  xor     eax, eax
0x14000a500  mov     [rbx], ax
0x14000a503  mov     [rbx+2], bp
0x14000a507  mov     rax, [r15]
0x14000a50a  mov     [rbx+8], rax
0x14000a50e  mov     rcx, rbx; struct _UNICODE_STRING *
0x14000a511  test    rsi, rsi
0x14000a514  jz      short loc_14000A532
0x14000a516  mov     rdx, rsi; struct _UNICODE_STRING *
0x14000a519  call    ?RtlUnicodeStringCopy@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCopy(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14000a51e  mov     rdx, r14; struct _UNICODE_STRING *
0x14000a521  mov     rcx, rbx; struct _UNICODE_STRING *
0x14000a524  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14000a529  jmp     short loc_14000A53A
0x14000a52b  mov     eax, 8007000Eh
0x14000a530  jmp     short loc_14000A54C
0x14000a532  mov     rdx, r14; struct _UNICODE_STRING *
0x14000a535  call    ?RtlUnicodeStringCopy@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCopy(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14000a53a  test    rdi, rdi
0x14000a53d  jz      short loc_14000A54A
0x14000a53f  mov     rdx, rdi; struct _UNICODE_STRING *
0x14000a542  mov     rcx, rbx; struct _UNICODE_STRING *
0x14000a545  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14000a54a  xor     eax, eax
0x14000a54c  add     rsp, 28h
0x14000a550  pop     r15
0x14000a552  pop     r14
0x14000a554  pop     rdi
0x14000a555  pop     rsi
0x14000a556  pop     rbp
0x14000a557  pop     rbx
0x14000a558  retn
```
