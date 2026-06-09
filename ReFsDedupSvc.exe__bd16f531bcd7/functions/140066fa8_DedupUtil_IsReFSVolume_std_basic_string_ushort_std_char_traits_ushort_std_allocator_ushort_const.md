# DedupUtil::IsReFSVolume(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140066fa8`
- end: `0x14006729f`
- name: `?IsReFSVolume@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1400793e8`

## callees

- `0x140004870`
- `0x140015f60`
- `0x140019504`
- `0x140019600`
- `0x14001983c`
- `0x1400198e4`
- `0x14001c194`
- `0x140063d48`
- `0x140063dd8`
- `0x1400667a0`
- `0x140066fa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400670a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400670cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400670a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400670cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140067271`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140067271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067232`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140067046`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140067046`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140067153`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140067153`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140067222`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140067222`

## string_xrefs

- `0x14006707d`: `Failed to query file system type for path %s, error = 0x%x\n`
- `0x14006724a`: `Unable to query downlevel volume for path %s, error = 0x%x\n`
- `0x140067189`: `Unable to create volume handle for path %s, error = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall DedupUtil::IsReFSVolume(__int64 a1)
{
  WCHAR *lpFileSystemNameBuffer; // rax
  LPCWSTR v3; // r10
  __int64 v4; // rcx
  char v5; // bl
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  HANDLE FileW; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  DWORD LastError; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  DWORD FileSystemFlags; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nFileSystemNameSize[4]; // [rsp+70h] [rbp-90h]
  _BYTE v23[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  _BYTE OutBuffer[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v26; // [rsp+A8h] [rbp-58h]
  _BYTE v27[532]; // [rsp+ACh] [rbp-54h] BYREF

  FileSystemFlags = 0;
  std::wstring::wstring(v21);
  if ( *(_QWORD *)nFileSystemNameSize < 0x105u )
    std::wstring::append(v21, 261LL - *(_QWORD *)nFileSystemNameSize);
  else
    std::wstring::_Eos(v21);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  lpFileSystemNameBuffer = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  if ( GetVolumeInformationW(v3, 0, 0, 0, 0, &FileSystemFlags, lpFileSystemNameBuffer, nFileSystemNameSize[0]) )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    if ( !(unsigned int)_o__wcsicmp(v6, L"ReFS") )
    {
LABEL_7:
      v5 = 1;
      goto LABEL_17;
    }
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    if ( (unsigned int)_o__wcsicmp(v7, L"CSVFS") )
    {
LABEL_16:
      v5 = 0;
      goto LABEL_17;
    }
    DedupUtil::GetVolumeGuid((__int64)v23, a1, 0);
    if ( !v24 )
    {
      LastError = 87;
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      DedupUtil::Print<unsigned short const *,long>(v9, v8, &v17, &LastError);
LABEL_15:
      std::wstring::_Tidy_deallocate(v23);
      goto LABEL_16;
    }
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    FileW = CreateFileW(v10, 0x80000000, 3u, 0, 3u, 0, 0);
    v17 = (__int64)FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      BytesReturned = 0;
      if ( DeviceIoControl(FileW, 0x902C0u, 0, 0, OutBuffer, 0x218u, &BytesReturned, 0) )
      {
        if ( v26 >= 8 && !(unsigned int)_o__wcsnicmp(v27, L"ReFS", 4) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
          std::wstring::_Tidy_deallocate(v23);
          goto LABEL_7;
        }
        goto LABEL_14;
      }
      LastError = GetLastError();
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      v14 = L"Unable to query downlevel volume for path %s, error = 0x%x\n";
    }
    else
    {
      LastError = GetLastError();
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      v14 = L"Unable to create volume handle for path %s, error = 0x%x\n";
    }
    v20 = v12;
    DedupUtil::Print<unsigned short const *,unsigned long>(v13, v14, &v20, &LastError);
LABEL_14:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    goto LABEL_15;
  }
  LastError = GetLastError();
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  DedupUtil::Print<unsigned short const *,unsigned long>(
    v4,
    L"Failed to query file system type for path %s, error = 0x%x\n",
    &v17,
    &LastError);
  v5 = 0;
LABEL_17:
  std::wstring::_Tidy_deallocate(v21);
  return v5;
}

```

## disassembly

```asm
0x140066fa8  mov     [rsp-8+arg_8], rbx
0x140066fad  push    rbp
0x140066fae  lea     rbp, [rsp-1D0h]
0x140066fb6  sub     rsp, 2D0h
0x140066fbd  mov     rax, cs:__security_cookie
0x140066fc4  xor     rax, rsp
0x140066fc7  mov     [rbp+1D0h+var_10], rax
0x140066fce  mov     rbx, rcx
0x140066fd1  mov     [rsp+2D0h+FileSystemFlags], 0
0x140066fd9  lea     rcx, [rsp+2D0h+var_270]
0x140066fde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140066fe3  nop
0x140066fe4  mov     edx, 105h
0x140066fe9  lea     rcx, [rsp+2D0h+var_270]
0x140066fee  cmp     qword ptr [rsp+2D0h+var_260], rdx
0x140066ff3  jb      short loc_140066FFC
0x140066ff5  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x140066ffa  jmp     short loc_140067006
0x140066ffc  sub     rdx, qword ptr [rsp+2D0h+var_260]
0x140067001  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x140067006  mov     rcx, rbx
0x140067009  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006700e  mov     r10, rax
0x140067011  lea     rcx, [rsp+2D0h+var_270]
0x140067016  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006701b  mov     ecx, [rsp+2D0h+var_260]
0x14006701f  mov     [rsp+2D0h+nFileSystemNameSize], ecx; nFileSystemNameSize
0x140067023  mov     [rsp+2D0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x140067028  lea     rax, [rsp+2D0h+FileSystemFlags]
0x14006702d  mov     [rsp+2D0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x140067032  mov     [rsp+2D0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x14006703b  xor     r9d, r9d; lpVolumeSerialNumber
0x14006703e  xor     r8d, r8d; nVolumeNameSize
0x140067041  xor     edx, edx; lpVolumeNameBuffer
0x140067043  mov     rcx, r10; lpRootPathName
0x140067046  call    cs:__imp_GetVolumeInformationW
0x14006704d  nop     dword ptr [rax+rax+00h]
0x140067052  test    eax, eax
0x140067054  jnz     short loc_140067090
0x140067056  call    cs:__imp_GetLastError
0x14006705d  nop     dword ptr [rax+rax+00h]
0x140067062  mov     [rsp+2D0h+var_290], eax
0x140067066  mov     rcx, rbx
0x140067069  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006706e  mov     [rsp+2D0h+var_288], rax
0x140067073  lea     r9, [rsp+2D0h+var_290]
0x140067078  lea     r8, [rsp+2D0h+var_288]
0x14006707d  lea     rdx, aFailedToQueryF_0; "Failed to query file system type for pa"...
0x140067084  call    ??$Print@PEBGK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG$$QEAK@Z; DedupUtil::Print<ushort const *,ulong>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &&)
0x140067089  xor     ebx, ebx
0x14006708b  jmp     loc_1400671BB
0x140067090  lea     rcx, [rsp+2D0h+var_270]
0x140067095  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006709a  mov     rcx, rax
0x14006709d  lea     rdx, aRefs; "ReFS"
0x1400670a4  call    cs:__imp__o__wcsicmp
0x1400670ab  nop     dword ptr [rax+rax+00h]
0x1400670b0  test    eax, eax
0x1400670b2  jnz     short loc_1400670BB
0x1400670b4  mov     bl, 1
0x1400670b6  jmp     loc_1400671BB
0x1400670bb  lea     rcx, [rsp+2D0h+var_270]
0x1400670c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400670c5  mov     rcx, rax
0x1400670c8  lea     rdx, aCsvfs_0; "CSVFS"
0x1400670cf  call    cs:__imp__o__wcsicmp
0x1400670d6  nop     dword ptr [rax+rax+00h]
0x1400670db  test    eax, eax
0x1400670dd  jnz     loc_1400671B9
0x1400670e3  xor     r8d, r8d
0x1400670e6  mov     rdx, rbx
0x1400670e9  lea     rcx, [rbp+1D0h+var_250]
0x1400670ed  call    ?GetVolumeGuid@DedupUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DedupUtil::GetVolumeGuid(std::wstring const &,bool)
0x1400670f2  nop
0x1400670f3  cmp     [rbp+1D0h+var_240], 0
0x1400670f8  jnz     short loc_140067123
0x1400670fa  mov     [rsp+2D0h+var_290], 57h ; 'W'
0x140067102  mov     rcx, rbx
0x140067105  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006710a  mov     [rsp+2D0h+var_288], rax
0x14006710f  lea     r9, [rsp+2D0h+var_290]
0x140067114  lea     r8, [rsp+2D0h+var_288]
0x140067119  call    ??$Print@PEBGJ@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG$$QEAJ@Z; DedupUtil::Print<ushort const *,long>(DedupUtil::MessageType,ushort const *,ushort const * &&,long &&)
0x14006711e  jmp     loc_1400671B0
0x140067123  lea     rcx, [rbp+1D0h+var_250]
0x140067127  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006712c  mov     rcx, rax; lpFileName
0x14006712f  mov     [rsp+2D0h+lpFileSystemNameBuffer], 0; hTemplateFile
0x140067138  mov     dword ptr [rsp+2D0h+lpFileSystemFlags], 0; dwFlagsAndAttributes
0x140067140  mov     r8d, 3; dwShareMode
0x140067146  mov     dword ptr [rsp+2D0h+lpMaximumComponentLength], r8d; dwCreationDisposition
0x14006714b  xor     r9d, r9d; lpSecurityAttributes
0x14006714e  mov     edx, 80000000h; dwDesiredAccess
0x140067153  call    cs:__imp_CreateFileW
0x14006715a  nop     dword ptr [rax+rax+00h]
0x14006715f  mov     [rsp+2D0h+var_288], rax
0x140067164  lea     rcx, [rax+1]
0x140067168  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14006716f  jnz     short loc_1400671E8
0x140067171  call    cs:__imp_GetLastError
0x140067178  nop     dword ptr [rax+rax+00h]
0x14006717d  mov     [rsp+2D0h+var_290], eax
0x140067181  mov     rcx, rbx
0x140067184  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140067189  lea     rdx, aUnableToCreate; "Unable to create volume handle for path"...
0x140067190  lea     r8, [rsp+2D0h+var_278]
0x140067195  lea     r9, [rsp+2D0h+var_290]
0x14006719a  mov     [rsp+2D0h+var_278], rax
0x14006719f  call    ??$Print@PEBGK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG$$QEAK@Z; DedupUtil::Print<ushort const *,ulong>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &&)
0x1400671a4  nop
0x1400671a5  lea     rcx, [rsp+2D0h+var_288]
0x1400671aa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400671af  nop
0x1400671b0  lea     rcx, [rbp+1D0h+var_250]
0x1400671b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400671b9  xor     bl, bl
0x1400671bb  lea     rcx, [rsp+2D0h+var_270]
0x1400671c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400671c5  mov     al, bl
0x1400671c7  mov     rcx, [rbp+1D0h+var_10]
0x1400671ce  xor     rcx, rsp; StackCookie
0x1400671d1  call    __security_check_cookie
0x1400671d6  mov     rbx, [rsp+2D0h+arg_8]
0x1400671de  add     rsp, 2D0h
0x1400671e5  pop     rbp
0x1400671e6  retn
0x1400671e8  mov     [rsp+2D0h+BytesReturned], 0
0x1400671f0  mov     qword ptr [rsp+2D0h+nFileSystemNameSize], 0; lpOverlapped
0x1400671f9  lea     rcx, [rsp+2D0h+BytesReturned]
0x1400671fe  mov     [rsp+2D0h+lpFileSystemNameBuffer], rcx; lpBytesReturned
0x140067203  mov     dword ptr [rsp+2D0h+lpFileSystemFlags], 218h; nOutBufferSize
0x14006720b  lea     rcx, [rbp+1D0h+OutBuffer]
0x14006720f  mov     [rsp+2D0h+lpMaximumComponentLength], rcx; lpOutBuffer
0x140067214  xor     r9d, r9d; nInBufferSize
0x140067217  xor     r8d, r8d; lpInBuffer
0x14006721a  mov     edx, 902C0h; dwIoControlCode
0x14006721f  mov     rcx, rax; hDevice
0x140067222  call    cs:__imp_DeviceIoControl
0x140067229  nop     dword ptr [rax+rax+00h]
0x14006722e  test    eax, eax
0x140067230  jnz     short loc_140067256
0x140067232  call    cs:__imp_GetLastError
0x140067239  nop     dword ptr [rax+rax+00h]
0x14006723e  mov     [rsp+2D0h+var_290], eax
0x140067242  mov     rcx, rbx
0x140067245  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006724a  lea     rdx, aUnableToQueryD_0; "Unable to query downlevel volume for pa"...
0x140067251  jmp     loc_140067190
0x140067256  cmp     [rbp+1D0h+var_228], 8
0x14006725a  jb      loc_1400671A5
0x140067260  mov     r8d, 4
0x140067266  lea     rdx, aRefs; "ReFS"
0x14006726d  lea     rcx, [rbp+1D0h+var_224]
0x140067271  call    cs:__imp__o__wcsnicmp
0x140067278  nop     dword ptr [rax+rax+00h]
0x14006727d  test    eax, eax
0x14006727f  jnz     loc_1400671A5
0x140067285  lea     rcx, [rsp+2D0h+var_288]
0x14006728a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14006728f  nop
0x140067290  lea     rcx, [rbp+1D0h+var_250]
0x140067294  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140067299  jmp     loc_1400670B4
```
