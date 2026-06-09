# LaunchINFSectionW

- ea: `0x18000b8f0`
- end: `0x18000bc43`
- name: `LaunchINFSectionW`
- size: `851`
- prototype: `INT __stdcall(HWND hwndOwner, HINSTANCE hInstance, LPWSTR pszParams, INT nShow)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180008860`

## callees

- `0x1800022bc`
- `0x180003ce0`
- `0x180003e20`
- `0x180004880`
- `0x180006af8`
- `0x180008a6c`
- `0x18000b8f0`
- `0x18000c574`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `msvcrt!_wtol` at `0x18000ba0b`
- `msvcrt!_wtol` at `0x18000ba0b`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000ba81`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000ba81`
- `KERNEL32!GetFullPathNameW` at `0x18000ba4e`
- `KERNEL32!GetFullPathNameW` at `0x18000ba4e`
- `KERNEL32!GetFileAttributesW` at `0x18000ba6a`
- `KERNEL32!GetFileAttributesW` at `0x18000bb5b`
- `KERNEL32!GetFileAttributesW` at `0x18000ba6a`
- `KERNEL32!GetFileAttributesW` at `0x18000bb5b`

## string_xrefs

- `0x18000b91d`: `Advanced INF Install`

## pseudocode

```c
INT __stdcall LaunchINFSectionW(HWND hwndOwner, HINSTANCE hInstance, LPWSTR pszParams, INT nShow)
{
  const WCHAR *v5; // rsi
  unsigned __int16 *StringField; // rbx
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // r15
  char v10; // di
  UINT v11; // edx
  __int64 v12; // rax
  __int64 v13; // rcx
  WCHAR v14; // bx
  ULONG v16; // [rsp+20h] [rbp-E0h]
  ULONG v17; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v18; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v22[26]; // [rsp+260h] [rbp+160h]
  _BYTE v23[470]; // [rsp+27Ah] [rbp+17Ah] BYREF
  unsigned __int16 v24[264]; // [rsp+450h] [rbp+350h] BYREF

  v21 = *(_OWORD *)L"Advanced INF Install";
  v18 = pszParams;
  *(_OWORD *)v22 = *(_OWORD *)L" INF Install";
  *(_OWORD *)&v22[10] = *(_OWORD *)L"Install";
  memset_0(v23, 0, sizeof(v23));
  FilePart = 0;
  AdvWriteToLog(L"LaunchINFSection: Param=%1\r\n", pszParams);
  if ( !(unsigned int)SaveGlobalContext() )
    goto LABEL_31;
  pszTitleString = (LPCWSTR)&v21;
  v5 = 0;
  StringField = GetStringField(&v18, L",", 34, 1);
  v7 = GetStringField(&v18, L",", 34, 1);
  v8 = GetStringField(&v18, L",", 34, 1);
  v9 = GetStringField(&v18, L",", 34, 1);
  if ( v8 )
  {
    v10 = _wtol(v8);
    if ( (v10 & 1) != 0 )
      word_1800257D2 = 1;
  }
  else
  {
    v10 = 0;
  }
  if ( !StringField || !*StringField )
  {
    v11 = 1137;
    goto LABEL_29;
  }
  if ( GetFullPathNameW(StringField, 0x104u, Buffer, &FilePart) )
  {
    if ( GetFileAttributesW(Buffer) == -1 )
    {
      if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
      {
        v11 = 1126;
        goto LABEL_29;
      }
      PathIsUnc2(L"inf");
      PathCchCombineEx(Buffer, 0x104u, Buffer, L"inf", v16);
      StringCchCopyW(v24, 0x104u, (size_t *)Buffer);
      v12 = -1;
      v13 = -1;
      do
        ++v13;
      while ( Buffer[v13] );
      do
        ++v12;
      while ( StringField[v12] );
      v5 = StringField;
      if ( (unsigned __int64)(v13 + v12 + 2) > 0x104 )
      {
        v11 = 1145;
        goto LABEL_29;
      }
      if ( !(unsigned int)PathIsUnc2(StringField) && !IsExtendedLengthDosDevicePath(StringField) && *StringField == 92 )
      {
        do
          ++v5;
        while ( *v5 == 92 );
      }
      PathCchCombineEx(Buffer, 0x104u, Buffer, v5, v17);
      if ( GetFileAttributesW(Buffer) == -1 )
      {
        v11 = 1145;
        goto LABEL_10;
      }
    }
    else
    {
      v14 = *FilePart;
      *FilePart = 0;
      StringCchCopyW(v24, 0x104u, (size_t *)Buffer);
      *FilePart = v14;
    }
    if ( (int)CoreInstall(Buffer, v7, v24, 0, ~v10 & 2 | 5u, v9) >= 0 )
    {
      RestoreGlobalContext();
      AdvWriteToLog(L"LaunchINFSection: %1 End Succeed\r\n", Buffer);
      return 0;
    }
    goto LABEL_30;
  }
  v11 = 1140;
LABEL_10:
  v5 = StringField;
LABEL_29:
  MsgBox2Param(hWnd, v11, v5, 0, 0x10u, 0);
LABEL_30:
  RestoreGlobalContext();
LABEL_31:
  AdvWriteToLog(L"LaunchINFSection: %1 End Failed\r\n", Buffer);
  return 1;
}

```

## disassembly

```asm
0x18000b8f0  push    rbp
0x18000b8f2  push    rbx
0x18000b8f3  push    rsi
0x18000b8f4  push    rdi
0x18000b8f5  push    r12
0x18000b8f7  push    r13
0x18000b8f9  push    r14
0x18000b8fb  push    r15
0x18000b8fd  lea     rbp, [rsp-578h]
0x18000b905  sub     rsp, 678h
0x18000b90c  mov     rax, cs:__security_cookie
0x18000b913  xor     rax, rsp
0x18000b916  mov     [rbp+5B0h+var_50], rax
0x18000b91d  movups  xmm0, xmmword ptr cs:aAdvancedInfIns; "Advanced INF Install"
0x18000b924  mov     rbx, r8
0x18000b927  xor     edx, edx; Val
0x18000b929  movups  xmm1, xmmword ptr cs:aAdvancedInfIns+10h; " INF Install"
0x18000b930  lea     rcx, [rbp+5B0h+var_436]; void *
0x18000b937  mov     r8d, 1D6h; Size
0x18000b93d  movaps  [rbp+5B0h+var_460], xmm0
0x18000b944  movups  xmm0, xmmword ptr cs:aAdvancedInfIns+1Ah; "Install"
0x18000b94b  mov     [rsp+6B0h+var_680], rbx
0x18000b950  movaps  xmmword ptr [rbp+5B0h+var_450], xmm1
0x18000b957  movups  xmmword ptr [rbp+5B0h+var_450+0Ah], xmm0
0x18000b95e  call    memset_0
0x18000b963  xor     r13d, r13d
0x18000b966  lea     rcx, aLaunchinfsecti_5; "LaunchINFSection: Param=%1\r\n"
0x18000b96d  mov     rdx, rbx
0x18000b970  mov     [rsp+6B0h+FilePart], r13
0x18000b975  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000b97a  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x18000b97f  lea     edi, [r13+1]
0x18000b983  test    eax, eax
0x18000b985  jz      loc_18000BC0D
0x18000b98b  lea     rax, [rbp+5B0h+var_460]
0x18000b992  mov     r9d, edi; int
0x18000b995  lea     r12d, [r13+22h]
0x18000b999  mov     cs:pszTitleString, rax
0x18000b9a0  lea     r15, asc_18001E134; ","
0x18000b9a7  mov     r8d, r12d; unsigned __int16
0x18000b9aa  mov     rdx, r15; unsigned __int16 *
0x18000b9ad  lea     rcx, [rsp+6B0h+var_680]; unsigned __int16 **
0x18000b9b2  mov     esi, r13d
0x18000b9b5  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000b9ba  mov     r8d, r12d; unsigned __int16
0x18000b9bd  lea     rcx, [rsp+6B0h+var_680]; unsigned __int16 **
0x18000b9c2  mov     r9d, edi; int
0x18000b9c5  mov     rdx, r15; unsigned __int16 *
0x18000b9c8  mov     rbx, rax
0x18000b9cb  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000b9d0  mov     r8d, r12d; unsigned __int16
0x18000b9d3  lea     rcx, [rsp+6B0h+var_680]; unsigned __int16 **
0x18000b9d8  mov     r9d, edi; int
0x18000b9db  mov     rdx, r15; unsigned __int16 *
0x18000b9de  mov     r14, rax
0x18000b9e1  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000b9e6  mov     r8d, r12d; unsigned __int16
0x18000b9e9  lea     rcx, [rsp+6B0h+var_680]; unsigned __int16 **
0x18000b9ee  lea     r12d, [r13+1]
0x18000b9f2  mov     rdx, r15; unsigned __int16 *
0x18000b9f5  mov     r9d, r12d; int
0x18000b9f8  mov     rdi, rax
0x18000b9fb  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000ba00  mov     r15, rax
0x18000ba03  test    rdi, rdi
0x18000ba06  jz      short loc_18000BA22
0x18000ba08  mov     rcx, rdi; String
0x18000ba0b  call    cs:__imp__wtol
0x18000ba11  mov     edi, eax
0x18000ba13  test    r12b, al
0x18000ba16  jz      short loc_18000BA25
0x18000ba18  mov     cs:word_1800257D2, r12w
0x18000ba20  jmp     short loc_18000BA25
0x18000ba22  mov     edi, r13d
0x18000ba25  test    rbx, rbx
0x18000ba28  jz      loc_18000BBDF
0x18000ba2e  cmp     [rbx], r13w
0x18000ba32  jz      loc_18000BBDF
0x18000ba38  mov     r12d, 104h
0x18000ba3e  lea     r9, [rsp+6B0h+FilePart]; lpFilePart
0x18000ba43  mov     edx, r12d; nBufferLength
0x18000ba46  lea     r8, [rsp+6B0h+Buffer]; lpBuffer
0x18000ba4b  mov     rcx, rbx; lpFileName
0x18000ba4e  call    cs:__imp_GetFullPathNameW
0x18000ba54  test    eax, eax
0x18000ba56  jnz     short loc_18000BA65
0x18000ba58  mov     edx, 474h
0x18000ba5d  mov     rsi, rbx
0x18000ba60  jmp     loc_18000BBE4
0x18000ba65  lea     rcx, [rsp+6B0h+Buffer]; lpFileName
0x18000ba6a  call    cs:__imp_GetFileAttributesW
0x18000ba70  cmp     eax, 0FFFFFFFFh
0x18000ba73  jnz     loc_18000BB70
0x18000ba79  mov     edx, r12d; uSize
0x18000ba7c  lea     rcx, [rsp+6B0h+Buffer]; lpBuffer
0x18000ba81  call    cs:__imp_GetWindowsDirectoryW
0x18000ba87  test    eax, eax
0x18000ba89  jnz     short loc_18000BA95
0x18000ba8b  mov     edx, 466h
0x18000ba90  jmp     loc_18000BBE4
0x18000ba95  lea     r8, IsBackslash
0x18000ba9c  xor     edx, edx
0x18000ba9e  lea     rcx, aInf_0; "inf"
0x18000baa5  call    PathIsUnc2
0x18000baaa  lea     r9, aInf_0; "inf"
0x18000bab1  mov     rdx, r12; cchPathOut
0x18000bab4  lea     r8, [rsp+6B0h+Buffer]; pszPathIn
0x18000bab9  lea     rcx, [rsp+6B0h+Buffer]; pszPathOut
0x18000babe  call    PathCchCombineEx
0x18000bac3  lea     r8, [rsp+6B0h+Buffer]; unsigned __int16 *
0x18000bac8  mov     rdx, r12; unsigned __int64
0x18000bacb  lea     rcx, [rbp+5B0h+var_260]; unsigned __int16 *
0x18000bad2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bad7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000badb  lea     r11, [rsp+6B0h+Buffer]
0x18000bae0  mov     rcx, rax
0x18000bae3  inc     rcx
0x18000bae6  cmp     [r11+rcx*2], r13w
0x18000baeb  jnz     short loc_18000BAE3
0x18000baed  inc     rax
0x18000baf0  cmp     [rbx+rax*2], r13w
0x18000baf5  jnz     short loc_18000BAED
0x18000baf7  add     rax, 2
0x18000bafb  mov     rsi, rbx
0x18000bafe  add     rax, rcx
0x18000bb01  cmp     rax, r12
0x18000bb04  jbe     short loc_18000BB10
0x18000bb06  mov     edx, 479h
0x18000bb0b  jmp     loc_18000BBE4
0x18000bb10  lea     r8, IsBackslash
0x18000bb17  xor     edx, edx
0x18000bb19  mov     rcx, rbx; unsigned __int16 *
0x18000bb1c  call    PathIsUnc2
0x18000bb21  test    eax, eax
0x18000bb23  jnz     short loc_18000BB41
0x18000bb25  mov     rcx, rbx; unsigned __int16 *
0x18000bb28  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000bb2d  test    al, al
0x18000bb2f  jnz     short loc_18000BB41
0x18000bb31  cmp     word ptr [rbx], 5Ch ; '\'
0x18000bb35  jnz     short loc_18000BB41
0x18000bb37  add     rsi, 2
0x18000bb3b  cmp     word ptr [rsi], 5Ch ; '\'
0x18000bb3f  jz      short loc_18000BB37
0x18000bb41  mov     r9, rsi; pszMore
0x18000bb44  lea     r8, [rsp+6B0h+Buffer]; pszPathIn
0x18000bb49  mov     rdx, r12; cchPathOut
0x18000bb4c  lea     rcx, [rsp+6B0h+Buffer]; pszPathOut
0x18000bb51  call    PathCchCombineEx
0x18000bb56  lea     rcx, [rsp+6B0h+Buffer]; lpFileName
0x18000bb5b  call    cs:__imp_GetFileAttributesW
0x18000bb61  cmp     eax, 0FFFFFFFFh
0x18000bb64  jnz     short loc_18000BB99
0x18000bb66  mov     edx, 479h
0x18000bb6b  jmp     loc_18000BA5D
0x18000bb70  mov     rcx, [rsp+6B0h+FilePart]
0x18000bb75  lea     r8, [rsp+6B0h+Buffer]; unsigned __int16 *
0x18000bb7a  mov     rdx, r12; unsigned __int64
0x18000bb7d  movzx   ebx, word ptr [rcx]
0x18000bb80  mov     [rcx], r13w
0x18000bb84  lea     rcx, [rbp+5B0h+var_260]; unsigned __int16 *
0x18000bb8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb90  mov     r11, [rsp+6B0h+FilePart]
0x18000bb95  mov     [r11], bx
0x18000bb99  not     edi
0x18000bb9b  mov     [rsp+6B0h+var_688], r15; unsigned __int16 *
0x18000bba0  and     edi, 2
0x18000bba3  lea     r8, [rbp+5B0h+var_260]; unsigned __int16 *
0x18000bbaa  or      edi, 5
0x18000bbad  lea     rcx, [rsp+6B0h+Buffer]; unsigned __int16 *
0x18000bbb2  xor     r9d, r9d; unsigned int
0x18000bbb5  mov     [rsp+6B0h+var_690], edi; ULONG
0x18000bbb9  mov     rdx, r14; unsigned __int16 *
0x18000bbbc  call    ?CoreInstall@@YAJPEBG00KK0@Z; CoreInstall(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *)
0x18000bbc1  test    eax, eax
0x18000bbc3  js      short loc_18000BC03
0x18000bbc5  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000bbca  lea     rdx, [rsp+6B0h+Buffer]
0x18000bbcf  lea     rcx, aLaunchinfsecti_8; "LaunchINFSection: %1 End Succeed\r\n"
0x18000bbd6  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000bbdb  xor     eax, eax
0x18000bbdd  jmp     short loc_18000BC20
0x18000bbdf  mov     edx, 471h; uID
0x18000bbe4  mov     rcx, cs:hWnd; hWnd
0x18000bbeb  xor     r9d, r9d; unsigned __int16 *
0x18000bbee  mov     dword ptr [rsp+6B0h+var_688], r13d; unsigned int
0x18000bbf3  mov     r8, rsi; unsigned __int16 *
0x18000bbf6  mov     [rsp+6B0h+var_690], 10h; unsigned int
0x18000bbfe  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000bc03  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000bc08  mov     edi, 1
0x18000bc0d  lea     rdx, [rsp+6B0h+Buffer]
0x18000bc12  lea     rcx, aLaunchinfsecti_9; "LaunchINFSection: %1 End Failed\r\n"
0x18000bc19  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000bc1e  mov     eax, edi
0x18000bc20  mov     rcx, [rbp+5B0h+var_50]
0x18000bc27  xor     rcx, rsp; StackCookie
0x18000bc2a  call    __security_check_cookie
0x18000bc2f  add     rsp, 678h
0x18000bc36  pop     r15
0x18000bc38  pop     r14
0x18000bc3a  pop     r13
0x18000bc3c  pop     r12
0x18000bc3e  pop     rdi
0x18000bc3f  pop     rsi
0x18000bc40  pop     rbx
0x18000bc41  pop     rbp
0x18000bc42  retn
```
