# AslFileMappingCreate

- ea: `0x180005a94`
- end: `0x180005d34`
- name: `AslFileMappingCreate`
- size: `672`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800059c4`
- `0x180006cac`
- `0x1800212e0`
- `0x18003e620`
- `0x180049250`
- `0x18004ea20`
- `0x18009729c`
- `0x1800e1a44`
- `0x1800e6414`
- `0x1800e7c8c`
- `0x1800e81a0`

## callees

- `0x180005a94`
- `0x180005d3c`
- `0x180005e1c`
- `0x180012920`
- `0x180012de0`
- `0x18003dc94`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180005c0c`
- `msvcrt!_wcsnicmp` at `0x180005c0c`
- `ntdll!ZwQueryInformationFile` at `0x180005b9d`
- `ntdll!ZwQueryInformationFile` at `0x180005b9d`
- `ntdll!RtlInitUnicodeString` at `0x180005b02`
- `ntdll!RtlInitUnicodeString` at `0x180005b02`
- `ntdll!RtlFreeUnicodeString` at `0x180005ca5`
- `ntdll!RtlFreeUnicodeString` at `0x180005ca5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180005c23`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180005c23`
- `ntdll!RtlAllocateHeap` at `0x180005b1f`
- `ntdll!RtlAllocateHeap` at `0x180005b1f`

## string_xrefs

- `0x180005ccd`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x180005cf2`: `AslFileMappingCreate`
- `0x180005d12`: `AslFileMappingCreate`
- `0x180005c83`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180005ce0`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(_QWORD *a1, const WCHAR *a2, __int64 a3)
{
  char *Heap; // rax
  char *v7; // rsi
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  HANDLE *v11; // r14
  int v13; // eax
  int v14; // eax
  int v15; // ecx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  const char *v18; // r9
  int v19; // r8d
  int v20; // ecx
  const char *v21; // r9
  int v22; // r8d
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  unsigned int v24; // [rsp+28h] [rbp-48h]
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h]

  v28 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v7 = Heap;
  if ( !Heap )
  {
    v9 = -1073741801;
    goto LABEL_12;
  }
  v8 = AslStringDuplicate(Heap, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    v21 = "AslStringDuplicate failed [%x]";
    v22 = 123;
LABEL_31:
    FileInformationClass[0] = v8;
    AslLogCallPrintf(1, (unsigned int)"AslFileMappingCreate", v22, (_DWORD)v21, *(_QWORD *)FileInformationClass);
    goto LABEL_32;
  }
  v10 = 0;
  if ( a3 != -1 )
    v10 = a3;
  if ( v10 )
  {
    v11 = (HANDLE *)(v7 + 8);
    *(_OWORD *)(v7 + 8) = 0;
    *(_OWORD *)(v7 + 24) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *((_QWORD *)v7 + 1) = v10;
    goto LABEL_10;
  }
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v13 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0);
    v9 = v13;
    if ( v13 < 0 )
    {
      v24 = v13;
      v18 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v19 = 148;
      goto LABEL_23;
    }
  }
  v11 = (HANDLE *)(v7 + 8);
  v14 = RtlFileMapInitializeByNtPath(v7 + 8, &DestinationString);
  v9 = v14;
  if ( v14 < 0 )
  {
    if ( (unsigned int)AslFileNotFound((unsigned int)v14) )
    {
LABEL_32:
      AslFileMappingDelete(v7);
      goto LABEL_12;
    }
    v16 = (unsigned int)(v15 + 1073741805);
    if ( (unsigned int)v16 <= 0x30 && (v17 = 0x1000000008001LL, _bittest64(&v17, v16)) || v9 == -1073741638 )
    {
      v24 = v9;
      v18 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v19 = 163;
      v20 = 3;
      goto LABEL_29;
    }
    v24 = v9;
    v18 = "RtlFileMapInitializeByFilePath failed %S [%x]";
    v19 = 161;
LABEL_23:
    v20 = 1;
LABEL_29:
    AslLogCallPrintf(
      v20,
      (unsigned int)"AslFileMappingCreate",
      v19,
      (_DWORD)v18,
      a2,
      v24,
      *(_QWORD *)&DestinationString.Length);
    goto LABEL_32;
  }
LABEL_10:
  v28 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = ZwQueryInformationFile(*v11, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  v9 = v8;
  if ( v8 < 0 )
  {
    v21 = "NtQueryInformationFile failed [%x]";
    v22 = 183;
    goto LABEL_31;
  }
  v9 = 0;
  *((_QWORD *)v7 + 3) = *((_QWORD *)&FileInformation + 1);
  *((_DWORD *)v7 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
  *a1 = v7;
LABEL_12:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v9;
}

```

## disassembly

```asm
0x180005a94  mov     [rsp-28h+arg_10], rbx
0x180005a99  mov     [rsp-28h+arg_18], rsi
0x180005a9e  push    rbp
0x180005a9f  push    rdi
0x180005aa0  push    r12
0x180005aa2  push    r14
0x180005aa4  push    r15
0x180005aa6  mov     rbp, rsp
0x180005aa9  sub     rsp, 70h
0x180005aad  mov     rax, cs:__security_cookie
0x180005ab4  xor     rax, rsp
0x180005ab7  mov     [rbp+var_8], rax
0x180005abb  xor     eax, eax
0x180005abd  xorps   xmm0, xmm0
0x180005ac0  xor     r12d, r12d
0x180005ac3  mov     [rbp+var_10], rax
0x180005ac7  xorps   xmm1, xmm1
0x180005aca  mov     r14, r8
0x180005acd  mov     rdi, rdx
0x180005ad0  mov     r15, rcx
0x180005ad3  movups  [rbp+FileInformation], xmm0
0x180005ad7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180005adb  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180005adf  test    rdx, rdx
0x180005ae2  jz      loc_180005CB0
0x180005ae8  cmp     [rdx], r12w
0x180005aec  jz      loc_180005CB0
0x180005af2  test    rcx, rcx
0x180005af5  jz      loc_180005CB0
0x180005afb  mov     [rcx], r12
0x180005afe  lea     rcx, [rbp+DestinationString]; DestinationString
0x180005b02  call    cs:__imp_RtlInitUnicodeString
0x180005b08  mov     rcx, gs:60h
0x180005b11  lea     edx, [r12+8]; Flags
0x180005b16  lea     r8d, [r12+50h]; Size
0x180005b1b  mov     rcx, [rcx+30h]; HeapHandle
0x180005b1f  call    cs:__imp_RtlAllocateHeap
0x180005b25  mov     rsi, rax
0x180005b28  test    rax, rax
0x180005b2b  jz      loc_180005C97
0x180005b31  mov     rdx, rdi
0x180005b34  mov     rcx, rax
0x180005b37  call    AslStringDuplicate
0x180005b3c  mov     ebx, eax
0x180005b3e  test    eax, eax
0x180005b40  js      loc_180005CBA
0x180005b46  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180005b4a  mov     eax, r12d
0x180005b4d  cmovnz  rax, r14
0x180005b51  test    rax, rax
0x180005b54  jz      loc_180005BFC
0x180005b5a  lea     r14, [rsi+8]
0x180005b5e  xorps   xmm0, xmm0
0x180005b61  movups  xmmword ptr [r14], xmm0
0x180005b65  movups  xmmword ptr [r14+10h], xmm0
0x180005b6a  movups  xmmword ptr [r14+20h], xmm0
0x180005b6f  mov     [r14], rax
0x180005b72  xor     eax, eax
0x180005b74  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x180005b7c  xorps   xmm0, xmm0
0x180005b7f  mov     [rbp+var_10], rax
0x180005b83  xorps   xmm1, xmm1
0x180005b86  lea     r8, [rbp+FileInformation]; FileInformation
0x180005b8a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180005b8e  lea     r9d, [rax+18h]; Length
0x180005b92  movups  [rbp+FileInformation], xmm1
0x180005b96  mov     rcx, [r14]; FileHandle
0x180005b99  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180005b9d  call    cs:__imp_ZwQueryInformationFile
0x180005ba3  mov     ebx, eax
0x180005ba5  test    eax, eax
0x180005ba7  js      loc_180005D05
0x180005bad  mov     rax, qword ptr [rbp+FileInformation+8]
0x180005bb1  mov     ebx, r12d
0x180005bb4  mov     [rsi+18h], rax
0x180005bb8  mov     rax, qword ptr [rbp+FileInformation+8]
0x180005bbc  neg     rax
0x180005bbf  sbb     ecx, ecx
0x180005bc1  neg     ecx
0x180005bc3  inc     ecx
0x180005bc5  mov     [rsi+38h], ecx
0x180005bc8  mov     [r15], rsi
0x180005bcb  cmp     [rbp+DestinationString.Buffer], rdi
0x180005bcf  jnz     loc_180005CA1
0x180005bd5  mov     eax, ebx
0x180005bd7  mov     rcx, [rbp+var_8]
0x180005bdb  xor     rcx, rsp; StackCookie
0x180005bde  call    __security_check_cookie
0x180005be3  lea     r11, [rsp+70h+var_s0]
0x180005be8  mov     rbx, [r11+40h]
0x180005bec  mov     rsi, [r11+48h]
0x180005bf0  mov     rsp, r11
0x180005bf3  pop     r15
0x180005bf5  pop     r14
0x180005bf7  pop     r12
0x180005bf9  pop     rdi
0x180005bfa  pop     rbp
0x180005bfb  retn
0x180005bfc  mov     r8d, 0Ch; MaxCount
0x180005c02  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x180005c09  mov     rcx, rdi; String1
0x180005c0c  call    cs:__imp__wcsnicmp
0x180005c12  test    eax, eax
0x180005c14  jz      short loc_180005C33
0x180005c16  xor     r9d, r9d
0x180005c19  lea     rdx, [rbp+DestinationString]
0x180005c1d  xor     r8d, r8d
0x180005c20  mov     rcx, rdi
0x180005c23  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180005c29  mov     ebx, eax
0x180005c2b  test    eax, eax
0x180005c2d  js      loc_180005CC9
0x180005c33  lea     r14, [rsi+8]
0x180005c37  mov     rcx, r14
0x180005c3a  lea     rdx, [rbp+DestinationString]
0x180005c3e  call    RtlFileMapInitializeByNtPath
0x180005c43  mov     ebx, eax
0x180005c45  test    eax, eax
0x180005c47  jns     loc_180005B72
0x180005c4d  mov     ecx, eax
0x180005c4f  call    AslFileNotFound
0x180005c54  test    eax, eax
0x180005c56  jnz     loc_180005D27
0x180005c5c  lea     eax, [rcx+3FFFFFEDh]
0x180005c62  cmp     eax, 30h ; '0'
0x180005c65  ja      short loc_180005C77
0x180005c67  mov     rcx, 1000000008001h
0x180005c71  bt      rcx, rax
0x180005c75  jb      short loc_180005CDC
0x180005c77  cmp     ebx, 0C00000BAh
0x180005c7d  jz      short loc_180005CDC
0x180005c7f  mov     [rsp+70h+var_48], ebx
0x180005c83  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180005c8a  mov     r8d, 0A1h
0x180005c90  mov     ecx, 1
0x180005c95  jmp     short loc_180005CF2
0x180005c97  mov     ebx, 0C0000017h
0x180005c9c  jmp     loc_180005BCB
0x180005ca1  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180005ca5  call    cs:__imp_RtlFreeUnicodeString
0x180005cab  jmp     loc_180005BD5
0x180005cb0  mov     eax, 0C000000Dh
0x180005cb5  jmp     loc_180005BD7
0x180005cba  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x180005cc1  mov     r8d, 7Bh ; '{'
0x180005cc7  jmp     short loc_180005D12
0x180005cc9  mov     [rsp+70h+var_48], eax
0x180005ccd  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180005cd4  mov     r8d, 94h
0x180005cda  jmp     short loc_180005C90
0x180005cdc  mov     [rsp+70h+var_48], ebx
0x180005ce0  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180005ce7  mov     r8d, 0A3h
0x180005ced  mov     ecx, 3
0x180005cf2  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x180005cf9  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x180005cfe  call    AslLogCallPrintf
0x180005d03  jmp     short loc_180005D27
0x180005d05  lea     r9, aNtqueryinforma_2; "NtQueryInformationFile failed [%x]"
0x180005d0c  mov     r8d, 0B7h
0x180005d12  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x180005d19  mov     [rsp+70h+FileInformationClass], eax
0x180005d1d  mov     ecx, 1
0x180005d22  call    AslLogCallPrintf
0x180005d27  mov     rcx, rsi
0x180005d2a  call    AslFileMappingDelete
0x180005d2f  jmp     loc_180005BCB
```
