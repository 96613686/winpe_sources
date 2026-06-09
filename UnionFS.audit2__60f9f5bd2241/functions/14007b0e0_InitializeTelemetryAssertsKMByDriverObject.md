# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14007b0e0`
- end: `0x14007b1df`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000701c`

## callees

- `0x14007b0e0`
- `0x14007b1e8`

## import_xrefs

- `ntoskrnl!RtlFreeAnsiString` at `0x14007b1c5`
- `ntoskrnl!RtlFreeAnsiString` at `0x14007b1c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b15f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b15f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007b119`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007b119`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14007b12c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14007b12c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14007b14b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14007b14b`
- `ntoskrnl!RtlInitAnsiString` at `0x14007b1a1`
- `ntoskrnl!RtlInitAnsiString` at `0x14007b1a1`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 v4; // rcx
  bool v5; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v8; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-10h] BYREF

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
      v4 = (unsigned int)AnsiString.Length - 1;
      if ( AnsiString.Length != 1 )
      {
        while ( AnsiString.Buffer[v4] != 92 )
        {
          v5 = (_DWORD)v4 == 1;
          v4 = (unsigned int)(v4 - 1);
          if ( v5 )
            goto LABEL_11;
        }
        if ( (_DWORD)v4 != AnsiString.Length )
        {
          v8 = 0;
          RtlInitAnsiString(&v8, &AnsiString.Buffer[(unsigned int)(v4 + 1)]);
          v9 = v8;
          v3 = InitializeTelemetryAssertsKMWorkerInternal(&v9);
        }
      }
LABEL_11:
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x14007b0e0  mov     [rsp-8+arg_0], rbx
0x14007b0e5  push    rbp
0x14007b0e6  mov     rbp, rsp
0x14007b0e9  sub     rsp, 60h
0x14007b0ed  xorps   xmm0, xmm0
0x14007b0f0  xorps   xmm1, xmm1
0x14007b0f3  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x14007b0f7  mov     rbx, rcx
0x14007b0fa  xor     eax, eax
0x14007b0fc  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14007b100  lock xadd cs:g_AssertsOperational, eax
0x14007b108  test    eax, eax
0x14007b10a  jz      short loc_14007B113
0x14007b10c  xor     eax, eax
0x14007b10e  jmp     loc_14007B1D3
0x14007b113  xor     edx, edx; SourceString
0x14007b115  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007b119  call    cs:__imp_RtlInitUnicodeString
0x14007b120  nop     dword ptr [rax+rax+00h]
0x14007b125  lea     rdx, [rbp+DestinationString]
0x14007b129  mov     rcx, rbx
0x14007b12c  call    cs:__imp_IoQueryFullDriverPath
0x14007b133  nop     dword ptr [rax+rax+00h]
0x14007b138  test    eax, eax
0x14007b13a  js      loc_14007B1D3
0x14007b140  mov     r8b, 1; AllocateDestinationString
0x14007b143  lea     rdx, [rbp+DestinationString]; SourceString
0x14007b147  lea     rcx, [rbp+AnsiString]; DestinationString
0x14007b14b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14007b152  nop     dword ptr [rax+rax+00h]
0x14007b157  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14007b15b  xor     edx, edx; Tag
0x14007b15d  mov     ebx, eax
0x14007b15f  call    cs:__imp_ExFreePoolWithTag
0x14007b166  nop     dword ptr [rax+rax+00h]
0x14007b16b  test    ebx, ebx
0x14007b16d  js      short loc_14007B1D1
0x14007b16f  movzx   edx, [rbp+AnsiString.Length]
0x14007b173  lea     ecx, [rdx-1]
0x14007b176  test    ecx, ecx
0x14007b178  jz      short loc_14007B1C1
0x14007b17a  mov     r8, [rbp+AnsiString.Buffer]
0x14007b17e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14007b183  jz      short loc_14007B18C
0x14007b185  add     ecx, 0FFFFFFFFh
0x14007b188  jnz     short loc_14007B17E
0x14007b18a  jmp     short loc_14007B1C1
0x14007b18c  cmp     ecx, edx
0x14007b18e  jz      short loc_14007B1C1
0x14007b190  lea     edx, [rcx+1]
0x14007b193  xorps   xmm0, xmm0
0x14007b196  add     rdx, r8; SourceString
0x14007b199  lea     rcx, [rbp+var_20]; DestinationString
0x14007b19d  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14007b1a1  call    cs:__imp_RtlInitAnsiString
0x14007b1a8  nop     dword ptr [rax+rax+00h]
0x14007b1ad  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14007b1b1  lea     rcx, [rbp+var_10]
0x14007b1b5  movdqa  [rbp+var_10], xmm0
0x14007b1ba  call    InitializeTelemetryAssertsKMWorkerInternal
0x14007b1bf  mov     ebx, eax
0x14007b1c1  lea     rcx, [rbp+AnsiString]; AnsiString
0x14007b1c5  call    cs:__imp_RtlFreeAnsiString
0x14007b1cc  nop     dword ptr [rax+rax+00h]
0x14007b1d1  mov     eax, ebx
0x14007b1d3  mov     rbx, [rsp+60h+arg_0]
0x14007b1d8  add     rsp, 60h
0x14007b1dc  pop     rbp
0x14007b1dd  retn
```
