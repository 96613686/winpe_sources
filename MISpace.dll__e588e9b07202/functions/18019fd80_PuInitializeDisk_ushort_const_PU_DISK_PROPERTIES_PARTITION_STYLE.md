# PuInitializeDisk(ushort const *,PU_DISK_PROPERTIES *,_PARTITION_STYLE)

- ea: `0x18019fd80`
- end: `0x18019ffa2`
- name: `?PuInitializeDisk@@YAJPEBGPEAVPU_DISK_PROPERTIES@@W4_PARTITION_STYLE@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct PU_DISK_PROPERTIES *, enum _PARTITION_STYLE)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180112d78`

## callees

- `0x180195a90`
- `0x180198120`
- `0x1801983e0`
- `0x18019fd80`
- `0x1801a0870`
- `0x1801a0df0`
- `0x1801a4388`
- `0x1801a4a40`
- `0x1801a4b30`
- `0x1801a56ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fea5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019fda9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019ff04`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019fda9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019ff04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ff8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ff8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019fdff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019fdff`

## string_xrefs

- `0x18019fe2a`: `CreateFile`
- `0x18019fe81`: `PuCreateDisk`
- `0x18019fee3`: `PuWriteBootCode`
- `0x18019febb`: `PuCreateMSRPartition`

## pseudocode

```c
__int64 __fastcall PuInitializeDisk(LPCWSTR lpFileName, struct PU_DISK_PROPERTIES *a2, unsigned int a3)
{
  __int64 FileW; // rsi
  signed int v7; // ebx
  const char *v8; // rdi
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  int v12; // eax
  int v13; // ecx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-58h] BYREF
  LARGE_INTEGER v16; // [rsp+48h] [rbp-50h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]

  FileW = -1;
  PU_TIMER::PU_TIMER((PU_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)a2 + 80) || *((_DWORD *)a2 + 55) != 2 )
  {
    v7 = -2147220992;
    v8 = "Not an unallocated disk";
  }
  else if ( a3 <= 1 )
  {
    v7 = 0;
    FileW = (__int64)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
      goto LABEL_41;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "CreateFile";
    }
    else
    {
LABEL_41:
      if ( (unsigned int)PuPerformBandManagement(a2) && (v7 = ActivateBandCapability((void *)FileW), v7 < 0) )
      {
        v8 = "ActivateBandCapability";
      }
      else
      {
        if ( (unsigned int)PuCreateDisk((HANDLE)FileW, (enum _PARTITION_STYLE)a3) )
          goto LABEL_23;
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 >= 0 )
        {
LABEL_23:
          if ( a3 != 1 || (unsigned int)PuIsWinPE() || (unsigned int)PuCreateMSRPartition((HANDLE)FileW) )
            goto LABEL_25;
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          if ( v7 >= 0 )
          {
LABEL_25:
            v8 = 0;
            v12 = PuWriteBootCode((HANDLE)FileW, a2);
            if ( v12 )
            {
              if ( v12 > 0 )
                v7 = (unsigned __int16)v12 | 0x80070000;
              else
                v7 = v12;
              v8 = "PuWriteBootCode";
            }
          }
          else
          {
            v8 = "PuCreateMSRPartition";
          }
        }
        else
        {
          v8 = "PuCreateDisk";
        }
      }
    }
  }
  else
  {
    v7 = -2147220991;
    v8 = "Invalid partition style";
  }
  QueryPerformanceCounter(&v16);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 1) != 0 )
      McTemplateU0sqqsd_EventWriteTransfer(
        v13,
        (unsigned int)InitializeDiskFailed,
        (unsigned int)"PuInitializeDisk",
        *((_DWORD *)a2 + 15),
        a3,
        (__int64)v8,
        v7);
  }
  else if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 2) != 0 )
  {
    McTemplateU0sqqx_EventWriteTransfer(
      v13,
      (unsigned int)InitializeDiskSucceeded,
      (unsigned int)"PuInitializeDisk",
      *((_DWORD *)a2 + 15),
      a3,
      1000000 * (v16.QuadPart - PerformanceCount.QuadPart) / v17);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18019fd80  push    rbx
0x18019fd82  push    rbp
0x18019fd83  push    rsi
0x18019fd84  push    rdi
0x18019fd85  push    r12
0x18019fd87  push    r14
0x18019fd89  sub     rsp, 68h
0x18019fd8d  mov     rdi, rcx
0x18019fd90  mov     r14d, r8d
0x18019fd93  lea     rcx, [rsp+98h+PerformanceCount]; this
0x18019fd98  mov     rbp, rdx
0x18019fd9b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18019fd9f  call    ??0PU_TIMER@@QEAA@XZ; PU_TIMER::PU_TIMER(void)
0x18019fda4  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x18019fda9  call    cs:__imp_QueryPerformanceCounter
0x18019fdaf  cmp     dword ptr [rbp+140h], 0
0x18019fdb6  jnz     loc_18019FEF3
0x18019fdbc  cmp     dword ptr [rbp+0DCh], 2
0x18019fdc3  jnz     loc_18019FEF3
0x18019fdc9  cmp     r14d, 1
0x18019fdcd  jbe     short loc_18019FDE0
0x18019fdcf  mov     ebx, 80040201h
0x18019fdd4  lea     rdi, aInvalidPartiti; "Invalid partition style"
0x18019fddb  jmp     loc_18019FEFF
0x18019fde0  xor     ebx, ebx
0x18019fde2  xor     r9d, r9d; lpSecurityAttributes
0x18019fde5  mov     [rsp+98h+hTemplateFile], rbx; hTemplateFile
0x18019fdea  mov     edx, 0C0000000h; dwDesiredAccess
0x18019fdef  mov     [rsp+98h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18019fdf3  mov     rcx, rdi; lpFileName
0x18019fdf6  lea     r8d, [rbx+3]; dwShareMode
0x18019fdfa  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x18019fdff  call    cs:__imp_CreateFileW
0x18019fe05  mov     rsi, rax
0x18019fe08  mov     r12d, 80070000h
0x18019fe0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019fe12  jnz     short loc_18019FE36
0x18019fe14  call    cs:__imp_GetLastError
0x18019fe1a  mov     ebx, eax
0x18019fe1c  test    eax, eax
0x18019fe1e  jle     short loc_18019FE26
0x18019fe20  movzx   ebx, ax
0x18019fe23  or      ebx, r12d
0x18019fe26  test    ebx, ebx
0x18019fe28  jns     short loc_18019FE36
0x18019fe2a  lea     rdi, aCreatefile; "CreateFile"
0x18019fe31  jmp     loc_18019FEFF
0x18019fe36  mov     rcx, rbp; struct PU_DISK_PROPERTIES *
0x18019fe39  call    ?PuPerformBandManagement@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuPerformBandManagement(PU_DISK_PROPERTIES *)
0x18019fe3e  test    eax, eax
0x18019fe40  jz      short loc_18019FE5C
0x18019fe42  mov     rcx, rsi; void *
0x18019fe45  call    ?ActivateBandCapability@@YAJPEAX@Z; ActivateBandCapability(void *)
0x18019fe4a  mov     ebx, eax
0x18019fe4c  test    eax, eax
0x18019fe4e  jns     short loc_18019FE5C
0x18019fe50  lea     rdi, aActivatebandca; "ActivateBandCapability"
0x18019fe57  jmp     loc_18019FEFF
0x18019fe5c  mov     edx, r14d; enum _PARTITION_STYLE
0x18019fe5f  mov     rcx, rsi; hDevice
0x18019fe62  call    ?PuCreateDisk@@YAHPEAXW4_PARTITION_STYLE@@@Z; PuCreateDisk(void *,_PARTITION_STYLE)
0x18019fe67  test    eax, eax
0x18019fe69  jnz     short loc_18019FE8A
0x18019fe6b  call    cs:__imp_GetLastError
0x18019fe71  mov     ebx, eax
0x18019fe73  test    eax, eax
0x18019fe75  jle     short loc_18019FE7D
0x18019fe77  movzx   ebx, ax
0x18019fe7a  or      ebx, r12d
0x18019fe7d  test    ebx, ebx
0x18019fe7f  jns     short loc_18019FE8A
0x18019fe81  lea     rdi, aPucreatedisk; "PuCreateDisk"
0x18019fe88  jmp     short loc_18019FEFF
0x18019fe8a  cmp     r14d, 1
0x18019fe8e  jnz     short loc_18019FEC4
0x18019fe90  call    ?PuIsWinPE@@YAHXZ; PuIsWinPE(void)
0x18019fe95  test    eax, eax
0x18019fe97  jnz     short loc_18019FEC4
0x18019fe99  mov     rcx, rsi; hDevice
0x18019fe9c  call    ?PuCreateMSRPartition@@YAHPEAX@Z; PuCreateMSRPartition(void *)
0x18019fea1  test    eax, eax
0x18019fea3  jnz     short loc_18019FEC4
0x18019fea5  call    cs:__imp_GetLastError
0x18019feab  mov     ebx, eax
0x18019fead  test    eax, eax
0x18019feaf  jle     short loc_18019FEB7
0x18019feb1  movzx   ebx, ax
0x18019feb4  or      ebx, r12d
0x18019feb7  test    ebx, ebx
0x18019feb9  jns     short loc_18019FEC4
0x18019febb  lea     rdi, aPucreatemsrpar; "PuCreateMSRPartition"
0x18019fec2  jmp     short loc_18019FEFF
0x18019fec4  mov     rdx, rbp; struct PU_DISK_PROPERTIES *
0x18019fec7  mov     rcx, rsi; hFile
0x18019feca  xor     edi, edi
0x18019fecc  call    ?PuWriteBootCode@@YAKPEAXPEAVPU_DISK_PROPERTIES@@@Z; PuWriteBootCode(void *,PU_DISK_PROPERTIES *)
0x18019fed1  test    eax, eax
0x18019fed3  jz      short loc_18019FEFF
0x18019fed5  jg      short loc_18019FEDB
0x18019fed7  mov     ebx, eax
0x18019fed9  jmp     short loc_18019FEE1
0x18019fedb  movzx   ebx, ax
0x18019fede  or      ebx, r12d
0x18019fee1  test    ebx, ebx
0x18019fee3  lea     rax, aPuwritebootcod; "PuWriteBootCode"
0x18019feea  cmovns  rax, rdi
0x18019feee  mov     rdi, rax
0x18019fef1  jmp     short loc_18019FEFF
0x18019fef3  mov     ebx, 80040200h
0x18019fef8  lea     rdi, aNotAnUnallocat; "Not an unallocated disk"
0x18019feff  lea     rcx, [rsp+98h+var_50]; lpPerformanceCount
0x18019ff04  call    cs:__imp_QueryPerformanceCounter
0x18019ff0a  test    ebx, ebx
0x18019ff0c  js      short loc_18019FF52
0x18019ff0e  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 2
0x18019ff15  jz      short loc_18019FF80
0x18019ff17  mov     rax, qword ptr [rsp+98h+var_50]
0x18019ff1c  lea     r8, aPuinitializedi; "PuInitializeDisk"
0x18019ff23  sub     rax, qword ptr [rsp+98h+PerformanceCount]
0x18019ff28  mov     r9d, [rbp+3Ch]
0x18019ff2c  imul    rax, 0F4240h
0x18019ff33  cqo
0x18019ff35  idiv    [rsp+98h+var_48]
0x18019ff3a  lea     rdx, InitializeDiskSucceeded
0x18019ff41  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax
0x18019ff46  mov     [rsp+98h+dwCreationDisposition], r14d
0x18019ff4b  call    McTemplateU0sqqx_EventWriteTransfer
0x18019ff50  jmp     short loc_18019FF80
0x18019ff52  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 1
0x18019ff59  jz      short loc_18019FF80
0x18019ff5b  mov     r9d, [rbp+3Ch]
0x18019ff5f  lea     r8, aPuinitializedi; "PuInitializeDisk"
0x18019ff66  mov     dword ptr [rsp+98h+hTemplateFile], ebx
0x18019ff6a  lea     rdx, InitializeDiskFailed
0x18019ff71  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi
0x18019ff76  mov     [rsp+98h+dwCreationDisposition], r14d
0x18019ff7b  call    McTemplateU0sqqsd_EventWriteTransfer
0x18019ff80  lea     rax, [rsi-1]
0x18019ff84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18019ff88  ja      short loc_18019FF93
0x18019ff8a  mov     rcx, rsi; hObject
0x18019ff8d  call    cs:__imp_CloseHandle
0x18019ff93  mov     eax, ebx
0x18019ff95  add     rsp, 68h
0x18019ff99  pop     r14
0x18019ff9b  pop     r12
0x18019ff9d  pop     rdi
0x18019ff9e  pop     rsi
0x18019ff9f  pop     rbp
0x18019ffa0  pop     rbx
0x18019ffa1  retn
```
