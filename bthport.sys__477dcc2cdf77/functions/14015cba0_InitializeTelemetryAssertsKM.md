# InitializeTelemetryAssertsKM

- ea: `0x14015cba0`
- end: `0x14015cd46`
- name: `InitializeTelemetryAssertsKM`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1402104e4`

## callees

- `0x14015cba0`
- `0x14015cd4c`
- `0x140165640`
- `0x140165940`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x14015cbdb`
- `ntoskrnl!RtlInitAnsiString` at `0x14015ccf3`
- `ntoskrnl!RtlInitAnsiString` at `0x14015cbdb`
- `ntoskrnl!RtlInitAnsiString` at `0x14015ccf3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14015cc7f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14015cc7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ccb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015ccb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015cd2b`
- `ntoskrnl!ExAllocatePool2` at `0x14015cbf9`
- `ntoskrnl!ExAllocatePool2` at `0x14015cbf9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14015cc2e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14015cc2e`
- `ntoskrnl!RtlFreeAnsiString` at `0x14015cd17`
- `ntoskrnl!RtlFreeAnsiString` at `0x14015cd17`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14015cca0`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14015cca0`

## string_xrefs

- `0x14015cc49`: `ImagePath`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKM(const void **a1)
{
  NTSTATUS RegistryValues; // ebx
  void *Pool2; // rax
  void *v5; // rdi
  __int64 i; // rcx
  struct _STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-69h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-59h] BYREF
  struct _STRING v10; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v11[18]; // [rsp+70h] [rbp-39h] BYREF

  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RegistryValues = -1073741801;
  RtlInitAnsiString(&DestinationString, 0);
  Pool2 = (void *)ExAllocatePool2(64, *(unsigned __int16 *)a1 + 2LL, 1953657665);
  v5 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, a1[1], *(unsigned __int16 *)a1);
    SourceString = 0;
    RtlInitUnicodeString(&SourceString, 0);
    memset(v11, 0, 0x70u);
    LODWORD(v11[1]) = 32;
    v11[2] = L"ImagePath";
    LODWORD(v11[4]) = 2;
    v11[3] = &SourceString;
    RegistryValues = RtlQueryRegistryValuesEx(0, v5, v11, 0, 0);
    if ( RegistryValues >= 0 )
    {
      RegistryValues = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
      ExFreePoolWithTag(SourceString.Buffer, 0);
      if ( RegistryValues >= 0 )
      {
        for ( i = (unsigned int)DestinationString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
        {
          if ( DestinationString.Buffer[i] == 92 )
          {
            if ( (_DWORD)i != DestinationString.Length )
            {
              v9 = 0;
              RtlInitAnsiString(&v9, &DestinationString.Buffer[(unsigned int)(i + 1)]);
              v10 = v9;
              RegistryValues = InitializeTelemetryAssertsKMWorkerInternal(&v10);
            }
            break;
          }
        }
        RtlFreeAnsiString(&DestinationString);
      }
    }
    ExFreePoolWithTag(v5, 0x74727341u);
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x14015cba0  push    rbp
0x14015cba2  push    rbx
0x14015cba3  push    rsi
0x14015cba4  push    rdi
0x14015cba5  lea     rbp, [rsp-3Fh]
0x14015cbaa  sub     rsp, 0E8h
0x14015cbb1  xorps   xmm0, xmm0
0x14015cbb4  mov     rsi, rcx
0x14015cbb7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14015cbbb  xor     eax, eax
0x14015cbbd  lock xadd cs:g_AssertsOperational, eax
0x14015cbc5  test    eax, eax
0x14015cbc7  jz      short loc_14015CBD0
0x14015cbc9  xor     eax, eax
0x14015cbcb  jmp     loc_14015CD39
0x14015cbd0  xor     edx, edx; SourceString
0x14015cbd2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14015cbd6  mov     ebx, 0C0000017h
0x14015cbdb  call    cs:__imp_RtlInitAnsiString
0x14015cbe2  nop     dword ptr [rax+rax+00h]
0x14015cbe7  movzx   edx, word ptr [rsi]
0x14015cbea  mov     ecx, 40h ; '@'
0x14015cbef  add     rdx, 2
0x14015cbf3  mov     r8d, 74727341h
0x14015cbf9  call    cs:__imp_ExAllocatePool2
0x14015cc00  nop     dword ptr [rax+rax+00h]
0x14015cc05  mov     rdi, rax
0x14015cc08  test    rax, rax
0x14015cc0b  jz      loc_14015CD37
0x14015cc11  movzx   r8d, word ptr [rsi]; Size
0x14015cc15  mov     rcx, rax; void *
0x14015cc18  mov     rdx, [rsi+8]; Src
0x14015cc1c  call    memmove
0x14015cc21  xorps   xmm0, xmm0
0x14015cc24  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14015cc28  xor     edx, edx; SourceString
0x14015cc2a  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x14015cc2e  call    cs:__imp_RtlInitUnicodeString
0x14015cc35  nop     dword ptr [rax+rax+00h]
0x14015cc3a  xor     edx, edx; Val
0x14015cc3c  lea     rcx, [rbp+57h+var_90]; void *
0x14015cc40  lea     r8d, [rdx+70h]; Size
0x14015cc44  call    memset
0x14015cc49  lea     rax, aImagepath; "ImagePath"
0x14015cc50  mov     [rbp+57h+var_88], 20h ; ' '
0x14015cc57  mov     [rbp+57h+var_80], rax
0x14015cc5b  lea     r8, [rbp+57h+var_90]
0x14015cc5f  lea     rax, [rbp+57h+SourceString]
0x14015cc63  mov     [rbp+57h+var_70], 2
0x14015cc6a  xor     r9d, r9d
0x14015cc6d  mov     [rbp+57h+var_78], rax
0x14015cc71  mov     rdx, rdi
0x14015cc74  mov     [rsp+100h+var_E0], 0
0x14015cc7d  xor     ecx, ecx
0x14015cc7f  call    cs:__imp_RtlQueryRegistryValuesEx
0x14015cc86  nop     dword ptr [rax+rax+00h]
0x14015cc8b  mov     ebx, eax
0x14015cc8d  test    eax, eax
0x14015cc8f  js      loc_14015CD23
0x14015cc95  mov     r8b, 1; AllocateDestinationString
0x14015cc98  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14015cc9c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14015cca0  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14015cca7  nop     dword ptr [rax+rax+00h]
0x14015ccac  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x14015ccb0  xor     edx, edx; Tag
0x14015ccb2  mov     ebx, eax
0x14015ccb4  call    cs:__imp_ExFreePoolWithTag
0x14015ccbb  nop     dword ptr [rax+rax+00h]
0x14015ccc0  test    ebx, ebx
0x14015ccc2  js      short loc_14015CD23
0x14015ccc4  movzx   edx, [rbp+57h+DestinationString.Length]
0x14015ccc8  mov     r8, [rbp+57h+DestinationString.Buffer]
0x14015cccc  lea     ecx, [rdx-1]
0x14015cccf  test    ecx, ecx
0x14015ccd1  jz      short loc_14015CD13
0x14015ccd3  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14015ccd8  jz      short loc_14015CCDE
0x14015ccda  dec     ecx
0x14015ccdc  jmp     short loc_14015CCCF
0x14015ccde  cmp     ecx, edx
0x14015cce0  jz      short loc_14015CD13
0x14015cce2  lea     edx, [rcx+1]
0x14015cce5  xorps   xmm0, xmm0
0x14015cce8  add     rdx, r8; SourceString
0x14015cceb  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x14015ccef  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x14015ccf3  call    cs:__imp_RtlInitAnsiString
0x14015ccfa  nop     dword ptr [rax+rax+00h]
0x14015ccff  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x14015cd03  lea     rcx, [rbp+57h+var_A0]
0x14015cd07  movdqa  [rbp+57h+var_A0], xmm0
0x14015cd0c  call    InitializeTelemetryAssertsKMWorkerInternal
0x14015cd11  mov     ebx, eax
0x14015cd13  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x14015cd17  call    cs:__imp_RtlFreeAnsiString
0x14015cd1e  nop     dword ptr [rax+rax+00h]
0x14015cd23  mov     edx, 74727341h; Tag
0x14015cd28  mov     rcx, rdi; P
0x14015cd2b  call    cs:__imp_ExFreePoolWithTag
0x14015cd32  nop     dword ptr [rax+rax+00h]
0x14015cd37  mov     eax, ebx
0x14015cd39  add     rsp, 0E8h
0x14015cd40  pop     rdi
0x14015cd41  pop     rsi
0x14015cd42  pop     rbx
0x14015cd43  pop     rbp
0x14015cd44  retn
```
