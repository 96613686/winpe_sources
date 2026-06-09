# OpenLongFile(char const *,_OFLONGSTRUCT *,uint)

- ea: `0x180019278`
- end: `0x1800194a8`
- name: `?OpenLongFile@@YAHPEBDPEAU_OFLONGSTRUCT@@I@Z`
- size: `560`
- prototype: `__int64 __fastcall(const char *, struct _OFLONGSTRUCT *, unsigned int)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180019ecc`
- `0x18001a1ac`
- `0x180026c1c`
- `0x18002a8f8`
- `0x18003b2ec`
- `0x180045ba0`
- `0x18009c1fc`

## callees

- `0x180019278`
- `0x18001ac78`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001946f`
- `KERNEL32!GetLastError` at `0x18001946f`
- `KERNEL32!SetLastError` at `0x1800192b7`
- `KERNEL32!SetLastError` at `0x1800192e5`
- `KERNEL32!SetLastError` at `0x180019430`
- `KERNEL32!SetLastError` at `0x1800192b7`
- `KERNEL32!SetLastError` at `0x1800192e5`
- `KERNEL32!SetLastError` at `0x180019430`
- `KERNEL32!DeleteFileA` at `0x1800193f0`
- `KERNEL32!DeleteFileA` at `0x1800193f0`
- `KERNEL32!CreateFileA` at `0x180019466`
- `KERNEL32!CreateFileA` at `0x180019466`
- `KERNEL32!GetFullPathNameA` at `0x1800192d6`
- `KERNEL32!GetFullPathNameA` at `0x18001941d`
- `KERNEL32!GetFullPathNameA` at `0x1800192d6`
- `KERNEL32!GetFullPathNameA` at `0x18001941d`
- `KERNEL32!FindFirstFileA` at `0x1800193a4`
- `KERNEL32!FindFirstFileA` at `0x1800193a4`
- `KERNEL32!SearchPathA` at `0x18001938a`
- `KERNEL32!SearchPathA` at `0x1800193e2`
- `KERNEL32!SearchPathA` at `0x18001938a`
- `KERNEL32!SearchPathA` at `0x1800193e2`

## pseudocode

```c
__int64 __fastcall OpenLongFile(const char *a1, CHAR *a2, int a3)
{
  unsigned int FileA; // ebx
  DWORD v7; // esi
  DWORD v8; // r13d
  int v9; // eax
  DWORD v10; // r15d
  DWORD v11; // eax
  DWORD v12; // r12d
  DWORD v13; // ecx
  DWORD FullPathNameA; // eax
  int LastError; // ecx
  __int64 result; // rax
  LPSTR FilePart; // [rsp+40h] [rbp-998h] BYREF
  LPCSTR lpFileName; // [rsp+48h] [rbp-990h]
  _WIN32_FIND_DATAA FindFileData; // [rsp+50h] [rbp-988h] BYREF
  CHAR FileName[2048]; // [rsp+190h] [rbp-848h] BYREF

  lpFileName = a1;
  SetLastError(0);
  if ( (a3 & 0x100) == 0 )
  {
    v7 = (a3 & 1) != 0 ? 0x40000000 : 0x80000000;
    if ( (a3 & 2) != 0 )
      v7 |= 0xC0000000;
    v8 = 3;
    v9 = a3 & 0x70;
    if ( (a3 & 0x70) != 0 )
    {
      switch ( v9 )
      {
        case 16:
          v10 = 0;
          goto LABEL_15;
        case 32:
          v10 = 1;
          goto LABEL_15;
        case 48:
          v10 = 2;
          goto LABEL_15;
      }
    }
    v10 = 3;
LABEL_15:
    if ( (a3 & 0x1000) != 0 )
    {
      v8 = 2;
      v7 = -1073741824;
    }
    if ( (a3 & 0x8000) == 0 )
    {
      v11 = SearchPathA(0, a1, 0, 0x7FFu, a2 + 4, &FilePart);
      FileA = -1;
      v12 = v11;
      if ( v11 && FindFirstFileA(a2 + 4, &FindFileData) == (HANDLE)-1LL )
      {
        HrFrefGetVBTempName(FileName, 0x800u);
        v12 = SearchPathA(0, FileName, 0, 0x7FFu, a2 + 4, &FilePart);
        DeleteFileA(lpFileName);
      }
      if ( v12 > 0x7FF )
        goto LABEL_27;
      if ( !v12 )
      {
        if ( (a3 & 0x4000) != 0 )
        {
          v13 = 2;
LABEL_28:
          SetLastError(v13);
          goto LABEL_32;
        }
        FullPathNameA = GetFullPathNameA(lpFileName, 0x7FFu, a2 + 4, &FilePart);
        if ( !FullPathNameA || FullPathNameA > 0x7FF )
        {
LABEL_27:
          v13 = 13;
          goto LABEL_28;
        }
      }
      if ( (a3 & 0x4000) != 0 )
      {
        FileA = 1;
        goto LABEL_32;
      }
    }
    FileA = (unsigned int)CreateFileA(a2 + 4, v7, v10, 0, v8, a3 & 0xFFFF0000, 0);
    goto LABEL_32;
  }
  if ( GetFullPathNameA(a1, 0x7FFu, a2 + 4, &FilePart) <= 0x7FF )
  {
    *(_DWORD *)a2 = 0;
    FileA = 0;
  }
  else
  {
    SetLastError(0xDu);
    FileA = -1;
  }
LABEL_32:
  LastError = (unsigned __int16)GetLastError();
  result = FileA;
  *(_DWORD *)a2 = LastError;
  return result;
}

```

## disassembly

```asm
0x180019278  mov     [rsp+arg_18], rbx
0x18001927d  push    rbp
0x18001927e  push    rsi
0x18001927f  push    rdi
0x180019280  push    r12
0x180019282  push    r13
0x180019284  push    r14
0x180019286  push    r15
0x180019288  mov     eax, 9A0h
0x18001928d  call    _alloca_probe
0x180019292  sub     rsp, rax
0x180019295  mov     rax, cs:__security_cookie
0x18001929c  xor     rax, rsp
0x18001929f  mov     [rsp+9D8h+var_48], rax
0x1800192a7  mov     rbx, rcx
0x1800192aa  mov     [rsp+9D8h+lpFileName], rcx
0x1800192af  xor     ecx, ecx; dwErrCode
0x1800192b1  mov     edi, r8d
0x1800192b4  mov     r14, rdx
0x1800192b7  call    cs:__imp_SetLastError
0x1800192bd  bt      edi, 8
0x1800192c1  jnb     short loc_1800192FF
0x1800192c3  mov     ebp, 7FFh
0x1800192c8  lea     r8, [r14+4]; lpBuffer
0x1800192cc  lea     r9, [rsp+9D8h+FilePart]; lpFilePart
0x1800192d1  mov     edx, ebp; nBufferLength
0x1800192d3  mov     rcx, rbx; lpFileName
0x1800192d6  call    cs:__imp_GetFullPathNameA
0x1800192dc  cmp     eax, ebp
0x1800192de  jbe     short loc_1800192F4
0x1800192e0  mov     ecx, 0Dh; dwErrCode
0x1800192e5  call    cs:__imp_SetLastError
0x1800192eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800192ef  jmp     loc_18001946F
0x1800192f4  and     dword ptr [r14], 0
0x1800192f8  xor     ebx, ebx
0x1800192fa  jmp     loc_18001946F
0x1800192ff  mov     al, dil
0x180019302  mov     edx, 0C0000000h
0x180019307  mov     ecx, 2
0x18001930c  and     al, 1
0x18001930e  neg     al
0x180019310  sbb     esi, esi
0x180019312  and     esi, edx
0x180019314  add     esi, 80000000h
0x18001931a  test    cl, dil
0x18001931d  jz      short loc_180019321
0x18001931f  or      esi, edx
0x180019321  mov     eax, edi
0x180019323  mov     r13d, 3
0x180019329  and     eax, 70h
0x18001932c  jz      short loc_18001934F
0x18001932e  cmp     eax, 10h
0x180019331  jz      short loc_18001934A
0x180019333  cmp     eax, 20h ; ' '
0x180019336  jz      short loc_180019342
0x180019338  cmp     eax, 30h ; '0'
0x18001933b  jnz     short loc_18001934F
0x18001933d  mov     r15d, ecx
0x180019340  jmp     short loc_180019352
0x180019342  mov     r15d, 1
0x180019348  jmp     short loc_180019352
0x18001934a  xor     r15d, r15d
0x18001934d  jmp     short loc_180019352
0x18001934f  mov     r15d, r13d
0x180019352  bt      edi, 0Ch
0x180019356  jnb     short loc_18001935D
0x180019358  mov     r13d, ecx
0x18001935b  mov     esi, edx
0x18001935d  bt      edi, 0Fh
0x180019361  jb      loc_180019445
0x180019367  lea     rcx, [rsp+9D8h+FilePart]
0x18001936c  lea     rax, [r14+4]
0x180019370  mov     ebp, 7FFh
0x180019375  mov     [rsp+9D8h+lpFilePart], rcx; lpFilePart
0x18001937a  xor     r8d, r8d; lpExtension
0x18001937d  mov     rdx, rbx; lpFileName
0x180019380  xor     ecx, ecx; lpPath
0x180019382  mov     r9d, ebp; nBufferLength
0x180019385  mov     [rsp+9D8h+lpBuffer], rax; lpBuffer
0x18001938a  call    cs:__imp_SearchPathA
0x180019390  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019394  mov     r12d, eax
0x180019397  test    eax, eax
0x180019399  jz      short loc_1800193F6
0x18001939b  lea     rdx, [rsp+9D8h+FindFileData]; lpFindFileData
0x1800193a0  lea     rcx, [r14+4]; lpFileName
0x1800193a4  call    cs:__imp_FindFirstFileA
0x1800193aa  cmp     rax, rbx
0x1800193ad  jnz     short loc_1800193F6
0x1800193af  lea     edx, [rbp+1]; unsigned int
0x1800193b2  lea     rcx, [rsp+9D8h+FileName]; char *
0x1800193ba  call    ?HrFrefGetVBTempName@@YAJPEADI@Z; HrFrefGetVBTempName(char *,uint)
0x1800193bf  lea     r11, [rsp+9D8h+FilePart]
0x1800193c4  lea     rax, [r14+4]
0x1800193c8  mov     [rsp+9D8h+lpFilePart], r11; lpFilePart
0x1800193cd  lea     rdx, [rsp+9D8h+FileName]; lpFileName
0x1800193d5  mov     r9d, ebp; nBufferLength
0x1800193d8  xor     r8d, r8d; lpExtension
0x1800193db  xor     ecx, ecx; lpPath
0x1800193dd  mov     [rsp+9D8h+lpBuffer], rax; lpBuffer
0x1800193e2  call    cs:__imp_SearchPathA
0x1800193e8  mov     rcx, [rsp+9D8h+lpFileName]; lpFileName
0x1800193ed  mov     r12d, eax
0x1800193f0  call    cs:__imp_DeleteFileA
0x1800193f6  cmp     r12d, ebp
0x1800193f9  ja      short loc_18001942B
0x1800193fb  test    r12d, r12d
0x1800193fe  jnz     short loc_180019438
0x180019400  bt      edi, 0Eh
0x180019404  jnb     short loc_18001940D
0x180019406  lea     ecx, [r12+2]
0x18001940b  jmp     short loc_180019430
0x18001940d  mov     rcx, [rsp+9D8h+lpFileName]; lpFileName
0x180019412  lea     r9, [rsp+9D8h+FilePart]; lpFilePart
0x180019417  lea     r8, [r14+4]; lpBuffer
0x18001941b  mov     edx, ebp; nBufferLength
0x18001941d  call    cs:__imp_GetFullPathNameA
0x180019423  test    eax, eax
0x180019425  jz      short loc_18001942B
0x180019427  cmp     eax, ebp
0x180019429  jbe     short loc_180019438
0x18001942b  mov     ecx, 0Dh; dwErrCode
0x180019430  call    cs:__imp_SetLastError
0x180019436  jmp     short loc_18001946F
0x180019438  bt      edi, 0Eh
0x18001943c  jnb     short loc_180019445
0x18001943e  mov     ebx, 1
0x180019443  jmp     short loc_18001946F
0x180019445  and     [rsp+9D8h+var_9A8], 0
0x18001944b  and     edi, 0FFFF0000h
0x180019451  lea     rcx, [r14+4]; lpFileName
0x180019455  xor     r9d, r9d; lpSecurityAttributes
0x180019458  mov     r8d, r15d; dwShareMode
0x18001945b  mov     edx, esi; dwDesiredAccess
0x18001945d  mov     dword ptr [rsp+9D8h+lpFilePart], edi; dwFlagsAndAttributes
0x180019461  mov     dword ptr [rsp+9D8h+lpBuffer], r13d; dwCreationDisposition
0x180019466  call    cs:__imp_CreateFileA
0x18001946c  mov     rbx, rax
0x18001946f  call    cs:__imp_GetLastError
0x180019475  movzx   ecx, ax
0x180019478  mov     eax, ebx
0x18001947a  mov     [r14], ecx
0x18001947d  mov     rcx, [rsp+9D8h+var_48]
0x180019485  xor     rcx, rsp; StackCookie
0x180019488  call    __security_check_cookie
0x18001948d  mov     rbx, [rsp+9D8h+arg_18]
0x180019495  add     rsp, 9A0h
0x18001949c  pop     r15
0x18001949e  pop     r14
0x1800194a0  pop     r13
0x1800194a2  pop     r12
0x1800194a4  pop     rdi
0x1800194a5  pop     rsi
0x1800194a6  pop     rbp
0x1800194a7  retn
```
