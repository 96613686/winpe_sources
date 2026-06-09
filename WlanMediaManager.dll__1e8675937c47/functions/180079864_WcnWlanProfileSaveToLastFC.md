# WcnWlanProfileSaveToLastFC

- ea: `0x180079864`
- end: `0x180079bb2`
- name: `WcnWlanProfileSaveToLastFC`
- size: `846`
- prototype: `__int64 __fastcall(BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18007972c`

## callees

- `0x180003ed0`
- `0x18001d4d4`
- `0x180076f84`
- `0x180076fe0`
- `0x1800795fc`
- `0x180079864`
- `0x180079fa4`
- `0x180088304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007997d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007997d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079adb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079b33`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180079abd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180079abd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079a31`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180079a31`
- `CRYPT32!CryptProtectData` at `0x180079969`
- `CRYPT32!CryptProtectData` at `0x180079969`

## string_xrefs

- `0x180079909`: `wszWlanXmlProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WcnWlanProfileSaveToLastFC(BYTE *a1)
{
  PVOID *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // edx
  unsigned int LastError; // ebx
  signed int v10; // ebx
  PVOID *v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10
  int v14; // edx
  int LastFcDirectory; // eax
  HANDLE FileW; // rax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // r10
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  NumberOfBytesWritten = 0;
  pDataIn = 0;
  pDataOut = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 17, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u )
      WPP_SF_s(v2[2], 18, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, "wszWlanXmlProfile");
    return 2147500035LL;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&a1[2 * v7] );
  pDataIn.pbData = a1;
  pDataIn.cbData = 2 * v7 + 2;
  if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v10 = LastError | 0x80000000;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    v12 = (unsigned int)GetIndent(0);
    v14 = 19;
    goto LABEL_36;
  }
  LastFcDirectory = WcnGetLastFcDirectory(FileName, v8);
  v10 = LastFcDirectory;
  if ( LastFcDirectory >= 0 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 6u, 0);
    v6 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      if ( (int)GetLastError() > 0 )
        v17 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v17 = GetLastError();
      v10 = v17 | 0x80000000;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_38;
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_sSd(*(_QWORD *)(v19 + 16), v20, v21, v18, (__int64)FileName, v10);
      goto LABEL_37;
    }
    if ( !WriteFile(FileW, pDataOut.pbData, pDataOut.cbData, &NumberOfBytesWritten, 0) )
    {
      if ( (int)GetLastError() > 0 )
        v22 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v22 = GetLastError();
      v10 = v22 | 0x80000000;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_38;
      v12 = (unsigned int)GetIndent(0);
      v14 = 22;
LABEL_36:
      WPP_SF_sd(*(_QWORD *)(v13 + 16), v14, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v12, v10);
    }
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_38;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids,
      (unsigned int)LastFcDirectory);
  }
LABEL_37:
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
  if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != -1 )
  {
    CloseHandle((HANDLE)v6);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)v11 + 25) >= 6u) )
  {
    v23 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v24 + 16), 23, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v23, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180079864  mov     [rsp-8+arg_8], rbx
0x180079869  mov     [rsp-8+arg_10], rsi
0x18007986e  push    rbp
0x18007986f  push    rdi
0x180079870  push    r12
0x180079872  push    r14
0x180079874  push    r15
0x180079876  lea     rbp, [rsp-190h]
0x18007987e  sub     rsp, 290h
0x180079885  mov     rax, cs:__security_cookie
0x18007988c  xor     rax, rsp
0x18007988f  mov     [rbp+1B0h+var_30], rax
0x180079896  xor     esi, esi
0x180079898  xorps   xmm0, xmm0
0x18007989b  xorps   xmm1, xmm1
0x18007989e  mov     [rsp+2B0h+NumberOfBytesWritten], esi
0x1800798a2  movups  xmmword ptr [rsp+2B0h+pDataIn.cbData], xmm0
0x1800798a7  mov     rbx, rcx
0x1800798aa  movups  xmmword ptr [rsp+2B0h+var_268.cbData], xmm1
0x1800798af  mov     r10, cs:WPP_GLOBAL_Control
0x1800798b6  lea     r14, WPP_GLOBAL_Control
0x1800798bd  lea     r12, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x1800798c4  cmp     r10, r14
0x1800798c7  jz      short loc_1800798F1
0x1800798c9  cmp     byte ptr [r10+19h], 6
0x1800798ce  jb      short loc_1800798F1
0x1800798d0  lea     ecx, [rsi+1]; int
0x1800798d3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800798d8  mov     rcx, [r10+10h]
0x1800798dc  lea     edx, [rsi+11h]
0x1800798df  mov     r9, rax
0x1800798e2  mov     r8, r12
0x1800798e5  call    WPP_SF_s
0x1800798ea  mov     r10, cs:WPP_GLOBAL_Control
0x1800798f1  test    rbx, rbx
0x1800798f4  jnz     short loc_180079922
0x1800798f6  cmp     r10, r14
0x1800798f9  jz      short loc_180079918
0x1800798fb  cmp     byte ptr [r10+19h], 2
0x180079900  jb      short loc_180079918
0x180079902  mov     rcx, [r10+10h]
0x180079906  lea     edx, [rbx+12h]
0x180079909  lea     r9, aWszwlanxmlprof; "wszWlanXmlProfile"
0x180079910  mov     r8, r12
0x180079913  call    WPP_SF_s
0x180079918  mov     eax, 80004003h
0x18007991d  jmp     loc_180079B87
0x180079922  or      r15, 0FFFFFFFFFFFFFFFFh
0x180079926  mov     rdi, r15
0x180079929  mov     rax, r15
0x18007992c  inc     rax
0x18007992f  cmp     [rbx+rax*2], si
0x180079933  jnz     short loc_18007992C
0x180079935  lea     eax, ds:2[rax*2]
0x18007993c  mov     [rsp+2B0h+pDataIn.pbData], rbx
0x180079941  mov     [rsp+2B0h+pDataIn.cbData], eax
0x180079945  lea     rcx, [rsp+2B0h+pDataIn]; pDataIn
0x18007994a  lea     rax, [rsp+2B0h+var_268]
0x18007994f  xor     r9d, r9d; pvReserved
0x180079952  mov     [rsp+2B0h+pDataOut], rax; pDataOut
0x180079957  xor     r8d, r8d; pOptionalEntropy
0x18007995a  mov     [rsp+2B0h+dwFlags], 1; dwFlags
0x180079962  xor     edx, edx; szDataDescr
0x180079964  mov     [rsp+2B0h+pPromptStruct], rsi; pPromptStruct
0x180079969  call    cs:__imp_CryptProtectData
0x18007996f  test    eax, eax
0x180079971  jnz     short loc_1800799C8
0x180079973  call    cs:__imp_GetLastError
0x180079979  test    eax, eax
0x18007997b  jg      short loc_180079987
0x18007997d  call    cs:__imp_GetLastError
0x180079983  mov     ebx, eax
0x180079985  jmp     short loc_180079996
0x180079987  call    cs:__imp_GetLastError
0x18007998d  movzx   ebx, ax
0x180079990  or      ebx, 80070000h
0x180079996  or      ebx, 80000000h
0x18007999c  mov     r10, cs:WPP_GLOBAL_Control
0x1800799a3  cmp     r10, r14
0x1800799a6  jz      loc_180079B29
0x1800799ac  cmp     byte ptr [r10+19h], 2
0x1800799b1  jb      loc_180079B29
0x1800799b7  xor     ecx, ecx; int
0x1800799b9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800799be  mov     edx, 13h
0x1800799c3  jmp     loc_180079B0F
0x1800799c8  lea     rcx, [rsp+2B0h+FileName]; Buffer
0x1800799cd  call    ?WcnGetLastFcDirectory@@YAJPEAGK@Z; WcnGetLastFcDirectory(ushort *,ulong)
0x1800799d2  mov     ebx, eax
0x1800799d4  test    eax, eax
0x1800799d6  jns     short loc_180079A0C
0x1800799d8  mov     r10, cs:WPP_GLOBAL_Control
0x1800799df  cmp     r10, r14
0x1800799e2  jz      loc_180079B29
0x1800799e8  cmp     byte ptr [r10+19h], 2
0x1800799ed  jb      loc_180079B29
0x1800799f3  mov     rcx, [r10+10h]
0x1800799f7  mov     edx, 14h
0x1800799fc  mov     r9d, eax
0x1800799ff  mov     r8, r12
0x180079a02  call    WPP_SF_d
0x180079a07  jmp     loc_180079B22
0x180079a0c  mov     [rsp+2B0h+pDataOut], rsi; hTemplateFile
0x180079a11  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180079a16  mov     [rsp+2B0h+dwFlags], 6; dwFlagsAndAttributes
0x180079a1e  xor     r9d, r9d; lpSecurityAttributes
0x180079a21  xor     r8d, r8d; dwShareMode
0x180079a24  mov     dword ptr [rsp+2B0h+pPromptStruct], 2; dwCreationDisposition
0x180079a2c  mov     edx, 40000000h; dwDesiredAccess
0x180079a31  call    cs:__imp_CreateFileW
0x180079a37  mov     rdi, rax
0x180079a3a  cmp     rax, r15
0x180079a3d  jnz     short loc_180079AA6
0x180079a3f  call    cs:__imp_GetLastError
0x180079a45  test    eax, eax
0x180079a47  jg      short loc_180079A53
0x180079a49  call    cs:__imp_GetLastError
0x180079a4f  mov     ebx, eax
0x180079a51  jmp     short loc_180079A62
0x180079a53  call    cs:__imp_GetLastError
0x180079a59  movzx   ebx, ax
0x180079a5c  or      ebx, 80070000h
0x180079a62  or      ebx, 80000000h
0x180079a68  mov     r10, cs:WPP_GLOBAL_Control
0x180079a6f  cmp     r10, r14
0x180079a72  jz      loc_180079B29
0x180079a78  cmp     byte ptr [r10+19h], 2
0x180079a7d  jb      loc_180079B29
0x180079a83  xor     ecx, ecx; int
0x180079a85  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079a8a  lea     rcx, [rsp+2B0h+FileName]
0x180079a8f  mov     [rsp+2B0h+dwFlags], ebx
0x180079a93  mov     [rsp+2B0h+pPromptStruct], rcx
0x180079a98  mov     r9, rax
0x180079a9b  mov     rcx, [r10+10h]
0x180079a9f  call    WPP_SF_sSd
0x180079aa4  jmp     short loc_180079B22
0x180079aa6  mov     r8d, [rsp+2B0h+var_268.cbData]; nNumberOfBytesToWrite
0x180079aab  lea     r9, [rsp+2B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180079ab0  mov     rdx, [rsp+2B0h+var_268.pbData]; lpBuffer
0x180079ab5  mov     rcx, rax; hFile
0x180079ab8  mov     [rsp+2B0h+pPromptStruct], rsi; lpOverlapped
0x180079abd  call    cs:__imp_WriteFile
0x180079ac3  test    eax, eax
0x180079ac5  jnz     short loc_180079B22
0x180079ac7  call    cs:__imp_GetLastError
0x180079acd  test    eax, eax
0x180079acf  jg      short loc_180079ADB
0x180079ad1  call    cs:__imp_GetLastError
0x180079ad7  mov     ebx, eax
0x180079ad9  jmp     short loc_180079AEA
0x180079adb  call    cs:__imp_GetLastError
0x180079ae1  movzx   ebx, ax
0x180079ae4  or      ebx, 80070000h
0x180079aea  or      ebx, 80000000h
0x180079af0  mov     r10, cs:WPP_GLOBAL_Control
0x180079af7  cmp     r10, r14
0x180079afa  jz      short loc_180079B29
0x180079afc  cmp     byte ptr [r10+19h], 2
0x180079b01  jb      short loc_180079B29
0x180079b03  xor     ecx, ecx; int
0x180079b05  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079b0a  mov     edx, 16h
0x180079b0f  mov     rcx, [r10+10h]
0x180079b13  mov     r9, rax
0x180079b16  mov     r8, r12
0x180079b19  mov     dword ptr [rsp+2B0h+pPromptStruct], ebx
0x180079b1d  call    WPP_SF_sd
0x180079b22  mov     r10, cs:WPP_GLOBAL_Control
0x180079b29  mov     rcx, [rsp+2B0h+var_268.pbData]; hMem
0x180079b2e  test    rcx, rcx
0x180079b31  jz      short loc_180079B40
0x180079b33  call    cs:__imp_LocalFree
0x180079b39  mov     r10, cs:WPP_GLOBAL_Control
0x180079b40  cmp     rdi, r15
0x180079b43  jz      short loc_180079B55
0x180079b45  mov     rcx, rdi; hObject
0x180079b48  call    cs:__imp_CloseHandle
0x180079b4e  mov     r10, cs:WPP_GLOBAL_Control
0x180079b55  cmp     r10, r14
0x180079b58  jz      short loc_180079B85
0x180079b5a  test    ebx, ebx
0x180079b5c  js      short loc_180079B65
0x180079b5e  cmp     byte ptr [r10+19h], 6
0x180079b63  jb      short loc_180079B85
0x180079b65  mov     ecx, r15d; int
0x180079b68  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180079b6d  mov     rcx, [r10+10h]
0x180079b71  mov     edx, 17h
0x180079b76  mov     r9, rax
0x180079b79  mov     dword ptr [rsp+2B0h+pPromptStruct], ebx
0x180079b7d  mov     r8, r12
0x180079b80  call    WPP_SF_sd
0x180079b85  mov     eax, ebx
0x180079b87  mov     rcx, [rbp+1B0h+var_30]
0x180079b8e  xor     rcx, rsp; StackCookie
0x180079b91  call    __security_check_cookie
0x180079b96  lea     r11, [rsp+2B0h+var_20]
0x180079b9e  mov     rbx, [r11+38h]
0x180079ba2  mov     rsi, [r11+40h]
0x180079ba6  mov     rsp, r11
0x180079ba9  pop     r15
0x180079bab  pop     r14
0x180079bad  pop     r12
0x180079baf  pop     rdi
0x180079bb0  pop     rbp
0x180079bb1  retn
```
