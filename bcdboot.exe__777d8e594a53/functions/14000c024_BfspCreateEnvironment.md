# BfspCreateEnvironment

- ea: `0x14000c024`
- end: `0x14000c5d7`
- name: `BfspCreateEnvironment`
- size: `1459`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, LPWSTR pszPath, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140009fd4`

## callees

- `0x140002c14`
- `0x1400030c0`
- `0x140003a04`
- `0x140003cbc`
- `0x14000c024`
- `0x14000c7bc`
- `0x14000c82c`
- `0x14000e628`
- `0x14000f344`
- `0x14000f4b0`
- `0x14000f50c`
- `0x1400265e2`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000c5b7`
- `KERNEL32!SetLastError` at `0x14000c5b7`
- `KERNEL32!GetLastError` at `0x14000c118`
- `KERNEL32!GetLastError` at `0x14000c156`
- `KERNEL32!GetLastError` at `0x14000c2ef`
- `KERNEL32!GetLastError` at `0x14000c47c`
- `KERNEL32!GetLastError` at `0x14000c51d`
- `KERNEL32!GetLastError` at `0x14000c118`
- `KERNEL32!GetLastError` at `0x14000c156`
- `KERNEL32!GetLastError` at `0x14000c2ef`
- `KERNEL32!GetLastError` at `0x14000c47c`
- `KERNEL32!GetLastError` at `0x14000c51d`
- `KERNEL32!HeapFree` at `0x14000c53a`
- `KERNEL32!HeapFree` at `0x14000c553`
- `KERNEL32!HeapFree` at `0x14000c571`
- `KERNEL32!HeapFree` at `0x14000c58a`
- `KERNEL32!HeapFree` at `0x14000c5a3`
- `KERNEL32!HeapFree` at `0x14000c53a`
- `KERNEL32!HeapFree` at `0x14000c553`
- `KERNEL32!HeapFree` at `0x14000c571`
- `KERNEL32!HeapFree` at `0x14000c58a`
- `KERNEL32!HeapFree` at `0x14000c5a3`
- `KERNEL32!HeapAlloc` at `0x14000c0b3`
- `KERNEL32!HeapAlloc` at `0x14000c360`
- `KERNEL32!HeapAlloc` at `0x14000c4b4`
- `KERNEL32!HeapAlloc` at `0x14000c0b3`
- `KERNEL32!HeapAlloc` at `0x14000c360`
- `KERNEL32!HeapAlloc` at `0x14000c4b4`
- `KERNEL32!GetProcessHeap` at `0x14000c09e`
- `KERNEL32!GetProcessHeap` at `0x14000c34b`
- `KERNEL32!GetProcessHeap` at `0x14000c4a3`
- `KERNEL32!GetProcessHeap` at `0x14000c52a`
- `KERNEL32!GetProcessHeap` at `0x14000c545`
- `KERNEL32!GetProcessHeap` at `0x14000c563`
- `KERNEL32!GetProcessHeap` at `0x14000c57c`
- `KERNEL32!GetProcessHeap` at `0x14000c595`
- `KERNEL32!GetProcessHeap` at `0x14000c09e`
- `KERNEL32!GetProcessHeap` at `0x14000c34b`
- `KERNEL32!GetProcessHeap` at `0x14000c4a3`
- `KERNEL32!GetProcessHeap` at `0x14000c52a`
- `KERNEL32!GetProcessHeap` at `0x14000c545`
- `KERNEL32!GetProcessHeap` at `0x14000c563`
- `KERNEL32!GetProcessHeap` at `0x14000c57c`
- `KERNEL32!GetProcessHeap` at `0x14000c595`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c058`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c0fa`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c17a`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c40b`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c058`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c0fa`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c17a`
- `SHLWAPI!PathRemoveBackslashW` at `0x14000c40b`
- `ntdll!RtlImageNtHeader` at `0x14000c280`
- `ntdll!RtlImageNtHeader` at `0x14000c280`

## pseudocode

```c
__int64 __fastcall BfspCreateEnvironment(STRSAFE_LPCWSTR pszSrc, LPWSTR pszPath, _QWORD *a3)
{
  WCHAR *v3; // r13
  __int64 v4; // rbp
  __int64 v8; // rdi
  int v9; // eax
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  _WORD *v14; // r15
  _WORD *v15; // r12
  __int64 v16; // rcx
  WCHAR *SystemPartition; // rax
  WCHAR *v18; // rbx
  int FirmwareType; // r14d
  const wchar_t *v20; // r8
  int v21; // r13d
  const wchar_t *v22; // rbp
  const WCHAR *v23; // rax
  void *v24; // rax
  int Machine; // ebx
  PIMAGE_NT_HEADERS v26; // rax
  int v27; // ebx
  int v28; // ebx
  const wchar_t *v29; // r8
  DWORD LastError; // eax
  HANDLE v31; // rax
  size_t v32; // rbx
  __int64 v33; // rbp
  __int64 v34; // rax
  HANDLE v35; // rax
  __int64 v36; // rbx
  HANDLE v37; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  WCHAR *v43; // [rsp+28h] [rbp-70h]
  wchar_t *lpMem; // [rsp+30h] [rbp-68h]
  void *v45; // [rsp+38h] [rbp-60h]
  __int128 v46; // [rsp+40h] [rbp-58h] BYREF
  __int64 v47; // [rsp+50h] [rbp-48h]
  int v49; // [rsp+B0h] [rbp+18h]

  v3 = 0;
  v4 = -1;
  LODWORD(v8) = 0;
  if ( pszPath )
  {
    PathRemoveBackslashW(pszPath);
    v8 = -1;
    do
      ++v8;
    while ( pszPath[v8] );
  }
  v9 = v8 + 1;
  a3[1] = a3;
  *a3 = a3;
  v10 = -1;
  if ( !(_DWORD)v8 )
    v9 = 0;
  v49 = v9;
  do
    ++v10;
  while ( pszSrc[v10] );
  ProcessHeap = GetProcessHeap();
  lpMem = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 2 * v10 + 2);
  if ( !lpMem )
  {
    v12 = 0;
    LODWORD(v13) = 8;
LABEL_76:
    BfspEnvDestory(a3);
    SetLastError(v13);
    return v12;
  }
  v14 = 0;
  v45 = 0;
  v15 = 0;
  do
    ++v4;
  while ( pszSrc[v4] );
  StringCchCopyW(lpMem, v4 + 1, pszSrc);
  PathRemoveBackslashW(lpMem);
  v12 = BfspEnvAddVariable(a3, L"SOURCE", lpMem);
  if ( !v12 || (v12 = BfspEnvAddVariable(a3, L"SYSROOT", lpMem)) == 0 )
  {
    LODWORD(v13) = GetLastError();
    goto LABEL_67;
  }
  LOBYTE(v16) = 1;
  SystemPartition = (WCHAR *)BfspGetSystemPartition(v16);
  v43 = SystemPartition;
  v18 = SystemPartition;
  if ( SystemPartition )
  {
    PathRemoveBackslashW(SystemPartition);
    v12 = BfspEnvAddVariable(a3, L"SYSPART", v18);
    if ( !v12 )
      goto LABEL_64;
    FirmwareType = BfspGetFirmwareType();
    if ( FirmwareType == 1 )
    {
      v20 = L"PCAT";
      v21 = 5;
      v22 = L"bootmgr";
    }
    else
    {
      if ( FirmwareType != 2 )
      {
        v12 = 0;
        LODWORD(v13) = 31;
        goto LABEL_66;
      }
      v12 = BfspEnvAddVariable(a3, L"BOOTMGBINEX", L"bootmgfw_EX.efi");
      if ( !v12 )
        goto LABEL_64;
      v20 = L"EFI";
      v21 = 19;
      v22 = L"bootmgfw.efi";
    }
    v12 = BfspEnvAddVariable(a3, L"FWTYPE", v20);
    if ( !v12 || (v12 = BfspEnvAddVariable(a3, L"BOOTMGBIN", v22)) == 0 )
    {
LABEL_64:
      LastError = GetLastError();
      goto LABEL_65;
    }
    if ( FirmwareType != 2 )
    {
LABEL_40:
      v12 = BfspEnvAddVariable(a3, L"FONTS", L"Fonts");
      if ( !v12 )
        goto LABEL_64;
      v12 = BfspEnvAddVariable(a3, L"RESOURCES", L"Resources");
      if ( !v12 )
        goto LABEL_64;
      v31 = GetProcessHeap();
      v14 = HeapAlloc(v31, 8u, 2LL * (unsigned int)(v21 + v49));
      if ( !v14 )
      {
        v12 = 0;
        LODWORD(v13) = 8;
        goto LABEL_66;
      }
      v14[v21 + v49 - 1] = 0;
      if ( (_DWORD)v8 )
      {
        v32 = (unsigned int)v8;
        memcpy_0(v14, pszPath, v32 * 2);
        LODWORD(v8) = v8 + 1;
        v14[v32] = 92;
      }
      if ( FirmwareType == 1 )
      {
        *(_QWORD *)&v14[(unsigned int)v8] = 0x74006F006F0042LL;
      }
      else
      {
        *(_OWORD *)&v14[(unsigned int)v8] = *(_OWORD *)L"EFI\\Microsoft\\Boot";
        *(_OWORD *)&v14[(unsigned int)v8 + 8] = *(_OWORD *)L"osoft\\Boot";
        *(_DWORD *)&v14[(unsigned int)v8 + 16] = *(_DWORD *)L"ot";
      }
      v33 = (unsigned int)(v8 - 1);
      if ( (unsigned int)v8 < 2 )
        v33 = (unsigned int)v8;
      PathRemoveBackslashW(v14);
      LODWORD(v13) = 0;
      v12 = BfspEnvAddVariable(a3, L"DEST", v14);
      if ( !v12 )
        goto LABEL_64;
      v34 = BfspEnvExpandString(a3, L"|SYSPART|\\");
      v45 = (void *)v34;
      if ( !v34 )
        goto LABEL_53;
      if ( (unsigned int)BfspIsSecuritySupported(v34) )
      {
        v12 = BfspEnvAddVariable(a3, L"ACLS", L"Yes");
        if ( !v12 )
          goto LABEL_64;
      }
      else if ( GetLastError() != 50 )
      {
LABEL_53:
        v12 = 0;
        goto LABEL_64;
      }
      if ( FirmwareType != 2 )
        goto LABEL_66;
      v35 = GetProcessHeap();
      v15 = HeapAlloc(v35, 8u, 2LL * (unsigned int)(v49 + 9));
      if ( !v15 )
      {
        v12 = 0;
        LODWORD(v13) = 8;
        goto LABEL_66;
      }
      v15[v49 + 8] = 0;
      if ( (_DWORD)v33 )
      {
        v36 = v33;
        memcpy_0(v15, pszPath, 2 * v33);
        v33 = (unsigned int)(v33 + 1);
        v15[v36] = 92;
      }
      *(_OWORD *)&v15[v33] = *(_OWORD *)L"EFI\\Boot";
      v12 = BfspEnvAddVariable(a3, L"EFIDEFAULTDIR", v15);
      if ( v12 )
        goto LABEL_66;
      goto LABEL_64;
    }
    v23 = (const WCHAR *)BfspEnvExpandString(a3, L"|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|");
    v47 = 0;
    v46 = 0;
    v24 = (void *)BfspMapFileForRead(v23);
    if ( v24 )
    {
      Machine = 0;
      v26 = RtlImageNtHeader(v24);
      if ( v26 )
        Machine = v26->FileHeader.Machine;
      BfspUnmapFile(&v46);
      if ( Machine )
      {
        v27 = Machine - 332;
        if ( !v27 )
        {
          v29 = L"bootia32.efi";
          goto LABEL_38;
        }
        v28 = v27 - 118;
        if ( !v28 )
        {
          v29 = L"bootarm.efi";
          goto LABEL_38;
        }
        if ( v28 == 43170 )
        {
          v29 = L"bootaa64.efi";
          goto LABEL_38;
        }
      }
    }
    v29 = L"bootx64.efi";
LABEL_38:
    if ( !(unsigned int)BfspEnvAddVariable(a3, L"DEFAULTAPP", v29) )
    {
      LastError = GetLastError();
      v12 = 0;
LABEL_65:
      LODWORD(v13) = LastError;
      goto LABEL_66;
    }
    goto LABEL_40;
  }
  v12 = 0;
  v13 = GetLastError();
  BfspLogMessage(4, L"Failed to get system partition! Last Error = %#x", v13);
LABEL_66:
  v3 = v43;
LABEL_67:
  v37 = GetProcessHeap();
  HeapFree(v37, 0, lpMem);
  if ( v3 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v3);
  }
  if ( v45 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v45);
  }
  if ( v14 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v14);
  }
  if ( v15 )
  {
    v41 = GetProcessHeap();
    HeapFree(v41, 0, v15);
  }
  if ( !v12 )
    goto LABEL_76;
  return v12;
}

```

## disassembly

```asm
0x14000c024  mov     [rsp+arg_0], rbx
0x14000c029  mov     [rsp+Src], rdx
0x14000c02e  push    rbp
0x14000c02f  push    rsi
0x14000c030  push    rdi
0x14000c031  push    r12
0x14000c033  push    r13
0x14000c035  push    r14
0x14000c037  push    r15
0x14000c039  sub     rsp, 60h
0x14000c03d  xor     r13d, r13d
0x14000c040  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000c044  mov     rsi, r8
0x14000c047  mov     rbx, rdx
0x14000c04a  mov     r14, rcx
0x14000c04d  mov     edi, r13d
0x14000c050  test    rdx, rdx
0x14000c053  jz      short loc_14000C06B
0x14000c055  mov     rcx, rdx; pszPath
0x14000c058  call    cs:__imp_PathRemoveBackslashW
0x14000c05e  mov     rdi, rbp
0x14000c061  inc     rdi
0x14000c064  cmp     [rbx+rdi*2], r13w
0x14000c069  jnz     short loc_14000C061
0x14000c06b  lea     eax, [rdi+1]
0x14000c06e  mov     [rsi+8], rsi
0x14000c072  cmp     edi, 1
0x14000c075  mov     [rsp+98h+arg_18], eax
0x14000c07c  mov     [rsi], rsi
0x14000c07f  mov     rbx, rbp
0x14000c082  cmovb   eax, edi
0x14000c085  mov     [rsp+98h+arg_10], eax
0x14000c08c  inc     rbx
0x14000c08f  cmp     [r14+rbx*2], r13w
0x14000c094  jnz     short loc_14000C08C
0x14000c096  lea     rbx, ds:2[rbx*2]
0x14000c09e  call    cs:__imp_GetProcessHeap
0x14000c0a4  mov     r15d, 8
0x14000c0aa  mov     r8, rbx; dwBytes
0x14000c0ad  mov     rcx, rax; hHeap
0x14000c0b0  mov     edx, r15d; dwFlags
0x14000c0b3  call    cs:__imp_HeapAlloc
0x14000c0b9  mov     [rsp+98h+lpMem], rax
0x14000c0be  mov     rbx, rax
0x14000c0c1  test    rax, rax
0x14000c0c4  jnz     short loc_14000C0D1
0x14000c0c6  mov     ebx, r13d
0x14000c0c9  mov     edi, r15d
0x14000c0cc  jmp     loc_14000C5AD
0x14000c0d1  xor     eax, eax
0x14000c0d3  mov     r15, r13
0x14000c0d6  mov     [rsp+98h+var_60], rax
0x14000c0db  mov     r12, r13
0x14000c0de  inc     rbp
0x14000c0e1  cmp     [r14+rbp*2], ax
0x14000c0e6  jnz     short loc_14000C0DE
0x14000c0e8  lea     rdx, [rbp+1]; cchDest
0x14000c0ec  mov     r8, r14; pszSrc
0x14000c0ef  mov     rcx, rbx; pszDest
0x14000c0f2  call    StringCchCopyW
0x14000c0f7  mov     rcx, rbx; pszPath
0x14000c0fa  call    cs:__imp_PathRemoveBackslashW
0x14000c100  mov     r8, rbx
0x14000c103  lea     rdx, aSource; "SOURCE"
0x14000c10a  mov     rcx, rsi
0x14000c10d  call    BfspEnvAddVariable
0x14000c112  mov     ebx, eax
0x14000c114  test    eax, eax
0x14000c116  jnz     short loc_14000C125
0x14000c118  call    cs:__imp_GetLastError
0x14000c11e  mov     edi, eax
0x14000c120  jmp     loc_14000C52A
0x14000c125  mov     r8, [rsp+98h+lpMem]
0x14000c12a  lea     rdx, aSysroot_0; "SYSROOT"
0x14000c131  mov     rcx, rsi
0x14000c134  call    BfspEnvAddVariable
0x14000c139  mov     ebx, eax
0x14000c13b  test    eax, eax
0x14000c13d  jz      short loc_14000C118
0x14000c13f  mov     cl, 1
0x14000c141  call    BfspGetSystemPartition
0x14000c146  mov     [rsp+98h+var_70], rax
0x14000c14b  mov     rbx, rax
0x14000c14e  test    rax, rax
0x14000c151  jnz     short loc_14000C177
0x14000c153  mov     ebx, r13d
0x14000c156  call    cs:__imp_GetLastError
0x14000c15c  lea     rdx, aFailedToGetSys; "Failed to get system partition! Last Er"...
0x14000c163  mov     ecx, 4
0x14000c168  mov     r8d, eax
0x14000c16b  mov     edi, eax
0x14000c16d  call    BfspLogMessage
0x14000c172  jmp     loc_14000C525
0x14000c177  mov     rcx, rbx; pszPath
0x14000c17a  call    cs:__imp_PathRemoveBackslashW
0x14000c180  mov     r8, rbx
0x14000c183  lea     rdx, aSyspart_1; "SYSPART"
0x14000c18a  mov     rcx, rsi
0x14000c18d  call    BfspEnvAddVariable
0x14000c192  mov     ebx, eax
0x14000c194  test    eax, eax
0x14000c196  jz      loc_14000C51D
0x14000c19c  call    BfspGetFirmwareType
0x14000c1a1  mov     edx, eax
0x14000c1a3  mov     r14d, eax
0x14000c1a6  sub     edx, 1
0x14000c1a9  jz      short loc_14000C1F3
0x14000c1ab  cmp     edx, 1
0x14000c1ae  jz      short loc_14000C1BD
0x14000c1b0  mov     ebx, r13d
0x14000c1b3  mov     edi, 1Fh
0x14000c1b8  jmp     loc_14000C525
0x14000c1bd  lea     r8, aBootmgfwExEfi; "bootmgfw_EX.efi"
0x14000c1c4  mov     rcx, rsi
0x14000c1c7  lea     rdx, aBootmgbinex; "BOOTMGBINEX"
0x14000c1ce  call    BfspEnvAddVariable
0x14000c1d3  mov     ebx, eax
0x14000c1d5  test    eax, eax
0x14000c1d7  jz      loc_14000C51D
0x14000c1dd  lea     r8, aEfi; "EFI"
0x14000c1e4  mov     r13d, 13h
0x14000c1ea  lea     rbp, aBootmgfwEfi; "bootmgfw.efi"
0x14000c1f1  jmp     short loc_14000C207
0x14000c1f3  lea     r8, aPcat; "PCAT"
0x14000c1fa  mov     r13d, 5
0x14000c200  lea     rbp, aBootmgr; "bootmgr"
0x14000c207  lea     rdx, aFwtype; "FWTYPE"
0x14000c20e  mov     rcx, rsi
0x14000c211  call    BfspEnvAddVariable
0x14000c216  mov     ebx, eax
0x14000c218  test    eax, eax
0x14000c21a  jz      loc_14000C51D
0x14000c220  mov     r8, rbp
0x14000c223  lea     rdx, aBootmgbin; "BOOTMGBIN"
0x14000c22a  mov     rcx, rsi
0x14000c22d  call    BfspEnvAddVariable
0x14000c232  mov     ebx, eax
0x14000c234  test    eax, eax
0x14000c236  jz      loc_14000C51D
0x14000c23c  cmp     r14d, 2
0x14000c240  jnz     loc_14000C2FC
0x14000c246  lea     rdx, aSourceFwtypeBo; "|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|"
0x14000c24d  mov     rcx, rsi
0x14000c250  call    BfspEnvExpandString
0x14000c255  xor     ecx, ecx
0x14000c257  lea     r8, [rsp+98h+var_58]
0x14000c25c  mov     [rsp+98h+var_48], rcx
0x14000c261  lea     rdx, [rsp+98h+var_78]
0x14000c266  xorps   xmm0, xmm0
0x14000c269  mov     rcx, rax; lpFileName
0x14000c26c  movups  [rsp+98h+var_58], xmm0
0x14000c271  call    BfspMapFileForRead
0x14000c276  test    rax, rax
0x14000c279  jz      short loc_14000C2D5
0x14000c27b  mov     rcx, rax; BaseAddress
0x14000c27e  xor     ebx, ebx
0x14000c280  call    cs:__imp_RtlImageNtHeader
0x14000c286  test    rax, rax
0x14000c289  jz      short loc_14000C28F
0x14000c28b  movzx   ebx, word ptr [rax+4]
0x14000c28f  lea     rcx, [rsp+98h+var_58]
0x14000c294  call    BfspUnmapFile
0x14000c299  test    ebx, ebx
0x14000c29b  jz      short loc_14000C2D5
0x14000c29d  sub     ebx, 14Ch
0x14000c2a3  jz      short loc_14000C2CC
0x14000c2a5  sub     ebx, 76h ; 'v'
0x14000c2a8  jz      short loc_14000C2C3
0x14000c2aa  sub     ebx, 84A2h
0x14000c2b0  jz      short loc_14000C2D5
0x14000c2b2  cmp     ebx, 2400h
0x14000c2b8  jnz     short loc_14000C2D5
0x14000c2ba  lea     r8, aBootaa64Efi; "bootaa64.efi"
0x14000c2c1  jmp     short loc_14000C2DC
0x14000c2c3  lea     r8, aBootarmEfi; "bootarm.efi"
0x14000c2ca  jmp     short loc_14000C2DC
0x14000c2cc  lea     r8, aBootia32Efi; "bootia32.efi"
0x14000c2d3  jmp     short loc_14000C2DC
0x14000c2d5  lea     r8, aBootx64Efi; "bootx64.efi"
0x14000c2dc  lea     rdx, aDefaultapp; "DEFAULTAPP"
0x14000c2e3  mov     rcx, rsi
0x14000c2e6  call    BfspEnvAddVariable
0x14000c2eb  test    eax, eax
0x14000c2ed  jnz     short loc_14000C2FC
0x14000c2ef  call    cs:__imp_GetLastError
0x14000c2f5  xor     ebx, ebx
0x14000c2f7  jmp     loc_14000C523
0x14000c2fc  lea     r8, aFonts_0; "Fonts"
0x14000c303  mov     rcx, rsi
0x14000c306  lea     rdx, aFonts; "FONTS"
0x14000c30d  call    BfspEnvAddVariable
0x14000c312  mov     ebx, eax
0x14000c314  test    eax, eax
0x14000c316  jz      loc_14000C51D
0x14000c31c  lea     r8, aResources_0; "Resources"
0x14000c323  mov     rcx, rsi
0x14000c326  lea     rdx, aResources; "RESOURCES"
0x14000c32d  call    BfspEnvAddVariable
0x14000c332  mov     ebx, eax
0x14000c334  test    eax, eax
0x14000c336  jz      loc_14000C51D
0x14000c33c  mov     ebp, [rsp+98h+arg_10]
0x14000c343  add     ebp, r13d
0x14000c346  mov     ebx, ebp
0x14000c348  add     rbx, rbx
0x14000c34b  call    cs:__imp_GetProcessHeap
0x14000c351  mov     r13d, 8
0x14000c357  mov     r8, rbx; dwBytes
0x14000c35a  mov     rcx, rax; hHeap
0x14000c35d  mov     edx, r13d; dwFlags
0x14000c360  call    cs:__imp_HeapAlloc
0x14000c366  xor     edx, edx
0x14000c368  mov     r15, rax
0x14000c36b  test    rax, rax
0x14000c36e  jnz     short loc_14000C37A
0x14000c370  mov     ebx, edx
0x14000c372  mov     edi, r13d
0x14000c375  jmp     loc_14000C525
0x14000c37a  mov     r13, [rsp+98h+Src]
0x14000c382  lea     eax, [rbp-1]
0x14000c385  mov     [r15+rax*2], dx
0x14000c38a  cmp     edi, 1
0x14000c38d  jb      short loc_14000C3B3
0x14000c38f  mov     eax, edi
0x14000c391  mov     rdx, r13; Src
0x14000c394  mov     rcx, r15; void *
0x14000c397  lea     rbx, [rax+rax]
0x14000c39b  mov     r8, rbx; Size
0x14000c39e  call    memcpy_0
0x14000c3a3  mov     edi, [rsp+98h+arg_18]
0x14000c3aa  xor     edx, edx
0x14000c3ac  mov     word ptr [rbx+r15], 5Ch ; '\'
0x14000c3b3  mov     ecx, r14d
0x14000c3b6  sub     ecx, 1
0x14000c3b9  jz      short loc_14000C3EF
0x14000c3bb  cmp     ecx, 1
0x14000c3be  jz      short loc_14000C3C7
0x14000c3c0  mov     ebx, edx
0x14000c3c2  jmp     loc_14000C1B3
0x14000c3c7  movups  xmm0, xmmword ptr cs:aEfiMicrosoftBo; "EFI\\Microsoft\\Boot"
0x14000c3ce  mov     ecx, edi
0x14000c3d0  movups  xmmword ptr [r15+rcx*2], xmm0
0x14000c3d5  movups  xmm1, xmmword ptr cs:aEfiMicrosoftBo+10h; "osoft\\Boot"
0x14000c3dc  movups  xmmword ptr [r15+rcx*2+10h], xmm1
0x14000c3e2  mov     eax, dword ptr cs:aEfiMicrosoftBo+20h; "ot"
0x14000c3e8  mov     [r15+rcx*2+20h], eax
0x14000c3ed  jmp     short loc_14000C3FF
0x14000c3ef  mov     eax, edi
0x14000c3f1  mov     rcx, 74006F006F0042h
0x14000c3fb  mov     [r15+rax*2], rcx
0x14000c3ff  cmp     edi, 2
0x14000c402  lea     ebp, [rdi-1]
0x14000c405  mov     rcx, r15; pszPath
0x14000c408  cmovb   ebp, edi
0x14000c40b  call    cs:__imp_PathRemoveBackslashW
0x14000c411  mov     r8, r15
0x14000c414  lea     rdx, aDest; "DEST"
0x14000c41b  mov     rcx, rsi
0x14000c41e  call    BfspEnvAddVariable
0x14000c423  xor     edi, edi
0x14000c425  mov     ebx, eax
0x14000c427  test    eax, eax
0x14000c429  jz      loc_14000C51D
0x14000c42f  lea     rdx, aSyspart_0; "|SYSPART|\\"
0x14000c436  mov     rcx, rsi
0x14000c439  call    BfspEnvExpandString
0x14000c43e  mov     [rsp+98h+var_60], rax
0x14000c443  test    rax, rax
0x14000c446  jnz     short loc_14000C44F
0x14000c448  mov     ebx, edi
0x14000c44a  jmp     loc_14000C51D
0x14000c44f  mov     rcx, rax
0x14000c452  call    BfspIsSecuritySupported
0x14000c457  test    eax, eax
0x14000c459  jz      short loc_14000C47C
0x14000c45b  lea     r8, aYes; "Yes"
0x14000c462  mov     rcx, rsi
0x14000c465  lea     rdx, aAcls; "ACLS"
0x14000c46c  call    BfspEnvAddVariable
0x14000c471  mov     ebx, eax
0x14000c473  test    eax, eax
0x14000c475  jnz     short loc_14000C487
0x14000c477  jmp     loc_14000C51D
0x14000c47c  call    cs:__imp_GetLastError
0x14000c482  cmp     eax, 32h ; '2'
0x14000c485  jnz     short loc_14000C448
0x14000c487  cmp     r14d, 2
0x14000c48b  jnz     loc_14000C525
0x14000c491  mov     r14d, [rsp+98h+arg_10]
0x14000c499  add     r14d, 9
0x14000c49d  mov     ebx, r14d
0x14000c4a0  add     rbx, rbx
0x14000c4a3  call    cs:__imp_GetProcessHeap
0x14000c4a9  mov     r8, rbx; dwBytes
0x14000c4ac  mov     edx, 8; dwFlags
0x14000c4b1  mov     rcx, rax; hHeap
0x14000c4b4  call    cs:__imp_HeapAlloc
0x14000c4ba  xor     edx, edx
0x14000c4bc  mov     r12, rax
0x14000c4bf  test    rax, rax
  ... truncated ...
```
