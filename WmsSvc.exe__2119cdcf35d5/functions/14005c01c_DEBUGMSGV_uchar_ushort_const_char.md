# DEBUGMSGV(uchar,ushort const *,char *)

- ea: `0x14005c01c`
- end: `0x14005c289`
- name: `?DEBUGMSGV@@YAXEPEBGPEAD@Z`
- size: `621`
- prototype: `void __fastcall(unsigned __int8, const unsigned __int16 *, va_list)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14005bc30`
- `0x14005bfec`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c01c`
- `0x14005c408`
- `0x14005c5c0`
- `0x14005c7a8`
- `0x14005c80c`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007cc60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14005c15b`
- `KERNEL32!WriteFile` at `0x14005c1a0`
- `KERNEL32!WriteFile` at `0x14005c15b`
- `KERNEL32!WriteFile` at `0x14005c1a0`
- `KERNEL32!GetLastError` at `0x14005c165`
- `KERNEL32!GetLastError` at `0x14005c1ae`
- `KERNEL32!GetLastError` at `0x14005c165`
- `KERNEL32!GetLastError` at `0x14005c1ae`
- `KERNEL32!IsDebuggerPresent` at `0x14005c0ae`
- `KERNEL32!IsDebuggerPresent` at `0x14005c209`
- `KERNEL32!IsDebuggerPresent` at `0x14005c0ae`
- `KERNEL32!IsDebuggerPresent` at `0x14005c209`

## string_xrefs

- `0x14005c08b`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x14005c1de`: `termsrv\wms\src\common\ehmlib\ehmlib.cpp`
- `0x14005c1d7`: `__EHM_FlatFileWrite`
- `0x14005c092`: `level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))`

## pseudocode

```c
void __fastcall DEBUGMSGV(unsigned __int8 a1, const unsigned __int16 *a2, va_list a3)
{
  __int64 v6; // rdx
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  __int64 v8; // rcx
  DWORD v9; // edi
  HANDLE v10; // rbx
  signed int v11; // eax
  signed int v12; // ebx
  unsigned int v13; // r12d
  signed int LastError; // eax
  int v15; // [rsp+30h] [rbp-2058h]
  signed int v16; // [rsp+30h] [rbp-2058h]
  int v17; // [rsp+38h] [rbp-2050h]
  signed int v18; // [rsp+38h] [rbp-2050h]
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-2048h] BYREF
  unsigned __int16 Buffer[4096]; // [rsp+50h] [rbp-2038h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  *(_QWORD *)NumberOfBytesWritten = 0;
  if ( a1 < 6u )
  {
    if ( (int)__EHM_AddPrefixToDebugMsg(Buffer, v6, (unsigned __int64 *)NumberOfBytesWritten, a2, a3) >= 0 )
    {
      v9 = NumberOfBytesWritten[0];
      __EHM_EtwWrite(v8, v7, Buffer, NumberOfBytesWritten[0] + 1);
      __EHM_MsiWrite(g_hMsi, Buffer);
      v10 = hFile;
      NumberOfBytesWritten[0] = 0;
      if ( hFile )
      {
        if ( WriteFile(hFile, Buffer, 2 * v9, NumberOfBytesWritten, 0) )
        {
          if ( WriteFile(v10, L"\r\n", 6u, NumberOfBytesWritten, 0) )
            return;
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          v13 = 286;
        }
        else
        {
          v11 = GetLastError();
          v12 = v11;
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          v13 = 283;
        }
        if ( v12 >= 0 )
          v12 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
          v13,
          L"__EHM_FlatFileWrite",
          L"CBRAEx",
          L"fSuccess",
          v12);
        if ( IsDebuggerPresent() )
        {
          v18 = v12;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
            v13,
            L"__EHM_FlatFileWrite",
            L"CBRAEx",
            L"fSuccess",
            v18,
            *(_QWORD *)NumberOfBytesWritten);
        }
        else
        {
          v16 = v12;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
            v13,
            L"__EHM_FlatFileWrite",
            L"CBRAEx",
            L"fSuccess",
            v16);
        }
      }
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
      0x1F8u,
      L"DEBUGMSGV",
      L"CBRAEx",
      L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      v17 = -2147024809;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        504,
        L"DEBUGMSGV",
        L"CBRAEx",
        L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
        v17,
        *(_QWORD *)NumberOfBytesWritten);
    }
    else
    {
      v15 = -2147024809;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\ehmlib\\ehmlib.cpp",
        504,
        L"DEBUGMSGV",
        L"CBRAEx",
        L"level < (sizeof(*RtlpNumberOf(s_rgEventDescriptor)))",
        v15);
    }
  }
}

```

## disassembly

```asm
0x14005c01c  mov     [rsp+arg_0], rbx
0x14005c021  push    rbp
0x14005c022  push    rsi
0x14005c023  push    rdi
0x14005c024  push    r12
0x14005c026  push    r14
0x14005c028  mov     eax, 2060h
0x14005c02d  call    _alloca_probe
0x14005c032  sub     rsp, rax
0x14005c035  mov     rax, cs:__security_cookie
0x14005c03c  xor     rax, rsp
0x14005c03f  mov     [rsp+2088h+var_38], rax
0x14005c047  mov     rsi, r8
0x14005c04a  mov     rdi, rdx
0x14005c04d  mov     bl, cl
0x14005c04f  xor     edx, edx; Val
0x14005c051  mov     r8d, 2000h; Size
0x14005c057  lea     rcx, [rsp+2088h+Buffer]; void *
0x14005c05c  call    memset_0
0x14005c061  mov     qword ptr [rsp+2088h+NumberOfBytesWritten], 0
0x14005c06a  cmp     bl, 6
0x14005c06d  jb      short loc_14005C0E7
0x14005c06f  mov     ebx, 80070057h
0x14005c074  lea     rsi, aCbraex; "CBRAEx"
0x14005c07b  lea     r14, aDebugmsgv; "DEBUGMSGV"
0x14005c082  mov     [rsp+2088h+var_2060], ebx; int
0x14005c086  mov     ebp, 1F8h
0x14005c08b  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x14005c092  lea     r12, aLevelSizeofRtl; "level < (sizeof(*RtlpNumberOf(s_rgEvent"...
0x14005c099  mov     r9, rsi; unsigned __int16 *
0x14005c09c  mov     r8, r14; unsigned __int16 *
0x14005c09f  mov     [rsp+2088h+lpOverlapped], r12; unsigned __int16 *
0x14005c0a4  mov     edx, ebp; unsigned int
0x14005c0a6  mov     rcx, rdi; unsigned __int16 *
0x14005c0a9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005c0ae  call    cs:__imp_IsDebuggerPresent
0x14005c0b4  test    eax, eax
0x14005c0b6  jz      short loc_14005C0D3
0x14005c0b8  mov     [rsp+2088h+var_2050], ebx
0x14005c0bc  mov     r9d, ebp
0x14005c0bf  mov     [rsp+2088h+var_2058], r12
0x14005c0c4  mov     qword ptr [rsp+2088h+var_2060], rsi
0x14005c0c9  mov     [rsp+2088h+lpOverlapped], r14
0x14005c0ce  jmp     loc_14005C229
0x14005c0d3  mov     dword ptr [rsp+2088h+var_2058], ebx
0x14005c0d7  mov     r9, r14
0x14005c0da  mov     qword ptr [rsp+2088h+var_2060], r12
0x14005c0df  mov     r8d, ebp
0x14005c0e2  jmp     loc_14005C24E
0x14005c0e7  mov     r9, rdi; unsigned __int16 *
0x14005c0ea  mov     [rsp+2088h+lpOverlapped], rsi; char *
0x14005c0ef  lea     r8, [rsp+2088h+NumberOfBytesWritten]; unsigned __int64 *
0x14005c0f4  lea     rcx, [rsp+2088h+Buffer]; unsigned __int16 *
0x14005c0f9  call    ?__EHM_AddPrefixToDebugMsg@@YAJPEAG_KPEA_KPEBGPEAD@Z; __EHM_AddPrefixToDebugMsg(ushort *,unsigned __int64,unsigned __int64 *,ushort const *,char *)
0x14005c0fe  test    eax, eax
0x14005c100  js      loc_14005C262
0x14005c106  mov     rdi, qword ptr [rsp+2088h+NumberOfBytesWritten]
0x14005c10b  lea     r8, [rsp+2088h+Buffer]; unsigned __int16 *
0x14005c110  lea     r9, [rdi+1]; unsigned __int64
0x14005c114  call    ?__EHM_EtwWrite@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEBG0@Z; __EHM_EtwWrite(unsigned __int64,_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)
0x14005c119  mov     ecx, cs:?g_hMsi@@3KA; unsigned int
0x14005c11f  lea     rdx, [rsp+2088h+Buffer]; unsigned __int16 *
0x14005c124  call    ?__EHM_MsiWrite@@YAXKPEBG@Z; __EHM_MsiWrite(ulong,ushort const *)
0x14005c129  mov     rbx, cs:hFile
0x14005c130  mov     [rsp+2088h+NumberOfBytesWritten], 0
0x14005c138  test    rbx, rbx
0x14005c13b  jz      loc_14005C262
0x14005c141  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x14005c145  mov     [rsp+2088h+lpOverlapped], 0; lpOverlapped
0x14005c14e  lea     r9, [rsp+2088h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005c153  mov     rcx, rbx; hFile
0x14005c156  lea     rdx, [rsp+2088h+Buffer]; lpBuffer
0x14005c15b  call    cs:__imp_WriteFile
0x14005c161  test    eax, eax
0x14005c163  jnz     short loc_14005C182
0x14005c165  call    cs:__imp_GetLastError
0x14005c16b  mov     ebx, eax
0x14005c16d  test    eax, eax
0x14005c16f  jle     short loc_14005C17A
0x14005c171  movzx   ebx, ax
0x14005c174  or      ebx, 80070000h
0x14005c17a  mov     r12d, 11Bh
0x14005c180  jmp     short loc_14005C1C9
0x14005c182  lea     r9, [rsp+2088h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14005c187  mov     [rsp+2088h+lpOverlapped], 0; lpOverlapped
0x14005c190  mov     r8d, 6; nNumberOfBytesToWrite
0x14005c196  lea     rdx, asc_1400D7808; "\r\n"
0x14005c19d  mov     rcx, rbx; hFile
0x14005c1a0  call    cs:__imp_WriteFile
0x14005c1a6  test    eax, eax
0x14005c1a8  jnz     loc_14005C262
0x14005c1ae  call    cs:__imp_GetLastError
0x14005c1b4  mov     ebx, eax
0x14005c1b6  test    eax, eax
0x14005c1b8  jle     short loc_14005C1C3
0x14005c1ba  movzx   ebx, ax
0x14005c1bd  or      ebx, 80070000h
0x14005c1c3  mov     r12d, 11Eh
0x14005c1c9  mov     eax, 80004005h
0x14005c1ce  lea     rsi, aCbraex; "CBRAEx"
0x14005c1d5  test    ebx, ebx
0x14005c1d7  lea     rbp, aEhmFlatfilewri; "__EHM_FlatFileWrite"
0x14005c1de  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\ehmlib\\ehml"...
0x14005c1e5  mov     r9, rsi; unsigned __int16 *
0x14005c1e8  cmovns  ebx, eax
0x14005c1eb  lea     r14, aFsuccess; "fSuccess"
0x14005c1f2  mov     [rsp+2088h+var_2060], ebx; int
0x14005c1f6  mov     r8, rbp; unsigned __int16 *
0x14005c1f9  mov     edx, r12d; unsigned int
0x14005c1fc  mov     [rsp+2088h+lpOverlapped], r14; unsigned __int16 *
0x14005c201  mov     rcx, rdi; unsigned __int16 *
0x14005c204  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005c209  call    cs:__imp_IsDebuggerPresent
0x14005c20f  test    eax, eax
0x14005c211  jz      short loc_14005C23F
0x14005c213  mov     [rsp+2088h+var_2050], ebx
0x14005c217  mov     r9d, r12d
0x14005c21a  mov     [rsp+2088h+var_2058], r14
0x14005c21f  mov     qword ptr [rsp+2088h+var_2060], rsi
0x14005c224  mov     [rsp+2088h+lpOverlapped], rbp
0x14005c229  mov     r8, rdi
0x14005c22c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005c233  mov     ecx, 2; unsigned __int8
0x14005c238  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005c23d  jmp     short loc_14005C262
0x14005c23f  mov     dword ptr [rsp+2088h+var_2058], ebx
0x14005c243  mov     r8d, r12d
0x14005c246  mov     qword ptr [rsp+2088h+var_2060], r14
0x14005c24b  mov     r9, rbp
0x14005c24e  mov     rdx, rdi
0x14005c251  mov     [rsp+2088h+lpOverlapped], rsi
0x14005c256  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005c25d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005c262  mov     rcx, [rsp+2088h+var_38]
0x14005c26a  xor     rcx, rsp; StackCookie
0x14005c26d  call    __security_check_cookie
0x14005c272  mov     rbx, [rsp+2088h+arg_0]
0x14005c27a  add     rsp, 2060h
0x14005c281  pop     r14
0x14005c283  pop     r12
0x14005c285  pop     rdi
0x14005c286  pop     rsi
0x14005c287  pop     rbp
0x14005c288  retn
```
