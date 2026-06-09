# AiConvertFullImagePathToMacroFormat

- ea: `0x18000423c`
- end: `0x18000457c`
- name: `AiConvertFullImagePathToMacroFormat`
- size: `832`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800061c8`

## callees

- `0x180003fd4`
- `0x18000423c`
- `0x180004f4c`
- `0x180005594`
- `0x180005b70`
- `0x180009562`
- `0x1800095c0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x1800042a4`
- `ntdll!RtlCopyUnicodeString` at `0x1800042f5`
- `ntdll!RtlCopyUnicodeString` at `0x1800042a4`
- `ntdll!RtlCopyUnicodeString` at `0x1800042f5`
- `ntdll!RtlFreeHeap` at `0x1800044f2`
- `ntdll!RtlFreeHeap` at `0x18000451c`
- `ntdll!RtlFreeHeap` at `0x180004556`
- `ntdll!RtlFreeHeap` at `0x1800044f2`
- `ntdll!RtlFreeHeap` at `0x18000451c`
- `ntdll!RtlFreeHeap` at `0x180004556`
- `ntdll!RtlInitUnicodeString` at `0x180004350`
- `ntdll!RtlInitUnicodeString` at `0x180004367`
- `ntdll!RtlInitUnicodeString` at `0x180004350`
- `ntdll!RtlInitUnicodeString` at `0x180004367`

## pseudocode

```c
__int64 __fastcall AiConvertFullImagePathToMacroFormat(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        _OWORD *a4,
        PCUNICODE_STRING String1,
        int a6,
        int a7)
{
  __int64 MaximumLength; // rcx
  int v12; // ebx
  struct _PEB *v13; // rcx
  PWSTR Buffer; // r8
  unsigned int i; // r14d
  int Length; // eax
  unsigned int v17; // edx
  WCHAR *v18; // rax
  PVOID *j; // rdi
  struct _UNICODE_STRING *v20; // rcx
  int v21; // eax
  unsigned int v22; // edx
  WCHAR *v23; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-60h] BYREF
  PVOID P[2]; // [rsp+30h] [rbp-50h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-40h]
  struct _UNICODE_STRING v28; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING v29; // [rsp+60h] [rbp-20h] BYREF

  MaximumLength = a2->MaximumLength;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.MaximumLength = MaximumLength;
  *(_OWORD *)P = 0;
  DestinationString.Buffer = (PWSTR)AiAlloc(MaximumLength);
  if ( !DestinationString.Buffer )
    return (unsigned int)-1073741801;
  RtlCopyUnicodeString(&DestinationString, a2);
  v12 = AiAddImagePathWithMacro(a1, &DestinationString);
  if ( v12 < 0 )
    goto LABEL_4;
  if ( !a3 || a3 == a2 )
    goto LABEL_44;
  DestinationString.MaximumLength = a3->MaximumLength;
  DestinationString.Buffer = (PWSTR)AiAlloc(DestinationString.MaximumLength);
  if ( !DestinationString.Buffer )
    return (unsigned int)-1073741801;
  RtlCopyUnicodeString(&DestinationString, a3);
  v12 = AiAddImagePathWithMacro(a1, &DestinationString);
  if ( v12 < 0 )
  {
LABEL_4:
    v13 = NtCurrentPeb();
    Buffer = DestinationString.Buffer;
LABEL_40:
    RtlFreeHeap(v13->ProcessHeap, 0, Buffer);
  }
  else
  {
LABEL_44:
    if ( String1->Buffer && (unsigned int)AipIsPathMacroPrefix(a2, String1) )
    {
      v28 = 0;
      v29 = 0;
      *(_OWORD *)Src = *a4;
      if ( a6 )
        RtlInitUnicodeString(&v28, L"%REMOVABLE%");
      if ( a7 )
        RtlInitUnicodeString(&v29, L"%HOT%");
      for ( i = 0; i < 3; ++i )
      {
        if ( Src[2 * i + 1] )
        {
          Length = a2->Length;
          v17 = Length + LOWORD(Src[2 * i]) - String1->Length;
          if ( v17 > 0xFFFE )
            return (unsigned int)-1073741562;
          DestinationString.Length = Length + LOWORD(Src[2 * i]) - String1->Length;
          DestinationString.MaximumLength = v17;
          v18 = (WCHAR *)AiAlloc(DestinationString.Length);
          DestinationString.Buffer = v18;
          if ( !v18 )
            return (unsigned int)-1073741801;
          memcpy_0(v18, Src[2 * i + 1], LOWORD(Src[2 * i]));
          memcpy_0(
            (char *)DestinationString.Buffer + LOWORD(Src[2 * i]),
            (char *)a2->Buffer + String1->Length,
            a2->Length - (unsigned __int64)String1->Length);
          v12 = AiAddImagePathWithMacro(a1, &DestinationString);
          if ( v12 < 0 )
            goto LABEL_4;
        }
      }
    }
    for ( j = (PVOID *)::P; j != &::P; j = (PVOID *)*j )
    {
      v20 = (struct _UNICODE_STRING *)(j + 5);
      if ( ((_BYTE)j[2] & 8) != 0 )
      {
        *(struct _UNICODE_STRING *)P = *v20;
      }
      else
      {
        v12 = AipConvertToNtPath(v20, (struct _UNICODE_STRING *)P);
        if ( v12 < 0 )
          return (unsigned int)v12;
      }
      if ( (unsigned int)AipIsPathMacroPrefix(a2, (PCUNICODE_STRING)P) )
      {
        v21 = a2->Length;
        v22 = v21 + *((unsigned __int16 *)j + 12) - LOWORD(P[0]);
        if ( v22 > 0xFFFE )
        {
          v12 = -1073741562;
          if ( P[1] == j[6] )
            return (unsigned int)v12;
          v13 = NtCurrentPeb();
          Buffer = (PWSTR)P[1];
          goto LABEL_40;
        }
        DestinationString.Length = v21 + *((_WORD *)j + 12) - LOWORD(P[0]);
        DestinationString.MaximumLength = v22;
        v23 = (WCHAR *)AiAlloc(DestinationString.Length);
        DestinationString.Buffer = v23;
        if ( v23 )
        {
          memcpy_0(v23, j[4], *((unsigned __int16 *)j + 12));
          memcpy_0(
            (char *)DestinationString.Buffer + *((unsigned __int16 *)j + 12),
            (char *)a2->Buffer + LOWORD(P[0]),
            a2->Length - (unsigned __int64)LOWORD(P[0]));
          v12 = AiAddImagePathWithMacro(a1, &DestinationString);
          if ( v12 < 0 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
        }
        else
        {
          v12 = -1073741801;
        }
      }
      if ( P[1] != j[6] )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
      if ( v12 < 0 )
        return (unsigned int)v12;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000423c  push    rbp
0x18000423e  push    rbx
0x18000423f  push    rsi
0x180004240  push    rdi
0x180004241  push    r12
0x180004243  push    r14
0x180004245  push    r15
0x180004247  mov     rbp, rsp
0x18000424a  sub     rsp, 80h
0x180004251  mov     rax, cs:__security_cookie
0x180004258  xor     rax, rsp
0x18000425b  mov     [rbp+var_10], rax
0x18000425f  mov     r15, [rbp+String1]
0x180004263  mov     r12, rcx
0x180004266  movzx   ecx, word ptr [rdx+2]
0x18000426a  xorps   xmm1, xmm1
0x18000426d  xorps   xmm0, xmm0
0x180004270  mov     r14, r9
0x180004273  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180004277  mov     [rbp+DestinationString.MaximumLength], cx
0x18000427b  mov     rdi, r8
0x18000427e  mov     rsi, rdx
0x180004281  movups  xmmword ptr [rbp+P], xmm0
0x180004285  call    AiAlloc
0x18000428a  mov     [rbp+DestinationString.Buffer], rax
0x18000428e  test    rax, rax
0x180004291  jnz     short loc_18000429D
0x180004293  mov     ebx, 0C0000017h
0x180004298  jmp     loc_18000455C
0x18000429d  mov     rdx, rsi; SourceString
0x1800042a0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800042a4  call    cs:__imp_RtlCopyUnicodeString
0x1800042aa  lea     rdx, [rbp+DestinationString]
0x1800042ae  mov     rcx, r12
0x1800042b1  call    AiAddImagePathWithMacro
0x1800042b6  mov     ebx, eax
0x1800042b8  test    eax, eax
0x1800042ba  jns     short loc_1800042CE
0x1800042bc  mov     rcx, gs:60h
0x1800042c5  mov     r8, [rbp+DestinationString.Buffer]
0x1800042c9  jmp     loc_180004550
0x1800042ce  test    rdi, rdi
0x1800042d1  jz      short loc_18000430D
0x1800042d3  cmp     rdi, rsi
0x1800042d6  jz      short loc_18000430D
0x1800042d8  movzx   ecx, word ptr [rdi+2]
0x1800042dc  mov     [rbp+DestinationString.MaximumLength], cx
0x1800042e0  call    AiAlloc
0x1800042e5  mov     [rbp+DestinationString.Buffer], rax
0x1800042e9  test    rax, rax
0x1800042ec  jz      short loc_180004293
0x1800042ee  mov     rdx, rdi; SourceString
0x1800042f1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800042f5  call    cs:__imp_RtlCopyUnicodeString
0x1800042fb  lea     rdx, [rbp+DestinationString]
0x1800042ff  mov     rcx, r12
0x180004302  call    AiAddImagePathWithMacro
0x180004307  mov     ebx, eax
0x180004309  test    eax, eax
0x18000430b  js      short loc_1800042BC
0x18000430d  cmp     qword ptr [r15+8], 0
0x180004312  jz      loc_180004411
0x180004318  mov     rdx, r15; String1
0x18000431b  mov     rcx, rsi; String2
0x18000431e  call    AipIsPathMacroPrefix
0x180004323  test    eax, eax
0x180004325  jz      loc_180004411
0x18000432b  cmp     [rbp+arg_28], 0
0x18000432f  xorps   xmm0, xmm0
0x180004332  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180004336  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x18000433a  movups  xmm0, xmmword ptr [r14]
0x18000433e  movdqu  xmmword ptr [rbp+Src], xmm0
0x180004343  jz      short loc_180004356
0x180004345  lea     rdx, SourceString; "%REMOVABLE%"
0x18000434c  lea     rcx, [rbp+var_30]; DestinationString
0x180004350  call    cs:__imp_RtlInitUnicodeString
0x180004356  cmp     [rbp+arg_30], 0
0x18000435a  jz      short loc_18000436D
0x18000435c  lea     rdx, aHot; "%HOT%"
0x180004363  lea     rcx, [rbp+var_20]; DestinationString
0x180004367  call    cs:__imp_RtlInitUnicodeString
0x18000436d  xor     r14d, r14d
0x180004370  mov     edi, r14d
0x180004373  add     rdi, rdi
0x180004376  cmp     [rbp+rdi*8+Src+8], 0
0x18000437c  jz      loc_180004404
0x180004382  movzx   eax, word ptr [r15]
0x180004386  movzx   edx, word ptr [rbp+rdi*8+Src]
0x18000438b  sub     edx, eax
0x18000438d  movzx   eax, word ptr [rsi]
0x180004390  add     edx, eax
0x180004392  cmp     edx, 0FFFEh
0x180004398  ja      loc_180004424
0x18000439e  movzx   ecx, dx
0x1800043a1  mov     [rbp+DestinationString.Length], cx
0x1800043a5  mov     [rbp+DestinationString.MaximumLength], cx
0x1800043a9  call    AiAlloc
0x1800043ae  mov     [rbp+DestinationString.Buffer], rax
0x1800043b2  test    rax, rax
0x1800043b5  jz      loc_180004293
0x1800043bb  movzx   r8d, word ptr [rbp+rdi*8+Src]; Size
0x1800043c1  mov     rcx, rax; void *
0x1800043c4  mov     rdx, [rbp+rdi*8+Src+8]; Src
0x1800043c9  call    memcpy_0
0x1800043ce  movzx   ecx, word ptr [r15]
0x1800043d2  movzx   r8d, word ptr [rsi]
0x1800043d6  mov     rdx, [rsi+8]
0x1800043da  sub     r8, rcx; Size
0x1800043dd  add     rdx, rcx; Src
0x1800043e0  movzx   ecx, word ptr [rbp+rdi*8+Src]
0x1800043e5  add     rcx, [rbp+DestinationString.Buffer]; void *
0x1800043e9  call    memcpy_0
0x1800043ee  lea     rdx, [rbp+DestinationString]
0x1800043f2  mov     rcx, r12
0x1800043f5  call    AiAddImagePathWithMacro
0x1800043fa  mov     ebx, eax
0x1800043fc  test    eax, eax
0x1800043fe  js      loc_1800042BC
0x180004404  inc     r14d
0x180004407  cmp     r14d, 3
0x18000440b  jb      loc_180004370
0x180004411  mov     rdi, cs:P
0x180004418  lea     r14, P
0x18000441f  jmp     loc_180004529
0x180004424  mov     ebx, 0C0000106h
0x180004429  jmp     loc_18000455C
0x18000442e  test    byte ptr [rdi+10h], 8
0x180004432  lea     rcx, [rdi+28h]
0x180004436  jz      short loc_180004442
0x180004438  movups  xmm0, xmmword ptr [rcx]
0x18000443b  movdqu  xmmword ptr [rbp+P], xmm0
0x180004440  jmp     short loc_180004455
0x180004442  lea     rdx, [rbp+P]
0x180004446  call    AipConvertToNtPath
0x18000444b  mov     ebx, eax
0x18000444d  test    eax, eax
0x18000444f  js      loc_18000455C
0x180004455  lea     rdx, [rbp+P]; String1
0x180004459  mov     rcx, rsi; String2
0x18000445c  call    AipIsPathMacroPrefix
0x180004461  test    eax, eax
0x180004463  jz      loc_1800044FF
0x180004469  movzx   eax, word ptr [rbp+P]
0x18000446d  movzx   edx, word ptr [rdi+18h]
0x180004471  sub     edx, eax
0x180004473  movzx   eax, word ptr [rsi]
0x180004476  add     edx, eax
0x180004478  cmp     edx, 0FFFEh
0x18000447e  ja      loc_180004534
0x180004484  movzx   ecx, dx
0x180004487  mov     [rbp+DestinationString.Length], cx
0x18000448b  mov     [rbp+DestinationString.MaximumLength], cx
0x18000448f  call    AiAlloc
0x180004494  mov     [rbp+DestinationString.Buffer], rax
0x180004498  test    rax, rax
0x18000449b  jz      short loc_1800044FA
0x18000449d  movzx   r8d, word ptr [rdi+18h]; Size
0x1800044a2  mov     rcx, rax; void *
0x1800044a5  mov     rdx, [rdi+20h]; Src
0x1800044a9  call    memcpy_0
0x1800044ae  movzx   ecx, word ptr [rbp+P]
0x1800044b2  movzx   r8d, word ptr [rsi]
0x1800044b6  mov     rdx, [rsi+8]
0x1800044ba  sub     r8, rcx; Size
0x1800044bd  add     rdx, rcx; Src
0x1800044c0  movzx   ecx, word ptr [rdi+18h]
0x1800044c4  add     rcx, [rbp+DestinationString.Buffer]; void *
0x1800044c8  call    memcpy_0
0x1800044cd  lea     rdx, [rbp+DestinationString]
0x1800044d1  mov     rcx, r12
0x1800044d4  call    AiAddImagePathWithMacro
0x1800044d9  mov     ebx, eax
0x1800044db  test    eax, eax
0x1800044dd  jns     short loc_1800044FF
0x1800044df  mov     rcx, gs:60h
0x1800044e8  xor     edx, edx; Flags
0x1800044ea  mov     r8, [rbp+DestinationString.Buffer]; P
0x1800044ee  mov     rcx, [rcx+30h]; HeapHandle
0x1800044f2  call    cs:__imp_RtlFreeHeap
0x1800044f8  jmp     short loc_1800044FF
0x1800044fa  mov     ebx, 0C0000017h
0x1800044ff  mov     rax, [rdi+30h]
0x180004503  cmp     [rbp+P+8], rax
0x180004507  jz      short loc_180004522
0x180004509  mov     rcx, gs:60h
0x180004512  xor     edx, edx; Flags
0x180004514  mov     r8, [rbp+P+8]; P
0x180004518  mov     rcx, [rcx+30h]; HeapHandle
0x18000451c  call    cs:__imp_RtlFreeHeap
0x180004522  test    ebx, ebx
0x180004524  js      short loc_18000455C
0x180004526  mov     rdi, [rdi]
0x180004529  cmp     rdi, r14
0x18000452c  jnz     loc_18000442E
0x180004532  jmp     short loc_18000455C
0x180004534  mov     rax, [rdi+30h]
0x180004538  mov     ebx, 0C0000106h
0x18000453d  cmp     [rbp+P+8], rax
0x180004541  jz      short loc_18000455C
0x180004543  mov     rcx, gs:60h
0x18000454c  mov     r8, [rbp+P+8]; P
0x180004550  mov     rcx, [rcx+30h]; HeapHandle
0x180004554  xor     edx, edx; Flags
0x180004556  call    cs:__imp_RtlFreeHeap
0x18000455c  mov     eax, ebx
0x18000455e  mov     rcx, [rbp+var_10]
0x180004562  xor     rcx, rsp; StackCookie
0x180004565  call    __security_check_cookie
0x18000456a  add     rsp, 80h
0x180004571  pop     r15
0x180004573  pop     r14
0x180004575  pop     r12
0x180004577  pop     rdi
0x180004578  pop     rsi
0x180004579  pop     rbx
0x18000457a  pop     rbp
0x18000457b  retn
```
