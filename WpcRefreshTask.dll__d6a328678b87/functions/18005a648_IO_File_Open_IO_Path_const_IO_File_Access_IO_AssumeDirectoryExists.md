# IO::File::Open(IO::Path const &,IO::File::Access,IO::AssumeDirectoryExists)

- ea: `0x18005a648`
- end: `0x18005a7f0`
- name: `?Open@File@IO@@YA?AV?$unique_ptr@XUHandleClose@Private@@@std@@AEBVPath@2@W4Access@12@UAssumeDirectoryExists@2@@Z`
- size: `424`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800670c8`
- `0x180096030`
- `0x18009ec5c`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000e93c`
- `0x18000fef0`
- `0x180035af4`
- `0x180035e0c`
- `0x180059820`
- `0x18005a1f4`
- `0x18005a648`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a6d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a6d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall IO::File::Open(_QWORD *a1, const WCHAR *a2, int a3)
{
  DWORD v5; // edx
  DWORD v6; // eax
  DWORD dwCreationDisposition; // r8d
  const WCHAR *v8; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r10
  _BYTE pExceptionObject[80]; // [rsp+50h] [rbp-68h] BYREF

  if ( a3 )
  {
    v6 = 0;
    if ( a3 == 1 )
    {
      v5 = 0x40000000;
    }
    else
    {
      v5 = -1073741824;
      if ( a3 != 2 )
        goto LABEL_9;
    }
    dwCreationDisposition = 4;
    goto LABEL_6;
  }
  v5 = 0x80000000;
  v6 = 1;
LABEL_9:
  dwCreationDisposition = 3;
LABEL_6:
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v8 = a2;
  else
    v8 = *(const WCHAR **)a2;
  FileW = CreateFileW(v8, v5, v6, 0, dwCreationDisposition, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = std::array<unsigned short,16>::data(a2);
        v14 = std::wstring::c_str(v13);
        WPP_SF_Sd(*(_QWORD *)(v15 + 16), 11, (unsigned int)WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v14, v11);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
      throw (ErrorCodeException *)pExceptionObject;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v16 = std::array<unsigned short,16>::data(a2);
      v17 = std::wstring::c_str(v16);
      WPP_SF_S(*(_QWORD *)(v18 + 16), 10, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v17);
    }
    IO::FileNotFoundException::FileNotFoundException(
      (IO::FileNotFoundException *)pExceptionObject,
      (const struct Path *)a2);
    throw (IO::FileNotFoundException *)pExceptionObject;
  }
  *a1 = FileW;
  return a1;
}

```

## disassembly

```asm
0x18005a648  mov     [rsp+arg_10], rbx
0x18005a64d  push    rdi
0x18005a64e  sub     rsp, 0B0h
0x18005a655  mov     rax, cs:__security_cookie
0x18005a65c  xor     rax, rsp
0x18005a65f  mov     [rsp+0B8h+var_18], rax
0x18005a667  mov     rdi, rdx
0x18005a66a  mov     rbx, rcx
0x18005a66d  mov     [rsp+0B8h+var_70], rcx
0x18005a672  test    r8d, r8d
0x18005a675  jnz     short loc_18005A682
0x18005a677  mov     edx, 80000000h
0x18005a67c  lea     eax, [r8+1]
0x18005a680  jmp     short loc_18005A6AC
0x18005a682  xor     eax, eax
0x18005a684  cmp     r8d, 1
0x18005a688  jnz     short loc_18005A6A1
0x18005a68a  mov     edx, 40000000h; dwDesiredAccess
0x18005a68f  mov     r8d, 4
0x18005a695  cmp     qword ptr [rdi+18h], 7
0x18005a69a  jbe     short loc_18005A6B4
0x18005a69c  mov     rcx, [rdi]
0x18005a69f  jmp     short loc_18005A6B7
0x18005a6a1  mov     edx, 0C0000000h
0x18005a6a6  cmp     r8d, 2
0x18005a6aa  jz      short loc_18005A68F
0x18005a6ac  mov     r8d, 3
0x18005a6b2  jmp     short loc_18005A695
0x18005a6b4  mov     rcx, rdi; lpFileName
0x18005a6b7  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x18005a6c0  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005a6c8  mov     [rsp+0B8h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005a6cd  xor     r9d, r9d; lpSecurityAttributes
0x18005a6d0  mov     r8d, eax; dwShareMode
0x18005a6d3  call    cs:__imp_CreateFileW
0x18005a6d9  mov     [rsp+0B8h+var_70], rax
0x18005a6de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005a6e2  jnz     short loc_18005A6F7
0x18005a6e4  call    cs:__imp_GetLastError
0x18005a6ea  mov     ebx, eax
0x18005a6ec  cmp     eax, 2
0x18005a6ef  jz      loc_18005A78F
0x18005a6f5  jmp     short loc_18005A71E
0x18005a6f7  mov     [rbx], rax
0x18005a6fa  mov     rax, rbx
0x18005a6fd  mov     rcx, [rsp+0B8h+var_18]
0x18005a705  xor     rcx, rsp; StackCookie
0x18005a708  call    __security_check_cookie
0x18005a70d  mov     rbx, [rsp+0B8h+arg_10]
0x18005a715  add     rsp, 0B0h
0x18005a71c  pop     rdi
0x18005a71d  retn
0x18005a71e  test    eax, eax
0x18005a720  jle     short loc_18005A72B
0x18005a722  movzx   ebx, ax
0x18005a725  or      ebx, 80070000h
0x18005a72b  lea     rax, WPP_GLOBAL_Control
0x18005a732  mov     r10, cs:WPP_GLOBAL_Control
0x18005a739  cmp     r10, rax
0x18005a73c  jz      short loc_18005A771
0x18005a73e  test    byte ptr [r10+1Ch], 1
0x18005a743  jz      short loc_18005A771
0x18005a745  mov     rcx, rdi
0x18005a748  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x18005a74d  mov     rcx, rax
0x18005a750  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005a755  mov     edx, 0Bh
0x18005a75a  mov     [rsp+0B8h+dwCreationDisposition], ebx
0x18005a75e  mov     r9, rax
0x18005a761  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x18005a768  mov     rcx, [r10+10h]
0x18005a76c  call    WPP_SF_Sd
0x18005a771  mov     edx, ebx; int
0x18005a773  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x18005a778  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005a77d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18005a784  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18005a789  call    _CxxThrowException_0
0x18005a78f  lea     rax, WPP_GLOBAL_Control
0x18005a796  mov     r10, cs:WPP_GLOBAL_Control
0x18005a79d  cmp     r10, rax
0x18005a7a0  jz      short loc_18005A7D1
0x18005a7a2  test    byte ptr [r10+1Ch], 1
0x18005a7a7  jz      short loc_18005A7D1
0x18005a7a9  mov     rcx, rdi
0x18005a7ac  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x18005a7b1  mov     rcx, rax
0x18005a7b4  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005a7b9  mov     edx, 0Ah
0x18005a7be  mov     r9, rax
0x18005a7c1  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x18005a7c8  mov     rcx, [r10+10h]
0x18005a7cc  call    WPP_SF_S
0x18005a7d1  mov     rdx, rdi; struct Path *
0x18005a7d4  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x18005a7d9  call    ??0FileNotFoundException@IO@@QEAA@AEBVPath@1@@Z; IO::FileNotFoundException::FileNotFoundException(IO::Path const &)
0x18005a7de  lea     rdx, _TI4?AUFileNotFoundException@IO@@; pThrowInfo
0x18005a7e5  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18005a7ea  call    _CxxThrowException_0
```
