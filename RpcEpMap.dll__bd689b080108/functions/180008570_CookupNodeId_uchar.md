# CookupNodeId(uchar *)

- ea: `0x180008570`
- end: `0x18000871b`
- name: `?CookupNodeId@@YAXPEAE@Z`
- size: `427`
- prototype: `void __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008df0`

## callees

- `0x180008570`
- `0x18000a8b4`
- `0x18000a980`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800086c3`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800086c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000861e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000861e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800085df`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800085df`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000865d`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000865d`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180008691`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180008691`

## pseudocode

```c
void __fastcall CookupNodeId(unsigned __int8 *a1)
{
  WCHAR *v2; // r8
  DWORD v3; // edx
  char v4; // cl
  DWORD v5; // eax
  DWORD nSize; // [rsp+30h] [rbp-49h] BYREF
  DWORD BytesPerSector; // [rsp+34h] [rbp-45h] BYREF
  DWORD SectorsPerCluster; // [rsp+38h] [rbp-41h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+3Ch] [rbp-3Dh] BYREF
  DWORD NumberOfFreeClusters; // [rsp+40h] [rbp-39h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-31h] BYREF
  struct _LUID Luid; // [rsp+50h] [rbp-29h] BYREF
  _MEMORYSTATUSEX v13; // [rsp+60h] [rbp-19h] BYREF
  _DWORD v14[2]; // [rsp+A0h] [rbp+27h] BYREF
  WCHAR Buffer[16]; // [rsp+A8h] [rbp+2Fh] BYREF

  nSize = 16;
  PerformanceCount.QuadPart = 0;
  Luid = 0;
  memset_0(&v13, 0, sizeof(v13));
  SectorsPerCluster = 0;
  memset(v14, 17, 6);
  BytesPerSector = 0;
  TotalNumberOfClusters = 0;
  NumberOfFreeClusters = 0;
  if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    nSize = 0;
    if ( Buffer[0] )
    {
      v2 = Buffer;
      v3 = 0;
      do
      {
        v4 = *(_BYTE *)v2++;
        *((_BYTE *)v14 + v3++) ^= v4;
        nSize = v3;
        if ( v3 >= 6 )
        {
          nSize = 0;
          v3 = 0;
        }
      }
      while ( *v2 );
    }
  }
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    *(_DWORD *)((char *)v14 + 2) ^= PerformanceCount.HighPart ^ PerformanceCount.LowPart;
    v5 = PerformanceCount.HighPart ^ PerformanceCount.LowPart ^ v14[0];
  }
  else
  {
    v5 = v14[0];
  }
  v13.dwLength = 64;
  v14[0] = ((unsigned int)&v13.ullTotalPageFile + 1 + 39) ^ v5;
  *(_DWORD *)((char *)v14 + 2) ^= (unsigned int)v14;
  GlobalMemoryStatusEx(&v13);
  v14[0] ^= v13.dwMemoryLoad;
  *(_DWORD *)((char *)v14 + 2) ^= LODWORD(v13.ullTotalPhys);
  v14[0] ^= LODWORD(v13.ullAvailPhys) ^ LODWORD(v13.ullTotalPageFile);
  *(_DWORD *)((char *)v14 + 2) ^= LODWORD(v13.ullAvailPageFile) ^ LODWORD(v13.ullTotalVirtual);
  v14[0] ^= LODWORD(v13.ullAvailVirtual);
  if ( AllocateLocallyUniqueId(&Luid) )
  {
    v14[0] ^= Luid.LowPart;
    *(_DWORD *)((char *)v14 + 2) ^= Luid.HighPart;
  }
  if ( GetDiskFreeSpaceW(L"c:\\", &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters) )
  {
    *(_DWORD *)((char *)v14 + 2) ^= SectorsPerCluster * BytesPerSector * TotalNumberOfClusters;
    v14[0] ^= SectorsPerCluster * BytesPerSector * NumberOfFreeClusters;
  }
  LOBYTE(v14[0]) |= 0x80u;
  *(_DWORD *)a1 = v14[0];
  *((_WORD *)a1 + 2) = v14[1];
}

```

## disassembly

```asm
0x180008570  mov     [rsp-8+arg_8], rbx
0x180008575  mov     [rsp-8+arg_10], rdi
0x18000857a  push    rbp
0x18000857b  lea     rbp, [rsp-57h]
0x180008580  sub     rsp, 0D0h
0x180008587  mov     rax, cs:__security_cookie
0x18000858e  xor     rax, rsp
0x180008591  mov     [rbp+57h+var_8], rax
0x180008595  xor     edi, edi
0x180008597  mov     [rbp+57h+nSize], 10h
0x18000859e  mov     rbx, rcx
0x1800085a1  mov     qword ptr [rbp+57h+PerformanceCount], rdi
0x1800085a5  xor     edx, edx; Val
0x1800085a7  mov     qword ptr [rbp+57h+Luid.LowPart], rdi
0x1800085ab  lea     rcx, [rbp+57h+var_70]; void *
0x1800085af  lea     r8d, [rdi+40h]; Size
0x1800085b3  call    memset_0
0x1800085b8  mov     rax, 1111111111111111h
0x1800085c2  mov     [rbp+57h+SectorsPerCluster], edi
0x1800085c5  lea     r8, [rbp+57h+nSize]; nSize
0x1800085c9  mov     [rbp+57h+var_30], eax
0x1800085cc  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800085d0  mov     [rbp+57h+var_2C], ax
0x1800085d4  xor     ecx, ecx; NameType
0x1800085d6  mov     [rbp+57h+BytesPerSector], edi
0x1800085d9  mov     [rbp+57h+TotalNumberOfClusters], edi
0x1800085dc  mov     [rbp+57h+NumberOfFreeClusters], edi
0x1800085df  call    cs:__imp_GetComputerNameExW
0x1800085e5  test    eax, eax
0x1800085e7  jz      short loc_18000861A
0x1800085e9  mov     [rbp+57h+nSize], edi
0x1800085ec  cmp     [rbp+57h+Buffer], di
0x1800085f0  jz      short loc_18000861A
0x1800085f2  lea     r8, [rbp+57h+Buffer]
0x1800085f6  mov     edx, edi
0x1800085f8  mov     cl, [r8]
0x1800085fb  lea     r8, [r8+2]
0x1800085ff  mov     eax, edx
0x180008601  xor     byte ptr [rbp+rax+57h+var_30], cl
0x180008605  inc     edx
0x180008607  mov     [rbp+57h+nSize], edx
0x18000860a  cmp     edx, 6
0x18000860d  jb      short loc_180008614
0x18000860f  mov     [rbp+57h+nSize], edi
0x180008612  mov     edx, edi
0x180008614  cmp     [r8], di
0x180008618  jnz     short loc_1800085F8
0x18000861a  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18000861e  call    cs:__imp_QueryPerformanceCounter
0x180008624  test    eax, eax
0x180008626  jz      short loc_18000863F
0x180008628  mov     eax, [rbp+57h+var_30+2]
0x18000862b  xor     eax, dword ptr [rbp+57h+PerformanceCount]
0x18000862e  xor     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x180008631  mov     [rbp+57h+var_30+2], eax
0x180008634  mov     eax, [rbp+57h+var_30]
0x180008637  xor     eax, dword ptr [rbp+57h+PerformanceCount]
0x18000863a  xor     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x18000863d  jmp     short loc_180008642
0x18000863f  mov     eax, [rbp+57h+var_30]
0x180008642  lea     rcx, [rbp+57h+var_30]
0x180008646  mov     [rbp+57h+var_70.dwLength], 40h ; '@'
0x18000864d  xor     eax, ecx
0x18000864f  lea     rcx, [rbp+57h+var_70]; lpBuffer
0x180008653  mov     [rbp+57h+var_30], eax
0x180008656  lea     rax, [rbp+57h+var_30]
0x18000865a  xor     [rbp+57h+var_30+2], eax
0x18000865d  call    cs:__imp_GlobalMemoryStatusEx
0x180008663  mov     eax, [rbp+57h+var_70.dwMemoryLoad]
0x180008666  lea     rcx, [rbp+57h+Luid]; Luid
0x18000866a  xor     [rbp+57h+var_30], eax
0x18000866d  mov     eax, dword ptr [rbp+57h+var_70.ullTotalPhys]
0x180008670  xor     [rbp+57h+var_30+2], eax
0x180008673  mov     eax, [rbp+57h+var_30]
0x180008676  xor     eax, dword ptr [rbp+57h+var_70.ullTotalPageFile]
0x180008679  xor     eax, dword ptr [rbp+57h+var_70.ullAvailPhys]
0x18000867c  mov     [rbp+57h+var_30], eax
0x18000867f  mov     eax, [rbp+57h+var_30+2]
0x180008682  xor     eax, dword ptr [rbp+57h+var_70.ullTotalVirtual]
0x180008685  xor     eax, dword ptr [rbp+57h+var_70.ullAvailPageFile]
0x180008688  mov     [rbp+57h+var_30+2], eax
0x18000868b  mov     eax, dword ptr [rbp+57h+var_70.ullAvailVirtual]
0x18000868e  xor     [rbp+57h+var_30], eax
0x180008691  call    cs:__imp_AllocateLocallyUniqueId
0x180008697  test    eax, eax
0x180008699  jz      short loc_1800086A7
0x18000869b  mov     eax, [rbp+57h+Luid.LowPart]
0x18000869e  xor     [rbp+57h+var_30], eax
0x1800086a1  mov     eax, [rbp+57h+Luid.HighPart]
0x1800086a4  xor     [rbp+57h+var_30+2], eax
0x1800086a7  lea     rax, [rbp+57h+TotalNumberOfClusters]
0x1800086ab  lea     r9, [rbp+57h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x1800086af  mov     [rsp+0D0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1800086b4  lea     r8, [rbp+57h+BytesPerSector]; lpBytesPerSector
0x1800086b8  lea     rdx, [rbp+57h+SectorsPerCluster]; lpSectorsPerCluster
0x1800086bc  lea     rcx, RootPathName; "c:\\"
0x1800086c3  call    cs:__imp_GetDiskFreeSpaceW
0x1800086c9  test    eax, eax
0x1800086cb  jz      short loc_1800086E9
0x1800086cd  mov     eax, [rbp+57h+TotalNumberOfClusters]
0x1800086d0  imul    eax, [rbp+57h+BytesPerSector]
0x1800086d4  imul    eax, [rbp+57h+SectorsPerCluster]
0x1800086d8  xor     [rbp+57h+var_30+2], eax
0x1800086db  mov     eax, [rbp+57h+NumberOfFreeClusters]
0x1800086de  imul    eax, [rbp+57h+BytesPerSector]
0x1800086e2  imul    eax, [rbp+57h+SectorsPerCluster]
0x1800086e6  xor     [rbp+57h+var_30], eax
0x1800086e9  or      byte ptr [rbp+57h+var_30], 80h
0x1800086ed  mov     eax, [rbp+57h+var_30]
0x1800086f0  mov     [rbx], eax
0x1800086f2  movzx   eax, [rbp+57h+var_2C]
0x1800086f6  mov     [rbx+4], ax
0x1800086fa  mov     rcx, [rbp+57h+var_8]
0x1800086fe  xor     rcx, rsp; StackCookie
0x180008701  call    __security_check_cookie
0x180008706  lea     r11, [rsp+0D0h+var_s0]
0x18000870e  mov     rbx, [r11+18h]
0x180008712  mov     rdi, [r11+20h]
0x180008716  mov     rsp, r11
0x180008719  pop     rbp
0x18000871a  retn
```
