# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x1400dd4c0`
- end: `0x1400dd5bc`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14012103c`

## callees

- `0x1400dd4c0`
- `0x1400dd5c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd53f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dd53f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dd4f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400dd4f9`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400dd50c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400dd50c`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400dd5a2`
- `ntoskrnl!RtlFreeAnsiString` at `0x1400dd5a2`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400dd52b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400dd52b`
- `ntoskrnl!RtlInitAnsiString` at `0x1400dd57e`
- `ntoskrnl!RtlInitAnsiString` at `0x1400dd57e`

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
0x1400dd4c0  mov     [rsp-8+arg_0], rbx
0x1400dd4c5  push    rbp
0x1400dd4c6  mov     rbp, rsp
0x1400dd4c9  sub     rsp, 60h
0x1400dd4cd  xorps   xmm0, xmm0
0x1400dd4d0  xorps   xmm1, xmm1
0x1400dd4d3  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x1400dd4d7  mov     rbx, rcx
0x1400dd4da  xor     eax, eax
0x1400dd4dc  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400dd4e0  lock xadd cs:g_AssertsOperational, eax
0x1400dd4e8  test    eax, eax
0x1400dd4ea  jz      short loc_1400DD4F3
0x1400dd4ec  xor     eax, eax
0x1400dd4ee  jmp     loc_1400DD5B0
0x1400dd4f3  xor     edx, edx; SourceString
0x1400dd4f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400dd4f9  call    cs:__imp_RtlInitUnicodeString
0x1400dd500  nop     dword ptr [rax+rax+00h]
0x1400dd505  lea     rdx, [rbp+DestinationString]
0x1400dd509  mov     rcx, rbx
0x1400dd50c  call    cs:__imp_IoQueryFullDriverPath
0x1400dd513  nop     dword ptr [rax+rax+00h]
0x1400dd518  test    eax, eax
0x1400dd51a  js      loc_1400DD5B0
0x1400dd520  mov     r8b, 1; AllocateDestinationString
0x1400dd523  lea     rdx, [rbp+DestinationString]; SourceString
0x1400dd527  lea     rcx, [rbp+AnsiString]; DestinationString
0x1400dd52b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400dd532  nop     dword ptr [rax+rax+00h]
0x1400dd537  mov     rcx, [rbp+DestinationString.Buffer]; P
0x1400dd53b  xor     edx, edx; Tag
0x1400dd53d  mov     ebx, eax
0x1400dd53f  call    cs:__imp_ExFreePoolWithTag
0x1400dd546  nop     dword ptr [rax+rax+00h]
0x1400dd54b  test    ebx, ebx
0x1400dd54d  js      short loc_1400DD5AE
0x1400dd54f  movzx   edx, [rbp+AnsiString.Length]
0x1400dd553  mov     r8, [rbp+AnsiString.Buffer]
0x1400dd557  lea     ecx, [rdx-1]
0x1400dd55a  test    ecx, ecx
0x1400dd55c  jz      short loc_1400DD59E
0x1400dd55e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x1400dd563  jz      short loc_1400DD569
0x1400dd565  dec     ecx
0x1400dd567  jmp     short loc_1400DD55A
0x1400dd569  cmp     ecx, edx
0x1400dd56b  jz      short loc_1400DD59E
0x1400dd56d  lea     edx, [rcx+1]
0x1400dd570  xorps   xmm0, xmm0
0x1400dd573  add     rdx, r8; SourceString
0x1400dd576  lea     rcx, [rbp+var_20]; DestinationString
0x1400dd57a  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400dd57e  call    cs:__imp_RtlInitAnsiString
0x1400dd585  nop     dword ptr [rax+rax+00h]
0x1400dd58a  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x1400dd58e  lea     rcx, [rbp+var_10]
0x1400dd592  movdqa  [rbp+var_10], xmm0
0x1400dd597  call    InitializeTelemetryAssertsKMWorkerInternal
0x1400dd59c  mov     ebx, eax
0x1400dd59e  lea     rcx, [rbp+AnsiString]; AnsiString
0x1400dd5a2  call    cs:__imp_RtlFreeAnsiString
0x1400dd5a9  nop     dword ptr [rax+rax+00h]
0x1400dd5ae  mov     eax, ebx
0x1400dd5b0  mov     rbx, [rsp+60h+arg_0]
0x1400dd5b5  add     rsp, 60h
0x1400dd5b9  pop     rbp
0x1400dd5ba  retn
```
