# SIPolicyPmGetSystemPartitionPolicyFolderCommon

- ea: `0x18002285c`
- end: `0x1800229f8`
- name: `SIPolicyPmGetSystemPartitionPolicyFolderCommon`
- size: `412`
- prototype: `__int64 __fastcall(SYSTEM_INFORMATION_CLASS SystemInformationClass, struct _UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002282c`
- `0x180022a00`

## callees

- `0x18002285c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800228d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800228d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022905`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022946`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022946`
- `ntdll!ZwQuerySystemInformation` at `0x1800228ba`
- `ntdll!ZwQuerySystemInformation` at `0x1800228ba`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022967`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002297b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022993`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800229b0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800229c7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022967`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002297b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180022993`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800229b0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800229c7`
- `ntdll!RtlInitUnicodeString` at `0x1800229e6`
- `ntdll!RtlInitUnicodeString` at `0x1800229e6`
- `ntdll!RtlFreeUnicodeString` at `0x1800228fc`
- `ntdll!RtlFreeUnicodeString` at `0x1800228fc`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetSystemPartitionPolicyFolderCommon(
        SYSTEM_INFORMATION_CLASS SystemInformationClass,
        struct _UNICODE_STRING *a2,
        const UNICODE_STRING *a3)
{
  SIZE_T v4; // rdx
  NTSTATUS v7; // eax
  NTSTATUS appended; // ebx
  UNICODE_STRING *v9; // rax
  UNICODE_STRING *v10; // rdi
  int Length; // ecx
  SIZE_T v13; // rbx
  WCHAR *v14; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING v16; // [rsp+30h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-18h] BYREF
  ULONG ReturnLength; // [rsp+A8h] [rbp+50h] BYREF

  *(_QWORD *)&Source.Length = 262146;
  Source.Buffer = L"\\";
  *(_QWORD *)&v16.Length = 2490404;
  v16.Buffer = L"EFI\\Microsoft\\Boot";
  v4 = 520;
  ReturnLength = 520;
  UnicodeString = 0;
  while ( 1 )
  {
    v9 = (UNICODE_STRING *)LocalAlloc(0x40u, v4);
    v10 = v9;
    if ( !v9 )
      goto LABEL_7;
    v7 = ZwQuerySystemInformation(SystemInformationClass, v9, ReturnLength, &ReturnLength);
    appended = v7;
    if ( v7 >= 0 )
      break;
    if ( v7 == -1073740718 )
    {
      appended = -1073741275;
      goto LABEL_8;
    }
    if ( v7 != -1073741789 )
      goto LABEL_8;
    LocalFree(v10);
    v4 = ReturnLength;
  }
  if ( a3 )
    Length = a3->Length;
  else
    Length = 0;
  v13 = Length + v10->Length + 2 * ((unsigned int)v16.Length + 3);
  v14 = (WCHAR *)LocalAlloc(0x40u, v13);
  if ( !v14 )
  {
LABEL_7:
    appended = -1073741801;
    goto LABEL_8;
  }
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.MaximumLength = v13;
  UnicodeString.Buffer = v14;
  appended = RtlAppendUnicodeStringToString(&UnicodeString, v10);
  if ( appended >= 0 )
  {
    appended = RtlAppendUnicodeStringToString(&UnicodeString, &Source);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&UnicodeString, &v16);
      if ( appended >= 0 )
      {
        if ( !a3
          || (appended = RtlAppendUnicodeStringToString(&UnicodeString, &Source), appended >= 0)
          && (appended = RtlAppendUnicodeStringToString(&UnicodeString, a3), appended >= 0) )
        {
          *a2 = UnicodeString;
          RtlInitUnicodeString(&UnicodeString, 0);
          a2[1].Length = 0;
        }
      }
    }
  }
LABEL_8:
  RtlFreeUnicodeString(&UnicodeString);
  LocalFree(v10);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18002285c  push    rbp
0x18002285e  push    rbx
0x18002285f  push    rsi
0x180022860  push    rdi
0x180022861  push    r14
0x180022863  push    r15
0x180022865  mov     rbp, rsp
0x180022868  sub     rsp, 58h
0x18002286c  lea     rax, asc_18002ED88; "\\"
0x180022873  mov     qword ptr [rbp+Source.Length], 40002h
0x18002287b  mov     [rbp+Source.Buffer], rax
0x18002287f  mov     r14, rdx
0x180022882  lea     rax, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot"
0x180022889  mov     qword ptr [rbp+var_28.Length], 260024h
0x180022891  xorps   xmm0, xmm0
0x180022894  mov     [rbp+var_28.Buffer], rax
0x180022898  mov     edx, 208h
0x18002289d  mov     rsi, r8
0x1800228a0  mov     r15d, ecx
0x1800228a3  mov     [rbp+ReturnLength], edx
0x1800228a6  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800228aa  jmp     short loc_1800228E0
0x1800228ac  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x1800228b0  lea     r9, [rbp+ReturnLength]; ReturnLength
0x1800228b4  mov     rdx, rdi; SystemInformation
0x1800228b7  mov     ecx, r15d; SystemInformationClass
0x1800228ba  call    cs:__imp_ZwQuerySystemInformation
0x1800228c0  mov     ebx, eax
0x1800228c2  test    eax, eax
0x1800228c4  jns     short loc_180022921
0x1800228c6  cmp     eax, 0C0000452h
0x1800228cb  jz      short loc_18002291A
0x1800228cd  cmp     eax, 0C0000023h
0x1800228d2  jnz     short loc_1800228F8
0x1800228d4  mov     rcx, rdi; hMem
0x1800228d7  call    cs:__imp_LocalFree
0x1800228dd  mov     edx, [rbp+ReturnLength]; uBytes
0x1800228e0  mov     ecx, 40h ; '@'; uFlags
0x1800228e5  call    cs:__imp_LocalAlloc
0x1800228eb  mov     rdi, rax
0x1800228ee  test    rax, rax
0x1800228f1  jnz     short loc_1800228AC
0x1800228f3  mov     ebx, 0C0000017h
0x1800228f8  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800228fc  call    cs:__imp_RtlFreeUnicodeString
0x180022902  mov     rcx, rdi; hMem
0x180022905  call    cs:__imp_LocalFree
0x18002290b  mov     eax, ebx
0x18002290d  add     rsp, 58h
0x180022911  pop     r15
0x180022913  pop     r14
0x180022915  pop     rdi
0x180022916  pop     rsi
0x180022917  pop     rbx
0x180022918  pop     rbp
0x180022919  retn
0x18002291a  mov     ebx, 0C0000225h
0x18002291f  jmp     short loc_1800228F8
0x180022921  test    rsi, rsi
0x180022924  jz      short loc_18002292B
0x180022926  movzx   ecx, word ptr [rsi]
0x180022929  jmp     short loc_18002292D
0x18002292b  xor     ecx, ecx
0x18002292d  movzx   edx, word ptr [rdi]
0x180022930  movzx   r8d, [rbp+var_28.Length]
0x180022935  add     edx, ecx
0x180022937  add     r8d, 3
0x18002293b  mov     ecx, 40h ; '@'; uFlags
0x180022940  lea     ebx, [rdx+r8*2]
0x180022944  mov     edx, ebx; uBytes
0x180022946  call    cs:__imp_LocalAlloc
0x18002294c  test    rax, rax
0x18002294f  jz      short loc_1800228F3
0x180022951  xorps   xmm0, xmm0
0x180022954  lea     rcx, [rbp+UnicodeString]; Destination
0x180022958  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18002295c  mov     rdx, rdi; Source
0x18002295f  mov     [rbp+UnicodeString.MaximumLength], bx
0x180022963  mov     [rbp+UnicodeString.Buffer], rax
0x180022967  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002296d  mov     ebx, eax
0x18002296f  test    eax, eax
0x180022971  js      short loc_1800228F8
0x180022973  lea     rdx, [rbp+Source]; Source
0x180022977  lea     rcx, [rbp+UnicodeString]; Destination
0x18002297b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180022981  mov     ebx, eax
0x180022983  test    eax, eax
0x180022985  js      loc_1800228F8
0x18002298b  lea     rdx, [rbp+var_28]; Source
0x18002298f  lea     rcx, [rbp+UnicodeString]; Destination
0x180022993  call    cs:__imp_RtlAppendUnicodeStringToString
0x180022999  mov     ebx, eax
0x18002299b  test    eax, eax
0x18002299d  js      loc_1800228F8
0x1800229a3  test    rsi, rsi
0x1800229a6  jz      short loc_1800229D7
0x1800229a8  lea     rdx, [rbp+Source]; Source
0x1800229ac  lea     rcx, [rbp+UnicodeString]; Destination
0x1800229b0  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800229b6  mov     ebx, eax
0x1800229b8  test    eax, eax
0x1800229ba  js      loc_1800228F8
0x1800229c0  mov     rdx, rsi; Source
0x1800229c3  lea     rcx, [rbp+UnicodeString]; Destination
0x1800229c7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800229cd  mov     ebx, eax
0x1800229cf  test    eax, eax
0x1800229d1  js      loc_1800228F8
0x1800229d7  movups  xmm0, xmmword ptr [rbp+UnicodeString.Length]
0x1800229db  xor     edx, edx; SourceString
0x1800229dd  lea     rcx, [rbp+UnicodeString]; DestinationString
0x1800229e1  movdqu  xmmword ptr [r14], xmm0
0x1800229e6  call    cs:__imp_RtlInitUnicodeString
0x1800229ec  mov     word ptr [r14+10h], 0
0x1800229f3  jmp     loc_1800228F8
```
