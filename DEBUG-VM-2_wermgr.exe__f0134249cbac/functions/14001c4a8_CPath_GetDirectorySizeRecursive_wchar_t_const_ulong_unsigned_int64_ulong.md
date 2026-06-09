# CPath::GetDirectorySizeRecursive(wchar_t const *,ulong,unsigned __int64 *,ulong *)

- ea: `0x14001c4a8`
- end: `0x14001c825`
- name: `?GetDirectorySizeRecursive@CPath@@SAJPEB_WKPEA_KPEAK@Z`
- size: `893`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned __int64 *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400058ec`
- `0x14001c4a8`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140003224`
- `0x14000e340`
- `0x14001c23c`
- `0x14001c4a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c629`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c63e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c629`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c63e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c72f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c72f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c75e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14001c5eb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14001c5eb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001c6be`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14001c6be`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14001c7fa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14001c7fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPath::GetDirectorySizeRecursive(
        const wchar_t *a1,
        unsigned int a2,
        unsigned __int64 *a3,
        unsigned int *a4)
{
  __int64 FirstFile; // r15
  int v8; // r12d
  int DirectorySizeRecursive; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rsi
  unsigned int v14; // edi
  unsigned int v15; // ebx
  signed int LastError; // eax
  int v17; // eax
  unsigned int v20; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v24[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v26[8]; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v27; // [rsp+88h] [rbp-78h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v27 = a1;
  FirstFile = -1;
  lpFileName[0] = v26;
  lpFileName[1] = v26;
  v8 = 0;
  v26[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v22 = 0;
  v20 = 0;
  v23[0] = v24;
  v23[1] = v24;
  v24[0] = 0;
  v21 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a3 )
  {
    DirectorySizeRecursive = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 17;
      v12 = 2147942487LL;
LABEL_49:
      WPP_SF_d(v10[2], v11, WPP_74b024c659e0370c20fde454c384f757_Traceguids, v12);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  DirectorySizeRecursive = CPath::Append(a1, L"*", lpFileName);
  if ( DirectorySizeRecursive < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v11 = 18;
LABEL_48:
    v12 = (unsigned int)DirectorySizeRecursive;
    goto LABEL_49;
  }
  FirstFile = (__int64)FindFirstFileExW(lpFileName[0], FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v28 = FirstFile;
  if ( FirstFile != -1 )
  {
    v13 = 0;
    v14 = 0;
    v15 = a2;
    while ( 1 )
    {
      if ( v15 < 0x80
        && (FindFileData.dwFileAttributes & 0x10) != 0
        && (unsigned int)_o__wcsicmp(FindFileData.cFileName, L".")
        && (unsigned int)_o__wcsicmp(FindFileData.cFileName, L"..")
        && FindFileData.cFileName[0] )
      {
        DirectorySizeRecursive = CPath::Append(v27, FindFileData.cFileName, v23);
        if ( DirectorySizeRecursive < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 20;
            goto LABEL_48;
          }
          goto LABEL_50;
        }
        DirectorySizeRecursive = CPath::GetDirectorySizeRecursive(v23[0], a2 + 1, &v22, &v20);
        if ( DirectorySizeRecursive < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 21;
            goto LABEL_48;
          }
          goto LABEL_50;
        }
        v13 += v22;
        v14 += v20;
        v15 = a2;
      }
      if ( (FindFileData.dwFileAttributes & 0x11450) == 0 )
      {
        v21 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
        v13 += __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
        ++v14;
      }
      if ( !FindNextFileW((HANDLE)FirstFile, &FindFileData) )
        break;
      if ( (unsigned int)++v8 >= 0x10000 )
        goto LABEL_37;
    }
    LastError = GetLastError();
    DirectorySizeRecursive = LastError;
    if ( LastError > 0 )
      DirectorySizeRecursive = (unsigned __int16)LastError | 0x80070000;
    if ( DirectorySizeRecursive == -2147024878 )
    {
LABEL_37:
      *a3 = v13;
      if ( a4 )
        *a4 = v14;
      DirectorySizeRecursive = 0;
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  DirectorySizeRecursive = GetLastError();
  if ( (unsigned int)DirectorySizeRecursive <= 0x12 )
  {
    v17 = 262188;
    if ( _bittest(&v17, DirectorySizeRecursive) )
    {
      DirectorySizeRecursive = 0;
      goto LABEL_50;
    }
  }
  if ( DirectorySizeRecursive > 0 )
    DirectorySizeRecursive = (unsigned __int16)DirectorySizeRecursive | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 19;
    goto LABEL_48;
  }
LABEL_50:
  if ( v23[0] != v24 )
    operator delete(v23[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v26 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FirstFile != -1 )
    FindClose((HANDLE)FirstFile);
  return (unsigned int)DirectorySizeRecursive;
}

```

## disassembly

```asm
0x14001c4a8  push    rbp
0x14001c4aa  push    rbx
0x14001c4ab  push    rsi
0x14001c4ac  push    rdi
0x14001c4ad  push    r12
0x14001c4af  push    r13
0x14001c4b1  push    r14
0x14001c4b3  push    r15
0x14001c4b5  lea     rbp, [rsp-208h]
0x14001c4bd  sub     rsp, 308h
0x14001c4c4  mov     rax, cs:__security_cookie
0x14001c4cb  xor     rax, rsp
0x14001c4ce  mov     [rbp+240h+var_50], rax
0x14001c4d5  mov     r14, r9
0x14001c4d8  mov     r13, r8
0x14001c4db  mov     [rsp+340h+var_310], edx
0x14001c4df  mov     rbx, rcx
0x14001c4e2  mov     [rbp+240h+var_2B8], rcx
0x14001c4e6  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001c4ea  lea     rax, [rsp+340h+var_2C8]
0x14001c4ef  mov     [rsp+340h+lpFileName], rax
0x14001c4f4  lea     rax, [rsp+340h+var_2C8]
0x14001c4f9  mov     [rsp+340h+var_2D0], rax
0x14001c4fe  xor     r12d, r12d
0x14001c501  mov     [rsp+340h+var_2C8], r12w
0x14001c507  xor     edx, edx; Val
0x14001c509  mov     r8d, 250h; Size
0x14001c50f  lea     rcx, [rbp+240h+FindFileData]; void *
0x14001c513  call    memset_0
0x14001c518  mov     [rsp+340h+var_300], r12
0x14001c51d  mov     [rsp+340h+var_30C], r12d
0x14001c522  lea     rax, [rsp+340h+var_2E8]
0x14001c527  mov     [rsp+340h+var_2F8], rax
0x14001c52c  lea     rax, [rsp+340h+var_2E8]
0x14001c531  mov     [rsp+340h+var_2F0], rax
0x14001c536  mov     [rsp+340h+var_2E8], r12w
0x14001c53c  mov     [rsp+340h+var_308], r12
0x14001c541  test    r13, r13
0x14001c544  jz      short loc_14001C54A
0x14001c546  mov     [r13+0], r12
0x14001c54a  test    r14, r14
0x14001c54d  jz      short loc_14001C552
0x14001c54f  mov     [r14], r12d
0x14001c552  test    r13, r13
0x14001c555  jnz     short loc_14001C58C
0x14001c557  mov     ebx, 80070057h
0x14001c55c  lea     rax, WPP_GLOBAL_Control
0x14001c563  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c56a  cmp     rcx, rax
0x14001c56d  jz      loc_14001C7B9
0x14001c573  test    byte ptr [rcx+1Ch], 1
0x14001c577  jz      loc_14001C7B9
0x14001c57d  lea     edx, [r13+11h]
0x14001c581  mov     r9d, 80070057h
0x14001c587  jmp     loc_14001C7A8
0x14001c58c  lea     r8, [rsp+340h+lpFileName]
0x14001c591  lea     rdx, asc_14002379C; "*"
0x14001c598  mov     rcx, rbx
0x14001c59b  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001c5a0  mov     ebx, eax
0x14001c5a2  test    eax, eax
0x14001c5a4  jns     short loc_14001C5D1
0x14001c5a6  lea     rax, WPP_GLOBAL_Control
0x14001c5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c5b4  cmp     rcx, rax
0x14001c5b7  jz      loc_14001C7B9
0x14001c5bd  test    byte ptr [rcx+1Ch], 1
0x14001c5c1  jz      loc_14001C7B9
0x14001c5c7  mov     edx, 12h
0x14001c5cc  jmp     loc_14001C7A5
0x14001c5d1  mov     [rsp+340h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x14001c5d6  mov     [rsp+340h+lpSearchFilter], r12; lpSearchFilter
0x14001c5db  xor     r9d, r9d; fSearchOp
0x14001c5de  lea     r8, [rbp+240h+FindFileData]; lpFindFileData
0x14001c5e2  lea     edx, [r9+1]; fInfoLevelId
0x14001c5e6  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x14001c5eb  call    cs:__imp_FindFirstFileExW
0x14001c5f1  mov     r15, rax
0x14001c5f4  mov     [rbp+240h+var_2B0], rax
0x14001c5f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c5fc  jz      loc_14001C75E
0x14001c602  mov     rsi, r12
0x14001c605  mov     edi, r12d
0x14001c608  mov     ebx, [rsp+340h+var_310]
0x14001c60c  cmp     ebx, 80h
0x14001c612  jnb     loc_14001C699
0x14001c618  test    byte ptr [rbp+240h+FindFileData], 10h
0x14001c61c  jz      short loc_14001C699
0x14001c61e  lea     rdx, asc_1400241F0; "."
0x14001c625  lea     rcx, [rbp+240h+var_274]
0x14001c629  call    cs:__imp__o__wcsicmp
0x14001c62f  test    eax, eax
0x14001c631  jz      short loc_14001C699
0x14001c633  lea     rdx, asc_140021C24; ".."
0x14001c63a  lea     rcx, [rbp+240h+var_274]
0x14001c63e  call    cs:__imp__o__wcsicmp
0x14001c644  xor     ecx, ecx
0x14001c646  test    eax, eax
0x14001c648  jz      short loc_14001C699
0x14001c64a  cmp     [rbp+240h+var_274], cx
0x14001c64e  jz      short loc_14001C699
0x14001c650  lea     r8, [rsp+340h+var_2F8]
0x14001c655  lea     rdx, [rbp+240h+var_274]
0x14001c659  mov     rcx, [rbp+240h+var_2B8]
0x14001c65d  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001c662  mov     ebx, eax
0x14001c664  test    eax, eax
0x14001c666  js      loc_14001C707
0x14001c66c  mov     edx, [rsp+340h+var_310]
0x14001c670  inc     edx; unsigned int
0x14001c672  lea     r9, [rsp+340h+var_30C]; unsigned int *
0x14001c677  lea     r8, [rsp+340h+var_300]; unsigned __int64 *
0x14001c67c  mov     rcx, [rsp+340h+var_2F8]; wchar_t *
0x14001c681  call    ?GetDirectorySizeRecursive@CPath@@SAJPEB_WKPEA_KPEAK@Z; CPath::GetDirectorySizeRecursive(wchar_t const *,ulong,unsigned __int64 *,ulong *)
0x14001c686  mov     ebx, eax
0x14001c688  test    eax, eax
0x14001c68a  js      short loc_14001C6DC
0x14001c68c  add     rsi, [rsp+340h+var_300]
0x14001c691  add     edi, [rsp+340h+var_30C]
0x14001c695  mov     ebx, [rsp+340h+var_310]
0x14001c699  test    [rbp+240h+FindFileData], 11450h
0x14001c6a0  jnz     short loc_14001C6B7
0x14001c6a2  mov     eax, [rbp+240h+var_280]
0x14001c6a5  mov     dword ptr [rsp+340h+var_308], eax
0x14001c6a9  mov     eax, [rbp+240h+var_284]
0x14001c6ac  mov     dword ptr [rsp+340h+var_308+4], eax
0x14001c6b0  add     rsi, [rsp+340h+var_308]
0x14001c6b5  inc     edi
0x14001c6b7  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x14001c6bb  mov     rcx, r15; hFindFile
0x14001c6be  call    cs:__imp_FindNextFileW
0x14001c6c4  xor     ecx, ecx
0x14001c6c6  test    eax, eax
0x14001c6c8  jz      short loc_14001C72F
0x14001c6ca  inc     r12d
0x14001c6cd  cmp     r12d, 10000h
0x14001c6d4  jb      loc_14001C60C
0x14001c6da  jmp     short loc_14001C74E
0x14001c6dc  lea     rax, WPP_GLOBAL_Control
0x14001c6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6ea  cmp     rcx, rax
0x14001c6ed  jz      loc_14001C7B9
0x14001c6f3  test    byte ptr [rcx+1Ch], 1
0x14001c6f7  jz      loc_14001C7B9
0x14001c6fd  mov     edx, 15h
0x14001c702  jmp     loc_14001C7A5
0x14001c707  lea     rax, WPP_GLOBAL_Control
0x14001c70e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c715  cmp     rcx, rax
0x14001c718  jz      loc_14001C7B9
0x14001c71e  test    byte ptr [rcx+1Ch], 1
0x14001c722  jz      loc_14001C7B9
0x14001c728  mov     edx, 14h
0x14001c72d  jmp     short loc_14001C7A5
0x14001c72f  call    cs:__imp_GetLastError
0x14001c735  mov     ebx, eax
0x14001c737  xor     ecx, ecx
0x14001c739  test    eax, eax
0x14001c73b  jle     short loc_14001C746
0x14001c73d  movzx   ebx, ax
0x14001c740  or      ebx, 80070000h
0x14001c746  cmp     ebx, 80070012h
0x14001c74c  jnz     short loc_14001C7B9
0x14001c74e  mov     [r13+0], rsi
0x14001c752  test    r14, r14
0x14001c755  jz      short loc_14001C75A
0x14001c757  mov     [r14], edi
0x14001c75a  mov     ebx, ecx
0x14001c75c  jmp     short loc_14001C7B9
0x14001c75e  call    cs:__imp_GetLastError
0x14001c764  mov     ebx, eax
0x14001c766  cmp     eax, 12h
0x14001c769  ja      short loc_14001C77A
0x14001c76b  mov     eax, 4002Ch
0x14001c770  bt      eax, ebx
0x14001c773  jnb     short loc_14001C77A
0x14001c775  mov     ebx, r12d
0x14001c778  jmp     short loc_14001C7B9
0x14001c77a  test    ebx, ebx
0x14001c77c  jle     short loc_14001C787
0x14001c77e  movzx   ebx, bx
0x14001c781  or      ebx, 80070000h
0x14001c787  lea     rax, WPP_GLOBAL_Control
0x14001c78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c795  cmp     rcx, rax
0x14001c798  jz      short loc_14001C7B9
0x14001c79a  test    byte ptr [rcx+1Ch], 1
0x14001c79e  jz      short loc_14001C7B9
0x14001c7a0  mov     edx, 13h
0x14001c7a5  mov     r9d, ebx
0x14001c7a8  lea     r8, WPP_74b024c659e0370c20fde454c384f757_Traceguids
0x14001c7af  mov     rcx, [rcx+10h]
0x14001c7b3  call    WPP_SF_d
0x14001c7b8  nop
0x14001c7b9  lea     rax, [rsp+340h+var_2E8]
0x14001c7be  mov     rcx, [rsp+340h+var_2F8]; void *
0x14001c7c3  cmp     rcx, rax
0x14001c7c6  jz      short loc_14001C7D5
0x14001c7c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c7cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c7d4  nop
0x14001c7d5  lea     rax, [rsp+340h+var_2C8]
0x14001c7da  mov     rcx, [rsp+340h+lpFileName]; void *
0x14001c7df  cmp     rcx, rax
0x14001c7e2  jz      short loc_14001C7F1
0x14001c7e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c7eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001c7f0  nop
0x14001c7f1  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14001c7f5  jz      short loc_14001C800
0x14001c7f7  mov     rcx, r15; hFindFile
0x14001c7fa  call    cs:__imp_FindClose
0x14001c800  mov     eax, ebx
0x14001c802  mov     rcx, [rbp+240h+var_50]
0x14001c809  xor     rcx, rsp; StackCookie
0x14001c80c  call    __security_check_cookie
0x14001c811  add     rsp, 308h
0x14001c818  pop     r15
0x14001c81a  pop     r14
0x14001c81c  pop     r13
0x14001c81e  pop     r12
0x14001c820  pop     rdi
0x14001c821  pop     rsi
0x14001c822  pop     rbx
0x14001c823  pop     rbp
0x14001c824  retn
```
