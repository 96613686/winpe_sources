# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140057bf4`
- end: `0x140057cf0`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007553c`

## callees

- `0x140057bf4`
- `0x140057cf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c73`
- `ntoskrnl!RtlInitUnicodeString` at `0x140057c2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140057c2d`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140057c40`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140057c40`
- `ntoskrnl!RtlFreeAnsiString` at `0x140057cd6`
- `ntoskrnl!RtlFreeAnsiString` at `0x140057cd6`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140057c5f`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140057c5f`
- `ntoskrnl!RtlInitAnsiString` at `0x140057cb2`
- `ntoskrnl!RtlInitAnsiString` at `0x140057cb2`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v7; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+50h] [rbp-10h] BYREF

  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RtlInitUnicodeString(&DestinationString, 0);
  result = IoQueryFullDriverPath(a1, &DestinationString);
  if ( (int)result >= 0 )
  {
    v3 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v3 >= 0 )
    {
      for ( i = (unsigned int)AnsiString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
      {
        if ( AnsiString.Buffer[i] == 92 )
        {
          if ( (_DWORD)i != AnsiString.Length )
          {
            v7 = 0;
            RtlInitAnsiString(&v7, &AnsiString.Buffer[(unsigned int)(i + 1)]);
            v8 = v7;
            v3 = InitializeTelemetryAssertsKMWorkerInternal(&v8);
          }
          break;
        }
      }
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x140057bf4  mov     [rsp-8+arg_0], rbx
0x140057bf9  push    rbp
0x140057bfa  mov     rbp, rsp
0x140057bfd  sub     rsp, 60h
0x140057c01  xorps   xmm0, xmm0
0x140057c04  xorps   xmm1, xmm1
0x140057c07  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140057c0b  mov     rbx, rcx
0x140057c0e  xor     eax, eax
0x140057c10  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140057c14  lock xadd cs:g_AssertsOperational, eax
0x140057c1c  test    eax, eax
0x140057c1e  jz      short loc_140057C27
0x140057c20  xor     eax, eax
0x140057c22  jmp     loc_140057CE4
0x140057c27  xor     edx, edx; SourceString
0x140057c29  lea     rcx, [rbp+DestinationString]; DestinationString
0x140057c2d  call    cs:__imp_RtlInitUnicodeString
0x140057c34  nop     dword ptr [rax+rax+00h]
0x140057c39  lea     rdx, [rbp+DestinationString]
0x140057c3d  mov     rcx, rbx
0x140057c40  call    cs:__imp_IoQueryFullDriverPath
0x140057c47  nop     dword ptr [rax+rax+00h]
0x140057c4c  test    eax, eax
0x140057c4e  js      loc_140057CE4
0x140057c54  mov     r8b, 1; AllocateDestinationString
0x140057c57  lea     rdx, [rbp+DestinationString]; SourceString
0x140057c5b  lea     rcx, [rbp+AnsiString]; DestinationString
0x140057c5f  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140057c66  nop     dword ptr [rax+rax+00h]
0x140057c6b  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140057c6f  xor     edx, edx; Tag
0x140057c71  mov     ebx, eax
0x140057c73  call    cs:__imp_ExFreePoolWithTag
0x140057c7a  nop     dword ptr [rax+rax+00h]
0x140057c7f  test    ebx, ebx
0x140057c81  js      short loc_140057CE2
0x140057c83  movzx   edx, [rbp+AnsiString.Length]
0x140057c87  mov     r8, [rbp+AnsiString.Buffer]
0x140057c8b  lea     ecx, [rdx-1]
0x140057c8e  test    ecx, ecx
0x140057c90  jz      short loc_140057CD2
0x140057c92  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140057c97  jz      short loc_140057C9D
0x140057c99  dec     ecx
0x140057c9b  jmp     short loc_140057C8E
0x140057c9d  cmp     ecx, edx
0x140057c9f  jz      short loc_140057CD2
0x140057ca1  lea     edx, [rcx+1]
0x140057ca4  xorps   xmm0, xmm0
0x140057ca7  add     rdx, r8; SourceString
0x140057caa  lea     rcx, [rbp+var_20]; DestinationString
0x140057cae  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140057cb2  call    cs:__imp_RtlInitAnsiString
0x140057cb9  nop     dword ptr [rax+rax+00h]
0x140057cbe  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140057cc2  lea     rcx, [rbp+var_10]
0x140057cc6  movdqa  [rbp+var_10], xmm0
0x140057ccb  call    InitializeTelemetryAssertsKMWorkerInternal
0x140057cd0  mov     ebx, eax
0x140057cd2  lea     rcx, [rbp+AnsiString]; AnsiString
0x140057cd6  call    cs:__imp_RtlFreeAnsiString
0x140057cdd  nop     dword ptr [rax+rax+00h]
0x140057ce2  mov     eax, ebx
0x140057ce4  mov     rbx, [rsp+60h+arg_0]
0x140057ce9  add     rsp, 60h
0x140057ced  pop     rbp
0x140057cee  retn
```
