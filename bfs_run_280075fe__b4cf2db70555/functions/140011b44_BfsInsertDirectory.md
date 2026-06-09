# BfsInsertDirectory

- ea: `0x140011b44`
- end: `0x140011d10`
- name: `BfsInsertDirectory`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001079c`

## callees

- `0x1400034e4`
- `0x14001126c`
- `0x140011b44`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011c8d`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140011c8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011bde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ccf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011bde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ccf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011c0a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140011c0a`
- `ntoskrnl!ExAllocatePool2` at `0x140011b97`
- `ntoskrnl!ExAllocatePool2` at `0x140011bc3`
- `ntoskrnl!ExAllocatePool2` at `0x140011b97`
- `ntoskrnl!ExAllocatePool2` at `0x140011bc3`

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
0x140011b44  push    rbp
0x140011b46  push    rbx
0x140011b47  push    rsi
0x140011b48  push    rdi
0x140011b49  push    r14
0x140011b4b  push    r15
0x140011b4d  lea     rbp, [rsp-2Fh]
0x140011b52  sub     rsp, 0D8h
0x140011b59  mov     rax, cs:__security_cookie
0x140011b60  xor     rax, rsp
0x140011b63  mov     [rbp+57h+var_40], rax
0x140011b67  mov     r15, r8
0x140011b6a  mov     rdi, rdx
0x140011b6d  mov     r14, rcx
0x140011b70  xor     edx, edx; Val
0x140011b72  mov     r8d, 0A0h; Size
0x140011b78  lea     rcx, [rsp+100h+P]; void *
0x140011b7d  mov     rbx, r9
0x140011b80  call    memset
0x140011b85  mov     esi, 4E736642h
0x140011b8a  mov     edx, 10h
0x140011b8f  mov     r8d, esi
0x140011b92  mov     ecx, 100h
0x140011b97  call    cs:__imp_ExAllocatePool2
0x140011b9e  nop     dword ptr [rax+rax+00h]
0x140011ba3  mov     [rsp+100h+P], rax
0x140011ba8  test    rax, rax
0x140011bab  jnz     short loc_140011BB7
0x140011bad  mov     eax, 0C0000017h
0x140011bb2  jmp     loc_140011CE5
0x140011bb7  movzx   edx, word ptr [rdi+2]
0x140011bbb  mov     r8d, esi
0x140011bbe  mov     ecx, 100h
0x140011bc3  call    cs:__imp_ExAllocatePool2
0x140011bca  nop     dword ptr [rax+rax+00h]
0x140011bcf  mov     rcx, rax
0x140011bd2  test    rax, rax
0x140011bd5  jnz     short loc_140011BEC
0x140011bd7  mov     rcx, [rsp+100h+P]; P
0x140011bdc  xor     edx, edx; Tag
0x140011bde  call    cs:__imp_ExFreePoolWithTag
0x140011be5  nop     dword ptr [rax+rax+00h]
0x140011bea  jmp     short loc_140011BAD
0x140011bec  mov     rax, [rsp+100h+P]
0x140011bf1  mov     rdx, rdi; SourceString
0x140011bf4  mov     [rax+8], rcx
0x140011bf8  movzx   ecx, word ptr [rdi+2]
0x140011bfc  mov     rax, [rsp+100h+P]
0x140011c01  mov     [rax+2], cx
0x140011c05  mov     rcx, [rsp+100h+P]; DestinationString
0x140011c0a  call    cs:__imp_RtlCopyUnicodeString
0x140011c11  nop     dword ptr [rax+rax+00h]
0x140011c16  lea     rax, [r14-18h]
0x140011c1a  mov     [rbp+57h+var_50], rax
0x140011c1e  lea     rsi, [rax-8]
0x140011c22  lock inc dword ptr [rsi+98h]
0x140011c29  lock inc [rbp+57h+var_48]
0x140011c2d  mov     rax, [r15]
0x140011c30  movups  xmm0, xmmword ptr [rax]
0x140011c33  movups  [rsp+100h+var_D8], xmm0
0x140011c38  movups  xmm1, xmmword ptr [rax+10h]
0x140011c3c  movups  [rbp+57h+var_C8], xmm1
0x140011c40  movups  xmm0, xmmword ptr [rax+20h]
0x140011c44  movups  [rbp+57h+var_B8], xmm0
0x140011c48  movups  xmm1, xmmword ptr [rax+30h]
0x140011c4c  movups  [rbp+57h+var_A8], xmm1
0x140011c50  movups  xmm0, xmmword ptr [rax+40h]
0x140011c54  movups  [rbp+57h+var_98], xmm0
0x140011c58  movups  xmm1, xmmword ptr [rax+50h]
0x140011c5c  movups  [rbp+57h+var_88], xmm1
0x140011c60  movups  xmm0, xmmword ptr [rax+60h]
0x140011c64  movups  [rbp+57h+var_78], xmm0
0x140011c68  movups  xmm1, xmmword ptr [rax+70h]
0x140011c6c  movups  [rbp+57h+var_68], xmm1
0x140011c70  mov     rax, [rax+80h]
0x140011c77  mov     [rbp+57h+var_58], rax
0x140011c7b  lea     rcx, [r14+8]; Table
0x140011c7f  mov     r9, rbx; NewElement
0x140011c82  mov     r8d, 0A0h; BufferSize
0x140011c88  lea     rdx, [rsp+100h+P]; Buffer
0x140011c8d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140011c94  nop     dword ptr [rax+rax+00h]
0x140011c99  mov     rdi, rax
0x140011c9c  lea     rcx, [rax+8]
0x140011ca0  mov     [r15], rcx
0x140011ca3  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140011ca8  test    eax, eax
0x140011caa  jz      short loc_140011D02
0x140011cac  cmp     byte ptr [rbx], 0
0x140011caf  jnz     short loc_140011D07
0x140011cb1  mov     rcx, [rsp+100h+P]
0x140011cb6  xor     edx, edx; Tag
0x140011cb8  mov     rcx, [rcx+8]; P
0x140011cbc  call    cs:__imp_ExFreePoolWithTag
0x140011cc3  nop     dword ptr [rax+rax+00h]
0x140011cc8  mov     rcx, [rsp+100h+P]; P
0x140011ccd  xor     edx, edx; Tag
0x140011ccf  call    cs:__imp_ExFreePoolWithTag
0x140011cd6  nop     dword ptr [rax+rax+00h]
0x140011cdb  mov     rcx, rsi; Buffer
0x140011cde  call    BfsDereferenceTableEntry
0x140011ce3  xor     eax, eax
0x140011ce5  mov     rcx, [rbp+57h+var_40]
0x140011ce9  xor     rcx, rsp; StackCookie
0x140011cec  call    __security_check_cookie
0x140011cf1  add     rsp, 0D8h
0x140011cf8  pop     r15
0x140011cfa  pop     r14
0x140011cfc  pop     rdi
0x140011cfd  pop     rsi
0x140011cfe  pop     rbx
0x140011cff  pop     rbp
0x140011d00  retn
0x140011d02  test    rbx, rbx
0x140011d05  jz      short loc_140011CB1
0x140011d07  lock inc dword ptr [rdi+98h]
0x140011d0e  jmp     short loc_140011CE3
```
