# ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)

- ea: `0x180001f90`
- end: `0x180002120`
- name: `?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ`
- size: `400`
- prototype: `__int64(ABO_MAPPER_LOG *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `61`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x180004140`
- `0x1800044e0`
- `0x180004828`
- `0x180004b80`
- `0x180004f98`
- `0x180005314`
- `0x1800053bc`
- `0x180005ec0`
- `0x180005f68`
- `0x180007ea8`
- `0x180008050`
- `0x180009818`
- `0x18000a6fc`
- `0x18000adb0`
- `0x18000b178`
- `0x18000be60`
- `0x18000bf00`
- `0x18000d544`
- `0x18000e99c`
- `0x18000ec90`
- `0x18000ef4c`
- `0x18000f390`
- `0x180010880`
- `0x180010f40`
- `0x180011c5c`
- `0x180011dd0`
- `0x180012a30`
- `0x180012cb0`
- `0x180013a08`
- `0x180013d64`
- `0x180013ec0`
- `0x180014488`
- `0x180014b90`
- `0x180016200`
- `0x1800165d0`
- `0x180017d90`
- `0x1800187e0`
- `0x1800193f0`
- `0x18001a040`
- `0x18001a36c`
- `0x18001a860`
- `0x18001b5b0`
- `0x18001b8d0`
- `0x1800259c0`
- `0x180025e78`
- `0x180026620`
- `0x180027294`
- `0x18002742c`
- `0x1800278cc`

## callees

- `0x180001f90`
- `0x180002128`
- `0x180003460`
- `0x1800034f0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002015`
- `msvcrt!_vsnwprintf` at `0x180002015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b67`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b51`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002028`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002028`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800020e0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003b08`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800020e0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003b08`
- `iisutil!?SetLen@STRA@@QEAA_NK@Z` at `0x180003af6`
- `iisutil!?SetLen@STRA@@QEAA_NK@Z` at `0x180003af6`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180003b2a`
- `iisutil!?QueryCB@STRA@@QEBAKXZ` at `0x180003b2a`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x1800020a3`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x1800020a3`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800020c2`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003ae8`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800020c2`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180003ae8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001fdf`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001fdf`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000208b`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000208b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800020b4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b37`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800020b4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003b37`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800020fc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800020fc`

## pseudocode

```c
__int64 ABO_MAPPER_LOG::WriteLogEntry(HANDLE *this, const unsigned __int16 *a2, ...)
{
  signed int v3; // ebx
  char *Str; // rbx
  unsigned int CCH; // eax
  DWORD CB; // edi
  char *v8; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[64]; // [rsp+70h] [rbp-90h] BYREF
  char v13[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v14[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t Buffer[2048]; // [rsp+3B0h] [rbp+2B0h] BYREF
  va_list Args; // [rsp+1400h] [rbp+1300h] BYREF

  va_start(Args, a2);
  STRA::STRA((STRA *)v12, v13, 0x100u);
  NumberOfBytesWritten = 0;
  SystemTime = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    goto LABEL_7;
  }
  _vsnwprintf(Buffer, 0x7FFu, a2, Args);
  Buffer[2047] = 0;
  GetLocalTime(&SystemTime);
  StringCchPrintfW(
    v14,
    0x100u,
    L"[%02d-%02d-%02d %02d:%02d:%02d] ",
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond);
  v3 = STRA::CopyW((STRA *)v12, v14);
  if ( v3 >= 0 )
  {
    v3 = STRA::AppendW((STRA *)v12, Buffer);
    if ( v3 >= 0 )
    {
      Str = STRA::QueryStr((STRA *)v12);
      if ( Str[STRA::QueryCCH((STRA *)v12) - 1] == 10 )
      {
        CCH = STRA::QueryCCH((STRA *)v12);
        STRA::SetLen((STRA *)v12, CCH - 1);
        v3 = STRA::Append((STRA *)v12, "\r\n");
        if ( v3 < 0 )
          goto LABEL_7;
      }
      else
      {
        v3 = STRA::Append((STRA *)v12, "\r\n");
        if ( v3 < 0 )
          goto LABEL_7;
      }
      if ( this[1] != (HANDLE)-1LL )
      {
        CB = STRA::QueryCB((STRA *)v12);
        v8 = STRA::QueryStr((STRA *)v12);
        if ( !WriteFile(this[1], v8, CB, &NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
LABEL_7:
  STRA::~STRA((STRA *)v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180001f90  mov     [rsp-8+Format], rdx
0x180001f95  mov     qword ptr [rsp-8+Args], r8
0x180001f9a  mov     [rsp-8+arg_18], r9
0x180001f9f  push    rbp
0x180001fa0  push    rbx
0x180001fa1  push    rsi
0x180001fa2  push    r14
0x180001fa4  lea     rbp, [rsp-12C8h]
0x180001fac  mov     eax, 13C8h
0x180001fb1  call    _alloca_probe
0x180001fb6  sub     rsp, rax
0x180001fb9  mov     rax, cs:__security_cookie
0x180001fc0  xor     rax, rsp
0x180001fc3  mov     [rbp+12E0h+var_30], rax
0x180001fca  mov     rsi, rcx
0x180001fcd  lea     rdx, [rbp+12E0h+var_1330]
0x180001fd1  lea     rcx, [rsp+13E0h+var_1370]
0x180001fd6  mov     r8d, 100h
0x180001fdc  xor     r14d, r14d
0x180001fdf  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001fe5  mov     r8, [rbp+12E0h+Format]; Format
0x180001fec  xorps   xmm0, xmm0
0x180001fef  mov     [rsp+13E0h+NumberOfBytesWritten], r14d
0x180001ff4  movups  xmmword ptr [rsp+13E0h+SystemTime.wYear], xmm0
0x180001ff9  test    r8, r8
0x180001ffc  jz      loc_180003ADE
0x180002002  lea     r9, [rbp+12E0h+Args]; Args
0x180002009  mov     edx, 7FFh; BufferCount
0x18000200e  lea     rcx, [rbp+12E0h+Buffer]; Buffer
0x180002015  call    cs:__imp__vsnwprintf
0x18000201b  lea     rcx, [rsp+13E0h+SystemTime]; lpSystemTime
0x180002020  mov     [rbp+12E0h+var_32], r14w
0x180002028  call    cs:__imp_GetLocalTime
0x18000202e  movzx   ecx, [rsp+13E0h+SystemTime.wMinute]
0x180002033  mov     edx, 100h; unsigned __int64
0x180002038  movzx   r8d, [rsp+13E0h+SystemTime.wHour]
0x18000203e  movzx   eax, [rsp+13E0h+SystemTime.wSecond]
0x180002043  movzx   r10d, [rsp+13E0h+SystemTime.wDay]
0x180002049  movzx   r11d, [rsp+13E0h+SystemTime.wMonth]
0x18000204f  movzx   r9d, [rsp+13E0h+SystemTime.wYear]
0x180002055  mov     [rsp+13E0h+var_13A0], eax
0x180002059  mov     [rsp+13E0h+var_13A8], ecx
0x18000205d  lea     rcx, [rbp+12E0h+var_1230]; unsigned __int16 *
0x180002064  mov     [rsp+13E0h+var_13B0], r8d
0x180002069  lea     r8, a02d02d02d02d02; "[%02d-%02d-%02d %02d:%02d:%02d] "
0x180002070  mov     [rsp+13E0h+var_13B8], r10d
0x180002075  mov     dword ptr [rsp+13E0h+lpOverlapped], r11d
0x18000207a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000207f  lea     rdx, [rbp+12E0h+var_1230]
0x180002086  lea     rcx, [rsp+13E0h+var_1370]
0x18000208b  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180002091  mov     ebx, eax
0x180002093  test    eax, eax
0x180002095  js      short loc_1800020F7
0x180002097  lea     rdx, [rbp+12E0h+Buffer]
0x18000209e  lea     rcx, [rsp+13E0h+var_1370]
0x1800020a3  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x1800020a9  mov     ebx, eax
0x1800020ab  test    eax, eax
0x1800020ad  js      short loc_1800020F7
0x1800020af  lea     rcx, [rsp+13E0h+var_1370]
0x1800020b4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800020ba  lea     rcx, [rsp+13E0h+var_1370]
0x1800020bf  mov     rbx, rax
0x1800020c2  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800020c8  dec     eax
0x1800020ca  lea     rcx, [rsp+13E0h+var_1370]
0x1800020cf  cmp     byte ptr [rax+rbx], 0Ah
0x1800020d3  jz      loc_180003AE8
0x1800020d9  lea     rdx, asc_18002E8E4; "\r\n"
0x1800020e0  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800020e6  mov     ebx, eax
0x1800020e8  test    eax, eax
0x1800020ea  js      short loc_1800020F7
0x1800020ec  cmp     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x1800020f1  jnz     loc_180003B1D
0x1800020f7  lea     rcx, [rsp+13E0h+var_1370]
0x1800020fc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002102  mov     eax, ebx
0x180002104  mov     rcx, [rbp+12E0h+var_30]
0x18000210b  xor     rcx, rsp; StackCookie
0x18000210e  call    __security_check_cookie
0x180002113  add     rsp, 13C8h
0x18000211a  pop     r14
0x18000211c  pop     rsi
0x18000211d  pop     rbx
0x18000211e  pop     rbp
0x18000211f  retn
0x180003ade  mov     ebx, 80070057h
0x180003ae3  jmp     loc_1800020F7
0x180003ae8  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180003aee  lea     rcx, [rsp+13E0h+var_1370]
0x180003af3  lea     edx, [rax-1]
0x180003af6  call    cs:__imp_?SetLen@STRA@@QEAA_NK@Z; STRA::SetLen(ulong)
0x180003afc  lea     rdx, asc_18002E8E4; "\r\n"
0x180003b03  lea     rcx, [rsp+13E0h+var_1370]
0x180003b08  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180003b0e  mov     ebx, eax
0x180003b10  test    eax, eax
0x180003b12  js      loc_1800020F7
0x180003b18  jmp     loc_1800020EC
0x180003b1d  lea     rcx, [rsp+13E0h+var_1370]
0x180003b22  mov     [rsp+13E0h+var_20], rdi
0x180003b2a  call    cs:__imp_?QueryCB@STRA@@QEBAKXZ; STRA::QueryCB(void)
0x180003b30  lea     rcx, [rsp+13E0h+var_1370]
0x180003b35  mov     edi, eax
0x180003b37  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180003b3d  mov     rcx, [rsi+8]; hFile
0x180003b41  lea     r9, [rsp+13E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003b46  mov     rdx, rax; lpBuffer
0x180003b49  mov     [rsp+13E0h+lpOverlapped], r14; lpOverlapped
0x180003b4e  mov     r8d, edi; nNumberOfBytesToWrite
0x180003b51  call    cs:__imp_WriteFile
0x180003b57  mov     rdi, [rsp+13E0h+var_20]
0x180003b5f  test    eax, eax
0x180003b61  jnz     loc_1800020F7
0x180003b67  call    cs:__imp_GetLastError
0x180003b6d  mov     ebx, eax
0x180003b6f  test    eax, eax
0x180003b71  jle     loc_1800020F7
0x180003b77  movzx   ebx, ax
0x180003b7a  or      ebx, 80070000h
0x180003b80  jmp     loc_1800020F7
```
