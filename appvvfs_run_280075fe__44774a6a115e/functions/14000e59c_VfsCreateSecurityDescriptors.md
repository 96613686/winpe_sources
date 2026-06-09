# VfsCreateSecurityDescriptors

- ea: `0x14000e59c`
- end: `0x14000e847`
- name: `VfsCreateSecurityDescriptors`
- size: `683`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000874c`

## callees

- `0x14000e59c`
- `0x14000e850`
- `0x14000e8d0`
- `0x14000e944`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e774`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e774`
- `ntoskrnl!RtlEqualSid` at `0x14000e791`
- `ntoskrnl!RtlEqualSid` at `0x14000e791`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e707`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000e707`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015472`
- `ntoskrnl!ExAllocatePool2` at `0x14000e697`
- `ntoskrnl!ExAllocatePool2` at `0x14000e697`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e6ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e6ce`

## string_xrefs

- `0x14000e743`: `VfsCreateSecurityDescriptors() - Failed to read security descriptors for : %wZ\n Status: 0x%08X`
- `0x14000e7cc`: `VfsCreateSecurityDescriptors() - Failed to get child file security descriptors for : %wZ\n Status: 0x%08X`
- `0x14000e7ed`: `VfsCreateSecurityDescriptors() - Failed to get child directory security descriptors for : %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateSecurityDescriptors(
        PFLT_INSTANCE Instance,
        UNICODE_STRING *a2,
        UNICODE_STRING *a3,
        void *a4,
        __int64 a5)
{
  char v7; // r14
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r8
  unsigned int v11; // esi
  int v12; // ebx
  unsigned __int16 Length; // ax
  int SecurityDescriptor; // eax
  const wchar_t *v15; // r8
  void *v16; // rcx
  bool v17; // zf
  char v18; // al
  unsigned __int8 OwnerDefaulted[3]; // [rsp+31h] [rbp-87h] BYREF
  int v21; // [rsp+34h] [rbp-84h]
  int v22; // [rsp+38h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-68h]
  PSID Owner; // [rsp+58h] [rbp-60h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-58h] BYREF
  UNICODE_STRING Source; // [rsp+70h] [rbp-48h] BYREF

  v21 = 0;
  DestinationString = 0;
  v7 = 0;
  *(_OWORD *)a5 = 0;
  *(_QWORD *)(a5 + 16) = 0;
  v24 = 0;
  v22 = 0;
  SourceString = *a2;
  Source = *a3;
  v8 = (unsigned int)_mm_cvtsi128_si32((__m128i)SourceString);
  v9 = *(_WORD *)(_mm_srli_si128((__m128i)SourceString, 8).m128i_u64[0]
                + 2 * ((unsigned __int64)(unsigned __int16)v8 >> 1)
                - 2) == 92;
  v22 = v9;
  if ( *(_WORD *)_mm_srli_si128((__m128i)Source, 8).m128i_i16[0] == 92 )
    v22 = ++v9;
  v10 = 65534;
  if ( v9 == 2 )
  {
    LOWORD(v8) = v8 - 2;
    SourceString.Length = v8;
    v9 = 1;
    v22 = 1;
  }
  if ( v9 )
    v11 = (unsigned __int16)v8 + Source.Length;
  else
    v11 = Source.Length + 2 + (unsigned __int16)v8;
  v24 = v11;
  if ( v11 <= 0xFFFE )
  {
    DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v11, 1951614550);
    if ( DestinationString.Buffer )
    {
      DestinationString.Length = 0;
      DestinationString.MaximumLength = v11;
      Length = SourceString.Length;
      if ( SourceString.Length )
      {
        RtlCopyUnicodeString(&DestinationString, &SourceString);
        Length = SourceString.Length;
      }
      if ( !v9 )
      {
        DestinationString.Buffer[(unsigned __int64)Length >> 1] = 92;
        DestinationString.Length += 2;
      }
      RtlAppendUnicodeStringToString(&DestinationString, &Source);
      v12 = 0;
    }
    else
    {
      v12 = -1073741670;
    }
  }
  else
  {
    v12 = -1073741562;
  }
  v21 = v12;
  if ( v12 >= 0 )
  {
    SecurityDescriptor = VfsReadSecurityDescriptor(Instance);
    v12 = SecurityDescriptor;
    v21 = SecurityDescriptor;
    if ( SecurityDescriptor < 0 )
    {
      v15 = L"VfsCreateSecurityDescriptors() - Failed to read security descriptors for : %wZ\n Status: 0x%08X";
LABEL_32:
      LogWrite(1, 0, v15, &DestinationString, SecurityDescriptor);
      goto LABEL_33;
    }
    v16 = *(void **)a5;
    if ( *(_QWORD *)a5 )
    {
      if ( !a4 )
        goto LABEL_28;
      Owner = 0;
      OwnerDefaulted[0] = 0;
      if ( RtlGetOwnerSecurityDescriptor(v16, &Owner, OwnerDefaulted) < 0 )
        goto LABEL_27;
      if ( !Owner || (v17 = RtlEqualSid(Owner, a4) == 0, v18 = 0, !v17) )
        v18 = 1;
      if ( v18 )
      {
LABEL_27:
        v7 = 1;
      }
      else
      {
LABEL_28:
        SecurityDescriptor = VfsGetChildSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)a5);
        v12 = SecurityDescriptor;
        v21 = SecurityDescriptor;
        if ( SecurityDescriptor < 0 )
        {
          v15 = L"VfsCreateSecurityDescriptors() - Failed to get child file security descriptors for : %wZ\n"
                 " Status: 0x%08X";
          goto LABEL_32;
        }
        SecurityDescriptor = VfsGetChildSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)a5);
        v12 = SecurityDescriptor;
        v21 = SecurityDescriptor;
        if ( SecurityDescriptor < 0 )
        {
          v15 = L"VfsCreateSecurityDescriptors() - Failed to get child directory security descriptors for : %wZ\n"
                 " Status: 0x%08X";
          goto LABEL_32;
        }
      }
    }
  }
LABEL_33:
  if ( v12 < 0 || v7 )
    VfsDeleteSecurityDescriptors(a5, v8, v10);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000e59c  push    rbx
0x14000e59e  push    rsi
0x14000e59f  push    rdi
0x14000e5a0  push    r12
0x14000e5a2  push    r13
0x14000e5a4  push    r14
0x14000e5a6  push    r15
0x14000e5a8  sub     rsp, 80h
0x14000e5af  mov     r15, r9
0x14000e5b2  mov     r12, rcx
0x14000e5b5  xor     r13d, r13d
0x14000e5b8  mov     [rsp+0B8h+var_84], r13d
0x14000e5bd  xorps   xmm0, xmm0
0x14000e5c0  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14000e5c5  mov     r14b, r13b
0x14000e5c8  mov     [rsp+0B8h+var_88], r13b
0x14000e5cd  xor     eax, eax
0x14000e5cf  mov     rdi, [rsp+0B8h+arg_20]
0x14000e5d7  movups  xmmword ptr [rdi], xmm0
0x14000e5da  mov     [rdi+10h], rax
0x14000e5de  mov     [rsp+0B8h+var_68], r13d
0x14000e5e3  mov     ebx, r13d
0x14000e5e6  mov     [rsp+0B8h+var_80], ebx
0x14000e5ea  movups  xmm0, xmmword ptr [rdx]
0x14000e5ed  movups  xmmword ptr [rsp+0B8h+SourceString.Length], xmm0
0x14000e5f2  movups  xmm1, xmmword ptr [r8]
0x14000e5f6  movups  xmmword ptr [rsp+0B8h+Source.Length], xmm1
0x14000e5fb  movd    edx, xmm0
0x14000e5ff  movzx   ecx, dx
0x14000e602  shr     rcx, 1
0x14000e605  lea     r9d, [r13+1]
0x14000e609  lea     r8d, [r13+5Ch]
0x14000e60d  psrldq  xmm0, 8
0x14000e612  movq    rax, xmm0
0x14000e617  cmp     [rax+rcx*2-2], r8w
0x14000e61d  cmovz   ebx, r9d
0x14000e621  mov     [rsp+0B8h+var_80], ebx
0x14000e625  psrldq  xmm1, 8
0x14000e62a  movq    rax, xmm1
0x14000e62f  cmp     [rax], r8w
0x14000e633  jnz     short loc_14000E63C
0x14000e635  add     ebx, r9d
0x14000e638  mov     [rsp+0B8h+var_80], ebx
0x14000e63c  mov     r8d, 0FFFEh
0x14000e642  cmp     ebx, 2
0x14000e645  jnz     short loc_14000E657
0x14000e647  add     dx, r8w
0x14000e64b  mov     [rsp+0B8h+SourceString.Length], dx
0x14000e650  mov     ebx, r9d
0x14000e653  mov     [rsp+0B8h+var_80], ebx
0x14000e657  test    ebx, ebx
0x14000e659  jnz     short loc_14000E66A
0x14000e65b  movzx   ecx, [rsp+0B8h+Source.Length]
0x14000e660  movzx   esi, dx
0x14000e663  add     ecx, 2
0x14000e666  add     esi, ecx
0x14000e668  jmp     short loc_14000E674
0x14000e66a  movzx   esi, [rsp+0B8h+Source.Length]
0x14000e66f  movzx   eax, dx
0x14000e672  add     esi, eax
0x14000e674  mov     eax, esi
0x14000e676  mov     [rsp+0B8h+var_68], esi
0x14000e67a  cmp     eax, r8d
0x14000e67d  jbe     short loc_14000E689
0x14000e67f  mov     ebx, 0C0000106h
0x14000e684  jmp     loc_14000E71D
0x14000e689  movzx   edx, si
0x14000e68c  mov     ecx, 100h
0x14000e691  mov     r8d, 74534656h
0x14000e697  call    cs:__imp_ExAllocatePool2
0x14000e69e  nop     dword ptr [rax+rax+00h]
0x14000e6a3  mov     [rsp+0B8h+DestinationString.Buffer], rax
0x14000e6a8  test    rax, rax
0x14000e6ab  jz      short loc_14000E718
0x14000e6ad  mov     eax, r13d
0x14000e6b0  mov     [rsp+0B8h+DestinationString.Length], ax
0x14000e6b5  mov     [rsp+0B8h+DestinationString.MaximumLength], si
0x14000e6ba  movzx   eax, [rsp+0B8h+SourceString.Length]
0x14000e6bf  test    ax, ax
0x14000e6c2  jz      short loc_14000E6DF
0x14000e6c4  lea     rdx, [rsp+0B8h+SourceString]; SourceString
0x14000e6c9  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14000e6ce  call    cs:__imp_RtlCopyUnicodeString
0x14000e6d5  nop     dword ptr [rax+rax+00h]
0x14000e6da  movzx   eax, [rsp+0B8h+SourceString.Length]
0x14000e6df  test    ebx, ebx
0x14000e6e1  jnz     short loc_14000E6FD
0x14000e6e3  movzx   ecx, ax
0x14000e6e6  shr     rcx, 1
0x14000e6e9  mov     rax, [rsp+0B8h+DestinationString.Buffer]
0x14000e6ee  lea     edx, [rbx+5Ch]
0x14000e6f1  mov     [rax+rcx*2], dx
0x14000e6f5  lea     eax, [rbx+2]
0x14000e6f8  add     [rsp+0B8h+DestinationString.Length], ax
0x14000e6fd  lea     rdx, [rsp+0B8h+Source]; Source
0x14000e702  lea     rcx, [rsp+0B8h+DestinationString]; Destination
0x14000e707  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e70e  nop     dword ptr [rax+rax+00h]
0x14000e713  mov     ebx, r13d
0x14000e716  jmp     short loc_14000E71D
0x14000e718  mov     ebx, 0C000009Ah
0x14000e71d  mov     [rsp+0B8h+var_84], ebx
0x14000e721  test    ebx, ebx
0x14000e723  js      loc_14000E808
0x14000e729  mov     r8, rdi
0x14000e72c  lea     rdx, [rsp+0B8h+DestinationString]
0x14000e731  mov     rcx, r12; Instance
0x14000e734  call    VfsReadSecurityDescriptor
0x14000e739  mov     ebx, eax
0x14000e73b  mov     [rsp+0B8h+var_84], eax
0x14000e73f  test    eax, eax
0x14000e741  jns     short loc_14000E74F
0x14000e743  lea     r8, aVfscreatesecur_0; "VfsCreateSecurityDescriptors() - Failed"...
0x14000e74a  jmp     loc_14000E7F4
0x14000e74f  mov     rcx, [rdi]; SecurityDescriptor
0x14000e752  test    rcx, rcx
0x14000e755  jz      loc_14000E808
0x14000e75b  test    r15, r15
0x14000e75e  jz      short loc_14000E7B4
0x14000e760  mov     [rsp+0B8h+Owner], r13
0x14000e765  mov     [rsp+0B8h+OwnerDefaulted], r13b
0x14000e76a  lea     r8, [rsp+0B8h+OwnerDefaulted]; OwnerDefaulted
0x14000e76f  lea     rdx, [rsp+0B8h+Owner]; Owner
0x14000e774  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000e77b  nop     dword ptr [rax+rax+00h]
0x14000e780  test    eax, eax
0x14000e782  js      short loc_14000E7AA
0x14000e784  mov     rcx, [rsp+0B8h+Owner]; Sid1
0x14000e789  test    rcx, rcx
0x14000e78c  jz      short loc_14000E7A4
0x14000e78e  mov     rdx, r15; Sid2
0x14000e791  call    cs:__imp_RtlEqualSid
0x14000e798  nop     dword ptr [rax+rax+00h]
0x14000e79d  test    al, al
0x14000e79f  mov     al, r13b
0x14000e7a2  jz      short loc_14000E7A6
0x14000e7a4  mov     al, 1
0x14000e7a6  test    al, al
0x14000e7a8  jz      short loc_14000E7B4
0x14000e7aa  mov     r14b, 1
0x14000e7ad  mov     [rsp+0B8h+var_88], r14b
0x14000e7b2  jmp     short loc_14000E808
0x14000e7b4  lea     r8, [rdi+8]
0x14000e7b8  xor     edx, edx
0x14000e7ba  mov     rcx, [rdi]; ParentDescriptor
0x14000e7bd  call    VfsGetChildSecurityDescriptor
0x14000e7c2  mov     ebx, eax
0x14000e7c4  mov     [rsp+0B8h+var_84], eax
0x14000e7c8  test    eax, eax
0x14000e7ca  jns     short loc_14000E7D5
0x14000e7cc  lea     r8, aVfscreatesecur_1; "VfsCreateSecurityDescriptors() - Failed"...
0x14000e7d3  jmp     short loc_14000E7F4
0x14000e7d5  lea     r8, [rdi+10h]
0x14000e7d9  mov     dl, 1
0x14000e7db  mov     rcx, [rdi]; ParentDescriptor
0x14000e7de  call    VfsGetChildSecurityDescriptor
0x14000e7e3  mov     ebx, eax
0x14000e7e5  mov     [rsp+0B8h+var_84], eax
0x14000e7e9  test    eax, eax
0x14000e7eb  jns     short loc_14000E808
0x14000e7ed  lea     r8, aVfscreatesecur; "VfsCreateSecurityDescriptors() - Failed"...
0x14000e7f4  mov     [rsp+0B8h+var_98], eax
0x14000e7f8  lea     r9, [rsp+0B8h+DestinationString]
0x14000e7fd  xor     edx, edx
0x14000e7ff  lea     ecx, [rdx+1]
0x14000e802  call    LogWrite
0x14000e807  nop
0x14000e808  test    ebx, ebx
0x14000e80a  js      short loc_14000E811
0x14000e80c  test    r14b, r14b
0x14000e80f  jz      short loc_14000E819
0x14000e811  mov     rcx, rdi
0x14000e814  call    VfsDeleteSecurityDescriptors
0x14000e819  mov     rcx, [rsp+0B8h+DestinationString.Buffer]; P
0x14000e81e  test    rcx, rcx
0x14000e821  jz      short loc_14000E831
0x14000e823  xor     edx, edx; Tag
0x14000e825  call    cs:__imp_ExFreePoolWithTag
0x14000e82c  nop     dword ptr [rax+rax+00h]
0x14000e831  mov     eax, ebx
0x14000e833  add     rsp, 80h
0x14000e83a  pop     r15
0x14000e83c  pop     r14
0x14000e83e  pop     r13
0x14000e840  pop     r12
0x14000e842  pop     rdi
0x14000e843  pop     rsi
0x14000e844  pop     rbx
0x14000e845  retn
0x140015445  push    rbp
0x140015447  sub     rsp, 30h
0x14001544b  mov     rbp, rdx
0x14001544e  cmp     dword ptr [rbp+34h], 0
0x140015452  jl      short loc_14001545A
0x140015454  cmp     byte ptr [rbp+30h], 0
0x140015458  jz      short loc_140015467
0x14001545a  mov     rcx, [rbp+0E0h]
0x140015461  call    VfsDeleteSecurityDescriptors
0x140015466  nop
0x140015467  mov     rcx, [rbp+48h]; P
0x14001546b  test    rcx, rcx
0x14001546e  jz      short loc_14001547F
0x140015470  xor     edx, edx; Tag
0x140015472  call    cs:__imp_ExFreePoolWithTag
0x140015479  nop     dword ptr [rax+rax+00h]
0x14001547e  nop
0x14001547f  add     rsp, 30h
0x140015483  pop     rbp
0x140015484  retn
```
