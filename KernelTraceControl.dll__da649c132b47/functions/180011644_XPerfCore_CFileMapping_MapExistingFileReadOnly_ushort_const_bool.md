# XPerfCore::CFileMapping::MapExistingFileReadOnly(ushort const *,bool)

- ea: `0x180011644`
- end: `0x180011811`
- name: `?MapExistingFileReadOnly@CFileMapping@XPerfCore@@QEAAJPEBG_N@Z`
- size: `461`
- prototype: `__int64 __fastcall(XPerfCore::CFileMapping *this, const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a30c`
- `0x1800262c4`

## callees

- `0x180011644`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800116f1`
- `KERNEL32!GetLastError` at `0x1800116f1`
- `KERNEL32!GetCurrentProcess` at `0x180011678`
- `KERNEL32!GetCurrentProcess` at `0x180011678`
- `KERNEL32!CloseHandle` at `0x180011758`
- `KERNEL32!CloseHandle` at `0x18001176a`
- `KERNEL32!CloseHandle` at `0x180011758`
- `KERNEL32!CloseHandle` at `0x18001176a`
- `KERNEL32!UnmapViewOfFile` at `0x180011745`
- `KERNEL32!UnmapViewOfFile` at `0x180011745`
- `KERNEL32!MapViewOfFileEx` at `0x18001178f`
- `KERNEL32!MapViewOfFileEx` at `0x18001178f`
- `KERNEL32!CreateFileMappingW` at `0x18001172d`
- `KERNEL32!CreateFileMappingW` at `0x18001172d`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1800116e2`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1800116e2`
- `KERNEL32!CreateFileW` at `0x1800116ce`
- `KERNEL32!CreateFileW` at `0x1800116ce`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x18001169c`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x18001169c`
- `KERNEL32!IsWow64Process` at `0x180011686`
- `KERNEL32!IsWow64Process` at `0x180011686`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall XPerfCore::CFileMapping::MapExistingFileReadOnly(
        XPerfCore::CFileMapping *this,
        const unsigned __int16 *a2,
        char a3)
{
  HANDLE CurrentProcess; // rax
  BOOL v7; // eax
  signed int LastError; // ecx
  __int64 result; // rax
  HANDLE FileMappingW; // rax
  const void *v11; // rcx
  void *v12; // rcx
  unsigned int *v13; // rax
  unsigned int *v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // ecx
  char *v17; // rax
  int v18; // edx
  WINBOOL Wow64Process; // [rsp+60h] [rbp+8h] BYREF
  PVOID OldValue; // [rsp+78h] [rbp+20h] BYREF

  if ( *(_OWORD *)((char *)this + 8) != 0 )
    return 2147483662LL;
  Wow64Process = 0;
  OldValue = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process == 1 )
  {
    v7 = Wow64DisableWow64FsRedirection(&OldValue);
    Wow64Process = v7 ? Wow64Process : 0;
  }
  *(_QWORD *)this = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( Wow64Process )
    Wow64RevertWow64FsRedirection(OldValue);
  if ( *(_QWORD *)this != -1 )
  {
    FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, a3 != 0 ? 285212674 : 2, 0, 0, 0);
    *((_QWORD *)this + 1) = FileMappingW;
    if ( !FileMappingW )
    {
      v11 = (const void *)*((_QWORD *)this + 2);
      if ( v11 )
      {
        UnmapViewOfFile(v11);
        *((_QWORD *)this + 2) = 0;
      }
      goto LABEL_14;
    }
    v13 = (unsigned int *)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    *((_QWORD *)this + 2) = v13;
    v14 = v13;
    if ( !v13 )
    {
LABEL_14:
      v12 = (void *)*((_QWORD *)this + 1);
      if ( v12 )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 1) = 0;
      }
      if ( *(_QWORD *)this != -1 )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = -1;
      }
      goto LABEL_8;
    }
    if ( *(_WORD *)v13 == 23117 )
    {
      v15 = v13[15];
      if ( (v15 & 3) == 0 && (_DWORD)v15 != -1 )
      {
        v16 = ~(_DWORD)v15;
        if ( (unsigned int)~(_DWORD)v15 >= 0x1B )
        {
          v17 = (char *)v14 + v15;
          if ( *(_DWORD *)v17 == 17744 )
          {
            v18 = *((unsigned __int16 *)v17 + 12);
            if ( v18 == 267 )
            {
              if ( v16 > 0xF8 )
              {
LABEL_30:
                *((_QWORD *)this + 3) = *((unsigned int *)v17 + 20);
                return 0;
              }
            }
            else if ( v18 == 523 && v16 > 0x108 )
            {
              goto LABEL_30;
            }
          }
        }
      }
    }
    v17 = 0;
    goto LABEL_30;
  }
LABEL_8:
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180011644  mov     [rsp+arg_8], rbx
0x180011649  push    rbp
0x18001164a  push    rsi
0x18001164b  push    rdi
0x18001164c  sub     rsp, 40h
0x180011650  xor     ebp, ebp
0x180011652  mov     sil, r8b
0x180011655  mov     rdi, rdx
0x180011658  mov     rbx, rcx
0x18001165b  cmp     [rcx+8], rbp
0x18001165f  jnz     loc_1800117FF
0x180011665  cmp     [rcx+10h], rbp
0x180011669  jnz     loc_1800117FF
0x18001166f  mov     [rsp+58h+Wow64Process], ebp
0x180011673  mov     [rsp+58h+OldValue], rbp
0x180011678  call    cs:__imp_GetCurrentProcess
0x18001167e  mov     rcx, rax; hProcess
0x180011681  lea     rdx, [rsp+58h+Wow64Process]; Wow64Process
0x180011686  call    cs:__imp_IsWow64Process
0x18001168c  test    eax, eax
0x18001168e  jz      short loc_1800116AA
0x180011690  cmp     [rsp+58h+Wow64Process], 1
0x180011695  jnz     short loc_1800116AA
0x180011697  lea     rcx, [rsp+58h+OldValue]; OldValue
0x18001169c  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1800116a2  neg     eax
0x1800116a4  sbb     ecx, ecx
0x1800116a6  and     [rsp+58h+Wow64Process], ecx
0x1800116aa  xor     r9d, r9d; lpSecurityAttributes
0x1800116ad  mov     [rsp+58h+hTemplateFile], rbp; hTemplateFile
0x1800116b2  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800116ba  mov     edx, 80000000h; dwDesiredAccess
0x1800116bf  mov     rcx, rdi; lpFileName
0x1800116c2  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800116ca  lea     r8d, [r9+1]; dwShareMode
0x1800116ce  call    cs:__imp_CreateFileW
0x1800116d4  mov     [rbx], rax
0x1800116d7  cmp     [rsp+58h+Wow64Process], ebp
0x1800116db  jz      short loc_1800116E8
0x1800116dd  mov     rcx, [rsp+58h+OldValue]; OlValue
0x1800116e2  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1800116e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800116ec  cmp     [rbx], rdi
0x1800116ef  jnz     short loc_18001170B
0x1800116f1  call    cs:__imp_GetLastError
0x1800116f7  mov     ecx, eax
0x1800116f9  movzx   eax, ax
0x1800116fc  or      eax, 80070000h
0x180011701  test    ecx, ecx
0x180011703  cmovle  eax, ecx
0x180011706  jmp     loc_180011804
0x18001170b  mov     rcx, [rbx]; hFile
0x18001170e  neg     sil
0x180011711  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rbp; lpName
0x180011716  sbb     r8d, r8d
0x180011719  mov     [rsp+58h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x18001171d  and     r8d, 11000000h
0x180011724  xor     r9d, r9d; dwMaximumSizeHigh
0x180011727  add     r8d, 2; flProtect
0x18001172b  xor     edx, edx; lpFileMappingAttributes
0x18001172d  call    cs:__imp_CreateFileMappingW
0x180011733  mov     [rbx+8], rax
0x180011737  test    rax, rax
0x18001173a  jnz     short loc_180011778
0x18001173c  mov     rcx, [rbx+10h]; lpBaseAddress
0x180011740  test    rcx, rcx
0x180011743  jz      short loc_18001174F
0x180011745  call    cs:__imp_UnmapViewOfFile
0x18001174b  mov     [rbx+10h], rbp
0x18001174f  mov     rcx, [rbx+8]; hObject
0x180011753  test    rcx, rcx
0x180011756  jz      short loc_180011762
0x180011758  call    cs:__imp_CloseHandle
0x18001175e  mov     [rbx+8], rbp
0x180011762  cmp     [rbx], rdi
0x180011765  jz      short loc_1800116F1
0x180011767  mov     rcx, [rbx]; hObject
0x18001176a  call    cs:__imp_CloseHandle
0x180011770  mov     [rbx], rdi
0x180011773  jmp     loc_1800116F1
0x180011778  xor     r9d, r9d; dwFileOffsetLow
0x18001177b  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rbp; lpBaseAddress
0x180011780  xor     r8d, r8d; dwFileOffsetHigh
0x180011783  mov     qword ptr [rsp+58h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x180011788  mov     rcx, rax; hFileMappingObject
0x18001178b  lea     edx, [r9+4]; dwDesiredAccess
0x18001178f  call    cs:__imp_MapViewOfFileEx
0x180011795  mov     [rbx+10h], rax
0x180011799  mov     rdx, rax
0x18001179c  test    rax, rax
0x18001179f  jz      short loc_18001174F
0x1800117a1  mov     eax, 5A4Dh
0x1800117a6  cmp     [rdx], ax
0x1800117a9  jnz     short loc_1800117F1
0x1800117ab  mov     eax, [rdx+3Ch]
0x1800117ae  test    al, 3
0x1800117b0  jnz     short loc_1800117F1
0x1800117b2  cmp     eax, 0FFFFFFFFh
0x1800117b5  jnb     short loc_1800117F1
0x1800117b7  mov     ecx, eax
0x1800117b9  not     ecx
0x1800117bb  cmp     ecx, 1Bh
0x1800117be  jb      short loc_1800117F1
0x1800117c0  add     rax, rdx
0x1800117c3  cmp     dword ptr [rax], 4550h
0x1800117c9  jnz     short loc_1800117F1
0x1800117cb  movzx   edx, word ptr [rax+18h]
0x1800117cf  cmp     edx, 10Bh
0x1800117d5  jz      short loc_1800117E9
0x1800117d7  cmp     edx, 20Bh
0x1800117dd  jnz     short loc_1800117F1
0x1800117df  cmp     ecx, 108h
0x1800117e5  jbe     short loc_1800117F1
0x1800117e7  jmp     short loc_1800117F4
0x1800117e9  cmp     ecx, 0F8h
0x1800117ef  ja      short loc_1800117F4
0x1800117f1  mov     rax, rbp
0x1800117f4  mov     eax, [rax+50h]
0x1800117f7  mov     [rbx+18h], rax
0x1800117fb  xor     eax, eax
0x1800117fd  jmp     short loc_180011804
0x1800117ff  mov     eax, 8000000Eh
0x180011804  mov     rbx, [rsp+58h+arg_8]
0x180011809  add     rsp, 40h
0x18001180d  pop     rdi
0x18001180e  pop     rsi
0x18001180f  pop     rbp
0x180011810  retn
```
