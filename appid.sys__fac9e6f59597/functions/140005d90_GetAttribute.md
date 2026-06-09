# GetAttribute

- ea: `0x140005d90`
- end: `0x140006198`
- name: `GetAttribute`
- size: `1032`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int16, struct _UNICODE_STRING **, PWSTR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140006418`

## callees

- `0x140002e98`
- `0x140005b48`
- `0x140005d90`
- `0x1400061a0`
- `0x1400067ec`
- `0x140006f40`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140005f77`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000614d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006163`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000614d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006163`
- `ntoskrnl!ExAllocatePool2` at `0x140005e06`
- `ntoskrnl!ExAllocatePool2` at `0x140005f25`
- `ntoskrnl!ExAllocatePool2` at `0x14000608b`
- `ntoskrnl!ExAllocatePool2` at `0x140005e06`
- `ntoskrnl!ExAllocatePool2` at `0x140005f25`
- `ntoskrnl!ExAllocatePool2` at `0x14000608b`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140005e75`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140005e75`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140005e42`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140005e42`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x140005e63`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x140005e63`

## pseudocode

```c
__int64 __fastcall GetAttribute(_QWORD *a1, __int64 a2, unsigned __int16 a3, struct _UNICODE_STRING **a4, PWSTR *a5)
{
  struct _UNICODE_STRING **v5; // r15
  struct _UNICODE_STRING *v9; // rdi
  unsigned int v10; // ecx
  __int64 Pool2; // r13
  int SecurityAttributesToken; // eax
  __int64 v13; // rcx
  int FqbnString; // esi
  __int64 v15; // rax
  const UNICODE_STRING *v16; // r14
  __int64 v17; // rax
  struct _UNICODE_STRING *v18; // r12
  WCHAR *v19; // rdi
  USHORT v20; // bx
  PWSTR *v21; // rcx
  PWSTR Buffer; // rax
  unsigned int v23; // eax
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned int v26; // ecx
  wchar_t *v27; // r12
  size_t v28; // rbx
  bool v29; // zf
  unsigned int v30; // r15d
  __int64 v32; // [rsp+30h] [rbp-30h]
  unsigned int i; // [rsp+40h] [rbp-20h] BYREF
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+48h] [rbp-18h] BYREF
  size_t pcbRemaining[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int pusResult; // [rsp+A8h] [rbp+48h] BYREF
  struct _UNICODE_STRING **v37; // [rsp+B8h] [rbp+58h]

  v37 = a4;
  v5 = a4;
  LODWORD(ppszDestEnd) = 0;
  if ( !a2 || a3 >= 5u )
    return 3221225485LL;
  v9 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = 128;
  if ( (unsigned __int16)(a3 - 3) > 1u )
    v10 = 256;
  for ( i = v10; ; v10 = i )
  {
    Pool2 = ExAllocatePool2(66, v10, 1097884741);
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    if ( *a1 )
    {
      SecurityAttributesToken = SeQuerySecurityAttributesToken(*a1, a2, 1, Pool2, i);
    }
    else
    {
      v13 = a1[2];
      SecurityAttributesToken = v13
                              ? SeQuerySecurityAttributesTokenAccessInformation(v13, a2, 1, Pool2)
                              : ZwQuerySecurityAttributesToken(a1[3], a2, 1, Pool2, i, &i);
    }
    FqbnString = SecurityAttributesToken;
    if ( SecurityAttributesToken >= 0 )
      break;
    if ( SecurityAttributesToken == -1073741275 )
    {
      FqbnString = 0;
      goto LABEL_59;
    }
    if ( SecurityAttributesToken != -1073741789 )
      goto LABEL_59;
    ExFreePoolWithTag((PVOID)Pool2, 0);
  }
  if ( !*(_DWORD *)(Pool2 + 4) )
    goto LABEL_59;
  v15 = *(_QWORD *)(Pool2 + 8);
  if ( !*(_DWORD *)(v15 + 24) )
    goto LABEL_59;
  v16 = *(const UNICODE_STRING **)(v15 + 32);
  if ( !v16 )
    goto LABEL_59;
  switch ( a3 )
  {
    case 0u:
      if ( v5 && *(_WORD *)(v15 + 16) == 3 )
      {
        FqbnString = CalcStringContiguousBufferSizeFromLength(v16->Length, &ppszDestEnd);
        if ( FqbnString >= 0 )
        {
          v17 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
          v18 = (struct _UNICODE_STRING *)v17;
          if ( !v17 )
          {
LABEL_27:
            FqbnString = -1073741801;
            goto LABEL_59;
          }
          v19 = (WCHAR *)(v17 + 16);
          v20 = v16->Length + 2;
          memset((void *)(v17 + 16), 0, v20);
          v18->MaximumLength = v20;
          v18->Length = 0;
          v18->Buffer = v19;
          RtlCopyUnicodeString(v18, v16);
          *v5 = v18;
LABEL_29:
          v9 = 0;
          goto LABEL_59;
        }
        goto LABEL_59;
      }
LABEL_58:
      FqbnString = -1073741811;
      goto LABEL_59;
    case 1u:
      if ( v5 && *(_WORD *)(v15 + 16) == 4 )
      {
        FqbnString = CreateFqbnString(*(__int64 **)(v15 + 32), v5);
        goto LABEL_59;
      }
      goto LABEL_58;
    case 3u:
      if ( *(_WORD *)(v15 + 16) != 2 )
        goto LABEL_58;
      v21 = a5;
      if ( !a5 )
        goto LABEL_58;
      Buffer = *(PWSTR *)&v16->Length;
LABEL_38:
      *v21 = Buffer;
      goto LABEL_59;
    case 4u:
      if ( *(_WORD *)(v15 + 16) != 2 )
        goto LABEL_58;
      v21 = a5;
      if ( !a5 )
        goto LABEL_58;
      Buffer = v16->Buffer;
      goto LABEL_38;
  }
  if ( a3 != 2 )
    goto LABEL_59;
  if ( *(_WORD *)(v15 + 16) != 16 || !v5 )
    goto LABEL_58;
  v23 = (unsigned int)v16->Buffer;
  if ( v23 > 0xFFFF || (v24 = 4 * (unsigned __int16)v23, v24 > 0xFFFF) )
  {
    FqbnString = -1073741675;
    goto LABEL_59;
  }
  LOWORD(pusResult) = 4 * v23;
  FqbnString = RtlUShortAdd(v24, 2u, (USHORT *)&pusResult);
  if ( FqbnString >= 0 )
  {
    FqbnString = CalcStringContiguousBufferSizeFromLength((unsigned __int16)pusResult, &ppszDestEnd);
    if ( FqbnString >= 0 )
    {
      v25 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
      v9 = (struct _UNICODE_STRING *)v25;
      if ( !v25 )
        goto LABEL_27;
      v26 = (unsigned __int16)pusResult;
      v27 = (wchar_t *)(v25 + 16);
      *(_QWORD *)(v25 + 8) = v25 + 16;
      *(_WORD *)(v25 + 2) = v26;
      ppszDestEnd = (NTSTRSAFE_PWSTR)(v25 + 16);
      v28 = v26;
      *(_WORD *)v25 = v26 - 2;
      memset((void *)(v25 + 16), 0, v26);
      v29 = LODWORD(v16->Buffer) == 0;
      pcbRemaining[0] = v28;
      pusResult = 0;
      if ( !v29 )
      {
        v30 = pusResult;
        while ( 1 )
        {
          LODWORD(v32) = *(unsigned __int8 *)(v30 + *(_QWORD *)&v16->Length);
          RtlStringCbPrintfExW(v27, v28, &ppszDestEnd, pcbRemaining, 0, L"%02x", v32);
          if ( ++v30 >= LODWORD(v16->Buffer) )
            break;
          v27 = ppszDestEnd;
          v28 = pcbRemaining[0];
        }
        v5 = v37;
      }
      *v5 = v9;
      goto LABEL_29;
    }
  }
LABEL_59:
  ExFreePoolWithTag((PVOID)Pool2, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)FqbnString;
}

```

## disassembly

```asm
0x140005d90  mov     [rsp-38h+arg_0], rbx
0x140005d95  mov     [rsp-38h+arg_18], r9
0x140005d9a  push    rbp
0x140005d9b  push    rsi
0x140005d9c  push    rdi
0x140005d9d  push    r12
0x140005d9f  push    r13
0x140005da1  push    r14
0x140005da3  push    r15
0x140005da5  mov     rbp, rsp
0x140005da8  sub     rsp, 60h
0x140005dac  xor     esi, esi
0x140005dae  mov     r15, r9
0x140005db1  mov     dword ptr [rbp+ppszDestEnd], esi
0x140005db4  movzx   r12d, r8w
0x140005db8  mov     rbx, rdx
0x140005dbb  mov     r14, rcx
0x140005dbe  test    rdx, rdx
0x140005dc1  jz      loc_14000617A
0x140005dc7  cmp     r8w, 5
0x140005dcc  jnb     loc_14000617A
0x140005dd2  mov     edi, esi
0x140005dd4  test    r9, r9
0x140005dd7  jz      short loc_140005DDC
0x140005dd9  mov     [r9], rsi
0x140005ddc  mov     ecx, 80h
0x140005de1  lea     eax, [r12-3]
0x140005de6  mov     edx, 100h
0x140005deb  lea     r8d, [rcx-7Fh]
0x140005def  cmp     ax, r8w
0x140005df3  cmova   ecx, edx
0x140005df6  mov     [rbp+var_20], ecx
0x140005df9  mov     edx, ecx
0x140005dfb  mov     r8d, 41706445h
0x140005e01  mov     ecx, 42h ; 'B'
0x140005e06  call    cs:__imp_ExAllocatePool2
0x140005e0d  nop     dword ptr [rax+rax+00h]
0x140005e12  mov     r13, rax
0x140005e15  test    rax, rax
0x140005e18  jz      loc_140006171
0x140005e1e  mov     rcx, [r14]
0x140005e21  lea     rax, [rbp+var_20]
0x140005e25  mov     [rsp+60h+pszFormat], rax
0x140005e2a  mov     r9, r13
0x140005e2d  mov     r8d, 1
0x140005e33  test    rcx, rcx
0x140005e36  jz      short loc_140005E50
0x140005e38  mov     edx, [rbp+var_20]
0x140005e3b  mov     [rsp+60h+dwFlags], edx
0x140005e3f  mov     rdx, rbx
0x140005e42  call    cs:__imp_SeQuerySecurityAttributesToken
0x140005e49  nop     dword ptr [rax+rax+00h]
0x140005e4e  jmp     short loc_140005E81
0x140005e50  mov     rcx, [r14+10h]
0x140005e54  mov     rdx, rbx
0x140005e57  mov     eax, [rbp+var_20]
0x140005e5a  mov     [rsp+60h+dwFlags], eax
0x140005e5e  test    rcx, rcx
0x140005e61  jz      short loc_140005E71
0x140005e63  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x140005e6a  nop     dword ptr [rax+rax+00h]
0x140005e6f  jmp     short loc_140005E81
0x140005e71  mov     rcx, [r14+18h]
0x140005e75  call    cs:__imp_ZwQuerySecurityAttributesToken
0x140005e7c  nop     dword ptr [rax+rax+00h]
0x140005e81  xor     r10d, r10d
0x140005e84  mov     esi, eax
0x140005e86  test    eax, eax
0x140005e88  jns     short loc_140005EBD
0x140005e8a  cmp     eax, 0C0000225h
0x140005e8f  jz      short loc_140005EB5
0x140005e91  cmp     eax, 0C0000023h
0x140005e96  jnz     loc_140006148
0x140005e9c  xor     edx, edx; Tag
0x140005e9e  mov     rcx, r13; P
0x140005ea1  call    cs:__imp_ExFreePoolWithTag
0x140005ea8  nop     dword ptr [rax+rax+00h]
0x140005ead  mov     ecx, [rbp+var_20]
0x140005eb0  jmp     loc_140005DF9
0x140005eb5  mov     esi, r10d
0x140005eb8  jmp     loc_140006148
0x140005ebd  cmp     [r13+4], r10d
0x140005ec1  jz      loc_140006148
0x140005ec7  mov     rax, [r13+8]
0x140005ecb  cmp     [rax+18h], r10d
0x140005ecf  jz      loc_140006148
0x140005ed5  mov     r14, [rax+20h]
0x140005ed9  test    r14, r14
0x140005edc  jz      loc_140006148
0x140005ee2  test    r12w, r12w
0x140005ee6  jnz     loc_140005F8D
0x140005eec  test    r15, r15
0x140005eef  jz      loc_140006143
0x140005ef5  cmp     word ptr [rax+10h], 3
0x140005efa  jnz     loc_140006143
0x140005f00  movzx   ecx, word ptr [r14]
0x140005f04  lea     rdx, [rbp+ppszDestEnd]
0x140005f08  call    CalcStringContiguousBufferSizeFromLength
0x140005f0d  mov     esi, eax
0x140005f0f  test    eax, eax
0x140005f11  js      loc_140006148
0x140005f17  mov     edx, dword ptr [rbp+ppszDestEnd]
0x140005f1a  mov     ecx, 42h ; 'B'
0x140005f1f  mov     r8d, 41706445h
0x140005f25  call    cs:__imp_ExAllocatePool2
0x140005f2c  nop     dword ptr [rax+rax+00h]
0x140005f31  mov     r12, rax
0x140005f34  test    rax, rax
0x140005f37  jnz     short loc_140005F43
0x140005f39  mov     esi, 0C0000017h
0x140005f3e  jmp     loc_140006148
0x140005f43  lea     rdi, [rax+10h]
0x140005f47  xor     edx, edx; Val
0x140005f49  movzx   eax, word ptr [r14]
0x140005f4d  mov     rcx, rdi; void *
0x140005f50  add     ax, 2
0x140005f54  movzx   ebx, ax
0x140005f57  mov     r8d, ebx; Size
0x140005f5a  call    memset
0x140005f5f  xor     eax, eax
0x140005f61  mov     [r12+2], bx
0x140005f67  mov     rdx, r14; SourceString
0x140005f6a  mov     [r12], ax
0x140005f6f  mov     rcx, r12; DestinationString
0x140005f72  mov     [r12+8], rdi
0x140005f77  call    cs:__imp_RtlCopyUnicodeString
0x140005f7e  nop     dword ptr [rax+rax+00h]
0x140005f83  mov     [r15], r12
0x140005f86  xor     edi, edi
0x140005f88  jmp     loc_140006148
0x140005f8d  mov     ecx, 1
0x140005f92  cmp     r12w, cx
0x140005f96  jnz     short loc_140005FBE
0x140005f98  test    r15, r15
0x140005f9b  jz      loc_140006143
0x140005fa1  cmp     word ptr [rax+10h], 4
0x140005fa6  jnz     loc_140006143
0x140005fac  mov     rdx, r15
0x140005faf  mov     rcx, r14
0x140005fb2  call    CreateFqbnString
0x140005fb7  mov     esi, eax
0x140005fb9  jmp     loc_140006148
0x140005fbe  mov     ebx, 2
0x140005fc3  cmp     r12w, 3
0x140005fc8  jnz     short loc_140005FEC
0x140005fca  cmp     [rax+10h], bx
0x140005fce  jnz     loc_140006143
0x140005fd4  mov     rcx, [rbp+arg_20]
0x140005fd8  test    rcx, rcx
0x140005fdb  jz      loc_140006143
0x140005fe1  mov     rax, [r14]
0x140005fe4  mov     [rcx], rax
0x140005fe7  jmp     loc_140006148
0x140005fec  cmp     r12w, 4
0x140005ff1  jnz     short loc_140006010
0x140005ff3  cmp     [rax+10h], bx
0x140005ff7  jnz     loc_140006143
0x140005ffd  mov     rcx, [rbp+arg_20]
0x140006001  test    rcx, rcx
0x140006004  jz      loc_140006143
0x14000600a  mov     rax, [r14+8]
0x14000600e  jmp     short loc_140005FE4
0x140006010  cmp     r12w, bx
0x140006014  jnz     loc_140006148
0x14000601a  cmp     word ptr [rax+10h], 10h
0x14000601f  jnz     loc_140006143
0x140006025  test    r15, r15
0x140006028  jz      loc_140006143
0x14000602e  mov     eax, [r14+8]
0x140006032  mov     edx, 0FFFFh
0x140006037  cmp     eax, edx
0x140006039  ja      loc_14000613C
0x14000603f  movzx   ecx, ax
0x140006042  shl     ecx, 2; usAugend
0x140006045  cmp     ecx, edx
0x140006047  ja      loc_14000613C
0x14000604d  mov     edx, ebx; usAddend
0x14000604f  mov     word ptr [rbp+pusResult], cx
0x140006053  lea     r8, [rbp+pusResult]; pusResult
0x140006057  call    RtlUShortAdd
0x14000605c  mov     esi, eax
0x14000605e  test    eax, eax
0x140006060  js      loc_140006148
0x140006066  movzx   ecx, word ptr [rbp+pusResult]
0x14000606a  lea     rdx, [rbp+ppszDestEnd]
0x14000606e  call    CalcStringContiguousBufferSizeFromLength
0x140006073  mov     esi, eax
0x140006075  test    eax, eax
0x140006077  js      loc_140006148
0x14000607d  mov     edx, dword ptr [rbp+ppszDestEnd]
0x140006080  mov     ecx, 42h ; 'B'
0x140006085  mov     r8d, 41706445h
0x14000608b  call    cs:__imp_ExAllocatePool2
0x140006092  nop     dword ptr [rax+rax+00h]
0x140006097  mov     rdi, rax
0x14000609a  test    rax, rax
0x14000609d  jz      loc_140005F39
0x1400060a3  movzx   ecx, word ptr [rbp+pusResult]
0x1400060a7  lea     r12, [rax+10h]
0x1400060ab  mov     [rax+8], r12
0x1400060af  mov     r8d, ecx; Size
0x1400060b2  movzx   eax, cx
0x1400060b5  mov     [rdi+2], cx
0x1400060b9  sub     ax, bx
0x1400060bc  mov     [rbp+ppszDestEnd], r12
0x1400060c0  mov     ebx, ecx
0x1400060c2  mov     [rdi], ax
0x1400060c5  mov     rcx, r12; void *
0x1400060c8  xor     edx, edx; Val
0x1400060ca  call    memset
0x1400060cf  cmp     dword ptr [r14+8], 0
0x1400060d4  mov     [rbp+pcbRemaining], rbx
0x1400060d8  mov     [rbp+pusResult], 0
0x1400060df  jbe     short loc_140006134
0x1400060e1  mov     r15d, [rbp+pusResult]
0x1400060e5  mov     rax, [r14]
0x1400060e8  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1400060ec  mov     r8d, r15d
0x1400060ef  mov     rdx, rbx; cbDest
0x1400060f2  mov     rcx, r12; pszDest
0x1400060f5  movzx   r8d, byte ptr [r8+rax]
0x1400060fa  lea     rax, a02x; "%02x"
0x140006101  mov     [rsp+60h+var_30], r8d
0x140006106  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x14000610a  mov     [rsp+60h+pszFormat], rax; pszFormat
0x14000610f  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x140006118  call    RtlStringCbPrintfExW
0x14000611d  inc     r15d
0x140006120  cmp     r15d, [r14+8]
0x140006124  jnb     short loc_140006130
0x140006126  mov     r12, [rbp+ppszDestEnd]
0x14000612a  mov     rbx, [rbp+pcbRemaining]
0x14000612e  jmp     short loc_1400060E5
0x140006130  mov     r15, [rbp+arg_18]
0x140006134  mov     [r15], rdi
0x140006137  jmp     loc_140005F86
0x14000613c  mov     esi, 0C0000095h
0x140006141  jmp     short loc_140006148
0x140006143  mov     esi, 0C000000Dh
0x140006148  xor     edx, edx; Tag
0x14000614a  mov     rcx, r13; P
0x14000614d  call    cs:__imp_ExFreePoolWithTag
0x140006154  nop     dword ptr [rax+rax+00h]
0x140006159  test    rdi, rdi
0x14000615c  jz      short loc_140006176
0x14000615e  xor     edx, edx; Tag
0x140006160  mov     rcx, rdi; P
0x140006163  call    cs:__imp_ExFreePoolWithTag
0x14000616a  nop     dword ptr [rax+rax+00h]
0x14000616f  jmp     short loc_140006176
0x140006171  mov     esi, 0C0000017h
0x140006176  mov     eax, esi
0x140006178  jmp     short loc_14000617F
0x14000617a  mov     eax, 0C000000Dh
0x14000617f  mov     rbx, [rsp+60h+arg_0]
0x140006187  add     rsp, 60h
0x14000618b  pop     r15
0x14000618d  pop     r14
0x14000618f  pop     r13
0x140006191  pop     r12
0x140006193  pop     rdi
0x140006194  pop     rsi
0x140006195  pop     rbp
0x140006196  retn
```
