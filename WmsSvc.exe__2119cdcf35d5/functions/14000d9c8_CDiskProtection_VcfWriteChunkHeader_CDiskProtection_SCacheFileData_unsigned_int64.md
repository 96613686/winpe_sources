# CDiskProtection::VcfWriteChunkHeader(CDiskProtection::SCacheFileData *,unsigned __int64)

- ea: `0x14000d9c8`
- end: `0x14000dc27`
- name: `?VcfWriteChunkHeader@CDiskProtection@@IEAAJPEAUSCacheFileData@1@_K@Z`
- size: `607`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, struct CDiskProtection::SCacheFileData *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000dc30`

## callees

- `0x14000d9c8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x14000da39`
- `KERNEL32!SetFilePointerEx` at `0x14000da73`
- `KERNEL32!SetFilePointerEx` at `0x14000db38`
- `KERNEL32!SetFilePointerEx` at `0x14000da39`
- `KERNEL32!SetFilePointerEx` at `0x14000da73`
- `KERNEL32!SetFilePointerEx` at `0x14000db38`
- `KERNEL32!WriteFile` at `0x14000db01`
- `KERNEL32!WriteFile` at `0x14000db01`
- `KERNEL32!GetLastError` at `0x14000da43`
- `KERNEL32!GetLastError` at `0x14000da7d`
- `KERNEL32!GetLastError` at `0x14000db0b`
- `KERNEL32!GetLastError` at `0x14000db46`
- `KERNEL32!GetLastError` at `0x14000da43`
- `KERNEL32!GetLastError` at `0x14000da7d`
- `KERNEL32!GetLastError` at `0x14000db0b`
- `KERNEL32!GetLastError` at `0x14000db46`
- `KERNEL32!IsDebuggerPresent` at `0x14000dba1`
- `KERNEL32!IsDebuggerPresent` at `0x14000dba1`

## string_xrefs

- `0x14000db6f`: `CDiskProtection::VcfWriteChunkHeader`

## pseudocode

```c
__int64 __fastcall CDiskProtection::VcfWriteChunkHeader(CDiskProtection *this, HANDLE *a2, __int64 a3)
{
  HANDLE v5; // rcx
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // r13d
  signed int v9; // eax
  int *p_Buffer; // r8
  unsigned int v11; // edx
  int v12; // r9d
  __int64 v13; // rax
  HANDLE v14; // rcx
  signed int v15; // eax
  signed int LastError; // eax
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  unsigned int v19; // [rsp+38h] [rbp-C8h]
  __int64 NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp-B8h] BYREF
  int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v23[127]; // [rsp+54h] [rbp-ACh] BYREF

  Buffer = 0;
  memset_0(v23, 0, sizeof(v23));
  v5 = *a2;
  NewFilePointer.QuadPart = 0;
  LODWORD(NumberOfBytesWritten) = 0;
  if ( SetFilePointerEx(v5, 0, &NewFilePointer, 1u) )
  {
    if ( SetFilePointerEx(*a2, (LARGE_INTEGER)(a3 * *((unsigned int *)a2 + 12)), 0, 0) )
    {
      v23[0] = -572662307;
      p_Buffer = &Buffer;
      Buffer = -808464433;
      v11 = -559038737;
      v12 = 504;
      do
      {
        v13 = (unsigned __int8)(v11 ^ *(_BYTE *)p_Buffer);
        p_Buffer = (int *)((char *)p_Buffer + 1);
        v11 = dword_1400D78D0[v13] ^ (v11 >> 8);
        --v12;
      }
      while ( v12 );
      v14 = *a2;
      v23[125] = v11;
      if ( WriteFile(v14, &Buffer, 0x200u, (LPDWORD)&NumberOfBytesWritten, 0) )
      {
        v7 = 0;
        if ( SetFilePointerEx(*a2, NewFilePointer, 0, 0) )
          return v7;
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v8 = 3392;
      }
      else
      {
        v15 = GetLastError();
        v7 = v15;
        if ( v15 > 0 )
          v7 = (unsigned __int16)v15 | 0x80070000;
        v8 = 3385;
      }
    }
    else
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      v8 = 3370;
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = 3361;
  }
  if ( (v7 & 0x80000000) == 0 )
    v7 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v8,
    L"CDiskProtection::VcfWriteChunkHeader",
    L"CBRAEx",
    L"fSuccess",
    v7);
  if ( IsDebuggerPresent() )
  {
    v19 = v7;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::VcfWriteChunkHeader",
      L"CBRAEx",
      L"fSuccess",
      v19,
      NumberOfBytesWritten);
  }
  else
  {
    v18 = v7;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::VcfWriteChunkHeader",
      L"CBRAEx",
      L"fSuccess",
      v18);
  }
  return v7;
}

```

## disassembly

```asm
0x14000d9c8  mov     [rsp-8+arg_0], rbx
0x14000d9cd  mov     [rsp-8+arg_18], rsi
0x14000d9d2  push    rbp
0x14000d9d3  push    rdi
0x14000d9d4  push    r13
0x14000d9d6  push    r14
0x14000d9d8  push    r15
0x14000d9da  lea     rbp, [rsp-160h]
0x14000d9e2  sub     rsp, 260h
0x14000d9e9  mov     rax, cs:__security_cookie
0x14000d9f0  xor     rax, rsp
0x14000d9f3  mov     [rbp+180h+var_30], rax
0x14000d9fa  mov     rbx, r8
0x14000d9fd  mov     [rsp+280h+Buffer], 0
0x14000da05  mov     rdi, rdx
0x14000da08  lea     rcx, [rsp+280h+var_22C]; void *
0x14000da0d  xor     edx, edx; Val
0x14000da0f  mov     r8d, 1FCh; Size
0x14000da15  call    memset_0
0x14000da1a  mov     rcx, [rdi]; hFile
0x14000da1d  lea     r8, [rsp+280h+NewFilePointer]; lpNewFilePointer
0x14000da22  xor     edx, edx; liDistanceToMove
0x14000da24  mov     qword ptr [rsp+280h+NewFilePointer], 0
0x14000da2d  mov     dword ptr [rsp+280h+NumberOfBytesWritten], 0
0x14000da35  lea     r9d, [rdx+1]; dwMoveMethod
0x14000da39  call    cs:__imp_SetFilePointerEx
0x14000da3f  test    eax, eax
0x14000da41  jnz     short loc_14000DA63
0x14000da43  call    cs:__imp_GetLastError
0x14000da49  mov     ebx, eax
0x14000da4b  test    eax, eax
0x14000da4d  jle     short loc_14000DA58
0x14000da4f  movzx   ebx, ax
0x14000da52  or      ebx, 80070000h
0x14000da58  mov     r13d, 0D21h
0x14000da5e  jmp     loc_14000DB61
0x14000da63  mov     edx, [rdi+30h]
0x14000da66  xor     r9d, r9d; dwMoveMethod
0x14000da69  mov     rcx, [rdi]; hFile
0x14000da6c  xor     r8d, r8d; lpNewFilePointer
0x14000da6f  imul    rdx, rbx; liDistanceToMove
0x14000da73  call    cs:__imp_SetFilePointerEx
0x14000da79  test    eax, eax
0x14000da7b  jnz     short loc_14000DA9D
0x14000da7d  call    cs:__imp_GetLastError
0x14000da83  mov     ebx, eax
0x14000da85  test    eax, eax
0x14000da87  jle     short loc_14000DA92
0x14000da89  movzx   ebx, ax
0x14000da8c  or      ebx, 80070000h
0x14000da92  mov     r13d, 0D2Ah
0x14000da98  jmp     loc_14000DB61
0x14000da9d  mov     [rsp+280h+var_22C], 0DDDDDDDDh
0x14000daa5  lea     r8, [rsp+280h+Buffer]
0x14000daaa  mov     [rsp+280h+Buffer], 0CFCFCFCFh
0x14000dab2  mov     edx, 0DEADBEEFh
0x14000dab7  mov     r9d, 1F8h
0x14000dabd  movzx   ecx, byte ptr [r8]
0x14000dac1  mov     eax, edx
0x14000dac3  xor     rcx, rax
0x14000dac6  shr     edx, 8
0x14000dac9  movzx   eax, cl
0x14000dacc  inc     r8
0x14000dacf  lea     rcx, dword_1400D78D0
0x14000dad6  xor     edx, [rcx+rax*4]
0x14000dad9  add     r9d, 0FFFFFFFFh
0x14000dadd  jnz     short loc_14000DABD
0x14000dadf  mov     rcx, [rdi]; hFile
0x14000dae2  lea     r9, [rsp+280h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000dae7  mov     [rbp+180h+var_38], edx
0x14000daed  mov     r8d, 200h; nNumberOfBytesToWrite
0x14000daf3  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x14000daf8  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x14000db01  call    cs:__imp_WriteFile
0x14000db07  test    eax, eax
0x14000db09  jnz     short loc_14000DB28
0x14000db0b  call    cs:__imp_GetLastError
0x14000db11  mov     ebx, eax
0x14000db13  test    eax, eax
0x14000db15  jle     short loc_14000DB20
0x14000db17  movzx   ebx, ax
0x14000db1a  or      ebx, 80070000h
0x14000db20  mov     r13d, 0D39h
0x14000db26  jmp     short loc_14000DB61
0x14000db28  mov     rdx, qword ptr [rsp+280h+NewFilePointer]; liDistanceToMove
0x14000db2d  xor     r9d, r9d; dwMoveMethod
0x14000db30  mov     rcx, [rdi]; hFile
0x14000db33  xor     r8d, r8d; lpNewFilePointer
0x14000db36  xor     ebx, ebx
0x14000db38  call    cs:__imp_SetFilePointerEx
0x14000db3e  test    eax, eax
0x14000db40  jnz     loc_14000DBFA
0x14000db46  call    cs:__imp_GetLastError
0x14000db4c  mov     ebx, eax
0x14000db4e  test    eax, eax
0x14000db50  jle     short loc_14000DB5B
0x14000db52  movzx   ebx, ax
0x14000db55  or      ebx, 80070000h
0x14000db5b  mov     r13d, 0D40h
0x14000db61  mov     eax, 80004005h
0x14000db66  lea     r15, aCbraex; "CBRAEx"
0x14000db6d  test    ebx, ebx
0x14000db6f  lea     rsi, aCdiskprotectio_166; "CDiskProtection::VcfWriteChunkHeader"
0x14000db76  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000db7d  mov     r9, r15; unsigned __int16 *
0x14000db80  cmovns  ebx, eax
0x14000db83  lea     r14, aFsuccess; "fSuccess"
0x14000db8a  mov     [rsp+280h+var_258], ebx; int
0x14000db8e  mov     r8, rsi; unsigned __int16 *
0x14000db91  mov     edx, r13d; unsigned int
0x14000db94  mov     [rsp+280h+lpOverlapped], r14; unsigned __int16 *
0x14000db99  mov     rcx, rdi; unsigned __int16 *
0x14000db9c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000dba1  call    cs:__imp_IsDebuggerPresent
0x14000dba7  test    eax, eax
0x14000dba9  jz      short loc_14000DBD7
0x14000dbab  mov     [rsp+280h+var_248], ebx
0x14000dbaf  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000dbb6  mov     [rsp+280h+var_250], r14
0x14000dbbb  mov     r9d, r13d
0x14000dbbe  mov     qword ptr [rsp+280h+var_258], r15
0x14000dbc3  mov     r8, rdi
0x14000dbc6  mov     ecx, 2; unsigned __int8
0x14000dbcb  mov     [rsp+280h+lpOverlapped], rsi
0x14000dbd0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000dbd5  jmp     short loc_14000DBFA
0x14000dbd7  mov     dword ptr [rsp+280h+var_250], ebx
0x14000dbdb  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000dbe2  mov     qword ptr [rsp+280h+var_258], r14
0x14000dbe7  mov     r9, rsi
0x14000dbea  mov     r8d, r13d
0x14000dbed  mov     [rsp+280h+lpOverlapped], r15
0x14000dbf2  mov     rdx, rdi
0x14000dbf5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000dbfa  mov     eax, ebx
0x14000dbfc  mov     rcx, [rbp+180h+var_30]
0x14000dc03  xor     rcx, rsp; StackCookie
0x14000dc06  call    __security_check_cookie
0x14000dc0b  lea     r11, [rsp+280h+var_20]
0x14000dc13  mov     rbx, [r11+30h]
0x14000dc17  mov     rsi, [r11+48h]
0x14000dc1b  mov     rsp, r11
0x14000dc1e  pop     r15
0x14000dc20  pop     r14
0x14000dc22  pop     r13
0x14000dc24  pop     rdi
0x14000dc25  pop     rbp
0x14000dc26  retn
```
