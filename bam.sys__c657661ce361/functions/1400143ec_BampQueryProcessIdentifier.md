# BampQueryProcessIdentifier

- ea: `0x1400143ec`
- end: `0x14001463f`
- name: `BampQueryProcessIdentifier`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012530`

## callees

- `0x1400143ec`

## import_xrefs

- `ntoskrnl!PsReferencePrimaryToken` at `0x14001441a`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14001441a`
- `ntoskrnl!ObfDereferenceObject` at `0x140014558`
- `ntoskrnl!ObfDereferenceObject` at `0x140014558`
- `ntoskrnl!ExAllocatePool2` at `0x140014470`
- `ntoskrnl!ExAllocatePool2` at `0x14001450d`
- `ntoskrnl!ExAllocatePool2` at `0x1400145e1`
- `ntoskrnl!ExAllocatePool2` at `0x140014470`
- `ntoskrnl!ExAllocatePool2` at `0x14001450d`
- `ntoskrnl!ExAllocatePool2` at `0x1400145e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014571`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001458a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014571`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001458a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145c6`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14001460d`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14001460d`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140014448`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400144b3`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140014448`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400144b3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001453c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001453c`

## pseudocode

```c
__int64 __fastcall BampQueryProcessIdentifier(struct _KPROCESS *a1, void *a2, char a3, _QWORD *a4)
{
  void *v4; // rdi
  __int64 v7; // rsi
  PACCESS_TOKEN v8; // r15
  int v9; // ebx
  __int64 Pool2; // rax
  __int64 v11; // rax
  const UNICODE_STRING *v12; // rbx
  struct _UNICODE_STRING *v13; // rax
  ULONG v15; // r9d
  void *i; // r8
  __int64 v17; // rax
  NTSTATUS v18; // eax
  ULONG ProcessInformationLength; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  ProcessInformationLength = 0;
  if ( a3 )
  {
    v7 = 0;
    v8 = PsReferencePrimaryToken(a1);
    v9 = SeQuerySecurityAttributesToken(v8, &qword_140004020, 1, 0, 0, &ProcessInformationLength);
    if ( v9 != -1073741789 )
      goto LABEL_13;
    Pool2 = ExAllocatePool2(256, ProcessInformationLength, 1265459522);
    v7 = Pool2;
    if ( !Pool2 )
      goto LABEL_4;
    v9 = SeQuerySecurityAttributesToken(
           v8,
           &qword_140004020,
           1,
           Pool2,
           ProcessInformationLength,
           &ProcessInformationLength);
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)(v7 + 4) == 1 )
      {
        v11 = *(_QWORD *)(v7 + 8);
        if ( *(_WORD *)(v11 + 16) == 3 && *(_DWORD *)(v11 + 24) >= 3u )
        {
          v12 = *(const UNICODE_STRING **)(v11 + 32);
          ProcessInformationLength = v12[2].MaximumLength + 16;
          v13 = (struct _UNICODE_STRING *)ExAllocatePool2(256, ProcessInformationLength, 1265459522);
          v4 = v13;
          if ( !v13 )
          {
LABEL_4:
            v9 = -1073741670;
            goto LABEL_13;
          }
          v13->MaximumLength = v12[2].MaximumLength;
          v13->Buffer = &v13[1].Length;
          RtlCopyUnicodeString(v13, v12 + 2);
          *a4 = v4;
          v4 = 0;
          v9 = 0;
        }
        else
        {
          v9 = -1073739509;
        }
      }
      else
      {
        v9 = -1073741275;
      }
    }
LABEL_13:
    if ( v8 )
      ObfDereferenceObject(v8);
    if ( v7 )
    {
      ExFreePoolWithTag((PVOID)v7, 0x4B6D6142u);
LABEL_17:
      if ( v4 )
        ExFreePoolWithTag(v4, 0x4B6D6142u);
    }
    return (unsigned int)v9;
  }
  v15 = 0;
  for ( i = 0; ; i = (void *)v17 )
  {
    v18 = ZwQueryInformationProcess(a2, ProcessImageFileName, i, v15, &ProcessInformationLength);
    v9 = v18;
    if ( v18 != -1073741820 )
      break;
    if ( v4 )
      ExFreePoolWithTag(v4, 0x4B6D6142u);
    v17 = ExAllocatePool2(256, ProcessInformationLength, 1265459522);
    v4 = (void *)v17;
    if ( !v17 )
      return (unsigned int)-1073741670;
    v15 = ProcessInformationLength;
  }
  if ( v18 < 0 )
    goto LABEL_17;
  *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x1400143ec  mov     [rsp+arg_0], rbx
0x1400143f1  mov     [rsp+arg_8], rsi
0x1400143f6  push    rdi
0x1400143f7  push    r12
0x1400143f9  push    r15
0x1400143fb  sub     rsp, 30h
0x1400143ff  xor     edi, edi
0x140014401  mov     [rsp+48h+ProcessInformationLength], 0
0x140014409  mov     r12, r9
0x14001440c  mov     rsi, rdx
0x14001440f  test    r8b, r8b
0x140014412  jz      loc_1400145AD
0x140014418  xor     esi, esi
0x14001441a  call    cs:__imp_PsReferencePrimaryToken
0x140014421  nop     dword ptr [rax+rax+00h]
0x140014426  xor     r9d, r9d
0x140014429  lea     r8d, [rdi+1]
0x14001442d  mov     r15, rax
0x140014430  lea     rdx, qword_140004020
0x140014437  lea     rax, [rsp+48h+ProcessInformationLength]
0x14001443c  mov     rcx, r15
0x14001443f  mov     [rsp+48h+var_20], rax
0x140014444  mov     dword ptr [rsp+48h+ReturnLength], esi
0x140014448  call    cs:__imp_SeQuerySecurityAttributesToken
0x14001444f  nop     dword ptr [rax+rax+00h]
0x140014454  mov     ebx, eax
0x140014456  cmp     eax, 0C0000023h
0x14001445b  jnz     loc_140014550
0x140014461  mov     edx, [rsp+48h+ProcessInformationLength]
0x140014465  mov     ecx, 100h
0x14001446a  mov     r8d, 4B6D6142h
0x140014470  call    cs:__imp_ExAllocatePool2
0x140014477  nop     dword ptr [rax+rax+00h]
0x14001447c  mov     rsi, rax
0x14001447f  test    rax, rax
0x140014482  jnz     short loc_14001448E
0x140014484  mov     ebx, 0C000009Ah
0x140014489  jmp     loc_140014550
0x14001448e  lea     rax, [rsp+48h+ProcessInformationLength]
0x140014493  mov     r9, rsi
0x140014496  mov     [rsp+48h+var_20], rax
0x14001449b  lea     rdx, qword_140004020
0x1400144a2  mov     eax, [rsp+48h+ProcessInformationLength]
0x1400144a6  mov     r8d, 1
0x1400144ac  mov     rcx, r15
0x1400144af  mov     dword ptr [rsp+48h+ReturnLength], eax
0x1400144b3  call    cs:__imp_SeQuerySecurityAttributesToken
0x1400144ba  nop     dword ptr [rax+rax+00h]
0x1400144bf  mov     ebx, eax
0x1400144c1  test    eax, eax
0x1400144c3  js      loc_140014550
0x1400144c9  cmp     dword ptr [rsi+4], 1
0x1400144cd  jz      short loc_1400144D6
0x1400144cf  mov     ebx, 0C0000225h
0x1400144d4  jmp     short loc_140014550
0x1400144d6  mov     rax, [rsi+8]
0x1400144da  mov     ecx, 3
0x1400144df  cmp     [rax+10h], cx
0x1400144e3  jz      short loc_1400144EC
0x1400144e5  mov     ebx, 0C000090Bh
0x1400144ea  jmp     short loc_140014550
0x1400144ec  cmp     [rax+18h], ecx
0x1400144ef  jb      short loc_1400144E5
0x1400144f1  mov     rbx, [rax+20h]
0x1400144f5  mov     ecx, 100h
0x1400144fa  mov     r8d, 4B6D6142h
0x140014500  movzx   eax, word ptr [rbx+22h]
0x140014504  add     eax, 10h
0x140014507  mov     edx, eax
0x140014509  mov     [rsp+48h+ProcessInformationLength], eax
0x14001450d  call    cs:__imp_ExAllocatePool2
0x140014514  nop     dword ptr [rax+rax+00h]
0x140014519  mov     rdi, rax
0x14001451c  test    rax, rax
0x14001451f  jz      loc_140014484
0x140014525  movzx   eax, word ptr [rbx+22h]
0x140014529  lea     rdx, [rbx+20h]; SourceString
0x14001452d  mov     [rdi+2], ax
0x140014531  mov     rcx, rdi; DestinationString
0x140014534  lea     rax, [rdi+10h]
0x140014538  mov     [rdi+8], rax
0x14001453c  call    cs:__imp_RtlCopyUnicodeString
0x140014543  nop     dword ptr [rax+rax+00h]
0x140014548  mov     [r12], rdi
0x14001454c  xor     edi, edi
0x14001454e  xor     ebx, ebx
0x140014550  test    r15, r15
0x140014553  jz      short loc_140014564
0x140014555  mov     rcx, r15; Object
0x140014558  call    cs:__imp_ObfDereferenceObject
0x14001455f  nop     dword ptr [rax+rax+00h]
0x140014564  test    rsi, rsi
0x140014567  jz      short loc_140014596
0x140014569  mov     edx, 4B6D6142h; Tag
0x14001456e  mov     rcx, rsi; P
0x140014571  call    cs:__imp_ExFreePoolWithTag
0x140014578  nop     dword ptr [rax+rax+00h]
0x14001457d  test    rdi, rdi
0x140014580  jz      short loc_140014596
0x140014582  mov     edx, 4B6D6142h; Tag
0x140014587  mov     rcx, rdi; P
0x14001458a  call    cs:__imp_ExFreePoolWithTag
0x140014591  nop     dword ptr [rax+rax+00h]
0x140014596  mov     rsi, [rsp+48h+arg_8]
0x14001459b  mov     eax, ebx
0x14001459d  mov     rbx, [rsp+48h+arg_0]
0x1400145a2  add     rsp, 30h
0x1400145a6  pop     r15
0x1400145a8  pop     r12
0x1400145aa  pop     rdi
0x1400145ab  retn
0x1400145ad  xor     r9d, r9d
0x1400145b0  xor     r8d, r8d
0x1400145b3  lea     r15d, [r9+1Bh]
0x1400145b7  jmp     short loc_1400145FD
0x1400145b9  test    rdi, rdi
0x1400145bc  jz      short loc_1400145D2
0x1400145be  mov     edx, 4B6D6142h; Tag
0x1400145c3  mov     rcx, rdi; P
0x1400145c6  call    cs:__imp_ExFreePoolWithTag
0x1400145cd  nop     dword ptr [rax+rax+00h]
0x1400145d2  mov     edx, [rsp+48h+ProcessInformationLength]
0x1400145d6  mov     ecx, 100h
0x1400145db  mov     r8d, 4B6D6142h
0x1400145e1  call    cs:__imp_ExAllocatePool2
0x1400145e8  nop     dword ptr [rax+rax+00h]
0x1400145ed  mov     rdi, rax
0x1400145f0  test    rax, rax
0x1400145f3  jz      short loc_140014635
0x1400145f5  mov     r9d, [rsp+48h+ProcessInformationLength]; ProcessInformationLength
0x1400145fa  mov     r8, rax; ProcessInformation
0x1400145fd  lea     rax, [rsp+48h+ProcessInformationLength]
0x140014602  mov     edx, r15d; ProcessInformationClass
0x140014605  mov     rcx, rsi; ProcessHandle
0x140014608  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001460d  call    cs:__imp_ZwQueryInformationProcess
0x140014614  nop     dword ptr [rax+rax+00h]
0x140014619  mov     ebx, eax
0x14001461b  cmp     eax, 0C0000004h
0x140014620  jz      short loc_1400145B9
0x140014622  test    eax, eax
0x140014624  js      loc_14001457D
0x14001462a  mov     [r12], rdi
0x14001462e  xor     ebx, ebx
0x140014630  jmp     loc_140014596
0x140014635  mov     ebx, 0C000009Ah
0x14001463a  jmp     loc_140014596
```
