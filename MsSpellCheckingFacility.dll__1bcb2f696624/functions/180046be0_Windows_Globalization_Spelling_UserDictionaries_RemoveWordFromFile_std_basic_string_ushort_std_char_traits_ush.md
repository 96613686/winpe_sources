# Windows::Globalization::Spelling::UserDictionaries::RemoveWordFromFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180046be0`
- end: `0x180046e40`
- name: `?RemoveWordFromFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180046920`

## callees

- `0x1800222ac`
- `0x180038aa0`
- `0x180038b40`
- `0x18003f8fc`
- `0x18004186c`
- `0x180046be0`
- `0x180046e48`
- `0x180047c48`
- `0x180061320`
- `0x18007f880`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046d2a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046d2a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046cc8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046cc8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046d07`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180046dbc`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180046dbc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046dae`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180046dae`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180046e00`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180046e00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180046dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180046dd1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046de9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180046de9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Windows::Globalization::Spelling::UserDictionaries::RemoveWordFromFile(const WCHAR *a1)
{
  bool v1; // bl
  void *File; // rax
  unsigned __int64 FileSizeFromHandle; // rdi
  __int64 v4; // rsi
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax
  HANDLE v7; // rdi
  unsigned int v9; // [rsp+30h] [rbp-D0h]
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  void **v11; // [rsp+50h] [rbp-B0h] BYREF
  BOOL (__stdcall *v12)(LPCVOID); // [rsp+58h] [rbp-A8h]
  void ***v13; // [rsp+88h] [rbp-78h]
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hFile; // [rsp+E0h] [rbp-20h]
  _BYTE v17[64]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD *v18; // [rsp+130h] [rbp+30h]
  _BYTE v19[64]; // [rsp+140h] [rbp+40h] BYREF
  HANDLE hFileMappingObject; // [rsp+180h] [rbp+80h]

  v1 = 0;
  v11 = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
  v12 = (BOOL (__stdcall *)(LPCVOID))Windows::Globalization::Spelling::CloseHandleIfValid;
  v13 = &v11;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  File = Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(a1, 0xC0000000, 0, 0, 3u, 1u, v9);
  std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(v15, File, &v11);
  std::_Func_class<void,UserDictionary *>::_Tidy(&v11);
  if ( hFile != (HANDLE)-1LL )
  {
    FileSizeFromHandle = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle(hFile);
    if ( FileSizeFromHandle )
    {
      v4 = 0;
      v11 = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
      v12 = (BOOL (__stdcall *)(LPCVOID))Windows::Globalization::Spelling::CloseHandleIfValid;
      v13 = &v11;
      FileMappingW = CreateFileMappingW(hFile, 0, 4u, 0, 0, 0);
      std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(
        v19,
        FileMappingW,
        &v11);
      std::_Func_class<void,UserDictionary *>::_Tidy(&v11);
      if ( hFileMappingObject != (HANDLE)-1LL )
      {
        v11 = &std::_Func_impl_no_alloc<int (*)(void const *),int,void const *>::`vftable';
        v12 = UnmapViewOfFile;
        v13 = &v11;
        v6 = MapViewOfFile(hFileMappingObject, 2u, 0, 0, 0);
        std::unique_ptr<void,std::function<int (void const *)>>::unique_ptr<void,std::function<int (void const *)>>(
          v17,
          v6,
          &v11);
        std::_Func_class<void,UserDictionary *>::_Tidy(&v11);
        if ( v18 && *v18 == 0xFEFF )
        {
          v4 = 2 * Windows::Globalization::Spelling::UserDictionaries::RemoveWordFromStream(v18 + 1) + 2;
          v1 = v4 != FileSizeFromHandle;
        }
        std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v17);
      }
      std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v19);
      if ( v1 )
      {
        if ( SetFilePointerEx(hFile, (LARGE_INTEGER)v4, 0, 0) )
        {
          SetEndOfFile(hFile);
          v7 = hFile;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          FileTime = 0;
          if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
            SetFileTime(v7, 0, 0, &FileTime);
        }
        else
        {
          v1 = 0;
        }
      }
    }
  }
  std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v15);
  return v1;
}

```

## disassembly

```asm
0x180046be0  mov     [rsp-8+arg_10], rbx
0x180046be5  mov     [rsp-8+arg_18], rsi
0x180046bea  push    rbp
0x180046beb  push    rdi
0x180046bec  push    r12
0x180046bee  push    r13
0x180046bf0  push    r14
0x180046bf2  lea     rbp, [rsp-0A0h]
0x180046bfa  sub     rsp, 1A0h
0x180046c01  mov     rax, cs:__security_cookie
0x180046c08  xor     rax, rsp
0x180046c0b  mov     [rbp+0C0h+var_30], rax
0x180046c12  mov     r14, rdx
0x180046c15  xor     bl, bl
0x180046c17  lea     r12, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x180046c1e  mov     [rsp+1C0h+var_170], r12
0x180046c23  lea     r13, Windows__Globalization__Spelling__CloseHandleIfValid
0x180046c2a  mov     [rsp+1C0h+var_168], r13
0x180046c2f  lea     rax, [rsp+1C0h+var_170]
0x180046c34  mov     [rbp+0C0h+var_138], rax
0x180046c38  cmp     qword ptr [rcx+18h], 7
0x180046c3d  jbe     short loc_180046C42
0x180046c3f  mov     rcx, [rcx]; lpFileName
0x180046c42  mov     dword ptr [rsp+1C0h+lpName], 1; DWORD
0x180046c4a  mov     [rsp+1C0h+dwMaximumSizeLow], 3; DWORD
0x180046c52  xor     r9d, r9d; lpSecurityAttributes
0x180046c55  xor     r8d, r8d; dwShareMode
0x180046c58  mov     edx, 0C0000000h; dwDesiredAccess
0x180046c5d  call    ?AttemptCreateFile@UserDictionaries@Spelling@Globalization@Windows@@CAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKK@Z; Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)
0x180046c62  mov     rdx, rax
0x180046c65  lea     r8, [rsp+1C0h+var_170]
0x180046c6a  lea     rcx, [rbp+0C0h+var_120]
0x180046c6e  call    ??$?0V?$function@$$A6AHPEAX@Z@std@@$0A@@?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6AHPEAX@Z@1@@Z; std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(void *,std::function<int (void *)> &&)
0x180046c73  nop
0x180046c74  lea     rcx, [rsp+1C0h+var_170]
0x180046c79  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180046c7e  mov     rcx, [rbp+0C0h+hFile]; void *
0x180046c82  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180046c86  jz      loc_180046E0A
0x180046c8c  call    ?GetFileSizeFromHandle@UserDictionaries@Spelling@Globalization@Windows@@SA_KPEAX@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromHandle(void *)
0x180046c91  mov     rdi, rax
0x180046c94  test    rax, rax
0x180046c97  jz      loc_180046E0A
0x180046c9d  xor     esi, esi
0x180046c9f  mov     [rsp+1C0h+var_170], r12
0x180046ca4  mov     [rsp+1C0h+var_168], r13
0x180046ca9  lea     rax, [rsp+1C0h+var_170]
0x180046cae  mov     [rbp+0C0h+var_138], rax
0x180046cb2  mov     [rsp+1C0h+lpName], rsi; lpName
0x180046cb7  mov     [rsp+1C0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180046cbb  xor     r9d, r9d; dwMaximumSizeHigh
0x180046cbe  xor     edx, edx; lpFileMappingAttributes
0x180046cc0  lea     r8d, [rsi+4]; flProtect
0x180046cc4  mov     rcx, [rbp+0C0h+hFile]; hFile
0x180046cc8  call    cs:__imp_CreateFileMappingW
0x180046cce  mov     rdx, rax
0x180046cd1  lea     r8, [rsp+1C0h+var_170]
0x180046cd6  lea     rcx, [rbp+0C0h+var_80]
0x180046cda  call    ??$?0V?$function@$$A6AHPEAX@Z@std@@$0A@@?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6AHPEAX@Z@1@@Z; std::unique_ptr<void,std::function<int (void *)>>::unique_ptr<void,std::function<int (void *)>>(void *,std::function<int (void *)> &&)
0x180046cdf  nop
0x180046ce0  lea     rcx, [rsp+1C0h+var_170]
0x180046ce5  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180046cea  mov     rcx, [rbp+0C0h+hFileMappingObject]; hFileMappingObject
0x180046cf1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180046cf5  jz      loc_180046D94
0x180046cfb  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEBX@ZHPEBX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void const *),int,void const *>::`vftable'
0x180046d02  mov     [rsp+1C0h+var_170], rax
0x180046d07  mov     rax, cs:__imp_UnmapViewOfFile
0x180046d0e  mov     [rsp+1C0h+var_168], rax
0x180046d13  lea     rax, [rsp+1C0h+var_170]
0x180046d18  mov     [rbp+0C0h+var_138], rax
0x180046d1c  mov     qword ptr [rsp+1C0h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x180046d21  xor     r9d, r9d; dwFileOffsetLow
0x180046d24  xor     r8d, r8d; dwFileOffsetHigh
0x180046d27  lea     edx, [rsi+2]; dwDesiredAccess
0x180046d2a  call    cs:__imp_MapViewOfFile
0x180046d30  mov     rdx, rax
0x180046d33  lea     r8, [rsp+1C0h+var_170]
0x180046d38  lea     rcx, [rbp+0C0h+var_D0]
0x180046d3c  call    ??$?0V?$function@$$A6AHPEBX@Z@std@@$0A@@?$unique_ptr@XV?$function@$$A6AHPEBX@Z@std@@@std@@QEAA@PEAX$$QEAV?$function@$$A6AHPEBX@Z@1@@Z; std::unique_ptr<void,std::function<int (void const *)>>::unique_ptr<void,std::function<int (void const *)>>(void *,std::function<int (void const *)> &&)
0x180046d41  nop
0x180046d42  lea     rcx, [rsp+1C0h+var_170]
0x180046d47  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x180046d4c  mov     rcx, [rbp+0C0h+var_90]
0x180046d50  test    rcx, rcx
0x180046d53  jz      short loc_180046D8A
0x180046d55  mov     eax, 0FEFFh
0x180046d5a  cmp     [rcx], ax
0x180046d5d  jnz     short loc_180046D8A
0x180046d5f  mov     rdx, rdi
0x180046d62  shr     rdx, 1
0x180046d65  lea     r12d, [rsi+1]
0x180046d69  sub     rdx, r12
0x180046d6c  add     rcx, 2; S1
0x180046d70  mov     r8, r14
0x180046d73  call    ?RemoveWordFromStream@UserDictionaries@Spelling@Globalization@Windows@@SA_KPEAG_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::RemoveWordFromStream(ushort *,unsigned __int64,std::wstring const &)
0x180046d78  lea     rsi, ds:2[rax*2]
0x180046d80  movzx   ebx, bl
0x180046d83  cmp     rsi, rdi
0x180046d86  cmovnz  ebx, r12d
0x180046d8a  lea     rcx, [rbp+0C0h+var_D0]
0x180046d8e  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x180046d93  nop
0x180046d94  lea     rcx, [rbp+0C0h+var_80]
0x180046d98  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180046d9d  test    bl, bl
0x180046d9f  jz      short loc_180046E0A
0x180046da1  xor     r9d, r9d; dwMoveMethod
0x180046da4  xor     r8d, r8d; lpNewFilePointer
0x180046da7  mov     rdx, rsi; liDistanceToMove
0x180046daa  mov     rcx, [rbp+0C0h+hFile]; hFile
0x180046dae  call    cs:__imp_SetFilePointerEx
0x180046db4  test    eax, eax
0x180046db6  jz      short loc_180046E08
0x180046db8  mov     rcx, [rbp+0C0h+hFile]; hFile
0x180046dbc  call    cs:__imp_SetEndOfFile
0x180046dc2  mov     rdi, [rbp+0C0h+hFile]
0x180046dc6  xorps   xmm0, xmm0
0x180046dc9  movups  xmmword ptr [rbp+0C0h+SystemTime.wYear], xmm0
0x180046dcd  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x180046dd1  call    cs:__imp_GetSystemTime
0x180046dd7  mov     qword ptr [rsp+1C0h+FileTime.dwLowDateTime], 0
0x180046de0  lea     rdx, [rsp+1C0h+FileTime]; lpFileTime
0x180046de5  lea     rcx, [rbp+0C0h+SystemTime]; lpSystemTime
0x180046de9  call    cs:__imp_SystemTimeToFileTime
0x180046def  test    eax, eax
0x180046df1  jz      short loc_180046E0A
0x180046df3  lea     r9, [rsp+1C0h+FileTime]; lpLastWriteTime
0x180046df8  xor     r8d, r8d; lpLastAccessTime
0x180046dfb  xor     edx, edx; lpCreationTime
0x180046dfd  mov     rcx, rdi; hFile
0x180046e00  call    cs:__imp_SetFileTime
0x180046e06  jmp     short loc_180046E0A
0x180046e08  xor     bl, bl
0x180046e0a  lea     rcx, [rbp+0C0h+var_120]
0x180046e0e  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180046e13  mov     al, bl
0x180046e15  mov     rcx, [rbp+0C0h+var_30]
0x180046e1c  xor     rcx, rsp; StackCookie
0x180046e1f  call    __security_check_cookie
0x180046e24  lea     r11, [rsp+1C0h+var_20]
0x180046e2c  mov     rbx, [r11+40h]
0x180046e30  mov     rsi, [r11+48h]
0x180046e34  mov     rsp, r11
0x180046e37  pop     r14
0x180046e39  pop     r13
0x180046e3b  pop     r12
0x180046e3d  pop     rdi
0x180046e3e  pop     rbp
0x180046e3f  retn
```
