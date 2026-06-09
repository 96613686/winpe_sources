# CreateFinalTiffFile(ushort const *,ushort *,ulong,void *)

- ea: `0x180016de4`
- end: `0x180016fcb`
- name: `?CreateFinalTiffFile@@YAHPEBGPEAGKPEAX@Z`
- size: `487`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001a82c`

## callees

- `0x180008438`
- `0x18000abe4`
- `0x180016de4`
- `0x18001a7a0`
- `0x18002bb58`
- `0x180038190`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180016e75`
- `KERNEL32!GetTempPath2W` at `0x180016e75`
- `KERNEL32!GetTempFileNameW` at `0x180016eb0`
- `KERNEL32!GetTempFileNameW` at `0x180016eb0`
- `KERNEL32!GetFullPathNameW` at `0x180016ed6`
- `KERNEL32!GetFullPathNameW` at `0x180016ed6`
- `KERNEL32!DeleteFileW` at `0x180016f12`
- `KERNEL32!DeleteFileW` at `0x180016f68`
- `KERNEL32!DeleteFileW` at `0x180016f12`
- `KERNEL32!DeleteFileW` at `0x180016f68`
- `KERNEL32!SetLastError` at `0x180016f8f`
- `KERNEL32!SetLastError` at `0x180016f8f`
- `KERNEL32!GetLastError` at `0x180016e85`
- `KERNEL32!GetLastError` at `0x180016eff`
- `KERNEL32!GetLastError` at `0x180016e85`
- `KERNEL32!GetLastError` at `0x180016eff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateFinalTiffFile(const unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, void *a4)
{
  unsigned __int16 *v7; // rdi
  DWORD LastError; // ebx
  DWORD FullPathNameW; // ebx
  unsigned __int16 *FaxPrinterName; // rax
  int v11; // eax
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR TempFileName[264]; // [rsp+450h] [rbp+350h] BYREF

  memset_0(PathName, 0, 0x208u);
  v7 = 0;
  FilePart = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  if ( !(unsigned int)GetTempPath2W(260, PathName) || !GetTempFileNameW(PathName, L"fax", 0, TempFileName) )
    goto LABEL_6;
  FullPathNameW = GetFullPathNameW(TempFileName, 0x104u, Buffer, &FilePart);
  if ( FullPathNameW - 1 > 0x103 )
  {
    DeleteFileW(PathName);
    if ( FullPathNameW )
    {
      LastError = 111;
      goto LABEL_18;
    }
LABEL_6:
    LastError = GetLastError();
    goto LABEL_18;
  }
  FaxPrinterName = GetFaxPrinterName(a4);
  v7 = FaxPrinterName;
  if ( FaxPrinterName && (unsigned int)PrintRandomDocumentEx(FaxPrinterName, a1, Buffer) )
  {
    v11 = StringCchCopyW(a2, 0x104u, Buffer);
    LastError = v11;
    if ( v11 >= 0 )
    {
      LastError = 0;
    }
    else if ( (v11 & 0x1FFF0000) == 0x70000 )
    {
      LastError = (unsigned __int16)v11;
    }
  }
  else
  {
    LastError = GetLastError();
    DeleteFileW(Buffer);
  }
LABEL_18:
  pMemFree(v7);
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x180016de4  mov     [rsp-8+arg_10], rbx
0x180016de9  push    rbp
0x180016dea  push    rsi
0x180016deb  push    rdi
0x180016dec  push    r14
0x180016dee  push    r15
0x180016df0  lea     rbp, [rsp-570h]
0x180016df8  sub     rsp, 670h
0x180016dff  mov     rax, cs:__security_cookie
0x180016e06  xor     rax, rsp
0x180016e09  mov     [rbp+590h+var_30], rax
0x180016e10  mov     r15, rdx
0x180016e13  mov     r14, rcx
0x180016e16  xor     edx, edx; Val
0x180016e18  lea     rcx, [rbp+590h+PathName]; void *
0x180016e1f  mov     r8d, 208h; Size
0x180016e25  mov     rsi, r9
0x180016e28  call    memset_0
0x180016e2d  xor     edi, edi
0x180016e2f  mov     [rsp+690h+FilePart], rdi
0x180016e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e3b  lea     rax, WPP_GLOBAL_Control
0x180016e42  cmp     rcx, rax
0x180016e45  jz      short loc_180016E69
0x180016e47  test    dword ptr [rcx+1Ch], 1000h
0x180016e4e  jz      short loc_180016E69
0x180016e50  cmp     byte ptr [rcx+19h], 5
0x180016e54  jb      short loc_180016E69
0x180016e56  mov     rcx, [rcx+10h]
0x180016e5a  lea     edx, [rdi+0Ah]
0x180016e5d  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016e64  call    WPP_SF_
0x180016e69  lea     rdx, [rbp+590h+PathName]
0x180016e70  mov     ecx, 104h
0x180016e75  call    cs:__imp_GetTempPath2W
0x180016e7c  nop     dword ptr [rax+rax+00h]
0x180016e81  test    eax, eax
0x180016e83  jnz     short loc_180016E98
0x180016e85  call    cs:__imp_GetLastError
0x180016e8c  nop     dword ptr [rax+rax+00h]
0x180016e91  mov     ebx, eax
0x180016e93  jmp     loc_180016F81
0x180016e98  lea     r9, [rbp+590h+TempFileName]; lpTempFileName
0x180016e9f  xor     r8d, r8d; uUnique
0x180016ea2  lea     rdx, PrefixString; "fax"
0x180016ea9  lea     rcx, [rbp+590h+PathName]; lpPathName
0x180016eb0  call    cs:__imp_GetTempFileNameW
0x180016eb7  nop     dword ptr [rax+rax+00h]
0x180016ebc  test    eax, eax
0x180016ebe  jz      short loc_180016E85
0x180016ec0  lea     r9, [rsp+690h+FilePart]; lpFilePart
0x180016ec5  mov     edx, 104h; nBufferLength
0x180016eca  lea     r8, [rsp+690h+Buffer]; lpBuffer
0x180016ecf  lea     rcx, [rbp+590h+TempFileName]; lpFileName
0x180016ed6  call    cs:__imp_GetFullPathNameW
0x180016edd  nop     dword ptr [rax+rax+00h]
0x180016ee2  mov     ebx, eax
0x180016ee4  lea     ecx, [rax-1]
0x180016ee7  cmp     ecx, 103h
0x180016eed  ja      short loc_180016F61
0x180016eef  mov     rcx, rsi; void *
0x180016ef2  call    ?GetFaxPrinterName@@YAPEAGPEAX@Z; GetFaxPrinterName(void *)
0x180016ef7  mov     rdi, rax
0x180016efa  test    rax, rax
0x180016efd  jnz     short loc_180016F20
0x180016eff  call    cs:__imp_GetLastError
0x180016f06  nop     dword ptr [rax+rax+00h]
0x180016f0b  lea     rcx, [rsp+690h+Buffer]; lpFileName
0x180016f10  mov     ebx, eax
0x180016f12  call    cs:__imp_DeleteFileW
0x180016f19  nop     dword ptr [rax+rax+00h]
0x180016f1e  jmp     short loc_180016F81
0x180016f20  lea     r8, [rsp+690h+Buffer]
0x180016f25  mov     rdx, r14
0x180016f28  mov     rcx, rax
0x180016f2b  call    PrintRandomDocumentEx
0x180016f30  test    eax, eax
0x180016f32  jz      short loc_180016EFF
0x180016f34  lea     r8, [rsp+690h+Buffer]; unsigned __int16 *
0x180016f39  mov     edx, 104h; unsigned __int64
0x180016f3e  mov     rcx, r15; unsigned __int16 *
0x180016f41  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016f46  mov     ebx, eax
0x180016f48  test    eax, eax
0x180016f4a  jns     short loc_180016F5D
0x180016f4c  and     eax, 1FFF0000h
0x180016f51  cmp     eax, 70000h
0x180016f56  jnz     short loc_180016F81
0x180016f58  movzx   ebx, bx
0x180016f5b  jmp     short loc_180016F81
0x180016f5d  xor     ebx, ebx
0x180016f5f  jmp     short loc_180016F81
0x180016f61  lea     rcx, [rbp+590h+PathName]; lpFileName
0x180016f68  call    cs:__imp_DeleteFileW
0x180016f6f  nop     dword ptr [rax+rax+00h]
0x180016f74  test    ebx, ebx
0x180016f76  jz      loc_180016E85
0x180016f7c  mov     ebx, 6Fh ; 'o'
0x180016f81  mov     rcx, rdi; lpMem
0x180016f84  call    pMemFree
0x180016f89  test    ebx, ebx
0x180016f8b  jz      short loc_180016F9F
0x180016f8d  mov     ecx, ebx; dwErrCode
0x180016f8f  call    cs:__imp_SetLastError
0x180016f96  nop     dword ptr [rax+rax+00h]
0x180016f9b  xor     eax, eax
0x180016f9d  jmp     short loc_180016FA4
0x180016f9f  mov     eax, 1
0x180016fa4  mov     rcx, [rbp+590h+var_30]
0x180016fab  xor     rcx, rsp; StackCookie
0x180016fae  call    __security_check_cookie
0x180016fb3  mov     rbx, [rsp+690h+arg_10]
0x180016fbb  add     rsp, 670h
0x180016fc2  pop     r15
0x180016fc4  pop     r14
0x180016fc6  pop     rdi
0x180016fc7  pop     rsi
0x180016fc8  pop     rbp
0x180016fc9  retn
```
