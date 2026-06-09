# __EHM_FlatFileWrite(void *,ushort const *,unsigned __int64)

- ea: `0x140004288`
- end: `0x140004437`
- name: `?__EHM_FlatFileWrite@@YAXPEAXPEBG_K@Z`
- size: `431`
- prototype: `void __fastcall(void *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400036d8`
- `0x140003948`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140004288`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1400042c1`
- `KERNEL32!WriteFile` at `0x14000438c`
- `KERNEL32!WriteFile` at `0x1400042c1`
- `KERNEL32!WriteFile` at `0x14000438c`
- `KERNEL32!IsDebuggerPresent` at `0x140004323`
- `KERNEL32!IsDebuggerPresent` at `0x1400043ee`
- `KERNEL32!IsDebuggerPresent` at `0x140004323`
- `KERNEL32!IsDebuggerPresent` at `0x1400043ee`
- `KERNEL32!GetLastError` at `0x1400042cf`
- `KERNEL32!GetLastError` at `0x14000439a`
- `KERNEL32!GetLastError` at `0x1400042cf`
- `KERNEL32!GetLastError` at `0x14000439a`

## string_xrefs

- `0x140004306`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x140004337`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x1400043d1`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x14000440d`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x1400042f2`: `__EHM_FlatFileWrite`
- `0x1400043bd`: `__EHM_FlatFileWrite`

## pseudocode

```c
void __fastcall __EHM_FlatFileWrite(void *a1, const unsigned __int16 *a2, int a3)
{
  HANDLE v3; // rbx
  signed int v4; // eax
  signed int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // r8
  signed int LastError; // eax
  signed int v9; // [rsp+30h] [rbp-38h]
  signed int v10; // [rsp+38h] [rbp-30h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  int v12; // [rsp+74h] [rbp+Ch]

  v12 = HIDWORD(a1);
  v3 = hFile;
  NumberOfBytesWritten = 0;
  if ( hFile )
  {
    if ( WriteFile(hFile, a2, 2 * a3, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile(v3, L"\r\n", 6u, &NumberOfBytesWritten, 0) )
        return;
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        0x11Eu,
        L"__EHM_FlatFileWrite",
        L"CBRAEx",
        L"fSuccess",
        v5);
      if ( IsDebuggerPresent() )
      {
        v6 = 286;
        goto LABEL_9;
      }
      v7 = 286;
    }
    else
    {
      v4 = GetLastError();
      v5 = v4;
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        0x11Bu,
        L"__EHM_FlatFileWrite",
        L"CBRAEx",
        L"fSuccess",
        v5);
      if ( IsDebuggerPresent() )
      {
        v6 = 283;
LABEL_9:
        v10 = v5;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          v6,
          L"__EHM_FlatFileWrite",
          L"CBRAEx",
          L"fSuccess",
          v10);
        return;
      }
      v7 = 283;
    }
    v9 = v5;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
      v7,
      L"__EHM_FlatFileWrite",
      L"CBRAEx",
      L"fSuccess",
      v9);
  }
}

```

## disassembly

```asm
0x140004288  mov     rax, rsp
0x14000428b  mov     [rax+8], rcx
0x14000428f  push    rbx
0x140004290  push    rbp
0x140004291  push    rsi
0x140004292  push    r14
0x140004294  sub     rsp, 48h
0x140004298  mov     rbx, cs:hFile
0x14000429f  mov     dword ptr [rax+8], 0
0x1400042a6  test    rbx, rbx
0x1400042a9  jz      loc_14000442D
0x1400042af  add     r8d, r8d; nNumberOfBytesToWrite
0x1400042b2  mov     qword ptr [rax-48h], 0
0x1400042ba  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1400042be  mov     rcx, rbx; hFile
0x1400042c1  call    cs:__imp_WriteFile
0x1400042c7  test    eax, eax
0x1400042c9  jnz     loc_14000436E
0x1400042cf  call    cs:__imp_GetLastError
0x1400042d5  mov     ebx, eax
0x1400042d7  test    eax, eax
0x1400042d9  jle     short loc_1400042E4
0x1400042db  movzx   ebx, ax
0x1400042de  or      ebx, 80070000h
0x1400042e4  mov     eax, 80004005h
0x1400042e9  lea     r14, aCbraex; "CBRAEx"
0x1400042f0  test    ebx, ebx
0x1400042f2  lea     rsi, aEhmFlatfilewri; "__EHM_FlatFileWrite"
0x1400042f9  lea     rbp, aFsuccess; "fSuccess"
0x140004300  mov     r9, r14; unsigned __int16 *
0x140004303  cmovns  ebx, eax
0x140004306  lea     rcx, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x14000430d  mov     [rsp+68h+var_40], ebx; int
0x140004311  mov     r8, rsi; unsigned __int16 *
0x140004314  mov     edx, 11Bh; unsigned int
0x140004319  mov     [rsp+68h+lpOverlapped], rbp; unsigned __int16 *
0x14000431e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140004323  call    cs:__imp_IsDebuggerPresent
0x140004329  test    eax, eax
0x14000432b  jz      short loc_140004363
0x14000432d  mov     r9d, 11Bh
0x140004333  mov     [rsp+68h+var_30], ebx
0x140004337  lea     r8, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x14000433e  mov     [rsp+68h+var_38], rbp
0x140004343  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000434a  mov     qword ptr [rsp+68h+var_40], r14
0x14000434f  mov     ecx, 2; unsigned __int8
0x140004354  mov     [rsp+68h+lpOverlapped], rsi
0x140004359  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000435e  jmp     loc_14000442D
0x140004363  mov     r8d, 11Bh
0x140004369  jmp     loc_140004409
0x14000436e  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140004373  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14000437c  mov     r8d, 6; nNumberOfBytesToWrite
0x140004382  lea     rdx, asc_14000EF58; "\r\n"
0x140004389  mov     rcx, rbx; hFile
0x14000438c  call    cs:__imp_WriteFile
0x140004392  test    eax, eax
0x140004394  jnz     loc_14000442D
0x14000439a  call    cs:__imp_GetLastError
0x1400043a0  mov     ebx, eax
0x1400043a2  test    eax, eax
0x1400043a4  jle     short loc_1400043AF
0x1400043a6  movzx   ebx, ax
0x1400043a9  or      ebx, 80070000h
0x1400043af  mov     eax, 80004005h
0x1400043b4  lea     r14, aCbraex; "CBRAEx"
0x1400043bb  test    ebx, ebx
0x1400043bd  lea     rsi, aEhmFlatfilewri; "__EHM_FlatFileWrite"
0x1400043c4  lea     rbp, aFsuccess; "fSuccess"
0x1400043cb  mov     r9, r14; unsigned __int16 *
0x1400043ce  cmovns  ebx, eax
0x1400043d1  lea     rcx, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x1400043d8  mov     [rsp+68h+var_40], ebx; int
0x1400043dc  mov     r8, rsi; unsigned __int16 *
0x1400043df  mov     edx, 11Eh; unsigned int
0x1400043e4  mov     [rsp+68h+lpOverlapped], rbp; unsigned __int16 *
0x1400043e9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400043ee  call    cs:__imp_IsDebuggerPresent
0x1400043f4  test    eax, eax
0x1400043f6  jz      short loc_140004403
0x1400043f8  mov     r9d, 11Eh
0x1400043fe  jmp     loc_140004333
0x140004403  mov     r8d, 11Eh
0x140004409  mov     dword ptr [rsp+68h+var_38], ebx
0x14000440d  lea     rdx, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x140004414  mov     qword ptr [rsp+68h+var_40], rbp
0x140004419  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140004420  mov     r9, rsi
0x140004423  mov     [rsp+68h+lpOverlapped], r14
0x140004428  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000442d  add     rsp, 48h
0x140004431  pop     r14
0x140004433  pop     rsi
0x140004434  pop     rbp
0x140004435  pop     rbx
0x140004436  retn
```
