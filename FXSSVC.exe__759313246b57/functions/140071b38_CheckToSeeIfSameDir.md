# CheckToSeeIfSameDir

- ea: `0x140071b38`
- end: `0x1400720bf`
- name: `CheckToSeeIfSameDir`
- size: `1415`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, wchar_t *String2)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000c004`
- `0x14001ee40`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14000cae8`
- `0x14006e124`
- `0x140071b38`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x140071be0`
- `KERNEL32!GetTempFileNameW` at `0x140071be0`
- `KERNEL32!GetFileInformationByHandle` at `0x140071f4c`
- `KERNEL32!GetFileInformationByHandle` at `0x140071fa7`
- `KERNEL32!GetFileInformationByHandle` at `0x140071f4c`
- `KERNEL32!GetFileInformationByHandle` at `0x140071fa7`
- `KERNEL32!GetLastError` at `0x140071bf0`
- `KERNEL32!GetLastError` at `0x140071c64`
- `KERNEL32!GetLastError` at `0x140071de5`
- `KERNEL32!GetLastError` at `0x140071e3d`
- `KERNEL32!GetLastError` at `0x140071eb4`
- `KERNEL32!GetLastError` at `0x140071f5c`
- `KERNEL32!GetLastError` at `0x140071fb7`
- `KERNEL32!GetLastError` at `0x140072062`
- `KERNEL32!GetLastError` at `0x140071bf0`
- `KERNEL32!GetLastError` at `0x140071c64`
- `KERNEL32!GetLastError` at `0x140071de5`
- `KERNEL32!GetLastError` at `0x140071e3d`
- `KERNEL32!GetLastError` at `0x140071eb4`
- `KERNEL32!GetLastError` at `0x140071f5c`
- `KERNEL32!GetLastError` at `0x140071fb7`
- `KERNEL32!GetLastError` at `0x140072062`
- `KERNEL32!CloseHandle` at `0x140071e15`
- `KERNEL32!CloseHandle` at `0x140071e75`
- `KERNEL32!CloseHandle` at `0x140071e15`
- `KERNEL32!CloseHandle` at `0x140071e75`
- `KERNEL32!DeleteFileW` at `0x14007203a`
- `KERNEL32!DeleteFileW` at `0x14007203a`
- `msvcrt!wcsrchr` at `0x140071cbe`
- `msvcrt!wcsrchr` at `0x140071cbe`
- `msvcrt!_wcsicmp` at `0x140071bb1`
- `msvcrt!_wcsicmp` at `0x140071bb1`

## pseudocode

```c
int __fastcall CheckToSeeIfSameDir(LPCWSTR lpPathName, wchar_t *String2, _DWORD *a3)
{
  int result; // eax
  __int64 v7; // r9
  DWORD v8; // eax
  int v9; // ebx
  void *File; // r15
  DWORD LastError; // eax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r14
  wchar_t *v15; // rax
  WCHAR *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rcx
  WCHAR *v19; // rcx
  int v20; // eax
  __int64 v21; // r9
  DWORD v22; // eax
  DWORD v23; // eax
  CMapDeviceId *v24; // rcx
  __int64 v25; // rdx
  char v26; // al
  struct _BY_HANDLE_FILE_INFORMATION v27; // [rsp+40h] [rbp-C0h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-88h] BYREF
  WCHAR TempFileName[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[520]; // [rsp+2C0h] [rbp+1C0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  result = _wcsicmp(lpPathName, String2);
  if ( !result )
  {
    *a3 = 1;
    return result;
  }
  if ( GetTempFileNameW(lpPathName, L"TST", 0, TempFileName) )
  {
    File = (void *)InternalSafeCreateFile(TempFileName, 0, 3u, v7, 3u, 0);
    if ( File == (void *)-1LL )
    {
      LastError = GetLastError();
      v9 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_71:
        if ( !DeleteFileW(TempFileName)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
            (unsigned int)TempFileName,
            v26);
        }
        return v9;
      }
      v13 = 65;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      goto LABEL_71;
    }
    v14 = -1;
    v15 = wcsrchr(TempFileName, 0x5Cu);
    v16 = FileName;
    v17 = 520;
    v18 = 2147483646;
    do
    {
      if ( !v18 )
        break;
      if ( !*String2 )
        break;
      *v16++ = *String2++;
      --v18;
      --v17;
    }
    while ( v17 );
    v19 = v16 - 1;
    if ( v17 )
      v19 = v16;
    *v19 = 0;
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
      }
      v9 = 122;
      goto LABEL_41;
    }
    v20 = StringCchCatW(FileName, 0x208u, v15);
    LOWORD(v9) = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (unsigned __int16)v20);
      }
      v9 = (unsigned __int16)v9;
      goto LABEL_41;
    }
    v14 = InternalSafeCreateFile(FileName, 0, 3u, v21, 3u, 0);
    if ( v14 == -1 )
    {
      v22 = GetLastError();
      v9 = v22;
      if ( v22 != 8 && v22 != 14 )
      {
        v9 = 0;
LABEL_40:
        *a3 = 0;
        goto LABEL_41;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v25 = 68;
    }
    else
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      memset(&v27, 0, sizeof(v27));
      if ( GetFileInformationByHandle(File, &FileInformation) )
      {
        if ( GetFileInformationByHandle((HANDLE)v14, &v27) )
        {
          v9 = 0;
          if ( FileInformation.nFileIndexHigh != v27.nFileIndexHigh
            || FileInformation.nFileIndexLow != v27.nFileIndexLow
            || FileInformation.dwVolumeSerialNumber != v27.dwVolumeSerialNumber )
          {
            goto LABEL_40;
          }
          *a3 = 1;
LABEL_41:
          if ( !CloseHandle(File)
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v23);
          }
          if ( v14 == -1
            || CloseHandle((HANDLE)v14)
            || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_71;
          }
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          v13 = 72;
          goto LABEL_17;
        }
        v22 = GetLastError();
        v9 = v22;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v25 = 70;
      }
      else
      {
        v22 = GetLastError();
        v9 = v22;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_41;
        }
        v25 = 69;
      }
    }
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v22);
    goto LABEL_41;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x140071b38  mov     [rsp-8+arg_18], rbx
0x140071b3d  push    rbp
0x140071b3e  push    rsi
0x140071b3f  push    rdi
0x140071b40  push    r12
0x140071b42  push    r13
0x140071b44  push    r14
0x140071b46  push    r15
0x140071b48  lea     rbp, [rsp-5E0h]
0x140071b50  sub     rsp, 6E0h
0x140071b57  mov     rax, cs:__security_cookie
0x140071b5e  xor     rax, rsp
0x140071b61  mov     [rbp+610h+var_40], rax
0x140071b68  mov     rdi, r8
0x140071b6b  mov     rsi, rdx
0x140071b6e  mov     rbx, rcx
0x140071b71  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b78  lea     r14, WPP_GLOBAL_Control
0x140071b7f  mov     r12d, 2
0x140071b85  cmp     rcx, r14
0x140071b88  jz      short loc_140071BAB
0x140071b8a  test    [rcx+1Ch], r12b
0x140071b8e  jz      short loc_140071BAB
0x140071b90  cmp     byte ptr [rcx+19h], 5
0x140071b94  jb      short loc_140071BAB
0x140071b96  mov     rcx, [rcx+10h]
0x140071b9a  lea     edx, [r12+3Dh]
0x140071b9f  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071ba6  call    WPP_SF_
0x140071bab  mov     rdx, rsi; String2
0x140071bae  mov     rcx, rbx; String1
0x140071bb1  call    cs:__imp__wcsicmp
0x140071bb8  nop     dword ptr [rax+rax+00h]
0x140071bbd  xor     r13d, r13d
0x140071bc0  test    eax, eax
0x140071bc2  jnz     short loc_140071BCF
0x140071bc4  mov     dword ptr [rdi], 1
0x140071bca  jmp     loc_140072094
0x140071bcf  lea     r9, [rbp+610h+TempFileName]; lpTempFileName
0x140071bd3  xor     r8d, r8d; uUnique
0x140071bd6  lea     rdx, PrefixString; "TST"
0x140071bdd  mov     rcx, rbx; lpPathName
0x140071be0  call    cs:__imp_GetTempFileNameW
0x140071be7  nop     dword ptr [rax+rax+00h]
0x140071bec  test    eax, eax
0x140071bee  jnz     short loc_140071C3F
0x140071bf0  call    cs:__imp_GetLastError
0x140071bf7  nop     dword ptr [rax+rax+00h]
0x140071bfc  mov     ebx, eax
0x140071bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c05  cmp     rcx, r14
0x140071c08  jz      loc_140072092
0x140071c0e  test    [rcx+1Ch], r12b
0x140071c12  jz      loc_140072092
0x140071c18  cmp     [rcx+19h], r12b
0x140071c1c  jb      loc_140072092
0x140071c22  mov     rcx, [rcx+10h]
0x140071c26  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071c2d  mov     edx, 40h ; '@'
0x140071c32  mov     r9d, eax
0x140071c35  call    WPP_SF_d
0x140071c3a  jmp     loc_140072092
0x140071c3f  mov     eax, 3
0x140071c44  mov     [rsp+710h+var_6E8], r13d; int
0x140071c49  mov     r8d, eax; dwShareMode
0x140071c4c  mov     [rsp+710h+var_6F0], eax; DWORD
0x140071c50  xor     edx, edx; dwDesiredAccess
0x140071c52  lea     rcx, [rbp+610h+TempFileName]; lpFileName
0x140071c56  call    InternalSafeCreateFile
0x140071c5b  mov     r15, rax
0x140071c5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140071c62  jnz     short loc_140071CB2
0x140071c64  call    cs:__imp_GetLastError
0x140071c6b  nop     dword ptr [rax+rax+00h]
0x140071c70  mov     ebx, eax
0x140071c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c79  cmp     rcx, r14
0x140071c7c  jz      loc_140072036
0x140071c82  test    [rcx+1Ch], r12b
0x140071c86  jz      loc_140072036
0x140071c8c  cmp     [rcx+19h], r12b
0x140071c90  jb      loc_140072036
0x140071c96  lea     edx, [r15+42h]
0x140071c9a  mov     rcx, [rcx+10h]
0x140071c9e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071ca5  mov     r9d, eax
0x140071ca8  call    WPP_SF_d
0x140071cad  jmp     loc_140072036
0x140071cb2  or      r14, 0FFFFFFFFFFFFFFFFh
0x140071cb6  lea     rcx, [rbp+610h+TempFileName]; Str
0x140071cba  lea     edx, [r14+5Dh]; Ch
0x140071cbe  call    cs:__imp_wcsrchr
0x140071cc5  nop     dword ptr [rax+rax+00h]
0x140071cca  mov     r10d, 208h
0x140071cd0  lea     rdx, [rbp+610h+FileName]
0x140071cd7  mov     ebx, r10d
0x140071cda  mov     ecx, 7FFFFFFEh
0x140071cdf  test    rcx, rcx
0x140071ce2  jz      short loc_140071D01
0x140071ce4  movzx   r8d, word ptr [rsi]
0x140071ce8  test    r8w, r8w
0x140071cec  jz      short loc_140071D01
0x140071cee  mov     [rdx], r8w
0x140071cf2  add     rsi, r12
0x140071cf5  add     rdx, r12
0x140071cf8  dec     rcx
0x140071cfb  sub     rbx, 1
0x140071cff  jnz     short loc_140071CDF
0x140071d01  test    rbx, rbx
0x140071d04  lea     rcx, [rdx-2]
0x140071d08  cmovnz  rcx, rdx
0x140071d0c  mov     [rcx], r13w
0x140071d10  jnz     short loc_140071D65
0x140071d12  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d19  lea     rdi, WPP_GLOBAL_Control
0x140071d20  cmp     rcx, rdi
0x140071d23  jz      short loc_140071D56
0x140071d25  test    [rcx+1Ch], r12b
0x140071d29  jz      short loc_140071D56
0x140071d2b  cmp     [rcx+19h], r12b
0x140071d2f  jb      short loc_140071D56
0x140071d31  mov     rcx, [rcx+10h]
0x140071d35  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071d3c  mov     rax, rbx
0x140071d3f  mov     edx, 42h ; 'B'
0x140071d44  neg     rax
0x140071d47  sbb     r9d, r9d
0x140071d4a  not     r9d
0x140071d4d  and     r9d, 7Ah
0x140071d51  call    WPP_SF_d
0x140071d56  neg     rbx
0x140071d59  sbb     ebx, ebx
0x140071d5b  not     ebx
0x140071d5d  and     ebx, 7Ah
0x140071d60  jmp     loc_140071E12
0x140071d65  mov     r8, rax; unsigned __int16 *
0x140071d68  lea     rcx, [rbp+610h+FileName]; unsigned __int16 *
0x140071d6f  mov     rdx, r10; unsigned __int64
0x140071d72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140071d77  mov     ebx, eax
0x140071d79  test    eax, eax
0x140071d7b  jns     short loc_140071DBA
0x140071d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d84  lea     rdi, WPP_GLOBAL_Control
0x140071d8b  cmp     rcx, rdi
0x140071d8e  jz      short loc_140071DB5
0x140071d90  test    [rcx+1Ch], r12b
0x140071d94  jz      short loc_140071DB5
0x140071d96  cmp     [rcx+19h], r12b
0x140071d9a  jb      short loc_140071DB5
0x140071d9c  mov     rcx, [rcx+10h]
0x140071da0  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071da7  movzx   r9d, bx
0x140071dab  mov     edx, 43h ; 'C'
0x140071db0  call    WPP_SF_d
0x140071db5  movzx   ebx, bx
0x140071db8  jmp     short loc_140071E12
0x140071dba  mov     r8d, 3; dwShareMode
0x140071dc0  mov     [rsp+710h+var_6E8], r13d; int
0x140071dc5  xor     edx, edx; dwDesiredAccess
0x140071dc7  mov     [rsp+710h+var_6F0], r8d; DWORD
0x140071dcc  lea     rcx, [rbp+610h+FileName]; lpFileName
0x140071dd3  call    InternalSafeCreateFile
0x140071dd8  mov     r14, rax
0x140071ddb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140071ddf  jnz     loc_140071F19
0x140071de5  call    cs:__imp_GetLastError
0x140071dec  nop     dword ptr [rax+rax+00h]
0x140071df1  mov     ebx, eax
0x140071df3  cmp     eax, 8
0x140071df6  jz      loc_140071ED1
0x140071dfc  cmp     eax, 0Eh
0x140071dff  jz      loc_140071ED1
0x140071e05  mov     ebx, r13d
0x140071e08  mov     [rdi], r13d
0x140071e0b  lea     rdi, WPP_GLOBAL_Control
0x140071e12  mov     rcx, r15; hObject
0x140071e15  call    cs:__imp_CloseHandle
0x140071e1c  nop     dword ptr [rax+rax+00h]
0x140071e21  test    eax, eax
0x140071e23  jnz     short loc_140071E68
0x140071e25  mov     rax, cs:WPP_GLOBAL_Control
0x140071e2c  cmp     rax, rdi
0x140071e2f  jz      short loc_140071E68
0x140071e31  test    [rax+1Ch], r12b
0x140071e35  jz      short loc_140071E68
0x140071e37  cmp     [rax+19h], r12b
0x140071e3b  jb      short loc_140071E68
0x140071e3d  call    cs:__imp_GetLastError
0x140071e44  nop     dword ptr [rax+rax+00h]
0x140071e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140071e50  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071e57  mov     edx, 47h ; 'G'
0x140071e5c  mov     r9d, eax
0x140071e5f  mov     rcx, [rcx+10h]
0x140071e63  call    WPP_SF_d
0x140071e68  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140071e6c  jz      loc_14007202F
0x140071e72  mov     rcx, r14; hObject
0x140071e75  call    cs:__imp_CloseHandle
0x140071e7c  nop     dword ptr [rax+rax+00h]
0x140071e81  test    eax, eax
0x140071e83  jnz     loc_14007202F
0x140071e89  mov     rax, cs:WPP_GLOBAL_Control
0x140071e90  lea     r14, WPP_GLOBAL_Control
0x140071e97  cmp     rax, r14
0x140071e9a  jz      loc_140072036
0x140071ea0  test    [rax+1Ch], r12b
0x140071ea4  jz      loc_140072036
0x140071eaa  cmp     [rax+19h], r12b
0x140071eae  jb      loc_140072036
0x140071eb4  call    cs:__imp_GetLastError
0x140071ebb  nop     dword ptr [rax+rax+00h]
0x140071ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ec7  mov     edx, 48h ; 'H'
0x140071ecc  jmp     loc_140071C9A
0x140071ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ed8  lea     rdi, WPP_GLOBAL_Control
0x140071edf  cmp     rcx, rdi
0x140071ee2  jz      loc_140071E12
0x140071ee8  test    [rcx+1Ch], r12b
0x140071eec  jz      loc_140071E12
0x140071ef2  cmp     [rcx+19h], r12b
0x140071ef6  jb      loc_140071E12
0x140071efc  mov     edx, 44h ; 'D'
0x140071f01  mov     rcx, [rcx+10h]
0x140071f05  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140071f0c  mov     r9d, eax
0x140071f0f  call    WPP_SF_d
0x140071f14  jmp     loc_140071E12
0x140071f19  xorps   xmm0, xmm0
0x140071f1c  lea     rdx, [rsp+710h+FileInformation]; lpFileInformation
0x140071f21  xorps   xmm1, xmm1
0x140071f24  xor     eax, eax
0x140071f26  mov     rcx, r15; hFile
0x140071f29  mov     [rbp+610h+FileInformation.nFileIndexLow], eax
0x140071f2c  movups  xmmword ptr [rsp+710h+FileInformation.dwFileAttributes], xmm0
0x140071f31  mov     [rsp+710h+var_6D0.nFileIndexLow], eax
0x140071f35  movups  xmmword ptr [rbp+610h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140071f39  movups  xmmword ptr [rbp+610h+FileInformation.nFileSizeHigh], xmm0
0x140071f3d  movups  xmmword ptr [rsp+710h+var_6D0.dwFileAttributes], xmm1
0x140071f42  movups  xmmword ptr [rsp+710h+var_6D0.ftLastAccessTime.dwHighDateTime], xmm1
0x140071f47  movups  xmmword ptr [rsp+710h+var_6D0.nFileSizeHigh], xmm1
0x140071f4c  call    cs:__imp_GetFileInformationByHandle
0x140071f53  nop     dword ptr [rax+rax+00h]
0x140071f58  test    eax, eax
0x140071f5a  jnz     short loc_140071F9F
0x140071f5c  call    cs:__imp_GetLastError
0x140071f63  nop     dword ptr [rax+rax+00h]
0x140071f68  mov     ebx, eax
0x140071f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140071f71  lea     rdi, WPP_GLOBAL_Control
0x140071f78  cmp     rcx, rdi
0x140071f7b  jz      loc_140071E12
0x140071f81  test    [rcx+1Ch], r12b
0x140071f85  jz      loc_140071E12
0x140071f8b  cmp     [rcx+19h], r12b
0x140071f8f  jb      loc_140071E12
0x140071f95  mov     edx, 45h ; 'E'
0x140071f9a  jmp     loc_140071F01
0x140071f9f  lea     rdx, [rsp+710h+var_6D0]; lpFileInformation
0x140071fa4  mov     rcx, r14; hFile
0x140071fa7  call    cs:__imp_GetFileInformationByHandle
0x140071fae  nop     dword ptr [rax+rax+00h]
0x140071fb3  test    eax, eax
0x140071fb5  jnz     short loc_140071FFA
0x140071fb7  call    cs:__imp_GetLastError
0x140071fbe  nop     dword ptr [rax+rax+00h]
0x140071fc3  mov     ebx, eax
0x140071fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140071fcc  lea     rdi, WPP_GLOBAL_Control
0x140071fd3  cmp     rcx, rdi
0x140071fd6  jz      loc_140071E12
0x140071fdc  test    [rcx+1Ch], r12b
0x140071fe0  jz      loc_140071E12
0x140071fe6  cmp     [rcx+19h], r12b
0x140071fea  jb      loc_140071E12
0x140071ff0  mov     edx, 46h ; 'F'
0x140071ff5  jmp     loc_140071F01
0x140071ffa  mov     eax, [rsp+710h+var_6D0.nFileIndexHigh]
0x140071ffe  mov     ebx, r13d
0x140072001  cmp     [rbp+610h+FileInformation.nFileIndexHigh], eax
0x140072004  jnz     loc_140071E08
0x14007200a  mov     eax, [rsp+710h+var_6D0.nFileIndexLow]
0x14007200e  cmp     [rbp+610h+FileInformation.nFileIndexLow], eax
0x140072011  jnz     loc_140071E08
0x140072017  mov     eax, [rsp+710h+var_6D0.dwVolumeSerialNumber]
0x14007201b  cmp     [rbp+610h+FileInformation.dwVolumeSerialNumber], eax
0x14007201e  jnz     loc_140071E08
0x140072024  mov     dword ptr [rdi], 1
0x14007202a  jmp     loc_140071E0B
0x14007202f  lea     r14, WPP_GLOBAL_Control
0x140072036  lea     rcx, [rbp+610h+TempFileName]; lpFileName
0x14007203a  call    cs:__imp_DeleteFileW
0x140072041  nop     dword ptr [rax+rax+00h]
0x140072046  test    eax, eax
0x140072048  jnz     short loc_140072092
0x14007204a  mov     rax, cs:WPP_GLOBAL_Control
0x140072051  cmp     rax, r14
0x140072054  jz      short loc_140072092
  ... truncated ...
```
