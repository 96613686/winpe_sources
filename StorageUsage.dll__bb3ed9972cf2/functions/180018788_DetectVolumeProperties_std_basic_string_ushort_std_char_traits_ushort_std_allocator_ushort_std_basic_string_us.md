# DetectVolumeProperties(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_ULARGE_INTEGER &,_ULARGE_INTEGER &,unsigned __int64 &,unsigned __int64 &)

- ea: `0x180018788`
- end: `0x180018a07`
- name: `?DetectVolumeProperties@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAT_ULARGE_INTEGER@@1AEA_K2@Z`
- size: `639`
- prototype: `__int64 __fastcall(__int64, __int64, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180018a10`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180016df8`
- `0x180016f6c`
- `0x180016fd4`
- `0x180018788`
- `0x18001eeac`
- `0x18001ef0c`
- `0x18001eff0`
- `0x18001f108`
- `0x18001f1c8`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001881a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001881a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188b8`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001896a`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001896a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18001890a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18001890a`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001899a`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001899a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DetectVolumeProperties(
        __int64 a1,
        __int64 a2,
        union _ULARGE_INTEGER *a3,
        union _ULARGE_INTEGER *a4,
        _QWORD *a5,
        __int64 *a6)
{
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rax
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  const WCHAR *v20; // rax
  BOOL DiskFreeSpace; // ebx
  NTSTATUS v22; // eax
  __int64 v23; // rdx
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE FsInformation[48]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  unsigned int v31; // [rsp+F8h] [rbp-8h]
  unsigned int v32; // [rsp+FCh] [rbp-4h]
  WCHAR VolumeNameBuffer[264]; // [rsp+100h] [rbp+0h] BYREF

  IoStatusBlock = 0;
  memset_0(FsInformation, 0, 0x60u);
  memset_0(VolumeNameBuffer, 0, 0x208u);
  if ( !*(_QWORD *)(a1 + 16) )
    return (unsigned int)-2147024809;
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(a1) )
    v12 = *(_QWORD *)a1;
  else
    v12 = a1;
  if ( *(_WORD *)(v12 + 2 * v11) == 92 )
  {
    memset(v26, 0, sizeof(v26));
    v13 = ((__int64 (*)(void))std::_String_val<std::_Simple_types<unsigned short>>::_Myptr)();
    std::wstring::_Construct<1,unsigned short const *>(v26, v13);
    if ( (_OWORD *)a1 != v26 )
    {
      std::wstring::_Tidy_deallocate(a1);
      std::wstring::_Take_contents(a1, v26);
    }
    std::wstring::_Tidy_deallocate((__int64)v26);
  }
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  FileW = CreateFileW(v14, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
    CloseHandle(FileW);
    return v10;
  }
  if ( GetVolumeInformationByHandleW(FileW, VolumeNameBuffer, 0x104u, 0, 0, 0, 0, 0)
    && (v18 = std::_WChar_traits<unsigned short>::length(VolumeNameBuffer),
        std::wstring::_Assign<unsigned short>(a2, VolumeNameBuffer, v18),
        v19 = std::operator+<unsigned short>(v27, a1),
        v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19),
        DiskFreeSpace = GetDiskFreeSpaceExW(v20, 0, a3, a4),
        std::wstring::_Tidy_deallocate((__int64)v27),
        DiskFreeSpace) )
  {
    v22 = NtQueryVolumeInformationFile(
            FileW,
            &IoStatusBlock,
            FsInformation,
            0x60u,
            FileFsMaximumInformation|FileFsDeviceInformation);
    v10 = v22 | 0x10000000;
    if ( v22 >= 0 )
    {
      v23 = v31 * v32 * (v29 + v30);
      *a5 = v29 * v31 * (unsigned __int64)v32;
      *a6 = v23;
    }
  }
  else
  {
    v17 = GetLastError();
    v10 = v17;
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
  }
  if ( FileW )
    goto LABEL_20;
  return v10;
}

```

## disassembly

```asm
0x180018788  push    rbp
0x18001878a  push    rbx
0x18001878b  push    rsi
0x18001878c  push    rdi
0x18001878d  push    r12
0x18001878f  push    r13
0x180018791  push    r14
0x180018793  push    r15
0x180018795  lea     rbp, [rsp-228h]
0x18001879d  sub     rsp, 328h
0x1800187a4  mov     rax, cs:__security_cookie
0x1800187ab  xor     rax, rsp
0x1800187ae  mov     [rbp+260h+var_50], rax
0x1800187b5  mov     rsi, [rbp+260h+arg_20]
0x1800187bc  mov     r15, rdx
0x1800187bf  mov     r14, [rbp+260h+arg_28]
0x1800187c6  xor     edx, edx; Val
0x1800187c8  mov     r12, r8
0x1800187cb  mov     rbx, rcx
0x1800187ce  xorps   xmm0, xmm0
0x1800187d1  lea     rcx, [rbp+260h+FsInformation]; void *
0x1800187d5  mov     r13, r9
0x1800187d8  lea     r8d, [rdx+60h]; Size
0x1800187dc  movups  xmmword ptr [rsp+360h+IoStatusBlock], xmm0
0x1800187e1  call    memset_0
0x1800187e6  xor     edx, edx; Val
0x1800187e8  lea     rcx, [rbp+260h+VolumeNameBuffer]; void *
0x1800187ec  mov     r8d, 208h; Size
0x1800187f2  call    memset_0
0x1800187f7  mov     rax, [rbx+10h]
0x1800187fb  test    rax, rax
0x1800187fe  jnz     short loc_18001880A
0x180018800  mov     ebx, 80070057h
0x180018805  jmp     loc_1800189E2
0x18001880a  lea     r8, [rax-1]
0x18001880e  cmp     rax, r8
0x180018811  ja      short loc_180018821
0x180018813  lea     rcx, aInvalidStringP; "invalid string position"
0x18001881a  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180018820  int     3; Trap to Debugger
0x180018821  mov     rcx, rbx
0x180018824  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x180018829  test    al, al
0x18001882b  jz      short loc_180018832
0x18001882d  mov     rax, [rbx]
0x180018830  jmp     short loc_180018835
0x180018832  mov     rax, rbx
0x180018835  cmp     word ptr [rax+r8*2], 5Ch ; '\'
0x18001883b  jnz     short loc_180018889
0x18001883d  xorps   xmm0, xmm0
0x180018840  xorps   xmm1, xmm1
0x180018843  movups  [rsp+360h+var_308], xmm0
0x180018848  movdqu  [rsp+360h+var_2F8], xmm1
0x18001884e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018853  mov     rdx, rax
0x180018856  lea     rcx, [rsp+360h+var_308]
0x18001885b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018860  lea     rax, [rsp+360h+var_308]
0x180018865  cmp     rbx, rax
0x180018868  jz      short loc_18001887F
0x18001886a  mov     rcx, rbx
0x18001886d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018872  lea     rdx, [rsp+360h+var_308]
0x180018877  mov     rcx, rbx
0x18001887a  call    ?_Take_contents@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x18001887f  lea     rcx, [rsp+360h+var_308]
0x180018884  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018889  mov     rcx, rbx
0x18001888c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018891  mov     [rsp+360h+hTemplateFile], 0; hTemplateFile
0x18001889a  mov     r8d, 3; dwShareMode
0x1800188a0  mov     [rsp+360h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800188a8  mov     rcx, rax; lpFileName
0x1800188ab  xor     r9d, r9d; lpSecurityAttributes
0x1800188ae  mov     [rsp+360h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800188b3  mov     edx, 80000000h; dwDesiredAccess
0x1800188b8  call    cs:__imp_CreateFileW
0x1800188be  mov     rdi, rax
0x1800188c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800188c5  jnz     short loc_1800188E5
0x1800188c7  call    cs:__imp_GetLastError
0x1800188cd  mov     ebx, eax
0x1800188cf  test    eax, eax
0x1800188d1  jle     loc_1800189D9
0x1800188d7  movzx   ebx, ax
0x1800188da  or      ebx, 80070000h
0x1800188e0  jmp     loc_1800189D9
0x1800188e5  xor     eax, eax
0x1800188e7  lea     rdx, [rbp+260h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800188eb  mov     [rsp+360h+nFileSystemNameSize], eax; nFileSystemNameSize
0x1800188ef  xor     r9d, r9d; lpVolumeSerialNumber
0x1800188f2  mov     [rsp+360h+hTemplateFile], rax; lpFileSystemNameBuffer
0x1800188f7  mov     r8d, 104h; nVolumeNameSize
0x1800188fd  mov     qword ptr [rsp+360h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x180018902  mov     rcx, rdi; hFile
0x180018905  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; lpMaximumComponentLength
0x18001890a  call    cs:__imp_GetVolumeInformationByHandleW
0x180018910  test    eax, eax
0x180018912  jnz     short loc_180018932
0x180018914  call    cs:__imp_GetLastError
0x18001891a  mov     ebx, eax
0x18001891c  test    eax, eax
0x18001891e  jle     loc_1800189D4
0x180018924  movzx   ebx, ax
0x180018927  or      ebx, 80070000h
0x18001892d  jmp     loc_1800189D4
0x180018932  lea     rcx, [rbp+260h+VolumeNameBuffer]
0x180018936  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001893b  mov     r8, rax
0x18001893e  lea     rdx, [rbp+260h+VolumeNameBuffer]
0x180018942  mov     rcx, r15
0x180018945  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001894a  mov     rdx, rbx
0x18001894d  lea     rcx, [rsp+360h+var_2E8]
0x180018952  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x180018957  mov     rcx, rax
0x18001895a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001895f  mov     rcx, rax; lpDirectoryName
0x180018962  mov     r9, r13; lpTotalNumberOfFreeBytes
0x180018965  mov     r8, r12; lpTotalNumberOfBytes
0x180018968  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18001896a  call    cs:__imp_GetDiskFreeSpaceExW
0x180018970  lea     rcx, [rsp+360h+var_2E8]
0x180018975  mov     ebx, eax
0x180018977  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001897c  test    ebx, ebx
0x18001897e  jz      short loc_180018914
0x180018980  mov     r9d, 60h ; '`'; Length
0x180018986  mov     [rsp+360h+dwCreationDisposition], 0Eh; FsInformationClass
0x18001898e  lea     r8, [rbp+260h+FsInformation]; FsInformation
0x180018992  mov     rcx, rdi; FileHandle
0x180018995  lea     rdx, [rsp+360h+IoStatusBlock]; IoStatusBlock
0x18001899a  call    cs:__imp_NtQueryVolumeInformationFile
0x1800189a0  mov     ebx, eax
0x1800189a2  or      ebx, 10000000h
0x1800189a8  jl      short loc_1800189D4
0x1800189aa  mov     r8d, [rbp+260h+var_264]
0x1800189ae  mov     r9d, [rbp+260h+var_268]
0x1800189b2  mov     eax, r8d
0x1800189b5  mov     rdx, [rbp+260h+var_288]
0x1800189b9  add     rdx, [rbp+260h+var_290]
0x1800189bd  imul    rax, r9
0x1800189c1  imul    rdx, r8
0x1800189c5  imul    rax, [rbp+260h+var_290]
0x1800189ca  imul    rdx, r9
0x1800189ce  mov     [rsi], rax
0x1800189d1  mov     [r14], rdx
0x1800189d4  test    rdi, rdi
0x1800189d7  jz      short loc_1800189E2
0x1800189d9  mov     rcx, rdi; hObject
0x1800189dc  call    cs:__imp_CloseHandle
0x1800189e2  mov     eax, ebx
0x1800189e4  mov     rcx, [rbp+260h+var_50]
0x1800189eb  xor     rcx, rsp; StackCookie
0x1800189ee  call    __security_check_cookie
0x1800189f3  add     rsp, 328h
0x1800189fa  pop     r15
0x1800189fc  pop     r14
0x1800189fe  pop     r13
0x180018a00  pop     r12
0x180018a02  pop     rdi
0x180018a03  pop     rsi
0x180018a04  pop     rbx
0x180018a05  pop     rbp
0x180018a06  retn
```
