# InitializeTelemetryAssertsKM

- ea: `0x1400545dc`
- end: `0x140054782`
- name: `InitializeTelemetryAssertsKM`
- size: `422`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400b6080`

## callees

- `0x1400545dc`
- `0x140054788`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x140054617`
- `ntoskrnl!RtlInitAnsiString` at `0x14005472f`
- `ntoskrnl!RtlInitAnsiString` at `0x140054617`
- `ntoskrnl!RtlInitAnsiString` at `0x14005472f`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400546dc`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400546dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400546bb`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400546bb`
- `ntoskrnl!RtlFreeAnsiString` at `0x140054753`
- `ntoskrnl!RtlFreeAnsiString` at `0x140054753`
- `ntoskrnl!ExAllocatePool2` at `0x140054635`
- `ntoskrnl!ExAllocatePool2` at `0x140054635`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400546f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054767`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400546f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054767`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005466a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005466a`

## string_xrefs

- `0x140054685`: `ImagePath`

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
0x1400545dc  push    rbp
0x1400545de  push    rbx
0x1400545df  push    rsi
0x1400545e0  push    rdi
0x1400545e1  lea     rbp, [rsp-3Fh]
0x1400545e6  sub     rsp, 0E8h
0x1400545ed  xorps   xmm0, xmm0
0x1400545f0  mov     rsi, rcx
0x1400545f3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400545f7  xor     eax, eax
0x1400545f9  lock xadd cs:g_AssertsOperational, eax
0x140054601  test    eax, eax
0x140054603  jz      short loc_14005460C
0x140054605  xor     eax, eax
0x140054607  jmp     loc_140054775
0x14005460c  xor     edx, edx; SourceString
0x14005460e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140054612  mov     ebx, 0C0000017h
0x140054617  call    cs:__imp_RtlInitAnsiString
0x14005461e  nop     dword ptr [rax+rax+00h]
0x140054623  movzx   edx, word ptr [rsi]
0x140054626  mov     ecx, 40h ; '@'
0x14005462b  add     rdx, 2
0x14005462f  mov     r8d, 74727341h
0x140054635  call    cs:__imp_ExAllocatePool2
0x14005463c  nop     dword ptr [rax+rax+00h]
0x140054641  mov     rdi, rax
0x140054644  test    rax, rax
0x140054647  jz      loc_140054773
0x14005464d  movzx   r8d, word ptr [rsi]; Size
0x140054651  mov     rcx, rax; void *
0x140054654  mov     rdx, [rsi+8]; Src
0x140054658  call    memmove
0x14005465d  xorps   xmm0, xmm0
0x140054660  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140054664  xor     edx, edx; SourceString
0x140054666  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x14005466a  call    cs:__imp_RtlInitUnicodeString
0x140054671  nop     dword ptr [rax+rax+00h]
0x140054676  xor     edx, edx; Val
0x140054678  lea     rcx, [rbp+57h+var_90]; void *
0x14005467c  lea     r8d, [rdx+70h]; Size
0x140054680  call    memset
0x140054685  lea     rax, aImagepath; "ImagePath"
0x14005468c  mov     [rbp+57h+var_88], 20h ; ' '
0x140054693  mov     [rbp+57h+var_80], rax
0x140054697  lea     r8, [rbp+57h+var_90]
0x14005469b  lea     rax, [rbp+57h+SourceString]
0x14005469f  mov     [rbp+57h+var_70], 2
0x1400546a6  xor     r9d, r9d
0x1400546a9  mov     [rbp+57h+var_78], rax
0x1400546ad  mov     rdx, rdi
0x1400546b0  mov     [rsp+100h+var_E0], 0
0x1400546b9  xor     ecx, ecx
0x1400546bb  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400546c2  nop     dword ptr [rax+rax+00h]
0x1400546c7  mov     ebx, eax
0x1400546c9  test    eax, eax
0x1400546cb  js      loc_14005475F
0x1400546d1  mov     r8b, 1; AllocateDestinationString
0x1400546d4  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1400546d8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400546dc  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400546e3  nop     dword ptr [rax+rax+00h]
0x1400546e8  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x1400546ec  xor     edx, edx; Tag
0x1400546ee  mov     ebx, eax
0x1400546f0  call    cs:__imp_ExFreePoolWithTag
0x1400546f7  nop     dword ptr [rax+rax+00h]
0x1400546fc  test    ebx, ebx
0x1400546fe  js      short loc_14005475F
0x140054700  movzx   edx, [rbp+57h+DestinationString.Length]
0x140054704  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140054708  lea     ecx, [rdx-1]
0x14005470b  test    ecx, ecx
0x14005470d  jz      short loc_14005474F
0x14005470f  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140054714  jz      short loc_14005471A
0x140054716  dec     ecx
0x140054718  jmp     short loc_14005470B
0x14005471a  cmp     ecx, edx
0x14005471c  jz      short loc_14005474F
0x14005471e  lea     edx, [rcx+1]
0x140054721  xorps   xmm0, xmm0
0x140054724  add     rdx, r8; SourceString
0x140054727  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x14005472b  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x14005472f  call    cs:__imp_RtlInitAnsiString
0x140054736  nop     dword ptr [rax+rax+00h]
0x14005473b  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x14005473f  lea     rcx, [rbp+57h+var_A0]
0x140054743  movdqa  [rbp+57h+var_A0], xmm0
0x140054748  call    InitializeTelemetryAssertsKMWorkerInternal
0x14005474d  mov     ebx, eax
0x14005474f  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x140054753  call    cs:__imp_RtlFreeAnsiString
0x14005475a  nop     dword ptr [rax+rax+00h]
0x14005475f  mov     edx, 74727341h; Tag
0x140054764  mov     rcx, rdi; P
0x140054767  call    cs:__imp_ExFreePoolWithTag
0x14005476e  nop     dword ptr [rax+rax+00h]
0x140054773  mov     eax, ebx
0x140054775  add     rsp, 0E8h
0x14005477c  pop     rdi
0x14005477d  pop     rsi
0x14005477e  pop     rbx
0x14005477f  pop     rbp
0x140054780  retn
```
