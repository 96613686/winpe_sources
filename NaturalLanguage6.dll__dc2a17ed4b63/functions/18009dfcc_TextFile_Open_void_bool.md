# TextFile::Open(void *,bool)

- ea: `0x18009dfcc`
- end: `0x18009e0d0`
- name: `?Open@TextFile@@QEAA_NPEAX_N@Z`
- size: `260`
- prototype: `bool __fastcall(TextFile *__hidden this, HANDLE hFile, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180072a4c`
- `0x18009e0d8`

## callees

- `0x18009dfcc`
- `0x18009e148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e007`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009dffc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18009dffc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009e020`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18009e020`

## pseudocode

```c
char __fastcall TextFile::Open(TextFile *this, HANDLE hFile, char a3)
{
  DWORD FileSize; // eax
  unsigned __int16 *v6; // rdx
  bool v7; // al
  int v8; // r8d
  DWORD FileSizeHigh; // [rsp+38h] [rbp+10h] BYREF

  if ( hFile == (HANDLE)-1LL )
    return 0;
  *(_QWORD *)this = hFile;
  FileSizeHigh = 0;
  FileSize = GetFileSize(hFile, &FileSizeHigh);
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
      return 0;
  }
  else if ( !FileSize && !FileSizeHigh )
  {
    *((_BYTE *)this + 12) = a3;
    goto LABEL_9;
  }
  if ( !SetFilePointer(*(HANDLE *)this, 0, 0, 0) )
  {
    TextFile::RefreshBuffer(this);
    if ( !*((_BYTE *)this + 13) )
    {
      v6 = (unsigned __int16 *)*((_QWORD *)this + 514);
      v7 = *v6 == 0xFEFF;
      *((_BYTE *)this + 12) = v7;
      if ( !v7 )
      {
        v8 = *v6 - 48111;
        if ( *v6 == 48111 )
          v8 = *((unsigned __int8 *)v6 + 2) - 191;
        if ( !v8 )
        {
          *((_DWORD *)this + 2) = 65001;
          *((_QWORD *)this + 514) = (char *)v6 + 3;
        }
        return 1;
      }
      if ( *v6 != 0xFEFF )
        return 1;
      *((_QWORD *)this + 514) = v6 + 1;
      if ( (unsigned __int64)(v6 + 1) < *((_QWORD *)this + 515) )
        return 1;
LABEL_9:
      *((_BYTE *)this + 13) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18009dfcc  mov     [rsp+arg_0], rbx
0x18009dfd1  push    rdi
0x18009dfd2  sub     rsp, 20h
0x18009dfd6  mov     dil, r8b
0x18009dfd9  mov     rax, rdx
0x18009dfdc  mov     rbx, rcx
0x18009dfdf  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18009dfe3  jz      loc_18009E0C3
0x18009dfe9  mov     [rcx], rdx
0x18009dfec  lea     rdx, [rsp+28h+FileSizeHigh]; lpFileSizeHigh
0x18009dff1  mov     rcx, rax; hFile
0x18009dff4  mov     [rsp+28h+FileSizeHigh], 0
0x18009dffc  call    cs:__imp_GetFileSize
0x18009e002  cmp     eax, 0FFFFFFFFh
0x18009e005  jnz     short loc_18009E079
0x18009e007  call    cs:__imp_GetLastError
0x18009e00d  test    eax, eax
0x18009e00f  jnz     loc_18009E0C3
0x18009e015  mov     rcx, [rbx]; hFile
0x18009e018  xor     r9d, r9d; dwMoveMethod
0x18009e01b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009e01e  xor     edx, edx; lDistanceToMove
0x18009e020  call    cs:__imp_SetFilePointer
0x18009e026  test    eax, eax
0x18009e028  jnz     loc_18009E0C3
0x18009e02e  mov     rcx, rbx; this
0x18009e031  call    ?RefreshBuffer@TextFile@@AEAAXXZ; TextFile::RefreshBuffer(void)
0x18009e036  cmp     byte ptr [rbx+0Dh], 0
0x18009e03a  jnz     loc_18009E0C3
0x18009e040  mov     rdx, [rbx+1010h]
0x18009e047  mov     r8d, 0FEFFh
0x18009e04d  cmp     [rdx], r8w
0x18009e051  setz    al
0x18009e054  mov     [rbx+0Ch], al
0x18009e057  jnz     short loc_18009E089
0x18009e059  cmp     [rdx], r8w
0x18009e05d  jnz     short loc_18009E0BF
0x18009e05f  lea     rax, [rdx+2]
0x18009e063  mov     [rbx+1010h], rax
0x18009e06a  cmp     rax, [rbx+1018h]
0x18009e071  jb      short loc_18009E0BF
0x18009e073  mov     byte ptr [rbx+0Dh], 1
0x18009e077  jmp     short loc_18009E0BF
0x18009e079  test    eax, eax
0x18009e07b  jnz     short loc_18009E015
0x18009e07d  cmp     [rsp+28h+FileSizeHigh], eax
0x18009e081  jnz     short loc_18009E015
0x18009e083  mov     [rbx+0Ch], dil
0x18009e087  jmp     short loc_18009E073
0x18009e089  movzx   r8d, word ptr [rdx]
0x18009e08d  movzx   eax, cs:word_1800C781C
0x18009e094  sub     r8d, eax
0x18009e097  jnz     short loc_18009E0A8
0x18009e099  movzx   r8d, byte ptr [rdx+2]
0x18009e09e  movzx   ecx, cs:byte_1800C781E
0x18009e0a5  sub     r8d, ecx
0x18009e0a8  test    r8d, r8d
0x18009e0ab  jnz     short loc_18009E0BF
0x18009e0ad  lea     rcx, [rdx+3]
0x18009e0b1  mov     dword ptr [rbx+8], 0FDE9h
0x18009e0b8  mov     [rbx+1010h], rcx
0x18009e0bf  mov     al, 1
0x18009e0c1  jmp     short loc_18009E0C5
0x18009e0c3  xor     al, al
0x18009e0c5  mov     rbx, [rsp+28h+arg_0]
0x18009e0ca  add     rsp, 20h
0x18009e0ce  pop     rdi
0x18009e0cf  retn
```
