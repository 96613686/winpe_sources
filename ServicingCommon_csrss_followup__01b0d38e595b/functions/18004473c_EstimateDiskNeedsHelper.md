# EstimateDiskNeedsHelper

- ea: `0x18004473c`
- end: `0x180044991`
- name: `EstimateDiskNeedsHelper`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180046170`

## callees

- `0x180024c80`
- `0x18002d2b0`
- `0x18004473c`
- `0x180044b34`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceW` at `0x1800447ed`
- `KERNEL32!GetDiskFreeSpaceW` at `0x1800447ed`

## string_xrefs

- `0x1800447a0`: `No old Windows path specified`
- `0x180044841`: `winsxs\manifests`
- `0x1800448ef`: `system32\config`
- `0x180044917`: `system32\wbem\repository`
- `0x18004493f`: `system32\SMI\Store\Machine`

## pseudocode

```c
__int64 __fastcall EstimateDiskNeedsHelper(
        char a1,
        const wchar_t *a2,
        WCHAR *a3,
        struct CEstimateDiskspaceProgressTracker *a4)
{
  __int64 v7; // rdi
  int v8; // esi
  unsigned __int64 DirectoryEffectiveSize; // rbx
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rax
  DWORD BytesPerSector; // [rsp+30h] [rbp-20h] BYREF
  DWORD SectorsPerCluster; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD TotalNumberOfClusters; // [rsp+38h] [rbp-18h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+3Ch] [rbp-14h] BYREF
  WCHAR RootPathName; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+42h] [rbp-Eh]
  wchar_t v23; // [rsp+46h] [rbp-Ah]

  v22 = *(_DWORD *)L":\\";
  v23 = asc_1800AF6E0[3];
  v7 = 0;
  RootPathName = *a3;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      v8 = 4096;
      if ( GetDiskFreeSpaceW(
             &RootPathName,
             &SectorsPerCluster,
             &BytesPerSector,
             &NumberOfFreeClusters,
             &TotalNumberOfClusters) )
      {
        v8 = SectorsPerCluster * BytesPerSector;
      }
      if ( (a1 & 1) != 0 )
      {
        DirectoryEffectiveSize = GetDirectoryEffectiveSize(a2, L"winsxs\\backup", 0, v8, a4, 0x845u);
        v10 = (DirectoryEffectiveSize >> 1)
            + GetDirectoryEffectiveSize(a2, L"winsxs\\manifests", 73400320, v8, a4, 0x6718u)
            + 2 * DirectoryEffectiveSize;
        v11 = GetDirectoryEffectiveSize(a2, L"winsxs\\filemaps", 11534336, v8, a4, 0x893u) + v10;
      }
      else
      {
        v11 = GetDirectoryEffectiveSize(a2, L"winsxs", 0x100000000LL, v8, a4, 0x11EE3u) + 419430400;
      }
      v12 = GetDirectoryEffectiveSize(a2, L"servicing\\packages", 94371840, v8, a4, 0x1DF2u);
      v13 = GetDirectoryEffectiveSize(a2, L"system32\\config", 524288000, v8, a4, 0x13u);
      v14 = GetDirectoryEffectiveSize(a2, L"system32\\wbem\\repository", 52428800, v8, a4, 5u);
      v15 = GetDirectoryEffectiveSize(a2, L"system32\\SMI\\Store\\Machine", 15728640, v8, a4, 6u);
      if ( *((_BYTE *)a4 + 24) )
        return 0;
      else
        return v12 + v13 + v15 + v14 + v11;
    }
    else
    {
      CBSWdsLog(0x4000000, 2147942487LL, 1, "No progress tracker specified");
    }
  }
  else
  {
    CBSWdsLog(0x4000000, 2147942487LL, 1, "No old Windows path specified");
  }
  return v7;
}

```

## disassembly

```asm
0x18004473c  mov     [rsp-38h+arg_0], rbx
0x180044741  push    rbp
0x180044742  push    rsi
0x180044743  push    rdi
0x180044744  push    r12
0x180044746  push    r13
0x180044748  push    r14
0x18004474a  push    r15
0x18004474c  mov     rbp, rsp
0x18004474f  sub     rsp, 50h
0x180044753  mov     rax, cs:__security_cookie
0x18004475a  xor     rax, rsp
0x18004475d  mov     [rbp+var_8], rax
0x180044761  mov     eax, dword ptr cs:asc_1800AF6E0+2; ":\\"
0x180044767  xor     r12d, r12d
0x18004476a  mov     [rbp+var_E], eax
0x18004476d  mov     r14, r9
0x180044770  movzx   eax, word ptr cs:asc_1800AF6E0+6; ""
0x180044777  mov     r15, rdx
0x18004477a  mov     [rbp+var_A], ax
0x18004477e  mov     ebx, ecx
0x180044780  movzx   eax, word ptr [r8]
0x180044784  mov     edi, r12d
0x180044787  mov     [rbp+RootPathName], ax
0x18004478b  mov     [rbp+SectorsPerCluster], r12d
0x18004478f  mov     [rbp+BytesPerSector], r12d
0x180044793  mov     [rbp+NumberOfFreeClusters], r12d
0x180044797  mov     [rbp+TotalNumberOfClusters], r12d
0x18004479b  test    rdx, rdx
0x18004479e  jnz     short loc_1800447C1
0x1800447a0  lea     r9, aNoOldWindowsPa; "No old Windows path specified"
0x1800447a7  mov     edx, 80070057h
0x1800447ac  mov     ecx, 4000000h
0x1800447b1  mov     r8d, 1
0x1800447b7  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1800447bc  jmp     loc_180044969
0x1800447c1  test    r14, r14
0x1800447c4  jnz     short loc_1800447CF
0x1800447c6  lea     r9, aNoProgressTrac; "No progress tracker specified"
0x1800447cd  jmp     short loc_1800447A7
0x1800447cf  lea     rax, [rbp+TotalNumberOfClusters]
0x1800447d3  mov     esi, 1000h
0x1800447d8  lea     r9, [rbp+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x1800447dc  mov     [rsp+50h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1800447e1  lea     r8, [rbp+BytesPerSector]; lpBytesPerSector
0x1800447e5  lea     rdx, [rbp+SectorsPerCluster]; lpSectorsPerCluster
0x1800447e9  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x1800447ed  call    cs:__imp_GetDiskFreeSpaceW
0x1800447f4  nop     dword ptr [rax+rax+00h]
0x1800447f9  test    eax, eax
0x1800447fb  jz      short loc_180044804
0x1800447fd  mov     esi, [rbp+BytesPerSector]
0x180044800  imul    esi, [rbp+SectorsPerCluster]
0x180044804  mov     r9d, esi; unsigned int
0x180044807  mov     rcx, r15; wchar_t *
0x18004480a  test    bl, 1
0x18004480d  jz      short loc_18004488A
0x18004480f  mov     [rsp+50h+var_28], 845h; unsigned int
0x180044817  lea     rdx, aWinsxsBackup; "winsxs\\backup"
0x18004481e  xor     r8d, r8d; unsigned __int64
0x180044821  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x180044826  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x18004482b  mov     r9d, esi; unsigned int
0x18004482e  mov     [rsp+50h+var_28], 6718h; unsigned int
0x180044836  mov     r8d, 4600000h; unsigned __int64
0x18004483c  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x180044841  lea     rdx, aWinsxsManifest; "winsxs\\manifests"
0x180044848  mov     rcx, r15; wchar_t *
0x18004484b  mov     rbx, rax
0x18004484e  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180044853  mov     rcx, rbx
0x180044856  mov     [rsp+50h+var_28], 893h; unsigned int
0x18004485e  shr     rcx, 1
0x180044861  lea     rdx, aWinsxsFilemaps_0; "winsxs\\filemaps"
0x180044868  add     rax, rcx
0x18004486b  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x180044870  mov     r9d, esi; unsigned int
0x180044873  mov     r8d, 0B00000h; unsigned __int64
0x180044879  mov     rcx, r15; wchar_t *
0x18004487c  lea     rdi, [rax+rbx*2]
0x180044880  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180044885  add     rdi, rax
0x180044888  jmp     short loc_1800448B4
0x18004488a  mov     [rsp+50h+var_28], 11EE3h; unsigned int
0x180044892  lea     rdx, aWinsxs; "winsxs"
0x180044899  mov     r8, 100000000h; unsigned __int64
0x1800448a3  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x1800448a8  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x1800448ad  lea     rdi, [rax+19000000h]
0x1800448b4  mov     [rsp+50h+var_28], 1DF2h; unsigned int
0x1800448bc  lea     rdx, aServicingPacka; "servicing\\packages"
0x1800448c3  mov     r9d, esi; unsigned int
0x1800448c6  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x1800448cb  mov     r8d, 5A00000h; unsigned __int64
0x1800448d1  mov     rcx, r15; wchar_t *
0x1800448d4  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x1800448d9  mov     r9d, esi; unsigned int
0x1800448dc  mov     [rsp+50h+var_28], 13h; unsigned int
0x1800448e4  mov     r8d, 1F400000h; unsigned __int64
0x1800448ea  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x1800448ef  lea     rdx, aSystem32Config; "system32\\config"
0x1800448f6  mov     rcx, r15; wchar_t *
0x1800448f9  mov     rbx, rax
0x1800448fc  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180044901  mov     r9d, esi; unsigned int
0x180044904  mov     [rsp+50h+var_28], 5; unsigned int
0x18004490c  mov     r8d, 3200000h; unsigned __int64
0x180044912  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x180044917  lea     rdx, aSystem32WbemRe; "system32\\wbem\\repository"
0x18004491e  mov     rcx, r15; wchar_t *
0x180044921  mov     r12, rax
0x180044924  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180044929  mov     r9d, esi; unsigned int
0x18004492c  mov     [rsp+50h+var_28], 6; unsigned int
0x180044934  mov     r8d, 0F00000h; unsigned __int64
0x18004493a  mov     [rsp+50h+lpTotalNumberOfClusters], r14; struct CEstimateDiskspaceProgressTracker *
0x18004493f  lea     rdx, aSystem32SmiSto; "system32\\SMI\\Store\\Machine"
0x180044946  mov     rcx, r15; wchar_t *
0x180044949  mov     r13, rax
0x18004494c  call    ?GetDirectoryEffectiveSize@@YA_KPEB_W0_KKPEAVCEstimateDiskspaceProgressTracker@@K@Z; GetDirectoryEffectiveSize(wchar_t const *,wchar_t const *,unsigned __int64,ulong,CEstimateDiskspaceProgressTracker *,ulong)
0x180044951  cmp     byte ptr [r14+18h], 0
0x180044956  jz      short loc_18004495C
0x180044958  xor     edi, edi
0x18004495a  jmp     short loc_180044969
0x18004495c  lea     rcx, [rax+r13]
0x180044960  add     rcx, r12
0x180044963  add     rcx, rbx
0x180044966  add     rdi, rcx
0x180044969  mov     rax, rdi
0x18004496c  mov     rcx, [rbp+var_8]
0x180044970  xor     rcx, rsp; StackCookie
0x180044973  call    __security_check_cookie
0x180044978  mov     rbx, [rsp+50h+arg_0]
0x180044980  add     rsp, 50h
0x180044984  pop     r15
0x180044986  pop     r14
0x180044988  pop     r13
0x18004498a  pop     r12
0x18004498c  pop     rdi
0x18004498d  pop     rsi
0x18004498e  pop     rbp
0x18004498f  retn
```
