# FSMakeDirPathExist_StringSecurityDescriptor

- ea: `0x1800030c4`
- end: `0x1800033b8`
- name: `FSMakeDirPathExist_StringSecurityDescriptor`
- size: `756`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800033c0`
- `0x180003b58`
- `0x180007380`
- `0x18000c880`
- `0x18000dabc`

## callees

- `0x1800030c4`

## import_xrefs

- `msvcrt!iswalpha` at `0x180003238`
- `msvcrt!iswalpha` at `0x180003238`
- `KERNEL32!HeapAlloc` at `0x1800030f9`
- `KERNEL32!HeapAlloc` at `0x1800030f9`
- `KERNEL32!GetProcessHeap` at `0x1800030e8`
- `KERNEL32!GetProcessHeap` at `0x180003124`
- `KERNEL32!GetProcessHeap` at `0x18000316a`
- `KERNEL32!GetProcessHeap` at `0x180003189`
- `KERNEL32!GetProcessHeap` at `0x1800031bc`
- `KERNEL32!GetProcessHeap` at `0x18000320d`
- `KERNEL32!GetProcessHeap` at `0x18000337d`
- `KERNEL32!GetProcessHeap` at `0x18000339d`
- `KERNEL32!GetProcessHeap` at `0x1800030e8`
- `KERNEL32!GetProcessHeap` at `0x180003124`
- `KERNEL32!GetProcessHeap` at `0x18000316a`
- `KERNEL32!GetProcessHeap` at `0x180003189`
- `KERNEL32!GetProcessHeap` at `0x1800031bc`
- `KERNEL32!GetProcessHeap` at `0x18000320d`
- `KERNEL32!GetProcessHeap` at `0x18000337d`
- `KERNEL32!GetProcessHeap` at `0x18000339d`
- `KERNEL32!SetLastError` at `0x18000313d`
- `KERNEL32!SetLastError` at `0x18000313d`
- `KERNEL32!HeapFree` at `0x180003132`
- `KERNEL32!HeapFree` at `0x1800031ca`
- `KERNEL32!HeapFree` at `0x18000321b`
- `KERNEL32!HeapFree` at `0x1800033ab`
- `KERNEL32!HeapFree` at `0x180003132`
- `KERNEL32!HeapFree` at `0x1800031ca`
- `KERNEL32!HeapFree` at `0x18000321b`
- `KERNEL32!HeapFree` at `0x1800033ab`
- `KERNEL32!GetFullPathNameW` at `0x180003118`
- `KERNEL32!GetFullPathNameW` at `0x1800031a0`
- `KERNEL32!GetFullPathNameW` at `0x180003118`
- `KERNEL32!GetFullPathNameW` at `0x1800031a0`
- `KERNEL32!HeapReAlloc` at `0x18000317b`
- `KERNEL32!HeapReAlloc` at `0x18000317b`
- `KERNEL32!GetFileAttributesW` at `0x1800031ad`
- `KERNEL32!GetFileAttributesW` at `0x1800032d5`
- `KERNEL32!GetFileAttributesW` at `0x1800031ad`
- `KERNEL32!GetFileAttributesW` at `0x1800032d5`
- `KERNEL32!CreateDirectoryW` at `0x180003317`
- `KERNEL32!CreateDirectoryW` at `0x180003358`
- `KERNEL32!CreateDirectoryW` at `0x180003317`
- `KERNEL32!CreateDirectoryW` at `0x180003358`
- `KERNEL32!GetLastError` at `0x180003395`
- `KERNEL32!GetLastError` at `0x180003395`
- `KERNEL32!LocalFree` at `0x180003364`
- `KERNEL32!LocalFree` at `0x18000338f`
- `KERNEL32!LocalFree` at `0x180003364`
- `KERNEL32!LocalFree` at `0x18000338f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003333`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003333`

## pseudocode

```c
__int64 __fastcall FSMakeDirPathExist_StringSecurityDescriptor(LPCWSTR lpFileName, LPCWSTR StringSecurityDescriptor)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  DWORD FullPathNameW; // eax
  __int64 v8; // rsi
  HANDLE v9; // rax
  WCHAR *v10; // r8
  DWORD v11; // ecx
  WCHAR *v13; // r14
  HANDLE v14; // rax
  WCHAR *v15; // rax
  DWORD FileAttributesW; // eax
  HANDLE v17; // rax
  WCHAR *v18; // r8
  WCHAR *v19; // rsi
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  HANDLE v22; // rax
  unsigned __int64 v23; // rbx
  _WORD *v24; // rcx
  WCHAR v25; // ax
  WCHAR *i; // rcx
  unsigned __int64 v27; // r14
  int v28; // r15d
  WCHAR *v29; // rdi
  unsigned __int64 v30; // r12
  DWORD v31; // eax
  WCHAR *v32; // rbx
  BOOL DirectoryW; // edi
  DWORD LastError; // ebx
  HANDLE v35; // rax
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+50h] BYREF
  LPWSTR FilePart; // [rsp+98h] [rbp+58h] BYREF

  FilePart = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_5;
  FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, v5, &FilePart);
  v8 = FullPathNameW;
  if ( !FullPathNameW )
  {
    v9 = GetProcessHeap();
    v10 = v6;
LABEL_4:
    HeapFree(v9, 0, v10);
LABEL_5:
    v11 = 87;
    goto LABEL_6;
  }
  if ( FullPathNameW > 0x104 )
  {
    v13 = v6;
    v14 = GetProcessHeap();
    v15 = (WCHAR *)HeapReAlloc(v14, 0, v6, 2 * v8);
    v6 = v15;
    if ( !v15 || !GetFullPathNameW(lpFileName, v8, v15, &FilePart) )
    {
      v9 = GetProcessHeap();
      v10 = v13;
      goto LABEL_4;
    }
  }
  FileAttributesW = GetFileAttributesW(v6);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
    v17 = GetProcessHeap();
    v18 = v6;
LABEL_14:
    HeapFree(v17, 0, v18);
    return 1;
  }
  v19 = v6;
  v20 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v20;
  }
  while ( v20 );
  v21 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
  if ( !v20 || (v23 = 3, v21 < 3) )
  {
LABEL_19:
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v19);
    v11 = 13;
    goto LABEL_6;
  }
  if ( !iswalpha(*v19) || v19[1] != 58 || v19[2] != 92 )
  {
    if ( *v19 == 92 && v19[1] == 92 )
    {
      v24 = v19 + 2;
      v25 = v19[2];
      if ( v25 )
      {
        v23 = 2;
        while ( 1 )
        {
          ++v23;
          if ( v25 == 92 )
            break;
          v25 = *++v24;
          if ( !*v24 )
            goto LABEL_19;
        }
        for ( i = &v19[v23]; *i; ++i )
        {
          ++v23;
          if ( *i == 92 )
            goto LABEL_36;
        }
      }
    }
    goto LABEL_19;
  }
LABEL_36:
  v27 = v21 - 1;
  v28 = 0;
  v29 = &v19[v27];
  do
  {
    while ( *v29 != 92 )
    {
      --v29;
      --v27;
    }
    v30 = v23;
    if ( v27 > v23 )
      v30 = v27 + 1;
    ++v28;
    *v29 = 0;
    if ( v30 <= v23 )
      break;
    v31 = GetFileAttributesW(v19);
  }
  while ( v31 == -1 || (v31 & 0x10) == 0 );
  if ( !v28 )
    goto LABEL_19;
  v32 = &v19[v30 - 1];
  while ( 1 )
  {
    while ( *v32 )
      ++v32;
    *v32 = 92;
    if ( !StringSecurityDescriptor )
    {
      DirectoryW = CreateDirectoryW(v19, 0);
      goto LABEL_52;
    }
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      break;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    DirectoryW = CreateDirectoryW(v19, &SecurityAttributes);
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
LABEL_52:
    if ( !DirectoryW )
      goto LABEL_56;
    if ( !--v28 )
    {
      v17 = GetProcessHeap();
      v18 = v19;
      goto LABEL_14;
    }
  }
  LocalFree(SecurityDescriptor);
LABEL_56:
  LastError = GetLastError();
  v35 = GetProcessHeap();
  HeapFree(v35, 0, v19);
  v11 = LastError;
LABEL_6:
  SetLastError(v11);
  return 0;
}

```

## disassembly

```asm
0x1800030c4  mov     [rsp-38h+arg_0], rbx
0x1800030c9  push    rbp
0x1800030ca  push    rsi
0x1800030cb  push    rdi
0x1800030cc  push    r12
0x1800030ce  push    r13
0x1800030d0  push    r14
0x1800030d2  push    r15
0x1800030d4  mov     rbp, rsp
0x1800030d7  sub     rsp, 40h
0x1800030db  xor     r12d, r12d
0x1800030de  mov     r13, rdx
0x1800030e1  mov     [rbp+FilePart], r12
0x1800030e5  mov     r15, rcx
0x1800030e8  call    cs:__imp_GetProcessHeap
0x1800030ee  xor     edx, edx; dwFlags
0x1800030f0  mov     r8d, 208h; dwBytes
0x1800030f6  mov     rcx, rax; hHeap
0x1800030f9  call    cs:__imp_HeapAlloc
0x1800030ff  mov     rdi, rax
0x180003102  test    rax, rax
0x180003105  jz      short loc_180003138
0x180003107  mov     ebx, 104h
0x18000310c  lea     r9, [rbp+FilePart]; lpFilePart
0x180003110  mov     edx, ebx; nBufferLength
0x180003112  mov     r8, rax; lpBuffer
0x180003115  mov     rcx, r15; lpFileName
0x180003118  call    cs:__imp_GetFullPathNameW
0x18000311e  mov     esi, eax
0x180003120  test    eax, eax
0x180003122  jnz     short loc_18000315D
0x180003124  call    cs:__imp_GetProcessHeap
0x18000312a  mov     r8, rdi; lpMem
0x18000312d  mov     rcx, rax; hHeap
0x180003130  xor     edx, edx; dwFlags
0x180003132  call    cs:__imp_HeapFree
0x180003138  mov     ecx, 57h ; 'W'; dwErrCode
0x18000313d  call    cs:__imp_SetLastError
0x180003143  xor     eax, eax
0x180003145  mov     rbx, [rsp+40h+arg_0]
0x18000314d  add     rsp, 40h
0x180003151  pop     r15
0x180003153  pop     r14
0x180003155  pop     r13
0x180003157  pop     r12
0x180003159  pop     rdi
0x18000315a  pop     rsi
0x18000315b  pop     rbp
0x18000315c  retn
0x18000315d  cmp     esi, ebx
0x18000315f  jbe     short loc_1800031AA
0x180003161  mov     rbx, rsi
0x180003164  mov     r14, rdi
0x180003167  add     rbx, rbx
0x18000316a  call    cs:__imp_GetProcessHeap
0x180003170  mov     r9, rbx; dwBytes
0x180003173  mov     r8, rdi; lpMem
0x180003176  mov     rcx, rax; hHeap
0x180003179  xor     edx, edx; dwFlags
0x18000317b  call    cs:__imp_HeapReAlloc
0x180003181  mov     rdi, rax
0x180003184  test    rax, rax
0x180003187  jnz     short loc_180003194
0x180003189  call    cs:__imp_GetProcessHeap
0x18000318f  mov     r8, r14
0x180003192  jmp     short loc_18000312D
0x180003194  lea     r9, [rbp+FilePart]; lpFilePart
0x180003198  mov     r8, rax; lpBuffer
0x18000319b  mov     edx, esi; nBufferLength
0x18000319d  mov     rcx, r15; lpFileName
0x1800031a0  call    cs:__imp_GetFullPathNameW
0x1800031a6  test    eax, eax
0x1800031a8  jz      short loc_180003189
0x1800031aa  mov     rcx, rdi; lpFileName
0x1800031ad  call    cs:__imp_GetFileAttributesW
0x1800031b3  cmp     eax, 0FFFFFFFFh
0x1800031b6  jz      short loc_1800031DA
0x1800031b8  test    al, 10h
0x1800031ba  jz      short loc_1800031DA
0x1800031bc  call    cs:__imp_GetProcessHeap
0x1800031c2  mov     r8, rdi; lpMem
0x1800031c5  mov     rcx, rax; hHeap
0x1800031c8  xor     edx, edx; dwFlags
0x1800031ca  call    cs:__imp_HeapFree
0x1800031d0  mov     eax, 1
0x1800031d5  jmp     loc_180003145
0x1800031da  mov     edx, 7FFFFFFFh
0x1800031df  mov     rsi, rdi
0x1800031e2  mov     ecx, edx
0x1800031e4  mov     r15d, 2
0x1800031ea  cmp     [rdi], r12w
0x1800031ee  jz      short loc_1800031F9
0x1800031f0  add     rdi, r15
0x1800031f3  sub     rcx, 1
0x1800031f7  jnz     short loc_1800031EA
0x1800031f9  sub     rdx, rcx
0x1800031fc  mov     rax, rcx
0x1800031ff  neg     rax
0x180003202  sbb     r14, r14
0x180003205  and     r14, rdx
0x180003208  test    rcx, rcx
0x18000320b  jnz     short loc_18000322B
0x18000320d  call    cs:__imp_GetProcessHeap
0x180003213  mov     r8, rsi; lpMem
0x180003216  xor     edx, edx; dwFlags
0x180003218  mov     rcx, rax; hHeap
0x18000321b  call    cs:__imp_HeapFree
0x180003221  mov     ecx, 0Dh
0x180003226  jmp     loc_18000313D
0x18000322b  mov     ebx, 3
0x180003230  cmp     r14, rbx
0x180003233  jb      short loc_18000320D
0x180003235  movzx   ecx, word ptr [rsi]; C
0x180003238  call    cs:__imp_iswalpha
0x18000323e  lea     edx, [rbx+59h]
0x180003241  test    eax, eax
0x180003243  jz      short loc_180003252
0x180003245  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18000324a  jnz     short loc_180003252
0x18000324c  cmp     [rsi+4], dx
0x180003250  jz      short loc_18000329F
0x180003252  cmp     [rsi], dx
0x180003255  jnz     short loc_18000320D
0x180003257  cmp     [rsi+2], dx
0x18000325b  jnz     short loc_18000320D
0x18000325d  lea     rcx, [rsi+4]
0x180003261  movzx   eax, word ptr [rcx]
0x180003264  test    ax, ax
0x180003267  jz      short loc_18000320D
0x180003269  mov     rbx, r15
0x18000326c  inc     rbx
0x18000326f  cmp     ax, dx
0x180003272  jz      short loc_180003281
0x180003274  add     rcx, r15
0x180003277  movzx   eax, word ptr [rcx]
0x18000327a  test    ax, ax
0x18000327d  jnz     short loc_18000326C
0x18000327f  jmp     short loc_18000320D
0x180003281  lea     rcx, [rsi+rbx*2]
0x180003285  jmp     short loc_180003292
0x180003287  inc     rbx
0x18000328a  cmp     ax, dx
0x18000328d  jz      short loc_18000329F
0x18000328f  add     rcx, r15
0x180003292  movzx   eax, word ptr [rcx]
0x180003295  test    ax, ax
0x180003298  jnz     short loc_180003287
0x18000329a  jmp     loc_18000320D
0x18000329f  dec     r14
0x1800032a2  mov     r15d, r12d
0x1800032a5  lea     rdi, [rsi+r14*2]
0x1800032a9  jmp     short loc_1800032B2
0x1800032ab  sub     rdi, 2
0x1800032af  dec     r14
0x1800032b2  cmp     [rdi], dx
0x1800032b5  jnz     short loc_1800032AB
0x1800032b7  cmp     r14, rbx
0x1800032ba  lea     rax, [r14+1]
0x1800032be  mov     r12, rbx
0x1800032c1  cmova   r12, rax
0x1800032c5  xor     eax, eax
0x1800032c7  inc     r15d
0x1800032ca  mov     [rdi], ax
0x1800032cd  cmp     r12, rbx
0x1800032d0  jbe     short loc_1800032E9
0x1800032d2  mov     rcx, rsi; lpFileName
0x1800032d5  call    cs:__imp_GetFileAttributesW
0x1800032db  mov     edx, 5Ch ; '\'
0x1800032e0  cmp     eax, 0FFFFFFFFh
0x1800032e3  jz      short loc_1800032B2
0x1800032e5  test    al, 10h
0x1800032e7  jz      short loc_1800032B2
0x1800032e9  xor     r14d, r14d
0x1800032ec  test    r15d, r15d
0x1800032ef  jz      loc_18000320D
0x1800032f5  lea     rbx, [r12-1]
0x1800032fa  lea     rbx, [rsi+rbx*2]
0x1800032fe  jmp     short loc_180003304
0x180003300  add     rbx, 2
0x180003304  cmp     [rbx], r14w
0x180003308  jnz     short loc_180003300
0x18000330a  mov     [rbx], dx
0x18000330d  test    r13, r13
0x180003310  jnz     short loc_180003321
0x180003312  xor     edx, edx; lpSecurityAttributes
0x180003314  mov     rcx, rsi; lpPathName
0x180003317  call    cs:__imp_CreateDirectoryW
0x18000331d  mov     edi, eax
0x18000331f  jmp     short loc_18000336E
0x180003321  xor     r9d, r9d; SecurityDescriptorSize
0x180003324  mov     [rbp+SecurityDescriptor], r14
0x180003328  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000332c  mov     rcx, r13; StringSecurityDescriptor
0x18000332f  lea     edx, [r9+1]; StringSDRevision
0x180003333  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003339  test    eax, eax
0x18000333b  jz      short loc_18000338B
0x18000333d  mov     rax, [rbp+SecurityDescriptor]
0x180003341  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180003345  mov     rcx, rsi; lpPathName
0x180003348  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18000334c  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x180003354  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], r14
0x180003358  call    cs:__imp_CreateDirectoryW
0x18000335e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180003362  mov     edi, eax
0x180003364  call    cs:__imp_LocalFree
0x18000336a  mov     [rbp+SecurityDescriptor], r14
0x18000336e  test    edi, edi
0x180003370  jz      short loc_180003395
0x180003372  mov     edx, 5Ch ; '\'
0x180003377  add     r15d, 0FFFFFFFFh
0x18000337b  jnz     short loc_180003304
0x18000337d  call    cs:__imp_GetProcessHeap
0x180003383  mov     r8, rsi
0x180003386  jmp     loc_1800031C5
0x18000338b  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000338f  call    cs:__imp_LocalFree
0x180003395  call    cs:__imp_GetLastError
0x18000339b  mov     ebx, eax
0x18000339d  call    cs:__imp_GetProcessHeap
0x1800033a3  mov     r8, rsi; lpMem
0x1800033a6  xor     edx, edx; dwFlags
0x1800033a8  mov     rcx, rax; hHeap
0x1800033ab  call    cs:__imp_HeapFree
0x1800033b1  mov     ecx, ebx
0x1800033b3  jmp     loc_18000313D
```
