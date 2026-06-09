# AhcLogVerboseFile

- ea: `0x140028c98`
- end: `0x140028f93`
- name: `AhcLogVerboseFile`
- size: `763`
- prototype: `char __fastcall(int, const char *, __int64, const char *, va_list argList)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400531c0`

## callees

- `0x140001ec4`
- `0x140003af4`
- `0x140003b50`
- `0x140004758`
- `0x1400079f0`
- `0x140007e40`
- `0x140028c98`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140028d1f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028d1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028d5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028d5f`
- `ntoskrnl!ZwClose` at `0x140028f53`
- `ntoskrnl!ZwClose` at `0x140028f53`
- `ntoskrnl!ZwCreateFile` at `0x140028dda`
- `ntoskrnl!ZwCreateFile` at `0x140028dda`
- `ntoskrnl!ZwWriteFile` at `0x140028f3d`
- `ntoskrnl!ZwWriteFile` at `0x140028f3d`

## string_xrefs

- `0x140028d33`: `\SystemRoot\Temp\AslLog_ahcache.txt`

## pseudocode

```c
char __fastcall AhcLogVerboseFile(int a1, const char *a2, __int64 a3, const char *a4, va_list argList)
{
  __int64 v5; // r12
  char *v9; // rax
  __int64 v10; // rdi
  size_t *v11; // r8
  size_t v12; // rdx
  char *v13; // rcx
  const char *v14; // r8
  __int64 v15; // rdx
  char *v16; // rcx
  size_t v17; // rbx
  ULONG FileAttributes[2]; // [rsp+28h] [rbp-D8h]
  size_t pcchLength; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  char psz[528]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v5 = a1;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  memset(pszDest, 0, 0x208u);
  memset(psz, 0, 0x208u);
  LOBYTE(v9) = KeGetCurrentIrql();
  if ( !(_BYTE)v9 )
  {
    LODWORD(v9) = RtlStringCchPrintfW(pszDest, 0x104u, L"\\SystemRoot\\Temp\\AslLog_ahcache.txt");
    if ( (int)v9 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pszDest);
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      LODWORD(v9) = ZwCreateFile(
                      &FileHandle,
                      0x100004u,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      1u,
                      byte_14001E2C1 == 0 ? 3 : 0,
                      0x60u,
                      0,
                      0);
      if ( (int)v9 >= 0 )
      {
        v10 = -1;
        if ( a3 == -1 )
          LODWORD(a3) = 0;
        FileAttributes[0] = a3;
        if ( !a2 )
          a2 = byte_14000DA20;
        LODWORD(v9) = RtlStringCchPrintfA(
                        psz,
                        0x207u,
                        "%s,%s,%d,",
                        (&off_14000A858)[2 * v5],
                        a2,
                        *(_QWORD *)FileAttributes);
        if ( (int)v9 >= 0 )
        {
          v9 = psz;
          do
            ++v10;
          while ( psz[v10] );
          v12 = 519 - v10;
          if ( v10 != 519 )
          {
            v13 = &psz[v10];
            if ( v12 <= 0x7FFFFFFF )
            {
              LODWORD(v9) = RtlStringVPrintfWorkerA(v13, v12, v11, a4, argList);
              if ( (int)v9 >= 0 )
              {
                pcchLength = 0;
                LODWORD(v9) = RtlStringLengthWorkerA(psz, 0x207u, &pcchLength);
                if ( (int)v9 >= 0 )
                {
                  v14 = "\r\n";
                  v15 = 2147483646;
                  v16 = &psz[pcchLength];
                  v17 = 519 - pcchLength;
                  if ( 519 != pcchLength )
                  {
                    do
                    {
                      if ( !v15 )
                        break;
                      if ( !*v14 )
                        break;
                      *v16++ = *v14++;
                      --v15;
                      --v17;
                    }
                    while ( v17 );
                  }
                  v9 = v16 - 1;
                  if ( v17 )
                    v9 = v16;
                  *v9 = 0;
                  if ( v17 )
                  {
                    pcchLength = 0;
                    LODWORD(v9) = RtlStringLengthWorkerA(psz, 0x208u, &pcchLength);
                    if ( (int)v9 >= 0 )
                      LOBYTE(v9) = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, psz, pcchLength, 0, 0);
                  }
                }
              }
            }
            else
            {
              *v13 = 0;
            }
          }
        }
      }
    }
  }
  if ( FileHandle )
    LOBYTE(v9) = ZwClose(FileHandle);
  if ( byte_14001E2C1 )
    byte_14001E2C1 = 0;
  return (char)v9;
}

```

## disassembly

```asm
0x140028c98  push    rbp
0x140028c9a  push    rbx
0x140028c9b  push    rsi
0x140028c9c  push    rdi
0x140028c9d  push    r12
0x140028c9f  push    r13
0x140028ca1  push    r14
0x140028ca3  push    r15
0x140028ca5  lea     rbp, [rsp-3F8h]
0x140028cad  sub     rsp, 4F8h
0x140028cb4  mov     rax, cs:__security_cookie
0x140028cbb  xor     rax, rsp
0x140028cbe  mov     [rbp+430h+var_50], rax
0x140028cc5  mov     r15, [rbp+430h+argList]
0x140028ccc  xorps   xmm1, xmm1
0x140028ccf  xorps   xmm0, xmm0
0x140028cd2  movsxd  r12, ecx
0x140028cd5  mov     rsi, r8
0x140028cd8  lea     rcx, [rbp+430h+pszDest]; void *
0x140028cdf  mov     rbx, rdx
0x140028ce2  mov     edi, 208h
0x140028ce7  xor     r13d, r13d
0x140028cea  mov     r8d, edi; Size
0x140028ced  xor     edx, edx; Val
0x140028cef  mov     [rsp+530h+FileHandle], r13
0x140028cf4  mov     r14, r9
0x140028cf7  movups  xmmword ptr [rsp+530h+DestinationString.Length], xmm0
0x140028cfc  movups  xmmword ptr [rbp+430h+ObjectAttributes.Length], xmm1
0x140028d00  movups  xmmword ptr [rbp+430h+ObjectAttributes.ObjectName], xmm1
0x140028d04  movups  xmmword ptr [rbp+430h+ObjectAttributes.SecurityDescriptor], xmm1
0x140028d08  movups  xmmword ptr [rbp+430h+IoStatusBlock], xmm0
0x140028d0c  call    memset
0x140028d11  mov     r8d, edi; Size
0x140028d14  lea     rcx, [rbp+430h+psz]; void *
0x140028d18  xor     edx, edx; Val
0x140028d1a  call    memset
0x140028d1f  call    cs:__imp_KeGetCurrentIrql
0x140028d26  nop     dword ptr [rax+rax+00h]
0x140028d2b  test    al, al
0x140028d2d  jnz     loc_140028F49
0x140028d33  lea     r8, aSystemrootTemp; "\\SystemRoot\\Temp\\AslLog_ahcache.txt"
0x140028d3a  mov     edx, 104h; cchDest
0x140028d3f  lea     rcx, [rbp+430h+pszDest]; pszDest
0x140028d46  call    RtlStringCchPrintfW
0x140028d4b  test    eax, eax
0x140028d4d  js      loc_140028F49
0x140028d53  lea     rdx, [rbp+430h+pszDest]; SourceString
0x140028d5a  lea     rcx, [rsp+530h+DestinationString]; DestinationString
0x140028d5f  call    cs:__imp_RtlInitUnicodeString
0x140028d66  nop     dword ptr [rax+rax+00h]
0x140028d6b  mov     [rsp+530h+EaLength], r13d; EaLength
0x140028d70  lea     rax, [rsp+530h+DestinationString]
0x140028d75  mov     [rsp+530h+EaBuffer], r13; EaBuffer
0x140028d7a  lea     r9, [rbp+430h+IoStatusBlock]; IoStatusBlock
0x140028d7e  mov     [rsp+530h+CreateOptions], 60h ; '`'; CreateOptions
0x140028d86  lea     r8, [rbp+430h+ObjectAttributes]; ObjectAttributes
0x140028d8a  mov     [rbp+430h+ObjectAttributes.ObjectName], rax
0x140028d8e  xorps   xmm0, xmm0
0x140028d91  mov     al, cs:byte_14001E2C1
0x140028d97  mov     edx, 100004h; DesiredAccess
0x140028d9c  neg     al
0x140028d9e  mov     [rbp+430h+ObjectAttributes.Length], 30h ; '0'
0x140028da5  mov     [rbp+430h+ObjectAttributes.RootDirectory], r13
0x140028da9  sbb     ecx, ecx
0x140028dab  mov     [rbp+430h+ObjectAttributes.Attributes], 40h ; '@'
0x140028db2  not     ecx
0x140028db4  and     ecx, 3
0x140028db7  mov     [rsp+530h+CreateDisposition], ecx; CreateDisposition
0x140028dbb  lea     rcx, [rsp+530h+FileHandle]; FileHandle
0x140028dc0  mov     [rsp+530h+ShareAccess], 1; ShareAccess
0x140028dc8  mov     [rsp+530h+FileAttributes], 80h; FileAttributes
0x140028dd0  mov     [rsp+530h+AllocationSize], r13; AllocationSize
0x140028dd5  movdqu  xmmword ptr [rbp+430h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028dda  call    cs:__imp_ZwCreateFile
0x140028de1  nop     dword ptr [rax+rax+00h]
0x140028de6  test    eax, eax
0x140028de8  js      loc_140028F49
0x140028dee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140028df2  lea     rax, byte_14000DA20
0x140028df9  cmp     rsi, rdi
0x140028dfc  lea     r8, aSSD; "%s,%s,%d,"
0x140028e03  mov     r9, r12
0x140028e06  lea     rcx, [rbp+430h+psz]; pszDest
0x140028e0a  cmovz   esi, r13d
0x140028e0e  test    rbx, rbx
0x140028e11  mov     [rsp+530h+FileAttributes], esi
0x140028e15  cmovz   rbx, rax
0x140028e19  add     r9, r9
0x140028e1c  lea     rax, off_14000A858; "PRINT"
0x140028e23  mov     [rsp+530h+AllocationSize], rbx
0x140028e28  mov     ebx, 207h
0x140028e2d  mov     edx, ebx; cchDest
0x140028e2f  mov     r9, [rax+r9*8]
0x140028e33  call    RtlStringCchPrintfA
0x140028e38  test    eax, eax
0x140028e3a  js      loc_140028F49
0x140028e40  lea     rax, [rbp+430h+psz]
0x140028e44  inc     rdi
0x140028e47  cmp     [rax+rdi], r13b
0x140028e4b  jnz     short loc_140028E44
0x140028e4d  mov     rdx, rbx
0x140028e50  sub     rdx, rdi; cchDest
0x140028e53  jz      loc_140028F49
0x140028e59  lea     rcx, [rbp+430h+psz]
0x140028e5d  add     rcx, rdi; pszDest
0x140028e60  cmp     rdx, 7FFFFFFFh
0x140028e67  jbe     short loc_140028E71
0x140028e69  mov     [rcx], r13b
0x140028e6c  jmp     loc_140028F49
0x140028e71  mov     r9, r14; pszFormat
0x140028e74  mov     [rsp+530h+AllocationSize], r15; argList
0x140028e79  call    RtlStringVPrintfWorkerA
0x140028e7e  test    eax, eax
0x140028e80  js      loc_140028F49
0x140028e86  lea     r8, [rsp+530h+pcchLength]; pcchLength
0x140028e8b  mov     [rsp+530h+pcchLength], r13
0x140028e90  mov     rdx, rbx; cchMax
0x140028e93  lea     rcx, [rbp+430h+psz]; psz
0x140028e97  call    RtlStringLengthWorkerA
0x140028e9c  test    eax, eax
0x140028e9e  js      loc_140028F49
0x140028ea4  mov     rax, [rsp+530h+pcchLength]
0x140028ea9  lea     rcx, [rbp+430h+psz]
0x140028ead  lea     r8, asc_14000F224; "\r\n"
0x140028eb4  mov     edx, 7FFFFFFEh
0x140028eb9  lea     rcx, [rcx+rax]
0x140028ebd  sub     rbx, rax
0x140028ec0  jz      short loc_140028EDF
0x140028ec2  test    rdx, rdx
0x140028ec5  jz      short loc_140028EDF
0x140028ec7  mov     al, [r8]
0x140028eca  test    al, al
0x140028ecc  jz      short loc_140028EDF
0x140028ece  mov     [rcx], al
0x140028ed0  inc     r8
0x140028ed3  inc     rcx
0x140028ed6  dec     rdx
0x140028ed9  sub     rbx, 1
0x140028edd  jnz     short loc_140028EC2
0x140028edf  test    rbx, rbx
0x140028ee2  lea     rax, [rcx-1]
0x140028ee6  cmovnz  rax, rcx
0x140028eea  mov     [rax], r13b
0x140028eed  jz      short loc_140028F49
0x140028eef  lea     r8, [rsp+530h+pcchLength]; pcchLength
0x140028ef4  mov     [rsp+530h+pcchLength], r13
0x140028ef9  mov     edx, 208h; cchMax
0x140028efe  lea     rcx, [rbp+430h+psz]; psz
0x140028f02  call    RtlStringLengthWorkerA
0x140028f07  test    eax, eax
0x140028f09  js      short loc_140028F49
0x140028f0b  mov     rax, [rsp+530h+pcchLength]
0x140028f10  xor     r9d, r9d; ApcContext
0x140028f13  mov     rcx, [rsp+530h+FileHandle]; FileHandle
0x140028f18  xor     r8d, r8d; ApcRoutine
0x140028f1b  mov     qword ptr [rsp+530h+CreateOptions], r13; Key
0x140028f20  xor     edx, edx; Event
0x140028f22  mov     qword ptr [rsp+530h+CreateDisposition], r13; ByteOffset
0x140028f27  mov     [rsp+530h+ShareAccess], eax; Length
0x140028f2b  lea     rax, [rbp+430h+psz]
0x140028f2f  mov     qword ptr [rsp+530h+FileAttributes], rax; Buffer
0x140028f34  lea     rax, [rbp+430h+IoStatusBlock]
0x140028f38  mov     [rsp+530h+AllocationSize], rax; IoStatusBlock
0x140028f3d  call    cs:__imp_ZwWriteFile
0x140028f44  nop     dword ptr [rax+rax+00h]
0x140028f49  mov     rcx, [rsp+530h+FileHandle]; Handle
0x140028f4e  test    rcx, rcx
0x140028f51  jz      short loc_140028F5F
0x140028f53  call    cs:__imp_ZwClose
0x140028f5a  nop     dword ptr [rax+rax+00h]
0x140028f5f  cmp     cs:byte_14001E2C1, r13b
0x140028f66  jz      short loc_140028F6F
0x140028f68  mov     cs:byte_14001E2C1, r13b
0x140028f6f  mov     rcx, [rbp+430h+var_50]
0x140028f76  xor     rcx, rsp; StackCookie
0x140028f79  call    __security_check_cookie
0x140028f7e  add     rsp, 4F8h
0x140028f85  pop     r15
0x140028f87  pop     r14
0x140028f89  pop     r13
0x140028f8b  pop     r12
0x140028f8d  pop     rdi
0x140028f8e  pop     rsi
0x140028f8f  pop     rbx
0x140028f90  pop     rbp
0x140028f91  retn
```
