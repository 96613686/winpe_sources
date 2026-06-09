# GetILTypeForFile(ushort const *,ulong *)

- ea: `0x18000b7c8`
- end: `0x18000bb40`
- name: `?GetILTypeForFile@@YAHPEBGPEAK@Z`
- size: `888`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c630`

## callees

- `0x18000b7c8`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `ntdll!RtlImageRvaToVa` at `0x18000ba35`
- `ntdll!RtlImageRvaToVa` at `0x18000ba35`
- `KERNEL32!HeapFree` at `0x18000baf7`
- `KERNEL32!HeapFree` at `0x18000baf7`
- `KERNEL32!CloseHandle` at `0x18000ba0e`
- `KERNEL32!CloseHandle` at `0x18000bb0a`
- `KERNEL32!CloseHandle` at `0x18000ba0e`
- `KERNEL32!CloseHandle` at `0x18000bb0a`
- `KERNEL32!HeapAlloc` at `0x18000b92d`
- `KERNEL32!HeapAlloc` at `0x18000b92d`
- `KERNEL32!GetProcessHeap` at `0x18000b918`
- `KERNEL32!GetProcessHeap` at `0x18000bae9`
- `KERNEL32!GetProcessHeap` at `0x18000b918`
- `KERNEL32!GetProcessHeap` at `0x18000bae9`
- `KERNEL32!ReadFile` at `0x18000b889`
- `KERNEL32!ReadFile` at `0x18000b95b`
- `KERNEL32!ReadFile` at `0x18000b889`
- `KERNEL32!ReadFile` at `0x18000b95b`
- `KERNEL32!GetFileSizeEx` at `0x18000b8c0`
- `KERNEL32!GetFileSizeEx` at `0x18000b8c0`
- `KERNEL32!SetFilePointer` at `0x18000b909`
- `KERNEL32!SetFilePointer` at `0x18000b909`
- `KERNEL32!CreateFileW` at `0x18000b855`
- `KERNEL32!CreateFileW` at `0x18000b855`
- `KERNEL32!UnmapViewOfFile` at `0x18000bade`
- `KERNEL32!UnmapViewOfFile` at `0x18000bade`
- `KERNEL32!CreateFileMappingW` at `0x18000b9d5`
- `KERNEL32!CreateFileMappingW` at `0x18000b9d5`
- `KERNEL32!MapViewOfFile` at `0x18000b9fb`
- `KERNEL32!MapViewOfFile` at `0x18000b9fb`

## pseudocode

```c
__int64 __fastcall GetILTypeForFile(LPCWSTR lpFileName, unsigned int *a2)
{
  _DWORD *v3; // rsi
  char *v4; // r13
  unsigned int v5; // r12d
  int v6; // r14d
  char *FileW; // rax
  char *v8; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  unsigned int v11; // eax
  HANDLE FileMappingW; // rax
  _DWORD *v13; // rcx
  unsigned int *v14; // rax
  HANDLE v15; // rax
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-C0h] BYREF
  int v19; // [rsp+4Ch] [rbp-BCh]
  unsigned int v20; // [rsp+50h] [rbp-B8h]
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A8h]
  char *v23; // [rsp+68h] [rbp-A0h]
  void *v24; // [rsp+70h] [rbp-98h]
  char *v25; // [rsp+78h] [rbp-90h]
  unsigned int *v26; // [rsp+80h] [rbp-88h]
  _WORD Buffer[30]; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v28; // [rsp+CCh] [rbp-3Ch]

  v26 = a2;
  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  FileSize.QuadPart = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v19 = 0;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v8 = FileW;
  v23 = FileW;
  if ( FileW == (char *)-1LL )
    goto LABEL_34;
  NumberOfBytesRead = 0;
  v5 = ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0);
  if ( !v5 )
    goto LABEL_34;
  if ( NumberOfBytesRead != 64 )
    goto LABEL_34;
  if ( Buffer[0] != 23117 )
    goto LABEL_34;
  if ( !GetFileSizeEx(v8, &FileSize) )
    goto LABEL_34;
  if ( v28 > 0x10000000 )
    goto LABEL_34;
  if ( FileSize.QuadPart < 0 )
    goto LABEL_34;
  if ( (int)v28 >= FileSize.QuadPart )
    goto LABEL_34;
  if ( SetFilePointer(v8, v28, 0, 0) == -1 )
    goto LABEL_34;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, 0x108u);
  v3 = v10;
  v24 = v10;
  if ( !v10 )
    goto LABEL_34;
  NumberOfBytesRead = 0;
  v5 = ReadFile(v8, v10, 0x108u, &NumberOfBytesRead, 0);
  v20 = v5;
  if ( !v5 || NumberOfBytesRead != 264 || *v3 != 17744 )
    goto LABEL_34;
  if ( *((_WORD *)v3 + 12) == 267 )
  {
    if ( v3[58] )
    {
      v11 = v3[59];
      if ( v11 )
      {
        if ( v11 >= 0x48 )
        {
          FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, 0, 0);
          hObject = FileMappingW;
          if ( !FileMappingW )
            goto LABEL_34;
          v4 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          v25 = v4;
          CloseHandle(hObject);
          if ( !v4 )
            goto LABEL_34;
          v13 = RtlImageRvaToVa((PIMAGE_NT_HEADERS)&v4[v28], v4, v3[58], 0);
          if ( !v13 )
          {
            v14 = a2;
            goto LABEL_35;
          }
          if ( *v13 != v3[59] )
          {
            v14 = a2;
            goto LABEL_35;
          }
          if ( *((_WORD *)v13 + 2) >= 2u || *((_WORD *)v13 + 3) < 5u )
          {
            v6 = v13[4] & 0x20003;
            v19 = v6;
          }
          else
          {
            v6 = 2;
            v19 = 2;
          }
        }
        else
        {
          v6 = 2;
        }
      }
    }
    goto LABEL_33;
  }
  if ( *((_WORD *)v3 + 12) == 523 )
  {
    if ( v3[62] && v3[63] )
      v6 = 0;
LABEL_33:
    v5 = 1;
  }
LABEL_34:
  v14 = a2;
LABEL_35:
  *v14 = v6;
  if ( v4 )
    UnmapViewOfFile(v4);
  if ( v3 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v3);
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return v5;
}

```

## disassembly

```asm
0x18000b7c8  mov     r11, rsp
0x18000b7cb  mov     [r11+18h], rbx
0x18000b7cf  mov     [r11+20h], rsi
0x18000b7d3  push    rdi
0x18000b7d4  push    r12
0x18000b7d6  push    r13
0x18000b7d8  push    r14
0x18000b7da  push    r15
0x18000b7dc  sub     rsp, 0E0h
0x18000b7e3  mov     rax, cs:__security_cookie
0x18000b7ea  xor     rax, rsp
0x18000b7ed  mov     [rsp+108h+var_38], rax
0x18000b7f5  mov     [rsp+108h+var_C8], rdx
0x18000b7fa  mov     rbx, rcx
0x18000b7fd  mov     [rsp+108h+var_88], rdx
0x18000b805  xor     edi, edi
0x18000b807  mov     [rsp+108h+NumberOfBytesRead], edi
0x18000b80b  lea     r15d, [rdi+40h]
0x18000b80f  mov     r8d, r15d; Size
0x18000b812  xor     edx, edx; Val
0x18000b814  lea     rcx, [r11-78h]; void *
0x18000b818  call    memset_0
0x18000b81d  mov     qword ptr [rsp+108h+FileSize], rdi
0x18000b822  mov     esi, edi
0x18000b824  mov     r13d, edi
0x18000b827  mov     r12d, edi
0x18000b82a  mov     r14d, edi
0x18000b82d  mov     [rsp+108h+var_BC], edi
0x18000b831  mov     [rsp+108h+hTemplateFile], rdi; hTemplateFile
0x18000b836  mov     [rsp+108h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000b83e  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b846  xor     r9d, r9d; lpSecurityAttributes
0x18000b849  mov     edx, 80000000h; dwDesiredAccess
0x18000b84e  lea     r8d, [rdi+1]; dwShareMode
0x18000b852  mov     rcx, rbx; lpFileName
0x18000b855  call    cs:__imp_CreateFileW
0x18000b85b  mov     rbx, rax
0x18000b85e  mov     [rsp+108h+var_A0], rax
0x18000b863  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b867  jz      loc_18000BACE
0x18000b86d  mov     [rsp+108h+NumberOfBytesRead], edi
0x18000b871  mov     qword ptr [rsp+108h+dwCreationDisposition], rdi; lpOverlapped
0x18000b876  lea     r9, [rsp+108h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000b87b  mov     r8d, r15d; nNumberOfBytesToRead
0x18000b87e  lea     rdx, [rsp+108h+Buffer]; lpBuffer
0x18000b886  mov     rcx, rax; hFile
0x18000b889  call    cs:__imp_ReadFile
0x18000b88f  mov     r12d, eax
0x18000b892  test    eax, eax
0x18000b894  jz      loc_18000BACE
0x18000b89a  cmp     [rsp+108h+NumberOfBytesRead], r15d
0x18000b89f  jnz     loc_18000BACE
0x18000b8a5  mov     eax, 5A4Dh
0x18000b8aa  cmp     [rsp+108h+Buffer], ax
0x18000b8b2  jnz     loc_18000BACE
0x18000b8b8  lea     rdx, [rsp+108h+FileSize]; lpFileSize
0x18000b8bd  mov     rcx, rbx; hFile
0x18000b8c0  call    cs:__imp_GetFileSizeEx
0x18000b8c6  test    eax, eax
0x18000b8c8  jz      loc_18000BACE
0x18000b8ce  movsxd  rdx, [rsp+108h+var_3C]; lDistanceToMove
0x18000b8d6  test    edx, edx
0x18000b8d8  js      loc_18000BACE
0x18000b8de  cmp     edx, 10000000h
0x18000b8e4  ja      loc_18000BACE
0x18000b8ea  cmp     qword ptr [rsp+108h+FileSize], rdi
0x18000b8ef  jl      loc_18000BACE
0x18000b8f5  cmp     rdx, qword ptr [rsp+108h+FileSize]
0x18000b8fa  jge     loc_18000BACE
0x18000b900  xor     r9d, r9d; dwMoveMethod
0x18000b903  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000b906  mov     rcx, rbx; hFile
0x18000b909  call    cs:__imp_SetFilePointer
0x18000b90f  cmp     eax, 0FFFFFFFFh
0x18000b912  jz      loc_18000BACE
0x18000b918  call    cs:__imp_GetProcessHeap
0x18000b91e  mov     rcx, rax; hHeap
0x18000b921  mov     r15d, 108h
0x18000b927  mov     r8d, r15d; dwBytes
0x18000b92a  lea     edx, [rdi+8]; dwFlags
0x18000b92d  call    cs:__imp_HeapAlloc
0x18000b933  mov     rsi, rax
0x18000b936  mov     [rsp+108h+var_98], rax
0x18000b93b  test    rax, rax
0x18000b93e  jz      loc_18000BACE
0x18000b944  mov     [rsp+108h+NumberOfBytesRead], edi
0x18000b948  mov     qword ptr [rsp+108h+dwCreationDisposition], rdi; lpOverlapped
0x18000b94d  lea     r9, [rsp+108h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000b952  mov     r8d, r15d; nNumberOfBytesToRead
0x18000b955  mov     rdx, rax; lpBuffer
0x18000b958  mov     rcx, rbx; hFile
0x18000b95b  call    cs:__imp_ReadFile
0x18000b961  mov     r12d, eax
0x18000b964  mov     [rsp+108h+var_B8], eax
0x18000b968  test    eax, eax
0x18000b96a  jz      loc_18000BACE
0x18000b970  cmp     [rsp+108h+NumberOfBytesRead], r15d
0x18000b975  jnz     loc_18000BACE
0x18000b97b  cmp     dword ptr [rsi], 4550h
0x18000b981  jnz     loc_18000BACE
0x18000b987  lea     eax, [r15+3]
0x18000b98b  cmp     [rsi+18h], ax
0x18000b98f  jnz     loc_18000BAAB
0x18000b995  cmp     [rsi+0E8h], edi
0x18000b99b  jz      loc_18000BAC8
0x18000b9a1  mov     eax, [rsi+0ECh]
0x18000b9a7  test    eax, eax
0x18000b9a9  jz      loc_18000BAC8
0x18000b9af  cmp     eax, 48h ; 'H'
0x18000b9b2  jnb     short loc_18000B9BD
0x18000b9b4  lea     r14d, [rdi+2]
0x18000b9b8  jmp     loc_18000BAC8
0x18000b9bd  mov     qword ptr [rsp+108h+dwFlagsAndAttributes], rdi; lpName
0x18000b9c2  mov     [rsp+108h+dwCreationDisposition], edi; dwMaximumSizeLow
0x18000b9c6  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b9c9  lea     r15d, [r9+2]
0x18000b9cd  mov     r8d, r15d; flProtect
0x18000b9d0  xor     edx, edx; lpFileMappingAttributes
0x18000b9d2  mov     rcx, rbx; hFile
0x18000b9d5  call    cs:__imp_CreateFileMappingW
0x18000b9db  mov     [rsp+108h+hObject], rax
0x18000b9e0  test    rax, rax
0x18000b9e3  jz      loc_18000BACE
0x18000b9e9  mov     qword ptr [rsp+108h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x18000b9ee  xor     r9d, r9d; dwFileOffsetLow
0x18000b9f1  xor     r8d, r8d; dwFileOffsetHigh
0x18000b9f4  lea     edx, [r15+2]; dwDesiredAccess
0x18000b9f8  mov     rcx, rax; hFileMappingObject
0x18000b9fb  call    cs:__imp_MapViewOfFile
0x18000ba01  mov     r13, rax
0x18000ba04  mov     [rsp+108h+var_90], rax
0x18000ba09  mov     rcx, [rsp+108h+hObject]; hObject
0x18000ba0e  call    cs:__imp_CloseHandle
0x18000ba14  test    r13, r13
0x18000ba17  jz      loc_18000BACE
0x18000ba1d  movsxd  rcx, [rsp+108h+var_3C]
0x18000ba25  add     rcx, r13; NtHeader
0x18000ba28  xor     r9d, r9d; SectionHeader
0x18000ba2b  mov     r8d, [rsi+0E8h]; Rva
0x18000ba32  mov     rdx, r13; BaseAddress
0x18000ba35  call    cs:__imp_RtlImageRvaToVa
0x18000ba3b  mov     rcx, rax
0x18000ba3e  test    rax, rax
0x18000ba41  jnz     short loc_18000BA4D
0x18000ba43  mov     rax, [rsp+108h+var_C8]
0x18000ba48  jmp     loc_18000BAD3
0x18000ba4d  mov     eax, [rsi+0ECh]
0x18000ba53  cmp     [rcx], eax
0x18000ba55  jz      short loc_18000BA5E
0x18000ba57  mov     rax, [rsp+108h+var_C8]
0x18000ba5c  jmp     short loc_18000BAD3
0x18000ba5e  cmp     [rcx+4], r15w
0x18000ba63  jnb     short loc_18000BA76
0x18000ba65  cmp     word ptr [rcx+6], 5
0x18000ba6a  jb      short loc_18000BA76
0x18000ba6c  mov     r14d, r15d
0x18000ba6f  mov     [rsp+108h+var_BC], r15d
0x18000ba74  jmp     short loc_18000BA86
0x18000ba76  mov     r14d, [rcx+10h]
0x18000ba7a  and     r14d, 20003h
0x18000ba81  mov     [rsp+108h+var_BC], r14d
0x18000ba86  jmp     short loc_18000BAC8
0x18000ba88  mov     r12d, [rsp+108h+var_B8]
0x18000ba8d  mov     r14d, [rsp+108h+var_BC]
0x18000ba92  mov     rbx, [rsp+108h+var_A0]
0x18000ba97  mov     rsi, [rsp+108h+var_98]
0x18000ba9c  mov     r13, [rsp+108h+var_90]
0x18000baa1  mov     rax, [rsp+108h+var_88]
0x18000baa9  jmp     short loc_18000BAD3
0x18000baab  mov     eax, 20Bh
0x18000bab0  cmp     [rsi+18h], ax
0x18000bab4  jnz     short loc_18000BACE
0x18000bab6  cmp     [rsi+0F8h], edi
0x18000babc  jz      short loc_18000BAC8
0x18000babe  cmp     [rsi+0FCh], edi
0x18000bac4  cmovnz  r14d, edi
0x18000bac8  mov     r12d, 1
0x18000bace  mov     rax, [rsp+108h+var_C8]
0x18000bad3  mov     [rax], r14d
0x18000bad6  test    r13, r13
0x18000bad9  jz      short loc_18000BAE4
0x18000badb  mov     rcx, r13; lpBaseAddress
0x18000bade  call    cs:__imp_UnmapViewOfFile
0x18000bae4  test    rsi, rsi
0x18000bae7  jz      short loc_18000BAFD
0x18000bae9  call    cs:__imp_GetProcessHeap
0x18000baef  mov     rcx, rax; hHeap
0x18000baf2  mov     r8, rsi; lpMem
0x18000baf5  xor     edx, edx; dwFlags
0x18000baf7  call    cs:__imp_HeapFree
0x18000bafd  lea     rax, [rbx-1]
0x18000bb01  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bb05  ja      short loc_18000BB10
0x18000bb07  mov     rcx, rbx; hObject
0x18000bb0a  call    cs:__imp_CloseHandle
0x18000bb10  mov     eax, r12d
0x18000bb13  mov     rcx, [rsp+108h+var_38]
0x18000bb1b  xor     rcx, rsp; StackCookie
0x18000bb1e  call    __security_check_cookie
0x18000bb23  lea     r11, [rsp+108h+var_28]
0x18000bb2b  mov     rbx, [r11+40h]
0x18000bb2f  mov     rsi, [r11+48h]
0x18000bb33  mov     rsp, r11
0x18000bb36  pop     r15
0x18000bb38  pop     r14
0x18000bb3a  pop     r13
0x18000bb3c  pop     r12
0x18000bb3e  pop     rdi
0x18000bb3f  retn
0x18001668c  push    rbp
0x18001668e  sub     rsp, 40h
0x180016692  mov     rbp, rdx
0x180016695  mov     rax, [rcx]
0x180016698  xor     ecx, ecx
0x18001669a  cmp     dword ptr [rax], 0C0000006h
0x1800166a0  setz    cl
0x1800166a3  mov     eax, ecx
0x1800166a5  add     rsp, 40h
0x1800166a9  pop     rbp
0x1800166aa  retn
```
