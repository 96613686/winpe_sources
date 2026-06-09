# Windows::Networking::UX::Internal::CAdapterStatistics::RuntimeClassInitialize(ushort const *)

- ea: `0x18002c508`
- end: `0x18002c75c`
- name: `?RuntimeClassInitialize@CAdapterStatistics@Internal@UX@Networking@Windows@@QEAAJPEBG@Z`
- size: `596`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterStatistics *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800532a0`

## callees

- `0x18001b1b4`
- `0x18001b1d4`
- `0x18001bdb8`
- `0x18001cb10`
- `0x180024a44`
- `0x18002c508`
- `0x18002c764`
- `0x18002cd20`
- `0x180051e58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002c6fb`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18002c6fb`
- `ntdll!NtOpenFile` at `0x18002c5d5`
- `ntdll!NtOpenFile` at `0x18002c5d5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002c658`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002c658`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterStatistics::RuntimeClassInitialize(
        Windows::Networking::UX::Internal::CAdapterStatistics *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rax
  NTSTATUS v6; // eax
  int LastError; // eax
  const char *v8; // r9
  unsigned int v9; // ebx
  unsigned __int64 v10; // rbx
  const struct _NDIS_STATISTICS_VALUE *v11; // rdi
  int v12; // eax
  unsigned __int64 v13; // rax
  int ShareAccess; // [rsp+20h] [rbp-E0h]
  unsigned int ShareAccessa; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  _DWORD InBuffer[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE OutBuffer[128]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v19 = 0;
  if ( a2 )
  {
    v4 = 0x7FFF;
    v5 = a2;
    while ( *v5 )
    {
      ++v5;
      if ( !--v4 )
        goto LABEL_7;
    }
    *((_QWORD *)&v19 + 1) = a2;
    LOWORD(v19) = -2 - 2 * v4;
    WORD1(v19) = -2 * v4;
  }
LABEL_7:
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  FileHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v6 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v6 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x44,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
                  (const char *)(unsigned int)v6,
                  ShareAccess);
LABEL_23:
    v9 = LastError;
    goto LABEL_24;
  }
  InBuffer[0] = 66055;
  InBuffer[1] = -2147417836;
  InBuffer[2] = -2147352063;
  InBuffer[3] = -2147352057;
  InBuffer[4] = -2130706433;
  BytesReturned = 0;
  if ( !DeviceIoControl(FileHandle, 0x17003Eu, InBuffer, 0x14u, OutBuffer, 0x74u, &BytesReturned, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5C,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
                  v8);
    goto LABEL_23;
  }
  if ( BytesReturned > 0x74 )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
      (const char *)0x8000FFFFLL,
      ShareAccessa);
LABEL_24:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
    return v9;
  }
  v10 = BytesReturned;
  v11 = (const struct _NDIS_STATISTICS_VALUE *)OutBuffer;
  while ( v10 >= 8 )
  {
    if ( v11->DataLength > v10 - 8 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x6B,
                    (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
                    (const char *)0xD,
                    ShareAccessa);
      goto LABEL_23;
    }
    v12 = Windows::Networking::UX::Internal::CAdapterStatistics::_UpdateFromStatisticsValue(this, v11);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
        (const char *)(unsigned int)v12,
        ShareAccessa);
    v13 = v11->DataLength + 8LL;
    if ( v10 < v13 || (v10 -= v13, v10 == -1) )
    {
      _o_terminate();
      __debugbreak();
    }
    v11 = (const struct _NDIS_STATISTICS_VALUE *)((char *)v11 + v13);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return 0;
}

```

## disassembly

```asm
0x18002c508  mov     [rsp-8+arg_8], rbx
0x18002c50d  mov     [rsp-8+arg_10], rsi
0x18002c512  push    rbp
0x18002c513  push    rdi
0x18002c514  push    r14
0x18002c516  lea     rbp, [rsp-50h]
0x18002c51b  sub     rsp, 150h
0x18002c522  mov     rax, cs:__security_cookie
0x18002c529  xor     rax, rsp
0x18002c52c  mov     [rbp+60h+var_20], rax
0x18002c530  xor     r14d, r14d
0x18002c533  xorps   xmm0, xmm0
0x18002c536  mov     r8, rdx
0x18002c539  mov     rsi, rcx
0x18002c53c  movups  [rsp+160h+var_110], xmm0
0x18002c541  test    rdx, rdx
0x18002c544  jz      short loc_18002C580
0x18002c546  mov     edx, 7FFFh
0x18002c54b  lea     ecx, [r14+2]
0x18002c54f  mov     rax, r8
0x18002c552  cmp     [rax], r14w
0x18002c556  jz      short loc_18002C563
0x18002c558  add     rax, rcx
0x18002c55b  sub     rdx, 1
0x18002c55f  jnz     short loc_18002C552
0x18002c561  jmp     short loc_18002C580
0x18002c563  add     dx, dx
0x18002c566  mov     qword ptr [rsp+160h+var_110+8], r8
0x18002c56b  mov     eax, 0FFFEh
0x18002c570  sub     ax, dx
0x18002c573  mov     word ptr [rsp+160h+var_110], ax
0x18002c578  add     ax, cx
0x18002c57b  mov     word ptr [rsp+160h+var_110+2], ax
0x18002c580  xorps   xmm0, xmm0
0x18002c583  mov     [rsp+160h+OpenOptions], 20h ; ' '; OpenOptions
0x18002c58b  lea     rax, [rsp+160h+var_110]
0x18002c590  mov     qword ptr [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x18002c599  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x18002c59d  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x18002c5a2  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x18002c5a7  mov     [rsp+160h+ObjectAttributes.RootDirectory], r14
0x18002c5ac  mov     edx, 12019Fh; DesiredAccess
0x18002c5b1  mov     qword ptr [rsp+160h+ObjectAttributes.Attributes], 40h ; '@'
0x18002c5ba  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x18002c5bf  mov     [rsp+160h+FileHandle], r14
0x18002c5c4  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c5c9  mov     [rsp+160h+ShareAccess], 7; int
0x18002c5d1  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x18002c5d5  call    cs:__imp_NtOpenFile
0x18002c5db  test    eax, eax
0x18002c5dd  jns     short loc_18002C5FC
0x18002c5df  mov     rcx, [rbp+68h]; this
0x18002c5e3  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18002c5ea  mov     r9d, eax; char *
0x18002c5ed  mov     edx, 44h ; 'D'; void *
0x18002c5f2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c5f7  jmp     loc_18002C71C
0x18002c5fc  mov     rcx, [rsp+160h+FileHandle]; hDevice
0x18002c601  lea     rax, [rsp+160h+BytesReturned]
0x18002c606  mov     [rsp+160h+lpOverlapped], r14; lpOverlapped
0x18002c60b  lea     r8, [rbp+60h+InBuffer]; lpInBuffer
0x18002c60f  mov     [rsp+160h+lpBytesReturned], rax; lpBytesReturned
0x18002c614  mov     r9d, 14h; nInBufferSize
0x18002c61a  lea     rax, [rbp+60h+OutBuffer]
0x18002c61e  mov     [rsp+160h+OpenOptions], 74h ; 't'; nOutBufferSize
0x18002c626  mov     edx, 17003Eh; dwIoControlCode
0x18002c62b  mov     qword ptr [rsp+160h+ShareAccess], rax; unsigned int
0x18002c630  mov     [rbp+60h+InBuffer], 10207h
0x18002c637  mov     [rbp+60h+var_BC], 80010114h
0x18002c63e  mov     [rbp+60h+var_B8], 80020201h
0x18002c645  mov     [rbp+60h+var_B4], 80020207h
0x18002c64c  mov     [rbp+60h+var_B0], 80FFFFFFh
0x18002c653  mov     [rsp+160h+BytesReturned], r14d
0x18002c658  call    cs:__imp_DeviceIoControl
0x18002c65e  test    eax, eax
0x18002c660  jnz     short loc_18002C67A
0x18002c662  mov     rcx, [rbp+68h]; this
0x18002c666  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18002c66d  lea     edx, [rax+5Ch]; void *
0x18002c670  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c675  jmp     loc_18002C71C
0x18002c67a  cmp     [rsp+160h+BytesReturned], 74h ; 't'
0x18002c67f  jbe     short loc_18002C6A0
0x18002c681  mov     rcx, [rbp+68h]; this
0x18002c685  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18002c68c  mov     ebx, 8000FFFFh
0x18002c691  mov     edx, 5Eh ; '^'; void *
0x18002c696  mov     r9d, ebx; char *
0x18002c699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c69e  jmp     short loc_18002C71E
0x18002c6a0  mov     ebx, [rsp+160h+BytesReturned]
0x18002c6a4  lea     rdi, [rbp+60h+OutBuffer]
0x18002c6a8  cmp     rbx, 8
0x18002c6ac  jb      short loc_18002C72C
0x18002c6ae  mov     eax, [rdi+4]
0x18002c6b1  lea     rcx, [rbx-8]
0x18002c6b5  cmp     rax, rcx
0x18002c6b8  ja      short loc_18002C702
0x18002c6ba  mov     rdx, rdi; struct _NDIS_STATISTICS_VALUE *
0x18002c6bd  mov     rcx, rsi; this
0x18002c6c0  call    ?_UpdateFromStatisticsValue@CAdapterStatistics@Internal@UX@Networking@Windows@@AEAAJAEBU_NDIS_STATISTICS_VALUE@@@Z; Windows::Networking::UX::Internal::CAdapterStatistics::_UpdateFromStatisticsValue(_NDIS_STATISTICS_VALUE const &)
0x18002c6c5  test    eax, eax
0x18002c6c7  jns     short loc_18002C6E1
0x18002c6c9  mov     rcx, [rbp+68h]; this
0x18002c6cd  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18002c6d4  mov     r9d, eax; char *
0x18002c6d7  mov     edx, 6Eh ; 'n'; void *
0x18002c6dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c6e1  mov     eax, [rdi+4]
0x18002c6e4  add     rax, 8
0x18002c6e8  cmp     rbx, rax
0x18002c6eb  jb      short loc_18002C6FB
0x18002c6ed  sub     rbx, rax
0x18002c6f0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002c6f4  jz      short loc_18002C6FB
0x18002c6f6  add     rdi, rax
0x18002c6f9  jmp     short loc_18002C6A8
0x18002c6fb  call    cs:__imp__o_terminate
0x18002c701  int     3; Trap to Debugger
0x18002c702  mov     rcx, [rbp+68h]; this
0x18002c706  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18002c70d  mov     r9d, 0Dh; char *
0x18002c713  lea     edx, [r9+5Eh]; void *
0x18002c717  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c71c  mov     ebx, eax
0x18002c71e  lea     rcx, [rsp+160h+FileHandle]
0x18002c723  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c728  mov     eax, ebx
0x18002c72a  jmp     short loc_18002C738
0x18002c72c  lea     rcx, [rsp+160h+FileHandle]
0x18002c731  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c736  xor     eax, eax
0x18002c738  mov     rcx, [rbp+60h+var_20]
0x18002c73c  xor     rcx, rsp; StackCookie
0x18002c73f  call    __security_check_cookie
0x18002c744  lea     r11, [rsp+160h+var_10]
0x18002c74c  mov     rbx, [r11+28h]
0x18002c750  mov     rsi, [r11+30h]
0x18002c754  mov     rsp, r11
0x18002c757  pop     r14
0x18002c759  pop     rdi
0x18002c75a  pop     rbp
0x18002c75b  retn
```
