# StorageService::EnsureSystemVolumeInformationFolder(_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180021d8c`
- end: `0x180021e77`
- name: `?EnsureSystemVolumeInformationFolder@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x180029c5c`

## callees

- `0x18000d030`
- `0x180012c9c`
- `0x180021d8c`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180021e42`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180021e42`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180021e37`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180021e37`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021e0a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021e0a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021df9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021df9`

## pseudocode

```c
__int64 __fastcall StorageService::EnsureSystemVolumeInformationFolder(__int64 a1, int a2, unsigned int a3)
{
  __int64 v4; // rbp
  __int64 v5; // rsi
  HRESULT v6; // ebx
  unsigned int v7; // r11d
  __int64 v8; // rcx
  NTSTATUS v9; // eax
  __int64 v11; // [rsp+20h] [rbp-258h] BYREF
  UNICODE_STRING VolumeRootPath; // [rsp+28h] [rbp-250h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-238h] BYREF

  v4 = a2;
  v5 = 1112LL * a3;
  VolumeRootPath = 0;
  v6 = StringCchCopyW(pszPath, 0x104u, (const wchar_t *)(v5 + *(_QWORD *)(a1 + 8LL * a2 + 40) + 4LL));
  if ( v6 >= 0 )
  {
    v6 = PathCchAppend(pszPath, v7, L"System Volume Information");
    if ( v6 >= 0 && GetFileAttributesW(pszPath) == -1 )
    {
      v8 = *(_QWORD *)(a1 + 8 * v4 + 40) + 4LL;
      v11 = 0;
      ((void (__fastcall *)(__int64, UNICODE_STRING *, __int64 *, _QWORD))RtlDosPathNameToRelativeNtPathName_U_WithStatus)(
        v5 + v8,
        &VolumeRootPath,
        &v11,
        0);
      v9 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
      if ( v9 < 0 )
        return (unsigned int)(v9 | 0x10000000);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021d8c  mov     [rsp+arg_18], rbx
0x180021d91  push    rbp
0x180021d92  push    rsi
0x180021d93  push    rdi
0x180021d94  sub     rsp, 260h
0x180021d9b  mov     rax, cs:__security_cookie
0x180021da2  xor     rax, rsp
0x180021da5  mov     [rsp+278h+var_28], rax
0x180021dad  mov     eax, r8d
0x180021db0  mov     rdi, rcx
0x180021db3  movsxd  rbp, edx
0x180021db6  mov     r11d, 104h
0x180021dbc  imul    rsi, rax, 458h
0x180021dc3  xorps   xmm0, xmm0
0x180021dc6  movups  xmmword ptr [rsp+278h+VolumeRootPath.Length], xmm0
0x180021dcb  mov     r8, [rcx+rbp*8+28h]
0x180021dd0  mov     edx, r11d; unsigned __int64
0x180021dd3  add     r8, 4
0x180021dd7  lea     rcx, [rsp+278h+pszPath]; wchar_t *
0x180021ddc  add     r8, rsi; wchar_t *
0x180021ddf  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180021de4  mov     ebx, eax
0x180021de6  test    eax, eax
0x180021de8  js      short loc_180021E52
0x180021dea  lea     r8, aSystemVolumeIn; "System Volume Information"
0x180021df1  mov     edx, r11d; cchPath
0x180021df4  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180021df9  call    cs:__imp_PathCchAppend
0x180021dff  mov     ebx, eax
0x180021e01  test    eax, eax
0x180021e03  js      short loc_180021E52
0x180021e05  lea     rcx, [rsp+278h+pszPath]; lpFileName
0x180021e0a  call    cs:__imp_GetFileAttributesW
0x180021e10  cmp     eax, 0FFFFFFFFh
0x180021e13  jnz     short loc_180021E52
0x180021e15  mov     rcx, [rdi+rbp*8+28h]
0x180021e1a  lea     r8, [rsp+278h+var_258]
0x180021e1f  add     rcx, 4
0x180021e23  mov     [rsp+278h+var_258], 0
0x180021e2c  add     rcx, rsi
0x180021e2f  lea     rdx, [rsp+278h+VolumeRootPath]
0x180021e34  xor     r9d, r9d
0x180021e37  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180021e3d  lea     rcx, [rsp+278h+VolumeRootPath]; VolumeRootPath
0x180021e42  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x180021e48  test    eax, eax
0x180021e4a  jns     short loc_180021E52
0x180021e4c  mov     ebx, eax
0x180021e4e  bts     ebx, 1Ch
0x180021e52  mov     eax, ebx
0x180021e54  mov     rcx, [rsp+278h+var_28]
0x180021e5c  xor     rcx, rsp; StackCookie
0x180021e5f  call    __security_check_cookie
0x180021e64  mov     rbx, [rsp+278h+arg_18]
0x180021e6c  add     rsp, 260h
0x180021e73  pop     rdi
0x180021e74  pop     rsi
0x180021e75  pop     rbp
0x180021e76  retn
```
