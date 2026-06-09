# UDRTrie::CheckForRead(void)

- ea: `0x180071ce0`
- end: `0x180071ede`
- name: `?CheckForRead@UDRTrie@@AEAAXXZ`
- size: `510`
- prototype: `void __fastcall(UDRTrie *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180073ac8`
- `0x180073ba0`

## callees

- `0x180035640`
- `0x18003ed6c`
- `0x180071ce0`
- `0x180072a4c`
- `0x180073dd8`
- `0x180073e0c`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ecd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180071d6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180071d6d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180071ddf`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180071ddf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall UDRTrie::CheckForRead(UDRTrie *this)
{
  const WCHAR *v2; // rcx
  __int64 v3; // rax
  char *FileW; // rax
  void *v5; // rax
  bool v6; // dl
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-108h] BYREF
  _BYTE v9[64]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v10[64]; // [rsp+E0h] [rbp-88h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+120h] [rbp-48h] BYREF
  const void *retaddr; // [rsp+168h] [rbp+0h]

  v2 = (const WCHAR *)((char *)this + 36);
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  if ( v3 && !*((_BYTE *)this + 1098) )
  {
    if ( ((*((_QWORD *)this + 133) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      FileW = (char *)CreateFileW(v2, 0xC0000000, 0, 0, 3u, 0x80u, 0);
      *((_QWORD *)this + 133) = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 3241213976LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
    }
    try
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      if ( !GetFileInformationByHandle(*((HANDLE *)this + 133), &FileInformation) )
      {
        CNLException::CNLException((CNLException *)v9, 3241213974LL, retaddr);
        throw (CNLException *)v9;
      }
      if ( *(_QWORD *)((char *)this + 28) >= *(_QWORD *)&FileInformation.ftLastWriteTime )
      {
        CloseHandle(*((HANDLE *)this + 133));
        *((_QWORD *)this + 133) = 0;
      }
      else
      {
        UDRTrie::UDictDestroy(*((void **)this + 136));
        *((_DWORD *)this + 271) = 0;
        v5 = UDRTrie::UDictCreate();
        *((_QWORD *)this + 136) = v5;
        if ( !v5 )
        {
          CNLException::CNLException((CNLException *)v10, 2147942414LL, retaddr);
          throw (CNLException *)v10;
        }
        UDRTrie::LoadFromFile(this, v6);
      }
    }
    catch ( ... )
    {
      ImxTraceCatch(3, 3134570718LL, retaddr);
      CloseHandle(*((HANDLE *)this + 133));
      *((_QWORD *)this + 133) = 0;
      throw;
    }
  }
}

```

## disassembly

```asm
0x180071ce0  mov     rax, rsp
0x180071ce3  push    rdi
0x180071ce4  sub     rsp, 160h
0x180071ceb  mov     [rsp+168h+var_120], 0FFFFFFFFFFFFFFFEh
0x180071cf4  mov     [rax+10h], rbx
0x180071cf8  mov     rax, cs:__security_cookie
0x180071cff  xor     rax, rsp
0x180071d02  mov     [rsp+168h+var_10], rax
0x180071d0a  mov     rbx, rcx
0x180071d0d  mov     [rsp+168h+var_128], rcx
0x180071d12  add     rcx, 24h ; '$'; lpFileName
0x180071d16  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071d1a  xor     edi, edi
0x180071d1c  inc     rax
0x180071d1f  cmp     [rcx+rax*2], di
0x180071d23  jnz     short loc_180071D1C
0x180071d25  test    rax, rax
0x180071d28  jz      loc_180071EA5
0x180071d2e  cmp     [rbx+44Ah], dil
0x180071d35  jnz     loc_180071EA5
0x180071d3b  mov     rax, [rbx+428h]
0x180071d42  inc     rax
0x180071d45  test    rax, 0FFFFFFFFFFFFFFFEh
0x180071d4b  jnz     short loc_180071DAC
0x180071d4d  mov     [rsp+168h+hTemplateFile], rdi; hTemplateFile
0x180071d52  mov     [rsp+168h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180071d5a  mov     [rsp+168h+dwCreationDisposition], 3; dwCreationDisposition
0x180071d62  xor     r9d, r9d; lpSecurityAttributes
0x180071d65  xor     r8d, r8d; dwShareMode
0x180071d68  mov     edx, 0C0000000h; dwDesiredAccess
0x180071d6d  call    cs:__imp_CreateFileW
0x180071d73  mov     [rbx+428h], rax
0x180071d7a  dec     rax
0x180071d7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180071d81  jbe     short loc_180071DAC
0x180071d83  mov     r8, [rsp+168h]; void *
0x180071d8b  mov     edx, 0C1310018h; int
0x180071d90  lea     rcx, [rsp+168h+pExceptionObject]; this
0x180071d95  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180071d9a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180071da1  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180071da6  call    _CxxThrowException_0
0x180071dac  xorps   xmm0, xmm0
0x180071daf  xor     eax, eax
0x180071db1  movups  xmmword ptr [rsp+168h+FileInformation.dwFileAttributes], xmm0
0x180071db9  movups  xmmword ptr [rsp+168h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180071dc1  movups  xmmword ptr [rsp+168h+FileInformation.nFileSizeHigh], xmm0
0x180071dc9  mov     [rsp+168h+FileInformation.nFileIndexLow], eax
0x180071dd0  lea     rdx, [rsp+168h+FileInformation]; lpFileInformation
0x180071dd8  mov     rcx, [rbx+428h]; hFile
0x180071ddf  call    cs:__imp_GetFileInformationByHandle
0x180071de5  test    eax, eax
0x180071de7  jnz     short loc_180071E17
0x180071de9  mov     r8, [rsp+168h]; void *
0x180071df1  mov     edx, 0C1310016h; int
0x180071df6  lea     rcx, [rsp+168h+var_C8]; this
0x180071dfe  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180071e03  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180071e0a  lea     rcx, [rsp+168h+var_C8]; pExceptionObject
0x180071e12  call    _CxxThrowException_0
0x180071e17  mov     rcx, [rbx+1Ch]
0x180071e1b  mov     [rsp+168h+var_118], rcx
0x180071e20  mov     rax, qword ptr [rsp+168h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180071e28  mov     [rsp+168h+var_110], rax
0x180071e2d  mov     rdx, rcx
0x180071e30  shr     rdx, 20h
0x180071e34  shr     rax, 20h
0x180071e38  cmp     edx, eax
0x180071e3a  ja      loc_180071EC6
0x180071e40  jnz     short loc_180071E4B
0x180071e42  cmp     ecx, [rsp+168h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180071e49  jnb     short loc_180071EC6
0x180071e4b  mov     rcx, [rbx+440h]; Block
0x180071e52  call    ?UDictDestroy@UDRTrie@@CAHPEAX@Z; UDRTrie::UDictDestroy(void *)
0x180071e57  mov     [rbx+43Ch], edi
0x180071e5d  call    ?UDictCreate@UDRTrie@@CAPEAXXZ; UDRTrie::UDictCreate(void)
0x180071e62  mov     [rbx+440h], rax
0x180071e69  test    rax, rax
0x180071e6c  jnz     short loc_180071E9C
0x180071e6e  mov     r8, [rsp+168h]; void *
0x180071e76  mov     edx, 8007000Eh; int
0x180071e7b  lea     rcx, [rsp+168h+var_88]; this
0x180071e83  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180071e88  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180071e8f  lea     rcx, [rsp+168h+var_88]; pExceptionObject
0x180071e97  call    _CxxThrowException_0
0x180071e9c  mov     rcx, rbx; this
0x180071e9f  call    ?LoadFromFile@UDRTrie@@QEAAX_N@Z; UDRTrie::LoadFromFile(bool)
0x180071ea4  nop
0x180071ea5  mov     rcx, [rsp+168h+var_10]
0x180071ead  xor     rcx, rsp; StackCookie
0x180071eb0  call    __security_check_cookie
0x180071eb5  mov     rbx, [rsp+168h+arg_8]
0x180071ebd  add     rsp, 160h
0x180071ec4  pop     rdi
0x180071ec5  retn
0x180071ec6  mov     rcx, [rbx+428h]; hObject
0x180071ecd  call    cs:__imp_CloseHandle
0x180071ed3  mov     [rbx+428h], rdi
0x180071eda  jmp     short loc_180071EA5
```
