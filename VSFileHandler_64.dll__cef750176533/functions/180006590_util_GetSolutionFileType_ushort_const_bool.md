# util_GetSolutionFileType(ushort const *,bool)

- ea: `0x180006590`
- end: `0x1800067f7`
- name: `?util_GetSolutionFileType@@YAHPEBG_N@Z`
- size: `615`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180002850`

## callees

- `0x1800060c0`
- `0x1800064b8`
- `0x180006590`
- `0x180007700`
- `0x180019aa8`
- `0x1800240b0`
- `0x180024c60`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180006665`
- `KERNEL32!GetFileType` at `0x180006665`
- `KERNEL32!ReadFile` at `0x180006695`
- `KERNEL32!ReadFile` at `0x180006695`
- `KERNEL32!CloseHandle` at `0x180006673`
- `KERNEL32!CloseHandle` at `0x1800066a0`
- `KERNEL32!CloseHandle` at `0x180006673`
- `KERNEL32!CloseHandle` at `0x1800066a0`
- `KERNEL32!CreateFileW` at `0x18000664f`
- `KERNEL32!CreateFileW` at `0x18000664f`

## pseudocode

```c
__int64 __fastcall util_GetSolutionFileType(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  BOOL v5; // ebx
  DWORD v6; // ecx
  char *p_Buffer; // rdi
  unsigned int v8; // ebx
  int v9; // r14d
  __int64 v10; // r15
  char *v11; // rdx
  __int64 v12; // rax
  char SolutionFileFormat; // al
  int SolutionProductName; // eax
  int v15; // [rsp+58h] [rbp-B0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-A8h] BYREF
  int Buffer; // [rsp+68h] [rbp-A0h] BYREF
  __int16 v18; // [rsp+6Ch] [rbp-9Ch] BYREF
  char v19; // [rsp+6Eh] [rbp-9Ah] BYREF
  wchar_t String1[264]; // [rsp+168h] [rbp+60h] BYREF

  wsplitpath_s(lpFileName, 0, 0, 0, 0, 0, 0, String1, 0x104u);
  if ( wcsicmp(String1, L".slnx") )
  {
    if ( wcsicmp(String1, L".sln") )
      return 0xFFFFFFFFLL;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      if ( GetFileType(FileW) != 1 )
      {
        CloseHandle(v4);
        return 0xFFFFFFFFLL;
      }
      NumberOfBytesRead = 0;
      v5 = ReadFile(v4, &Buffer, 0x100u, &NumberOfBytesRead, 0);
      CloseHandle(v4);
      if ( v5 )
      {
        v6 = NumberOfBytesRead;
        p_Buffer = (char *)&Buffer;
        v8 = 0;
        if ( NumberOfBytesRead >= 5 && Buffer == 230669295 && (_BYTE)v18 == 10 )
        {
          v8 = 1;
          p_Buffer = (char *)&v18 + 1;
          v6 = NumberOfBytesRead - 5;
        }
        else
        {
          if ( NumberOfBytesRead < 6 || Buffer != 917247 || v18 != 10 )
          {
LABEL_17:
            v9 = 0;
            v10 = 0;
            do
            {
              if ( v8 < 2 )
              {
                v11 = off_180033750[v10];
                v12 = -1;
                do
                  ++v12;
                while ( v11[v12] );
              }
              else
              {
                v11 = (char *)off_180033860[v10];
                v12 = -1;
                do
                  ++v12;
                while ( *(_WORD *)&v11[2 * v12] );
                LODWORD(v12) = 2 * v12;
              }
              if ( v6 >= (unsigned int)v12 )
              {
                _mm_lfence();
                if ( !memcmp(p_Buffer, v11, (unsigned int)v12) )
                  return (unsigned int)v9;
                v6 = NumberOfBytesRead;
              }
              ++v9;
              ++v10;
            }
            while ( v9 < 33 );
            SolutionFileFormat = anonymous_namespace_::util_GetSolutionFileFormat(p_Buffer, (__int64)v11, v8, &v15);
            if ( (SolutionFileFormat != 0 ? v15 : 0) >= 11 )
            {
              SolutionProductName = anonymous_namespace_::util_GetSolutionProductName(p_Buffer, NumberOfBytesRead, v8);
              if ( SolutionProductName != -1 )
                return (unsigned int)(SolutionProductName + 18);
            }
            return 68;
          }
          v8 = 2;
          p_Buffer = &v19;
          v6 = NumberOfBytesRead - 6;
        }
        NumberOfBytesRead = v6;
        goto LABEL_17;
      }
    }
  }
  return 68;
}

```

## disassembly

```asm
0x180006590  mov     rax, rsp
0x180006593  mov     [rax+10h], rbx
0x180006597  mov     [rax+18h], rdi
0x18000659b  mov     [rax+20h], r12
0x18000659f  push    rbp
0x1800065a0  push    r14
0x1800065a2  push    r15
0x1800065a4  lea     rbp, [rax-298h]
0x1800065ab  sub     rsp, 380h
0x1800065b2  mov     rax, cs:__security_cookie
0x1800065b9  xor     rax, rsp
0x1800065bc  mov     [rbp+290h+var_20], rax
0x1800065c3  mov     [rsp+390h+ExtCount], 104h; ExtCount
0x1800065cc  lea     rax, [rbp+290h+String1]
0x1800065d0  mov     [rsp+390h+Ext], rax; Ext
0x1800065d5  xor     r12d, r12d
0x1800065d8  mov     [rsp+390h+FilenameCount], r12; FilenameCount
0x1800065dd  xor     r9d, r9d; Dir
0x1800065e0  mov     [rsp+390h+Filename], r12; Filename
0x1800065e5  xor     r8d, r8d; DriveCount
0x1800065e8  xor     edx, edx; Drive
0x1800065ea  mov     [rsp+390h+DirCount], r12; DirCount
0x1800065ef  mov     rbx, rcx
0x1800065f2  call    _wsplitpath_s
0x1800065f7  lea     rdx, aSlnx; ".slnx"
0x1800065fe  lea     rcx, [rbp+290h+String1]; String1
0x180006602  call    _wcsicmp
0x180006607  test    eax, eax
0x180006609  jz      loc_1800067C6
0x18000660f  lea     rdx, aSln; ".sln"
0x180006616  lea     rcx, [rbp+290h+String1]; String1
0x18000661a  call    _wcsicmp
0x18000661f  test    eax, eax
0x180006621  jz      short loc_18000662B
0x180006623  or      eax, 0FFFFFFFFh
0x180006626  jmp     loc_1800067CB
0x18000662b  xor     r9d, r9d; lpSecurityAttributes
0x18000662e  mov     [rsp+390h+FilenameCount], r12; hTemplateFile
0x180006633  mov     dword ptr [rsp+390h+Filename], 8000080h; dwFlagsAndAttributes
0x18000663b  mov     edx, 80000000h; dwDesiredAccess
0x180006640  mov     rcx, rbx; lpFileName
0x180006643  mov     dword ptr [rsp+390h+DirCount], 3; dwCreationDisposition
0x18000664b  lea     r8d, [r9+1]; dwShareMode
0x18000664f  call    cs:__imp_CreateFileW
0x180006655  mov     rdi, rax
0x180006658  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000665c  jz      loc_1800067C6
0x180006662  mov     rcx, rax; hFile
0x180006665  call    cs:__imp_GetFileType
0x18000666b  mov     rcx, rdi; hFile
0x18000666e  cmp     eax, 1
0x180006671  jz      short loc_18000667B
0x180006673  call    cs:__imp_CloseHandle
0x180006679  jmp     short loc_180006623
0x18000667b  lea     r9, [rsp+390h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006680  mov     [rsp+390h+NumberOfBytesRead], r12d
0x180006685  mov     r8d, 100h; nNumberOfBytesToRead
0x18000668b  mov     [rsp+390h+DirCount], r12; lpOverlapped
0x180006690  lea     rdx, [rsp+390h+Buffer]; lpBuffer
0x180006695  call    cs:__imp_ReadFile
0x18000669b  mov     rcx, rdi; hObject
0x18000669e  mov     ebx, eax
0x1800066a0  call    cs:__imp_CloseHandle
0x1800066a6  test    ebx, ebx
0x1800066a8  jz      loc_1800067C6
0x1800066ae  mov     ecx, [rsp+390h+NumberOfBytesRead]
0x1800066b2  lea     rdi, [rsp+390h+Buffer]
0x1800066b7  movzx   edx, [rsp+390h+var_32C]
0x1800066bc  mov     ebx, r12d
0x1800066bf  mov     eax, [rsp+390h+Buffer]
0x1800066c3  cmp     ecx, 5
0x1800066c6  jb      short loc_1800066E7
0x1800066c8  cmp     eax, cs:dword_18002F428
0x1800066ce  jnz     short loc_1800066E7
0x1800066d0  cmp     dl, cs:byte_18002F42C
0x1800066d6  jnz     short loc_1800066E7
0x1800066d8  mov     ebx, 1
0x1800066dd  lea     rdi, [rsp+390h+var_32C+1]
0x1800066e2  add     ecx, 0FFFFFFFBh
0x1800066e5  jmp     short loc_18000670A
0x1800066e7  cmp     ecx, 6
0x1800066ea  jb      short loc_18000670E
0x1800066ec  cmp     eax, cs:dword_180033708
0x1800066f2  jnz     short loc_18000670E
0x1800066f4  cmp     dx, cs:word_18003370C
0x1800066fb  jnz     short loc_18000670E
0x1800066fd  mov     ebx, 2
0x180006702  lea     rdi, [rsp+390h+var_32A]
0x180006707  add     ecx, 0FFFFFFFAh
0x18000670a  mov     [rsp+390h+NumberOfBytesRead], ecx
0x18000670e  mov     r14d, r12d
0x180006711  lea     r8, cs:180000000h
0x180006718  mov     r15, r12
0x18000671b  mov     edx, ebx
0x18000671d  test    ebx, ebx
0x18000671f  jz      short loc_180006745
0x180006721  sub     edx, 1
0x180006724  jz      short loc_180006745
0x180006726  cmp     edx, 1
0x180006729  jnz     short loc_18000677B
0x18000672b  mov     rdx, [r15+r8+33860h]
0x180006733  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006737  inc     rax
0x18000673a  cmp     [rdx+rax*2], r12w
0x18000673f  jnz     short loc_180006737
0x180006741  add     eax, eax
0x180006743  jmp     short loc_18000675A
0x180006745  mov     rdx, [r15+r8+33750h]; Buf2
0x18000674d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006751  inc     rax
0x180006754  cmp     [rdx+rax], r12b
0x180006758  jnz     short loc_180006751
0x18000675a  cmp     ecx, eax
0x18000675c  jb      short loc_18000677B
0x18000675e  lfence
0x180006761  mov     r8d, eax; Size
0x180006764  mov     rcx, rdi; Buf1
0x180006767  call    memcmp
0x18000676c  test    eax, eax
0x18000676e  jz      short loc_1800067C1
0x180006770  mov     ecx, [rsp+390h+NumberOfBytesRead]
0x180006774  lea     r8, cs:180000000h
0x18000677b  inc     r14d
0x18000677e  add     r15, 8
0x180006782  cmp     r14d, 21h ; '!'
0x180006786  jl      short loc_18000671B
0x180006788  lea     r9, [rsp+390h+var_340]
0x18000678d  mov     r8d, ebx
0x180006790  mov     rcx, rdi
0x180006793  call    _anonymous_namespace___util_GetSolutionFileFormat
0x180006798  neg     al
0x18000679a  sbb     r9d, r9d
0x18000679d  and     r9d, [rsp+390h+var_340]
0x1800067a2  cmp     r9d, 0Bh
0x1800067a6  jl      short loc_1800067C6
0x1800067a8  mov     edx, [rsp+390h+NumberOfBytesRead]
0x1800067ac  mov     r8d, ebx
0x1800067af  mov     rcx, rdi
0x1800067b2  call    _anonymous_namespace___util_GetSolutionProductName
0x1800067b7  cmp     eax, 0FFFFFFFFh
0x1800067ba  jz      short loc_1800067C6
0x1800067bc  add     eax, 12h
0x1800067bf  jmp     short loc_1800067CB
0x1800067c1  mov     eax, r14d
0x1800067c4  jmp     short loc_1800067CB
0x1800067c6  mov     eax, 44h ; 'D'
0x1800067cb  mov     rcx, [rbp+290h+var_20]
0x1800067d2  xor     rcx, rsp; StackCookie
0x1800067d5  call    __security_check_cookie
0x1800067da  lea     r11, [rsp+390h+var_10]
0x1800067e2  mov     rbx, [r11+28h]
0x1800067e6  mov     rdi, [r11+30h]
0x1800067ea  mov     r12, [r11+38h]
0x1800067ee  mov     rsp, r11
0x1800067f1  pop     r15
0x1800067f3  pop     r14
0x1800067f5  pop     rbp
0x1800067f6  retn
```
