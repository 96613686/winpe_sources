# SIPolicyPmBuildPathFromPolicyID

- ea: `0x180020b44`
- end: `0x180020e19`
- name: `SIPolicyPmBuildPathFromPolicyID`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD *, const UNICODE_STRING *, char, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180021270`
- `0x18002195c`
- `0x180021a38`
- `0x180021af4`
- `0x180021bd8`
- `0x180021e34`
- `0x180021f5c`
- `0x180021ffc`

## callees

- `0x180020b44`
- `0x18002121c`
- `0x180021608`
- `0x180021680`
- `0x180022404`
- `0x18002282c`
- `0x180022a00`
- `0x180022ca4`
- `0x180022f2c`
- `0x180023e30`
- `0x1800241f8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180020d7b`
- `ntdll!RtlInitUnicodeString` at `0x180020d95`
- `ntdll!RtlInitUnicodeString` at `0x180020dae`
- `ntdll!RtlInitUnicodeString` at `0x180020d7b`
- `ntdll!RtlInitUnicodeString` at `0x180020d95`
- `ntdll!RtlInitUnicodeString` at `0x180020dae`
- `ntdll!RtlFreeUnicodeString` at `0x180020db9`
- `ntdll!RtlFreeUnicodeString` at `0x180020dc3`
- `ntdll!RtlFreeUnicodeString` at `0x180020dcd`
- `ntdll!RtlFreeUnicodeString` at `0x180020dd7`
- `ntdll!RtlFreeUnicodeString` at `0x180020db9`
- `ntdll!RtlFreeUnicodeString` at `0x180020dc3`
- `ntdll!RtlFreeUnicodeString` at `0x180020dcd`
- `ntdll!RtlFreeUnicodeString` at `0x180020dd7`

## string_xrefs

- `0x180020b9f`: `Tokens\Active`
- `0x180020bc7`: `Tokens\Staged`

## pseudocode

```c
__int64 __fastcall SIPolicyPmBuildPathFromPolicyID(
        _QWORD *a1,
        const UNICODE_STRING *a2,
        char a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6)
{
  char IsLegacyPolicyID; // si
  __int64 v10; // rcx
  int ExpectedFilename; // ebx
  _QWORD *v12; // rdi
  _QWORD *v13; // r15
  int BootPartitionPolicyFolder10S; // eax
  _QWORD *v15; // rdx
  _QWORD *v16; // rdx
  int VirtESPPartitionPolicyFolder; // eax
  int OsDataPartitionPolicyFolder; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-C9h] BYREF
  _QWORD v21[2]; // [rsp+30h] [rbp-B9h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-A9h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-99h] BYREF
  _QWORD v24[2]; // [rsp+60h] [rbp-89h] BYREF
  struct _UNICODE_STRING v25; // [rsp+70h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-69h] BYREF
  struct _UNICODE_STRING v27; // [rsp+90h] [rbp-59h] BYREF
  UNICODE_STRING Source; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-39h]
  UNICODE_STRING v30; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-21h]
  UNICODE_STRING v32; // [rsp+D0h] [rbp-19h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-9h]

  v21[0] = 2359330;
  v24[0] = 1835034;
  v29 = 0;
  v22[0] = 2359330;
  v23[0] = 1835034;
  v21[1] = L"CiPolicies\\Active";
  v24[1] = L"Tokens\\Active";
  v33 = 0;
  v31 = 0;
  v22[1] = L"CiPolicies\\Staged";
  v23[1] = L"Tokens\\Staged";
  Source = 0;
  DestinationString = 0;
  v27 = 0;
  v25 = 0;
  UnicodeString = 0;
  v32 = 0;
  v30 = 0;
  if ( a1 )
  {
    IsLegacyPolicyID = SIPolicyIsLegacyPolicyID(a1);
    ExpectedFilename = SIPolicyGetExpectedFilename(v10, &UnicodeString);
    if ( ExpectedFilename < 0 )
      goto LABEL_46;
    v12 = v21;
    v13 = v22;
  }
  else
  {
    ExpectedFilename = SIPolicyPmGetTokenFileName(a2);
    if ( ExpectedFilename < 0 )
      goto LABEL_46;
    IsLegacyPolicyID = 0;
    v13 = v23;
    v12 = v24;
  }
  if ( !a4 )
    goto LABEL_20;
  if ( a1 && *a1 == 0x4D3DE0B55951A96ALL && a1[1] == 0x840703615B3EB88FuLL )
  {
    BootPartitionPolicyFolder10S = SIPolicyPmGetBootPartitionPolicyFolder10S(&Source);
  }
  else
  {
    v15 = 0;
    if ( a3 )
    {
      if ( !IsLegacyPolicyID )
        v15 = v12;
      BootPartitionPolicyFolder10S = SIPolicyPmGetOsDataPartitionPolicyFolder(&Source, v15);
    }
    else
    {
      if ( !IsLegacyPolicyID )
        v15 = v12;
      BootPartitionPolicyFolder10S = SIPolicyPmGetBootPartitionPolicyFolder(&Source, v15);
    }
  }
  ExpectedFilename = BootPartitionPolicyFolder10S;
  if ( BootPartitionPolicyFolder10S >= 0 )
  {
    ExpectedFilename = SIPolicyBuildPath(&Source, &UnicodeString, &DestinationString);
    if ( ExpectedFilename >= 0 )
    {
LABEL_20:
      if ( a5 )
      {
        v16 = 0;
        if ( a3 )
        {
          if ( !IsLegacyPolicyID )
            v16 = v12;
          VirtESPPartitionPolicyFolder = SIPolicyPmGetVirtESPPartitionPolicyFolder(&v30, v16);
        }
        else
        {
          if ( !IsLegacyPolicyID )
            v16 = v12;
          VirtESPPartitionPolicyFolder = SIPolicyPmGetSystemPartitionPolicyFolder(&v30, v16);
        }
        ExpectedFilename = VirtESPPartitionPolicyFolder;
        if ( VirtESPPartitionPolicyFolder >= 0 )
        {
          ExpectedFilename = SIPolicyBuildPath(&v30, &UnicodeString, &v27);
          if ( ExpectedFilename < 0 )
            goto LABEL_46;
        }
        else
        {
          if ( VirtESPPartitionPolicyFolder != -1073741275 )
            goto LABEL_46;
          ExpectedFilename = 0;
        }
      }
      if ( a6 )
      {
        if ( a3 )
          OsDataPartitionPolicyFolder = SIPolicyPmGetOsDataPartitionPolicyFolder(&v32, v13);
        else
          OsDataPartitionPolicyFolder = SIPolicyPmGetBootPartitionPolicyFolder(&v32, v13);
        ExpectedFilename = OsDataPartitionPolicyFolder;
        if ( OsDataPartitionPolicyFolder >= 0 )
        {
          ExpectedFilename = SIPolicyBuildPath(&v32, &UnicodeString, &v25);
          if ( ExpectedFilename < 0 )
            goto LABEL_46;
        }
        else
        {
          if ( OsDataPartitionPolicyFolder != -1073741275 )
            goto LABEL_46;
          ExpectedFilename = 0;
        }
      }
      if ( a4 )
      {
        *a4 = DestinationString;
        RtlInitUnicodeString(&DestinationString, 0);
      }
      if ( a5 )
      {
        *a5 = v27;
        RtlInitUnicodeString(&v27, 0);
      }
      if ( a6 )
      {
        *a6 = v25;
        RtlInitUnicodeString(&v25, 0);
      }
    }
  }
LABEL_46:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v25);
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&v27);
  SIPolicyPmFreeFileItems(&Source, 1);
  SIPolicyPmFreeFileItems(&v30, 1);
  SIPolicyPmFreeFileItems(&v32, 1);
  return (unsigned int)ExpectedFilename;
}

```

## disassembly

```asm
0x180020b44  push    rbp
0x180020b46  push    rbx
0x180020b47  push    rsi
0x180020b48  push    rdi
0x180020b49  push    r12
0x180020b4b  push    r13
0x180020b4d  push    r14
0x180020b4f  push    r15
0x180020b51  lea     rbp, [rsp-0Fh]
0x180020b56  sub     rsp, 0F8h
0x180020b5d  mov     r14, rcx
0x180020b60  mov     [rsp+130h+var_100], 240022h
0x180020b69  xor     ecx, ecx
0x180020b6b  mov     [rsp+130h+var_D0], 1C001Ah
0x180020b74  mov     [rbp+47h+var_80], rcx
0x180020b78  xorps   xmm0, xmm0
0x180020b7b  xorps   xmm1, xmm1
0x180020b7e  mov     [rsp+130h+var_F0], 240022h
0x180020b87  lea     rcx, aCipoliciesActi; "CiPolicies\\Active"
0x180020b8e  mov     [rsp+130h+var_E0], 1C001Ah
0x180020b97  mov     [rsp+130h+var_F8], rcx
0x180020b9c  mov     r13, r9
0x180020b9f  lea     rcx, aTokensActive; "Tokens\\Active"
0x180020ba6  mov     r12b, r8b
0x180020ba9  mov     [rsp+130h+var_C8], rcx
0x180020bae  mov     rax, rdx
0x180020bb1  xor     ecx, ecx
0x180020bb3  mov     [rbp+47h+var_50], rcx
0x180020bb7  mov     [rbp+47h+var_68], rcx
0x180020bbb  lea     rcx, aCipoliciesStag; "CiPolicies\\Staged"
0x180020bc2  mov     [rsp+130h+var_E8], rcx
0x180020bc7  lea     rcx, aTokensStaged; "Tokens\\Staged"
0x180020bce  mov     [rsp+130h+var_D8], rcx
0x180020bd3  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x180020bd7  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180020bdb  movups  xmmword ptr [rbp+47h+var_A0.Length], xmm1
0x180020bdf  movups  xmmword ptr [rbp+47h+var_C0.Length], xmm0
0x180020be3  movups  xmmword ptr [rsp+130h+UnicodeString.Length], xmm1
0x180020be8  movups  xmmword ptr [rbp+47h+var_60.Length], xmm0
0x180020bec  movups  xmmword ptr [rbp+47h+var_78.Length], xmm1
0x180020bf0  test    r14, r14
0x180020bf3  jz      short loc_180020C20
0x180020bf5  mov     rcx, r14
0x180020bf8  call    SIPolicyIsLegacyPolicyID
0x180020bfd  lea     rdx, [rsp+130h+UnicodeString]
0x180020c02  mov     sil, al
0x180020c05  call    SIPolicyGetExpectedFilename
0x180020c0a  mov     ebx, eax
0x180020c0c  test    eax, eax
0x180020c0e  js      loc_180020DB4
0x180020c14  lea     rdi, [rsp+130h+var_100]
0x180020c19  lea     r15, [rsp+130h+var_F0]
0x180020c1e  jmp     short loc_180020C44
0x180020c20  lea     rdx, [rsp+130h+UnicodeString]
0x180020c25  mov     rcx, rax; Source
0x180020c28  call    SIPolicyPmGetTokenFileName
0x180020c2d  mov     ebx, eax
0x180020c2f  test    eax, eax
0x180020c31  js      loc_180020DB4
0x180020c37  xor     sil, sil
0x180020c3a  lea     r15, [rsp+130h+var_E0]
0x180020c3f  lea     rdi, [rsp+130h+var_D0]
0x180020c44  test    r13, r13
0x180020c47  jz      short loc_180020CBD
0x180020c49  test    r14, r14
0x180020c4c  jz      short loc_180020C72
0x180020c4e  mov     rax, [r14]
0x180020c51  cmp     rax, cs:qword_18002F310
0x180020c58  jnz     short loc_180020C72
0x180020c5a  mov     rax, [r14+8]
0x180020c5e  cmp     rax, cs:qword_18002F318
0x180020c65  jnz     short loc_180020C72
0x180020c67  lea     rcx, [rbp+47h+Source]
0x180020c6b  call    SIPolicyPmGetBootPartitionPolicyFolder10S
0x180020c70  jmp     short loc_180020C97
0x180020c72  xor     edx, edx
0x180020c74  lea     rcx, [rbp+47h+Source]
0x180020c78  test    r12b, r12b
0x180020c7b  jnz     short loc_180020C8B
0x180020c7d  test    sil, sil
0x180020c80  cmovz   rdx, rdi
0x180020c84  call    SIPolicyPmGetBootPartitionPolicyFolder
0x180020c89  jmp     short loc_180020C97
0x180020c8b  test    sil, sil
0x180020c8e  cmovz   rdx, rdi
0x180020c92  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x180020c97  mov     ebx, eax
0x180020c99  test    eax, eax
0x180020c9b  js      loc_180020DB4
0x180020ca1  lea     r8, [rbp+47h+DestinationString]
0x180020ca5  lea     rdx, [rsp+130h+UnicodeString]; PCUNICODE_STRING
0x180020caa  lea     rcx, [rbp+47h+Source]; Source
0x180020cae  call    SIPolicyBuildPath
0x180020cb3  mov     ebx, eax
0x180020cb5  test    eax, eax
0x180020cb7  js      loc_180020DB4
0x180020cbd  mov     r14, [rbp+47h+arg_20]
0x180020cc1  test    r14, r14
0x180020cc4  jz      short loc_180020D1C
0x180020cc6  xor     edx, edx
0x180020cc8  lea     rcx, [rbp+47h+var_78]
0x180020ccc  test    r12b, r12b
0x180020ccf  jnz     short loc_180020CDF
0x180020cd1  test    sil, sil
0x180020cd4  cmovz   rdx, rdi
0x180020cd8  call    SIPolicyPmGetSystemPartitionPolicyFolder
0x180020cdd  jmp     short loc_180020CEB
0x180020cdf  test    sil, sil
0x180020ce2  cmovz   rdx, rdi
0x180020ce6  call    SIPolicyPmGetVirtESPPartitionPolicyFolder
0x180020ceb  mov     ebx, eax
0x180020ced  test    eax, eax
0x180020cef  jns     short loc_180020D00
0x180020cf1  cmp     eax, 0C0000225h
0x180020cf6  jnz     loc_180020DB4
0x180020cfc  xor     ebx, ebx
0x180020cfe  jmp     short loc_180020D1C
0x180020d00  lea     r8, [rbp+47h+var_A0]
0x180020d04  lea     rdx, [rsp+130h+UnicodeString]; PCUNICODE_STRING
0x180020d09  lea     rcx, [rbp+47h+var_78]; Source
0x180020d0d  call    SIPolicyBuildPath
0x180020d12  mov     ebx, eax
0x180020d14  test    eax, eax
0x180020d16  js      loc_180020DB4
0x180020d1c  mov     rdi, [rbp+47h+arg_28]
0x180020d20  test    rdi, rdi
0x180020d23  jz      short loc_180020D66
0x180020d25  lea     rcx, [rbp+47h+var_60]
0x180020d29  mov     rdx, r15
0x180020d2c  test    r12b, r12b
0x180020d2f  jnz     short loc_180020D38
0x180020d31  call    SIPolicyPmGetBootPartitionPolicyFolder
0x180020d36  jmp     short loc_180020D3D
0x180020d38  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x180020d3d  mov     ebx, eax
0x180020d3f  test    eax, eax
0x180020d41  jns     short loc_180020D4E
0x180020d43  cmp     eax, 0C0000225h
0x180020d48  jnz     short loc_180020DB4
0x180020d4a  xor     ebx, ebx
0x180020d4c  jmp     short loc_180020D66
0x180020d4e  lea     r8, [rbp+47h+var_C0]
0x180020d52  lea     rdx, [rsp+130h+UnicodeString]; PCUNICODE_STRING
0x180020d57  lea     rcx, [rbp+47h+var_60]; Source
0x180020d5b  call    SIPolicyBuildPath
0x180020d60  mov     ebx, eax
0x180020d62  test    eax, eax
0x180020d64  js      short loc_180020DB4
0x180020d66  test    r13, r13
0x180020d69  jz      short loc_180020D81
0x180020d6b  movups  xmm0, xmmword ptr [rbp+47h+DestinationString.Length]
0x180020d6f  xor     edx, edx; SourceString
0x180020d71  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180020d75  movdqu  xmmword ptr [r13+0], xmm0
0x180020d7b  call    cs:__imp_RtlInitUnicodeString
0x180020d81  test    r14, r14
0x180020d84  jz      short loc_180020D9B
0x180020d86  movups  xmm0, xmmword ptr [rbp+47h+var_A0.Length]
0x180020d8a  xor     edx, edx; SourceString
0x180020d8c  lea     rcx, [rbp+47h+var_A0]; DestinationString
0x180020d90  movdqu  xmmword ptr [r14], xmm0
0x180020d95  call    cs:__imp_RtlInitUnicodeString
0x180020d9b  test    rdi, rdi
0x180020d9e  jz      short loc_180020DB4
0x180020da0  movups  xmm0, xmmword ptr [rbp+47h+var_C0.Length]
0x180020da4  xor     edx, edx; SourceString
0x180020da6  lea     rcx, [rbp+47h+var_C0]; DestinationString
0x180020daa  movdqu  xmmword ptr [rdi], xmm0
0x180020dae  call    cs:__imp_RtlInitUnicodeString
0x180020db4  lea     rcx, [rsp+130h+UnicodeString]; UnicodeString
0x180020db9  call    cs:__imp_RtlFreeUnicodeString
0x180020dbf  lea     rcx, [rbp+47h+var_C0]; UnicodeString
0x180020dc3  call    cs:__imp_RtlFreeUnicodeString
0x180020dc9  lea     rcx, [rbp+47h+DestinationString]; UnicodeString
0x180020dcd  call    cs:__imp_RtlFreeUnicodeString
0x180020dd3  lea     rcx, [rbp+47h+var_A0]; UnicodeString
0x180020dd7  call    cs:__imp_RtlFreeUnicodeString
0x180020ddd  mov     edi, 1
0x180020de2  lea     rcx, [rbp+47h+Source]
0x180020de6  mov     edx, edi
0x180020de8  call    SIPolicyPmFreeFileItems
0x180020ded  mov     edx, edi
0x180020def  lea     rcx, [rbp+47h+var_78]
0x180020df3  call    SIPolicyPmFreeFileItems
0x180020df8  mov     edx, edi
0x180020dfa  lea     rcx, [rbp+47h+var_60]
0x180020dfe  call    SIPolicyPmFreeFileItems
0x180020e03  mov     eax, ebx
0x180020e05  add     rsp, 0F8h
0x180020e0c  pop     r15
0x180020e0e  pop     r14
0x180020e10  pop     r13
0x180020e12  pop     r12
0x180020e14  pop     rdi
0x180020e15  pop     rsi
0x180020e16  pop     rbx
0x180020e17  pop     rbp
0x180020e18  retn
```
