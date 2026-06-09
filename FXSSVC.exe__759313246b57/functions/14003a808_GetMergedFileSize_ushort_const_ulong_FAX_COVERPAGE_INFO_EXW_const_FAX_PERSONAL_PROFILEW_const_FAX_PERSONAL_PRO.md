# GetMergedFileSize(ushort const *,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *)

- ea: `0x14003a808`
- end: `0x14003ab09`
- name: `?GetMergedFileSize@@YAKPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@2@Z`
- size: `769`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, const struct _FAX_COVERPAGE_INFO_EXW *, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_PERSONAL_PROFILEW *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14003735c`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14002f968`
- `0x140032b98`
- `0x14003a808`
- `0x140053b44`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003a8ac`
- `KERNEL32!GetLastError` at `0x14003a970`
- `KERNEL32!GetLastError` at `0x14003a9db`
- `KERNEL32!GetLastError` at `0x14003aa35`
- `KERNEL32!GetLastError` at `0x14003aaa1`
- `KERNEL32!GetLastError` at `0x14003a8ac`
- `KERNEL32!GetLastError` at `0x14003a970`
- `KERNEL32!GetLastError` at `0x14003a9db`
- `KERNEL32!GetLastError` at `0x14003aa35`
- `KERNEL32!GetLastError` at `0x14003aaa1`
- `KERNEL32!SetLastError` at `0x14003aad8`
- `KERNEL32!SetLastError` at `0x14003aad8`
- `KERNEL32!DeleteFileW` at `0x14003aa79`
- `KERNEL32!DeleteFileW` at `0x14003aa79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetMergedFileSize(
        const unsigned __int16 *a1,
        int a2,
        const struct _FAX_COVERPAGE_INFO_EXW *a3,
        const struct _FAX_PERSONAL_PROFILEW *a4,
        const struct _FAX_PERSONAL_PROFILEW *a5)
{
  __int16 v8; // si
  unsigned int FileSize; // edi
  CMapDeviceId *v11; // rcx
  DWORD LastError; // ebx
  DWORD v13; // eax
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  char v17; // al
  __int16 v19[8]; // [rsp+50h] [rbp-268h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-258h] BYREF

  v8 = 0;
  v19[0] = 0;
  FileSize = 0;
  memset_0(FileName, 0, 0x208u);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( !(unsigned int)GetBodyTiffResolution(a1, v19) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
      }
LABEL_40:
      SetLastError(LastError);
      return FileSize;
    }
    v8 = v19[0];
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v11 + 2), 33, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  if ( !(unsigned int)CreateCoverpageTiffFileEx2(v8, a2, a3, a5, a4, L"tmp", 0, FileName) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        203,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        *((_QWORD *)a3 + 1),
        LastError);
    }
    goto LABEL_40;
  }
  FileSize = MyGetFileSize(FileName);
  if ( FileSize )
  {
    v16 = 0;
    if ( !a1 || (v16 = MyGetFileSize(a1)) != 0 )
    {
      LastError = 0;
      FileSize += v16;
      goto LABEL_34;
    }
    v13 = GetLastError();
    LastError = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 205;
      goto LABEL_26;
    }
  }
  else
  {
    v13 = GetLastError();
    LastError = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 204;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
    }
  }
LABEL_34:
  if ( !DeleteFileW(FileName)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      206,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (unsigned int)FileName,
      v17);
  }
  if ( !FileSize )
    goto LABEL_40;
  return FileSize;
}

```

## disassembly

```asm
0x14003a808  push    rbx
0x14003a80a  push    rbp
0x14003a80b  push    rsi
0x14003a80c  push    rdi
0x14003a80d  push    r12
0x14003a80f  push    r14
0x14003a811  push    r15
0x14003a813  sub     rsp, 280h
0x14003a81a  mov     rax, cs:__security_cookie
0x14003a821  xor     rax, rsp
0x14003a824  mov     [rsp+2B8h+var_48], rax
0x14003a82c  mov     r12, [rsp+2B8h+arg_20]
0x14003a834  mov     rbp, r8
0x14003a837  mov     r14d, edx
0x14003a83a  mov     rbx, rcx
0x14003a83d  xor     esi, esi
0x14003a83f  lea     rcx, [rsp+2B8h+FileName]; void *
0x14003a844  xor     edx, edx; Val
0x14003a846  mov     [rsp+2B8h+var_268], si
0x14003a84b  mov     r8d, 208h; Size
0x14003a851  xor     edi, edi
0x14003a853  mov     r15, r9
0x14003a856  call    memset_0
0x14003a85b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a862  lea     rax, WPP_GLOBAL_Control
0x14003a869  cmp     rcx, rax
0x14003a86c  jz      short loc_14003A896
0x14003a86e  test    byte ptr [rcx+1Ch], 4
0x14003a872  jz      short loc_14003A896
0x14003a874  cmp     byte ptr [rcx+19h], 5
0x14003a878  jb      short loc_14003A896
0x14003a87a  mov     rcx, [rcx+10h]
0x14003a87e  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a885  mov     edx, 0C9h
0x14003a88a  call    WPP_SF_
0x14003a88f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a896  test    rbx, rbx
0x14003a899  jz      short loc_14003A90E
0x14003a89b  lea     rdx, [rsp+2B8h+var_268]; __int16 *
0x14003a8a0  mov     rcx, rbx; unsigned __int16 *
0x14003a8a3  call    ?GetBodyTiffResolution@@YAHPEBGPEAF@Z; GetBodyTiffResolution(ushort const *,short *)
0x14003a8a8  test    eax, eax
0x14003a8aa  jnz     short loc_14003A902
0x14003a8ac  call    cs:__imp_GetLastError
0x14003a8b3  nop     dword ptr [rax+rax+00h]
0x14003a8b8  mov     ebx, eax
0x14003a8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a8c1  lea     rax, WPP_GLOBAL_Control
0x14003a8c8  cmp     rcx, rax
0x14003a8cb  jz      loc_14003AAD6
0x14003a8d1  test    byte ptr [rcx+1Ch], 4
0x14003a8d5  jz      loc_14003AAD6
0x14003a8db  cmp     byte ptr [rcx+19h], 2
0x14003a8df  jb      loc_14003AAD6
0x14003a8e5  mov     rcx, [rcx+10h]
0x14003a8e9  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a8f0  mov     edx, 0CAh
0x14003a8f5  mov     r9d, ebx
0x14003a8f8  call    WPP_SF_d
0x14003a8fd  jmp     loc_14003AAD6
0x14003a902  movzx   esi, [rsp+2B8h+var_268]
0x14003a907  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a90e  lea     rax, WPP_GLOBAL_Control
0x14003a915  cmp     rcx, rax
0x14003a918  jz      short loc_14003A93B
0x14003a91a  test    byte ptr [rcx+1Ch], 4
0x14003a91e  jz      short loc_14003A93B
0x14003a920  cmp     byte ptr [rcx+19h], 5
0x14003a924  jb      short loc_14003A93B
0x14003a926  mov     rcx, [rcx+10h]
0x14003a92a  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003a931  mov     edx, 21h ; '!'
0x14003a936  call    WPP_SF_
0x14003a93b  lea     rax, [rsp+2B8h+FileName]
0x14003a940  mov     r9, r12; struct _FAX_PERSONAL_PROFILEW *
0x14003a943  mov     [rsp+2B8h+var_280], rax; unsigned __int16 *
0x14003a948  mov     r8, rbp; struct _FAX_COVERPAGE_INFO_EXW *
0x14003a94b  lea     rax, aTmp; "tmp"
0x14003a952  mov     [rsp+2B8h+var_288], rdi; unsigned __int16 *
0x14003a957  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x14003a95c  mov     edx, r14d; unsigned int
0x14003a95f  movzx   ecx, si; __int16
0x14003a962  mov     [rsp+2B8h+var_298], r15; struct _FAX_PERSONAL_PROFILEW *
0x14003a967  call    ?CreateCoverpageTiffFileEx2@@YAHFKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@1PEBG2PEAGK@Z; CreateCoverpageTiffFileEx2(short,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *,ushort const *,ushort const *,ushort *,ulong)
0x14003a96c  test    eax, eax
0x14003a96e  jnz     short loc_14003A9CB
0x14003a970  call    cs:__imp_GetLastError
0x14003a977  nop     dword ptr [rax+rax+00h]
0x14003a97c  mov     ebx, eax
0x14003a97e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a985  lea     rax, WPP_GLOBAL_Control
0x14003a98c  cmp     rcx, rax
0x14003a98f  jz      loc_14003AAD6
0x14003a995  test    byte ptr [rcx+1Ch], 4
0x14003a999  jz      loc_14003AAD6
0x14003a99f  cmp     byte ptr [rcx+19h], 2
0x14003a9a3  jb      loc_14003AAD6
0x14003a9a9  mov     r9, [rbp+8]
0x14003a9ad  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a9b4  mov     rcx, [rcx+10h]
0x14003a9b8  mov     edx, 0CBh
0x14003a9bd  mov     dword ptr [rsp+2B8h+var_298], ebx
0x14003a9c1  call    WPP_SF_Sd
0x14003a9c6  jmp     loc_14003AAD6
0x14003a9cb  lea     rcx, [rsp+2B8h+FileName]; unsigned __int16 *
0x14003a9d0  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x14003a9d5  mov     edi, eax
0x14003a9d7  test    eax, eax
0x14003a9d9  jnz     short loc_14003AA22
0x14003a9db  call    cs:__imp_GetLastError
0x14003a9e2  nop     dword ptr [rax+rax+00h]
0x14003a9e7  mov     ebx, eax
0x14003a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9f0  lea     rsi, WPP_GLOBAL_Control
0x14003a9f7  cmp     rcx, rsi
0x14003a9fa  jz      short loc_14003AA74
0x14003a9fc  test    byte ptr [rcx+1Ch], 4
0x14003aa00  jz      short loc_14003AA74
0x14003aa02  cmp     byte ptr [rcx+19h], 2
0x14003aa06  jb      short loc_14003AA74
0x14003aa08  mov     edx, 0CCh
0x14003aa0d  mov     rcx, [rcx+10h]
0x14003aa11  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003aa18  mov     r9d, eax
0x14003aa1b  call    WPP_SF_d
0x14003aa20  jmp     short loc_14003AA74
0x14003aa22  xor     eax, eax
0x14003aa24  test    rbx, rbx
0x14003aa27  jz      short loc_14003AA69
0x14003aa29  mov     rcx, rbx; unsigned __int16 *
0x14003aa2c  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x14003aa31  test    eax, eax
0x14003aa33  jnz     short loc_14003AA69
0x14003aa35  call    cs:__imp_GetLastError
0x14003aa3c  nop     dword ptr [rax+rax+00h]
0x14003aa41  mov     ebx, eax
0x14003aa43  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa4a  lea     rsi, WPP_GLOBAL_Control
0x14003aa51  cmp     rcx, rsi
0x14003aa54  jz      short loc_14003AA74
0x14003aa56  test    byte ptr [rcx+1Ch], 4
0x14003aa5a  jz      short loc_14003AA74
0x14003aa5c  cmp     byte ptr [rcx+19h], 2
0x14003aa60  jb      short loc_14003AA74
0x14003aa62  mov     edx, 0CDh
0x14003aa67  jmp     short loc_14003AA0D
0x14003aa69  xor     ebx, ebx
0x14003aa6b  lea     rsi, WPP_GLOBAL_Control
0x14003aa72  add     edi, eax
0x14003aa74  lea     rcx, [rsp+2B8h+FileName]; lpFileName
0x14003aa79  call    cs:__imp_DeleteFileW
0x14003aa80  nop     dword ptr [rax+rax+00h]
0x14003aa85  test    eax, eax
0x14003aa87  jnz     short loc_14003AAD2
0x14003aa89  mov     rax, cs:WPP_GLOBAL_Control
0x14003aa90  cmp     rax, rsi
0x14003aa93  jz      short loc_14003AAD2
0x14003aa95  test    byte ptr [rax+1Ch], 4
0x14003aa99  jz      short loc_14003AAD2
0x14003aa9b  cmp     byte ptr [rax+19h], 2
0x14003aa9f  jb      short loc_14003AAD2
0x14003aaa1  call    cs:__imp_GetLastError
0x14003aaa8  nop     dword ptr [rax+rax+00h]
0x14003aaad  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aab4  lea     r9, [rsp+2B8h+FileName]
0x14003aab9  mov     edx, 0CEh
0x14003aabe  mov     dword ptr [rsp+2B8h+var_298], eax
0x14003aac2  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003aac9  mov     rcx, [rcx+10h]
0x14003aacd  call    WPP_SF_Sd
0x14003aad2  test    edi, edi
0x14003aad4  jnz     short loc_14003AAE4
0x14003aad6  mov     ecx, ebx; dwErrCode
0x14003aad8  call    cs:__imp_SetLastError
0x14003aadf  nop     dword ptr [rax+rax+00h]
0x14003aae4  mov     eax, edi
0x14003aae6  mov     rcx, [rsp+2B8h+var_48]
0x14003aaee  xor     rcx, rsp; StackCookie
0x14003aaf1  call    __security_check_cookie
0x14003aaf6  add     rsp, 280h
0x14003aafd  pop     r15
0x14003aaff  pop     r14
0x14003ab01  pop     r12
0x14003ab03  pop     rdi
0x14003ab04  pop     rsi
0x14003ab05  pop     rbp
0x14003ab06  pop     rbx
0x14003ab07  retn
```
