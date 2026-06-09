# BfsInsertDirectory

- ea: `0x140011cd4`
- end: `0x140011ea0`
- name: `BfsInsertDirectory`
- size: `460`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, PVOID **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001093c`

## callees

- `0x140003614`
- `0x140011404`
- `0x140011cd4`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011e1d`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011e1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e5f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011d9a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011d9a`
- `ntoskrnl!ExAllocatePool2` at `0x140011d27`
- `ntoskrnl!ExAllocatePool2` at `0x140011d53`
- `ntoskrnl!ExAllocatePool2` at `0x140011d27`
- `ntoskrnl!ExAllocatePool2` at `0x140011d53`

## pseudocode

```c
__int64 __fastcall BfsInsertDirectory(__int64 a1, const UNICODE_STRING *a2, PVOID **a3, unsigned __int8 *a4)
{
  __int64 Pool2; // rax
  PVOID *v10; // rax
  char *inserted; // rdi
  PVOID P[20]; // [rsp+20h] [rbp-89h] BYREF

  memset(P, 0, sizeof(P));
  P[0] = (PVOID)ExAllocatePool2(256, 16, 1316185666);
  if ( !P[0] )
    return 3221225495LL;
  Pool2 = ExAllocatePool2(256, a2->MaximumLength, 1316185666);
  if ( !Pool2 )
  {
    ExFreePoolWithTag(P[0], 0);
    return 3221225495LL;
  }
  *((_QWORD *)P[0] + 1) = Pool2;
  *((_WORD *)P[0] + 1) = a2->MaximumLength;
  RtlCopyUnicodeString((PUNICODE_STRING)P[0], a2);
  P[18] = (PVOID)(a1 - 24);
  _InterlockedIncrement((volatile signed __int32 *)(a1 - 32 + 152));
  _InterlockedIncrement((volatile signed __int32 *)&P[19]);
  v10 = *a3;
  *(_OWORD *)&P[1] = *(_OWORD *)*a3;
  *(_OWORD *)&P[3] = *((_OWORD *)v10 + 1);
  *(_OWORD *)&P[5] = *((_OWORD *)v10 + 2);
  *(_OWORD *)&P[7] = *((_OWORD *)v10 + 3);
  *(_OWORD *)&P[9] = *((_OWORD *)v10 + 4);
  *(_OWORD *)&P[11] = *((_OWORD *)v10 + 5);
  *(_OWORD *)&P[13] = *((_OWORD *)v10 + 6);
  *(_OWORD *)&P[15] = *((_OWORD *)v10 + 7);
  P[17] = v10[16];
  inserted = (char *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), P, 0xA0u, a4);
  *a3 = (PVOID *)(inserted + 8);
  if ( !(unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(inserted + 8) )
  {
    if ( !a4 )
      goto LABEL_7;
LABEL_10:
    _InterlockedIncrement((volatile signed __int32 *)inserted + 38);
    return 0;
  }
  if ( *a4 )
    goto LABEL_10;
LABEL_7:
  ExFreePoolWithTag(*((PVOID *)P[0] + 1), 0);
  ExFreePoolWithTag(P[0], 0);
  BfsDereferenceTableEntry((PVOID)(a1 - 32));
  return 0;
}

```

## disassembly

```asm
0x140011cd4  push    rbp
0x140011cd6  push    rbx
0x140011cd7  push    rsi
0x140011cd8  push    rdi
0x140011cd9  push    r14
0x140011cdb  push    r15
0x140011cdd  lea     rbp, [rsp-2Fh]
0x140011ce2  sub     rsp, 0D8h
0x140011ce9  mov     rax, cs:__security_cookie
0x140011cf0  xor     rax, rsp
0x140011cf3  mov     [rbp+57h+var_40], rax
0x140011cf7  mov     r15, r8
0x140011cfa  mov     rdi, rdx
0x140011cfd  mov     r14, rcx
0x140011d00  xor     edx, edx; Val
0x140011d02  mov     r8d, 0A0h; Size
0x140011d08  lea     rcx, [rsp+100h+P]; void *
0x140011d0d  mov     rbx, r9
0x140011d10  call    memset
0x140011d15  mov     esi, 4E736642h
0x140011d1a  mov     edx, 10h
0x140011d1f  mov     r8d, esi
0x140011d22  mov     ecx, 100h
0x140011d27  call    cs:__imp_ExAllocatePool2
0x140011d2e  nop     dword ptr [rax+rax+00h]
0x140011d33  mov     [rsp+100h+P], rax
0x140011d38  test    rax, rax
0x140011d3b  jnz     short loc_140011D47
0x140011d3d  mov     eax, 0C0000017h
0x140011d42  jmp     loc_140011E75
0x140011d47  movzx   edx, word ptr [rdi+2]
0x140011d4b  mov     r8d, esi
0x140011d4e  mov     ecx, 100h
0x140011d53  call    cs:__imp_ExAllocatePool2
0x140011d5a  nop     dword ptr [rax+rax+00h]
0x140011d5f  mov     rcx, rax
0x140011d62  test    rax, rax
0x140011d65  jnz     short loc_140011D7C
0x140011d67  mov     rcx, [rsp+100h+P]; P
0x140011d6c  xor     edx, edx; Tag
0x140011d6e  call    cs:__imp_ExFreePoolWithTag
0x140011d75  nop     dword ptr [rax+rax+00h]
0x140011d7a  jmp     short loc_140011D3D
0x140011d7c  mov     rax, [rsp+100h+P]
0x140011d81  mov     rdx, rdi; SourceString
0x140011d84  mov     [rax+8], rcx
0x140011d88  movzx   ecx, word ptr [rdi+2]
0x140011d8c  mov     rax, [rsp+100h+P]
0x140011d91  mov     [rax+2], cx
0x140011d95  mov     rcx, [rsp+100h+P]; DestinationString
0x140011d9a  call    cs:__imp_RtlCopyUnicodeString
0x140011da1  nop     dword ptr [rax+rax+00h]
0x140011da6  lea     rax, [r14-18h]
0x140011daa  mov     [rbp+57h+var_50], rax
0x140011dae  lea     rsi, [rax-8]
0x140011db2  lock inc dword ptr [rsi+98h]
0x140011db9  lock inc [rbp+57h+var_48]
0x140011dbd  mov     rax, [r15]
0x140011dc0  lea     rcx, [r14+8]; Table
0x140011dc4  mov     r9, rbx; NewElement
0x140011dc7  lea     rdx, [rsp+100h+P]; Buffer
0x140011dcc  mov     r8d, 0A0h; BufferSize
0x140011dd2  movups  xmm0, xmmword ptr [rax]
0x140011dd5  movups  [rsp+100h+var_D8], xmm0
0x140011dda  movups  xmm1, xmmword ptr [rax+10h]
0x140011dde  movups  [rbp+57h+var_C8], xmm1
0x140011de2  movups  xmm0, xmmword ptr [rax+20h]
0x140011de6  movups  [rbp+57h+var_B8], xmm0
0x140011dea  movups  xmm1, xmmword ptr [rax+30h]
0x140011dee  movups  [rbp+57h+var_A8], xmm1
0x140011df2  movups  xmm0, xmmword ptr [rax+40h]
0x140011df6  movups  [rbp+57h+var_98], xmm0
0x140011dfa  movups  xmm1, xmmword ptr [rax+50h]
0x140011dfe  movups  [rbp+57h+var_88], xmm1
0x140011e02  movups  xmm0, xmmword ptr [rax+60h]
0x140011e06  movups  [rbp+57h+var_78], xmm0
0x140011e0a  movups  xmm1, xmmword ptr [rax+70h]
0x140011e0e  movups  [rbp+57h+var_68], xmm1
0x140011e12  mov     rax, [rax+80h]
0x140011e19  mov     [rbp+57h+var_58], rax
0x140011e1d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140011e24  nop     dword ptr [rax+rax+00h]
0x140011e29  mov     rdi, rax
0x140011e2c  lea     rcx, [rax+8]
0x140011e30  mov     [r15], rcx
0x140011e33  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140011e38  test    eax, eax
0x140011e3a  jz      short loc_140011E92
0x140011e3c  cmp     byte ptr [rbx], 0
0x140011e3f  jnz     short loc_140011E97
0x140011e41  mov     rcx, [rsp+100h+P]
0x140011e46  xor     edx, edx; Tag
0x140011e48  mov     rcx, [rcx+8]; P
0x140011e4c  call    cs:__imp_ExFreePoolWithTag
0x140011e53  nop     dword ptr [rax+rax+00h]
0x140011e58  mov     rcx, [rsp+100h+P]; P
0x140011e5d  xor     edx, edx; Tag
0x140011e5f  call    cs:__imp_ExFreePoolWithTag
0x140011e66  nop     dword ptr [rax+rax+00h]
0x140011e6b  mov     rcx, rsi; Buffer
0x140011e6e  call    BfsDereferenceTableEntry
0x140011e73  xor     eax, eax
0x140011e75  mov     rcx, [rbp+57h+var_40]
0x140011e79  xor     rcx, rsp; StackCookie
0x140011e7c  call    __security_check_cookie
0x140011e81  add     rsp, 0D8h
0x140011e88  pop     r15
0x140011e8a  pop     r14
0x140011e8c  pop     rdi
0x140011e8d  pop     rsi
0x140011e8e  pop     rbx
0x140011e8f  pop     rbp
0x140011e90  retn
0x140011e92  test    rbx, rbx
0x140011e95  jz      short loc_140011E41
0x140011e97  lock inc dword ptr [rdi+98h]
0x140011e9e  jmp     short loc_140011E73
```
