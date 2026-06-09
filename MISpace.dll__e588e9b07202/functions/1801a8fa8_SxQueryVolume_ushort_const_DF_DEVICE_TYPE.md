# SxQueryVolume(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x1801a8fa8`
- end: `0x1801a940e`
- name: `?SxQueryVolume@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `1126`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum DF_DEVICE_TYPE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18012e390`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x1801a8374`
- `0x1801a8ddc`
- `0x1801a8fa8`
- `0x1801a95bc`
- `0x1801a9c4c`
- `0x1801aa130`
- `0x1801aa5bc`
- `0x1801aad0c`
- `0x1801ab1bc`
- `0x1801ab268`
- `0x1801ab4a0`
- `0x1801ab4d0`
- `0x1801ab5c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a9337`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a934c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a9337`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a934c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a93d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a93d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a9135`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a9135`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a90ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a90ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a93a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a93b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a93a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a93b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9154`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a920a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a920a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a91d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a91d2`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801a9322`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801a9322`

## pseudocode

```c
__int64 __fastcall SxQueryVolume(const unsigned __int16 *a1, enum DF_DEVICE_TYPE *a2)
{
  struct _VOLUME_DISK_EXTENTS *v4; // rdi
  __int64 FileW; // rbx
  __int16 v6; // ax
  _DWORD *v7; // r14
  __int64 v8; // rcx
  enum DF_DEVICE_TYPE *v9; // rax
  int v10; // r9d
  int v11; // eax
  _DWORD *v12; // rax
  unsigned __int16 v13; // dx
  int DiskExts; // eax
  bool v15; // sf
  DWORD DiskNumber; // ecx
  DWORD v17; // esi
  unsigned int v18; // ecx
  unsigned int v19; // edi
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  int DeviceType; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v25; // [rsp+54h] [rbp-ACh]
  __int16 v26; // [rsp+56h] [rbp-AAh]
  DWORD BytesReturned; // [rsp+88h] [rbp-78h] BYREF
  struct _VOLUME_DISK_EXTENTS *v28; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileSystemNameBuffer; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[206]; // [rsp+B2h] [rbp-4Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DeviceType, "SxQueryVolume", 0x770u, 1u);
  v22 = 1;
  v28 = 0;
  v21 = 0;
  FileSystemNameBuffer = 0;
  v4 = 0;
  memset_0(v32, 0, 0xC6u);
  BytesReturned = 0;
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1802DEE50;
  lpFileName[1] = 0;
  v6 = 1921;
  hKey = 0;
  v7 = 0;
  v23 = 0;
  if ( !a1 )
    goto LABEL_50;
  DeviceType = 0;
  v25 = 1921;
  if ( !a2 )
  {
    v6 = 1924;
LABEL_50:
    DeviceType = -2147024809;
    goto LABEL_51;
  }
  v8 = 4;
  v9 = a2;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (enum DF_DEVICE_TYPE *)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  DeviceType = 0;
  v25 = 1924;
  if ( (unsigned int)SxIsRemovableFatVolume(a1) )
  {
    v21 = 2;
  }
  else
  {
    DiskExts = SxGetDiskExts(a1, &v28);
    v4 = v28;
    v15 = DiskExts < 0;
    DeviceType = DiskExts;
    v6 = 1947;
    if ( v15 )
      goto LABEL_51;
    v25 = 1947;
    DiskNumber = v28->Extents[0].DiskNumber;
    if ( DiskNumber == -1 )
    {
      DeviceType = -1996488691;
      v6 = 1952;
      goto LABEL_51;
    }
    DeviceType = SxQueryDeviceType(DiskNumber, (enum DF_DEVICE_TYPE *)&v21);
    v6 = 1955;
    if ( DeviceType < 0 )
      goto LABEL_51;
    v25 = 1955;
    if ( v4->NumberOfDiskExtents > 1 )
    {
      v17 = 0;
      do
      {
        v18 = v4->Extents[v17].DiskNumber;
        if ( v18 == -1 )
        {
          DeviceType = -1996488691;
          v6 = 1969;
          goto LABEL_51;
        }
        if ( (int)SxQueryDeviceDefragAppropriate(v18, &v22) < 0 )
          break;
        if ( v22 )
          break;
        ++v17;
      }
      while ( v17 < v4->NumberOfDiskExtents );
      if ( v17 == v4->NumberOfDiskExtents )
        v21 = 3;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl'::`2'::impl)
    && v21 - 9 <= 1 )
  {
    SxQueryDeviceForThinProvisionedDisk(v4->Extents[0].DiskNumber, v21, &v21);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfrg", 0, 0x20019u, &hKey) )
  {
    if ( !(unsigned int)SxRegReadDWORD(hKey, L"MatchingSlabOptimization", &v23, v10) && v23 == 1 && v21 - 9 <= 1 )
      SxQueryDeviceForThinProvisionedDisk(v4->Extents[0].DiskNumber, v21, &v21);
    RegCloseKey(hKey);
  }
  v11 = v21;
  if ( v21 != 6 && v21 != 12 )
    goto LABEL_38;
  v12 = CoTaskMemAlloc(0x4000u);
  v7 = v12;
  if ( !v12 )
  {
    DeviceType = -2147024882;
    v26 = 2016;
    goto LABEL_52;
  }
  v25 = 2016;
  DeviceType = 0;
  memset_0(v12, 0, 0x4000u);
  DeviceType = CBsString::Set((CBsString *)lpFileName, a1);
  v6 = 2019;
  if ( DeviceType < 0 )
  {
LABEL_51:
    v26 = v6;
    goto LABEL_52;
  }
  v25 = 2019;
  CBsString::UnTrailing((CBsString *)lpFileName, v13);
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( FileW == -1 || !DeviceIoControl((HANDLE)FileW, 0x902ECu, 0, 0, v7, 0x4000u, &BytesReturned, 0) || v7[3] <= 1u )
  {
    v11 = v21;
  }
  else
  {
    v11 = 11;
    v21 = 11;
  }
LABEL_38:
  if ( v11 == 3 || v11 == 12 )
  {
    if ( !GetVolumeInformationW(a1, 0, 0, 0, 0, 0, &FileSystemNameBuffer, 0x64u)
      || (unsigned int)_o__wcsicmp(&FileSystemNameBuffer, L"NTFS")
      && (unsigned int)_o__wcsicmp(&FileSystemNameBuffer, L"REFS") )
    {
      v11 = v21;
    }
    else
    {
      v11 = 13;
      if ( v21 == 3 )
        v11 = 4;
      v21 = v11;
    }
  }
  *(_DWORD *)a2 = v11;
  v25 = 2081;
  DeviceType = 0;
LABEL_52:
  CoTaskMemFree(v4);
  CoTaskMemFree(v7);
  v19 = DeviceType;
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DeviceType);
  return v19;
}

```

## disassembly

```asm
0x1801a8fa8  mov     [rsp-8+arg_10], rbx
0x1801a8fad  push    rbp
0x1801a8fae  push    rsi
0x1801a8faf  push    rdi
0x1801a8fb0  push    r12
0x1801a8fb2  push    r13
0x1801a8fb4  push    r14
0x1801a8fb6  push    r15
0x1801a8fb8  lea     rbp, [rsp-90h]
0x1801a8fc0  sub     rsp, 190h
0x1801a8fc7  mov     rax, cs:__security_cookie
0x1801a8fce  xor     rax, rsp
0x1801a8fd1  mov     [rbp+0C0h+var_40], rax
0x1801a8fd8  mov     r12, rdx
0x1801a8fdb  mov     r15, rcx
0x1801a8fde  lea     rdx, aSxqueryvolume; "SxQueryVolume"
0x1801a8fe5  mov     r9d, 1; unsigned __int16
0x1801a8feb  lea     rcx, [rsp+1C0h+var_170]; this
0x1801a8ff0  mov     r8d, 770h; unsigned __int16
0x1801a8ff6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801a8ffb  xor     r13d, r13d
0x1801a8ffe  mov     [rsp+1C0h+var_17C], 1
0x1801a9006  xor     edx, edx; Val
0x1801a9008  mov     [rbp+0C0h+var_130], r13
0x1801a900c  mov     r8d, 0C6h; Size
0x1801a9012  mov     [rsp+1C0h+var_180], r13d
0x1801a9017  lea     rcx, [rbp+0C0h+var_10E]; void *
0x1801a901b  mov     [rbp+0C0h+FileSystemNameBuffer], r13w
0x1801a9020  mov     edi, r13d
0x1801a9023  call    memset_0
0x1801a9028  lea     rax, qword_1802DEE50
0x1801a902f  mov     [rbp+0C0h+BytesReturned], r13d
0x1801a9033  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801a9037  mov     [rbp+0C0h+lpFileName], rax
0x1801a903b  mov     [rbp+0C0h+var_118], r13
0x1801a903f  mov     eax, 781h
0x1801a9044  mov     [rbp+0C0h+hKey], r13
0x1801a9048  mov     r14d, r13d
0x1801a904b  mov     [rsp+1C0h+var_178], r13d
0x1801a9050  test    r15, r15
0x1801a9053  jz      loc_1801A9399
0x1801a9059  mov     [rsp+1C0h+var_170], r13d
0x1801a905e  mov     [rsp+1C0h+var_16C], ax
0x1801a9063  test    r12, r12
0x1801a9066  jz      loc_1801A9394
0x1801a906c  lea     ecx, [rbx+5]
0x1801a906f  mov     rax, r12
0x1801a9072  mov     [rax], r13b
0x1801a9075  inc     rax
0x1801a9078  sub     rcx, 1
0x1801a907c  jnz     short loc_1801A9072
0x1801a907e  mov     eax, 784h
0x1801a9083  mov     [rsp+1C0h+var_170], r13d
0x1801a9088  mov     rcx, r15; lpRootPathName
0x1801a908b  mov     [rsp+1C0h+var_16C], ax
0x1801a9090  call    ?SxIsRemovableFatVolume@@YAHPEBG@Z; SxIsRemovableFatVolume(ushort const *)
0x1801a9095  test    eax, eax
0x1801a9097  jz      loc_1801A9231
0x1801a909d  mov     [rsp+1C0h+var_180], 2
0x1801a90a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster> `wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl(void)'::`2'::impl
0x1801a90ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(void)
0x1801a90b1  test    al, al
0x1801a90b3  jz      short loc_1801A90CE
0x1801a90b5  mov     edx, [rsp+1C0h+var_180]
0x1801a90b9  lea     eax, [rdx-9]
0x1801a90bc  cmp     eax, 1
0x1801a90bf  ja      short loc_1801A90CE
0x1801a90c1  mov     ecx, [rdi+8]
0x1801a90c4  lea     r8, [rsp+1C0h+var_180]
0x1801a90c9  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x1801a90ce  lea     rax, [rbp+0C0h+hKey]
0x1801a90d2  mov     r9d, 20019h; samDesired
0x1801a90d8  xor     r8d, r8d; ulOptions
0x1801a90db  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1801a90e0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfrg"
0x1801a90e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a90ee  call    cs:__imp_RegOpenKeyExW
0x1801a90f4  test    eax, eax
0x1801a90f6  jnz     short loc_1801A913B
0x1801a90f8  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1801a90fc  lea     r8, [rsp+1C0h+var_178]; unsigned int *
0x1801a9101  lea     rdx, aMatchingslabop; "MatchingSlabOptimization"
0x1801a9108  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1801a910d  test    eax, eax
0x1801a910f  jnz     short loc_1801A9131
0x1801a9111  cmp     [rsp+1C0h+var_178], 1
0x1801a9116  jnz     short loc_1801A9131
0x1801a9118  mov     edx, [rsp+1C0h+var_180]
0x1801a911c  lea     eax, [rdx-9]
0x1801a911f  cmp     eax, 1
0x1801a9122  ja      short loc_1801A9131
0x1801a9124  mov     ecx, [rdi+8]
0x1801a9127  lea     r8, [rsp+1C0h+var_180]
0x1801a912c  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x1801a9131  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1801a9135  call    cs:__imp_RegCloseKey
0x1801a913b  mov     eax, [rsp+1C0h+var_180]
0x1801a913f  cmp     eax, 6
0x1801a9142  jz      short loc_1801A914D
0x1801a9144  cmp     eax, 0Ch
0x1801a9147  jnz     loc_1801A92F2
0x1801a914d  mov     esi, 4000h
0x1801a9152  mov     ecx, esi; cb
0x1801a9154  call    cs:__imp_CoTaskMemAlloc
0x1801a915a  mov     r14, rax
0x1801a915d  mov     ecx, 7E0h
0x1801a9162  test    rax, rax
0x1801a9165  jz      loc_1801A9385
0x1801a916b  mov     [rsp+1C0h+var_16C], cx
0x1801a9170  mov     r8d, esi; Size
0x1801a9173  mov     rcx, rax; void *
0x1801a9176  mov     [rsp+1C0h+var_170], r13d
0x1801a917b  xor     edx, edx; Val
0x1801a917d  call    memset_0
0x1801a9182  mov     rdx, r15; unsigned __int16 *
0x1801a9185  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801a9189  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801a918e  mov     [rsp+1C0h+var_170], eax
0x1801a9192  test    eax, eax
0x1801a9194  mov     eax, 7E3h
0x1801a9199  js      loc_1801A93A1
0x1801a919f  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801a91a3  mov     [rsp+1C0h+var_16C], ax
0x1801a91a8  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801a91ad  mov     rcx, [rbp+0C0h+lpFileName]; lpFileName
0x1801a91b1  mov     eax, 3
0x1801a91b6  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x1801a91bb  mov     r8d, eax; dwShareMode
0x1801a91be  mov     [rsp+1C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x1801a91c6  xor     r9d, r9d; lpSecurityAttributes
0x1801a91c9  mov     edx, 0C0000000h; dwDesiredAccess
0x1801a91ce  mov     dword ptr [rsp+1C0h+phkResult], eax; dwCreationDisposition
0x1801a91d2  call    cs:__imp_CreateFileW
0x1801a91d8  mov     rbx, rax
0x1801a91db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a91df  jz      loc_1801A92EE
0x1801a91e5  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x1801a91ea  lea     rax, [rbp+0C0h+BytesReturned]
0x1801a91ee  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1801a91f3  xor     r9d, r9d; nInBufferSize
0x1801a91f6  mov     [rsp+1C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1801a91fa  xor     r8d, r8d; lpInBuffer
0x1801a91fd  mov     edx, 902ECh; dwIoControlCode
0x1801a9202  mov     [rsp+1C0h+phkResult], r14; lpOutBuffer
0x1801a9207  mov     rcx, rbx; hDevice
0x1801a920a  call    cs:__imp_DeviceIoControl
0x1801a9210  test    eax, eax
0x1801a9212  jz      loc_1801A92EE
0x1801a9218  cmp     dword ptr [r14+0Ch], 1
0x1801a921d  jbe     loc_1801A92EE
0x1801a9223  mov     eax, 0Bh
0x1801a9228  mov     [rsp+1C0h+var_180], eax
0x1801a922c  jmp     loc_1801A92F2
0x1801a9231  lea     rdx, [rbp+0C0h+var_130]; struct _VOLUME_DISK_EXTENTS **
0x1801a9235  mov     rcx, r15; unsigned __int16 *
0x1801a9238  call    ?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z; SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)
0x1801a923d  mov     rdi, [rbp+0C0h+var_130]
0x1801a9241  test    eax, eax
0x1801a9243  mov     [rsp+1C0h+var_170], eax
0x1801a9247  mov     eax, 79Bh
0x1801a924c  js      loc_1801A93A1
0x1801a9252  mov     [rsp+1C0h+var_16C], ax
0x1801a9257  mov     ecx, [rdi+8]; unsigned int
0x1801a925a  cmp     ecx, 0FFFFFFFFh
0x1801a925d  jnz     short loc_1801A9271
0x1801a925f  mov     [rsp+1C0h+var_170], 8900000Dh
0x1801a9267  mov     eax, 7A0h
0x1801a926c  jmp     loc_1801A93A1
0x1801a9271  lea     rdx, [rsp+1C0h+var_180]; enum DF_DEVICE_TYPE *
0x1801a9276  call    ?SxQueryDeviceType@@YAJKPEAW4DF_DEVICE_TYPE@@@Z; SxQueryDeviceType(ulong,DF_DEVICE_TYPE *)
0x1801a927b  mov     [rsp+1C0h+var_170], eax
0x1801a927f  test    eax, eax
0x1801a9281  mov     eax, 7A3h
0x1801a9286  js      loc_1801A93A1
0x1801a928c  mov     [rsp+1C0h+var_16C], ax
0x1801a9291  cmp     dword ptr [rdi], 1
0x1801a9294  jbe     loc_1801A90A5
0x1801a929a  mov     esi, r13d
0x1801a929d  mov     eax, esi
0x1801a929f  lea     rcx, [rax+rax*2]
0x1801a92a3  mov     ecx, [rdi+rcx*8+8]; unsigned int
0x1801a92a7  cmp     ecx, 0FFFFFFFFh
0x1801a92aa  jz      short loc_1801A92DC
0x1801a92ac  lea     rdx, [rsp+1C0h+var_17C]; int *
0x1801a92b1  call    ?SxQueryDeviceDefragAppropriate@@YAJKPEAH@Z; SxQueryDeviceDefragAppropriate(ulong,int *)
0x1801a92b6  test    eax, eax
0x1801a92b8  js      short loc_1801A92C7
0x1801a92ba  cmp     [rsp+1C0h+var_17C], r13d
0x1801a92bf  jnz     short loc_1801A92C7
0x1801a92c1  inc     esi
0x1801a92c3  cmp     esi, [rdi]
0x1801a92c5  jb      short loc_1801A929D
0x1801a92c7  cmp     esi, [rdi]
0x1801a92c9  jnz     loc_1801A90A5
0x1801a92cf  mov     [rsp+1C0h+var_180], 3
0x1801a92d7  jmp     loc_1801A90A5
0x1801a92dc  mov     [rsp+1C0h+var_170], 8900000Dh
0x1801a92e4  mov     eax, 7B1h
0x1801a92e9  jmp     loc_1801A93A1
0x1801a92ee  mov     eax, [rsp+1C0h+var_180]
0x1801a92f2  cmp     eax, 3
0x1801a92f5  jz      short loc_1801A92FC
0x1801a92f7  cmp     eax, 0Ch
0x1801a92fa  jnz     short loc_1801A9370
0x1801a92fc  mov     dword ptr [rsp+1C0h+lpOverlapped], 64h ; 'd'; nFileSystemNameSize
0x1801a9304  lea     rax, [rbp+0C0h+FileSystemNameBuffer]
0x1801a9308  mov     [rsp+1C0h+hTemplateFile], rax; lpFileSystemNameBuffer
0x1801a930d  xor     r9d, r9d; lpVolumeSerialNumber
0x1801a9310  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], r13; lpFileSystemFlags
0x1801a9315  xor     r8d, r8d; nVolumeNameSize
0x1801a9318  xor     edx, edx; lpVolumeNameBuffer
0x1801a931a  mov     [rsp+1C0h+phkResult], r13; lpMaximumComponentLength
0x1801a931f  mov     rcx, r15; lpRootPathName
0x1801a9322  call    cs:__imp_GetVolumeInformationW
0x1801a9328  test    eax, eax
0x1801a932a  jz      short loc_1801A936C
0x1801a932c  lea     rdx, aNtfs_0; "NTFS"
0x1801a9333  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]
0x1801a9337  call    cs:__imp__o__wcsicmp
0x1801a933d  test    eax, eax
0x1801a933f  jz      short loc_1801A9356
0x1801a9341  lea     rdx, aRefs; "REFS"
0x1801a9348  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]
0x1801a934c  call    cs:__imp__o__wcsicmp
0x1801a9352  test    eax, eax
0x1801a9354  jnz     short loc_1801A936C
0x1801a9356  cmp     [rsp+1C0h+var_180], 3
0x1801a935b  mov     eax, 0Dh
0x1801a9360  lea     ecx, [rax-9]
0x1801a9363  cmovz   eax, ecx
0x1801a9366  mov     [rsp+1C0h+var_180], eax
0x1801a936a  jmp     short loc_1801A9370
0x1801a936c  mov     eax, [rsp+1C0h+var_180]
0x1801a9370  mov     [r12], eax
0x1801a9374  mov     eax, 821h
0x1801a9379  mov     [rsp+1C0h+var_16C], ax
0x1801a937e  mov     [rsp+1C0h+var_170], r13d
0x1801a9383  jmp     short loc_1801A93A6
0x1801a9385  mov     [rsp+1C0h+var_170], 8007000Eh
0x1801a938d  mov     [rsp+1C0h+var_16A], cx
0x1801a9392  jmp     short loc_1801A93A6
0x1801a9394  mov     eax, 784h
0x1801a9399  mov     [rsp+1C0h+var_170], 80070057h
0x1801a93a1  mov     [rsp+1C0h+var_16A], ax
0x1801a93a6  mov     rcx, rdi; pv
0x1801a93a9  call    cs:__imp_CoTaskMemFree
0x1801a93af  mov     rcx, r14; pv
0x1801a93b2  call    cs:__imp_CoTaskMemFree
0x1801a93b8  mov     edi, [rsp+1C0h+var_170]
0x1801a93bc  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801a93c0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1801a93c5  lea     rcx, [rbx-1]
0x1801a93c9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801a93cd  ja      short loc_1801A93D8
0x1801a93cf  mov     rcx, rbx; hObject
0x1801a93d2  call    cs:__imp_CloseHandle
0x1801a93d8  lea     rcx, [rsp+1C0h+var_170]; this
0x1801a93dd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801a93e2  mov     eax, edi
0x1801a93e4  mov     rcx, [rbp+0C0h+var_40]
0x1801a93eb  xor     rcx, rsp; StackCookie
0x1801a93ee  call    __security_check_cookie
0x1801a93f3  mov     rbx, [rsp+1C0h+arg_10]
0x1801a93fb  add     rsp, 190h
0x1801a9402  pop     r15
0x1801a9404  pop     r14
0x1801a9406  pop     r13
0x1801a9408  pop     r12
0x1801a940a  pop     rdi
0x1801a940b  pop     rsi
0x1801a940c  pop     rbp
0x1801a940d  retn
```
