# CSmsConcatenateStore::UpdateFileHeader(void)

- ea: `0x180061f54`
- end: `0x18006207b`
- name: `?UpdateFileHeader@CSmsConcatenateStore@@AEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CSmsConcatenateStore *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180060dbc`
- `0x18006133c`
- `0x180061618`

## callees

- `0x180061f54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ffb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061ff0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180062043`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061ff0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180062043`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062055`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062055`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006202a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006202a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsConcatenateStore::UpdateFileHeader(CSmsConcatenateStore *this)
{
  void *v1; // r10
  unsigned int v2; // ebx
  __int64 v4; // r8
  unsigned int v5; // esi
  __int64 v6; // rcx
  signed int LastError; // eax
  int Buffer; // [rsp+40h] [rbp+8h] BYREF
  int v10; // [rsp+44h] [rbp+Ch]

  v1 = (void *)*((_QWORD *)this + 16);
  v2 = 0;
  if ( v1 != (void *)-1LL )
  {
    v4 = *((_QWORD *)this + 13);
    v5 = 664 * *((_DWORD *)this + 34) + 8;
    v6 = (*((_QWORD *)this + 14) - v4) >> 4;
    while ( 1 )
    {
      LODWORD(v6) = v6 - 1;
      if ( (int)v6 < 0 || v5 <= 8 || v5 - 664 != *(_DWORD *)(*(_QWORD *)(v4 + 16LL * (unsigned int)v6) + 8LL) )
        break;
      v5 -= 664;
    }
    Buffer = -2023476720;
    if ( v5 <= 8 )
      v10 = 0;
    else
      v10 = ((unsigned __int64)v5 - 8) / 0x298;
    if ( SetFilePointer(v1, 0, 0, 0) == -1
      || !WriteFile(*((HANDLE *)this + 16), &Buffer, 8u, 0, 0)
      || SetFilePointer(*((HANDLE *)this + 16), v5, 0, 0) == -1
      || !SetEndOfFile(*((HANDLE *)this + 16)) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      *((_DWORD *)this + 34) = v10;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180061f54  mov     [rsp+arg_8], rbx
0x180061f59  mov     [rsp+arg_10], rsi
0x180061f5e  push    rdi
0x180061f5f  sub     rsp, 30h
0x180061f63  mov     r10, [rcx+80h]
0x180061f6a  xor     ebx, ebx
0x180061f6c  mov     rdi, rcx
0x180061f6f  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180061f73  jz      loc_180062069
0x180061f79  imul    esi, [rcx+88h], 298h
0x180061f83  mov     r8, [rcx+68h]
0x180061f87  mov     rcx, [rcx+70h]
0x180061f8b  sub     rcx, r8
0x180061f8e  add     esi, 8
0x180061f91  sar     rcx, 4
0x180061f95  jmp     short loc_180061FB2
0x180061f97  cmp     esi, 8
0x180061f9a  jbe     short loc_180061FB7
0x180061f9c  mov     eax, ecx
0x180061f9e  lea     edx, [rsi-298h]
0x180061fa4  add     rax, rax
0x180061fa7  mov     rax, [r8+rax*8]
0x180061fab  cmp     edx, [rax+8]
0x180061fae  jnz     short loc_180061FB7
0x180061fb0  mov     esi, edx
0x180061fb2  sub     ecx, 1
0x180061fb5  jns     short loc_180061F97
0x180061fb7  mov     [rsp+38h+Buffer], 87643210h
0x180061fbf  cmp     esi, 8
0x180061fc2  jbe     short loc_180061FE1
0x180061fc4  mov     ecx, esi
0x180061fc6  mov     rax, 3159721ED7E75347h
0x180061fd0  sub     rcx, 8
0x180061fd4  mul     rcx
0x180061fd7  shr     rdx, 7
0x180061fdb  mov     [rsp+38h+arg_4], edx
0x180061fdf  jmp     short loc_180061FE5
0x180061fe1  mov     [rsp+38h+arg_4], ebx
0x180061fe5  xor     r9d, r9d; dwMoveMethod
0x180061fe8  xor     r8d, r8d; lpDistanceToMoveHigh
0x180061feb  xor     edx, edx; lDistanceToMove
0x180061fed  mov     rcx, r10; hFile
0x180061ff0  call    cs:__imp_SetFilePointer
0x180061ff6  cmp     eax, 0FFFFFFFFh
0x180061ff9  jnz     short loc_180062012
0x180061ffb  call    cs:__imp_GetLastError
0x180062001  mov     ebx, eax
0x180062003  test    eax, eax
0x180062005  jle     short loc_180062069
0x180062007  movzx   ebx, ax
0x18006200a  or      ebx, 80070000h
0x180062010  jmp     short loc_180062069
0x180062012  mov     rcx, [rdi+80h]; hFile
0x180062019  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18006201e  xor     r9d, r9d; lpNumberOfBytesWritten
0x180062021  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x180062026  lea     r8d, [r9+8]; nNumberOfBytesToWrite
0x18006202a  call    cs:__imp_WriteFile
0x180062030  test    eax, eax
0x180062032  jz      short loc_180061FFB
0x180062034  mov     rcx, [rdi+80h]; hFile
0x18006203b  xor     r9d, r9d; dwMoveMethod
0x18006203e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180062041  mov     edx, esi; lDistanceToMove
0x180062043  call    cs:__imp_SetFilePointer
0x180062049  cmp     eax, 0FFFFFFFFh
0x18006204c  jz      short loc_180061FFB
0x18006204e  mov     rcx, [rdi+80h]; hFile
0x180062055  call    cs:__imp_SetEndOfFile
0x18006205b  test    eax, eax
0x18006205d  jz      short loc_180061FFB
0x18006205f  mov     ecx, [rsp+38h+arg_4]
0x180062063  mov     [rdi+88h], ecx
0x180062069  mov     rsi, [rsp+38h+arg_10]
0x18006206e  mov     eax, ebx
0x180062070  mov     rbx, [rsp+38h+arg_8]
0x180062075  add     rsp, 30h
0x180062079  pop     rdi
0x18006207a  retn
```
