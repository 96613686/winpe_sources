# RegRestoreHelper(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180013280`
- end: `0x1800135d0`
- name: `?RegRestoreHelper@@YAHPEAUHKEY__@@0PEBG11@Z`
- size: `848`
- prototype: `__int64 __fastcall(HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *lpValueName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180013acc`

## callees

- `0x1800022bc`
- `0x180008a6c`
- `0x180012ea0`
- `0x180013280`
- `0x180013fa4`
- `0x180014148`
- `0x1800141f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001349d`
- `KERNEL32!LocalFree` at `0x1800135a4`
- `KERNEL32!LocalFree` at `0x1800135ad`
- `KERNEL32!LocalFree` at `0x18001349d`
- `KERNEL32!LocalFree` at `0x1800135a4`
- `KERNEL32!LocalFree` at `0x1800135ad`
- `KERNEL32!LocalAlloc` at `0x180013548`
- `KERNEL32!LocalAlloc` at `0x180013548`
- `ADVAPI32!RegCreateKeyExW` at `0x18001340f`
- `ADVAPI32!RegCreateKeyExW` at `0x18001340f`
- `ADVAPI32!RegCloseKey` at `0x18001348f`
- `ADVAPI32!RegCloseKey` at `0x1800134c0`
- `ADVAPI32!RegCloseKey` at `0x18001348f`
- `ADVAPI32!RegCloseKey` at `0x1800134c0`
- `ADVAPI32!RegSetValueExW` at `0x180013457`
- `ADVAPI32!RegSetValueExW` at `0x180013457`
- `ADVAPI32!RegDeleteValueW` at `0x1800134b6`
- `ADVAPI32!RegDeleteValueW` at `0x1800134b6`
- `ADVAPI32!RegDeleteKeyW` at `0x18001357d`
- `ADVAPI32!RegDeleteKeyW` at `0x18001357d`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013586`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180013586`

## string_xrefs

- `0x180013342`: `RemoveRegistryBackupData: `
- `0x1800134df`: `\nBackup Value deleted`

## pseudocode

```c
__int64 __fastcall RegRestoreHelper(
        HKEY a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpValueName)
{
  HKEY v5; // r13
  const WCHAR *v6; // r12
  const WCHAR *v8; // rsi
  int v9; // eax
  HLOCAL v10; // r15
  unsigned __int16 v11; // bx
  __int64 NextToken; // r14
  __int64 v13; // rax
  const unsigned __int16 *v14; // rbx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r14
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rbx
  HKEY v24; // rsi
  __int64 v25; // rax
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h]
  HKEY phkResult; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF
  int v30; // [rsp+ACh] [rbp+4Ch]
  char *v31; // [rsp+B0h] [rbp+50h] BYREF

  HIDWORD(v31) = HIDWORD(a3);
  v30 = HIDWORD(a2);
  v5 = g_hkBckupKey;
  v6 = lpValueName;
  v8 = g_pszSubKey;
  hKey = g_hkRootKey;
  phkResult = 0;
  hMem = 0;
  LODWORD(v31) = 0;
  dwDisposition = 0;
  v9 = ValueDataHelper(g_hkBckupKey, lpValueName, (unsigned __int8 **)&hMem, (unsigned int *)&v31, 2u);
  v10 = hMem;
  if ( v9 )
  {
    v11 = *(_WORD *)hMem;
    v31 = (char *)hMem + 2;
    NextToken = GetNextToken(&v31, v11);
    v13 = GetNextToken(&v31, v11);
    v31 += 2;
    v14 = (const unsigned __int16 *)v13;
    if ( g_fRemovBkData )
      WriteToLog(L"RemoveRegistryBackupData: ");
    WriteToLog(L"BckupSubKey = ");
    if ( NextToken )
    {
      WriteToLog(L"%1", NextToken);
      if ( !a4 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v8[v15] );
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(NextToken + 2 * v16) );
        if ( v16 > v15 )
          v8 = (const WCHAR *)NextToken;
      }
    }
    if ( g_fRemovBkData )
    {
      if ( v14 )
        WriteToLog(L", BckupValueName = %1", a4);
      ValueDataHelper(v5, v6, 0, 0, 4u);
      WriteToLog(L" <Done>\r\n");
    }
    else
    {
      if ( !RegCreateKeyExW(hKey, v8, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition) )
      {
        if ( v14 )
        {
          WriteToLog(L", BckupValueName = %1", a4);
          if ( RegSetValueExW(phkResult, v14, 0, *(_DWORD *)v31, (const BYTE *)v31 + 4, *(_DWORD *)(v31 + 2)) )
          {
            MsgBox2Param(hWnd, 0x481u, v14, 0, 0x10u, 0);
            goto LABEL_21;
          }
        }
        else if ( a4 )
        {
          RegDeleteValueW(phkResult, a4);
        }
        RegCloseKey(phkResult);
        ValueDataHelper(v5, v6, 0, 0, 4u);
        WriteToLog(L"\r\nBackup Value deleted");
      }
      WriteToLog(L"\r\n");
      if ( !v14 )
      {
        LODWORD(v18) = 0;
        if ( !NextToken )
          goto LABEL_36;
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(NextToken + 2 * v18) );
        v19 = -1;
        do
          ++v19;
        while ( v8[v19] );
        if ( (unsigned int)v19 > (unsigned int)v18 )
        {
LABEL_36:
          v20 = -1;
          do
            ++v20;
          while ( v8[v20] );
          v21 = (unsigned int)(v20 + 1);
          v22 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v21);
          v23 = v22;
          if ( v22 )
          {
            StringCchCopyW(v22, (unsigned int)v21, v8);
            v24 = hKey;
            do
            {
              if ( !RegKeyEmpty(v24, v23) )
                break;
              RegDeleteKeyW(v24, v23);
              if ( !PathRemoveFileSpecW(v23) )
                break;
              v25 = -1;
              do
                ++v25;
              while ( v23[v25] );
            }
            while ( (unsigned int)v25 > (unsigned int)v18 );
            LocalFree(v23);
          }
        }
      }
    }
    LocalFree(v10);
    return 1;
  }
  MsgBox2Param(hWnd, 0x482u, v6, 0, 0x10u, 0);
LABEL_21:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180013280  mov     rax, rsp
0x180013283  mov     [rax+20h], rbx
0x180013287  mov     [rax+18h], r8
0x18001328b  mov     [rax+10h], rdx
0x18001328f  mov     [rax+8], rcx
0x180013293  push    rbp
0x180013294  push    rsi
0x180013295  push    rdi
0x180013296  push    r12
0x180013298  push    r13
0x18001329a  push    r14
0x18001329c  push    r15
0x18001329e  mov     rbp, rsp
0x1800132a1  sub     rsp, 60h
0x1800132a5  mov     r13, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; HKEY__ * g_hkBckupKey
0x1800132ac  lea     r8, [rbp+hMem]; unsigned __int8 **
0x1800132b0  mov     rax, cs:?g_hkRootKey@@3PEAUHKEY__@@EA; HKEY__ * g_hkRootKey
0x1800132b7  xor     ebx, ebx
0x1800132b9  mov     r12, [rbp+lpValueName]
0x1800132bd  mov     rdi, r9
0x1800132c0  mov     rsi, cs:?g_pszSubKey@@3PEAGEA; ushort * g_pszSubKey
0x1800132c7  lea     r9, [rbp+arg_10]; unsigned int *
0x1800132cb  mov     rdx, r12; lpValueName
0x1800132ce  mov     [rbp+hKey], rax
0x1800132d2  mov     rcx, r13; hKey
0x1800132d5  mov     [rbp+arg_0], rbx
0x1800132d9  mov     [rbp+hMem], rbx
0x1800132dd  mov     dword ptr [rbp+arg_10], ebx
0x1800132e0  mov     [rbp+dwDisposition], ebx
0x1800132e3  mov     [rsp+60h+dwOptions], 2; unsigned int
0x1800132eb  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x1800132f0  mov     r15, [rbp+hMem]
0x1800132f4  test    eax, eax
0x1800132f6  jnz     short loc_180013309
0x1800132f8  mov     [rsp+60h+samDesired], ebx
0x1800132fc  mov     r8, r12
0x1800132ff  mov     edx, 482h
0x180013304  jmp     loc_18001346F
0x180013309  movzx   ebx, word ptr [r15]
0x18001330d  lea     rax, [r15+2]
0x180013311  movzx   edx, bx
0x180013314  mov     [rbp+arg_10], rax
0x180013318  lea     rcx, [rbp+arg_10]
0x18001331c  call    GetNextToken
0x180013321  movzx   edx, bx
0x180013324  lea     rcx, [rbp+arg_10]
0x180013328  mov     r14, rax
0x18001332b  call    GetNextToken
0x180013330  add     [rbp+arg_10], 2
0x180013335  xor     ecx, ecx
0x180013337  cmp     cs:?g_fRemovBkData@@3HA, ecx; int g_fRemovBkData
0x18001333d  mov     rbx, rax
0x180013340  jz      short loc_18001334E
0x180013342  lea     rcx, aRemoveregistry; "RemoveRegistryBackupData: "
0x180013349  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x18001334e  lea     rcx, aBckupsubkey; "BckupSubKey = "
0x180013355  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x18001335a  xor     edx, edx
0x18001335c  test    r14, r14
0x18001335f  jz      short loc_180013399
0x180013361  mov     rdx, r14
0x180013364  lea     rcx, a1_0; "%1"
0x18001336b  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x180013370  xor     edx, edx
0x180013372  test    rdi, rdi
0x180013375  jnz     short loc_180013399
0x180013377  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001337b  inc     rcx
0x18001337e  cmp     [rsi+rcx*2], dx
0x180013382  jnz     short loc_18001337B
0x180013384  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013388  inc     rax
0x18001338b  cmp     [r14+rax*2], dx
0x180013390  jnz     short loc_180013388
0x180013392  cmp     rax, rcx
0x180013395  cmova   rsi, r14
0x180013399  cmp     cs:?g_fRemovBkData@@3HA, edx; int g_fRemovBkData
0x18001339f  jz      short loc_1800133DF
0x1800133a1  test    rbx, rbx
0x1800133a4  jz      short loc_1800133B5
0x1800133a6  mov     rdx, rdi
0x1800133a9  lea     rcx, aBckupvaluename; ", BckupValueName = %1"
0x1800133b0  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x1800133b5  xor     r9d, r9d; unsigned int *
0x1800133b8  mov     [rsp+60h+dwOptions], 4; unsigned int
0x1800133c0  xor     r8d, r8d; unsigned __int8 **
0x1800133c3  mov     rdx, r12; lpValueName
0x1800133c6  mov     rcx, r13; hKey
0x1800133c9  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x1800133ce  lea     rcx, aDone; " <Done>\r\n"
0x1800133d5  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x1800133da  jmp     loc_1800135AA
0x1800133df  mov     rcx, [rbp+hKey]; hKey
0x1800133e3  lea     rax, [rbp+dwDisposition]
0x1800133e7  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800133ec  xor     r9d, r9d; lpClass
0x1800133ef  lea     rax, [rbp+arg_0]
0x1800133f3  xor     r8d, r8d; Reserved
0x1800133f6  mov     [rsp+60h+phkResult], rax; phkResult
0x1800133fb  mov     [rsp+60h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x180013400  mov     [rsp+60h+samDesired], 20006h; samDesired
0x180013408  mov     [rsp+60h+dwOptions], edx; dwOptions
0x18001340c  mov     rdx, rsi; lpSubKey
0x18001340f  call    cs:__imp_RegCreateKeyExW
0x180013415  test    eax, eax
0x180013417  jnz     loc_1800134EB
0x18001341d  test    rbx, rbx
0x180013420  jz      loc_1800134AA
0x180013426  mov     rdx, rdi
0x180013429  lea     rcx, aBckupvaluename; ", BckupValueName = %1"
0x180013430  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x180013435  mov     r9, [rbp+arg_10]
0x180013439  xor     r8d, r8d; Reserved
0x18001343c  mov     rdx, rbx; lpValueName
0x18001343f  mov     eax, [r9+2]
0x180013443  lea     rcx, [r9+4]
0x180013447  mov     r9d, [r9]; dwType
0x18001344a  mov     [rsp+60h+samDesired], eax; cbData
0x18001344e  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180013453  mov     rcx, [rbp+arg_0]; hKey
0x180013457  call    cs:__imp_RegSetValueExW
0x18001345d  xor     ecx, ecx
0x18001345f  test    eax, eax
0x180013461  jz      short loc_1800134BC
0x180013463  mov     [rsp+60h+samDesired], ecx; unsigned int
0x180013467  mov     r8, rbx; unsigned __int16 *
0x18001346a  mov     edx, 481h; uID
0x18001346f  mov     rcx, cs:hWnd; hWnd
0x180013476  xor     r9d, r9d; unsigned __int16 *
0x180013479  mov     [rsp+60h+dwOptions], 10h; unsigned int
0x180013481  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180013486  mov     rcx, [rbp+arg_0]; hKey
0x18001348a  test    rcx, rcx
0x18001348d  jz      short loc_180013495
0x18001348f  call    cs:__imp_RegCloseKey
0x180013495  test    r15, r15
0x180013498  jz      short loc_1800134A3
0x18001349a  mov     rcx, r15; hMem
0x18001349d  call    cs:__imp_LocalFree
0x1800134a3  xor     eax, eax
0x1800134a5  jmp     loc_1800135B8
0x1800134aa  test    rdi, rdi
0x1800134ad  jz      short loc_1800134BC
0x1800134af  mov     rcx, [rbp+arg_0]; hKey
0x1800134b3  mov     rdx, rdi; lpValueName
0x1800134b6  call    cs:__imp_RegDeleteValueW
0x1800134bc  mov     rcx, [rbp+arg_0]; hKey
0x1800134c0  call    cs:__imp_RegCloseKey
0x1800134c6  xor     r9d, r9d; unsigned int *
0x1800134c9  mov     [rsp+60h+dwOptions], 4; unsigned int
0x1800134d1  xor     r8d, r8d; unsigned __int8 **
0x1800134d4  mov     rdx, r12; lpValueName
0x1800134d7  mov     rcx, r13; hKey
0x1800134da  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x1800134df  lea     rcx, aBackupValueDel; "\r\nBackup Value deleted"
0x1800134e6  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x1800134eb  lea     rcx, asc_18002076C; "\r\n"
0x1800134f2  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x1800134f7  xor     r12d, r12d
0x1800134fa  test    rbx, rbx
0x1800134fd  jnz     loc_1800135AA
0x180013503  or      r13, 0FFFFFFFFFFFFFFFFh
0x180013507  mov     edi, r12d
0x18001350a  test    r14, r14
0x18001350d  jz      short loc_18001352D
0x18001350f  mov     rdi, r13
0x180013512  inc     rdi
0x180013515  cmp     [r14+rdi*2], r12w
0x18001351a  jnz     short loc_180013512
0x18001351c  mov     rax, r13
0x18001351f  inc     rax
0x180013522  cmp     [rsi+rax*2], r12w
0x180013527  jnz     short loc_18001351F
0x180013529  cmp     eax, edi
0x18001352b  jbe     short loc_1800135AA
0x18001352d  mov     rax, r13
0x180013530  inc     rax
0x180013533  cmp     [rsi+rax*2], r12w
0x180013538  jnz     short loc_180013530
0x18001353a  inc     eax
0x18001353c  mov     ecx, 40h ; '@'; uFlags
0x180013541  mov     r14d, eax
0x180013544  lea     rdx, [rax+rax]; uBytes
0x180013548  call    cs:__imp_LocalAlloc
0x18001354e  mov     rbx, rax
0x180013551  test    rax, rax
0x180013554  jz      short loc_1800135AA
0x180013556  mov     r8, rsi; unsigned __int16 *
0x180013559  mov     edx, r14d; unsigned __int64
0x18001355c  mov     rcx, rax; unsigned __int16 *
0x18001355f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013564  mov     rsi, [rbp+hKey]
0x180013568  mov     rdx, rbx; unsigned __int16 *
0x18001356b  mov     rcx, rsi; HKEY
0x18001356e  call    ?RegKeyEmpty@@YAHPEAUHKEY__@@PEBG@Z; RegKeyEmpty(HKEY__ *,ushort const *)
0x180013573  test    eax, eax
0x180013575  jz      short loc_1800135A1
0x180013577  mov     rdx, rbx; lpSubKey
0x18001357a  mov     rcx, rsi; hKey
0x18001357d  call    cs:__imp_RegDeleteKeyW
0x180013583  mov     rcx, rbx; pszPath
0x180013586  call    cs:__imp_PathRemoveFileSpecW
0x18001358c  test    eax, eax
0x18001358e  jz      short loc_1800135A1
0x180013590  mov     rax, r13
0x180013593  inc     rax
0x180013596  cmp     [rbx+rax*2], r12w
0x18001359b  jnz     short loc_180013593
0x18001359d  cmp     eax, edi
0x18001359f  ja      short loc_180013568
0x1800135a1  mov     rcx, rbx; hMem
0x1800135a4  call    cs:__imp_LocalFree
0x1800135aa  mov     rcx, r15; hMem
0x1800135ad  call    cs:__imp_LocalFree
0x1800135b3  mov     eax, 1
0x1800135b8  mov     rbx, [rsp+60h+arg_18]
0x1800135c0  add     rsp, 60h
0x1800135c4  pop     r15
0x1800135c6  pop     r14
0x1800135c8  pop     r13
0x1800135ca  pop     r12
0x1800135cc  pop     rdi
0x1800135cd  pop     rsi
0x1800135ce  pop     rbp
0x1800135cf  retn
```
