# Windows::Networking::UX::Internal::CAdapterStatistics::RuntimeClassInitialize(ushort const *)

- ea: `0x1800860ac`
- end: `0x180086312`
- name: `?RuntimeClassInitialize@CAdapterStatistics@Internal@UX@Networking@Windows@@QEAAJPEBG@Z`
- size: `614`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterStatistics *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008082c`

## callees

- `0x180003ed0`
- `0x180009794`
- `0x1800097b4`
- `0x18000bbf4`
- `0x18001668c`
- `0x18001b230`
- `0x180028984`
- `0x18005cfec`
- `0x1800860ac`
- `0x180086318`
- `0x1800865b0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180086185`
- `ntdll!NtOpenFile` at `0x180086185`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180086208`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180086208`

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
0x1800860ac  mov     [rsp-8+arg_8], rbx
0x1800860b1  mov     [rsp-8+arg_10], rsi
0x1800860b6  push    rbp
0x1800860b7  push    rdi
0x1800860b8  push    r14
0x1800860ba  lea     rbp, [rsp-50h]
0x1800860bf  sub     rsp, 150h
0x1800860c6  mov     rax, cs:__security_cookie
0x1800860cd  xor     rax, rsp
0x1800860d0  mov     [rbp+60h+var_20], rax
0x1800860d4  xor     r14d, r14d
0x1800860d7  xorps   xmm0, xmm0
0x1800860da  mov     r8, rdx
0x1800860dd  mov     rsi, rcx
0x1800860e0  movups  [rsp+160h+var_110], xmm0
0x1800860e5  test    rdx, rdx
0x1800860e8  jz      short loc_180086124
0x1800860ea  mov     edx, 7FFFh
0x1800860ef  lea     ecx, [r14+2]
0x1800860f3  mov     rax, r8
0x1800860f6  cmp     [rax], r14w
0x1800860fa  jz      short loc_180086107
0x1800860fc  add     rax, rcx
0x1800860ff  sub     rdx, 1
0x180086103  jnz     short loc_1800860F6
0x180086105  jmp     short loc_180086124
0x180086107  add     dx, dx
0x18008610a  mov     qword ptr [rsp+160h+var_110+8], r8
0x18008610f  mov     eax, 0FFFEh
0x180086114  sub     ax, dx
0x180086117  mov     word ptr [rsp+160h+var_110], ax
0x18008611c  add     ax, cx
0x18008611f  mov     word ptr [rsp+160h+var_110+2], ax
0x180086124  xorps   xmm0, xmm0
0x180086127  mov     [rsp+160h+FileHandle], r14
0x18008612c  lea     rax, [rsp+160h+var_110]
0x180086131  mov     qword ptr [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x18008613a  xor     edx, edx
0x18008613c  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x180086141  lea     rcx, [rsp+160h+FileHandle]
0x180086146  mov     [rsp+160h+ObjectAttributes.RootDirectory], r14
0x18008614b  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180086150  mov     qword ptr [rsp+160h+ObjectAttributes.Attributes], 40h ; '@'
0x180086159  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x18008615d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180086162  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180086166  mov     [rsp+160h+OpenOptions], 20h ; ' '; OpenOptions
0x18008616e  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x180086173  mov     [rsp+160h+ShareAccess], 7; int
0x18008617b  mov     edx, 12019Fh; DesiredAccess
0x180086180  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180086185  call    cs:__imp_NtOpenFile
0x18008618b  test    eax, eax
0x18008618d  jns     short loc_1800861AC
0x18008618f  mov     rcx, [rbp+68h]; this
0x180086193  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18008619a  mov     r9d, eax; char *
0x18008619d  mov     edx, 44h ; 'D'; void *
0x1800861a2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800861a7  jmp     loc_1800862FC
0x1800861ac  mov     rcx, [rsp+160h+FileHandle]; hDevice
0x1800861b1  lea     rax, [rsp+160h+BytesReturned]
0x1800861b6  mov     [rsp+160h+lpOverlapped], r14; lpOverlapped
0x1800861bb  lea     r8, [rbp+60h+InBuffer]; lpInBuffer
0x1800861bf  mov     [rsp+160h+lpBytesReturned], rax; lpBytesReturned
0x1800861c4  mov     r9d, 14h; nInBufferSize
0x1800861ca  lea     rax, [rbp+60h+OutBuffer]
0x1800861ce  mov     [rsp+160h+OpenOptions], 74h ; 't'; nOutBufferSize
0x1800861d6  mov     edx, 17003Eh; dwIoControlCode
0x1800861db  mov     qword ptr [rsp+160h+ShareAccess], rax; unsigned int
0x1800861e0  mov     [rbp+60h+InBuffer], 10207h
0x1800861e7  mov     [rbp+60h+var_BC], 80010114h
0x1800861ee  mov     [rbp+60h+var_B8], 80020201h
0x1800861f5  mov     [rbp+60h+var_B4], 80020207h
0x1800861fc  mov     [rbp+60h+var_B0], 80FFFFFFh
0x180086203  mov     [rsp+160h+BytesReturned], r14d
0x180086208  call    cs:__imp_DeviceIoControl
0x18008620e  test    eax, eax
0x180086210  jnz     short loc_18008622A
0x180086212  mov     rcx, [rbp+68h]; this
0x180086216  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18008621d  lea     edx, [rax+5Ch]; void *
0x180086220  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086225  jmp     loc_1800862FC
0x18008622a  cmp     [rsp+160h+BytesReturned], 74h ; 't'
0x18008622f  jbe     short loc_180086253
0x180086231  mov     rcx, [rbp+68h]; this
0x180086235  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18008623c  mov     ebx, 8000FFFFh
0x180086241  mov     edx, 5Eh ; '^'; void *
0x180086246  mov     r9d, ebx; char *
0x180086249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008624e  jmp     loc_1800862FE
0x180086253  mov     ebx, [rsp+160h+BytesReturned]
0x180086257  cmp     rbx, 8
0x18008625b  jb      short loc_1800862B2
0x18008625d  lea     rdi, [rbp+60h+OutBuffer]
0x180086261  mov     eax, [rdi+4]
0x180086264  lea     rcx, [rbx-8]
0x180086268  cmp     rax, rcx
0x18008626b  ja      short loc_1800862E2
0x18008626d  mov     rdx, rdi; struct _NDIS_STATISTICS_VALUE *
0x180086270  mov     rcx, rsi; this
0x180086273  call    ?_UpdateFromStatisticsValue@CAdapterStatistics@Internal@UX@Networking@Windows@@AEAAJAEBU_NDIS_STATISTICS_VALUE@@@Z; Windows::Networking::UX::Internal::CAdapterStatistics::_UpdateFromStatisticsValue(_NDIS_STATISTICS_VALUE const &)
0x180086278  test    eax, eax
0x18008627a  jns     short loc_180086294
0x18008627c  mov     rcx, [rbp+68h]; this
0x180086280  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180086287  mov     r9d, eax; char *
0x18008628a  mov     edx, 6Eh ; 'n'; void *
0x18008628f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086294  mov     eax, [rdi+4]
0x180086297  add     rax, 8
0x18008629b  cmp     rbx, rax
0x18008629e  jb      short loc_18008630C
0x1800862a0  sub     rbx, rax
0x1800862a3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800862a7  jz      short loc_18008630C
0x1800862a9  add     rdi, rax
0x1800862ac  cmp     rbx, 8
0x1800862b0  jnb     short loc_180086261
0x1800862b2  lea     rcx, [rsp+160h+FileHandle]
0x1800862b7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800862bc  xor     eax, eax
0x1800862be  mov     rcx, [rbp+60h+var_20]
0x1800862c2  xor     rcx, rsp; StackCookie
0x1800862c5  call    __security_check_cookie
0x1800862ca  lea     r11, [rsp+160h+var_10]
0x1800862d2  mov     rbx, [r11+28h]
0x1800862d6  mov     rsi, [r11+30h]
0x1800862da  mov     rsp, r11
0x1800862dd  pop     r14
0x1800862df  pop     rdi
0x1800862e0  pop     rbp
0x1800862e1  retn
0x1800862e2  mov     rcx, [rbp+68h]; this
0x1800862e6  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800862ed  mov     r9d, 0Dh; char *
0x1800862f3  lea     edx, [r9+5Eh]; void *
0x1800862f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800862fc  mov     ebx, eax
0x1800862fe  lea     rcx, [rsp+160h+FileHandle]
0x180086303  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086308  mov     eax, ebx
0x18008630a  jmp     short loc_1800862BE
0x18008630c  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
