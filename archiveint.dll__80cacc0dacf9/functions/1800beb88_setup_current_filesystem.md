# setup_current_filesystem

- ea: `0x1800beb88`
- end: `0x1800bed23`
- name: `setup_current_filesystem`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800c01ec`

## callees

- `0x180006c00`
- `0x180014fc0`
- `0x1800beb88`
- `0x1800bf6bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800bebe1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800bec16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800bebe1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800bec16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bec3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bec7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bec3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bec7a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800bebf0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800bebf0`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800bec2d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800bec2d`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800becd3`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800becd3`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800bec85`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800bec85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bece7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bec55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bece7`

## string_xrefs

- `0x1800bec5b`: `GetVolumePathName failed: %d`

## pseudocode

```c
__int64 __fastcall setup_current_filesystem(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  __int64 v4; // rdx
  wchar_t *v5; // rdi
  wchar_t *v6; // rax
  unsigned __int64 v7; // rcx
  DWORD LastError; // eax
  UINT DriveTypeW; // eax
  UINT v11; // eax
  bool v12; // zf
  __int64 v13; // rax
  DWORD v14; // eax
  WCHAR szVolumePathName[256]; // [rsp+30h] [rbp-228h] BYREF

  v1 = *(_QWORD *)(a1 + 160);
  *(_DWORD *)(*(_QWORD *)(v1 + 888) + 8LL) = -1;
  v3 = *(_QWORD *)(v1 + 640);
  if ( tree_current_stat(v1) )
  {
    v5 = (wchar_t *)_o__wcsdup(v3, v4);
  }
  else
  {
    v5 = (wchar_t *)_o__wcsdup(v3, v4);
    v6 = wcsrchr(v5, 0x2Fu);
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v7 >= 2 )
        *(_DWORD *)(v6 + 1) = 46;
    }
  }
  if ( !GetVolumePathNameW(v5, szVolumePathName, 0x100u) )
  {
    free(v5);
    *(_DWORD *)(*(_QWORD *)(v1 + 888) + 12LL) = -1;
    *(_DWORD *)(*(_QWORD *)(v1 + 888) + 16LL) = 0;
    LastError = GetLastError();
    archive_set_error(a1, 0xFFFFFFFFLL, "GetVolumePathName failed: %d", LastError);
    return 4294967271LL;
  }
  free(v5);
  DriveTypeW = GetDriveTypeW(szVolumePathName);
  if ( DriveTypeW && (v11 = DriveTypeW - 1) != 0 )
  {
    v12 = v11 == 3;
    v13 = *(_QWORD *)(v1 + 888);
    *(_DWORD *)(v13 + 12) = v12;
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)(v1 + 888) + 12LL) = -1;
  }
  if ( !GetDiskFreeSpaceW(szVolumePathName, 0, (LPDWORD)(*(_QWORD *)(v1 + 888) + 16LL), 0, 0) )
  {
    *(_DWORD *)(*(_QWORD *)(v1 + 888) + 16LL) = 0;
    v14 = GetLastError();
    archive_set_error(a1, 0xFFFFFFFFLL, "GetDiskFreeSpace failed: %d", v14);
    return 4294967271LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800beb88  mov     [rsp+arg_8], rbx
0x1800beb8d  mov     [rsp+arg_10], rbp
0x1800beb92  push    rsi
0x1800beb93  push    rdi
0x1800beb94  push    r14
0x1800beb96  sub     rsp, 240h
0x1800beb9d  mov     rax, cs:__security_cookie
0x1800beba4  xor     rax, rsp
0x1800beba7  mov     [rsp+258h+var_28], rax
0x1800bebaf  mov     rbx, [rcx+0A0h]
0x1800bebb6  mov     rsi, rcx
0x1800bebb9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800bebbd  mov     rcx, rbx
0x1800bebc0  mov     rax, [rbx+378h]
0x1800bebc7  mov     [rax+8], r14d
0x1800bebcb  mov     rdi, [rbx+280h]
0x1800bebd2  call    tree_current_stat
0x1800bebd7  xor     ebp, ebp
0x1800bebd9  mov     rcx, rdi
0x1800bebdc  test    rax, rax
0x1800bebdf  jnz     short loc_1800BEC16
0x1800bebe1  call    cs:__imp__o__wcsdup
0x1800bebe7  mov     rcx, rax; Str
0x1800bebea  lea     edx, [rbp+2Fh]; Ch
0x1800bebed  mov     rdi, rax
0x1800bebf0  call    cs:__imp_wcsrchr
0x1800bebf6  test    rax, rax
0x1800bebf9  jz      short loc_1800BEC1F
0x1800bebfb  mov     rcx, r14
0x1800bebfe  inc     rcx
0x1800bec01  cmp     [rax+rcx*2], bp
0x1800bec05  jnz     short loc_1800BEBFE
0x1800bec07  cmp     rcx, 2
0x1800bec0b  jb      short loc_1800BEC1F
0x1800bec0d  mov     dword ptr [rax+2], 2Eh ; '.'
0x1800bec14  jmp     short loc_1800BEC1F
0x1800bec16  call    cs:__imp__o__wcsdup
0x1800bec1c  mov     rdi, rax
0x1800bec1f  mov     r8d, 100h; cchBufferLength
0x1800bec25  lea     rdx, [rsp+258h+szVolumePathName]; lpszVolumePathName
0x1800bec2a  mov     rcx, rdi; lpszFileName
0x1800bec2d  call    cs:__imp_GetVolumePathNameW
0x1800bec33  mov     rcx, rdi; Block
0x1800bec36  test    eax, eax
0x1800bec38  jnz     short loc_1800BEC7A
0x1800bec3a  call    cs:__imp_free
0x1800bec40  mov     rax, [rbx+378h]
0x1800bec47  mov     [rax+0Ch], r14d
0x1800bec4b  mov     rax, [rbx+378h]
0x1800bec52  mov     [rax+10h], ebp
0x1800bec55  call    cs:__imp_GetLastError
0x1800bec5b  lea     r8, aGetvolumepathn; "GetVolumePathName failed: %d"
0x1800bec62  mov     r9d, eax
0x1800bec65  mov     edx, r14d
0x1800bec68  mov     rcx, rsi
0x1800bec6b  call    archive_set_error
0x1800bec70  mov     eax, 0FFFFFFE7h
0x1800bec75  jmp     loc_1800BECFB
0x1800bec7a  call    cs:__imp_free
0x1800bec80  lea     rcx, [rsp+258h+szVolumePathName]; lpRootPathName
0x1800bec85  call    cs:__imp_GetDriveTypeW
0x1800bec8b  test    eax, eax
0x1800bec8d  jz      short loc_1800BECAE
0x1800bec8f  sub     eax, 1
0x1800bec92  jz      short loc_1800BECAE
0x1800bec94  cmp     eax, 3
0x1800bec97  mov     rax, [rbx+378h]
0x1800bec9e  jz      short loc_1800BECA5
0x1800beca0  mov     [rax+0Ch], ebp
0x1800beca3  jmp     short loc_1800BECB9
0x1800beca5  mov     dword ptr [rax+0Ch], 1
0x1800becac  jmp     short loc_1800BECB9
0x1800becae  mov     rax, [rbx+378h]
0x1800becb5  mov     [rax+0Ch], r14d
0x1800becb9  mov     r8, [rbx+378h]
0x1800becc0  lea     rcx, [rsp+258h+szVolumePathName]; lpRootPathName
0x1800becc5  add     r8, 10h; lpBytesPerSector
0x1800becc9  mov     [rsp+258h+lpTotalNumberOfClusters], rbp; lpTotalNumberOfClusters
0x1800becce  xor     r9d, r9d; lpNumberOfFreeClusters
0x1800becd1  xor     edx, edx; lpSectorsPerCluster
0x1800becd3  call    cs:__imp_GetDiskFreeSpaceW
0x1800becd9  test    eax, eax
0x1800becdb  jnz     short loc_1800BECF9
0x1800becdd  mov     rax, [rbx+378h]
0x1800bece4  mov     [rax+10h], ebp
0x1800bece7  call    cs:__imp_GetLastError
0x1800beced  lea     r8, aGetdiskfreespa; "GetDiskFreeSpace failed: %d"
0x1800becf4  jmp     loc_1800BEC62
0x1800becf9  xor     eax, eax
0x1800becfb  mov     rcx, [rsp+258h+var_28]
0x1800bed03  xor     rcx, rsp; StackCookie
0x1800bed06  call    __security_check_cookie
0x1800bed0b  lea     r11, [rsp+258h+var_18]
0x1800bed13  mov     rbx, [r11+28h]
0x1800bed17  mov     rbp, [r11+30h]
0x1800bed1b  mov     rsp, r11
0x1800bed1e  pop     r14
0x1800bed20  pop     rdi
0x1800bed21  pop     rsi
0x1800bed22  retn
```
