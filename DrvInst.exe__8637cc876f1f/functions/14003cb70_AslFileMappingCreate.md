# AslFileMappingCreate

- ea: `0x14003cb70`
- end: `0x14003cdfb`
- name: `AslFileMappingCreate`
- size: `651`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x140030008`
- `0x140030f70`
- `0x140031a0c`
- `0x140031f20`
- `0x140037870`

## callees

- `0x14003bf18`
- `0x14003c340`
- `0x14003cb70`
- `0x14003ce04`
- `0x14003d574`
- `0x140041140`
- `0x140045f30`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14003ccd9`
- `msvcrt!_wcsnicmp` at `0x14003ccd9`
- `ntdll!RtlInitUnicodeString` at `0x14003cbde`
- `ntdll!RtlInitUnicodeString` at `0x14003cbde`
- `ntdll!RtlFreeUnicodeString` at `0x14003cdc7`
- `ntdll!RtlFreeUnicodeString` at `0x14003cdc7`
- `ntdll!RtlAllocateHeap` at `0x14003cbfb`
- `ntdll!RtlAllocateHeap` at `0x14003cbfb`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003ccf0`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003ccf0`
- `ntdll!ZwQueryInformationFile` at `0x14003cc8a`
- `ntdll!ZwQueryInformationFile` at `0x14003cc8a`

## string_xrefs

- `0x14003cd00`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x14003cca7`: `AslFileMappingCreate`
- `0x14003cd12`: `AslFileMappingCreate`
- `0x14003cd75`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x14003cd88`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(_QWORD *a1, const WCHAR *a2, __int64 a3)
{
  char *Heap; // rax
  char *v7; // rsi
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rax
  HANDLE *v13; // r14
  int v14; // eax
  const char *v15; // r9
  __int64 v16; // r8
  int v17; // eax
  int v18; // ecx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  unsigned int v23; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h]

  v27 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v7 = Heap;
  if ( Heap )
  {
    v9 = AslStringDuplicate(Heap, a2);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = "AslStringDuplicate failed [%x]";
      v11 = 123;
LABEL_14:
      FileInformationClass[0] = v9;
      AslLogCallPrintf(1, "AslFileMappingCreate", v11, v10, *(_QWORD *)FileInformationClass);
LABEL_15:
      AslFileMappingDelete(v7);
      goto LABEL_29;
    }
    v12 = 0;
    if ( a3 != -1 )
      v12 = a3;
    if ( v12 )
    {
      v13 = (HANDLE *)(v7 + 8);
      *(_OWORD *)(v7 + 8) = 0;
      *(_OWORD *)(v7 + 24) = 0;
      *(_OWORD *)(v7 + 40) = 0;
      *((_QWORD *)v7 + 1) = v12;
LABEL_12:
      v27 = 0;
      IoStatusBlock = 0;
      FileInformation = 0;
      v9 = ZwQueryInformationFile(*v13, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v8 = 0;
        *((_QWORD *)v7 + 3) = *((_QWORD *)&FileInformation + 1);
        *((_DWORD *)v7 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
        *a1 = v7;
        goto LABEL_29;
      }
      v10 = "NtQueryInformationFile failed [%x]";
      v11 = 183;
      goto LABEL_14;
    }
    if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
      && (v14 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v8 = v14, v14 < 0) )
    {
      v23 = v14;
      v15 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v16 = 148;
    }
    else
    {
      v13 = (HANDLE *)(v7 + 8);
      v17 = RtlFileMapInitializeByNtPath(v7 + 8, &DestinationString);
      v8 = v17;
      if ( v17 >= 0 )
        goto LABEL_12;
      if ( (unsigned int)AslFileNotFound((unsigned int)v17) )
        goto LABEL_15;
      v19 = (unsigned int)(v18 + 1073741805);
      if ( (unsigned int)v19 <= 0x30 && (v20 = 0x1000000008001LL, _bittest64(&v20, v19)) || v8 == -1073741638 )
      {
        AslLogCallPrintf(3, "AslFileMappingCreate", 163, "RtlFileMapInitializeByFilePath failed %S [%x]", a2, v8);
        goto LABEL_15;
      }
      v23 = v8;
      v15 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v16 = 161;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", v16, v15, a2, v23, *(_QWORD *)&DestinationString.Length);
    goto LABEL_15;
  }
  v8 = -1073741801;
LABEL_29:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v8;
}

```

## disassembly

```asm
0x14003cb70  mov     [rsp-28h+arg_10], rbx
0x14003cb75  mov     [rsp-28h+arg_18], rsi
0x14003cb7a  push    rbp
0x14003cb7b  push    rdi
0x14003cb7c  push    r12
0x14003cb7e  push    r14
0x14003cb80  push    r15
0x14003cb82  mov     rbp, rsp
0x14003cb85  sub     rsp, 70h
0x14003cb89  mov     rax, cs:__security_cookie
0x14003cb90  xor     rax, rsp
0x14003cb93  mov     [rbp+var_8], rax
0x14003cb97  xor     eax, eax
0x14003cb99  xorps   xmm0, xmm0
0x14003cb9c  xor     r12d, r12d
0x14003cb9f  mov     [rbp+var_10], rax
0x14003cba3  xorps   xmm1, xmm1
0x14003cba6  mov     r14, r8
0x14003cba9  mov     rdi, rdx
0x14003cbac  mov     r15, rcx
0x14003cbaf  movups  [rbp+FileInformation], xmm0
0x14003cbb3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003cbb7  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x14003cbbb  test    rdx, rdx
0x14003cbbe  jz      loc_14003CDD1
0x14003cbc4  cmp     [rdx], r12w
0x14003cbc8  jz      loc_14003CDD1
0x14003cbce  test    rcx, rcx
0x14003cbd1  jz      loc_14003CDD1
0x14003cbd7  mov     [rcx], r12
0x14003cbda  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003cbde  call    cs:__imp_RtlInitUnicodeString
0x14003cbe4  mov     rcx, gs:60h
0x14003cbed  lea     edx, [r12+8]; Flags
0x14003cbf2  lea     r8d, [r12+50h]; Size
0x14003cbf7  mov     rcx, [rcx+30h]; HeapHandle
0x14003cbfb  call    cs:__imp_RtlAllocateHeap
0x14003cc01  mov     rsi, rax
0x14003cc04  test    rax, rax
0x14003cc07  jnz     short loc_14003CC13
0x14003cc09  mov     ebx, 0C0000017h
0x14003cc0e  jmp     loc_14003CDBD
0x14003cc13  mov     rdx, rdi
0x14003cc16  mov     rcx, rsi
0x14003cc19  call    AslStringDuplicate
0x14003cc1e  mov     ebx, eax
0x14003cc20  test    eax, eax
0x14003cc22  jns     short loc_14003CC33
0x14003cc24  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x14003cc2b  mov     r8d, 7Bh ; '{'
0x14003cc31  jmp     short loc_14003CCA7
0x14003cc33  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14003cc37  mov     rax, r12
0x14003cc3a  cmovnz  rax, r14
0x14003cc3e  test    rax, rax
0x14003cc41  jz      loc_14003CCC9
0x14003cc47  lea     r14, [rsi+8]
0x14003cc4b  xorps   xmm0, xmm0
0x14003cc4e  movups  xmmword ptr [r14], xmm0
0x14003cc52  movups  xmmword ptr [r14+10h], xmm0
0x14003cc57  movups  xmmword ptr [r14+20h], xmm0
0x14003cc5c  mov     [r14], rax
0x14003cc5f  xor     eax, eax
0x14003cc61  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x14003cc69  xorps   xmm0, xmm0
0x14003cc6c  mov     [rbp+var_10], rax
0x14003cc70  xorps   xmm1, xmm1
0x14003cc73  lea     r8, [rbp+FileInformation]; FileInformation
0x14003cc77  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14003cc7b  lea     r9d, [rax+18h]; Length
0x14003cc7f  movups  [rbp+FileInformation], xmm1
0x14003cc83  mov     rcx, [r14]; FileHandle
0x14003cc86  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14003cc8a  call    cs:__imp_ZwQueryInformationFile
0x14003cc90  mov     ebx, eax
0x14003cc92  test    eax, eax
0x14003cc94  jns     loc_14003CD9F
0x14003cc9a  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x14003cca1  mov     r8d, 0B7h
0x14003cca7  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x14003ccae  mov     [rsp+70h+FileInformationClass], eax
0x14003ccb2  mov     ecx, 1
0x14003ccb7  call    AslLogCallPrintf
0x14003ccbc  mov     rcx, rsi
0x14003ccbf  call    AslFileMappingDelete
0x14003ccc4  jmp     loc_14003CDBD
0x14003ccc9  mov     r8d, 0Ch; MaxCount
0x14003cccf  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x14003ccd6  mov     rcx, rdi; String1
0x14003ccd9  call    cs:__imp__wcsnicmp
0x14003ccdf  test    eax, eax
0x14003cce1  jz      short loc_14003CD25
0x14003cce3  xor     r9d, r9d
0x14003cce6  lea     rdx, [rbp+DestinationString]
0x14003ccea  xor     r8d, r8d
0x14003cced  mov     rcx, rdi
0x14003ccf0  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14003ccf6  mov     ebx, eax
0x14003ccf8  test    eax, eax
0x14003ccfa  jns     short loc_14003CD25
0x14003ccfc  mov     [rsp+70h+var_48], eax
0x14003cd00  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x14003cd07  mov     r8d, 94h
0x14003cd0d  mov     ecx, 1
0x14003cd12  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x14003cd19  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x14003cd1e  call    AslLogCallPrintf
0x14003cd23  jmp     short loc_14003CCBC
0x14003cd25  lea     r14, [rsi+8]
0x14003cd29  mov     rcx, r14
0x14003cd2c  lea     rdx, [rbp+DestinationString]
0x14003cd30  call    RtlFileMapInitializeByNtPath
0x14003cd35  mov     ebx, eax
0x14003cd37  test    eax, eax
0x14003cd39  jns     loc_14003CC5F
0x14003cd3f  mov     ecx, eax
0x14003cd41  call    AslFileNotFound
0x14003cd46  test    eax, eax
0x14003cd48  jnz     loc_14003CCBC
0x14003cd4e  lea     eax, [rcx+3FFFFFEDh]
0x14003cd54  cmp     eax, 30h ; '0'
0x14003cd57  ja      short loc_14003CD69
0x14003cd59  mov     rcx, 1000000008001h
0x14003cd63  bt      rcx, rax
0x14003cd67  jb      short loc_14003CD84
0x14003cd69  cmp     ebx, 0C00000BAh
0x14003cd6f  jz      short loc_14003CD84
0x14003cd71  mov     [rsp+70h+var_48], ebx
0x14003cd75  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14003cd7c  mov     r8d, 0A1h
0x14003cd82  jmp     short loc_14003CD0D
0x14003cd84  mov     [rsp+70h+var_48], ebx
0x14003cd88  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14003cd8f  mov     r8d, 0A3h
0x14003cd95  mov     ecx, 3
0x14003cd9a  jmp     loc_14003CD12
0x14003cd9f  mov     rax, qword ptr [rbp+FileInformation+8]
0x14003cda3  mov     ebx, r12d
0x14003cda6  mov     [rsi+18h], rax
0x14003cdaa  mov     rax, qword ptr [rbp+FileInformation+8]
0x14003cdae  neg     rax
0x14003cdb1  sbb     ecx, ecx
0x14003cdb3  neg     ecx
0x14003cdb5  inc     ecx
0x14003cdb7  mov     [rsi+38h], ecx
0x14003cdba  mov     [r15], rsi
0x14003cdbd  cmp     [rbp+DestinationString.Buffer], rdi
0x14003cdc1  jz      short loc_14003CDCD
0x14003cdc3  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14003cdc7  call    cs:__imp_RtlFreeUnicodeString
0x14003cdcd  mov     eax, ebx
0x14003cdcf  jmp     short loc_14003CDD6
0x14003cdd1  mov     eax, 0C000000Dh
0x14003cdd6  mov     rcx, [rbp+var_8]
0x14003cdda  xor     rcx, rsp; StackCookie
0x14003cddd  call    __security_check_cookie
0x14003cde2  lea     r11, [rsp+70h+var_s0]
0x14003cde7  mov     rbx, [r11+40h]
0x14003cdeb  mov     rsi, [r11+48h]
0x14003cdef  mov     rsp, r11
0x14003cdf2  pop     r15
0x14003cdf4  pop     r14
0x14003cdf6  pop     r12
0x14003cdf8  pop     rdi
0x14003cdf9  pop     rbp
0x14003cdfa  retn
```
