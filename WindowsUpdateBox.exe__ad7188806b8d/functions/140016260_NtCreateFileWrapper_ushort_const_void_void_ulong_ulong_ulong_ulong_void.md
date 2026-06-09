# NtCreateFileWrapper(ushort const *,void *,void *,ulong,ulong,ulong,ulong,void * *)

- ea: `0x140016260`
- end: `0x14001652d`
- name: `?NtCreateFileWrapper@@YAJPEBGPEAX1KKKKPEAPEAX@Z`
- size: `717`
- prototype: `int(const unsigned __int16 *, void *, void *, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a7d0`

## callees

- `0x140006538`
- `0x1400076c8`
- `0x140008434`
- `0x14000f4a4`
- `0x1400135b8`
- `0x140016260`
- `0x140027438`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140016479`
- `KERNEL32!CloseHandle` at `0x140016479`
- `KERNEL32!HeapFree` at `0x1400164a8`
- `KERNEL32!HeapFree` at `0x1400164d5`
- `KERNEL32!HeapFree` at `0x1400164fc`
- `KERNEL32!HeapFree` at `0x1400164a8`
- `KERNEL32!HeapFree` at `0x1400164d5`
- `KERNEL32!HeapFree` at `0x1400164fc`
- `KERNEL32!GetProcessHeap` at `0x140016493`
- `KERNEL32!GetProcessHeap` at `0x1400164c1`
- `KERNEL32!GetProcessHeap` at `0x1400164e7`
- `KERNEL32!GetProcessHeap` at `0x140016493`
- `KERNEL32!GetProcessHeap` at `0x1400164c1`
- `KERNEL32!GetProcessHeap` at `0x1400164e7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140016330`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140016330`
- `ntdll!RtlInitUnicodeString` at `0x1400163ba`
- `ntdll!RtlInitUnicodeString` at `0x1400163ba`
- `ntdll!NtCreateFile` at `0x140016429`
- `ntdll!NtCreateFile` at `0x140016429`
- `ntdll!RtlFreeUnicodeString` at `0x14001636b`
- `ntdll!RtlFreeUnicodeString` at `0x14001636b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NtCreateFileWrapper(
        const unsigned __int16 *a1,
        void *a2,
        void *a3,
        ACCESS_MASK a4,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        void **a8)
{
  LPWSTR v10; // rsi
  _WORD *v11; // r14
  void **v12; // r15
  int FullPathNameW; // eax
  int v14; // edi
  int v15; // ecx
  int v16; // ecx
  _WORD *v17; // rcx
  int v18; // eax
  NTSTATUS v19; // eax
  void *v20; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  void *FileHandle; // [rsp+70h] [rbp-81h] BYREF
  LPWSTR v25; // [rsp+78h] [rbp-79h] BYREF
  _WORD *v26; // [rsp+80h] [rbp-71h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-29h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-19h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-11h] BYREF
  void *Src; // [rsp+138h] [rbp+47h] BYREF
  void *v33; // [rsp+148h] [rbp+57h]

  v33 = a3;
  v30 = -2;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Src = 0;
  v10 = 0;
  v25 = 0;
  v11 = 0;
  v26 = 0;
  DestinationString = 0;
  FileHandle = 0;
  if ( a1 )
  {
    v12 = a8;
    if ( a8 )
    {
      FullPathNameW = CMiscHelpersT<CEmptyType>::GetFullPathNameW(a1, &v25, (WCHAR **)&Src);
      v14 = FullPathNameW;
      if ( FullPathNameW < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(FullPathNameW);
        v10 = v25;
        goto LABEL_22;
      }
      v10 = v25;
      if ( a2 )
      {
        v17 = Src;
LABEL_14:
        v18 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v17);
        v14 = v18;
        LODWORD(Src) = v18;
        if ( v18 < 0 )
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
          goto LABEL_22;
        }
        RtlInitUnicodeString(&DestinationString, 0);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = a2;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.SecurityDescriptor = v33;
        ObjectAttributes.SecurityQualityOfService = 0;
        v19 = NtCreateFile(
                &FileHandle,
                a4,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0x80u,
                ShareAccess,
                CreateDisposition,
                CreateOptions,
                0,
                0);
        if ( SErrorConverterT<CEmptyType>::C_NtStatus2HR(v19, &Src) )
        {
          v20 = FileHandle;
          FileHandle = 0;
          *v12 = v20;
          v14 = (int)Src;
          goto LABEL_22;
        }
        v14 = (int)Src;
        goto LABEL_20;
      }
      UnicodeString = 0;
      if ( v25 )
      {
        v11 = 0;
        v26 = 0;
        v15 = RtlDosPathNameToNtPathName_U_WithStatus(v25, &UnicodeString, 0, 0);
        v14 = 0;
        if ( v15 < 0 )
          v14 = v15 | 0x10000000;
        if ( v14 >= 0 )
        {
          v14 = StrAllocatingPrintf(&v26, L"%wZ", &UnicodeString);
          v11 = v26;
        }
        RtlFreeUnicodeString(&UnicodeString);
        v16 = v14;
        if ( v14 < 0 )
          goto LABEL_21;
        v17 = v11;
        goto LABEL_14;
      }
    }
  }
  v14 = -2147024809;
LABEL_20:
  v16 = v14;
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
  if ( FileHandle )
  {
    CloseHandle(FileHandle);
    FileHandle = 0;
  }
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  if ( v10 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v10 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140016260  mov     rax, rsp
0x140016263  mov     [rax+18h], r8
0x140016267  push    rbp
0x140016268  push    rsi
0x140016269  push    rdi
0x14001626a  push    r12
0x14001626c  push    r13
0x14001626e  push    r14
0x140016270  push    r15
0x140016272  lea     rbp, [rax-3Fh]
0x140016276  sub     rsp, 0F0h
0x14001627d  mov     [rbp+37h+var_50], 0FFFFFFFFFFFFFFFEh
0x140016285  mov     [rax+10h], rbx
0x140016289  mov     r13d, r9d
0x14001628c  mov     r12, rdx
0x14001628f  xorps   xmm0, xmm0
0x140016292  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x140016296  xorps   xmm1, xmm1
0x140016299  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm1
0x14001629d  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x1400162a1  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400162a5  mov     [rbp+37h+Src], 0
0x1400162ad  xor     esi, esi
0x1400162af  mov     [rbp+37h+var_B0], rsi
0x1400162b3  xor     r14d, r14d
0x1400162b6  mov     [rbp+37h+var_A8], r14
0x1400162ba  xor     ebx, ebx
0x1400162bc  mov     [rsp+120h+SourceString], rbx
0x1400162c1  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x1400162c5  mov     [rsp+120h+FileHandle], rbx
0x1400162ca  test    rcx, rcx
0x1400162cd  jz      loc_14001645B
0x1400162d3  mov     r15, [rbp+37h+arg_38]
0x1400162d7  test    r15, r15
0x1400162da  jz      loc_14001645B
0x1400162e0  lea     r8, [rbp+37h+Src]
0x1400162e4  lea     rdx, [rbp+37h+var_B0]
0x1400162e8  call    ?GetFullPathNameW@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG1@Z; CMiscHelpersT<CEmptyType>::GetFullPathNameW(ushort const *,ushort * *,ushort * *)
0x1400162ed  mov     edi, eax
0x1400162ef  test    eax, eax
0x1400162f1  jns     short loc_140016303
0x1400162f3  mov     ecx, eax
0x1400162f5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400162fa  mov     rsi, [rbp+37h+var_B0]
0x1400162fe  jmp     loc_140016467
0x140016303  mov     rsi, [rbp+37h+var_B0]
0x140016307  test    r12, r12
0x14001630a  jnz     short loc_140016386
0x14001630c  xorps   xmm0, xmm0
0x14001630f  movups  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x140016313  test    rsi, rsi
0x140016316  jz      loc_14001645B
0x14001631c  xor     r14d, r14d
0x14001631f  mov     [rbp+37h+var_A8], r14
0x140016323  xor     r9d, r9d
0x140016326  xor     r8d, r8d
0x140016329  lea     rdx, [rbp+37h+UnicodeString]
0x14001632d  mov     rcx, rsi
0x140016330  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140016337  nop     dword ptr [rax+rax+00h]
0x14001633c  mov     ecx, eax
0x14001633e  bts     eax, 1Ch
0x140016342  xor     edi, edi
0x140016344  test    ecx, ecx
0x140016346  cmovs   edi, eax
0x140016349  test    edi, edi
0x14001634b  js      short loc_140016367
0x14001634d  lea     r8, [rbp+37h+UnicodeString]
0x140016351  lea     rdx, aWz; "%wZ"
0x140016358  lea     rcx, [rbp+37h+var_A8]
0x14001635c  call    StrAllocatingPrintf
0x140016361  mov     edi, eax
0x140016363  mov     r14, [rbp+37h+var_A8]
0x140016367  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x14001636b  call    cs:__imp_RtlFreeUnicodeString
0x140016372  nop     dword ptr [rax+rax+00h]
0x140016377  mov     ecx, edi
0x140016379  test    edi, edi
0x14001637b  js      loc_140016462
0x140016381  mov     rcx, r14
0x140016384  jmp     short loc_14001638A
0x140016386  mov     rcx, [rbp+37h+Src]; Src
0x14001638a  lea     rdx, [rsp+120h+SourceString]
0x14001638f  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x140016394  mov     edi, eax
0x140016396  mov     dword ptr [rbp+37h+Src], eax
0x140016399  test    eax, eax
0x14001639b  jns     short loc_1400163AE
0x14001639d  mov     ecx, eax
0x14001639f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400163a4  mov     rbx, [rsp+120h+SourceString]
0x1400163a9  jmp     loc_140016467
0x1400163ae  mov     rbx, [rsp+120h+SourceString]
0x1400163b3  mov     rdx, rbx; SourceString
0x1400163b6  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x1400163ba  call    cs:__imp_RtlInitUnicodeString
0x1400163c1  nop     dword ptr [rax+rax+00h]
0x1400163c6  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1400163cd  mov     [rbp+37h+ObjectAttributes.RootDirectory], r12
0x1400163d1  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x1400163d8  lea     rax, [rbp+37h+DestinationString]
0x1400163dc  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x1400163e0  mov     rax, [rbp+37h+arg_10]
0x1400163e4  mov     [rbp+37h+ObjectAttributes.SecurityDescriptor], rax
0x1400163e8  xor     edi, edi
0x1400163ea  mov     [rbp+37h+ObjectAttributes.SecurityQualityOfService], rdi
0x1400163ee  mov     [rsp+50h], edi; EaLength
0x1400163f2  mov     [rsp+120h+EaBuffer], rdi; EaBuffer
0x1400163f7  mov     eax, [rbp+37h+arg_30]
0x1400163fa  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x1400163fe  mov     eax, [rbp+37h+arg_28]
0x140016401  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x140016405  mov     eax, [rbp+37h+arg_20]
0x140016408  mov     [rsp+120h+ShareAccess], eax; ShareAccess
0x14001640c  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x140016414  mov     [rsp+120h+AllocationSize], rdi; AllocationSize
0x140016419  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x14001641d  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x140016421  mov     edx, r13d; DesiredAccess
0x140016424  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x140016429  call    cs:__imp_NtCreateFile
0x140016430  nop     dword ptr [rax+rax+00h]
0x140016435  mov     ecx, eax
0x140016437  lea     rdx, [rbp+37h+Src]
0x14001643b  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x140016440  test    eax, eax
0x140016442  jnz     short loc_140016449
0x140016444  mov     edi, dword ptr [rbp+37h+Src]
0x140016447  jmp     short loc_140016460
0x140016449  mov     rax, [rsp+120h+FileHandle]
0x14001644e  mov     [rsp+120h+FileHandle], rdi
0x140016453  mov     [r15], rax
0x140016456  mov     edi, dword ptr [rbp+37h+Src]
0x140016459  jmp     short loc_140016467
0x14001645b  mov     edi, 80070057h
0x140016460  mov     ecx, edi
0x140016462  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140016467  mov     ecx, edi
0x140016469  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001646e  nop
0x14001646f  mov     rcx, [rsp+120h+FileHandle]; hObject
0x140016474  test    rcx, rcx
0x140016477  jz      short loc_14001648E
0x140016479  call    cs:__imp_CloseHandle
0x140016480  nop     dword ptr [rax+rax+00h]
0x140016485  mov     [rsp+120h+FileHandle], 0
0x14001648e  test    rbx, rbx
0x140016491  jz      short loc_1400164BC
0x140016493  call    cs:__imp_GetProcessHeap
0x14001649a  nop     dword ptr [rax+rax+00h]
0x14001649f  mov     rcx, rax; hHeap
0x1400164a2  lea     r8, [rbx-4]; lpMem
0x1400164a6  xor     edx, edx; dwFlags
0x1400164a8  call    cs:__imp_HeapFree
0x1400164af  nop     dword ptr [rax+rax+00h]
0x1400164b4  xor     ecx, ecx
0x1400164b6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400164bb  nop
0x1400164bc  test    r14, r14
0x1400164bf  jz      short loc_1400164E2
0x1400164c1  call    cs:__imp_GetProcessHeap
0x1400164c8  nop     dword ptr [rax+rax+00h]
0x1400164cd  mov     rcx, rax; hHeap
0x1400164d0  mov     r8, r14; lpMem
0x1400164d3  xor     edx, edx; dwFlags
0x1400164d5  call    cs:__imp_HeapFree
0x1400164dc  nop     dword ptr [rax+rax+00h]
0x1400164e1  nop
0x1400164e2  test    rsi, rsi
0x1400164e5  jz      short loc_14001650F
0x1400164e7  call    cs:__imp_GetProcessHeap
0x1400164ee  nop     dword ptr [rax+rax+00h]
0x1400164f3  mov     rcx, rax; hHeap
0x1400164f6  lea     r8, [rsi-4]; lpMem
0x1400164fa  xor     edx, edx; dwFlags
0x1400164fc  call    cs:__imp_HeapFree
0x140016503  nop     dword ptr [rax+rax+00h]
0x140016508  xor     ecx, ecx
0x14001650a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001650f  mov     eax, edi
0x140016511  mov     rbx, [rsp+120h+arg_8]
0x140016519  add     rsp, 0F0h
0x140016520  pop     r15
0x140016522  pop     r14
0x140016524  pop     r13
0x140016526  pop     r12
0x140016528  pop     rdi
0x140016529  pop     rsi
0x14001652a  pop     rbp
0x14001652b  retn
```
