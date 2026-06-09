# EstimateDiskNeedsHelper

- ea: `0x18004291c`
- end: `0x180042b59`
- name: `EstimateDiskNeedsHelper`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180043520`

## callees

- `0x1800293a0`
- `0x18004255c`
- `0x18004291c`
- `0x180042b60`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceW` at `0x1800429c6`
- `KERNEL32!GetDiskFreeSpaceW` at `0x1800429c6`

## string_xrefs

- `0x180042982`: `No old Windows path specified`
- `0x180042a1a`: `winsxs\manifests`
- `0x180042aba`: `system32\config`
- `0x180042af1`: `system32\wbem\repository`
- `0x180042b19`: `system32\SMI\Store\Machine`

## pseudocode

```c
unsigned __int64 __fastcall EstimateDiskNeedsHelper(
        __int64 a1,
        const wchar_t *a2,
        WCHAR *a3,
        struct CEstimateDiskspaceProgressTracker *a4)
{
  char v6; // bl
  const char *v7; // r8
  unsigned __int64 result; // rax
  unsigned int v9; // edi
  unsigned __int64 DirectoryEffectiveSize; // rbx
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  DWORD BytesPerSector; // [rsp+30h] [rbp-20h] BYREF
  DWORD SectorsPerCluster; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD TotalNumberOfClusters; // [rsp+38h] [rbp-18h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+3Ch] [rbp-14h] BYREF
  WCHAR RootPathName; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+42h] [rbp-Eh]
  wchar_t v23; // [rsp+46h] [rbp-Ah]

  v22 = *(_DWORD *)L":\\";
  v6 = a1;
  v23 = asc_1800AFCF8[3];
  RootPathName = *a3;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  if ( !a2 )
  {
    v7 = "No old Windows path specified";
LABEL_3:
    LogAdapter::TraceAtLevelIfFailed<long,>(a1, 2147942487LL, v7);
    return 0;
  }
  if ( !a4 )
  {
    v7 = "No progress tracker specified";
    goto LABEL_3;
  }
  v9 = 4096;
  if ( GetDiskFreeSpaceW(
         &RootPathName,
         &SectorsPerCluster,
         &BytesPerSector,
         &NumberOfFreeClusters,
         &TotalNumberOfClusters) )
  {
    v9 = SectorsPerCluster * BytesPerSector;
  }
  if ( (v6 & 1) != 0 )
  {
    DirectoryEffectiveSize = GetDirectoryEffectiveSize(a2, L"winsxs\\backup", 0, v9, a4, 0x845u);
    v11 = (DirectoryEffectiveSize >> 1)
        + GetDirectoryEffectiveSize(a2, L"winsxs\\manifests", 0x4600000u, v9, a4, 0x6718u)
        + 2 * DirectoryEffectiveSize;
    v12 = GetDirectoryEffectiveSize(a2, L"winsxs\\filemaps", 0xB00000u, v9, a4, 0x893u) + v11;
  }
  else
  {
    v12 = GetDirectoryEffectiveSize(a2, L"winsxs", 0x100000000uLL, v9, a4, 0x11EE3u) + 419430400;
  }
  v13 = GetDirectoryEffectiveSize(a2, L"servicing\\packages", 0x5A00000u, v9, a4, 0x1DF2u) + v12;
  v14 = GetDirectoryEffectiveSize(a2, L"system32\\config", 0x1F400000u, v9, a4, 0x13u) + v13;
  v15 = GetDirectoryEffectiveSize(a2, L"system32\\wbem\\repository", 0x3200000u, v9, a4, 5u) + v14;
  v16 = GetDirectoryEffectiveSize(a2, L"system32\\SMI\\Store\\Machine", 0xF00000u, v9, a4, 6u) + v15;
  result = 0;
  if ( !*((_BYTE *)a4 + 24) )
    return v16;
  return result;
}

```

## disassembly

```asm
0x18004291c  mov     [rsp-28h+arg_0], rbx
0x180042921  push    rbp
0x180042922  push    rsi
0x180042923  push    rdi
0x180042924  push    r14
0x180042926  push    r15
0x180042928  mov     rbp, rsp
0x18004292b  sub     rsp, 50h
0x18004292f  mov     rax, cs:__security_cookie
0x180042936  xor     rax, rsp
0x180042939  mov     [rbp+var_8], rax
0x18004293d  mov     eax, dword ptr cs:asc_1800AFCF8+2; ":\\"
0x180042943  mov     rsi, r9
0x180042946  mov     [rbp+var_E], eax
0x180042949  mov     r15, rdx
0x18004294c  movzx   eax, word ptr cs:asc_1800AFCF8+6; ""
0x180042953  mov     ebx, ecx
0x180042955  mov     [rbp+var_A], ax
0x180042959  movzx   eax, word ptr [r8]
0x18004295d  mov     [rbp+RootPathName], ax
0x180042961  mov     [rbp+SectorsPerCluster], 0
0x180042968  mov     [rbp+BytesPerSector], 0
0x18004296f  mov     [rbp+NumberOfFreeClusters], 0
0x180042976  mov     [rbp+TotalNumberOfClusters], 0
0x18004297d  test    rdx, rdx
0x180042980  jnz     short loc_18004299A
0x180042982  lea     r8, aNoOldWindowsPa; "No old Windows path specified"
0x180042989  mov     edx, 80070057h
0x18004298e  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x180042993  xor     eax, eax
0x180042995  jmp     loc_180042B38
0x18004299a  test    rsi, rsi
0x18004299d  jnz     short loc_1800429A8
0x18004299f  lea     r8, aNoProgressTrac; "No progress tracker specified"
0x1800429a6  jmp     short loc_180042989
0x1800429a8  lea     rax, [rbp+TotalNumberOfClusters]
0x1800429ac  mov     edi, 1000h
0x1800429b1  lea     r9, [rbp+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x1800429b5  mov     [rsp+50h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1800429ba  lea     r8, [rbp+BytesPerSector]; lpBytesPerSector
0x1800429be  lea     rdx, [rbp+SectorsPerCluster]; lpSectorsPerCluster
0x1800429c2  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x1800429c6  call    cs:__imp_GetDiskFreeSpaceW
0x1800429cd  nop     dword ptr [rax+rax+00h]
0x1800429d2  test    eax, eax
0x1800429d4  jz      short loc_1800429DD
0x1800429d6  mov     edi, [rbp+BytesPerSector]
0x1800429d9  imul    edi, [rbp+SectorsPerCluster]
0x1800429dd  mov     r9d, edi; unsigned int
0x1800429e0  mov     rcx, r15; wchar_t *
0x1800429e3  test    bl, 1
0x1800429e6  jz      short loc_180042A63
0x1800429e8  mov     [rsp+50h+var_28], 845h; unsigned int
0x1800429f0  lea     rdx, aWinsxsBackup; "winsxs\\backup"
0x1800429f7  xor     r8d, r8d; unsigned __int64
0x1800429fa  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x1800429ff  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042a04  mov     r9d, edi; unsigned int
0x180042a07  mov     [rsp+50h+var_28], 6718h; unsigned int
0x180042a0f  mov     r8d, 4600000h; unsigned __int64
0x180042a15  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042a1a  lea     rdx, aWinsxsManifest; "winsxs\\manifests"
0x180042a21  mov     rcx, r15; wchar_t *
0x180042a24  mov     rbx, rax
0x180042a27  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042a2c  mov     rcx, rbx
0x180042a2f  mov     [rsp+50h+var_28], 893h; unsigned int
0x180042a37  shr     rcx, 1
0x180042a3a  lea     rdx, aWinsxsFilemaps_0; "winsxs\\filemaps"
0x180042a41  add     rax, rcx
0x180042a44  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042a49  mov     r9d, edi; unsigned int
0x180042a4c  mov     r8d, 0B00000h; unsigned __int64
0x180042a52  mov     rcx, r15; wchar_t *
0x180042a55  lea     r14, [rax+rbx*2]
0x180042a59  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042a5e  add     r14, rax
0x180042a61  jmp     short loc_180042A8D
0x180042a63  mov     [rsp+50h+var_28], 11EE3h; unsigned int
0x180042a6b  lea     rdx, aWinsxs; "winsxs"
0x180042a72  mov     r8, 100000000h; unsigned __int64
0x180042a7c  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042a81  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042a86  lea     r14, [rax+19000000h]
0x180042a8d  mov     [rsp+50h+var_28], 1DF2h; unsigned int
0x180042a95  lea     rdx, aServicingPacka; "servicing\\packages"
0x180042a9c  mov     r9d, edi; unsigned int
0x180042a9f  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042aa4  mov     r8d, 5A00000h; unsigned __int64
0x180042aaa  mov     rcx, r15; wchar_t *
0x180042aad  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042ab2  mov     [rsp+50h+var_28], 13h; unsigned int
0x180042aba  lea     rdx, aSystem32Config; "system32\\config"
0x180042ac1  mov     r9d, edi; unsigned int
0x180042ac4  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042ac9  mov     r8d, 1F400000h; unsigned __int64
0x180042acf  mov     rcx, r15; wchar_t *
0x180042ad2  lea     rbx, [rax+r14]
0x180042ad6  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042adb  mov     r9d, edi; unsigned int
0x180042ade  mov     [rsp+50h+var_28], 5; unsigned int
0x180042ae6  mov     r8d, 3200000h; unsigned __int64
0x180042aec  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042af1  lea     rdx, aSystem32WbemRe; "system32\\wbem\\repository"
0x180042af8  mov     rcx, r15; wchar_t *
0x180042afb  add     rbx, rax
0x180042afe  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042b03  mov     r9d, edi; unsigned int
0x180042b06  mov     [rsp+50h+var_28], 6; unsigned int
0x180042b0e  mov     r8d, 0F00000h; unsigned __int64
0x180042b14  mov     [rsp+50h+lpTotalNumberOfClusters], rsi; struct CEstimateDiskspaceProgressTracker *
0x180042b19  lea     rdx, aSystem32SmiSto; "system32\\SMI\\Store\\Machine"
0x180042b20  mov     rcx, r15; wchar_t *
0x180042b23  add     rbx, rax
0x180042b26  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180042b2b  lea     rcx, [rax+rbx]
0x180042b2f  xor     eax, eax
0x180042b31  cmp     [rsi+18h], al
0x180042b34  cmovz   rax, rcx
0x180042b38  mov     rcx, [rbp+var_8]
0x180042b3c  xor     rcx, rsp; StackCookie
0x180042b3f  call    __security_check_cookie
0x180042b44  mov     rbx, [rsp+50h+arg_0]
0x180042b4c  add     rsp, 50h
0x180042b50  pop     r15
0x180042b52  pop     r14
0x180042b54  pop     rdi
0x180042b55  pop     rsi
0x180042b56  pop     rbp
0x180042b57  retn
```
