# CreateFqbnString

- ea: `0x140005b48`
- end: `0x140005d8a`
- name: `CreateFqbnString`
- size: `578`
- prototype: `__int64 __fastcall(__int64 *, struct _UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005d90`

## callees

- `0x140002e98`
- `0x140005b48`
- `0x1400065c4`
- `0x140006a20`
- `0x140006f40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005c20`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005c6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005cbd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005d02`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005d3f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005c20`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005c6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005cbd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005d02`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005d3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d5b`
- `ntoskrnl!ExAllocatePool2` at `0x140005bce`
- `ntoskrnl!ExAllocatePool2` at `0x140005bce`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005c40`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005c90`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005cd9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005d1a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005c40`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005c90`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005cd9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140005d1a`

## pseudocode

```c
__int64 __fastcall CreateFqbnString(__int64 *a1, struct _UNICODE_STRING **a2)
{
  UNICODE_STRING v2; // xmm1
  NTSTATUS appended; // ebx
  USHORT v6; // bx
  unsigned __int64 v7; // rsi
  size_t v8; // r14
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v10; // rdi
  USHORT pusResult; // [rsp+20h] [rbp-40h] BYREF
  UNICODE_STRING v13; // [rsp+28h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h] BYREF
  int v16; // [rsp+50h] [rbp-10h]

  v2 = *(UNICODE_STRING *)(a1 + 1);
  v15 = 0;
  v16 = 0;
  Source = v2;
  pusResult = _mm_cvtsi128_si32((__m128i)v2);
  v13 = 0;
  appended = RtlUShortAdd(pusResult, 0x32u, &pusResult);
  if ( appended >= 0 )
  {
    v6 = pusResult;
    v7 = *a1;
    v8 = (unsigned int)pusResult + 16;
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(66, v8, 1097884741);
    v10 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, v8);
      v10->MaximumLength = v6;
      v10->Buffer = &v10[1].Length;
      v10->Length = 0;
      v13.Buffer = (PWSTR)&v15;
      *(_DWORD *)&v13.Length = 786432;
      appended = RtlAppendUnicodeStringToString(v10, &Source);
      if ( appended < 0 )
        goto LABEL_14;
      appended = RtlAppendUnicodeToString(v10, L"\\");
      if ( appended < 0 )
        goto LABEL_14;
      UShortToUnicodeString(HIWORD(v7), &v13);
      appended = RtlAppendUnicodeStringToString(v10, &v13);
      if ( appended < 0 )
        goto LABEL_14;
      appended = RtlAppendUnicodeToString(v10, L".");
      if ( appended < 0 )
        goto LABEL_14;
      UShortToUnicodeString(HIDWORD(v7), &v13);
      appended = RtlAppendUnicodeStringToString(v10, &v13);
      if ( appended < 0
        || (appended = RtlAppendUnicodeToString(v10, L"."), appended < 0)
        || (UShortToUnicodeString(v7 >> 16, &v13), appended = RtlAppendUnicodeStringToString(v10, &v13), appended < 0)
        || (appended = RtlAppendUnicodeToString(v10, L"."), appended < 0)
        || (UShortToUnicodeString((unsigned __int16)v7, &v13),
            appended = RtlAppendUnicodeStringToString(v10, &v13),
            appended < 0) )
      {
LABEL_14:
        ExFreePoolWithTag(v10, 0);
      }
      else
      {
        *a2 = v10;
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140005b48  mov     [rsp-28h+arg_10], rbx
0x140005b4d  push    rbp
0x140005b4e  push    rsi
0x140005b4f  push    rdi
0x140005b50  push    r14
0x140005b52  push    r15
0x140005b54  mov     rbp, rsp
0x140005b57  sub     rsp, 60h
0x140005b5b  mov     rax, cs:__security_cookie
0x140005b62  xor     rax, rsp
0x140005b65  mov     [rbp+var_8], rax
0x140005b69  movups  xmm1, xmmword ptr [rcx+8]
0x140005b6d  xor     eax, eax
0x140005b6f  lea     r8, [rbp+pusResult]; pusResult
0x140005b73  mov     r15, rdx
0x140005b76  mov     [rbp+var_18], rax
0x140005b7a  mov     rsi, rcx
0x140005b7d  mov     [rbp+var_10], eax
0x140005b80  movd    ecx, xmm1; usAugend
0x140005b84  xorps   xmm0, xmm0
0x140005b87  lea     edx, [rax+32h]; usAddend
0x140005b8a  movups  xmmword ptr [rbp+Source.Length], xmm1
0x140005b8e  mov     [rbp+pusResult], cx
0x140005b92  movups  xmmword ptr [rbp+var_38.Length], xmm0
0x140005b96  call    RtlUShortAdd
0x140005b9b  mov     ebx, eax
0x140005b9d  test    eax, eax
0x140005b9f  js      loc_140005D67
0x140005ba5  movzx   ebx, [rbp+pusResult]
0x140005ba9  lea     eax, [rbx+10h]
0x140005bac  cmp     eax, 10h
0x140005baf  jnb     short loc_140005BBB
0x140005bb1  mov     ebx, 0C0000095h
0x140005bb6  jmp     loc_140005D67
0x140005bbb  mov     rsi, [rsi]
0x140005bbe  mov     r8d, 41706445h
0x140005bc4  mov     edx, eax
0x140005bc6  mov     ecx, 42h ; 'B'
0x140005bcb  mov     r14d, eax
0x140005bce  call    cs:__imp_ExAllocatePool2
0x140005bd5  nop     dword ptr [rax+rax+00h]
0x140005bda  mov     rdi, rax
0x140005bdd  test    rax, rax
0x140005be0  jnz     short loc_140005BEC
0x140005be2  mov     ebx, 0C0000017h
0x140005be7  jmp     loc_140005D67
0x140005bec  mov     r8, r14; Size
0x140005bef  xor     edx, edx; Val
0x140005bf1  mov     rcx, rdi; void *
0x140005bf4  call    memset
0x140005bf9  lea     rax, [rdi+10h]
0x140005bfd  mov     [rdi+2], bx
0x140005c01  mov     [rdi+8], rax
0x140005c05  lea     rdx, [rbp+Source]; Source
0x140005c09  xor     eax, eax
0x140005c0b  mov     rcx, rdi; Destination
0x140005c0e  mov     [rdi], ax
0x140005c11  lea     rax, [rbp+var_18]
0x140005c15  mov     [rbp+var_38.Buffer], rax
0x140005c19  mov     dword ptr [rbp+var_38.Length], 0C0000h
0x140005c20  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005c27  nop     dword ptr [rax+rax+00h]
0x140005c2c  mov     ebx, eax
0x140005c2e  test    eax, eax
0x140005c30  js      loc_140005D56
0x140005c36  lea     rdx, Source; "\\"
0x140005c3d  mov     rcx, rdi; Destination
0x140005c40  call    cs:__imp_RtlAppendUnicodeToString
0x140005c47  nop     dword ptr [rax+rax+00h]
0x140005c4c  mov     ebx, eax
0x140005c4e  test    eax, eax
0x140005c50  js      loc_140005D56
0x140005c56  mov     rcx, rsi
0x140005c59  lea     rdx, [rbp+var_38]
0x140005c5d  shr     rcx, 30h
0x140005c61  call    UShortToUnicodeString
0x140005c66  lea     rdx, [rbp+var_38]; Source
0x140005c6a  mov     rcx, rdi; Destination
0x140005c6d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005c74  nop     dword ptr [rax+rax+00h]
0x140005c79  mov     ebx, eax
0x140005c7b  test    eax, eax
0x140005c7d  js      loc_140005D56
0x140005c83  lea     r14, asc_1400159EC; "."
0x140005c8a  mov     rcx, rdi; Destination
0x140005c8d  mov     rdx, r14; Source
0x140005c90  call    cs:__imp_RtlAppendUnicodeToString
0x140005c97  nop     dword ptr [rax+rax+00h]
0x140005c9c  mov     ebx, eax
0x140005c9e  test    eax, eax
0x140005ca0  js      loc_140005D56
0x140005ca6  mov     rcx, rsi
0x140005ca9  lea     rdx, [rbp+var_38]
0x140005cad  shr     rcx, 20h
0x140005cb1  call    UShortToUnicodeString
0x140005cb6  lea     rdx, [rbp+var_38]; Source
0x140005cba  mov     rcx, rdi; Destination
0x140005cbd  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005cc4  nop     dword ptr [rax+rax+00h]
0x140005cc9  mov     ebx, eax
0x140005ccb  test    eax, eax
0x140005ccd  js      loc_140005D56
0x140005cd3  mov     rdx, r14; Source
0x140005cd6  mov     rcx, rdi; Destination
0x140005cd9  call    cs:__imp_RtlAppendUnicodeToString
0x140005ce0  nop     dword ptr [rax+rax+00h]
0x140005ce5  mov     ebx, eax
0x140005ce7  test    eax, eax
0x140005ce9  js      short loc_140005D56
0x140005ceb  mov     rcx, rsi
0x140005cee  lea     rdx, [rbp+var_38]
0x140005cf2  shr     rcx, 10h
0x140005cf6  call    UShortToUnicodeString
0x140005cfb  lea     rdx, [rbp+var_38]; Source
0x140005cff  mov     rcx, rdi; Destination
0x140005d02  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005d09  nop     dword ptr [rax+rax+00h]
0x140005d0e  mov     ebx, eax
0x140005d10  test    eax, eax
0x140005d12  js      short loc_140005D56
0x140005d14  mov     rdx, r14; Source
0x140005d17  mov     rcx, rdi; Destination
0x140005d1a  call    cs:__imp_RtlAppendUnicodeToString
0x140005d21  nop     dword ptr [rax+rax+00h]
0x140005d26  mov     ebx, eax
0x140005d28  test    eax, eax
0x140005d2a  js      short loc_140005D56
0x140005d2c  movzx   ecx, si
0x140005d2f  lea     rdx, [rbp+var_38]
0x140005d33  call    UShortToUnicodeString
0x140005d38  lea     rdx, [rbp+var_38]; Source
0x140005d3c  mov     rcx, rdi; Destination
0x140005d3f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005d46  nop     dword ptr [rax+rax+00h]
0x140005d4b  mov     ebx, eax
0x140005d4d  test    eax, eax
0x140005d4f  js      short loc_140005D56
0x140005d51  mov     [r15], rdi
0x140005d54  jmp     short loc_140005D67
0x140005d56  xor     edx, edx; Tag
0x140005d58  mov     rcx, rdi; P
0x140005d5b  call    cs:__imp_ExFreePoolWithTag
0x140005d62  nop     dword ptr [rax+rax+00h]
0x140005d67  mov     eax, ebx
0x140005d69  mov     rcx, [rbp+var_8]
0x140005d6d  xor     rcx, rsp; StackCookie
0x140005d70  call    __security_check_cookie
0x140005d75  mov     rbx, [rsp+60h+arg_10]
0x140005d7d  add     rsp, 60h
0x140005d81  pop     r15
0x140005d83  pop     r14
0x140005d85  pop     rdi
0x140005d86  pop     rsi
0x140005d87  pop     rbp
0x140005d88  retn
```
