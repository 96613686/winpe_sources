# DeleteQueueFiles(ushort const *)

- ea: `0x140039bb4`
- end: `0x140039e7f`
- name: `?DeleteQueueFiles@@YAHPEBG@Z`
- size: `715`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x14003e168`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004eb0`
- `0x140004f64`
- `0x140039bb4`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140039db7`
- `KERNEL32!GetLastError` at `0x140039e33`
- `KERNEL32!GetLastError` at `0x140039db7`
- `KERNEL32!GetLastError` at `0x140039e33`
- `KERNEL32!FindFirstFileW` at `0x140039c8c`
- `KERNEL32!FindFirstFileW` at `0x140039c8c`
- `KERNEL32!FindClose` at `0x140039e0b`
- `KERNEL32!FindClose` at `0x140039e0b`
- `KERNEL32!DeleteFileW` at `0x140039d8f`
- `KERNEL32!DeleteFileW` at `0x140039d8f`
- `KERNEL32!FindNextFileW` at `0x140039df4`
- `KERNEL32!FindNextFileW` at `0x140039df4`

## pseudocode

```c
_BOOL8 __fastcall DeleteQueueFiles(const unsigned __int16 *a1)
{
  int v2; // eax
  HANDLE FirstFileW; // rdi
  int v5; // ebx
  int v6; // eax
  char LastError; // al
  DWORD v8; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-498h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v2 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.%s", *((_QWORD *)g_pFaxConfig + 12), a1);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (unsigned int)v2);
    }
    return 0;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (_DWORD)a1,
        *((_QWORD *)g_pFaxConfig + 12));
    }
    return 1;
  }
  v5 = 0;
  do
  {
    v6 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", *((_QWORD *)g_pFaxConfig + 12), FindFileData.cFileName);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)v6);
      }
LABEL_32:
      v5 = 1;
      continue;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, FileName);
    }
    if ( !DeleteFileW(FileName) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)FileName,
          LastError);
      }
      goto LABEL_32;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( !FindClose(FirstFileW)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v8);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x140039bb4  push    rbx
0x140039bb6  push    rbp
0x140039bb7  push    rdi
0x140039bb8  push    r14
0x140039bba  sub     rsp, 4A8h
0x140039bc1  mov     rax, cs:__security_cookie
0x140039bc8  xor     rax, rsp
0x140039bcb  mov     [rsp+4C8h+var_38], rax
0x140039bd3  mov     rbx, rcx
0x140039bd6  xor     edx, edx; Val
0x140039bd8  lea     rcx, [rsp+4C8h+FindFileData]; void *
0x140039bdd  mov     r8d, 250h; Size
0x140039be3  call    memset_0
0x140039be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140039bef  lea     rbp, WPP_GLOBAL_Control
0x140039bf6  lea     r14, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140039bfd  cmp     rcx, rbp
0x140039c00  jz      short loc_140039C1F
0x140039c02  test    byte ptr [rcx+1Ch], 4
0x140039c06  jz      short loc_140039C1F
0x140039c08  cmp     byte ptr [rcx+19h], 5
0x140039c0c  jb      short loc_140039C1F
0x140039c0e  mov     rcx, [rcx+10h]
0x140039c12  mov     edx, 30h ; '0'
0x140039c17  mov     r8, r14
0x140039c1a  call    WPP_SF_
0x140039c1f  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140039c26  lea     r8, aSS; "%s\\*.%s"
0x140039c2d  mov     edx, 104h; unsigned __int64
0x140039c32  mov     [rsp+4C8h+var_4A8], rbx
0x140039c37  lea     rcx, [rsp+4C8h+FileName]; unsigned __int16 *
0x140039c3f  mov     r9, [r9+60h]
0x140039c43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140039c48  test    eax, eax
0x140039c4a  jns     short loc_140039C7F
0x140039c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c53  cmp     rcx, rbp
0x140039c56  jz      short loc_140039C78
0x140039c58  test    byte ptr [rcx+1Ch], 4
0x140039c5c  jz      short loc_140039C78
0x140039c5e  cmp     byte ptr [rcx+19h], 2
0x140039c62  jb      short loc_140039C78
0x140039c64  mov     rcx, [rcx+10h]
0x140039c68  mov     edx, 31h ; '1'
0x140039c6d  mov     r9d, eax
0x140039c70  mov     r8, r14
0x140039c73  call    WPP_SF_d
0x140039c78  xor     eax, eax
0x140039c7a  jmp     loc_140039E61
0x140039c7f  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140039c84  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140039c8c  call    cs:__imp_FindFirstFileW
0x140039c93  nop     dword ptr [rax+rax+00h]
0x140039c98  mov     rdi, rax
0x140039c9b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140039c9f  jnz     short loc_140039CE5
0x140039ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ca8  cmp     rcx, rbp
0x140039cab  jz      short loc_140039CDB
0x140039cad  test    byte ptr [rcx+1Ch], 4
0x140039cb1  jz      short loc_140039CDB
0x140039cb3  cmp     byte ptr [rcx+19h], 3
0x140039cb7  jb      short loc_140039CDB
0x140039cb9  mov     rcx, [rcx+10h]
0x140039cbd  lea     edx, [rax+33h]
0x140039cc0  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140039cc7  mov     r9, rbx
0x140039cca  mov     r8, [rax+60h]
0x140039cce  mov     [rsp+4C8h+var_4A8], r8
0x140039cd3  mov     r8, r14
0x140039cd6  call    WPP_SF_SS
0x140039cdb  mov     eax, 1
0x140039ce0  jmp     loc_140039E61
0x140039ce5  xor     ebx, ebx
0x140039ce7  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140039cee  lea     rax, [rsp+4C8h+FindFileData.cFileName]
0x140039cf3  lea     r8, aSS_0; "%s\\%s"
0x140039cfa  mov     [rsp+4C8h+var_4A8], rax
0x140039cff  mov     edx, 104h; unsigned __int64
0x140039d04  lea     rcx, [rsp+4C8h+FileName]; unsigned __int16 *
0x140039d0c  mov     r9, [r9+60h]
0x140039d10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140039d15  test    eax, eax
0x140039d17  jns     short loc_140039D56
0x140039d19  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d20  cmp     rcx, rbp
0x140039d23  jz      loc_140039DE7
0x140039d29  test    byte ptr [rcx+1Ch], 4
0x140039d2d  jz      loc_140039DE7
0x140039d33  cmp     byte ptr [rcx+19h], 2
0x140039d37  jb      loc_140039DE7
0x140039d3d  mov     rcx, [rcx+10h]
0x140039d41  mov     edx, 33h ; '3'
0x140039d46  mov     r9d, eax
0x140039d49  mov     r8, r14
0x140039d4c  call    WPP_SF_d
0x140039d51  jmp     loc_140039DE7
0x140039d56  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d5d  cmp     rcx, rbp
0x140039d60  jz      short loc_140039D87
0x140039d62  test    byte ptr [rcx+1Ch], 4
0x140039d66  jz      short loc_140039D87
0x140039d68  cmp     byte ptr [rcx+19h], 5
0x140039d6c  jb      short loc_140039D87
0x140039d6e  mov     rcx, [rcx+10h]
0x140039d72  lea     r9, [rsp+4C8h+FileName]
0x140039d7a  mov     edx, 34h ; '4'
0x140039d7f  mov     r8, r14
0x140039d82  call    WPP_SF_S
0x140039d87  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140039d8f  call    cs:__imp_DeleteFileW
0x140039d96  nop     dword ptr [rax+rax+00h]
0x140039d9b  test    eax, eax
0x140039d9d  jnz     short loc_140039DEC
0x140039d9f  mov     rax, cs:WPP_GLOBAL_Control
0x140039da6  cmp     rax, rbp
0x140039da9  jz      short loc_140039DE7
0x140039dab  test    byte ptr [rax+1Ch], 4
0x140039daf  jz      short loc_140039DE7
0x140039db1  cmp     byte ptr [rax+19h], 2
0x140039db5  jb      short loc_140039DE7
0x140039db7  call    cs:__imp_GetLastError
0x140039dbe  nop     dword ptr [rax+rax+00h]
0x140039dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140039dca  lea     r9, [rsp+4C8h+FileName]
0x140039dd2  mov     edx, 35h ; '5'
0x140039dd7  mov     dword ptr [rsp+4C8h+var_4A8], eax
0x140039ddb  mov     r8, r14
0x140039dde  mov     rcx, [rcx+10h]
0x140039de2  call    WPP_SF_Sd
0x140039de7  mov     ebx, 1
0x140039dec  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140039df1  mov     rcx, rdi; hFindFile
0x140039df4  call    cs:__imp_FindNextFileW
0x140039dfb  nop     dword ptr [rax+rax+00h]
0x140039e00  test    eax, eax
0x140039e02  jnz     loc_140039CE7
0x140039e08  mov     rcx, rdi; hFindFile
0x140039e0b  call    cs:__imp_FindClose
0x140039e12  nop     dword ptr [rax+rax+00h]
0x140039e17  test    eax, eax
0x140039e19  jnz     short loc_140039E5A
0x140039e1b  mov     rax, cs:WPP_GLOBAL_Control
0x140039e22  cmp     rax, rbp
0x140039e25  jz      short loc_140039E5A
0x140039e27  test    byte ptr [rax+1Ch], 4
0x140039e2b  jz      short loc_140039E5A
0x140039e2d  cmp     byte ptr [rax+19h], 2
0x140039e31  jb      short loc_140039E5A
0x140039e33  call    cs:__imp_GetLastError
0x140039e3a  nop     dword ptr [rax+rax+00h]
0x140039e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039e46  mov     edx, 36h ; '6'
0x140039e4b  mov     r9d, eax
0x140039e4e  mov     r8, r14
0x140039e51  mov     rcx, [rcx+10h]
0x140039e55  call    WPP_SF_d
0x140039e5a  xor     eax, eax
0x140039e5c  test    ebx, ebx
0x140039e5e  setz    al
0x140039e61  mov     rcx, [rsp+4C8h+var_38]
0x140039e69  xor     rcx, rsp; StackCookie
0x140039e6c  call    __security_check_cookie
0x140039e71  add     rsp, 4A8h
0x140039e78  pop     r14
0x140039e7a  pop     rdi
0x140039e7b  pop     rbp
0x140039e7c  pop     rbx
0x140039e7d  retn
```
