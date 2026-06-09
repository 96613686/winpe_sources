# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId(void *,__int64,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x18011fcb0`
- end: `0x18011fea4`
- name: `?GetPathFromFileId@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJPEAX_JPEAV?$Auto@U_LUNICODE_STRING@@@4@@Z`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x18011f408`
- `0x18011fcb0`

## import_xrefs

- `ntdll!NtClose` at `0x18011fdf6`
- `ntdll!NtClose` at `0x18011fe37`
- `ntdll!NtClose` at `0x18011fe64`
- `ntdll!NtClose` at `0x18011fdf6`
- `ntdll!NtClose` at `0x18011fe37`
- `ntdll!NtClose` at `0x18011fe64`
- `ntdll!NtOpenFile` at `0x18011fd99`
- `ntdll!NtOpenFile` at `0x18011fd99`

## string_xrefs

- `0x18011fcf4`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId`
- `0x18011fdb6`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId`
- `0x18011fdc9`: `::NtOpenFile( File.GetInitPointer(), ( 0x0080 ) | (0x00100000L), &ObjectAttributes, &IoStatusBlock, (0x00000001|0x00000002|0x00000004), 0x00000020 | 0x00004000 | 0x00200000 | 0x00002000)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  NTSTATUS ObjectNameFromHandle; // ebx
  _QWORD v5[4]; // [rsp+38h] [rbp-69h] BYREF
  _QWORD v6[5]; // [rsp+58h] [rbp-49h] BYREF
  _QWORD v7[2]; // [rsp+80h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-11h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+1Fh] BYREF
  __int64 v10; // [rsp+C8h] [rbp+27h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp+2Fh] BYREF

  v6[4] = -2;
  v10 = a3;
  if ( *(_BYTE *)(a2 + 16) )
  {
    v5[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v5[1] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId";
    v5[2] = 5007;
    v5[3] = "!Info.IsFsTx";
    RtlReportErrorOrigination(v5, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  v7[0] = 524296;
  v7[1] = &v10;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = *(HANDLE *)a2;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  ObjectNameFromHandle = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x206020u);
  if ( ObjectNameFromHandle < 0 )
  {
    v6[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v6[1] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::GetPathFromFileId";
    v6[2] = 5025;
    v6[3] = "::NtOpenFile( File.GetInitPointer(), ( 0x0080 ) | (0x00100000L), &ObjectAttributes, &IoStatusBlock, (0x00000"
            "001|0x00000002|0x00000004), 0x00000020 | 0x00004000 | 0x00200000 | 0x00002000)";
    RtlReportErrorOrigination(v6, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ObjectNameFromHandle);
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return (unsigned int)ObjectNameFromHandle;
  }
  ObjectNameFromHandle = Windows::Rtl::SystemImplementation::DirectGetObjectNameFromHandle(FileHandle);
  if ( ObjectNameFromHandle < 0 )
  {
    if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(FileHandle) < 0 )
        __fastfail(7u);
      FileHandle = 0;
    }
    return (unsigned int)ObjectNameFromHandle;
  }
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(FileHandle) < 0 )
      __fastfail(7u);
    FileHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18011fcb0  mov     rax, rsp
0x18011fcb3  push    rbp
0x18011fcb4  push    rdi
0x18011fcb5  push    r14
0x18011fcb7  lea     rbp, [rax-5Fh]
0x18011fcbb  sub     rsp, 0E0h
0x18011fcc2  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x18011fcca  mov     [rax+8], rbx
0x18011fcce  mov     rax, cs:__security_cookie
0x18011fcd5  xor     rax, rsp
0x18011fcd8  mov     [rbp+57h+var_18], rax
0x18011fcdc  mov     rdi, r9
0x18011fcdf  mov     [rbp+57h+var_30], r8
0x18011fce3  cmp     byte ptr [rdx+10h], 0
0x18011fce7  jz      short loc_18011FD32
0x18011fce9  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18011fcf0  mov     [rbp+57h+var_C0], rax
0x18011fcf4  lea     rax, aWindowsRtlSyst_185; "Windows::Rtl::SystemImplementation::Dir"...
0x18011fcfb  mov     [rbp+57h+var_B8], rax
0x18011fcff  mov     [rbp+57h+var_B0], 138Fh
0x18011fd07  lea     rax, aInfoIsfstx; "!Info.IsFsTx"
0x18011fd0e  mov     [rbp+57h+var_A8], rax
0x18011fd12  mov     r8d, 0C000000Dh
0x18011fd18  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18011fd1f  lea     rcx, [rbp+57h+var_C0]
0x18011fd23  call    RtlReportErrorOrigination
0x18011fd28  mov     eax, 0C000000Dh
0x18011fd2d  jmp     loc_18011FE83
0x18011fd32  mov     [rbp+57h+var_78], 80008h
0x18011fd3a  lea     rax, [rbp+57h+var_30]
0x18011fd3e  mov     [rbp+57h+var_70], rax
0x18011fd42  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18011fd4a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18011fd52  mov     rax, [rdx]
0x18011fd55  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18011fd59  lea     rax, [rbp+57h+var_78]
0x18011fd5d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18011fd61  xorps   xmm0, xmm0
0x18011fd64  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18011fd69  mov     [rbp+57h+FileHandle], 0
0x18011fd71  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18011fd75  mov     dword ptr [rsp+28h], 206020h; OpenOptions
0x18011fd7d  mov     r14d, 7
0x18011fd83  mov     [rsp+0F0h+ShareAccess], r14d; ShareAccess
0x18011fd88  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18011fd8c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18011fd90  mov     edx, 100080h; DesiredAccess
0x18011fd95  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18011fd99  call    cs:__imp_NtOpenFile
0x18011fda0  nop     dword ptr [rax+rax+00h]
0x18011fda5  mov     ebx, eax
0x18011fda7  test    eax, eax
0x18011fda9  jns     short loc_18011FE17
0x18011fdab  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18011fdb2  mov     [rbp+57h+var_A0], rax
0x18011fdb6  lea     rax, aWindowsRtlSyst_185; "Windows::Rtl::SystemImplementation::Dir"...
0x18011fdbd  mov     [rbp+57h+var_98], rax
0x18011fdc1  mov     [rbp+57h+var_90], 13A1h
0x18011fdc9  lea     rax, aNtopenfileFile; "::NtOpenFile( File.GetInitPointer(), ( "...
0x18011fdd0  mov     [rbp+57h+var_88], rax
0x18011fdd4  mov     r8d, ebx
0x18011fdd7  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18011fdde  lea     rcx, [rbp+57h+var_A0]
0x18011fde2  call    RtlReportErrorOrigination
0x18011fde7  nop
0x18011fde8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18011fdec  lea     rax, [rcx-1]
0x18011fdf0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18011fdf4  ja      short loc_18011FE13
0x18011fdf6  call    cs:__imp_NtClose
0x18011fdfd  nop     dword ptr [rax+rax+00h]
0x18011fe02  test    eax, eax
0x18011fe04  jns     short loc_18011FE0B
0x18011fe06  mov     ecx, r14d
0x18011fe09  int     29h; Win8: RtlFailFast(ecx)
0x18011fe0b  mov     [rbp+57h+FileHandle], 0
0x18011fe13  mov     eax, ebx
0x18011fe15  jmp     short loc_18011FE83
0x18011fe17  mov     rdx, rdi
0x18011fe1a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18011fe1e  call    ?DirectGetObjectNameFromHandle@SystemImplementation@Rtl@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@3@@Z; Windows::Rtl::SystemImplementation::DirectGetObjectNameFromHandle(void *,Windows::Auto<_LUNICODE_STRING> *)
0x18011fe23  mov     ebx, eax
0x18011fe25  test    eax, eax
0x18011fe27  jns     short loc_18011FE56
0x18011fe29  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18011fe2d  lea     rdx, [rcx-1]
0x18011fe31  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18011fe35  ja      short loc_18011FE54
0x18011fe37  call    cs:__imp_NtClose
0x18011fe3e  nop     dword ptr [rax+rax+00h]
0x18011fe43  test    eax, eax
0x18011fe45  jns     short loc_18011FE4C
0x18011fe47  mov     rcx, r14
0x18011fe4a  int     29h; Win8: RtlFailFast(ecx)
0x18011fe4c  mov     [rbp+57h+FileHandle], 0
0x18011fe54  jmp     short loc_18011FE13
0x18011fe56  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18011fe5a  lea     rax, [rcx-1]
0x18011fe5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18011fe62  ja      short loc_18011FE81
0x18011fe64  call    cs:__imp_NtClose
0x18011fe6b  nop     dword ptr [rax+rax+00h]
0x18011fe70  test    eax, eax
0x18011fe72  jns     short loc_18011FE79
0x18011fe74  mov     rcx, r14
0x18011fe77  int     29h; Win8: RtlFailFast(ecx)
0x18011fe79  mov     [rbp+57h+FileHandle], 0
0x18011fe81  xor     eax, eax
0x18011fe83  mov     rcx, [rbp+57h+var_18]
0x18011fe87  xor     rcx, rsp; StackCookie
0x18011fe8a  call    __security_check_cookie
0x18011fe8f  mov     rbx, [rsp+0F0h+arg_0]
0x18011fe97  add     rsp, 0E0h
0x18011fe9e  pop     r14
0x18011fea0  pop     rdi
0x18011fea1  pop     rbp
0x18011fea2  retn
```
