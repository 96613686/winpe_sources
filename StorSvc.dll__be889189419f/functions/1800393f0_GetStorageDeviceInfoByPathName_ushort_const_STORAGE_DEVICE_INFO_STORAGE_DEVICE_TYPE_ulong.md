# GetStorageDeviceInfoByPathName(ushort const *,_STORAGE_DEVICE_INFO *,_STORAGE_DEVICE_TYPE *,ulong *)

- ea: `0x1800393f0`
- end: `0x180039509`
- name: `?GetStorageDeviceInfoByPathName@@YAJPEBGPEAU_STORAGE_DEVICE_INFO@@PEAW4_STORAGE_DEVICE_TYPE@@PEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _STORAGE_DEVICE_INFO *, enum _STORAGE_DEVICE_TYPE *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180033118`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18001fea0`
- `0x180023d64`
- `0x180024638`
- `0x1800393f0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003943b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800394b8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003943b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800394b8`

## pseudocode

```c
__int64 __fastcall GetStorageDeviceInfoByPathName(
        const unsigned __int16 *a1,
        struct _STORAGE_DEVICE_INFO *a2,
        enum _STORAGE_DEVICE_TYPE *a3,
        unsigned int *a4)
{
  __int64 v6; // rcx
  int DriveNumberW; // r15d
  int StorageDeviceInfo; // ebx
  int v9; // edi
  unsigned int InstanceCount; // r12d
  unsigned int i; // ebp
  __int64 v12; // rcx
  int v13; // eax
  int v15; // [rsp+30h] [rbp-4A8h] BYREF
  WCHAR pszPath[558]; // [rsp+34h] [rbp-4A4h] BYREF

  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( a3 )
    *(_DWORD *)a3 = 2;
  if ( a4 )
    *a4 = 31;
  DriveNumberW = PathGetDriveNumberW(a1);
  if ( DriveNumberW >= 0 )
  {
    StorageDeviceInfo = 0;
    v9 = 0;
LABEL_8:
    if ( v9 < 2 )
    {
      StorageDeviceInfo = StorageService::CheckDeviceParameters(v6, v9);
      if ( StorageDeviceInfo >= 0 )
      {
        InstanceCount = StorageService::GetInstanceCount(&g_StorageService);
        for ( i = 0; ; ++i )
        {
          if ( i >= InstanceCount )
          {
            ++v9;
            goto LABEL_8;
          }
          memset_0(pszPath, 0, 0x454u);
          v15 = 1112;
          StorageDeviceInfo = StorageService::GetStorageDeviceInfo(v12, 0, v9, i, (__int64)&v15);
          if ( StorageDeviceInfo < 0 )
            return (unsigned int)StorageDeviceInfo;
          v13 = PathGetDriveNumberW(pszPath);
          if ( v13 < 0 )
            return (unsigned int)-2147024809;
          if ( DriveNumberW == v13 )
            break;
        }
        if ( a3 )
          *(_DWORD *)a3 = v9;
        if ( a4 )
          *a4 = i;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)StorageDeviceInfo;
}

```

## disassembly

```asm
0x1800393f0  push    rbx
0x1800393f2  push    rbp
0x1800393f3  push    rsi
0x1800393f4  push    rdi
0x1800393f5  push    r12
0x1800393f7  push    r14
0x1800393f9  push    r15
0x1800393fb  sub     rsp, 4A0h
0x180039402  mov     rax, cs:__security_cookie
0x180039409  xor     rax, rsp
0x18003940c  mov     [rsp+4D8h+var_48], rax
0x180039414  mov     rsi, r9
0x180039417  mov     r14, r8
0x18003941a  test    rcx, rcx
0x18003941d  jz      loc_1800394E0
0x180039423  test    r8, r8
0x180039426  jz      short loc_18003942F
0x180039428  mov     dword ptr [r8], 2
0x18003942f  test    rsi, rsi
0x180039432  jz      short loc_18003943B
0x180039434  mov     dword ptr [r9], 1Fh
0x18003943b  call    cs:__imp_PathGetDriveNumberW
0x180039441  mov     r15d, eax
0x180039444  test    eax, eax
0x180039446  js      loc_1800394E0
0x18003944c  xor     ebx, ebx
0x18003944e  xor     edi, edi
0x180039450  cmp     edi, 2
0x180039453  jge     loc_1800394E5
0x180039459  mov     edx, edi
0x18003945b  call    ?CheckDeviceParameters@StorageService@@IEBAJW4_STORAGE_DEVICE_TYPE@@@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE)
0x180039460  mov     ebx, eax
0x180039462  test    eax, eax
0x180039464  js      short loc_1800394E5
0x180039466  lea     rcx, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x18003946d  call    ?GetInstanceCount@StorageService@@IEAAKW4_STORAGE_DEVICE_TYPE@@@Z; StorageService::GetInstanceCount(_STORAGE_DEVICE_TYPE)
0x180039472  mov     r12d, eax
0x180039475  xor     ebp, ebp
0x180039477  cmp     ebp, r12d
0x18003947a  jnb     short loc_1800394CB
0x18003947c  xor     edx, edx; Val
0x18003947e  lea     rcx, [rsp+4D8h+pszPath]; void *
0x180039483  mov     r8d, 454h; Size
0x180039489  call    memset_0
0x18003948e  lea     rax, [rsp+4D8h+var_4A8]
0x180039493  mov     [rsp+4D8h+var_4A8], 458h
0x18003949b  mov     r9d, ebp
0x18003949e  mov     [rsp+4D8h+var_4B8], rax
0x1800394a3  mov     r8d, edi
0x1800394a6  xor     edx, edx
0x1800394a8  call    ?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z; StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)
0x1800394ad  mov     ebx, eax
0x1800394af  test    eax, eax
0x1800394b1  js      short loc_1800394E5
0x1800394b3  lea     rcx, [rsp+4D8h+pszPath]; pszPath
0x1800394b8  call    cs:__imp_PathGetDriveNumberW
0x1800394be  test    eax, eax
0x1800394c0  js      short loc_1800394E0
0x1800394c2  cmp     r15d, eax
0x1800394c5  jz      short loc_1800394CF
0x1800394c7  inc     ebp
0x1800394c9  jmp     short loc_180039477
0x1800394cb  inc     edi
0x1800394cd  jmp     short loc_180039450
0x1800394cf  test    r14, r14
0x1800394d2  jz      short loc_1800394D7
0x1800394d4  mov     [r14], edi
0x1800394d7  test    rsi, rsi
0x1800394da  jz      short loc_1800394E5
0x1800394dc  mov     [rsi], ebp
0x1800394de  jmp     short loc_1800394E5
0x1800394e0  mov     ebx, 80070057h
0x1800394e5  mov     eax, ebx
0x1800394e7  mov     rcx, [rsp+4D8h+var_48]
0x1800394ef  xor     rcx, rsp; StackCookie
0x1800394f2  call    __security_check_cookie
0x1800394f7  add     rsp, 4A0h
0x1800394fe  pop     r15
0x180039500  pop     r14
0x180039502  pop     r12
0x180039504  pop     rdi
0x180039505  pop     rsi
0x180039506  pop     rbp
0x180039507  pop     rbx
0x180039508  retn
```
