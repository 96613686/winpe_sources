# SIPolicyBuildPath

- ea: `0x180022ca4`
- end: `0x180022dae`
- name: `SIPolicyBuildPath`
- size: `266`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, struct _UNICODE_STRING *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180020b44`
- `0x18002121c`
- `0x180021608`
- `0x1800220e0`
- `0x180022404`
- `0x18002247c`

## callees

- `0x180022ca4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022d09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022d09`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d38`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d63`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d76`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d38`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d63`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022d76`
- `ntdll!RtlInitUnicodeString` at `0x180022d91`
- `ntdll!RtlInitUnicodeString` at `0x180022d91`
- `ntdll!RtlFreeUnicodeString` at `0x180022d9b`
- `ntdll!RtlFreeUnicodeString` at `0x180022d9b`

## pseudocode

```c
__int64 __fastcall SIPolicyBuildPath(PCUNICODE_STRING Source, PCUNICODE_STRING a2, struct _UNICODE_STRING *a3)
{
  int v6; // ecx
  NTSTATUS appended; // ebx
  int v8; // ebx
  WCHAR *v9; // rax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING Sourcea; // [rsp+30h] [rbp-10h] BYREF

  *(_QWORD *)&Sourcea.Length = 262146;
  Sourcea.Buffer = L"\\";
  Destination = 0;
  if ( a2 )
    v6 = a2->Length >> 1;
  else
    v6 = 0;
  if ( Source->Length >= 2u )
  {
    v8 = v6 + (Source->Length >> 1);
    v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v8 + 3));
    if ( v9 )
    {
      *(_QWORD *)&Destination.Length = 0;
      Destination.Buffer = v9;
      *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(2 * (v8 + 3));
      appended = RtlAppendUnicodeStringToString(&Destination, Source);
      if ( appended >= 0 )
      {
        if ( !a2
          || (Source->Buffer[((unsigned __int64)Source->Length >> 1) - 1] == 92
           || (appended = RtlAppendUnicodeStringToString(&Destination, &Sourcea), appended >= 0))
          && (appended = RtlAppendUnicodeStringToString(&Destination, a2), appended >= 0) )
        {
          *a3 = Destination;
          RtlInitUnicodeString(&Destination, 0);
        }
      }
    }
    else
    {
      appended = -1073741801;
    }
  }
  else
  {
    appended = -1073741811;
  }
  RtlFreeUnicodeString(&Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180022ca4  push    rbp
0x180022ca6  push    rbx
0x180022ca7  push    rsi
0x180022ca8  push    rdi
0x180022ca9  push    r14
0x180022cab  mov     rbp, rsp
0x180022cae  sub     rsp, 40h
0x180022cb2  mov     rdi, rdx
0x180022cb5  mov     qword ptr [rbp+Source.Length], 40002h
0x180022cbd  lea     rax, asc_18002ED88; "\\"
0x180022cc4  xorps   xmm0, xmm0
0x180022cc7  mov     [rbp+Source.Buffer], rax
0x180022ccb  mov     r14, r8
0x180022cce  mov     rsi, rcx
0x180022cd1  mov     edx, 2
0x180022cd6  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180022cda  test    rdi, rdi
0x180022cdd  jz      short loc_180022CE6
0x180022cdf  movzx   ecx, word ptr [rdi]
0x180022ce2  shr     ecx, 1
0x180022ce4  jmp     short loc_180022CE8
0x180022ce6  xor     ecx, ecx
0x180022ce8  cmp     [rsi], dx
0x180022ceb  jnb     short loc_180022CF7
0x180022ced  mov     ebx, 0C000000Dh
0x180022cf2  jmp     loc_180022D97
0x180022cf7  movzx   ebx, word ptr [rsi]
0x180022cfa  shr     ebx, 1
0x180022cfc  add     ebx, ecx
0x180022cfe  mov     ecx, 40h ; '@'; uFlags
0x180022d03  lea     edx, [rbx+3]
0x180022d06  add     rdx, rdx; uBytes
0x180022d09  call    cs:__imp_LocalAlloc
0x180022d0f  test    rax, rax
0x180022d12  jnz     short loc_180022D1B
0x180022d14  mov     ebx, 0C0000017h
0x180022d19  jmp     short loc_180022D97
0x180022d1b  xorps   xmm0, xmm0
0x180022d1e  lea     rcx, [rbp+Destination]; Destination
0x180022d22  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180022d26  add     bx, 3
0x180022d2a  mov     [rbp+Destination.Buffer], rax
0x180022d2e  add     bx, bx
0x180022d31  mov     rdx, rsi; Source
0x180022d34  mov     [rbp+Destination.MaximumLength], bx
0x180022d38  call    cs:__imp_RtlAppendUnicodeStringToString
0x180022d3e  mov     ebx, eax
0x180022d40  test    eax, eax
0x180022d42  js      short loc_180022D97
0x180022d44  test    rdi, rdi
0x180022d47  jz      short loc_180022D82
0x180022d49  movzx   ecx, word ptr [rsi]
0x180022d4c  mov     rax, [rsi+8]
0x180022d50  shr     rcx, 1
0x180022d53  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180022d59  jz      short loc_180022D6F
0x180022d5b  lea     rdx, [rbp+Source]; Source
0x180022d5f  lea     rcx, [rbp+Destination]; Destination
0x180022d63  call    cs:__imp_RtlAppendUnicodeStringToString
0x180022d69  mov     ebx, eax
0x180022d6b  test    eax, eax
0x180022d6d  js      short loc_180022D97
0x180022d6f  mov     rdx, rdi; Source
0x180022d72  lea     rcx, [rbp+Destination]; Destination
0x180022d76  call    cs:__imp_RtlAppendUnicodeStringToString
0x180022d7c  mov     ebx, eax
0x180022d7e  test    eax, eax
0x180022d80  js      short loc_180022D97
0x180022d82  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x180022d86  xor     edx, edx; SourceString
0x180022d88  lea     rcx, [rbp+Destination]; DestinationString
0x180022d8c  movdqu  xmmword ptr [r14], xmm0
0x180022d91  call    cs:__imp_RtlInitUnicodeString
0x180022d97  lea     rcx, [rbp+Destination]; UnicodeString
0x180022d9b  call    cs:__imp_RtlFreeUnicodeString
0x180022da1  mov     eax, ebx
0x180022da3  add     rsp, 40h
0x180022da7  pop     r14
0x180022da9  pop     rdi
0x180022daa  pop     rsi
0x180022dab  pop     rbx
0x180022dac  pop     rbp
0x180022dad  retn
```
