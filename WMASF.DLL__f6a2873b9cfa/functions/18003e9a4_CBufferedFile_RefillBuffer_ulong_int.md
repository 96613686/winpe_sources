# CBufferedFile::RefillBuffer(ulong,int)

- ea: `0x18003e9a4`
- end: `0x18003eb65`
- name: `?RefillBuffer@CBufferedFile@@IEAAJKH@Z`
- size: `449`
- prototype: `signed int __fastcall(const void **this, unsigned int, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e640`
- `0x18003e9a4`
- `0x18003eb70`
- `0x18003ebf0`
- `0x18003ece0`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x18003e3fc`
- `0x18003e5c8`
- `0x18003e9a4`
- `0x18003f2ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003eaf2`
- `KERNEL32!GetLastError` at `0x18003eaf2`
- `KERNEL32!ReadFile` at `0x18003eae8`
- `KERNEL32!ReadFile` at `0x18003eae8`

## pseudocode

```c
signed int __fastcall CBufferedFile::RefillBuffer(const void **this, unsigned int a2, int a3)
{
  unsigned int v6; // esi
  signed int result; // eax
  void *v8; // rax
  const void *v9; // rbp
  int v10; // r8d
  unsigned int v11; // esi
  bool v12; // zf
  unsigned __int64 FilePosition; // rax
  __int64 v14; // rdx
  int v15; // r8d
  const void *v16; // rdx
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  DWORD v19; // r8d
  char *v20; // rdx
  void *v21; // rcx
  DWORD v22; // ecx
  unsigned int v23; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 19) )
    CBufferedFile::CommitBuffer((CBufferedFile *)this);
  if ( a2 > *((_DWORD *)this + 14) )
  {
    v6 = (a2 & 0xFFFF0000) + 0x10000;
    if ( v6 < a2 )
      return -2147467259;
    v8 = operator new[](v6);
    v9 = v8;
    if ( !v8 )
      return -2147024882;
    a2 = (a2 & 0xFFFF0000) + 0x10000;
    memmove_0(v8, this[6], *((unsigned int *)this + 14));
    operator delete((void *)this[6]);
    *((_DWORD *)this + 14) = v6;
    this[6] = v9;
  }
  v10 = *((_DWORD *)this + 15);
  if ( v10 )
  {
    memmove_0(
      (void *)this[6],
      (char *)this[6] + *((unsigned int *)this + 16) + *((unsigned int *)this + 17),
      (unsigned int)(v10 - *((_DWORD *)this + 16) - *((_DWORD *)this + 17)));
    *((_DWORD *)this + 15) -= *((_DWORD *)this + 16) + *((_DWORD *)this + 17);
    v11 = *((_DWORD *)this + 15);
  }
  else
  {
    v11 = 0;
  }
  v12 = *((_DWORD *)this + 6) == 0;
  this[8] = 0;
  if ( !v12 )
  {
    if ( !a3 )
      return 1;
    FilePosition = CBufferedFile::GetFilePosition((CBufferedFile *)this);
    v14 = *((unsigned int *)this + 10);
    v15 = v14 - *((_DWORD *)this + 15);
    v16 = (const void *)(FilePosition + v14 - v11);
    LODWORD(FilePosition) = *((_DWORD *)this + 14);
    this[4] = v16;
    *((_DWORD *)this + 10) = FilePosition + v15;
    *((_DWORD *)this + 15) = FilePosition;
    return 0;
  }
  v17 = CBufferedFile::GetFilePosition((CBufferedFile *)this);
  v18 = *((unsigned int *)this + 15);
  v19 = *((_DWORD *)this + 14) - v18;
  v20 = (char *)this[6] + v18;
  v21 = (void *)this[1];
  this[4] = (const void *)(v17 - v11);
  NumberOfBytesRead = 0;
  if ( ReadFile(v21, v20, v19, &NumberOfBytesRead, 0) )
  {
    v22 = NumberOfBytesRead;
    *((_DWORD *)this + 15) += NumberOfBytesRead;
    v23 = *((_DWORD *)this + 14) - *((_DWORD *)this + 15);
    *((_DWORD *)this + 10) = 0;
    if ( v22 < v23 )
    {
      if ( *((_DWORD *)this + 15) < a2 && !*((_DWORD *)this + 6) && a3 )
      {
        *((_DWORD *)this + 6) = 1;
        return CBufferedFile::RefillBuffer((CBufferedFile *)this, a2, a3);
      }
      *((_DWORD *)this + 6) = 1;
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003e9a4  push    rbx
0x18003e9a6  push    rbp
0x18003e9a7  push    rsi
0x18003e9a8  push    rdi
0x18003e9a9  push    r14
0x18003e9ab  sub     rsp, 40h
0x18003e9af  mov     rax, cs:__security_cookie
0x18003e9b6  xor     rax, rsp
0x18003e9b9  mov     [rsp+68h+var_30], rax
0x18003e9be  cmp     dword ptr [rcx+4Ch], 0
0x18003e9c2  mov     r14d, r8d
0x18003e9c5  mov     edi, edx
0x18003e9c7  mov     rbx, rcx
0x18003e9ca  jz      short loc_18003E9D1
0x18003e9cc  call    ?CommitBuffer@CBufferedFile@@IEAAJXZ; CBufferedFile::CommitBuffer(void)
0x18003e9d1  cmp     edi, [rbx+38h]
0x18003e9d4  jbe     short loc_18003EA2D
0x18003e9d6  mov     esi, edi
0x18003e9d8  and     esi, 0FFFF0000h
0x18003e9de  add     esi, 10000h
0x18003e9e4  cmp     esi, edi
0x18003e9e6  jnb     short loc_18003E9F2
0x18003e9e8  mov     eax, 80004005h
0x18003e9ed  jmp     loc_18003EB4D
0x18003e9f2  mov     ecx, esi; unsigned __int64
0x18003e9f4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e9f9  mov     rbp, rax
0x18003e9fc  test    rax, rax
0x18003e9ff  jnz     short loc_18003EA0B
0x18003ea01  mov     eax, 8007000Eh
0x18003ea06  jmp     loc_18003EB4D
0x18003ea0b  mov     r8d, [rbx+38h]; Size
0x18003ea0f  mov     rcx, rbp; void *
0x18003ea12  mov     rdx, [rbx+30h]; Src
0x18003ea16  mov     edi, esi
0x18003ea18  call    memmove_0
0x18003ea1d  mov     rcx, [rbx+30h]; Block
0x18003ea21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ea26  mov     [rbx+38h], esi
0x18003ea29  mov     [rbx+30h], rbp
0x18003ea2d  mov     r8d, [rbx+3Ch]
0x18003ea31  test    r8d, r8d
0x18003ea34  jz      short loc_18003EA5F
0x18003ea36  mov     eax, [rbx+40h]
0x18003ea39  mov     edx, [rbx+44h]
0x18003ea3c  sub     r8d, eax
0x18003ea3f  mov     rcx, [rbx+30h]; void *
0x18003ea43  sub     r8d, edx; Size
0x18003ea46  add     rax, rcx
0x18003ea49  add     rdx, rax; Src
0x18003ea4c  call    memmove_0
0x18003ea51  mov     eax, [rbx+44h]
0x18003ea54  add     eax, [rbx+40h]
0x18003ea57  sub     [rbx+3Ch], eax
0x18003ea5a  mov     esi, [rbx+3Ch]
0x18003ea5d  jmp     short loc_18003EA61
0x18003ea5f  xor     esi, esi
0x18003ea61  cmp     dword ptr [rbx+18h], 0
0x18003ea65  mov     qword ptr [rbx+40h], 0
0x18003ea6d  jz      short loc_18003EAAF
0x18003ea6f  test    r14d, r14d
0x18003ea72  jz      short loc_18003EAA5
0x18003ea74  mov     rcx, rbx; this
0x18003ea77  call    ?GetFilePosition@CBufferedFile@@IEAA_KXZ; CBufferedFile::GetFilePosition(void)
0x18003ea7c  mov     r8d, [rbx+28h]
0x18003ea80  mov     edx, r8d
0x18003ea83  mov     ecx, esi
0x18003ea85  sub     r8d, [rbx+3Ch]
0x18003ea89  sub     rdx, rcx
0x18003ea8c  add     rdx, rax
0x18003ea8f  mov     eax, [rbx+38h]
0x18003ea92  add     r8d, eax
0x18003ea95  mov     [rbx+20h], rdx
0x18003ea99  mov     [rbx+28h], r8d
0x18003ea9d  mov     [rbx+3Ch], eax
0x18003eaa0  jmp     loc_18003EB4B
0x18003eaa5  mov     eax, 1
0x18003eaaa  jmp     loc_18003EB4D
0x18003eaaf  mov     rcx, rbx; this
0x18003eab2  call    ?GetFilePosition@CBufferedFile@@IEAA_KXZ; CBufferedFile::GetFilePosition(void)
0x18003eab7  mov     edx, [rbx+3Ch]
0x18003eaba  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003eabf  mov     r8d, [rbx+38h]
0x18003eac3  mov     ecx, esi
0x18003eac5  sub     r8d, edx; nNumberOfBytesToRead
0x18003eac8  add     rdx, [rbx+30h]; lpBuffer
0x18003eacc  sub     rax, rcx
0x18003eacf  mov     rcx, [rbx+8]; hFile
0x18003ead3  mov     [rbx+20h], rax
0x18003ead7  mov     [rsp+68h+NumberOfBytesRead], 0
0x18003eadf  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18003eae8  call    cs:__imp_ReadFile
0x18003eaee  test    eax, eax
0x18003eaf0  jnz     short loc_18003EB06
0x18003eaf2  call    cs:__imp_GetLastError
0x18003eaf8  test    eax, eax
0x18003eafa  jle     short loc_18003EB4D
0x18003eafc  movzx   eax, ax
0x18003eaff  or      eax, 80070000h
0x18003eb04  jmp     short loc_18003EB4D
0x18003eb06  mov     ecx, [rsp+68h+NumberOfBytesRead]
0x18003eb0a  add     [rbx+3Ch], ecx
0x18003eb0d  mov     eax, [rbx+38h]
0x18003eb10  sub     eax, [rbx+3Ch]
0x18003eb13  mov     dword ptr [rbx+28h], 0
0x18003eb1a  cmp     ecx, eax
0x18003eb1c  jnb     short loc_18003EB4B
0x18003eb1e  cmp     [rbx+3Ch], edi
0x18003eb21  jnb     short loc_18003EB44
0x18003eb23  cmp     dword ptr [rbx+18h], 0
0x18003eb27  jnz     short loc_18003EB44
0x18003eb29  test    r14d, r14d
0x18003eb2c  jz      short loc_18003EB44
0x18003eb2e  mov     r8d, r14d; int
0x18003eb31  mov     dword ptr [rbx+18h], 1
0x18003eb38  mov     edx, edi; unsigned int
0x18003eb3a  mov     rcx, rbx; this
0x18003eb3d  call    ?RefillBuffer@CBufferedFile@@IEAAJKH@Z; CBufferedFile::RefillBuffer(ulong,int)
0x18003eb42  jmp     short loc_18003EB4D
0x18003eb44  mov     dword ptr [rbx+18h], 1
0x18003eb4b  xor     eax, eax
0x18003eb4d  mov     rcx, [rsp+68h+var_30]
0x18003eb52  xor     rcx, rsp; StackCookie
0x18003eb55  call    __security_check_cookie
0x18003eb5a  add     rsp, 40h
0x18003eb5e  pop     r14
0x18003eb60  pop     rdi
0x18003eb61  pop     rsi
0x18003eb62  pop     rbp
0x18003eb63  pop     rbx
0x18003eb64  retn
```
