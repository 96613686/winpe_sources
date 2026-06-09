# CreateCoverpageTiffFile

- ea: `0x14002f530`
- end: `0x14002f95f`
- name: `CreateCoverpageTiffFile`
- size: `1071`
- prototype: `__int64 __fastcall(__int16, __int64, const wchar_t *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x14002f968`

## callees

- `0x140002c73`
- `0x140004b70`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14002f530`
- `0x140032778`
- `0x140032d14`
- `0x14006998c`
- `0x1400720c8`
- `0x140072a70`
- `0x14007de2c`
- `0x14007df80`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002f5f9`
- `KERNEL32!GetLastError` at `0x14002f660`
- `KERNEL32!GetLastError` at `0x14002f725`
- `KERNEL32!GetLastError` at `0x14002f827`
- `KERNEL32!GetLastError` at `0x14002f8eb`
- `KERNEL32!GetLastError` at `0x14002f5f9`
- `KERNEL32!GetLastError` at `0x14002f660`
- `KERNEL32!GetLastError` at `0x14002f725`
- `KERNEL32!GetLastError` at `0x14002f827`
- `KERNEL32!GetLastError` at `0x14002f8eb`
- `KERNEL32!SetLastError` at `0x14002f92f`
- `KERNEL32!SetLastError` at `0x14002f92f`
- `KERNEL32!DeleteFileW` at `0x14002f7f0`
- `KERNEL32!DeleteFileW` at `0x14002f8c4`
- `KERNEL32!DeleteFileW` at `0x14002f7f0`
- `KERNEL32!DeleteFileW` at `0x14002f8c4`

## pseudocode

```c
__int64 __fastcall CreateCoverpageTiffFile(__int16 a1, __int64 a2, const wchar_t *a3, unsigned __int16 *a4)
{
  int v8; // r8d
  unsigned __int16 *v9; // rcx
  WCHAR *FaxPrinterName; // r15
  DWORD LastError; // eax
  DWORD v12; // edi
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  __int16 v19; // r9
  DWORD v20; // eax
  char v21; // al
  int v22; // edx
  int v23; // eax
  unsigned __int16 v24; // r14
  __int64 i; // rbx
  __int64 v27[30]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v28[20]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v29; // [rsp+134h] [rbp+34h]
  WCHAR FileName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR v31[264]; // [rsp+3B0h] [rbp+2B0h] BYREF

  memset_0(v28, 0, 0x74u);
  memset_0(v27, 0, sizeof(v27));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v8 = *(_DWORD *)(a2 + 16);
  v9 = *(unsigned __int16 **)(a2 + 8);
  if ( !a3 )
    a3 = L"tif";
  FileName[0] = 0;
  if ( !(unsigned int)ValidateCoverpage(v9, 0, v8, v31) )
  {
    FaxPrinterName = 0;
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v14 = 35;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
LABEL_13:
    v15 = 0;
    goto LABEL_53;
  }
  FillCoverPageFields((const struct _FAX_COVERPAGE_INFOW2 *)a2, (struct _COVERPAGEFIELDS *)v27);
  FaxPrinterName = (WCHAR *)GetFaxPrinterName(v16);
  if ( !FaxPrinterName )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v14 = 36;
    goto LABEL_12;
  }
  v17 = PrintCoverPage(0, 0, v31, (__int64)v28);
  v12 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v17);
    }
    goto LABEL_13;
  }
  if ( !GenerateUniqueFileNameWithPrefix(v18, *((_QWORD *)g_pFaxConfig + 12), 0, a3, FileName) )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v14 = 38;
    goto LABEL_12;
  }
  v19 = 1;
  if ( v29 == 2 )
    v19 = 2;
  v20 = PrintCoverPageToFile((__int64)v31, FileName, FaxPrinterName, v19, a1);
  v12 = v20;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v20);
    }
    v15 = 0;
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = GetLastError();
      v22 = 40;
LABEL_41:
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)FileName,
        v21);
    }
  }
  else
  {
    v23 = StringCchCopyW(a4, 0x104u, FileName);
    v24 = v23;
    if ( v23 >= 0 )
    {
      v15 = 1;
      goto LABEL_53;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(a2 + 8),
        v23);
    }
    v12 = v24;
    v15 = 0;
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = GetLastError();
      v22 = 42;
      goto LABEL_41;
    }
  }
LABEL_53:
  pMemFree(FaxPrinterName);
  for ( i = 0; i != 29; ++i )
    pMemFree((LPVOID)v27[i + 1]);
  if ( !v15 )
  {
    if ( !v12 )
      v12 = 31;
    SetLastError(v12);
  }
  return v15;
}

```

## disassembly

```asm
0x14002f530  push    rbp
0x14002f532  push    rbx
0x14002f533  push    rsi
0x14002f534  push    rdi
0x14002f535  push    r12
0x14002f537  push    r14
0x14002f539  push    r15
0x14002f53b  lea     rbp, [rsp-4D0h]
0x14002f543  sub     rsp, 5D0h
0x14002f54a  mov     rax, cs:__security_cookie
0x14002f551  xor     rax, rsp
0x14002f554  mov     [rbp+500h+var_40], rax
0x14002f55b  mov     rsi, rdx
0x14002f55e  mov     rbx, r8
0x14002f561  xor     edx, edx; Val
0x14002f563  movzx   r12d, cx
0x14002f567  lea     rcx, [rbp+500h+var_4E0]; void *
0x14002f56b  mov     r14, r9
0x14002f56e  lea     r8d, [rdx+74h]; Size
0x14002f572  call    memset_0
0x14002f577  xor     edx, edx; Val
0x14002f579  lea     rcx, [rsp+600h+var_5D0]; void *
0x14002f57e  mov     r8d, 0F0h; Size
0x14002f584  call    memset_0
0x14002f589  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f590  lea     rax, WPP_GLOBAL_Control
0x14002f597  cmp     rcx, rax
0x14002f59a  jz      short loc_14002F5BD
0x14002f59c  test    byte ptr [rcx+1Ch], 4
0x14002f5a0  jz      short loc_14002F5BD
0x14002f5a2  cmp     byte ptr [rcx+19h], 5
0x14002f5a6  jb      short loc_14002F5BD
0x14002f5a8  mov     rcx, [rcx+10h]
0x14002f5ac  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f5b3  mov     edx, 22h ; '"'
0x14002f5b8  call    WPP_SF_
0x14002f5bd  mov     r8d, [rsi+10h]
0x14002f5c1  lea     rax, aTif; "tif"
0x14002f5c8  mov     rcx, [rsi+8]; unsigned __int16 *
0x14002f5cc  lea     r9, [rbp+500h+var_250]
0x14002f5d3  test    rbx, rbx
0x14002f5d6  mov     dword ptr [rsp+600h+var_5E0], 104h
0x14002f5de  cmovz   rbx, rax
0x14002f5e2  xor     eax, eax
0x14002f5e4  xor     edx, edx
0x14002f5e6  mov     [rbp+500h+FileName], ax
0x14002f5ed  call    ValidateCoverpage
0x14002f5f2  test    eax, eax
0x14002f5f4  jnz     short loc_14002F646
0x14002f5f6  xor     r15d, r15d
0x14002f5f9  call    cs:__imp_GetLastError
0x14002f600  nop     dword ptr [rax+rax+00h]
0x14002f605  mov     edi, eax
0x14002f607  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f60e  lea     r12, WPP_GLOBAL_Control
0x14002f615  cmp     rcx, r12
0x14002f618  jz      short loc_14002F63F
0x14002f61a  test    byte ptr [rcx+1Ch], 4
0x14002f61e  jz      short loc_14002F63F
0x14002f620  lea     ebx, [r15+2]
0x14002f624  cmp     [rcx+19h], bl
0x14002f627  jb      short loc_14002F63F
0x14002f629  lea     edx, [rbx+21h]
0x14002f62c  mov     rcx, [rcx+10h]
0x14002f630  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f637  mov     r9d, eax
0x14002f63a  call    WPP_SF_d
0x14002f63f  xor     esi, esi
0x14002f641  jmp     loc_14002F904
0x14002f646  lea     rdx, [rsp+600h+var_5D0]; struct _COVERPAGEFIELDS *
0x14002f64b  mov     rcx, rsi; struct _FAX_COVERPAGE_INFOW2 *
0x14002f64e  call    ?FillCoverPageFields@@YAHPEBU_FAX_COVERPAGE_INFOW2@@PEAU_COVERPAGEFIELDS@@@Z; FillCoverPageFields(_FAX_COVERPAGE_INFOW2 const *,_COVERPAGEFIELDS *)
0x14002f653  call    GetFaxPrinterName
0x14002f658  mov     r15, rax
0x14002f65b  test    rax, rax
0x14002f65e  jnz     short loc_14002F695
0x14002f660  call    cs:__imp_GetLastError
0x14002f667  nop     dword ptr [rax+rax+00h]
0x14002f66c  mov     edi, eax
0x14002f66e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f675  lea     r12, WPP_GLOBAL_Control
0x14002f67c  cmp     rcx, r12
0x14002f67f  jz      short loc_14002F63F
0x14002f681  test    byte ptr [rcx+1Ch], 4
0x14002f685  jz      short loc_14002F63F
0x14002f687  lea     ebx, [r15+2]
0x14002f68b  cmp     [rcx+19h], bl
0x14002f68e  jb      short loc_14002F63F
0x14002f690  lea     edx, [rbx+22h]
0x14002f693  jmp     short loc_14002F62C
0x14002f695  lea     r9, [rbp+500h+var_4E0]
0x14002f699  xor     edx, edx
0x14002f69b  lea     r8, [rbp+500h+var_250]
0x14002f6a2  xor     ecx, ecx; hdc
0x14002f6a4  call    PrintCoverPage
0x14002f6a9  mov     edi, eax
0x14002f6ab  test    eax, eax
0x14002f6ad  jz      short loc_14002F6FE
0x14002f6af  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6b6  lea     r12, WPP_GLOBAL_Control
0x14002f6bd  cmp     rcx, r12
0x14002f6c0  jz      loc_14002F63F
0x14002f6c6  test    byte ptr [rcx+1Ch], 4
0x14002f6ca  jz      loc_14002F63F
0x14002f6d0  mov     ebx, 2
0x14002f6d5  cmp     [rcx+19h], bl
0x14002f6d8  jb      loc_14002F63F
0x14002f6de  mov     r9, [rsi+8]
0x14002f6e2  lea     edx, [rbx+23h]
0x14002f6e5  mov     rcx, [rcx+10h]
0x14002f6e9  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f6f0  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002f6f4  call    WPP_SF_Sd
0x14002f6f9  jmp     loc_14002F63F
0x14002f6fe  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002f705  lea     rax, [rbp+500h+FileName]
0x14002f70c  mov     r9, rbx
0x14002f70f  mov     qword ptr [rsp+600h+var_5E0], rax
0x14002f714  xor     r8d, r8d
0x14002f717  mov     rdx, [rdx+60h]
0x14002f71b  call    GenerateUniqueFileNameWithPrefix
0x14002f720  test    rax, rax
0x14002f723  jnz     short loc_14002F76A
0x14002f725  call    cs:__imp_GetLastError
0x14002f72c  nop     dword ptr [rax+rax+00h]
0x14002f731  mov     edi, eax
0x14002f733  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f73a  lea     r12, WPP_GLOBAL_Control
0x14002f741  cmp     rcx, r12
0x14002f744  jz      loc_14002F63F
0x14002f74a  test    byte ptr [rcx+1Ch], 4
0x14002f74e  jz      loc_14002F63F
0x14002f754  mov     ebx, 2
0x14002f759  cmp     [rcx+19h], bl
0x14002f75c  jb      loc_14002F63F
0x14002f762  lea     edx, [rbx+24h]
0x14002f765  jmp     loc_14002F62C
0x14002f76a  mov     ebx, 2
0x14002f76f  lea     r9d, [rbx-1]
0x14002f773  cmp     [rbp+500h+var_4CC], bx
0x14002f777  jnz     short loc_14002F77C
0x14002f779  mov     r9d, ebx
0x14002f77c  lea     rax, [rsp+600h+var_5D0]
0x14002f781  mov     r8, r15; pwszDevice
0x14002f784  mov     [rsp+600h+var_5D8], rax; __int64
0x14002f789  lea     rdx, [rbp+500h+FileName]; __int64
0x14002f790  lea     rcx, [rbp+500h+var_250]; __int64
0x14002f797  mov     [rsp+600h+var_5E0], r12w; __int16
0x14002f79d  call    PrintCoverPageToFile
0x14002f7a2  mov     edi, eax
0x14002f7a4  test    eax, eax
0x14002f7a6  jz      loc_14002F85D
0x14002f7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f7b3  lea     r12, WPP_GLOBAL_Control
0x14002f7ba  cmp     rcx, r12
0x14002f7bd  jz      short loc_14002F7E7
0x14002f7bf  test    byte ptr [rcx+1Ch], 4
0x14002f7c3  jz      short loc_14002F7E7
0x14002f7c5  cmp     [rcx+19h], bl
0x14002f7c8  jb      short loc_14002F7E7
0x14002f7ca  mov     r9, [rsi+8]
0x14002f7ce  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f7d5  mov     rcx, [rcx+10h]
0x14002f7d9  mov     edx, 27h ; '''
0x14002f7de  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002f7e2  call    WPP_SF_Sd
0x14002f7e7  lea     rcx, [rbp+500h+FileName]; lpFileName
0x14002f7ee  xor     esi, esi
0x14002f7f0  call    cs:__imp_DeleteFileW
0x14002f7f7  nop     dword ptr [rax+rax+00h]
0x14002f7fc  test    eax, eax
0x14002f7fe  jnz     loc_14002F904
0x14002f804  mov     rax, cs:WPP_GLOBAL_Control
0x14002f80b  cmp     rax, r12
0x14002f80e  jz      loc_14002F904
0x14002f814  test    byte ptr [rax+1Ch], 4
0x14002f818  jz      loc_14002F904
0x14002f81e  cmp     [rax+19h], bl
0x14002f821  jb      loc_14002F904
0x14002f827  call    cs:__imp_GetLastError
0x14002f82e  nop     dword ptr [rax+rax+00h]
0x14002f833  lea     edx, [rsi+28h]
0x14002f836  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f83d  lea     r9, [rbp+500h+FileName]
0x14002f844  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f84b  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002f84f  mov     rcx, [rcx+10h]
0x14002f853  call    WPP_SF_Sd
0x14002f858  jmp     loc_14002F904
0x14002f85d  lea     r8, [rbp+500h+FileName]; unsigned __int16 *
0x14002f864  mov     edx, 104h; unsigned __int64
0x14002f869  mov     rcx, r14; unsigned __int16 *
0x14002f86c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002f871  mov     r14d, eax
0x14002f874  test    eax, eax
0x14002f876  jns     loc_14002F8FF
0x14002f87c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f883  lea     r12, WPP_GLOBAL_Control
0x14002f88a  cmp     rcx, r12
0x14002f88d  jz      short loc_14002F8B7
0x14002f88f  test    byte ptr [rcx+1Ch], 4
0x14002f893  jz      short loc_14002F8B7
0x14002f895  cmp     [rcx+19h], bl
0x14002f898  jb      short loc_14002F8B7
0x14002f89a  mov     r9, [rsi+8]
0x14002f89e  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f8a5  mov     rcx, [rcx+10h]
0x14002f8a9  mov     edx, 29h ; ')'
0x14002f8ae  mov     dword ptr [rsp+600h+var_5E0], eax
0x14002f8b2  call    WPP_SF_Sd
0x14002f8b7  lea     rcx, [rbp+500h+FileName]; lpFileName
0x14002f8be  movzx   edi, r14w
0x14002f8c2  xor     esi, esi
0x14002f8c4  call    cs:__imp_DeleteFileW
0x14002f8cb  nop     dword ptr [rax+rax+00h]
0x14002f8d0  test    eax, eax
0x14002f8d2  jnz     short loc_14002F904
0x14002f8d4  mov     rax, cs:WPP_GLOBAL_Control
0x14002f8db  cmp     rax, r12
0x14002f8de  jz      short loc_14002F904
0x14002f8e0  test    byte ptr [rax+1Ch], 4
0x14002f8e4  jz      short loc_14002F904
0x14002f8e6  cmp     [rax+19h], bl
0x14002f8e9  jb      short loc_14002F904
0x14002f8eb  call    cs:__imp_GetLastError
0x14002f8f2  nop     dword ptr [rax+rax+00h]
0x14002f8f7  lea     edx, [rsi+2Ah]
0x14002f8fa  jmp     loc_14002F836
0x14002f8ff  mov     esi, 1
0x14002f904  mov     rcx, r15; lpMem
0x14002f907  call    pMemFree
0x14002f90c  xor     ebx, ebx
0x14002f90e  mov     rcx, [rsp+rbx*8+600h+lpMem]; lpMem
0x14002f913  call    pMemFree
0x14002f918  inc     rbx
0x14002f91b  cmp     rbx, 1Dh
0x14002f91f  jnz     short loc_14002F90E
0x14002f921  test    esi, esi
0x14002f923  jnz     short loc_14002F93B
0x14002f925  test    edi, edi
0x14002f927  lea     eax, [rbx+2]
0x14002f92a  cmovz   edi, eax
0x14002f92d  mov     ecx, edi; dwErrCode
0x14002f92f  call    cs:__imp_SetLastError
0x14002f936  nop     dword ptr [rax+rax+00h]
0x14002f93b  mov     eax, esi
0x14002f93d  mov     rcx, [rbp+500h+var_40]
0x14002f944  xor     rcx, rsp; StackCookie
0x14002f947  call    __security_check_cookie
0x14002f94c  add     rsp, 5D0h
0x14002f953  pop     r15
0x14002f955  pop     r14
0x14002f957  pop     r12
0x14002f959  pop     rdi
0x14002f95a  pop     rsi
0x14002f95b  pop     rbx
0x14002f95c  pop     rbp
0x14002f95d  retn
```
