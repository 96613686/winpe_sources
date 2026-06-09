# CVaultFileStore::InitializeOrDeleteSchema(uchar,IVaultFileSystem *)

- ea: `0x180011a94`
- end: `0x180011ea4`
- name: `?InitializeOrDeleteSchema@CVaultFileStore@@AEAAKEPEAUIVaultFileSystem@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CVaultFileStore *this, char, struct IVaultFileSystem *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180019dec`
- `0x1800398d0`

## callees

- `0x180003140`
- `0x180011a94`
- `0x18001b5a0`
- `0x18001b6b0`
- `0x18003a580`
- `0x18003aef8`
- `0x18003af10`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x1800412b4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c26`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180011cb1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180011cb1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180011b61`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180011b61`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180011ae8`

## string_xrefs

- `0x180011e06`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVaultFileStore::InitializeOrDeleteSchema(
        CVaultFileStore *this,
        char a2,
        struct IVaultFileSystem *a3)
{
  CVaultFileStore *v5; // rdi
  unsigned int v6; // ebx
  HANDLE FirstFile; // r13
  int v8; // r13d
  const wchar_t *v9; // r15
  __int64 v10; // rbx
  __int64 v11; // rsi
  unsigned int v12; // eax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // rdi
  wchar_t *v16; // r14
  unsigned int SchemaFile; // eax
  int v18; // edx
  int v19; // r8d
  const char *v20; // r9
  BOOL (__stdcall *v22)(HANDLE); // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h]
  struct IVaultFileSystem *v31; // [rsp+80h] [rbp-80h]
  HANDLE hFindFile; // [rsp+88h] [rbp-78h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

  v31 = a3;
  v5 = this;
  lpFileName = 0;
  v30 = 0;
  v28 = 0;
  v22 = FindClose;
  v23 = 0;
  v24 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v26 = 0;
  v27 = 0;
  v25 = 0;
  if ( a2 && !a3 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
    return 87;
  }
  v6 = PathCombine(*((wchar_t **)v5 + 39), (wchar_t *)L"*.vsch", (unsigned __int16 **)&lpFileName);
  if ( v6 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
    return v6;
  }
  FirstFile = FindFirstFileExW(lpFileName, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
  hFindFile = FirstFile;
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
  v23 = FirstFile;
  if ( FirstFile == (HANDLE)-1LL )
  {
    v23 = 0;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
    return 0;
  }
  v8 = 1;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      goto LABEL_22;
    v9 = (const wchar_t *)*((_QWORD *)v5 + 39);
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    v11 = -1;
    do
      ++v11;
    while ( FindFileData.cFileName[v11] );
    v12 = v11 + v10;
    if ( (int)v11 + (int)v10 < (unsigned int)v10 || v12 + 2 < v12 )
    {
      v6 = 534;
      goto LABEL_12;
    }
    v14 = (wchar_t *)LocalAlloc(0x40u, 2LL * (v12 + 2));
    v15 = v14;
    if ( !v14 )
      break;
    v26 = v14;
    wcscpy_s(v14, (unsigned int)(v10 + 1), v9);
    v16 = (wchar_t *)&v15[(unsigned int)v10];
    if ( (_DWORD)v10 && v9[(unsigned int)(v10 - 1)] != 92 )
    {
      wcscpy_s((wchar_t *)&v15[(unsigned int)v10], 2u, L"\\");
      ++v16;
    }
    wcscpy_s(v16, (unsigned int)(v11 + 1), FindFileData.cFileName);
    if ( a2 )
      SchemaFile = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, const unsigned __int16 *))(*(_QWORD *)v31 + 56LL))(
                     v31,
                     v15);
    else
      SchemaFile = CVaultFileStore::LoadSchemaFile(this, v15);
    v6 = SchemaFile;
    if ( SchemaFile )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v20 = "delete";
        if ( !a2 )
          v20 = "load";
        WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (_DWORD)v20, (__int64)v15, SchemaFile);
      }
      if ( a2 )
        goto LABEL_12;
      v6 = 0;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    if ( dword_18005F624 )
    {
      if ( ++v8 > (unsigned int)dword_18005F624 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids,
            (unsigned int)dword_18005F624);
        goto LABEL_12;
      }
    }
    v5 = this;
LABEL_22:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13ef719d6c39382471689e3834fa0ad3_Traceguids);
  v6 = 14;
LABEL_12:
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
  return v6;
}

```

## disassembly

```asm
0x180011a94  mov     [rsp-8+arg_8], rbx
0x180011a99  push    rbp
0x180011a9a  push    rsi
0x180011a9b  push    rdi
0x180011a9c  push    r12
0x180011a9e  push    r13
0x180011aa0  push    r14
0x180011aa2  push    r15
0x180011aa4  lea     rbp, [rsp-1F0h]
0x180011aac  sub     rsp, 2F0h
0x180011ab3  mov     rax, cs:__security_cookie
0x180011aba  xor     rax, rsp
0x180011abd  mov     [rbp+220h+var_40], rax
0x180011ac4  mov     rsi, r8
0x180011ac7  mov     [rbp+220h+var_2A0], r8
0x180011acb  mov     r12b, dl
0x180011ace  mov     rdi, rcx
0x180011ad1  mov     [rsp+320h+var_2F0], rcx
0x180011ad6  xor     r14d, r14d
0x180011ad9  mov     [rsp+320h+lpFileName], r14
0x180011ade  mov     [rsp+320h+var_2A8], r14d
0x180011ae3  mov     [rsp+320h+var_2B8], r14
0x180011ae8  mov     rax, cs:__imp_FindClose
0x180011aef  mov     [rsp+320h+var_2E8], rax
0x180011af4  mov     [rsp+320h+var_2E0], r14
0x180011af9  mov     [rsp+320h+var_2D8], r14d
0x180011afe  xor     edx, edx; Val
0x180011b00  mov     r8d, 250h; Size
0x180011b06  lea     rcx, [rbp+220h+FindFileData]; void *
0x180011b0a  call    memset_0
0x180011b0f  mov     [rsp+320h+var_2C8], r14
0x180011b14  mov     [rsp+320h+var_2C0], r14d
0x180011b19  mov     [rsp+320h+var_2D0], r14
0x180011b1e  test    r12b, r12b
0x180011b21  jnz     loc_180011D9D
0x180011b27  lea     r8, [rsp+320h+lpFileName]; unsigned __int16 **
0x180011b2c  lea     rdx, aVsch_0; "*.vsch"
0x180011b33  mov     rcx, [rdi+138h]; Source
0x180011b3a  call    ?PathCombine@@YAKPEBG0PEAPEAG@Z; PathCombine(ushort const *,ushort const *,ushort * *)
0x180011b3f  mov     ebx, eax
0x180011b41  test    eax, eax
0x180011b43  jnz     loc_180011DCF
0x180011b49  mov     [rsp+320h+dwAdditionalFlags], r14d; dwAdditionalFlags
0x180011b4e  mov     [rsp+320h+lpSearchFilter], r14; lpSearchFilter
0x180011b53  xor     r9d, r9d; fSearchOp
0x180011b56  lea     r8, [rbp+220h+FindFileData]; lpFindFileData
0x180011b5a  xor     edx, edx; fInfoLevelId
0x180011b5c  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x180011b61  call    cs:__imp_FindFirstFileExW
0x180011b67  mov     r13, rax
0x180011b6a  mov     [rbp+220h+hFindFile], rax
0x180011b6e  lea     rcx, [rsp+320h+var_2E8]
0x180011b73  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011b78  mov     [rsp+320h+var_2E0], r13
0x180011b7d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180011b81  jz      loc_180011D70
0x180011b87  lea     r13d, [rbx+1]
0x180011b8b  test    [rbp+220h+FindFileData], 10h
0x180011b8f  jnz     loc_180011CA9
0x180011b95  mov     r15, [rdi+138h]
0x180011b9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011ba0  inc     rbx
0x180011ba3  cmp     [r15+rbx*2], r14w
0x180011ba8  jnz     short loc_180011BA0
0x180011baa  lea     rax, [rbp+220h+Source]
0x180011bae  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011bb2  inc     rsi
0x180011bb5  cmp     [rax+rsi*2], r14w
0x180011bba  jnz     short loc_180011BB2
0x180011bbc  lea     eax, [rsi+rbx]
0x180011bbf  cmp     eax, ebx
0x180011bc1  jnb     short loc_180011C15
0x180011bc3  mov     ebx, 216h
0x180011bc8  lea     rcx, [rsp+320h+var_2D0]
0x180011bcd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011bd2  nop
0x180011bd3  lea     rcx, [rsp+320h+var_2E8]
0x180011bd8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011bdd  nop
0x180011bde  lea     rcx, [rsp+320h+var_2B8]
0x180011be3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011be8  nop
0x180011be9  mov     eax, ebx
0x180011beb  mov     rcx, [rbp+220h+var_40]
0x180011bf2  xor     rcx, rsp; StackCookie
0x180011bf5  call    __security_check_cookie
0x180011bfa  mov     rbx, [rsp+320h+arg_8]
0x180011c02  add     rsp, 2F0h
0x180011c09  pop     r15
0x180011c0b  pop     r14
0x180011c0d  pop     r13
0x180011c0f  pop     r12
0x180011c11  pop     rdi
0x180011c12  pop     rsi
0x180011c13  pop     rbp
0x180011c14  retn
0x180011c15  lea     ecx, [rax+2]
0x180011c18  cmp     ecx, eax
0x180011c1a  jb      short loc_180011BC3
0x180011c1c  mov     edx, ecx
0x180011c1e  add     rdx, rdx; uBytes
0x180011c21  mov     ecx, 40h ; '@'; uFlags
0x180011c26  call    cs:__imp_LocalAlloc
0x180011c2c  mov     rdi, rax
0x180011c2f  test    rax, rax
0x180011c32  jz      loc_180011E6B
0x180011c38  mov     [rsp+320h+var_2C8], rax
0x180011c3d  lea     edx, [rbx+1]; SizeInWords
0x180011c40  mov     r8, r15; Source
0x180011c43  mov     rcx, rax; Destination
0x180011c46  call    wcscpy_s
0x180011c4b  mov     ecx, ebx
0x180011c4d  lea     r14, [rdi+rcx*2]
0x180011c51  test    ebx, ebx
0x180011c53  jnz     loc_180011D3C
0x180011c59  lea     edx, [rsi+1]; SizeInWords
0x180011c5c  lea     r8, [rbp+220h+Source]; Source
0x180011c60  mov     rcx, r14; Destination
0x180011c63  call    wcscpy_s
0x180011c68  xor     r14d, r14d
0x180011c6b  mov     rdx, rdi; unsigned __int16 *
0x180011c6e  test    r12b, r12b
0x180011c71  jnz     short loc_180011CE5
0x180011c73  mov     rcx, [rsp+320h+var_2F0]; this
0x180011c78  call    ?LoadSchemaFile@CVaultFileStore@@AEAAKPEBG@Z; CVaultFileStore::LoadSchemaFile(ushort const *)
0x180011c7d  mov     ebx, eax
0x180011c7f  test    eax, eax
0x180011c81  jnz     short loc_180011CFA
0x180011c83  lea     rsi, WPP_GLOBAL_Control
0x180011c8a  lea     rcx, [rsp+320h+var_2D0]
0x180011c8f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011c94  mov     r9d, cs:dword_18005F624
0x180011c9b  test    r9d, r9d
0x180011c9e  jnz     loc_180011E2B
0x180011ca4  mov     rdi, [rsp+320h+var_2F0]
0x180011ca9  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x180011cad  mov     rcx, [rbp+220h+hFindFile]; hFindFile
0x180011cb1  call    cs:__imp_FindNextFileW
0x180011cb7  test    eax, eax
0x180011cb9  jnz     loc_180011B8B
0x180011cbf  lea     rcx, [rsp+320h+var_2D0]
0x180011cc4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011cc9  nop
0x180011cca  lea     rcx, [rsp+320h+var_2E8]
0x180011ccf  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011cd4  nop
0x180011cd5  lea     rcx, [rsp+320h+var_2B8]
0x180011cda  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011cdf  nop
0x180011ce0  jmp     loc_180011BE9
0x180011ce5  mov     rsi, [rbp+220h+var_2A0]
0x180011ce9  mov     rax, [rsi]
0x180011cec  mov     rcx, rsi
0x180011cef  mov     rax, [rax+38h]
0x180011cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf8  jmp     short loc_180011C7D
0x180011cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d01  lea     rsi, WPP_GLOBAL_Control
0x180011d08  cmp     rcx, rsi
0x180011d0b  jnz     loc_180011DF5
0x180011d11  test    r12b, r12b
0x180011d14  jz      short loc_180011D68
0x180011d16  lea     rcx, [rsp+320h+var_2D0]
0x180011d1b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d20  nop
0x180011d21  lea     rcx, [rsp+320h+var_2E8]
0x180011d26  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d2b  nop
0x180011d2c  lea     rcx, [rsp+320h+var_2B8]
0x180011d31  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d36  nop
0x180011d37  jmp     loc_180011BE9
0x180011d3c  lea     eax, [rbx-1]
0x180011d3f  cmp     word ptr [r15+rax*2], 5Ch ; '\'
0x180011d45  jz      loc_180011C59
0x180011d4b  lea     r8, Source; "\\"
0x180011d52  mov     edx, 2; SizeInWords
0x180011d57  mov     rcx, r14; Destination
0x180011d5a  call    wcscpy_s
0x180011d5f  add     r14, 2
0x180011d63  jmp     loc_180011C59
0x180011d68  mov     ebx, r14d
0x180011d6b  jmp     loc_180011C8A
0x180011d70  mov     [rsp+320h+var_2E0], r14
0x180011d75  lea     rcx, [rsp+320h+var_2D0]
0x180011d7a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d7f  nop
0x180011d80  lea     rcx, [rsp+320h+var_2E8]
0x180011d85  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d8a  nop
0x180011d8b  lea     rcx, [rsp+320h+var_2B8]
0x180011d90  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011d95  nop
0x180011d96  xor     eax, eax
0x180011d98  jmp     loc_180011BEB
0x180011d9d  test    rsi, rsi
0x180011da0  jnz     loc_180011B27
0x180011da6  lea     rcx, [rsp+320h+var_2D0]
0x180011dab  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011db0  nop
0x180011db1  lea     rcx, [rsp+320h+var_2E8]
0x180011db6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011dbb  nop
0x180011dbc  lea     rcx, [rsp+320h+var_2B8]
0x180011dc1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011dc6  nop
0x180011dc7  lea     eax, [rsi+57h]
0x180011dca  jmp     loc_180011BEB
0x180011dcf  lea     rcx, [rsp+320h+var_2D0]
0x180011dd4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011dd9  nop
0x180011dda  lea     rcx, [rsp+320h+var_2E8]
0x180011ddf  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011de4  nop
0x180011de5  lea     rcx, [rsp+320h+var_2B8]
0x180011dea  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011def  nop
0x180011df0  jmp     loc_180011BE9
0x180011df5  test    byte ptr [rcx+1Ch], 2
0x180011df9  jz      loc_180011D11
0x180011dff  lea     rax, aLoad; "load"
0x180011e06  lea     r9, aDelete; "delete"
0x180011e0d  test    r12b, r12b
0x180011e10  cmovz   r9, rax
0x180011e14  mov     [rsp+320h+dwAdditionalFlags], ebx
0x180011e18  mov     [rsp+320h+lpSearchFilter], rdi
0x180011e1d  mov     rcx, [rcx+10h]
0x180011e21  call    WPP_SF_sSD
0x180011e26  jmp     loc_180011D11
0x180011e2b  inc     r13d
0x180011e2e  cmp     r13d, r9d
0x180011e31  jbe     loc_180011CA4
0x180011e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e3e  cmp     rcx, rsi
0x180011e41  jz      loc_180011CBF
0x180011e47  test    byte ptr [rcx+1Ch], 4
0x180011e4b  jz      loc_180011CBF
0x180011e51  mov     edx, 0Dh
0x180011e56  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x180011e5d  mov     rcx, [rcx+10h]
0x180011e61  call    WPP_SF_d
0x180011e66  jmp     loc_180011CBF
0x180011e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e72  lea     rax, WPP_GLOBAL_Control
0x180011e79  cmp     rcx, rax
0x180011e7c  jz      short loc_180011E99
0x180011e7e  test    byte ptr [rcx+1Ch], 2
0x180011e82  jz      short loc_180011E99
0x180011e84  mov     edx, 0Ah
0x180011e89  lea     r8, WPP_13ef719d6c39382471689e3834fa0ad3_Traceguids
0x180011e90  mov     rcx, [rcx+10h]
0x180011e94  call    WPP_SF_
0x180011e99  mov     ebx, 0Eh
0x180011e9e  jmp     loc_180011BC8
```
