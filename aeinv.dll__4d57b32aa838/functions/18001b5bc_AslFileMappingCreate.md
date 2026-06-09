# AslFileMappingCreate

- ea: `0x18001b5bc`
- end: `0x18001b827`
- name: `AslFileMappingCreate`
- size: `619`
- prototype: `__int64 __fastcall(HANDLE **, const WCHAR *)`
- caller_count: `8`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800131f4`
- `0x1800454f4`
- `0x18004c27c`
- `0x18004d2dc`
- `0x1800558d8`
- `0x180119160`
- `0x1801207a0`
- `0x180121230`

## callees

- `0x1800197d4`
- `0x18001b0b8`
- `0x18001b5bc`
- `0x18001b830`
- `0x18001ba64`
- `0x180059920`
- `0x18005a7d8`
- `0x18006b234`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001b74a`
- `ntdll!RtlFreeUnicodeString` at `0x18001b74a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001b690`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001b690`
- `ntdll!RtlAllocateHeap` at `0x18001b644`
- `ntdll!RtlAllocateHeap` at `0x18001b644`
- `ntdll!RtlInitUnicodeString` at `0x18001b627`
- `ntdll!RtlInitUnicodeString` at `0x18001b627`
- `ntdll!ZwQueryInformationFile` at `0x18001b6e3`
- `ntdll!ZwQueryInformationFile` at `0x18001b6e3`

## string_xrefs

- `0x18001b6fc`: `AslFileMappingCreate`
- `0x18001b788`: `AslFileMappingCreate`
- `0x18001b776`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18001b7fa`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x18001b810`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall AslFileMappingCreate(HANDLE **a1, const WCHAR *a2)
{
  HANDLE *Heap; // rax
  HANDLE *v5; // rsi
  NTSTATUS v6; // ebx
  int v7; // eax
  const char *v8; // r9
  int v9; // r8d
  const char *v11; // r9
  int v12; // r8d
  int v13; // ecx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]

  v19 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    goto LABEL_13;
  }
  v6 = AslStringDuplicate(Heap, a2);
  if ( v6 >= 0 )
  {
    if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
      && (v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v6 < 0) )
    {
      v11 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v12 = 148;
    }
    else
    {
      v7 = RtlFileMapInitializeByNtPath(v5 + 1, &DestinationString);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v19 = 0;
        IoStatusBlock = 0;
        FileInformation = 0;
        v6 = ZwQueryInformationFile(v5[1], &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
        if ( v6 >= 0 )
        {
          v6 = 0;
          v5[3] = (HANDLE)*((_QWORD *)&FileInformation + 1);
          *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
          *a1 = v5;
          goto LABEL_13;
        }
        v8 = "NtQueryInformationFile failed [%x]";
        v9 = 183;
        goto LABEL_11;
      }
      if ( (unsigned int)AslFileNotFound((unsigned int)v7) )
        goto LABEL_12;
      v14 = (unsigned int)(v6 + 1073741805);
      if ( (unsigned int)v14 <= 0x30 && (v15 = 0x1000000008001LL, _bittest64(&v15, v14)) || v6 == -1073741638 )
      {
        v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
        v12 = 163;
        v13 = 3;
        goto LABEL_19;
      }
      v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v12 = 161;
    }
    v13 = 1;
LABEL_19:
    AslLogCallPrintf(v13, (unsigned int)"AslFileMappingCreate", v12, (_DWORD)v11);
    goto LABEL_12;
  }
  v8 = "AslStringDuplicate failed [%x]";
  v9 = 123;
LABEL_11:
  AslLogCallPrintf(1, (unsigned int)"AslFileMappingCreate", v9, (_DWORD)v8);
LABEL_12:
  AslFileMappingDelete(v5);
LABEL_13:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b5bc  mov     [rsp-28h+arg_10], rbx
0x18001b5c1  mov     [rsp-28h+arg_18], rsi
0x18001b5c6  push    rbp
0x18001b5c7  push    rdi
0x18001b5c8  push    r12
0x18001b5ca  push    r14
0x18001b5cc  push    r15
0x18001b5ce  mov     rbp, rsp
0x18001b5d1  sub     rsp, 70h
0x18001b5d5  mov     rax, cs:__security_cookie
0x18001b5dc  xor     rax, rsp
0x18001b5df  mov     [rbp+var_8], rax
0x18001b5e3  xor     eax, eax
0x18001b5e5  xorps   xmm0, xmm0
0x18001b5e8  xor     r12d, r12d
0x18001b5eb  mov     [rbp+var_10], rax
0x18001b5ef  xorps   xmm1, xmm1
0x18001b5f2  mov     rdi, rdx
0x18001b5f5  mov     r14, rcx
0x18001b5f8  movups  [rbp+FileInformation], xmm0
0x18001b5fc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001b600  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x18001b604  test    rdx, rdx
0x18001b607  jz      loc_18001B79E
0x18001b60d  cmp     [rdx], r12w
0x18001b611  jz      loc_18001B79E
0x18001b617  test    rcx, rcx
0x18001b61a  jz      loc_18001B79E
0x18001b620  mov     [rcx], r12
0x18001b623  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001b627  call    cs:__imp_RtlInitUnicodeString
0x18001b62d  mov     rcx, gs:60h
0x18001b636  lea     edx, [r12+8]; Flags
0x18001b63b  lea     r8d, [r12+50h]; Size
0x18001b640  mov     rcx, [rcx+30h]; HeapHandle
0x18001b644  call    cs:__imp_RtlAllocateHeap
0x18001b64a  mov     rsi, rax
0x18001b64d  test    rax, rax
0x18001b650  jz      loc_18001B7A8
0x18001b656  mov     rdx, rdi
0x18001b659  mov     rcx, rax
0x18001b65c  call    AslStringDuplicate
0x18001b661  mov     ebx, eax
0x18001b663  test    eax, eax
0x18001b665  js      loc_18001B7B2
0x18001b66b  lea     r8d, [r12+0Ch]; MaxCount
0x18001b670  mov     rcx, rdi; String1
0x18001b673  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18001b67a  call    _wcsnicmp
0x18001b67f  test    eax, eax
0x18001b681  jz      short loc_18001B6A0
0x18001b683  xor     r9d, r9d
0x18001b686  lea     rdx, [rbp+DestinationString]
0x18001b68a  xor     r8d, r8d
0x18001b68d  mov     rcx, rdi
0x18001b690  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18001b696  mov     ebx, eax
0x18001b698  test    eax, eax
0x18001b69a  js      loc_18001B772
0x18001b6a0  lea     rdx, [rbp+DestinationString]
0x18001b6a4  lea     rcx, [rsi+8]
0x18001b6a8  call    RtlFileMapInitializeByNtPath
0x18001b6ad  mov     ebx, eax
0x18001b6af  test    eax, eax
0x18001b6b1  js      loc_18001B7C4
0x18001b6b7  xor     eax, eax
0x18001b6b9  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x18001b6c1  xorps   xmm0, xmm0
0x18001b6c4  mov     [rbp+var_10], rax
0x18001b6c8  xorps   xmm1, xmm1
0x18001b6cb  lea     r8, [rbp+FileInformation]; FileInformation
0x18001b6cf  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001b6d3  lea     r9d, [rax+18h]; Length
0x18001b6d7  movups  [rbp+FileInformation], xmm1
0x18001b6db  mov     rcx, [rsi+8]; FileHandle
0x18001b6df  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18001b6e3  call    cs:__imp_ZwQueryInformationFile
0x18001b6e9  mov     ebx, eax
0x18001b6eb  test    eax, eax
0x18001b6ed  jns     short loc_18001B752
0x18001b6ef  lea     r9, aNtqueryinforma_1; "NtQueryInformationFile failed [%x]"
0x18001b6f6  mov     r8d, 0B7h
0x18001b6fc  lea     rdx, aAslfilemapping_15; "AslFileMappingCreate"
0x18001b703  mov     [rsp+70h+FileInformationClass], eax
0x18001b707  mov     ecx, 1
0x18001b70c  call    AslLogCallPrintf
0x18001b711  mov     rcx, rsi
0x18001b714  call    AslFileMappingDelete
0x18001b719  cmp     [rbp+DestinationString.Buffer], rdi
0x18001b71d  jnz     short loc_18001B746
0x18001b71f  mov     eax, ebx
0x18001b721  mov     rcx, [rbp+var_8]
0x18001b725  xor     rcx, rsp; StackCookie
0x18001b728  call    __security_check_cookie
0x18001b72d  lea     r11, [rsp+70h+var_s0]
0x18001b732  mov     rbx, [r11+40h]
0x18001b736  mov     rsi, [r11+48h]
0x18001b73a  mov     rsp, r11
0x18001b73d  pop     r15
0x18001b73f  pop     r14
0x18001b741  pop     r12
0x18001b743  pop     rdi
0x18001b744  pop     rbp
0x18001b745  retn
0x18001b746  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18001b74a  call    cs:__imp_RtlFreeUnicodeString
0x18001b750  jmp     short loc_18001B71F
0x18001b752  mov     rax, qword ptr [rbp+FileInformation+8]
0x18001b756  mov     ebx, r12d
0x18001b759  mov     [rsi+18h], rax
0x18001b75d  mov     rax, qword ptr [rbp+FileInformation+8]
0x18001b761  neg     rax
0x18001b764  sbb     ecx, ecx
0x18001b766  neg     ecx
0x18001b768  inc     ecx
0x18001b76a  mov     [rsi+38h], ecx
0x18001b76d  mov     [r14], rsi
0x18001b770  jmp     short loc_18001B719
0x18001b772  mov     [rsp+70h+var_48], eax
0x18001b776  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18001b77d  mov     r8d, 94h
0x18001b783  mov     ecx, 1
0x18001b788  lea     rdx, aAslfilemapping_15; "AslFileMappingCreate"
0x18001b78f  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x18001b794  call    AslLogCallPrintf
0x18001b799  jmp     loc_18001B711
0x18001b79e  mov     eax, 0C000000Dh
0x18001b7a3  jmp     loc_18001B721
0x18001b7a8  mov     ebx, 0C0000017h
0x18001b7ad  jmp     loc_18001B719
0x18001b7b2  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x18001b7b9  mov     r8d, 7Bh ; '{'
0x18001b7bf  jmp     loc_18001B6FC
0x18001b7c4  mov     ecx, ebx
0x18001b7c6  call    AslFileNotFound
0x18001b7cb  test    eax, eax
0x18001b7cd  jnz     loc_18001B711
0x18001b7d3  lea     eax, [rbx+3FFFFFEDh]
0x18001b7d9  cmp     eax, 30h ; '0'
0x18001b7dc  ja      short loc_18001B7EE
0x18001b7de  mov     rcx, 1000000008001h
0x18001b7e8  bt      rcx, rax
0x18001b7ec  jb      short loc_18001B80C
0x18001b7ee  cmp     ebx, 0C00000BAh
0x18001b7f4  jz      short loc_18001B80C
0x18001b7f6  mov     [rsp+70h+var_48], ebx
0x18001b7fa  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18001b801  mov     r8d, 0A1h
0x18001b807  jmp     loc_18001B783
0x18001b80c  mov     [rsp+70h+var_48], ebx
0x18001b810  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18001b817  mov     r8d, 0A3h
0x18001b81d  mov     ecx, 3
0x18001b822  jmp     loc_18001B788
```
