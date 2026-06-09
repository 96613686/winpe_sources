# StorageService::GenerateStorageId(_STORAGE_DEVICE_TYPE,ulong,uchar *,int)

- ea: `0x180022c28`
- end: `0x180022dd8`
- name: `?GenerateStorageId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAEH@Z`
- size: `432`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, service_task`

## callers

- `0x180024480`
- `0x180029c5c`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18000dd8c`
- `0x18001a0fc`
- `0x18001a70c`
- `0x18001b164`
- `0x180022c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022d7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022da7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cbb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180022cb1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180022cb1`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180022d62`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180022d62`

## pseudocode

```c
__int64 __fastcall StorageService::GenerateStorageId(__int64 a1, int a2, unsigned int a3, unsigned __int8 *a4, int a5)
{
  __int64 v5; // r14
  __int64 v7; // rbx
  int RandomNumber; // edi
  __int64 v10; // r14
  signed int LastError; // eax
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  const WCHAR *v14; // rcx
  __int64 Buf2; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Buf1; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = a3;
  v7 = a2;
  RandomNumber = 0;
  Buf1 = 0;
  Buf2 = 0;
  if ( !a5 || (RandomNumber = GenerateRandomNumber(8u, a4), RandomNumber >= 0) )
  {
    v10 = 1112 * v5;
    if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)(v10 + *(_QWORD *)(a1 + 8 * v7 + 40) + 4LL), szVolumeName, 0x104u) )
    {
      v12 = -1;
      do
        ++v12;
      while ( szVolumeName[v12] );
      v13 = 2 * v12 - 2;
      if ( v13 >= 0x208 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)szVolumeName + v13) = 0;
      if ( (int)GetStorageSerialNumber(szVolumeName, (unsigned __int8 *)&Buf1) < 0 || !memcmp_0(&Buf1, &Buf2, 8u) )
      {
        v14 = (const WCHAR *)(v10 + *(_QWORD *)(a1 + 8 * v7 + 40) + 4LL);
        LODWORD(Buf1) = 0;
        if ( !GetVolumeInformationW(v14, 0, 0, (LPDWORD)&Buf1, 0, 0, 0, 0) )
          GetLastHr();
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
      *(_QWORD *)(*(_QWORD *)(a1 + 8 * v7 + 40) + v10 + 548) = Buf1;
      *(_QWORD *)(*(_QWORD *)(a1 + 8 * v7 + 40) + v10 + 556) = *(_QWORD *)a4;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1624));
    }
    else
    {
      LastError = GetLastError();
      RandomNumber = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)RandomNumber;
}

```

## disassembly

```asm
0x180022c28  push    rbp
0x180022c2a  push    rbx
0x180022c2b  push    rsi
0x180022c2c  push    rdi
0x180022c2d  push    r12
0x180022c2f  push    r13
0x180022c31  push    r14
0x180022c33  push    r15
0x180022c35  lea     rbp, [rsp-178h]
0x180022c3d  sub     rsp, 278h
0x180022c44  mov     rax, cs:__security_cookie
0x180022c4b  xor     rax, rsp
0x180022c4e  mov     [rbp+1B0h+var_50], rax
0x180022c55  xor     r13d, r13d
0x180022c58  mov     r14d, r8d
0x180022c5b  mov     r12, r9
0x180022c5e  movsxd  rbx, edx
0x180022c61  mov     rsi, rcx
0x180022c64  mov     edi, r13d
0x180022c67  mov     [rsp+2B0h+Buf1], r13
0x180022c6c  mov     [rsp+2B0h+Buf2], r13
0x180022c71  cmp     [rbp+1B0h+arg_20], r13d
0x180022c78  jz      short loc_180022C90
0x180022c7a  mov     rdx, r9; unsigned __int8 *
0x180022c7d  lea     ecx, [r13+8]; cbBuffer
0x180022c81  call    ?GenerateRandomNumber@@YAJKPEAE@Z; GenerateRandomNumber(ulong,uchar *)
0x180022c86  mov     edi, eax
0x180022c88  test    eax, eax
0x180022c8a  js      loc_180022DAD
0x180022c90  mov     rcx, [rsi+rbx*8+28h]
0x180022c95  lea     rdx, [rsp+2B0h+szVolumeName]; lpszVolumeName
0x180022c9a  add     rcx, 4
0x180022c9e  mov     r8d, 104h; cchBufferLength
0x180022ca4  imul    r14, 458h
0x180022cab  mov     r15, rbx
0x180022cae  add     rcx, r14; lpszVolumeMountPoint
0x180022cb1  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180022cb7  test    eax, eax
0x180022cb9  jnz     short loc_180022CD9
0x180022cbb  call    cs:__imp_GetLastError
0x180022cc1  mov     edi, eax
0x180022cc3  test    eax, eax
0x180022cc5  jle     loc_180022DAD
0x180022ccb  movzx   edi, ax
0x180022cce  or      edi, 80070000h
0x180022cd4  jmp     loc_180022DAD
0x180022cd9  lea     rcx, [rsp+2B0h+szVolumeName]
0x180022cde  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022ce2  inc     rax
0x180022ce5  cmp     [rcx+rax*2], r13w
0x180022cea  jnz     short loc_180022CE2
0x180022cec  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180022cf4  cmp     rcx, 208h
0x180022cfb  jnb     loc_180022DD2
0x180022d01  mov     [rsp+rcx+2B0h+szVolumeName], r13w
0x180022d07  lea     rdx, [rsp+2B0h+Buf1]; unsigned __int8 *
0x180022d0c  lea     rcx, [rsp+2B0h+szVolumeName]; unsigned __int16 *
0x180022d11  call    ?GetStorageSerialNumber@@YAJPEBGPEAE@Z; GetStorageSerialNumber(ushort const *,uchar *)
0x180022d16  test    eax, eax
0x180022d18  js      short loc_180022D33
0x180022d1a  mov     r8d, 8; Size
0x180022d20  lea     rdx, [rsp+2B0h+Buf2]; Buf2
0x180022d25  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x180022d2a  call    memcmp_0
0x180022d2f  test    eax, eax
0x180022d31  jnz     short loc_180022D71
0x180022d33  mov     rcx, [rsi+rbx*8+28h]
0x180022d38  lea     r9, [rsp+2B0h+Buf1]; lpVolumeSerialNumber
0x180022d3d  mov     [rsp+2B0h+nFileSystemNameSize], r13d; nFileSystemNameSize
0x180022d42  add     rcx, 4
0x180022d46  mov     [rsp+2B0h+lpFileSystemNameBuffer], r13; lpFileSystemNameBuffer
0x180022d4b  add     rcx, r14; lpRootPathName
0x180022d4e  mov     [rsp+2B0h+lpFileSystemFlags], r13; lpFileSystemFlags
0x180022d53  xor     r8d, r8d; nVolumeNameSize
0x180022d56  xor     edx, edx; lpVolumeNameBuffer
0x180022d58  mov     dword ptr [rsp+2B0h+Buf1], r13d
0x180022d5d  mov     [rsp+2B0h+lpMaximumComponentLength], r13; lpMaximumComponentLength
0x180022d62  call    cs:__imp_GetVolumeInformationW
0x180022d68  test    eax, eax
0x180022d6a  jnz     short loc_180022D71
0x180022d6c  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180022d71  lea     rbx, [rsi+658h]
0x180022d78  mov     rcx, rbx; lpCriticalSection
0x180022d7b  call    cs:__imp_EnterCriticalSection
0x180022d81  mov     rdx, [rsi+r15*8+28h]
0x180022d86  mov     rcx, rbx; lpCriticalSection
0x180022d89  mov     rax, [rsp+2B0h+Buf1]
0x180022d8e  mov     [rdx+r14+224h], rax
0x180022d96  mov     rdx, [rsi+r15*8+28h]
0x180022d9b  mov     rax, [r12]
0x180022d9f  mov     [rdx+r14+22Ch], rax
0x180022da7  call    cs:__imp_LeaveCriticalSection
0x180022dad  mov     eax, edi
0x180022daf  mov     rcx, [rbp+1B0h+var_50]
0x180022db6  xor     rcx, rsp; StackCookie
0x180022db9  call    __security_check_cookie
0x180022dbe  add     rsp, 278h
0x180022dc5  pop     r15
0x180022dc7  pop     r14
0x180022dc9  pop     r13
0x180022dcb  pop     r12
0x180022dcd  pop     rdi
0x180022dce  pop     rsi
0x180022dcf  pop     rbx
0x180022dd0  pop     rbp
0x180022dd1  retn
0x180022dd2  call    __report_rangecheckfailure
```
