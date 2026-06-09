# AslFileMappingCreate

- ea: `0x1800301b8`
- end: `0x180030420`
- name: `AslFileMappingCreate`
- size: `616`
- prototype: `__int64 __fastcall(HANDLE **, const WCHAR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800296b0`
- `0x1800e286c`

## callees

- `0x180005890`
- `0x18000689c`
- `0x1800295dc`
- `0x18002ae1c`
- `0x1800301b8`
- `0x180030428`
- `0x180030c3c`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800302a1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800302a1`
- `ntdll!RtlFreeUnicodeString` at `0x1800303ec`
- `ntdll!RtlFreeUnicodeString` at `0x1800303ec`
- `ntdll!ZwQueryInformationFile` at `0x18003038c`
- `ntdll!ZwQueryInformationFile` at `0x18003038c`
- `ntdll!RtlAllocateHeap` at `0x180030240`
- `ntdll!RtlAllocateHeap` at `0x180030240`
- `ntdll!RtlInitUnicodeString` at `0x180030223`
- `ntdll!RtlInitUnicodeString` at `0x180030223`

## string_xrefs

- `0x1800302b1`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x1800302c3`: `AslFileMappingCreate`
- `0x1800303a5`: `AslFileMappingCreate`
- `0x180030333`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180030349`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AslFileMappingCreate(HANDLE **a1, const WCHAR *a2)
{
  HANDLE *Heap; // rax
  HANDLE *v5; // rsi
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  unsigned int v18; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h]

  v22 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( Heap )
  {
    v7 = AslStringDuplicate(Heap);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = "AslStringDuplicate failed [%x]";
      v9 = 123;
LABEL_24:
      FileInformationClass[0] = v7;
      AslLogCallPrintf(1, "AslFileMappingCreate", v9, v8, *(_QWORD *)FileInformationClass);
      goto LABEL_25;
    }
    if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
      && (v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v6 = v10, v10 < 0) )
    {
      v18 = v10;
      v11 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v12 = 148;
    }
    else
    {
      v13 = RtlFileMapInitializeByNtPath(v5 + 1, &DestinationString);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v22 = 0;
        IoStatusBlock = 0;
        FileInformation = 0;
        v7 = ZwQueryInformationFile(v5[1], &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
        v6 = v7;
        if ( v7 >= 0 )
        {
          v6 = 0;
          v5[3] = (HANDLE)*((_QWORD *)&FileInformation + 1);
          *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
          *a1 = v5;
          goto LABEL_27;
        }
        v8 = "NtQueryInformationFile failed [%x]";
        v9 = 183;
        goto LABEL_24;
      }
      if ( v13 == -1073741766 || v13 == -1073741772 || v13 == -1073741620 )
        goto LABEL_25;
      v14 = (unsigned int)(v13 + 1073741805);
      if ( (unsigned int)v14 <= 0x30 && (v15 = 0x1000000008001LL, _bittest64(&v15, v14)) || v6 == -1073741638 )
      {
        AslLogCallPrintf(3, "AslFileMappingCreate", 163, "RtlFileMapInitializeByFilePath failed %S [%x]", a2, v6);
LABEL_25:
        AslFileMappingDelete(v5);
        goto LABEL_27;
      }
      v18 = v6;
      v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v12 = 161;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", v12, v11, a2, v18, *(_QWORD *)&DestinationString.Length);
    goto LABEL_25;
  }
  v6 = -1073741801;
LABEL_27:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v6;
}

```

## disassembly

```asm
0x1800301b8  mov     [rsp-28h+arg_10], rbx
0x1800301bd  mov     [rsp-28h+arg_18], rsi
0x1800301c2  push    rbp
0x1800301c3  push    rdi
0x1800301c4  push    r12
0x1800301c6  push    r14
0x1800301c8  push    r15
0x1800301ca  mov     rbp, rsp
0x1800301cd  sub     rsp, 70h
0x1800301d1  mov     rax, cs:__security_cookie
0x1800301d8  xor     rax, rsp
0x1800301db  mov     [rbp+var_8], rax
0x1800301df  xor     eax, eax
0x1800301e1  xorps   xmm0, xmm0
0x1800301e4  xor     r12d, r12d
0x1800301e7  mov     [rbp+var_10], rax
0x1800301eb  xorps   xmm1, xmm1
0x1800301ee  mov     rdi, rdx
0x1800301f1  mov     r14, rcx
0x1800301f4  movups  [rbp+FileInformation], xmm0
0x1800301f8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800301fc  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180030200  test    rdx, rdx
0x180030203  jz      loc_1800303F6
0x180030209  cmp     [rdx], r12w
0x18003020d  jz      loc_1800303F6
0x180030213  test    rcx, rcx
0x180030216  jz      loc_1800303F6
0x18003021c  mov     [rcx], r12
0x18003021f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180030223  call    cs:__imp_RtlInitUnicodeString
0x180030229  mov     rcx, gs:60h
0x180030232  lea     edx, [r12+8]; Flags
0x180030237  lea     r8d, [r12+50h]; Size
0x18003023c  mov     rcx, [rcx+30h]; HeapHandle
0x180030240  call    cs:__imp_RtlAllocateHeap
0x180030246  mov     rsi, rax
0x180030249  test    rax, rax
0x18003024c  jnz     short loc_180030258
0x18003024e  mov     ebx, 0C0000017h
0x180030253  jmp     loc_1800303E2
0x180030258  mov     rdx, rdi
0x18003025b  mov     rcx, rsi
0x18003025e  call    AslStringDuplicate
0x180030263  mov     ebx, eax
0x180030265  test    eax, eax
0x180030267  jns     short loc_18003027B
0x180030269  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x180030270  mov     r8d, 7Bh ; '{'
0x180030276  jmp     loc_1800303A5
0x18003027b  mov     r8d, 0Ch; MaxCount
0x180030281  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x180030288  mov     rcx, rdi; String1
0x18003028b  call    _wcsnicmp
0x180030290  test    eax, eax
0x180030292  jz      short loc_1800302D9
0x180030294  xor     r9d, r9d
0x180030297  lea     rdx, [rbp+DestinationString]
0x18003029b  xor     r8d, r8d
0x18003029e  mov     rcx, rdi
0x1800302a1  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800302a7  mov     ebx, eax
0x1800302a9  test    eax, eax
0x1800302ab  jns     short loc_1800302D9
0x1800302ad  mov     [rsp+70h+var_48], eax
0x1800302b1  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800302b8  mov     r8d, 94h
0x1800302be  mov     ecx, 1
0x1800302c3  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x1800302ca  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x1800302cf  call    AslLogCallPrintf
0x1800302d4  jmp     loc_1800303BA
0x1800302d9  lea     rdx, [rbp+DestinationString]
0x1800302dd  lea     rcx, [rsi+8]
0x1800302e1  call    RtlFileMapInitializeByNtPath
0x1800302e6  mov     ebx, eax
0x1800302e8  test    eax, eax
0x1800302ea  jns     short loc_180030360
0x1800302ec  cmp     eax, 0C000003Ah
0x1800302f1  jz      loc_1800303BA
0x1800302f7  cmp     eax, 0C0000034h
0x1800302fc  jz      loc_1800303BA
0x180030302  cmp     eax, 0C00000CCh
0x180030307  jz      loc_1800303BA
0x18003030d  add     eax, 3FFFFFEDh
0x180030312  cmp     eax, 30h ; '0'
0x180030315  ja      short loc_180030327
0x180030317  mov     rcx, 1000000008001h
0x180030321  bt      rcx, rax
0x180030325  jb      short loc_180030345
0x180030327  cmp     ebx, 0C00000BAh
0x18003032d  jz      short loc_180030345
0x18003032f  mov     [rsp+70h+var_48], ebx
0x180030333  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18003033a  mov     r8d, 0A1h
0x180030340  jmp     loc_1800302BE
0x180030345  mov     [rsp+70h+var_48], ebx
0x180030349  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180030350  mov     r8d, 0A3h
0x180030356  mov     ecx, 3
0x18003035b  jmp     loc_1800302C3
0x180030360  xor     eax, eax
0x180030362  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x18003036a  xorps   xmm0, xmm0
0x18003036d  mov     [rbp+var_10], rax
0x180030371  xorps   xmm1, xmm1
0x180030374  lea     r8, [rbp+FileInformation]; FileInformation
0x180030378  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18003037c  lea     r9d, [rax+18h]; Length
0x180030380  movups  [rbp+FileInformation], xmm1
0x180030384  mov     rcx, [rsi+8]; FileHandle
0x180030388  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18003038c  call    cs:__imp_ZwQueryInformationFile
0x180030392  mov     ebx, eax
0x180030394  test    eax, eax
0x180030396  jns     short loc_1800303C4
0x180030398  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x18003039f  mov     r8d, 0B7h
0x1800303a5  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x1800303ac  mov     [rsp+70h+FileInformationClass], eax
0x1800303b0  mov     ecx, 1
0x1800303b5  call    AslLogCallPrintf
0x1800303ba  mov     rcx, rsi
0x1800303bd  call    AslFileMappingDelete
0x1800303c2  jmp     short loc_1800303E2
0x1800303c4  mov     rax, qword ptr [rbp+FileInformation+8]
0x1800303c8  mov     ebx, r12d
0x1800303cb  mov     [rsi+18h], rax
0x1800303cf  mov     rax, qword ptr [rbp+FileInformation+8]
0x1800303d3  neg     rax
0x1800303d6  sbb     ecx, ecx
0x1800303d8  neg     ecx
0x1800303da  inc     ecx
0x1800303dc  mov     [rsi+38h], ecx
0x1800303df  mov     [r14], rsi
0x1800303e2  cmp     [rbp+DestinationString.Buffer], rdi
0x1800303e6  jz      short loc_1800303F2
0x1800303e8  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800303ec  call    cs:__imp_RtlFreeUnicodeString
0x1800303f2  mov     eax, ebx
0x1800303f4  jmp     short loc_1800303FB
0x1800303f6  mov     eax, 0C000000Dh
0x1800303fb  mov     rcx, [rbp+var_8]
0x1800303ff  xor     rcx, rsp; StackCookie
0x180030402  call    __security_check_cookie
0x180030407  lea     r11, [rsp+70h+var_s0]
0x18003040c  mov     rbx, [r11+40h]
0x180030410  mov     rsi, [r11+48h]
0x180030414  mov     rsp, r11
0x180030417  pop     r15
0x180030419  pop     r14
0x18003041b  pop     r12
0x18003041d  pop     rdi
0x18003041e  pop     rbp
0x18003041f  retn
```
