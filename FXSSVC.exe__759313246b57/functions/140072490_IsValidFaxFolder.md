# IsValidFaxFolder

- ea: `0x140072490`
- end: `0x140072750`
- name: `IsValidFaxFolder`
- size: `704`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000c004`
- `0x14001ee40`
- `0x140028d5c`
- `0x1400411a0`
- `0x1400530d0`
- `0x140053d40`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x14006998c`
- `0x14006a574`
- `0x14006ff04`
- `0x140072490`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x1400725a9`
- `KERNEL32!GetTempFileNameW` at `0x1400725a9`
- `KERNEL32!GetLastError` at `0x14007252b`
- `KERNEL32!GetLastError` at `0x1400725b9`
- `KERNEL32!GetLastError` at `0x140072623`
- `KERNEL32!GetLastError` at `0x14007267d`
- `KERNEL32!GetLastError` at `0x1400726b3`
- `KERNEL32!GetLastError` at `0x1400726e3`
- `KERNEL32!GetLastError` at `0x14007252b`
- `KERNEL32!GetLastError` at `0x1400725b9`
- `KERNEL32!GetLastError` at `0x140072623`
- `KERNEL32!GetLastError` at `0x14007267d`
- `KERNEL32!GetLastError` at `0x1400726b3`
- `KERNEL32!GetLastError` at `0x1400726e3`
- `KERNEL32!FindFirstFileW` at `0x140072611`
- `KERNEL32!FindFirstFileW` at `0x140072611`
- `KERNEL32!FindClose` at `0x140072655`
- `KERNEL32!FindClose` at `0x140072655`
- `KERNEL32!GetFileAttributesW` at `0x140072577`
- `KERNEL32!GetFileAttributesW` at `0x140072577`

## pseudocode

```c
__int64 __fastcall IsValidFaxFolder(unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  WCHAR *v3; // rdi
  DWORD v4; // eax
  DWORD v5; // ebx
  DWORD FileAttributesW; // eax
  DWORD v7; // eax
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  HANDLE FirstFileW; // rax
  DWORD v11; // eax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-488h] BYREF
  WCHAR TempFileName[264]; // [rsp+270h] [rbp-238h] BYREF

  memset_0(TempFileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  v2 = (const WCHAR *)ExpandEnvironmentString(a1);
  v3 = (WCHAR *)v2;
  if ( v2 )
  {
    FileAttributesW = GetFileAttributesW(v2);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      }
      goto LABEL_38;
    }
    if ( !GetTempFileNameW(v3, L"TST", 0, TempFileName) )
    {
      v7 = GetLastError();
      v5 = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_38;
      }
      v9 = 89;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v7);
LABEL_38:
      pMemFree(v3);
      return v5;
    }
    FirstFileW = FindFirstFileW(TempFileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      v11 = GetLastError();
      v5 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v13 = 90;
    }
    else
    {
      v5 = 0;
      if ( FindClose(FirstFileW)
        || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v11 = GetLastError();
      v12 = WPP_GLOBAL_Control;
      v13 = 91;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v11);
LABEL_29:
    if ( (unsigned int)SafeDeleteFileByHandle(TempFileName) )
      goto LABEL_38;
    v7 = GetLastError();
    v5 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v9 = 92;
    goto LABEL_17;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x140072490  mov     [rsp+arg_8], rbx
0x140072495  mov     [rsp+arg_10], rbp
0x14007249a  push    rsi
0x14007249b  push    rdi
0x14007249c  push    r14
0x14007249e  sub     rsp, 490h
0x1400724a5  mov     rax, cs:__security_cookie
0x1400724ac  xor     rax, rsp
0x1400724af  mov     [rsp+4A8h+var_28], rax
0x1400724b7  mov     rbx, rcx
0x1400724ba  xor     edx, edx; Val
0x1400724bc  lea     rcx, [rsp+4A8h+TempFileName]; void *
0x1400724c4  mov     r8d, 208h; Size
0x1400724ca  call    memset_0
0x1400724cf  xor     edx, edx; Val
0x1400724d1  lea     rcx, [rsp+4A8h+FindFileData]; void *
0x1400724d6  mov     r8d, 250h; Size
0x1400724dc  call    memset_0
0x1400724e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724e8  lea     rbp, WPP_GLOBAL_Control
0x1400724ef  lea     r14, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1400724f6  mov     sil, 2
0x1400724f9  cmp     rcx, rbp
0x1400724fc  jz      short loc_14007251B
0x1400724fe  test    [rcx+1Ch], sil
0x140072502  jz      short loc_14007251B
0x140072504  cmp     byte ptr [rcx+19h], 5
0x140072508  jb      short loc_14007251B
0x14007250a  mov     rcx, [rcx+10h]
0x14007250e  mov     edx, 56h ; 'V'
0x140072513  mov     r8, r14
0x140072516  call    WPP_SF_
0x14007251b  mov     rcx, rbx; unsigned __int16 *
0x14007251e  call    ExpandEnvironmentString
0x140072523  mov     rdi, rax
0x140072526  test    rax, rax
0x140072529  jnz     short loc_140072574
0x14007252b  call    cs:__imp_GetLastError
0x140072532  nop     dword ptr [rax+rax+00h]
0x140072537  mov     ebx, eax
0x140072539  mov     rcx, cs:WPP_GLOBAL_Control
0x140072540  cmp     rcx, rbp
0x140072543  jz      loc_140072725
0x140072549  test    [rcx+1Ch], sil
0x14007254d  jz      loc_140072725
0x140072553  cmp     [rcx+19h], sil
0x140072557  jb      loc_140072725
0x14007255d  mov     rcx, [rcx+10h]
0x140072561  lea     edx, [rdi+57h]
0x140072564  mov     r9d, eax
0x140072567  mov     r8, r14
0x14007256a  call    WPP_SF_d
0x14007256f  jmp     loc_140072725
0x140072574  mov     rcx, rdi; lpFileName
0x140072577  call    cs:__imp_GetFileAttributesW
0x14007257e  nop     dword ptr [rax+rax+00h]
0x140072583  cmp     eax, 0FFFFFFFFh
0x140072586  jz      loc_1400726E3
0x14007258c  test    al, 10h
0x14007258e  jz      loc_1400726E3
0x140072594  lea     r9, [rsp+4A8h+TempFileName]; lpTempFileName
0x14007259c  xor     r8d, r8d; uUnique
0x14007259f  lea     rdx, PrefixString; "TST"
0x1400725a6  mov     rcx, rdi; lpPathName
0x1400725a9  call    cs:__imp_GetTempFileNameW
0x1400725b0  nop     dword ptr [rax+rax+00h]
0x1400725b5  test    eax, eax
0x1400725b7  jnz     short loc_140072604
0x1400725b9  call    cs:__imp_GetLastError
0x1400725c0  nop     dword ptr [rax+rax+00h]
0x1400725c5  mov     ebx, eax
0x1400725c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400725ce  cmp     rcx, rbp
0x1400725d1  jz      loc_14007271D
0x1400725d7  test    [rcx+1Ch], sil
0x1400725db  jz      loc_14007271D
0x1400725e1  cmp     [rcx+19h], sil
0x1400725e5  jb      loc_14007271D
0x1400725eb  mov     edx, 59h ; 'Y'
0x1400725f0  mov     rcx, [rcx+10h]
0x1400725f4  mov     r9d, eax
0x1400725f7  mov     r8, r14
0x1400725fa  call    WPP_SF_d
0x1400725ff  jmp     loc_14007271D
0x140072604  lea     rdx, [rsp+4A8h+FindFileData]; lpFindFileData
0x140072609  lea     rcx, [rsp+4A8h+TempFileName]; lpFileName
0x140072611  call    cs:__imp_FindFirstFileW
0x140072618  nop     dword ptr [rax+rax+00h]
0x14007261d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140072621  jnz     short loc_140072650
0x140072623  call    cs:__imp_GetLastError
0x14007262a  nop     dword ptr [rax+rax+00h]
0x14007262f  mov     ebx, eax
0x140072631  mov     rcx, cs:WPP_GLOBAL_Control
0x140072638  cmp     rcx, rbp
0x14007263b  jz      short loc_1400726A2
0x14007263d  test    [rcx+1Ch], sil
0x140072641  jz      short loc_1400726A2
0x140072643  cmp     [rcx+19h], sil
0x140072647  jb      short loc_1400726A2
0x140072649  mov     edx, 5Ah ; 'Z'
0x14007264e  jmp     short loc_140072693
0x140072650  mov     rcx, rax; hFindFile
0x140072653  xor     ebx, ebx
0x140072655  call    cs:__imp_FindClose
0x14007265c  nop     dword ptr [rax+rax+00h]
0x140072661  test    eax, eax
0x140072663  jnz     short loc_1400726A2
0x140072665  mov     rax, cs:WPP_GLOBAL_Control
0x14007266c  cmp     rax, rbp
0x14007266f  jz      short loc_1400726A2
0x140072671  test    [rax+1Ch], sil
0x140072675  jz      short loc_1400726A2
0x140072677  cmp     [rax+19h], sil
0x14007267b  jb      short loc_1400726A2
0x14007267d  call    cs:__imp_GetLastError
0x140072684  nop     dword ptr [rax+rax+00h]
0x140072689  mov     rcx, cs:WPP_GLOBAL_Control
0x140072690  lea     edx, [rbx+5Bh]
0x140072693  mov     rcx, [rcx+10h]
0x140072697  mov     r9d, eax
0x14007269a  mov     r8, r14
0x14007269d  call    WPP_SF_d
0x1400726a2  lea     rcx, [rsp+4A8h+TempFileName]; unsigned __int16 *
0x1400726aa  call    ?SafeDeleteFileByHandle@@YAHPEAG@Z; SafeDeleteFileByHandle(ushort *)
0x1400726af  test    eax, eax
0x1400726b1  jnz     short loc_14007271D
0x1400726b3  call    cs:__imp_GetLastError
0x1400726ba  nop     dword ptr [rax+rax+00h]
0x1400726bf  mov     ebx, eax
0x1400726c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726c8  cmp     rcx, rbp
0x1400726cb  jz      short loc_14007271D
0x1400726cd  test    [rcx+1Ch], sil
0x1400726d1  jz      short loc_14007271D
0x1400726d3  cmp     [rcx+19h], sil
0x1400726d7  jb      short loc_14007271D
0x1400726d9  mov     edx, 5Ch ; '\'
0x1400726de  jmp     loc_1400725F0
0x1400726e3  call    cs:__imp_GetLastError
0x1400726ea  nop     dword ptr [rax+rax+00h]
0x1400726ef  mov     ebx, eax
0x1400726f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726f8  cmp     rcx, rbp
0x1400726fb  jz      short loc_14007271D
0x1400726fd  test    [rcx+1Ch], sil
0x140072701  jz      short loc_14007271D
0x140072703  cmp     [rcx+19h], sil
0x140072707  jb      short loc_14007271D
0x140072709  mov     rcx, [rcx+10h]
0x14007270d  mov     edx, 58h ; 'X'
0x140072712  mov     r9d, eax
0x140072715  mov     r8, r14
0x140072718  call    WPP_SF_d
0x14007271d  mov     rcx, rdi; lpMem
0x140072720  call    pMemFree
0x140072725  mov     eax, ebx
0x140072727  mov     rcx, [rsp+4A8h+var_28]
0x14007272f  xor     rcx, rsp; StackCookie
0x140072732  call    __security_check_cookie
0x140072737  lea     r11, [rsp+4A8h+var_18]
0x14007273f  mov     rbx, [r11+28h]
0x140072743  mov     rbp, [r11+30h]
0x140072747  mov     rsp, r11
0x14007274a  pop     r14
0x14007274c  pop     rdi
0x14007274d  pop     rsi
0x14007274e  retn
```
