# Windows::Networking::UX::Internal::CAdapterStatistics::RuntimeClassInitialize(ushort const *)

- ea: `0x18004411c`
- end: `0x180044382`
- name: `?RuntimeClassInitialize@CAdapterStatistics@Internal@UX@Networking@Windows@@QEAAJPEBG@Z`
- size: `614`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterStatistics *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040cfc`

## callees

- `0x180002520`
- `0x18000e768`
- `0x180011c34`
- `0x18001916c`
- `0x18001918c`
- `0x18001a2d0`
- `0x18001ab7c`
- `0x180030678`
- `0x18004411c`
- `0x180044388`
- `0x180044620`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800441f5`
- `ntdll!NtOpenFile` at `0x1800441f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180044278`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180044278`

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
  gsl::details *v13; // rcx
  unsigned __int64 v14; // rax
  int ShareAccess; // [rsp+20h] [rbp-E0h]
  unsigned int ShareAccessa; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  _DWORD InBuffer[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE OutBuffer[128]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v20 = 0;
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
    *((_QWORD *)&v20 + 1) = a2;
    LOWORD(v20) = -2 - 2 * v4;
    WORD1(v20) = -2 * v4;
  }
LABEL_7:
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &FileHandle,
    0);
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
  if ( BytesReturned <= 0x74 )
  {
    v10 = BytesReturned;
    if ( BytesReturned < 8uLL )
    {
LABEL_21:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
      return 0;
    }
    v11 = (const struct _NDIS_STATISTICS_VALUE *)OutBuffer;
    while ( v11->DataLength <= v10 - 8 )
    {
      v12 = Windows::Networking::UX::Internal::CAdapterStatistics::_UpdateFromStatisticsValue(this, v11);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
          (const char *)(unsigned int)v12,
          ShareAccessa);
      v14 = v11->DataLength + 8LL;
      if ( v10 < v14 || (v10 -= v14, v10 == -1) )
        gsl::details::terminate(v13);
      v11 = (const struct _NDIS_STATISTICS_VALUE *)((char *)v11 + v14);
      if ( v10 < 8 )
        goto LABEL_21;
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x6B,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterstatistics.cpp",
                  (const char *)0xD,
                  ShareAccessa);
    goto LABEL_23;
  }
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

```

## disassembly

```asm
0x18004411c  mov     [rsp-8+arg_8], rbx
0x180044121  mov     [rsp-8+arg_10], rsi
0x180044126  push    rbp
0x180044127  push    rdi
0x180044128  push    r14
0x18004412a  lea     rbp, [rsp-50h]
0x18004412f  sub     rsp, 150h
0x180044136  mov     rax, cs:__security_cookie
0x18004413d  xor     rax, rsp
0x180044140  mov     [rbp+60h+var_20], rax
0x180044144  xor     r14d, r14d
0x180044147  xorps   xmm0, xmm0
0x18004414a  mov     r8, rdx
0x18004414d  mov     rsi, rcx
0x180044150  movups  [rsp+160h+var_110], xmm0
0x180044155  test    rdx, rdx
0x180044158  jz      short loc_180044194
0x18004415a  mov     edx, 7FFFh
0x18004415f  lea     ecx, [r14+2]
0x180044163  mov     rax, r8
0x180044166  cmp     [rax], r14w
0x18004416a  jz      short loc_180044177
0x18004416c  add     rax, rcx
0x18004416f  sub     rdx, 1
0x180044173  jnz     short loc_180044166
0x180044175  jmp     short loc_180044194
0x180044177  add     dx, dx
0x18004417a  mov     qword ptr [rsp+160h+var_110+8], r8
0x18004417f  mov     eax, 0FFFEh
0x180044184  sub     ax, dx
0x180044187  mov     word ptr [rsp+160h+var_110], ax
0x18004418c  add     ax, cx
0x18004418f  mov     word ptr [rsp+160h+var_110+2], ax
0x180044194  xorps   xmm0, xmm0
0x180044197  mov     [rsp+160h+FileHandle], r14
0x18004419c  lea     rax, [rsp+160h+var_110]
0x1800441a1  mov     qword ptr [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x1800441aa  xor     edx, edx
0x1800441ac  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x1800441b1  lea     rcx, [rsp+160h+FileHandle]
0x1800441b6  mov     [rsp+160h+ObjectAttributes.RootDirectory], r14
0x1800441bb  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800441c0  mov     qword ptr [rsp+160h+ObjectAttributes.Attributes], 40h ; '@'
0x1800441c9  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1800441cd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800441d2  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x1800441d6  mov     [rsp+160h+OpenOptions], 20h ; ' '; OpenOptions
0x1800441de  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x1800441e3  mov     [rsp+160h+ShareAccess], 7; int
0x1800441eb  mov     edx, 12019Fh; DesiredAccess
0x1800441f0  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x1800441f5  call    cs:__imp_NtOpenFile
0x1800441fb  test    eax, eax
0x1800441fd  jns     short loc_18004421C
0x1800441ff  mov     rcx, [rbp+68h]; this
0x180044203  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18004420a  mov     r9d, eax; char *
0x18004420d  mov     edx, 44h ; 'D'; void *
0x180044212  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180044217  jmp     loc_18004436C
0x18004421c  mov     rcx, [rsp+160h+FileHandle]; hDevice
0x180044221  lea     rax, [rsp+160h+BytesReturned]
0x180044226  mov     [rsp+160h+lpOverlapped], r14; lpOverlapped
0x18004422b  lea     r8, [rbp+60h+InBuffer]; lpInBuffer
0x18004422f  mov     [rsp+160h+lpBytesReturned], rax; lpBytesReturned
0x180044234  mov     r9d, 14h; nInBufferSize
0x18004423a  lea     rax, [rbp+60h+OutBuffer]
0x18004423e  mov     [rsp+160h+OpenOptions], 74h ; 't'; nOutBufferSize
0x180044246  mov     edx, 17003Eh; dwIoControlCode
0x18004424b  mov     qword ptr [rsp+160h+ShareAccess], rax; unsigned int
0x180044250  mov     [rbp+60h+InBuffer], 10207h
0x180044257  mov     [rbp+60h+var_BC], 80010114h
0x18004425e  mov     [rbp+60h+var_B8], 80020201h
0x180044265  mov     [rbp+60h+var_B4], 80020207h
0x18004426c  mov     [rbp+60h+var_B0], 80FFFFFFh
0x180044273  mov     [rsp+160h+BytesReturned], r14d
0x180044278  call    cs:__imp_DeviceIoControl
0x18004427e  test    eax, eax
0x180044280  jnz     short loc_18004429A
0x180044282  mov     rcx, [rbp+68h]; this
0x180044286  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18004428d  lea     edx, [rax+5Ch]; void *
0x180044290  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044295  jmp     loc_18004436C
0x18004429a  cmp     [rsp+160h+BytesReturned], 74h ; 't'
0x18004429f  jbe     short loc_1800442C3
0x1800442a1  mov     rcx, [rbp+68h]; this
0x1800442a5  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800442ac  mov     ebx, 8000FFFFh
0x1800442b1  mov     edx, 5Eh ; '^'; void *
0x1800442b6  mov     r9d, ebx; char *
0x1800442b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442be  jmp     loc_18004436E
0x1800442c3  mov     ebx, [rsp+160h+BytesReturned]
0x1800442c7  cmp     rbx, 8
0x1800442cb  jb      short loc_180044322
0x1800442cd  lea     rdi, [rbp+60h+OutBuffer]
0x1800442d1  mov     eax, [rdi+4]
0x1800442d4  lea     rcx, [rbx-8]
0x1800442d8  cmp     rax, rcx
0x1800442db  ja      short loc_180044352
0x1800442dd  mov     rdx, rdi; struct _NDIS_STATISTICS_VALUE *
0x1800442e0  mov     rcx, rsi; this
0x1800442e3  call    ?_UpdateFromStatisticsValue@CAdapterStatistics@Internal@UX@Networking@Windows@@AEAAJAEBU_NDIS_STATISTICS_VALUE@@@Z; Windows::Networking::UX::Internal::CAdapterStatistics::_UpdateFromStatisticsValue(_NDIS_STATISTICS_VALUE const &)
0x1800442e8  test    eax, eax
0x1800442ea  jns     short loc_180044304
0x1800442ec  mov     rcx, [rbp+68h]; this
0x1800442f0  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800442f7  mov     r9d, eax; char *
0x1800442fa  mov     edx, 6Eh ; 'n'; void *
0x1800442ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044304  mov     eax, [rdi+4]
0x180044307  add     rax, 8
0x18004430b  cmp     rbx, rax
0x18004430e  jb      short loc_18004437C
0x180044310  sub     rbx, rax
0x180044313  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180044317  jz      short loc_18004437C
0x180044319  add     rdi, rax
0x18004431c  cmp     rbx, 8
0x180044320  jnb     short loc_1800442D1
0x180044322  lea     rcx, [rsp+160h+FileHandle]
0x180044327  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004432c  xor     eax, eax
0x18004432e  mov     rcx, [rbp+60h+var_20]
0x180044332  xor     rcx, rsp; StackCookie
0x180044335  call    __security_check_cookie
0x18004433a  lea     r11, [rsp+160h+var_10]
0x180044342  mov     rbx, [r11+28h]
0x180044346  mov     rsi, [r11+30h]
0x18004434a  mov     rsp, r11
0x18004434d  pop     r14
0x18004434f  pop     rdi
0x180044350  pop     rbp
0x180044351  retn
0x180044352  mov     rcx, [rbp+68h]; this
0x180044356  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18004435d  mov     r9d, 0Dh; char *
0x180044363  lea     edx, [r9+5Eh]; void *
0x180044367  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004436c  mov     ebx, eax
0x18004436e  lea     rcx, [rsp+160h+FileHandle]
0x180044373  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180044378  mov     eax, ebx
0x18004437a  jmp     short loc_18004432E
0x18004437c  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
