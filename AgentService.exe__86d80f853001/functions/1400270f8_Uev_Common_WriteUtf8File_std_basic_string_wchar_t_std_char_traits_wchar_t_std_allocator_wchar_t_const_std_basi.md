# Uev::Common::WriteUtf8File(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1400270f8`
- end: `0x140027380`
- name: `?WriteUtf8File@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `648`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003b0a0`
- `0x14003d840`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d2d8`
- `0x1400131ec`
- `0x140014998`
- `0x1400270f8`

## import_xrefs

- `KERNEL32!Sleep` at `0x140027192`
- `KERNEL32!Sleep` at `0x140027192`
- `KERNEL32!GetLastError` at `0x140027175`
- `KERNEL32!GetLastError` at `0x1400272d2`
- `KERNEL32!GetLastError` at `0x14002730c`
- `KERNEL32!GetLastError` at `0x140027346`
- `KERNEL32!GetLastError` at `0x140027175`
- `KERNEL32!GetLastError` at `0x1400272d2`
- `KERNEL32!GetLastError` at `0x14002730c`
- `KERNEL32!GetLastError` at `0x140027346`
- `KERNEL32!CreateFileW` at `0x140027166`
- `KERNEL32!CreateFileW` at `0x140027166`
- `KERNEL32!WriteFile` at `0x140027256`
- `KERNEL32!WriteFile` at `0x140027256`
- `KERNEL32!WideCharToMultiByte` at `0x1400271db`
- `KERNEL32!WideCharToMultiByte` at `0x14002722e`
- `KERNEL32!WideCharToMultiByte` at `0x1400271db`
- `KERNEL32!WideCharToMultiByte` at `0x14002722e`

## string_xrefs

- `0x1400272a3`: `Attempting to use an invalid handle.`
- `0x14002734e`: `File write error`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Uev::Common::WriteUtf8File(_QWORD *lpFileName, LPCWCH lpWideCharStr)
{
  int v4; // edi
  const WCHAR *v5; // rcx
  HANDLE FileW; // rax
  void *v7; // r14
  const WCHAR *v8; // r8
  int v9; // eax
  DWORD v10; // esi
  CHAR *v11; // rax
  CHAR *v12; // rdi
  int v13; // r9d
  DWORD LastError; // ebx
  DWORD v16; // ebx
  DWORD v17; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v19[2]; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v20[5]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-39h] BYREF

  v4 = 5;
  while ( 1 )
  {
    if ( v4 <= 0 )
    {
      LastError = GetLastError();
      std::wstring::wstring(v20, L"File creation error (sharing violation)");
      Uev::SystemException::SystemException(pExceptionObject, v20, LastError);
      throw (Uev::SystemException *)pExceptionObject;
    }
    v5 = lpFileName[3] <= 7u ? (const WCHAR *)lpFileName : (const WCHAR *)*lpFileName;
    FileW = CreateFileW(v5, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v7 = FileW;
    if ( FileW != (HANDLE)-1LL )
      break;
    if ( GetLastError() != 32 || (--v4, !v4) )
    {
      v16 = GetLastError();
      std::wstring::wstring(v20, L"File creation error");
      Uev::SystemException::SystemException(pExceptionObject, v20, v16);
      throw (Uev::SystemException *)pExceptionObject;
    }
    Sleep(0x3E8u);
  }
  v19[0] = FileW;
  if ( *((_QWORD *)lpWideCharStr + 3) <= 7u )
    v8 = lpWideCharStr;
  else
    v8 = *(const WCHAR **)lpWideCharStr;
  v9 = WideCharToMultiByte(0xFDE9u, 0, v8, *((_DWORD *)lpWideCharStr + 4), 0, 0, 0, 0);
  v10 = v9;
  if ( v9 > 0 )
  {
    v11 = (CHAR *)operator new[](v9);
    v12 = v11;
    v19[1] = v11;
    v13 = *((_DWORD *)lpWideCharStr + 4);
    if ( *((_QWORD *)lpWideCharStr + 3) > 7u )
      lpWideCharStr = *(LPCWCH *)lpWideCharStr;
    WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v13, v11, v10, 0, 0);
    NumberOfBytesWritten = 0;
    if ( !v7 )
    {
      std::wstring::wstring(v20, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v20);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    if ( !WriteFile(v7, v12, v10, &NumberOfBytesWritten, 0) )
    {
      v17 = GetLastError();
      std::wstring::wstring(v20, L"File write error");
      Uev::SystemException::SystemException(pExceptionObject, v20, v17);
      throw (Uev::SystemException *)pExceptionObject;
    }
    operator delete(v12);
  }
  Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::Close(v19);
  return Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(v19);
}

```

## disassembly

```asm
0x1400270f8  mov     [rsp-8+arg_10], rbx
0x1400270fd  mov     [rsp-8+arg_18], rsi
0x140027102  push    rbp
0x140027103  push    rdi
0x140027104  push    r14
0x140027106  lea     rbp, [rsp-47h]
0x14002710b  sub     rsp, 100h
0x140027112  mov     rax, cs:__security_cookie
0x140027119  xor     rax, rsp
0x14002711c  mov     [rbp+57h+var_20], rax
0x140027120  mov     rbx, rdx
0x140027123  mov     rsi, rcx
0x140027126  mov     edi, 5
0x14002712b  test    edi, edi
0x14002712d  jle     loc_1400272D2
0x140027133  cmp     qword ptr [rsi+18h], 7
0x140027138  jbe     short loc_14002713F
0x14002713a  mov     rcx, [rsi]
0x14002713d  jmp     short loc_140027142
0x14002713f  mov     rcx, rsi; lpFileName
0x140027142  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x14002714b  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140027153  mov     [rsp+110h+dwCreationDisposition], 2; dwCreationDisposition
0x14002715b  xor     r9d, r9d; lpSecurityAttributes
0x14002715e  xor     r8d, r8d; dwShareMode
0x140027161  mov     edx, 40000000h; dwDesiredAccess
0x140027166  call    cs:__imp_CreateFileW
0x14002716c  mov     r14, rax
0x14002716f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140027173  jnz     short loc_14002719A
0x140027175  call    cs:__imp_GetLastError
0x14002717b  cmp     eax, 20h ; ' '
0x14002717e  jnz     loc_14002730C
0x140027184  sub     edi, 1
0x140027187  jz      loc_14002730C
0x14002718d  mov     ecx, 3E8h; dwMilliseconds
0x140027192  call    cs:__imp_Sleep
0x140027198  jmp     short loc_14002712B
0x14002719a  mov     [rbp+57h+var_C8], r14
0x14002719e  cmp     qword ptr [rbx+18h], 7
0x1400271a3  jbe     short loc_1400271AA
0x1400271a5  mov     r8, [rbx]
0x1400271a8  jmp     short loc_1400271AD
0x1400271aa  mov     r8, rbx; lpWideCharStr
0x1400271ad  mov     [rsp+110h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400271b6  mov     [rsp+110h+hTemplateFile], 0; lpDefaultChar
0x1400271bf  mov     [rsp+110h+dwFlagsAndAttributes], 0; cbMultiByte
0x1400271c7  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpMultiByteStr
0x1400271d0  mov     r9d, [rbx+10h]; cchWideChar
0x1400271d4  xor     edx, edx; dwFlags
0x1400271d6  mov     ecx, 0FDE9h; CodePage
0x1400271db  call    cs:__imp_WideCharToMultiByte
0x1400271e1  movsxd  rsi, eax
0x1400271e4  test    eax, eax
0x1400271e6  jle     loc_14002726C
0x1400271ec  mov     rcx, rsi; unsigned __int64
0x1400271ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400271f4  mov     rdi, rax
0x1400271f7  mov     [rbp+57h+var_C0], rax
0x1400271fb  mov     r9d, [rbx+10h]; cchWideChar
0x1400271ff  cmp     qword ptr [rbx+18h], 7
0x140027204  jbe     short loc_140027209
0x140027206  mov     rbx, [rbx]
0x140027209  mov     [rsp+110h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140027212  mov     [rsp+110h+hTemplateFile], 0; lpDefaultChar
0x14002721b  mov     [rsp+110h+dwFlagsAndAttributes], esi; cbMultiByte
0x14002721f  mov     qword ptr [rsp+110h+dwCreationDisposition], rdi; lpMultiByteStr
0x140027224  mov     r8, rbx; lpWideCharStr
0x140027227  xor     edx, edx; dwFlags
0x140027229  mov     ecx, 0FDE9h; CodePage
0x14002722e  call    cs:__imp_WideCharToMultiByte
0x140027234  mov     [rbp+57h+NumberOfBytesWritten], 0
0x14002723b  test    r14, r14
0x14002723e  jz      short loc_1400272A3
0x140027240  mov     qword ptr [rsp+110h+dwCreationDisposition], 0; lpOverlapped
0x140027249  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002724d  mov     r8d, esi; nNumberOfBytesToWrite
0x140027250  mov     rdx, rdi; lpBuffer
0x140027253  mov     rcx, r14; hFile
0x140027256  call    cs:__imp_WriteFile
0x14002725c  test    eax, eax
0x14002725e  jz      loc_140027346
0x140027264  mov     rcx, rdi; Block
0x140027267  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002726c  lea     rcx, [rbp+57h+var_C8]
0x140027270  call    ?Close@?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAAXXZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::Close(void)
0x140027275  nop
0x140027276  lea     rcx, [rbp+57h+var_C8]
0x14002727a  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x14002727f  mov     rcx, [rbp+57h+var_20]
0x140027283  xor     rcx, rsp; StackCookie
0x140027286  call    __security_check_cookie
0x14002728b  lea     r11, [rsp+110h+var_10]
0x140027293  mov     rbx, [r11+30h]
0x140027297  mov     rsi, [r11+38h]
0x14002729b  mov     rsp, r11
0x14002729e  pop     r14
0x1400272a0  pop     rdi
0x1400272a1  pop     rbp
0x1400272a2  retn
0x1400272a3  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x1400272aa  lea     rcx, [rbp+57h+var_B8]
0x1400272ae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400272b3  nop
0x1400272b4  lea     rdx, [rbp+57h+var_B8]
0x1400272b8  lea     rcx, [rbp+57h+pExceptionObject]
0x1400272bc  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x1400272c1  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x1400272c8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400272cc  call    _CxxThrowException_0
0x1400272d2  call    cs:__imp_GetLastError
0x1400272d8  mov     ebx, eax
0x1400272da  lea     rdx, aFileCreationEr_0; "File creation error (sharing violation)"
0x1400272e1  lea     rcx, [rbp+57h+var_B8]
0x1400272e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400272ea  nop
0x1400272eb  mov     r8d, ebx
0x1400272ee  lea     rdx, [rbp+57h+var_B8]
0x1400272f2  lea     rcx, [rbp+57h+pExceptionObject]
0x1400272f6  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x1400272fb  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140027302  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140027306  call    _CxxThrowException_0
0x14002730c  call    cs:__imp_GetLastError
0x140027312  mov     ebx, eax
0x140027314  lea     rdx, aFileCreationEr; "File creation error"
0x14002731b  lea     rcx, [rbp+57h+var_B8]
0x14002731f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140027324  nop
0x140027325  mov     r8d, ebx
0x140027328  lea     rdx, [rbp+57h+var_B8]
0x14002732c  lea     rcx, [rbp+57h+pExceptionObject]
0x140027330  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140027335  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x14002733c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140027340  call    _CxxThrowException_0
0x140027346  call    cs:__imp_GetLastError
0x14002734c  mov     ebx, eax
0x14002734e  lea     rdx, aFileWriteError; "File write error"
0x140027355  lea     rcx, [rbp+57h+var_B8]
0x140027359  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14002735e  nop
0x14002735f  mov     r8d, ebx
0x140027362  lea     rdx, [rbp+57h+var_B8]
0x140027366  lea     rcx, [rbp+57h+pExceptionObject]
0x14002736a  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x14002736f  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140027376  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14002737a  call    _CxxThrowException_0
```
