# AslFileMappingCreate

- ea: `0x180015a6c`
- end: `0x180015da4`
- name: `AslFileMappingCreate`
- size: `824`
- prototype: `__int64 __fastcall(const wchar_t ***, const WCHAR *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `12`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x180002f60`
- `0x180004ff0`
- `0x180016250`
- `0x1800264d0`
- `0x180038478`
- `0x18003f760`
- `0x180047a20`
- `0x18004aa70`
- `0x18004cb90`
- `0x18004def0`
- `0x180050e20`
- `0x180051234`

## callees

- `0x18000f114`
- `0x180013424`
- `0x18001577c`
- `0x180015a6c`
- `0x180015dac`
- `0x180015e8c`
- `0x180015f80`
- `0x180039a66`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180015adb`
- `ntdll!RtlInitUnicodeString` at `0x180015adb`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180015b55`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180015b55`
- `ntdll!ZwQueryInformationFile` at `0x180015baa`
- `ntdll!ZwQueryInformationFile` at `0x180015baa`
- `ntdll!RtlFreeUnicodeString` at `0x180015bf5`
- `ntdll!RtlFreeUnicodeString` at `0x180015bf5`
- `ntdll!RtlAllocateHeap` at `0x180015af6`
- `ntdll!RtlAllocateHeap` at `0x180015af6`

## string_xrefs

- `0x180015c4e`: `AslFileMappingCreate`
- `0x180015cdc`: `AslFileMappingCreate`
- `0x180015d3f`: `AslFileMappingCreate`
- `0x180015d7c`: `AslFileMappingCreate`
- `0x180015c9f`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x180015cb2`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180015cca`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(
        const wchar_t ***a1,
        const WCHAR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  const wchar_t **Heap; // rax
  const wchar_t **v10; // rdi
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rax
  int v14; // eax
  HANDLE *v15; // r14
  int v16; // eax
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  __int64 v21; // r8
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  int FileKind; // eax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  unsigned int v27; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h]

  v31 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (const wchar_t **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v10 = Heap;
  if ( !Heap )
  {
    v12 = -1073741801;
    goto LABEL_18;
  }
  v11 = AslStringDuplicate(Heap, a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    v18 = "AslStringDuplicate failed [%x]";
    v19 = 123;
    goto LABEL_25;
  }
  v13 = 0;
  if ( a3 != (const wchar_t *)-1LL )
    v13 = a3;
  if ( !v13 )
  {
    if ( wcsnicmp_0(a2, L"\\SystemRoot\\", 0xCu)
      && (v14 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v12 = v14, v14 < 0) )
    {
      v27 = v14;
      v20 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v21 = 148;
    }
    else
    {
      v15 = (HANDLE *)(v10 + 1);
      v16 = RtlFileMapInitializeByNtPath(v10 + 1, &DestinationString);
      v12 = v16;
      if ( v16 >= 0 )
        goto LABEL_12;
      if ( (unsigned int)AslFileNotFound((unsigned int)v16) )
        goto LABEL_22;
      v23 = v12 + 1073741805;
      if ( (unsigned int)v23 <= 0x30 && (v24 = 0x1000000008001LL, _bittest64(&v24, v23)) || v12 == -1073741638 )
      {
        v27 = v12;
        v20 = "RtlFileMapInitializeByFilePath failed %S [%x]";
        v21 = 163;
        v22 = 3;
        goto LABEL_32;
      }
      v27 = v12;
      v20 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v21 = 161;
    }
    v22 = 1;
LABEL_32:
    AslLogCallPrintf(v22, "AslFileMappingCreate", v21, v20, a2, v27, *(_QWORD *)&DestinationString.Length);
    goto LABEL_22;
  }
  v15 = (HANDLE *)(v10 + 1);
  *(_OWORD *)(v10 + 1) = 0;
  *(_OWORD *)(v10 + 3) = 0;
  *(_OWORD *)(v10 + 5) = 0;
  v10[1] = v13;
LABEL_12:
  v31 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v11 = ZwQueryInformationFile(*v15, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  v12 = v11;
  if ( v11 < 0 )
  {
    v18 = "NtQueryInformationFile failed [%x]";
    v19 = 183;
LABEL_25:
    FileInformationClass[0] = v11;
    AslLogCallPrintf(1, "AslFileMappingCreate", v19, v18, *(_QWORD *)FileInformationClass);
    goto LABEL_22;
  }
  if ( a4 )
  {
    v10[5] = a5;
    *((_BYTE *)v10 + 51) = 1;
    v10[4] = a4;
  }
  v10[3] = (const wchar_t *)*((_QWORD *)&FileInformation + 1);
  if ( a4 )
  {
    if ( *((_QWORD *)&FileInformation + 1) )
    {
      FileKind = AslpFileMappingGetFileKind(v15, v10 + 7);
      if ( FileKind < 0 )
      {
        AslLogCallPrintf(1, "AslFileMappingCreate", 215, "AslpFileMappingGetFileKind failed %S [%x]", *v10, FileKind);
        *((_DWORD *)v10 + 14) = 3;
      }
      goto LABEL_17;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", 208, "File size is 0 bytes yet ImageViewBase was present");
    v12 = -1073741811;
LABEL_22:
    AslFileMappingDelete(v10);
    goto LABEL_18;
  }
  *((_DWORD *)v10 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
LABEL_17:
  *a1 = v10;
  v12 = 0;
LABEL_18:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v12;
}

```

## disassembly

```asm
0x180015a6c  mov     [rsp-38h+arg_10], rbx
0x180015a71  push    rbp
0x180015a72  push    rsi
0x180015a73  push    rdi
0x180015a74  push    r12
0x180015a76  push    r13
0x180015a78  push    r14
0x180015a7a  push    r15
0x180015a7c  mov     rbp, rsp
0x180015a7f  sub     rsp, 70h
0x180015a83  mov     rax, cs:__security_cookie
0x180015a8a  xor     rax, rsp
0x180015a8d  mov     [rbp+var_8], rax
0x180015a91  xor     eax, eax
0x180015a93  xorps   xmm0, xmm0
0x180015a96  xor     r13d, r13d
0x180015a99  mov     [rbp+var_10], rax
0x180015a9d  xorps   xmm1, xmm1
0x180015aa0  mov     r15, r9
0x180015aa3  mov     r14, r8
0x180015aa6  mov     rsi, rdx
0x180015aa9  mov     r12, rcx
0x180015aac  movups  [rbp+FileInformation], xmm0
0x180015ab0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015ab4  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180015ab8  test    rdx, rdx
0x180015abb  jz      loc_180015C3A
0x180015ac1  cmp     [rdx], r13w
0x180015ac5  jz      loc_180015C3A
0x180015acb  test    rcx, rcx
0x180015ace  jz      loc_180015C3A
0x180015ad4  mov     [rcx], r13
0x180015ad7  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015adb  call    cs:__imp_RtlInitUnicodeString
0x180015ae1  mov     rcx, gs:60h
0x180015aea  lea     edx, [r13+8]; Flags
0x180015aee  lea     r8d, [r13+50h]; Size
0x180015af2  mov     rcx, [rcx+30h]; HeapHandle
0x180015af6  call    cs:__imp_RtlAllocateHeap
0x180015afc  mov     rdi, rax
0x180015aff  test    rax, rax
0x180015b02  jz      loc_180015C82
0x180015b08  mov     rdx, rsi
0x180015b0b  mov     rcx, rax
0x180015b0e  call    AslStringDuplicate
0x180015b13  mov     ebx, eax
0x180015b15  test    eax, eax
0x180015b17  js      loc_180015C8C
0x180015b1d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180015b21  mov     eax, r13d
0x180015b24  cmovnz  rax, r14
0x180015b28  test    rax, rax
0x180015b2b  jnz     loc_180015C65
0x180015b31  lea     r8d, [r13+0Ch]; MaxCount
0x180015b35  mov     rcx, rsi; String1
0x180015b38  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x180015b3f  call    _wcsnicmp_0
0x180015b44  test    eax, eax
0x180015b46  jz      short loc_180015B65
0x180015b48  xor     r9d, r9d
0x180015b4b  lea     rdx, [rbp+DestinationString]
0x180015b4f  xor     r8d, r8d
0x180015b52  mov     rcx, rsi
0x180015b55  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180015b5b  mov     ebx, eax
0x180015b5d  test    eax, eax
0x180015b5f  js      loc_180015C9B
0x180015b65  lea     r14, [rdi+8]
0x180015b69  mov     rcx, r14
0x180015b6c  lea     rdx, [rbp+DestinationString]
0x180015b70  call    RtlFileMapInitializeByNtPath
0x180015b75  mov     ebx, eax
0x180015b77  test    eax, eax
0x180015b79  js      loc_180015C21
0x180015b7f  xor     eax, eax
0x180015b81  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x180015b89  xorps   xmm0, xmm0
0x180015b8c  mov     [rbp+var_10], rax
0x180015b90  xorps   xmm1, xmm1
0x180015b93  lea     r8, [rbp+FileInformation]; FileInformation
0x180015b97  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180015b9b  lea     r9d, [rax+18h]; Length
0x180015b9f  movups  [rbp+FileInformation], xmm1
0x180015ba3  mov     rcx, [r14]; FileHandle
0x180015ba6  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180015baa  call    cs:__imp_ZwQueryInformationFile
0x180015bb0  mov     ebx, eax
0x180015bb2  test    eax, eax
0x180015bb4  js      loc_180015C41
0x180015bba  test    r15, r15
0x180015bbd  jnz     loc_180015D17
0x180015bc3  mov     rax, qword ptr [rbp+FileInformation+8]
0x180015bc7  mov     [rdi+18h], rax
0x180015bcb  test    r15, r15
0x180015bce  jnz     loc_180015D2C
0x180015bd4  mov     rax, qword ptr [rbp+FileInformation+8]
0x180015bd8  neg     rax
0x180015bdb  sbb     ecx, ecx
0x180015bdd  neg     ecx
0x180015bdf  inc     ecx
0x180015be1  mov     [rdi+38h], ecx
0x180015be4  mov     [r12], rdi
0x180015be8  mov     ebx, r13d
0x180015beb  cmp     [rbp+DestinationString.Buffer], rsi
0x180015bef  jz      short loc_180015BFB
0x180015bf1  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180015bf5  call    cs:__imp_RtlFreeUnicodeString
0x180015bfb  mov     eax, ebx
0x180015bfd  mov     rcx, [rbp+var_8]
0x180015c01  xor     rcx, rsp; StackCookie
0x180015c04  call    __security_check_cookie
0x180015c09  mov     rbx, [rsp+70h+arg_10]
0x180015c11  add     rsp, 70h
0x180015c15  pop     r15
0x180015c17  pop     r14
0x180015c19  pop     r13
0x180015c1b  pop     r12
0x180015c1d  pop     rdi
0x180015c1e  pop     rsi
0x180015c1f  pop     rbp
0x180015c20  retn
0x180015c21  mov     ecx, ebx
0x180015c23  call    AslFileNotFound
0x180015c28  test    eax, eax
0x180015c2a  jz      loc_180015CF2
0x180015c30  mov     rcx, rdi
0x180015c33  call    AslFileMappingDelete
0x180015c38  jmp     short loc_180015BEB
0x180015c3a  mov     eax, 0C000000Dh
0x180015c3f  jmp     short loc_180015BFD
0x180015c41  lea     r9, aNtqueryinforma_1; "NtQueryInformationFile failed [%x]"
0x180015c48  mov     r8d, 0B7h
0x180015c4e  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x180015c55  mov     [rsp+70h+FileInformationClass], eax
0x180015c59  mov     ecx, 1
0x180015c5e  call    AslLogCallPrintf
0x180015c63  jmp     short loc_180015C30
0x180015c65  lea     r14, [rdi+8]
0x180015c69  xorps   xmm0, xmm0
0x180015c6c  movups  xmmword ptr [r14], xmm0
0x180015c70  movups  xmmword ptr [r14+10h], xmm0
0x180015c75  movups  xmmword ptr [r14+20h], xmm0
0x180015c7a  mov     [r14], rax
0x180015c7d  jmp     loc_180015B7F
0x180015c82  mov     ebx, 0C0000017h
0x180015c87  jmp     loc_180015BEB
0x180015c8c  lea     r9, aAslstringdupli_2; "AslStringDuplicate failed [%x]"
0x180015c93  mov     r8d, 7Bh ; '{'
0x180015c99  jmp     short loc_180015C4E
0x180015c9b  mov     [rsp+70h+var_48], eax
0x180015c9f  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180015ca6  mov     r8d, 94h
0x180015cac  jmp     short loc_180015CBF
0x180015cae  mov     [rsp+70h+var_48], ebx
0x180015cb2  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180015cb9  mov     r8d, 0A1h
0x180015cbf  mov     ecx, 1
0x180015cc4  jmp     short loc_180015CDC
0x180015cc6  mov     [rsp+70h+var_48], ebx
0x180015cca  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180015cd1  mov     r8d, 0A3h
0x180015cd7  mov     ecx, 3
0x180015cdc  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x180015ce3  mov     qword ptr [rsp+70h+FileInformationClass], rsi
0x180015ce8  call    AslLogCallPrintf
0x180015ced  jmp     loc_180015C30
0x180015cf2  lea     eax, [rbx+3FFFFFEDh]
0x180015cf8  cmp     eax, 30h ; '0'
0x180015cfb  ja      short loc_180015D0D
0x180015cfd  mov     rcx, 1000000008001h
0x180015d07  bt      rcx, rax
0x180015d0b  jb      short loc_180015CC6
0x180015d0d  cmp     ebx, 0C00000BAh
0x180015d13  jz      short loc_180015CC6
0x180015d15  jmp     short loc_180015CAE
0x180015d17  mov     rax, [rbp+arg_20]
0x180015d1b  mov     [rdi+28h], rax
0x180015d1f  mov     byte ptr [rdi+33h], 1
0x180015d23  mov     [rdi+20h], r15
0x180015d27  jmp     loc_180015BC3
0x180015d2c  cmp     qword ptr [rbp+FileInformation+8], r13
0x180015d30  jnz     short loc_180015D5A
0x180015d32  lea     r9, aFileSizeIs0Byt; "File size is 0 bytes yet ImageViewBase "...
0x180015d39  mov     r8d, 0D0h
0x180015d3f  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x180015d46  mov     ecx, 1
0x180015d4b  call    AslLogCallPrintf
0x180015d50  mov     ebx, 0C000000Dh
0x180015d55  jmp     loc_180015C30
0x180015d5a  lea     rdx, [rdi+38h]
0x180015d5e  mov     rcx, r14
0x180015d61  call    AslpFileMappingGetFileKind
0x180015d66  test    eax, eax
0x180015d68  jns     loc_180015BE4
0x180015d6e  mov     [rsp+70h+var_48], eax
0x180015d72  lea     r9, aAslpfilemappin; "AslpFileMappingGetFileKind failed %S [%"...
0x180015d79  mov     rax, [rdi]
0x180015d7c  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x180015d83  mov     r8d, 0D7h
0x180015d89  mov     qword ptr [rsp+70h+FileInformationClass], rax
0x180015d8e  mov     ecx, 1
0x180015d93  call    AslLogCallPrintf
0x180015d98  mov     dword ptr [rdi+38h], 3
0x180015d9f  jmp     loc_180015BE4
```
