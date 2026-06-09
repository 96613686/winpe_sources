# Uev::Common::GetFileTimestamp(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_FILETIME &)

- ea: `0x140026a34`
- end: `0x140026b4e`
- name: `?GetFileTimestamp@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_FILETIME@@@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003cb90`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000d1d8`
- `0x14000d2d8`
- `0x1400131ec`
- `0x140026a34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140026ad1`
- `KERNEL32!GetLastError` at `0x140026b10`
- `KERNEL32!GetLastError` at `0x140026ad1`
- `KERNEL32!GetLastError` at `0x140026b10`
- `KERNEL32!GetFileTime` at `0x140026aa4`
- `KERNEL32!GetFileTime` at `0x140026aa4`
- `KERNEL32!CreateFileW` at `0x140026a81`
- `KERNEL32!CreateFileW` at `0x140026a81`

## string_xrefs

- `0x140026b18`: `Unable to open file`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::Common::GetFileTimestamp(const WCHAR *a1, struct _FILETIME *a2)
{
  HANDLE FileW; // rax
  DWORD v5; // ebx
  DWORD LastError; // ebx
  HANDLE v7; // [rsp+40h] [rbp-B8h] BYREF
  _QWORD v8[5]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    std::wstring::wstring(v8, L"Unable to open file");
    Uev::SystemException::SystemException(pExceptionObject, v8, LastError);
    throw (Uev::SystemException *)pExceptionObject;
  }
  if ( !GetFileTime(FileW, 0, 0, a2) )
  {
    v5 = GetLastError();
    std::wstring::wstring(v8, L"Unable to get file timestamp");
    Uev::SystemException::SystemException(pExceptionObject, v8, v5);
    throw (Uev::SystemException *)pExceptionObject;
  }
  return Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(&v7);
}

```

## disassembly

```asm
0x140026a34  push    rbx
0x140026a36  sub     rsp, 0F0h
0x140026a3d  mov     rax, cs:__security_cookie
0x140026a44  xor     rax, rsp
0x140026a47  mov     [rsp+0F8h+var_18], rax
0x140026a4f  mov     rbx, rdx
0x140026a52  cmp     qword ptr [rcx+18h], 7
0x140026a57  jbe     short loc_140026A5C
0x140026a59  mov     rcx, [rcx]; lpFileName
0x140026a5c  mov     [rsp+0F8h+hTemplateFile], 0; hTemplateFile
0x140026a65  mov     [rsp+0F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140026a6d  mov     [rsp+0F8h+dwCreationDisposition], 3; dwCreationDisposition
0x140026a75  xor     r9d, r9d; lpSecurityAttributes
0x140026a78  mov     edx, 80000000h; dwDesiredAccess
0x140026a7d  lea     r8d, [r9+1]; dwShareMode
0x140026a81  call    cs:__imp_CreateFileW
0x140026a87  mov     [rsp+0F8h+var_B8], rax
0x140026a8c  lea     rcx, [rax+1]
0x140026a90  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140026a97  jz      short loc_140026B10
0x140026a99  mov     r9, rbx; lpLastWriteTime
0x140026a9c  xor     r8d, r8d; lpLastAccessTime
0x140026a9f  xor     edx, edx; lpCreationTime
0x140026aa1  mov     rcx, rax; hFile
0x140026aa4  call    cs:__imp_GetFileTime
0x140026aaa  test    eax, eax
0x140026aac  jz      short loc_140026AD1
0x140026aae  lea     rcx, [rsp+0F8h+var_B8]
0x140026ab3  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x140026ab8  mov     rcx, [rsp+0F8h+var_18]
0x140026ac0  xor     rcx, rsp; StackCookie
0x140026ac3  call    __security_check_cookie
0x140026ac8  add     rsp, 0F0h
0x140026acf  pop     rbx
0x140026ad0  retn
0x140026ad1  call    cs:__imp_GetLastError
0x140026ad7  nop
0x140026ad8  mov     ebx, eax
0x140026ada  lea     rdx, aUnableToGetFil_0; "Unable to get file timestamp"
0x140026ae1  lea     rcx, [rsp+0F8h+var_B0]
0x140026ae6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140026aeb  nop
0x140026aec  mov     r8d, ebx
0x140026aef  lea     rdx, [rsp+0F8h+var_B0]
0x140026af4  lea     rcx, [rsp+0F8h+pExceptionObject]
0x140026af9  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140026afe  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140026b05  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x140026b0a  call    _CxxThrowException_0
0x140026b10  call    cs:__imp_GetLastError
0x140026b16  mov     ebx, eax
0x140026b18  lea     rdx, aUnableToOpenFi; "Unable to open file"
0x140026b1f  lea     rcx, [rsp+0F8h+var_B0]
0x140026b24  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140026b29  nop
0x140026b2a  mov     r8d, ebx
0x140026b2d  lea     rdx, [rsp+0F8h+var_B0]
0x140026b32  lea     rcx, [rsp+0F8h+pExceptionObject]
0x140026b37  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140026b3c  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140026b43  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x140026b48  call    _CxxThrowException_0
```
