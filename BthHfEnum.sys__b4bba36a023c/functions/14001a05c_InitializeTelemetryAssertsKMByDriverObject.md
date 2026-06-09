# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14001a05c`
- end: `0x14001a158`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003003c`

## callees

- `0x14001a05c`
- `0x14001a160`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a095`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a095`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a0db`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001a0a8`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14001a0a8`
- `ntoskrnl!RtlFreeAnsiString` at `0x14001a13e`
- `ntoskrnl!RtlFreeAnsiString` at `0x14001a13e`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001a0c7`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14001a0c7`
- `ntoskrnl!RtlInitAnsiString` at `0x14001a11a`
- `ntoskrnl!RtlInitAnsiString` at `0x14001a11a`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
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
0x14001a05c  mov     [rsp-8+arg_0], rbx
0x14001a061  push    rbp
0x14001a062  mov     rbp, rsp
0x14001a065  sub     rsp, 60h
0x14001a069  xorps   xmm0, xmm0
0x14001a06c  xorps   xmm1, xmm1
0x14001a06f  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x14001a073  mov     rbx, rcx
0x14001a076  xor     eax, eax
0x14001a078  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14001a07c  lock xadd cs:g_AssertsOperational, eax
0x14001a084  test    eax, eax
0x14001a086  jz      short loc_14001A08F
0x14001a088  xor     eax, eax
0x14001a08a  jmp     loc_14001A14C
0x14001a08f  xor     edx, edx; SourceString
0x14001a091  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a095  call    cs:__imp_RtlInitUnicodeString
0x14001a09c  nop     dword ptr [rax+rax+00h]
0x14001a0a1  lea     rdx, [rbp+DestinationString]
0x14001a0a5  mov     rcx, rbx
0x14001a0a8  call    cs:__imp_IoQueryFullDriverPath
0x14001a0af  nop     dword ptr [rax+rax+00h]
0x14001a0b4  test    eax, eax
0x14001a0b6  js      loc_14001A14C
0x14001a0bc  mov     r8b, 1; AllocateDestinationString
0x14001a0bf  lea     rdx, [rbp+DestinationString]; SourceString
0x14001a0c3  lea     rcx, [rbp+AnsiString]; DestinationString
0x14001a0c7  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14001a0ce  nop     dword ptr [rax+rax+00h]
0x14001a0d3  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14001a0d7  xor     edx, edx; Tag
0x14001a0d9  mov     ebx, eax
0x14001a0db  call    cs:__imp_ExFreePoolWithTag
0x14001a0e2  nop     dword ptr [rax+rax+00h]
0x14001a0e7  test    ebx, ebx
0x14001a0e9  js      short loc_14001A14A
0x14001a0eb  movzx   edx, [rbp+AnsiString.Length]
0x14001a0ef  mov     r8, [rbp+AnsiString.Buffer]
0x14001a0f3  lea     ecx, [rdx-1]
0x14001a0f6  test    ecx, ecx
0x14001a0f8  jz      short loc_14001A13A
0x14001a0fa  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14001a0ff  jz      short loc_14001A105
0x14001a101  dec     ecx
0x14001a103  jmp     short loc_14001A0F6
0x14001a105  cmp     ecx, edx
0x14001a107  jz      short loc_14001A13A
0x14001a109  lea     edx, [rcx+1]
0x14001a10c  xorps   xmm0, xmm0
0x14001a10f  add     rdx, r8; SourceString
0x14001a112  lea     rcx, [rbp+var_20]; DestinationString
0x14001a116  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14001a11a  call    cs:__imp_RtlInitAnsiString
0x14001a121  nop     dword ptr [rax+rax+00h]
0x14001a126  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14001a12a  lea     rcx, [rbp+var_10]
0x14001a12e  movdqa  [rbp+var_10], xmm0
0x14001a133  call    InitializeTelemetryAssertsKMWorkerInternal
0x14001a138  mov     ebx, eax
0x14001a13a  lea     rcx, [rbp+AnsiString]; AnsiString
0x14001a13e  call    cs:__imp_RtlFreeAnsiString
0x14001a145  nop     dword ptr [rax+rax+00h]
0x14001a14a  mov     eax, ebx
0x14001a14c  mov     rbx, [rsp+60h+arg_0]
0x14001a151  add     rsp, 60h
0x14001a155  pop     rbp
0x14001a156  retn
```
