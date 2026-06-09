# CodeAuthzFullyQualifyFilename

- ea: `0x180011eb4`
- end: `0x1800121ac`
- name: `CodeAuthzFullyQualifyFilename`
- size: `760`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800118c0`

## callees

- `0x180011eb4`
- `0x1800121b4`
- `0x1800130ec`
- `0x1800135b8`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x180012111`
- `ntdll!RtlDuplicateUnicodeString` at `0x180012111`
- `ntdll!RtlCreateUnicodeString` at `0x1800120b2`
- `ntdll!RtlCreateUnicodeString` at `0x1800120b2`
- `ntdll!RtlPrefixUnicodeString` at `0x180011fef`
- `ntdll!RtlPrefixUnicodeString` at `0x180011fef`
- `ntdll!RtlGetFullPathName_U` at `0x18001215b`
- `ntdll!RtlGetFullPathName_U` at `0x18001215b`
- `ntdll!RtlFreeHeap` at `0x1800120d8`
- `ntdll!RtlFreeHeap` at `0x1800120f9`
- `ntdll!RtlFreeHeap` at `0x1800120d8`
- `ntdll!RtlFreeHeap` at `0x1800120f9`
- `ntdll!RtlAllocateHeap` at `0x180012082`
- `ntdll!RtlAllocateHeap` at `0x180012140`
- `ntdll!RtlAllocateHeap` at `0x180012082`
- `ntdll!RtlAllocateHeap` at `0x180012140`
- `ntdll!RtlInitUnicodeString` at `0x180011fcc`
- `ntdll!RtlInitUnicodeString` at `0x180011fcc`
- `KERNEL32!GetLongPathNameW` at `0x1800120a2`
- `KERNEL32!GetLongPathNameW` at `0x1800120a2`
- `KERNEL32!GetVolumePathNameW` at `0x180011fb8`
- `KERNEL32!GetVolumePathNameW` at `0x180011fb8`

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
0x180011eb4  mov     [rsp-8+arg_8], rbx
0x180011eb9  push    rbp
0x180011eba  push    rsi
0x180011ebb  push    rdi
0x180011ebc  push    r12
0x180011ebe  push    r13
0x180011ec0  push    r14
0x180011ec2  push    r15
0x180011ec4  lea     rbp, [rsp-160h]
0x180011ecc  sub     rsp, 260h
0x180011ed3  mov     rax, cs:__security_cookie
0x180011eda  xor     rax, rsp
0x180011edd  mov     [rbp+190h+var_40], rax
0x180011ee4  mov     rdi, r8
0x180011ee7  mov     r15b, dl
0x180011eea  mov     r14, rcx
0x180011eed  xor     esi, esi
0x180011eef  xor     edx, edx; Val
0x180011ef1  mov     [rsp+290h+var_270], si
0x180011ef6  mov     r8d, 20Ah; Size
0x180011efc  lea     rcx, [rsp+290h+szVolumePathName]; void *
0x180011f01  mov     r13, r9
0x180011f04  mov     ebx, 0C0000001h
0x180011f09  call    memset_0
0x180011f0e  mov     [rsp+290h+var_258], rdi
0x180011f13  xorps   xmm0, xmm0
0x180011f16  mov     r12, rdi
0x180011f19  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180011f1e  test    r14, r14
0x180011f21  jz      loc_180012180
0x180011f27  test    rdi, rdi
0x180011f2a  jz      short loc_180011F7E
0x180011f2c  lea     r8, [rsp+290h+var_270]
0x180011f31  mov     rdx, rdi
0x180011f34  mov     rcx, r14
0x180011f37  test    r15b, r15b
0x180011f3a  jnz     loc_180012003
0x180011f40  mov     ebx, esi
0x180011f42  call    SaferpQueryCanonicalizedDriveLetterFromDosPathname
0x180011f47  test    al, al
0x180011f49  mov     eax, 0C0000001h
0x180011f4e  cmovz   ebx, eax
0x180011f51  movzx   esi, [rsp+290h+var_270]
0x180011f56  test    si, si
0x180011f59  jnz     short loc_180011FAA
0x180011f5b  test    ebx, ebx
0x180011f5d  js      short loc_180011FC2
0x180011f5f  mov     r9, r13
0x180011f62  lea     r8, [rsp+290h+szVolumePathName]
0x180011f67  movzx   edx, si
0x180011f6a  mov     rcx, r14; FileHandle
0x180011f6d  call    SaferpQueryFilenameFromHandle
0x180011f72  xor     esi, esi
0x180011f74  mov     ebx, eax
0x180011f76  test    eax, eax
0x180011f78  js      loc_180012180
0x180011f7e  mov     eax, ebx
0x180011f80  mov     rcx, [rbp+190h+var_40]
0x180011f87  xor     rcx, rsp; StackCookie
0x180011f8a  call    __security_check_cookie
0x180011f8f  mov     rbx, [rsp+290h+arg_8]
0x180011f97  add     rsp, 260h
0x180011f9e  pop     r15
0x180011fa0  pop     r14
0x180011fa2  pop     r13
0x180011fa4  pop     r12
0x180011fa6  pop     rdi
0x180011fa7  pop     rsi
0x180011fa8  pop     rbp
0x180011fa9  retn
0x180011faa  mov     r8d, 105h; cchBufferLength
0x180011fb0  lea     rdx, [rsp+290h+szVolumePathName]; lpszVolumePathName
0x180011fb5  mov     rcx, r12; lpszFileName
0x180011fb8  call    cs:__imp_GetVolumePathNameW
0x180011fbe  test    eax, eax
0x180011fc0  jnz     short loc_180011F5B
0x180011fc2  xor     esi, esi
0x180011fc4  mov     rdx, rdi; SourceString
0x180011fc7  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x180011fcc  call    cs:__imp_RtlInitUnicodeString
0x180011fd2  mov     ebx, 208h
0x180011fd7  test    r15b, r15b
0x180011fda  jz      loc_18001212E
0x180011fe0  mov     r8b, 1; CaseInsensitive
0x180011fe3  lea     rdx, [rsp+290h+DestinationString]; String2
0x180011fe8  lea     rcx, String1; String1
0x180011fef  call    cs:__imp_RtlPrefixUnicodeString
0x180011ff5  test    al, al
0x180011ff7  jnz     short loc_180012023
0x180011ff9  mov     ebx, 0C0000001h
0x180011ffe  jmp     loc_180011F7E
0x180012003  lea     r9, [rsp+290h+var_258]
0x180012008  call    SaferpQueryCanonicalizedDriveLetterFromNtPathname
0x18001200d  mov     r12, [rsp+290h+var_258]
0x180012012  neg     al
0x180012014  sbb     ebx, ebx
0x180012016  not     ebx
0x180012018  and     ebx, 0C0000001h
0x18001201e  jmp     loc_180011F51
0x180012023  movzx   ecx, [rsp+290h+DestinationString.Length]
0x180012028  cmp     cx, 0Ch
0x18001202c  jb      short loc_180011FF9
0x18001202e  mov     r8, [rsp+290h+DestinationString.Buffer]
0x180012033  cmp     word ptr [r8+0Ah], 3Ah ; ':'
0x180012039  jnz     short loc_180011FF9
0x18001203b  lea     r9, [r8+8]
0x18001203f  movzx   edx, word ptr [r9]
0x180012043  lea     eax, [rdx-41h]
0x180012046  cmp     ax, 19h
0x18001204a  ja      loc_18001211B
0x180012050  cmp     word ptr [r8+0Ch], 5Ch ; '\'
0x180012056  jnz     short loc_180011FF9
0x180012058  mov     eax, 0FFF8h
0x18001205d  mov     [rsp+290h+DestinationString.Buffer], r9
0x180012062  add     cx, ax
0x180012065  mov     rdi, rsi
0x180012068  mov     [rsp+290h+DestinationString.Length], cx
0x18001206d  mov     rcx, gs:60h
0x180012076  mov     r8, rbx; Size
0x180012079  xor     edx, edx; Flags
0x18001207b  mov     r14d, esi
0x18001207e  mov     rcx, [rcx+30h]; HeapHandle
0x180012082  call    cs:__imp_RtlAllocateHeap
0x180012088  mov     rsi, rax
0x18001208b  test    rax, rax
0x18001208e  jz      loc_180012198
0x180012094  mov     rcx, [rsp+290h+DestinationString.Buffer]; lpszShortPath
0x180012099  mov     r8d, 104h; cchBuffer
0x18001209f  mov     rdx, rax; lpszLongPath
0x1800120a2  call    cs:__imp_GetLongPathNameW
0x1800120a8  test    eax, eax
0x1800120aa  jz      short loc_180012104
0x1800120ac  mov     rdx, rsi; SourceString
0x1800120af  mov     rcx, r13; DestinationString
0x1800120b2  call    cs:__imp_RtlCreateUnicodeString
0x1800120b8  mov     ebx, 0C0000017h
0x1800120bd  test    al, al
0x1800120bf  cmovz   r14d, ebx
0x1800120c3  mov     ebx, r14d
0x1800120c6  mov     rcx, gs:60h
0x1800120cf  mov     r8, rsi; P
0x1800120d2  xor     edx, edx; Flags
0x1800120d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800120d8  call    cs:__imp_RtlFreeHeap
0x1800120de  test    rdi, rdi
0x1800120e1  jz      loc_180011F7E
0x1800120e7  mov     rcx, gs:60h
0x1800120f0  mov     r8, rdi; P
0x1800120f3  xor     edx, edx; Flags
0x1800120f5  mov     rcx, [rcx+30h]; HeapHandle
0x1800120f9  call    cs:__imp_RtlFreeHeap
0x1800120ff  jmp     loc_180011F7E
0x180012104  mov     r8, r13; DestinationString
0x180012107  lea     rdx, [rsp+290h+DestinationString]; SourceString
0x18001210c  mov     ecx, 3; Flags
0x180012111  call    cs:__imp_RtlDuplicateUnicodeString
0x180012117  mov     ebx, eax
0x180012119  jmp     short loc_1800120C6
0x18001211b  sub     dx, 61h ; 'a'
0x18001211f  cmp     dx, 19h
0x180012123  jbe     loc_180012050
0x180012129  jmp     loc_180011FF9
0x18001212e  mov     rcx, gs:60h
0x180012137  mov     r8, rbx; Size
0x18001213a  xor     edx, edx; Flags
0x18001213c  mov     rcx, [rcx+30h]; HeapHandle
0x180012140  call    cs:__imp_RtlAllocateHeap
0x180012146  mov     rdi, rax
0x180012149  test    rax, rax
0x18001214c  jz      short loc_18001218E
0x18001214e  mov     rcx, [rsp+290h+DestinationString.Buffer]; FileName
0x180012153  xor     r9d, r9d; ShortName
0x180012156  mov     r8, rax; Buffer
0x180012159  mov     edx, ebx; Size
0x18001215b  call    cs:__imp_RtlGetFullPathName_U
0x180012161  lea     ecx, [rax-1]
0x180012164  cmp     ecx, 206h
0x18001216a  ja      short loc_1800121A2
0x18001216c  mov     [rsp+290h+DestinationString.Buffer], rdi
0x180012171  mov     [rsp+290h+DestinationString.Length], ax
0x180012176  mov     [rsp+290h+DestinationString.MaximumLength], bx
0x18001217b  jmp     loc_18001206D
0x180012180  test    rdi, rdi
0x180012183  jnz     loc_180011FC4
0x180012189  jmp     loc_180011F7E
0x18001218e  mov     ebx, 0C0000017h
0x180012193  jmp     loc_180011F7E
0x180012198  mov     ebx, 0C0000017h
0x18001219d  jmp     loc_1800120DE
0x1800121a2  mov     ebx, 0C0000001h
0x1800121a7  jmp     loc_1800120E7
```
