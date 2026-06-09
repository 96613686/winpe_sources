# AiConvertFullImagePathToMacroFormat

- ea: `0x140037ac0`
- end: `0x140037e8b`
- name: `AiConvertFullImagePathToMacroFormat`
- size: `971`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, const UNICODE_STRING *, __int128 *, PCUNICODE_STRING, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1400333b0`

## callees

- `0x140006a20`
- `0x140006c40`
- `0x140032a50`
- `0x140035990`
- `0x140035fb0`
- `0x1400365f0`
- `0x140037ac0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140037d5f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140037d5f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140037b3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140037b88`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140037b3a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140037b88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e5e`
- `ntoskrnl!ExAllocatePool2` at `0x140037b14`
- `ntoskrnl!ExAllocatePool2` at `0x140037c73`
- `ntoskrnl!ExAllocatePool2` at `0x140037da4`
- `ntoskrnl!ExAllocatePool2` at `0x140037b14`
- `ntoskrnl!ExAllocatePool2` at `0x140037c73`
- `ntoskrnl!ExAllocatePool2` at `0x140037da4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037bf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037c0e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037bf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037c0e`

## pseudocode

```c
__int64 __fastcall AiConvertFullImagePathToMacroFormat(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        __int128 *a4,
        PCUNICODE_STRING a5,
        int a6,
        int a7)
{
  __int64 MaximumLength; // rdx
  int v12; // edi
  PWSTR Buffer; // rcx
  unsigned int i; // ebx
  __int64 v15; // rax
  const void **v16; // r14
  unsigned __int16 *v17; // rdi
  unsigned int v18; // r8d
  WCHAR *Pool2; // rax
  __int64 v20; // rbx
  UNICODE_STRING *v21; // rcx
  unsigned int Length; // eax
  WCHAR v23; // dx
  unsigned int v24; // edx
  WCHAR *v25; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-60h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-50h] BYREF
  __int128 v29; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING v30; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING v31; // [rsp+60h] [rbp-20h] BYREF

  MaximumLength = a2->MaximumLength;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.MaximumLength = MaximumLength;
  String1 = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, MaximumLength, 1145663553);
  if ( !DestinationString.Buffer )
    return (unsigned int)-1073741801;
  RtlCopyUnicodeString(&DestinationString, a2);
  v12 = AiAddImagePathWithMacro(a1, &DestinationString);
  if ( v12 < 0 )
  {
LABEL_4:
    Buffer = DestinationString.Buffer;
    goto LABEL_45;
  }
  if ( a3 && a3 != a2 )
  {
    DestinationString.MaximumLength = a3->MaximumLength;
    DestinationString.Buffer = (PWSTR)AiAlloc(DestinationString.MaximumLength);
    if ( !DestinationString.Buffer )
      return (unsigned int)-1073741801;
    RtlCopyUnicodeString(&DestinationString, a3);
    v12 = AiAddImagePathWithMacro(a1, &DestinationString);
    if ( v12 < 0 )
    {
      Buffer = DestinationString.Buffer;
LABEL_45:
      if ( Buffer )
        ExFreePoolWithTag(Buffer, 0);
      return (unsigned int)v12;
    }
  }
  if ( a5->Buffer && (unsigned int)AipIsPathMacroPrefix(a2, a5) )
  {
    v30 = 0;
    v31 = 0;
    v29 = *a4;
    if ( a6 )
      RtlInitUnicodeString(&v30, L"%REMOVABLE%");
    if ( a7 )
      RtlInitUnicodeString(&v31, L"%HOT%");
    for ( i = 0; i < 3; ++i )
    {
      v15 = 16LL * i;
      v16 = (const void **)((char *)&v29 + v15 + 8);
      if ( *(_QWORD *)((char *)&v29 + v15 + 8) )
      {
        v17 = (unsigned __int16 *)((char *)&v29 + v15);
        v18 = a2->Length + *(unsigned __int16 *)((char *)&v29 + v15) - a5->Length;
        if ( v18 > 0xFFFE )
          return (unsigned int)-1073741562;
        DestinationString.Length = a2->Length + *(_WORD *)((char *)&v29 + v15) - a5->Length;
        DestinationString.MaximumLength = v18;
        Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)v18, 1145663553);
        DestinationString.Buffer = Pool2;
        if ( !Pool2 )
          return (unsigned int)-1073741801;
        memmove(Pool2, *v16, *v17);
        memmove(
          (char *)DestinationString.Buffer + *v17,
          (char *)a2->Buffer + a5->Length,
          a2->Length - (unsigned __int64)a5->Length);
        v12 = AiAddImagePathWithMacro(a1, &DestinationString);
        if ( v12 < 0 )
          goto LABEL_4;
      }
    }
  }
  v20 = qword_1400195B8;
  if ( (__int64 *)qword_1400195B8 == &qword_1400195B8 )
    return (unsigned int)v12;
  while ( 1 )
  {
    v21 = (UNICODE_STRING *)(v20 + 40);
    if ( (*(_DWORD *)(v20 + 16) & 8) != 0 )
    {
      String1 = *v21;
    }
    else
    {
      v12 = AipConvertToNtPath(v21, &String1);
      if ( v12 < 0 )
        return (unsigned int)v12;
    }
    Length = a2->Length;
    if ( (unsigned __int16)Length < String1.Length )
      goto LABEL_38;
    if ( Length > (unsigned int)String1.Length + 1 )
    {
      v23 = a2->Buffer[(unsigned __int64)String1.Length >> 1];
      if ( v23 != 92 )
      {
        if ( v23 )
          goto LABEL_38;
      }
    }
    if ( !RtlPrefixUnicodeString(&String1, a2, 1u) )
      goto LABEL_38;
    v24 = a2->Length + *(unsigned __int16 *)(v20 + 24) - String1.Length;
    if ( v24 > 0xFFFE )
      break;
    DestinationString.Length = a2->Length + *(_WORD *)(v20 + 24) - String1.Length;
    DestinationString.MaximumLength = v24;
    v25 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)v24, 1145663553);
    DestinationString.Buffer = v25;
    if ( v25 )
    {
      memmove(v25, *(const void **)(v20 + 32), *(unsigned __int16 *)(v20 + 24));
      memmove(
        (char *)DestinationString.Buffer + *(unsigned __int16 *)(v20 + 24),
        (char *)a2->Buffer + String1.Length,
        a2->Length - (unsigned __int64)String1.Length);
      v12 = AiAddImagePathWithMacro(a1, &DestinationString);
      if ( v12 < 0 && DestinationString.Buffer )
        ExFreePoolWithTag(DestinationString.Buffer, 0);
    }
    else
    {
      v12 = -1073741801;
    }
LABEL_38:
    if ( String1.Buffer != *(PWSTR *)(v20 + 48) && String1.Buffer )
      ExFreePoolWithTag(String1.Buffer, 0);
    if ( v12 >= 0 )
    {
      v20 = *(_QWORD *)v20;
      if ( (__int64 *)v20 != &qword_1400195B8 )
        continue;
    }
    return (unsigned int)v12;
  }
  Buffer = String1.Buffer;
  v12 = -1073741562;
  if ( String1.Buffer != *(PWSTR *)(v20 + 48) )
    goto LABEL_45;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140037ac0  push    rbp
0x140037ac2  push    rbx
0x140037ac3  push    rsi
0x140037ac4  push    rdi
0x140037ac5  push    r12
0x140037ac7  push    r14
0x140037ac9  push    r15
0x140037acb  mov     rbp, rsp
0x140037ace  sub     rsp, 80h
0x140037ad5  mov     rax, cs:__security_cookie
0x140037adc  xor     rax, rsp
0x140037adf  mov     [rbp+var_10], rax
0x140037ae3  mov     r15, [rbp+arg_20]
0x140037ae7  mov     rsi, rdx
0x140037aea  movzx   edx, word ptr [rdx+2]
0x140037aee  xorps   xmm1, xmm1
0x140037af1  mov     rbx, r8
0x140037af4  mov     r12, rcx
0x140037af7  xorps   xmm0, xmm0
0x140037afa  mov     ecx, 102h
0x140037aff  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140037b03  mov     r8d, 44497041h
0x140037b09  mov     [rbp+DestinationString.MaximumLength], dx
0x140037b0d  mov     r14, r9
0x140037b10  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140037b14  call    cs:__imp_ExAllocatePool2
0x140037b1b  nop     dword ptr [rax+rax+00h]
0x140037b20  mov     [rbp+DestinationString.Buffer], rax
0x140037b24  test    rax, rax
0x140037b27  jnz     short loc_140037B33
0x140037b29  mov     edi, 0C0000017h
0x140037b2e  jmp     loc_140037E6A
0x140037b33  mov     rdx, rsi; SourceString
0x140037b36  lea     rcx, [rbp+DestinationString]; DestinationString
0x140037b3a  call    cs:__imp_RtlCopyUnicodeString
0x140037b41  nop     dword ptr [rax+rax+00h]
0x140037b46  lea     rdx, [rbp+DestinationString]
0x140037b4a  mov     rcx, r12
0x140037b4d  call    AiAddImagePathWithMacro
0x140037b52  mov     edi, eax
0x140037b54  test    eax, eax
0x140037b56  jns     short loc_140037B61
0x140037b58  mov     rcx, [rbp+DestinationString.Buffer]
0x140037b5c  jmp     loc_140037E57
0x140037b61  test    rbx, rbx
0x140037b64  jz      short loc_140037BAF
0x140037b66  cmp     rbx, rsi
0x140037b69  jz      short loc_140037BAF
0x140037b6b  movzx   ecx, word ptr [rbx+2]
0x140037b6f  mov     [rbp+DestinationString.MaximumLength], cx
0x140037b73  call    AiAlloc
0x140037b78  mov     [rbp+DestinationString.Buffer], rax
0x140037b7c  test    rax, rax
0x140037b7f  jz      short loc_140037B29
0x140037b81  mov     rdx, rbx; SourceString
0x140037b84  lea     rcx, [rbp+DestinationString]; DestinationString
0x140037b88  call    cs:__imp_RtlCopyUnicodeString
0x140037b8f  nop     dword ptr [rax+rax+00h]
0x140037b94  lea     rdx, [rbp+DestinationString]
0x140037b98  mov     rcx, r12
0x140037b9b  call    AiAddImagePathWithMacro
0x140037ba0  mov     edi, eax
0x140037ba2  test    eax, eax
0x140037ba4  jns     short loc_140037BAF
0x140037ba6  mov     rcx, [rbp+DestinationString.Buffer]
0x140037baa  jmp     loc_140037E57
0x140037baf  cmp     qword ptr [r15+8], 0
0x140037bb4  jz      loc_140037CDA
0x140037bba  mov     rdx, r15; String1
0x140037bbd  mov     rcx, rsi; String2
0x140037bc0  call    AipIsPathMacroPrefix
0x140037bc5  test    eax, eax
0x140037bc7  jz      loc_140037CDA
0x140037bcd  cmp     [rbp+arg_28], 0
0x140037bd1  xorps   xmm0, xmm0
0x140037bd4  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140037bd8  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140037bdc  movups  xmm0, xmmword ptr [r14]
0x140037be0  movups  [rbp+var_40], xmm0
0x140037be4  jz      short loc_140037BFD
0x140037be6  lea     rdx, aRemovable; "%REMOVABLE%"
0x140037bed  lea     rcx, [rbp+var_30]; DestinationString
0x140037bf1  call    cs:__imp_RtlInitUnicodeString
0x140037bf8  nop     dword ptr [rax+rax+00h]
0x140037bfd  cmp     [rbp+arg_30], 0
0x140037c01  jz      short loc_140037C1A
0x140037c03  lea     rdx, aHot; "%HOT%"
0x140037c0a  lea     rcx, [rbp+var_20]; DestinationString
0x140037c0e  call    cs:__imp_RtlInitUnicodeString
0x140037c15  nop     dword ptr [rax+rax+00h]
0x140037c1a  xor     ebx, ebx
0x140037c1c  nop     dword ptr [rax+00h]
0x140037c20  mov     eax, ebx
0x140037c22  lea     r14, [rbp+var_40+8]
0x140037c26  shl     rax, 4
0x140037c2a  add     r14, rax
0x140037c2d  cmp     qword ptr [r14], 0
0x140037c31  jz      loc_140037CCF
0x140037c37  lea     rdi, [rbp+var_40]
0x140037c3b  add     rdi, rax
0x140037c3e  movzx   eax, word ptr [r15]
0x140037c42  movzx   r8d, word ptr [rdi]
0x140037c46  sub     r8d, eax
0x140037c49  movzx   eax, word ptr [rsi]
0x140037c4c  add     r8d, eax
0x140037c4f  cmp     r8d, 0FFFEh
0x140037c56  ja      loc_140037D05
0x140037c5c  movzx   edx, r8w
0x140037c60  mov     ecx, 102h
0x140037c65  mov     r8d, 44497041h
0x140037c6b  mov     [rbp+DestinationString.Length], dx
0x140037c6f  mov     [rbp+DestinationString.MaximumLength], dx
0x140037c73  call    cs:__imp_ExAllocatePool2
0x140037c7a  nop     dword ptr [rax+rax+00h]
0x140037c7f  mov     [rbp+DestinationString.Buffer], rax
0x140037c83  test    rax, rax
0x140037c86  jz      loc_140037B29
0x140037c8c  movzx   r8d, word ptr [rdi]; Size
0x140037c90  mov     rcx, rax; void *
0x140037c93  mov     rdx, [r14]; Src
0x140037c96  call    memmove
0x140037c9b  movzx   ecx, word ptr [r15]
0x140037c9f  movzx   r8d, word ptr [rsi]
0x140037ca3  mov     rdx, [rsi+8]
0x140037ca7  sub     r8, rcx; Size
0x140037caa  add     rdx, rcx; Src
0x140037cad  movzx   ecx, word ptr [rdi]
0x140037cb0  add     rcx, [rbp+DestinationString.Buffer]; void *
0x140037cb4  call    memmove
0x140037cb9  lea     rdx, [rbp+DestinationString]
0x140037cbd  mov     rcx, r12
0x140037cc0  call    AiAddImagePathWithMacro
0x140037cc5  mov     edi, eax
0x140037cc7  test    eax, eax
0x140037cc9  js      loc_140037B58
0x140037ccf  inc     ebx
0x140037cd1  cmp     ebx, 3
0x140037cd4  jb      loc_140037C20
0x140037cda  mov     rbx, cs:qword_1400195B8
0x140037ce1  lea     r14, qword_1400195B8
0x140037ce8  cmp     rbx, r14
0x140037ceb  jz      loc_140037E6A
0x140037cf1  mov     eax, [rbx+10h]
0x140037cf4  lea     rcx, [rbx+28h]
0x140037cf8  test    al, 8
0x140037cfa  jz      short loc_140037D0F
0x140037cfc  movups  xmm0, xmmword ptr [rcx]
0x140037cff  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140037d03  jmp     short loc_140037D22
0x140037d05  mov     edi, 0C0000106h
0x140037d0a  jmp     loc_140037E6A
0x140037d0f  lea     rdx, [rbp+String1]
0x140037d13  call    AipConvertToNtPath
0x140037d18  mov     edi, eax
0x140037d1a  test    eax, eax
0x140037d1c  js      loc_140037E6A
0x140037d22  movzx   eax, word ptr [rsi]
0x140037d25  movzx   edx, [rbp+String1.Length]
0x140037d29  cmp     ax, dx
0x140037d2c  jb      loc_140037E19
0x140037d32  lea     ecx, [rdx+1]
0x140037d35  cmp     eax, ecx
0x140037d37  jbe     short loc_140037D55
0x140037d39  mov     rax, [rsi+8]
0x140037d3d  mov     ecx, edx
0x140037d3f  shr     rcx, 1
0x140037d42  movzx   edx, word ptr [rax+rcx*2]
0x140037d46  cmp     dx, 5Ch ; '\'
0x140037d4a  jz      short loc_140037D55
0x140037d4c  test    dx, dx
0x140037d4f  jnz     loc_140037E19
0x140037d55  mov     r8b, 1; CaseInSensitive
0x140037d58  lea     rcx, [rbp+String1]; String1
0x140037d5c  mov     rdx, rsi; String2
0x140037d5f  call    cs:__imp_RtlPrefixUnicodeString
0x140037d66  nop     dword ptr [rax+rax+00h]
0x140037d6b  test    al, al
0x140037d6d  jz      loc_140037E19
0x140037d73  movzx   eax, [rbp+String1.Length]
0x140037d77  movzx   edx, word ptr [rbx+18h]
0x140037d7b  sub     edx, eax
0x140037d7d  movzx   eax, word ptr [rsi]
0x140037d80  add     edx, eax
0x140037d82  cmp     edx, 0FFFEh
0x140037d88  ja      loc_140037E48
0x140037d8e  movzx   edx, dx
0x140037d91  mov     ecx, 102h
0x140037d96  mov     r8d, 44497041h
0x140037d9c  mov     [rbp+DestinationString.Length], dx
0x140037da0  mov     [rbp+DestinationString.MaximumLength], dx
0x140037da4  call    cs:__imp_ExAllocatePool2
0x140037dab  nop     dword ptr [rax+rax+00h]
0x140037db0  mov     [rbp+DestinationString.Buffer], rax
0x140037db4  test    rax, rax
0x140037db7  jz      short loc_140037E14
0x140037db9  movzx   r8d, word ptr [rbx+18h]; Size
0x140037dbe  mov     rcx, rax; void *
0x140037dc1  mov     rdx, [rbx+20h]; Src
0x140037dc5  call    memmove
0x140037dca  movzx   ecx, [rbp+String1.Length]
0x140037dce  movzx   r8d, word ptr [rsi]
0x140037dd2  mov     rdx, [rsi+8]
0x140037dd6  sub     r8, rcx; Size
0x140037dd9  add     rdx, rcx; Src
0x140037ddc  movzx   ecx, word ptr [rbx+18h]
0x140037de0  add     rcx, [rbp+DestinationString.Buffer]; void *
0x140037de4  call    memmove
0x140037de9  lea     rdx, [rbp+DestinationString]
0x140037ded  mov     rcx, r12
0x140037df0  call    AiAddImagePathWithMacro
0x140037df5  mov     edi, eax
0x140037df7  test    eax, eax
0x140037df9  jns     short loc_140037E19
0x140037dfb  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140037dff  test    rcx, rcx
0x140037e02  jz      short loc_140037E19
0x140037e04  xor     edx, edx; Tag
0x140037e06  call    cs:__imp_ExFreePoolWithTag
0x140037e0d  nop     dword ptr [rax+rax+00h]
0x140037e12  jmp     short loc_140037E19
0x140037e14  mov     edi, 0C0000017h
0x140037e19  mov     rcx, [rbp+String1.Buffer]; P
0x140037e1d  cmp     rcx, [rbx+30h]
0x140037e21  jz      short loc_140037E36
0x140037e23  test    rcx, rcx
0x140037e26  jz      short loc_140037E36
0x140037e28  xor     edx, edx; Tag
0x140037e2a  call    cs:__imp_ExFreePoolWithTag
0x140037e31  nop     dword ptr [rax+rax+00h]
0x140037e36  test    edi, edi
0x140037e38  js      short loc_140037E6A
0x140037e3a  mov     rbx, [rbx]
0x140037e3d  cmp     rbx, r14
0x140037e40  jnz     loc_140037CF1
0x140037e46  jmp     short loc_140037E6A
0x140037e48  mov     rcx, [rbp+String1.Buffer]; P
0x140037e4c  mov     edi, 0C0000106h
0x140037e51  cmp     rcx, [rbx+30h]
0x140037e55  jz      short loc_140037E6A
0x140037e57  test    rcx, rcx
0x140037e5a  jz      short loc_140037E6A
0x140037e5c  xor     edx, edx; Tag
0x140037e5e  call    cs:__imp_ExFreePoolWithTag
0x140037e65  nop     dword ptr [rax+rax+00h]
0x140037e6a  mov     eax, edi
0x140037e6c  mov     rcx, [rbp+var_10]
0x140037e70  xor     rcx, rsp; StackCookie
0x140037e73  call    __security_check_cookie
0x140037e78  add     rsp, 80h
0x140037e7f  pop     r15
0x140037e81  pop     r14
0x140037e83  pop     r12
0x140037e85  pop     rdi
0x140037e86  pop     rsi
0x140037e87  pop     rbx
0x140037e88  pop     rbp
0x140037e89  retn
```
