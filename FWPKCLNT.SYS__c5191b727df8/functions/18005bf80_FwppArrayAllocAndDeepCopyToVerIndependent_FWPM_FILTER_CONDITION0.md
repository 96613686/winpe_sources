# FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0

- ea: `0x18005bf80`
- end: `0x18005c0c0`
- name: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005de0c`

## callees

- `0x1800050cc`
- `0x18000891c`
- `0x18000c9b4`
- `0x18000e0bc`
- `0x1800208c0`
- `0x18005bf80`
- `0x18005c9d0`
- `0x180061970`

## string_xrefs

- `0x18005c03e`: `FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x18005c056`: `FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x18005c079`: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x18005c09c`: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`

## pseudocode

```c
__int64 __fastcall FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  char *v3; // rdi
  __int64 v4; // rsi
  __int64 v8; // rbx
  unsigned int v9; // edi
  size_t v10; // r8
  __int64 v11; // r8
  char *v12; // rdx
  __int64 v13; // rax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  void *v16; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v16 = 0;
  LODWORD(Size) = 0;
  if ( !a1 || !a3 )
  {
    v8 = WfpReportAppErrorAsNtStatus(
           a1,
           (__int64)"FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0",
           3223453724LL);
    if ( !v8 )
      return v8;
    goto LABEL_17;
  }
  v8 = WfpUINT32Multiply(a2, 40, &Size);
  if ( v8 )
  {
LABEL_17:
    FwppArrayDeepFree_FWPM_FILTER_CONDITION0(v3, (unsigned int)v4);
    if ( v8 )
      WfpReportError(v8, (int)"FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0");
    return v8;
  }
  v9 = Size;
  v8 = WfpPoolAllocNonPaged((unsigned int)Size, 1886418758, &v16);
  if ( v8 )
  {
    v3 = (char *)v16;
    goto LABEL_17;
  }
  v10 = v9;
  v3 = (char *)v16;
  memset(v16, 0, v10);
  while ( (unsigned int)v4 < a2 )
  {
    v11 = a1 + 40 * v4;
    if ( v11 && (v12 = &v3[40 * v4]) != 0 )
    {
      *(_OWORD *)v12 = *(_OWORD *)v11;
      *((_DWORD *)v12 + 4) = *(_DWORD *)(v11 + 16);
      v13 = FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0(v11 + 24, v12 + 24);
    }
    else
    {
      v13 = WfpReportAppErrorAsNtStatus(
              5 * v4,
              (__int64)"FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0",
              3223453724LL);
    }
    v8 = v13;
    if ( v13 )
    {
      WfpReportError(v13, (int)"FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0");
      goto LABEL_17;
    }
    v4 = (unsigned int)(v4 + 1);
  }
  *a3 = v3;
  return v8;
}

```

## disassembly

```asm
0x18005bf80  mov     rax, rsp
0x18005bf83  mov     [rax+10h], rbx
0x18005bf87  push    rbp
0x18005bf88  push    rsi
0x18005bf89  push    rdi
0x18005bf8a  push    r14
0x18005bf8c  push    r15
0x18005bf8e  sub     rsp, 30h
0x18005bf92  xor     edi, edi
0x18005bf94  xor     esi, esi
0x18005bf96  mov     [rax+20h], rdi
0x18005bf9a  mov     r14, r8
0x18005bf9d  mov     [rax+8], edi
0x18005bfa0  mov     ebp, edx
0x18005bfa2  mov     r15, rcx
0x18005bfa5  test    rcx, rcx
0x18005bfa8  jz      loc_18005C073
0x18005bfae  test    r8, r8
0x18005bfb1  jz      loc_18005C073
0x18005bfb7  lea     r8, [rax+8]
0x18005bfbb  mov     ecx, ebp
0x18005bfbd  lea     edx, [rdi+28h]
0x18005bfc0  call    WfpUINT32Multiply
0x18005bfc5  mov     rbx, rax
0x18005bfc8  test    rax, rax
0x18005bfcb  jnz     loc_18005C08D
0x18005bfd1  mov     edi, dword ptr [rsp+58h+Size]
0x18005bfd5  lea     r8, [rsp+58h+arg_18]
0x18005bfda  mov     ecx, edi
0x18005bfdc  mov     edx, 70707746h
0x18005bfe1  call    WfpPoolAllocNonPaged
0x18005bfe6  mov     rbx, rax
0x18005bfe9  test    rax, rax
0x18005bfec  jnz     short loc_18005C06C
0x18005bfee  mov     r8d, edi; Size
0x18005bff1  xor     edx, edx; Val
0x18005bff3  mov     rdi, [rsp+58h+arg_18]
0x18005bff8  mov     rcx, rdi; void *
0x18005bffb  call    memset
0x18005c000  cmp     esi, ebp
0x18005c002  jnb     short loc_18005C067
0x18005c004  lea     rcx, [rsi+rsi*4]
0x18005c008  lea     r8, [r15+rcx*8]
0x18005c00c  test    r8, r8
0x18005c00f  jz      short loc_18005C038
0x18005c011  lea     rdx, [rdi+rcx*8]
0x18005c015  test    rdx, rdx
0x18005c018  jz      short loc_18005C038
0x18005c01a  movups  xmm0, xmmword ptr [r8]
0x18005c01e  lea     rcx, [r8+18h]
0x18005c022  movdqu  xmmword ptr [rdx], xmm0
0x18005c026  mov     eax, [r8+10h]
0x18005c02a  mov     [rdx+10h], eax
0x18005c02d  add     rdx, 18h
0x18005c031  call    FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0
0x18005c036  jmp     short loc_18005C04A
0x18005c038  mov     r8d, 0C022001Ch
0x18005c03e  lea     rdx, aFwppdeepcopyto_27; "FwppDeepCopyToVerIndependent_FWPM_FILTE"...
0x18005c045  call    WfpReportAppErrorAsNtStatus
0x18005c04a  mov     rbx, rax
0x18005c04d  test    rax, rax
0x18005c050  jnz     short loc_18005C056
0x18005c052  inc     esi
0x18005c054  jmp     short loc_18005C000
0x18005c056  lea     rdx, aFwppdeepcopyto_27; "FwppDeepCopyToVerIndependent_FWPM_FILTE"...
0x18005c05d  mov     rcx, rbx
0x18005c060  call    WfpReportError
0x18005c065  jmp     short loc_18005C08D
0x18005c067  mov     [r14], rdi
0x18005c06a  jmp     short loc_18005C0AB
0x18005c06c  mov     rdi, [rsp+58h+arg_18]
0x18005c071  jmp     short loc_18005C08D
0x18005c073  mov     r8d, 0C022001Ch
0x18005c079  lea     rdx, aFwpparrayalloc_5; "FwppArrayAllocAndDeepCopyToVerIndepende"...
0x18005c080  call    WfpReportAppErrorAsNtStatus
0x18005c085  mov     rbx, rax
0x18005c088  test    rax, rax
0x18005c08b  jz      short loc_18005C0AB
0x18005c08d  mov     edx, esi
0x18005c08f  mov     rcx, rdi
0x18005c092  call    FwppArrayDeepFree_FWPM_FILTER_CONDITION0
0x18005c097  test    rbx, rbx
0x18005c09a  jz      short loc_18005C0AB
0x18005c09c  lea     rdx, aFwpparrayalloc_5; "FwppArrayAllocAndDeepCopyToVerIndepende"...
0x18005c0a3  mov     rcx, rbx
0x18005c0a6  call    WfpReportError
0x18005c0ab  mov     rax, rbx
0x18005c0ae  mov     rbx, [rsp+58h+arg_8]
0x18005c0b3  add     rsp, 30h
0x18005c0b7  pop     r15
0x18005c0b9  pop     r14
0x18005c0bb  pop     rdi
0x18005c0bc  pop     rsi
0x18005c0bd  pop     rbp
0x18005c0be  retn
```
