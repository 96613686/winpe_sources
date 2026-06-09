# CodeAuthzFullyQualifyFilename

- ea: `0x180017460`
- end: `0x18001779b`
- name: `CodeAuthzFullyQualifyFilename`
- size: `827`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180016e28`

## callees

- `0x180017460`
- `0x1800177a4`
- `0x180018708`
- `0x180018c08`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x1800176ee`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800176ee`
- `ntdll!RtlCreateUnicodeString` at `0x18001767d`
- `ntdll!RtlCreateUnicodeString` at `0x18001767d`
- `ntdll!RtlPrefixUnicodeString` at `0x1800175a8`
- `ntdll!RtlPrefixUnicodeString` at `0x1800175a8`
- `ntdll!RtlGetFullPathName_U` at `0x180017744`
- `ntdll!RtlGetFullPathName_U` at `0x180017744`
- `ntdll!RtlFreeHeap` at `0x1800176a9`
- `ntdll!RtlFreeHeap` at `0x1800176d0`
- `ntdll!RtlFreeHeap` at `0x1800176a9`
- `ntdll!RtlFreeHeap` at `0x1800176d0`
- `ntdll!RtlAllocateHeap` at `0x180017641`
- `ntdll!RtlAllocateHeap` at `0x180017723`
- `ntdll!RtlAllocateHeap` at `0x180017641`
- `ntdll!RtlAllocateHeap` at `0x180017723`
- `ntdll!RtlInitUnicodeString` at `0x18001757f`
- `ntdll!RtlInitUnicodeString` at `0x18001757f`
- `KERNEL32!GetLongPathNameW` at `0x180017667`
- `KERNEL32!GetLongPathNameW` at `0x180017667`
- `KERNEL32!GetVolumePathNameW` at `0x180017565`
- `KERNEL32!GetVolumePathNameW` at `0x180017565`

## pseudocode

```c
__int64 __fastcall CodeAuthzFullyQualifyFilename(
        HANDLE FileHandle,
        char a2,
        const WCHAR *a3,
        struct _UNICODE_STRING *a4)
{
  unsigned int FilenameFromHandle; // ebx
  const WCHAR *v9; // r12
  signed int v10; // ebx
  char v12; // al
  WCHAR v13; // dx
  WCHAR *v14; // rdi
  int v15; // r14d
  WCHAR *v16; // rax
  WCHAR *v17; // rsi
  WCHAR *Heap; // rax
  ULONG FullPathName_U; // eax
  __int16 v20; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-D8h] BYREF
  const WCHAR *v22; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v20 = 0;
  FilenameFromHandle = -1073741823;
  memset_0(szVolumePathName, 0, 0x20Au);
  v22 = a3;
  v9 = a3;
  DestinationString = 0;
  if ( !FileHandle )
  {
LABEL_34:
    if ( !a3 )
      return FilenameFromHandle;
    goto LABEL_11;
  }
  if ( !a3 )
    return FilenameFromHandle;
  if ( a2 )
  {
    v12 = SaferpQueryCanonicalizedDriveLetterFromNtPathname(FileHandle, a3, &v20, &v22);
    v9 = v22;
    v10 = v12 == 0 ? 0xC0000001 : 0;
  }
  else
  {
    v10 = 0;
    if ( !(unsigned __int8)SaferpQueryCanonicalizedDriveLetterFromDosPathname(FileHandle, a3, &v20) )
      v10 = -1073741823;
  }
  if ( (!v20 || GetVolumePathNameW(v9, szVolumePathName, 0x105u)) && v10 >= 0 )
  {
    FilenameFromHandle = SaferpQueryFilenameFromHandle(FileHandle);
    if ( (FilenameFromHandle & 0x80000000) == 0 )
      return FilenameFromHandle;
    goto LABEL_34;
  }
LABEL_11:
  RtlInitUnicodeString(&DestinationString, a3);
  if ( a2 )
  {
    if ( !RtlPrefixUnicodeString(&String1, &DestinationString, 1u) )
      return (unsigned int)-1073741823;
    if ( DestinationString.Length < 0xCu )
      return (unsigned int)-1073741823;
    if ( DestinationString.Buffer[5] != 58 )
      return (unsigned int)-1073741823;
    v13 = DestinationString.Buffer[4];
    if ( (unsigned __int16)(v13 - 65) > 0x19u && (unsigned __int16)(v13 - 97) > 0x19u )
      return (unsigned int)-1073741823;
    if ( DestinationString.Buffer[6] != 92 )
      return (unsigned int)-1073741823;
    DestinationString.Buffer += 4;
    v14 = 0;
    DestinationString.Length -= 8;
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x208u);
    v14 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    FullPathName_U = RtlGetFullPathName_U(DestinationString.Buffer, 0x208u, Heap, 0);
    if ( FullPathName_U - 1 > 0x206 )
    {
      FilenameFromHandle = -1073741823;
LABEL_27:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      return FilenameFromHandle;
    }
    DestinationString.Buffer = v14;
    DestinationString.Length = FullPathName_U;
    DestinationString.MaximumLength = 520;
  }
  v15 = 0;
  v16 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x208u);
  v17 = v16;
  if ( v16 )
  {
    if ( GetLongPathNameW(DestinationString.Buffer, v16, 0x104u) )
    {
      if ( !RtlCreateUnicodeString(a4, v17) )
        v15 = -1073741801;
      FilenameFromHandle = v15;
    }
    else
    {
      FilenameFromHandle = RtlDuplicateUnicodeString(3u, &DestinationString, a4);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  }
  else
  {
    FilenameFromHandle = -1073741801;
  }
  if ( v14 )
    goto LABEL_27;
  return FilenameFromHandle;
}

```

## disassembly

```asm
0x180017460  mov     [rsp-8+arg_8], rbx
0x180017465  push    rbp
0x180017466  push    rsi
0x180017467  push    rdi
0x180017468  push    r12
0x18001746a  push    r13
0x18001746c  push    r14
0x18001746e  push    r15
0x180017470  lea     rbp, [rsp-160h]
0x180017478  sub     rsp, 260h
0x18001747f  mov     rax, cs:__security_cookie
0x180017486  xor     rax, rsp
0x180017489  mov     [rbp+190h+var_40], rax
0x180017490  mov     rdi, r8
0x180017493  mov     r15b, dl
0x180017496  mov     r14, rcx
0x180017499  xor     esi, esi
0x18001749b  xor     edx, edx; Val
0x18001749d  mov     [rsp+290h+var_270], si
0x1800174a2  mov     r8d, 20Ah; Size
0x1800174a8  lea     rcx, [rsp+290h+szVolumePathName]; void *
0x1800174ad  mov     r13, r9
0x1800174b0  mov     ebx, 0C0000001h
0x1800174b5  call    memset_0
0x1800174ba  mov     [rsp+290h+var_258], rdi
0x1800174bf  xorps   xmm0, xmm0
0x1800174c2  mov     r12, rdi
0x1800174c5  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x1800174ca  test    r14, r14
0x1800174cd  jz      loc_18001776F
0x1800174d3  test    rdi, rdi
0x1800174d6  jz      short loc_18001752A
0x1800174d8  lea     r8, [rsp+290h+var_270]
0x1800174dd  mov     rdx, rdi
0x1800174e0  mov     rcx, r14
0x1800174e3  test    r15b, r15b
0x1800174e6  jnz     loc_1800175C2
0x1800174ec  mov     ebx, esi
0x1800174ee  call    SaferpQueryCanonicalizedDriveLetterFromDosPathname
0x1800174f3  test    al, al
0x1800174f5  mov     eax, 0C0000001h
0x1800174fa  cmovz   ebx, eax
0x1800174fd  movzx   esi, [rsp+290h+var_270]
0x180017502  test    si, si
0x180017505  jnz     short loc_180017557
0x180017507  test    ebx, ebx
0x180017509  js      short loc_180017575
0x18001750b  mov     r9, r13
0x18001750e  lea     r8, [rsp+290h+szVolumePathName]
0x180017513  movzx   edx, si
0x180017516  mov     rcx, r14; FileHandle
0x180017519  call    SaferpQueryFilenameFromHandle
0x18001751e  xor     esi, esi
0x180017520  mov     ebx, eax
0x180017522  test    eax, eax
0x180017524  js      loc_18001776F
0x18001752a  mov     eax, ebx
0x18001752c  mov     rcx, [rbp+190h+var_40]
0x180017533  xor     rcx, rsp; StackCookie
0x180017536  call    __security_check_cookie
0x18001753b  mov     rbx, [rsp+290h+arg_8]
0x180017543  add     rsp, 260h
0x18001754a  pop     r15
0x18001754c  pop     r14
0x18001754e  pop     r13
0x180017550  pop     r12
0x180017552  pop     rdi
0x180017553  pop     rsi
0x180017554  pop     rbp
0x180017555  retn
0x180017557  mov     r8d, 105h; cchBufferLength
0x18001755d  lea     rdx, [rsp+290h+szVolumePathName]; lpszVolumePathName
0x180017562  mov     rcx, r12; lpszFileName
0x180017565  call    cs:__imp_GetVolumePathNameW
0x18001756c  nop     dword ptr [rax+rax+00h]
0x180017571  test    eax, eax
0x180017573  jnz     short loc_180017507
0x180017575  xor     esi, esi
0x180017577  mov     rdx, rdi; SourceString
0x18001757a  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x18001757f  call    cs:__imp_RtlInitUnicodeString
0x180017586  nop     dword ptr [rax+rax+00h]
0x18001758b  mov     ebx, 208h
0x180017590  test    r15b, r15b
0x180017593  jz      loc_180017711
0x180017599  mov     r8b, 1; CaseInsensitive
0x18001759c  lea     rdx, [rsp+290h+DestinationString]; String2
0x1800175a1  lea     rcx, String1; String1
0x1800175a8  call    cs:__imp_RtlPrefixUnicodeString
0x1800175af  nop     dword ptr [rax+rax+00h]
0x1800175b4  test    al, al
0x1800175b6  jnz     short loc_1800175E2
0x1800175b8  mov     ebx, 0C0000001h
0x1800175bd  jmp     loc_18001752A
0x1800175c2  lea     r9, [rsp+290h+var_258]
0x1800175c7  call    SaferpQueryCanonicalizedDriveLetterFromNtPathname
0x1800175cc  mov     r12, [rsp+290h+var_258]
0x1800175d1  neg     al
0x1800175d3  sbb     ebx, ebx
0x1800175d5  not     ebx
0x1800175d7  and     ebx, 0C0000001h
0x1800175dd  jmp     loc_1800174FD
0x1800175e2  movzx   ecx, [rsp+290h+DestinationString.Length]
0x1800175e7  cmp     cx, 0Ch
0x1800175eb  jb      short loc_1800175B8
0x1800175ed  mov     r8, [rsp+290h+DestinationString.Buffer]
0x1800175f2  cmp     word ptr [r8+0Ah], 3Ah ; ':'
0x1800175f8  jnz     short loc_1800175B8
0x1800175fa  lea     r9, [r8+8]
0x1800175fe  movzx   edx, word ptr [r9]
0x180017602  lea     eax, [rdx-41h]
0x180017605  cmp     ax, 19h
0x180017609  ja      loc_1800176FE
0x18001760f  cmp     word ptr [r8+0Ch], 5Ch ; '\'
0x180017615  jnz     short loc_1800175B8
0x180017617  mov     eax, 0FFF8h
0x18001761c  mov     [rsp+290h+DestinationString.Buffer], r9
0x180017621  add     cx, ax
0x180017624  mov     rdi, rsi
0x180017627  mov     [rsp+290h+DestinationString.Length], cx
0x18001762c  mov     rcx, gs:60h
0x180017635  mov     r8, rbx; Size
0x180017638  xor     edx, edx; Flags
0x18001763a  mov     r14d, esi
0x18001763d  mov     rcx, [rcx+30h]; HeapHandle
0x180017641  call    cs:__imp_RtlAllocateHeap
0x180017648  nop     dword ptr [rax+rax+00h]
0x18001764d  mov     rsi, rax
0x180017650  test    rax, rax
0x180017653  jz      loc_180017787
0x180017659  mov     rcx, [rsp+290h+DestinationString.Buffer]; lpszShortPath
0x18001765e  mov     r8d, 104h; cchBuffer
0x180017664  mov     rdx, rax; lpszLongPath
0x180017667  call    cs:__imp_GetLongPathNameW
0x18001766e  nop     dword ptr [rax+rax+00h]
0x180017673  test    eax, eax
0x180017675  jz      short loc_1800176E1
0x180017677  mov     rdx, rsi; SourceString
0x18001767a  mov     rcx, r13; DestinationString
0x18001767d  call    cs:__imp_RtlCreateUnicodeString
0x180017684  nop     dword ptr [rax+rax+00h]
0x180017689  mov     ebx, 0C0000017h
0x18001768e  test    al, al
0x180017690  cmovz   r14d, ebx
0x180017694  mov     ebx, r14d
0x180017697  mov     rcx, gs:60h
0x1800176a0  mov     r8, rsi; P
0x1800176a3  xor     edx, edx; Flags
0x1800176a5  mov     rcx, [rcx+30h]; HeapHandle
0x1800176a9  call    cs:__imp_RtlFreeHeap
0x1800176b0  nop     dword ptr [rax+rax+00h]
0x1800176b5  test    rdi, rdi
0x1800176b8  jz      loc_18001752A
0x1800176be  mov     rcx, gs:60h
0x1800176c7  mov     r8, rdi; P
0x1800176ca  xor     edx, edx; Flags
0x1800176cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800176d0  call    cs:__imp_RtlFreeHeap
0x1800176d7  nop     dword ptr [rax+rax+00h]
0x1800176dc  jmp     loc_18001752A
0x1800176e1  mov     r8, r13; DestinationString
0x1800176e4  lea     rdx, [rsp+290h+DestinationString]; SourceString
0x1800176e9  mov     ecx, 3; Flags
0x1800176ee  call    cs:__imp_RtlDuplicateUnicodeString
0x1800176f5  nop     dword ptr [rax+rax+00h]
0x1800176fa  mov     ebx, eax
0x1800176fc  jmp     short loc_180017697
0x1800176fe  sub     dx, 61h ; 'a'
0x180017702  cmp     dx, 19h
0x180017706  jbe     loc_18001760F
0x18001770c  jmp     loc_1800175B8
0x180017711  mov     rcx, gs:60h
0x18001771a  mov     r8, rbx; Size
0x18001771d  xor     edx, edx; Flags
0x18001771f  mov     rcx, [rcx+30h]; HeapHandle
0x180017723  call    cs:__imp_RtlAllocateHeap
0x18001772a  nop     dword ptr [rax+rax+00h]
0x18001772f  mov     rdi, rax
0x180017732  test    rax, rax
0x180017735  jz      short loc_18001777D
0x180017737  mov     rcx, [rsp+290h+DestinationString.Buffer]; FileName
0x18001773c  xor     r9d, r9d; ShortName
0x18001773f  mov     r8, rax; Buffer
0x180017742  mov     edx, ebx; Size
0x180017744  call    cs:__imp_RtlGetFullPathName_U
0x18001774b  nop     dword ptr [rax+rax+00h]
0x180017750  lea     ecx, [rax-1]
0x180017753  cmp     ecx, 206h
0x180017759  ja      short loc_180017791
0x18001775b  mov     [rsp+290h+DestinationString.Buffer], rdi
0x180017760  mov     [rsp+290h+DestinationString.Length], ax
0x180017765  mov     [rsp+290h+DestinationString.MaximumLength], bx
0x18001776a  jmp     loc_18001762C
0x18001776f  test    rdi, rdi
0x180017772  jnz     loc_180017577
0x180017778  jmp     loc_18001752A
0x18001777d  mov     ebx, 0C0000017h
0x180017782  jmp     loc_18001752A
0x180017787  mov     ebx, 0C0000017h
0x18001778c  jmp     loc_1800176B5
0x180017791  mov     ebx, 0C0000001h
0x180017796  jmp     loc_1800176BE
```
