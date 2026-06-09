# CxFullPath(char *,char const *)

- ea: `0x182dcf2c0`
- end: `0x182dcf47d`
- name: `?CxFullPath@@YA_NPEADPEBD@Z`
- size: `445`
- prototype: `bool __fastcall(LPSTR lpBuffer, LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x182dd0450`

## callees

- `0x182dcf2c0`
- `0x182dcf5d0`
- `0x183052ed0`
- `0x183053010`
- `0x183055940`
- `0x1832c35f0`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!FindClose` at `0x182dcf403`
- `KERNEL32!FindClose` at `0x182dcf403`
- `KERNEL32!FindFirstFileA` at `0x182dcf3f5`
- `KERNEL32!FindFirstFileA` at `0x182dcf3f5`
- `KERNEL32!GetFullPathNameA` at `0x182dcf308`
- `KERNEL32!GetFullPathNameA` at `0x182dcf308`
- `KERNEL32!GetVolumeInformationA` at `0x182dcf3ce`
- `KERNEL32!GetVolumeInformationA` at `0x182dcf3ce`
- `SHLWAPI!PathIsUNCA` at `0x182dcf38d`
- `SHLWAPI!PathIsUNCA` at `0x182dcf38d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CxFullPath(LPSTR lpBuffer, LPCSTR lpFileName)
{
  char *v3; // rdi
  __int64 v4; // rbx
  const CHAR *v5; // rsi
  char v6; // al
  char *v7; // rax
  const CHAR *CharPointer; // rax
  const CHAR *v10; // rax
  HANDLE FirstFileA; // rax
  _BYTE *v12; // rcx
  CHAR *v13; // rdx
  char v14; // al
  _BYTE *v15; // rax
  __int64 v16; // [rsp+48h] [rbp-180h] BYREF
  DWORD FileSystemFlags; // [rsp+50h] [rbp-178h] BYREF
  DWORD MaximumComponentLength[3]; // [rsp+54h] [rbp-174h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+60h] [rbp-168h] BYREF

  v3 = lpBuffer;
  v4 = 260;
  if ( GetFullPathNameA(lpFileName, 0x104u, lpBuffer, 0) )
  {
    if ( !IsAppContainerEnabled() )
    {
      v16 = 0;
      CxString::CxString((CxString *)&v16);
      CxGetRoot(v3, (struct CxString *)&v16);
      CharPointer = CxString::GetCharPointer((CxString *)&v16);
      if ( !PathIsUNCA(CharPointer) )
      {
        v10 = CxString::GetCharPointer((CxString *)&v16);
        if ( !GetVolumeInformationA(v10, 0, 0, 0, MaximumComponentLength, &FileSystemFlags, 0, 0) )
        {
          CxString::~CxString((CxString *)&v16);
          return 0;
        }
        if ( (FileSystemFlags & 4) == 0 )
        {
          FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
          if ( FirstFileA )
          {
            FindClose(FirstFileA);
            v12 = (_BYTE *)MEMORY[0];
            v13 = &FindFileData.cFileName[-MEMORY[0]];
            do
            {
              if ( v4 == -2147483386 )
                break;
              v14 = v12[(_QWORD)v13];
              if ( !v14 )
                break;
              *v12++ = v14;
              --v4;
            }
            while ( v4 );
            v15 = v12 - 1;
            if ( v4 )
              v15 = v12;
            *v15 = 0;
          }
        }
      }
      CxString::~CxString((CxString *)&v16);
    }
    return 1;
  }
  else
  {
    v5 = (const CHAR *)(lpFileName - v3);
    do
    {
      if ( v4 == -2147483386 )
        break;
      v6 = v3[(_QWORD)v5];
      if ( !v6 )
        break;
      *v3++ = v6;
      --v4;
    }
    while ( v4 );
    v7 = v3 - 1;
    if ( v4 )
      v7 = v3;
    *v7 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x182dcf2c0  push    rsi
0x182dcf2c2  push    rdi
0x182dcf2c3  push    r14
0x182dcf2c5  sub     rsp, 1B0h
0x182dcf2cc  mov     [rsp+1C8h+var_188], 0FFFFFFFFFFFFFFFEh
0x182dcf2d5  mov     [rsp+1C8h+arg_10], rbx
0x182dcf2dd  mov     rax, cs:__security_cookie
0x182dcf2e4  xor     rax, rsp
0x182dcf2e7  mov     [rsp+1C8h+var_28], rax
0x182dcf2ef  mov     rsi, rdx
0x182dcf2f2  mov     rdi, rcx
0x182dcf2f5  xor     r14d, r14d
0x182dcf2f8  xor     r9d, r9d; lpFilePart
0x182dcf2fb  mov     r8, rcx; lpBuffer
0x182dcf2fe  mov     ebx, 104h
0x182dcf303  mov     edx, ebx; nBufferLength
0x182dcf305  mov     rcx, rsi; lpFileName
0x182dcf308  call    cs:__imp_GetFullPathNameA
0x182dcf30e  test    eax, eax
0x182dcf310  jnz     short loc_182DCF354
0x182dcf312  sub     rsi, rdi
0x182dcf315  nop     word ptr [rax+rax+00000000h]
0x182dcf320  lea     rax, [rbx+7FFFFEFAh]
0x182dcf327  test    rax, rax
0x182dcf32a  jz      short loc_182DCF33F
0x182dcf32c  movzx   eax, byte ptr [rsi+rdi]
0x182dcf330  test    al, al
0x182dcf332  jz      short loc_182DCF33F
0x182dcf334  mov     [rdi], al
0x182dcf336  inc     rdi
0x182dcf339  sub     rbx, 1
0x182dcf33d  jnz     short loc_182DCF320
0x182dcf33f  lea     rax, [rdi-1]
0x182dcf343  test    rbx, rbx
0x182dcf346  cmovnz  rax, rdi
0x182dcf34a  mov     [rax], r14b
0x182dcf34d  xor     al, al
0x182dcf34f  jmp     loc_182DCF459
0x182dcf354  call    ?IsAppContainerEnabled@@YA_NXZ; IsAppContainerEnabled(void)
0x182dcf359  test    al, al
0x182dcf35b  jnz     loc_182DCF457
0x182dcf361  xor     eax, eax
0x182dcf363  mov     [rsp+1C8h+var_180], rax
0x182dcf368  lea     rcx, [rsp+1C8h+var_180]; this
0x182dcf36d  call    ??0CxString@@QEAA@XZ; CxString::CxString(void)
0x182dcf372  nop
0x182dcf373  lea     rdx, [rsp+1C8h+var_180]; struct CxString *
0x182dcf378  mov     rcx, rdi; char *
0x182dcf37b  call    ?CxGetRoot@@YAXPEBDAEAVCxString@@@Z; CxGetRoot(char const *,CxString &)
0x182dcf380  lea     rcx, [rsp+1C8h+var_180]; this
0x182dcf385  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x182dcf38a  mov     rcx, rax; pszPath
0x182dcf38d  call    cs:__imp_PathIsUNCA
0x182dcf393  test    eax, eax
0x182dcf395  jnz     loc_182DCF44D
0x182dcf39b  lea     rcx, [rsp+1C8h+var_180]; this
0x182dcf3a0  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x182dcf3a5  mov     rcx, rax; lpRootPathName
0x182dcf3a8  mov     [rsp+1C8h+nFileSystemNameSize], r14d; nFileSystemNameSize
0x182dcf3ad  mov     [rsp+1C8h+lpFileSystemNameBuffer], r14; lpFileSystemNameBuffer
0x182dcf3b2  lea     rax, [rsp+1C8h+FileSystemFlags]
0x182dcf3b7  mov     [rsp+1C8h+lpFileSystemFlags], rax; lpFileSystemFlags
0x182dcf3bc  lea     rax, [rsp+1C8h+MaximumComponentLength]
0x182dcf3c1  mov     [rsp+1C8h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x182dcf3c6  xor     r9d, r9d; lpVolumeSerialNumber
0x182dcf3c9  xor     r8d, r8d; nVolumeNameSize
0x182dcf3cc  xor     edx, edx; lpVolumeNameBuffer
0x182dcf3ce  call    cs:__imp_GetVolumeInformationA
0x182dcf3d4  test    eax, eax
0x182dcf3d6  jnz     short loc_182DCF3E6
0x182dcf3d8  lea     rcx, [rsp+1C8h+var_180]; this
0x182dcf3dd  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x182dcf3e2  xor     al, al
0x182dcf3e4  jmp     short loc_182DCF459
0x182dcf3e6  test    byte ptr [rsp+1C8h+FileSystemFlags], 4
0x182dcf3eb  jnz     short loc_182DCF44D
0x182dcf3ed  lea     rdx, [rsp+1C8h+FindFileData]; lpFindFileData
0x182dcf3f2  mov     rcx, rsi; lpFileName
0x182dcf3f5  call    cs:__imp_FindFirstFileA
0x182dcf3fb  test    rax, rax
0x182dcf3fe  jz      short loc_182DCF44D
0x182dcf400  mov     rcx, rax; hFindFile
0x182dcf403  call    cs:__imp_FindClose
0x182dcf409  mov     rcx, [r14]
0x182dcf40c  lea     rdx, [rsp+1C8h+FindFileData.cFileName]
0x182dcf414  sub     rdx, rcx
0x182dcf417  nop     word ptr [rax+rax+00000000h]
0x182dcf420  lea     rax, [rbx+7FFFFEFAh]
0x182dcf427  test    rax, rax
0x182dcf42a  jz      short loc_182DCF43F
0x182dcf42c  movzx   eax, byte ptr [rdx+rcx]
0x182dcf430  test    al, al
0x182dcf432  jz      short loc_182DCF43F
0x182dcf434  mov     [rcx], al
0x182dcf436  inc     rcx
0x182dcf439  sub     rbx, 1
0x182dcf43d  jnz     short loc_182DCF420
0x182dcf43f  lea     rax, [rcx-1]
0x182dcf443  test    rbx, rbx
0x182dcf446  cmovnz  rax, rcx
0x182dcf44a  mov     byte ptr [rax], 0
0x182dcf44d  lea     rcx, [rsp+1C8h+var_180]; this
0x182dcf452  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x182dcf457  mov     al, 1
0x182dcf459  mov     rcx, [rsp+1C8h+var_28]
0x182dcf461  xor     rcx, rsp; StackCookie
0x182dcf464  call    __security_check_cookie
0x182dcf469  mov     rbx, [rsp+1C8h+arg_10]
0x182dcf471  add     rsp, 1B0h
0x182dcf478  pop     r14
0x182dcf47a  pop     rdi
0x182dcf47b  pop     rsi
0x182dcf47c  retn
```
