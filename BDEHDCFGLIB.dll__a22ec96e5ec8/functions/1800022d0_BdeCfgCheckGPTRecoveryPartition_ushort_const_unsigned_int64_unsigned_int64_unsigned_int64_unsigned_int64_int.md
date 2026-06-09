# BdeCfgCheckGPTRecoveryPartition(ushort const *,unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *,int *)

- ea: `0x1800022d0`
- end: `0x180002453`
- name: `?BdeCfgCheckGPTRecoveryPartition@@YAJPEBG_K1PEA_K2PEAH@Z`
- size: `387`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int64, unsigned __int64, unsigned __int64 *, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003a10`

## callees

- `0x1800022d0`
- `0x1800081bc`
- `0x180013576`
- `0x18001358e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000235d`
- `KERNEL32!GetLastError` at `0x1800023e3`
- `KERNEL32!GetLastError` at `0x18000235d`
- `KERNEL32!GetLastError` at `0x1800023e3`
- `KERNEL32!CreateFileW` at `0x18000234e`
- `KERNEL32!CreateFileW` at `0x18000234e`
- `KERNEL32!DeviceIoControl` at `0x1800023d9`
- `KERNEL32!DeviceIoControl` at `0x1800023d9`
- `KERNEL32!CloseHandle` at `0x180002434`
- `KERNEL32!CloseHandle` at `0x180002434`

## pseudocode

```c
__int64 __fastcall BdeCfgCheckGPTRecoveryPartition(
        LPCWSTR lpFileName,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        int *a6)
{
  int *v10; // rdi
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v13; // ebx
  signed int v14; // eax
  _DWORD OutBuffer[8]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE Buf1[168]; // [rsp+60h] [rbp-A8h] BYREF
  DWORD BytesReturned; // [rsp+110h] [rbp+8h] BYREF

  BytesReturned = 0;
  memset_0(OutBuffer, 0, 0x90u);
  if ( lpFileName && (v10 = a6) != 0 )
  {
    *a6 = 0;
    FileW = CreateFileW(lpFileName, 1u, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v13 = BdeCfgpCheckVolumeNtfsDataForMerge(FileW, a2, a3, a4, a5);
      if ( v13 >= 0 )
      {
        if ( DeviceIoControl(FileW, 0x70048u, 0, 0, OutBuffer, 0x90u, &BytesReturned, 0) )
        {
          if ( OutBuffer[0] == 1 )
          {
            *v10 = memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) == 0;
          }
          else if ( !OutBuffer[0] )
          {
            *v10 = Buf1[0] == 39;
          }
        }
        else
        {
          v14 = GetLastError();
          v13 = v14;
          if ( v14 > 0 )
            v13 = (unsigned __int16)v14 | 0x80070000;
        }
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800022d0  mov     rax, rsp
0x1800022d3  push    rbx
0x1800022d4  push    rbp
0x1800022d5  push    rsi
0x1800022d6  push    rdi
0x1800022d7  push    r14
0x1800022d9  push    r15
0x1800022db  sub     rsp, 0D8h
0x1800022e2  mov     r14, r8
0x1800022e5  mov     dword ptr [rax+8], 0
0x1800022ec  mov     r15, rdx
0x1800022ef  mov     rbx, rcx
0x1800022f2  xor     edx, edx; Val
0x1800022f4  lea     rcx, [rsp+108h+OutBuffer]; void *
0x1800022f9  mov     r8d, 90h; Size
0x1800022ff  mov     rbp, r9
0x180002302  call    memset_0
0x180002307  test    rbx, rbx
0x18000230a  jz      loc_18000243C
0x180002310  mov     rdi, [rsp+108h+arg_28]
0x180002318  test    rdi, rdi
0x18000231b  jz      loc_18000243C
0x180002321  xor     r9d, r9d; lpSecurityAttributes
0x180002324  mov     [rsp+108h+hTemplateFile], 0; hTemplateFile
0x18000232d  mov     [rsp+108h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180002335  mov     rcx, rbx; lpFileName
0x180002338  mov     dword ptr [rdi], 0
0x18000233e  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x180002346  lea     edx, [r9+1]; dwDesiredAccess
0x18000234a  lea     r8d, [r9+7]; dwShareMode
0x18000234e  call    cs:__imp_CreateFileW
0x180002354  mov     rsi, rax
0x180002357  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000235b  jnz     short loc_18000237B
0x18000235d  call    cs:__imp_GetLastError
0x180002363  mov     ebx, eax
0x180002365  test    eax, eax
0x180002367  jle     loc_180002441
0x18000236d  movzx   ebx, ax
0x180002370  or      ebx, 80070000h
0x180002376  jmp     loc_180002441
0x18000237b  mov     rax, [rsp+108h+arg_20]
0x180002383  mov     r9, rbp; unsigned __int64 *
0x180002386  mov     r8, r14; unsigned __int64
0x180002389  mov     qword ptr [rsp+108h+dwCreationDisposition], rax; unsigned __int64 *
0x18000238e  mov     rdx, r15; unsigned __int64
0x180002391  mov     rcx, rsi; void *
0x180002394  call    ?BdeCfgpCheckVolumeNtfsDataForMerge@@YAJPEAX_K1PEA_K2@Z; BdeCfgpCheckVolumeNtfsDataForMerge(void *,unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180002399  mov     ebx, eax
0x18000239b  test    eax, eax
0x18000239d  js      loc_180002431
0x1800023a3  mov     [rsp+108h+lpOverlapped], 0; lpOverlapped
0x1800023ac  lea     rax, [rsp+108h+BytesReturned]
0x1800023b4  mov     [rsp+108h+hTemplateFile], rax; lpBytesReturned
0x1800023b9  xor     r9d, r9d; nInBufferSize
0x1800023bc  lea     rax, [rsp+108h+OutBuffer]
0x1800023c1  mov     [rsp+108h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x1800023c9  xor     r8d, r8d; lpInBuffer
0x1800023cc  mov     qword ptr [rsp+108h+dwCreationDisposition], rax; lpOutBuffer
0x1800023d1  mov     edx, 70048h; dwIoControlCode
0x1800023d6  mov     rcx, rsi; hDevice
0x1800023d9  call    cs:__imp_DeviceIoControl
0x1800023df  test    eax, eax
0x1800023e1  jnz     short loc_1800023FA
0x1800023e3  call    cs:__imp_GetLastError
0x1800023e9  mov     ebx, eax
0x1800023eb  test    eax, eax
0x1800023ed  jle     short loc_180002431
0x1800023ef  movzx   ebx, ax
0x1800023f2  or      ebx, 80070000h
0x1800023f8  jmp     short loc_180002431
0x1800023fa  mov     eax, [rsp+108h+OutBuffer]
0x1800023fe  cmp     eax, 1
0x180002401  jnz     short loc_180002423
0x180002403  lea     r8d, [rax+0Fh]; Size
0x180002407  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18000240e  lea     rcx, [rsp+108h+Buf1]; Buf1
0x180002413  call    memcmp_0
0x180002418  xor     ecx, ecx
0x18000241a  test    eax, eax
0x18000241c  setz    cl
0x18000241f  mov     [rdi], ecx
0x180002421  jmp     short loc_180002431
0x180002423  test    eax, eax
0x180002425  jnz     short loc_180002431
0x180002427  cmp     [rsp+108h+Buf1], 27h ; '''
0x18000242c  setz    al
0x18000242f  mov     [rdi], eax
0x180002431  mov     rcx, rsi; hObject
0x180002434  call    cs:__imp_CloseHandle
0x18000243a  jmp     short loc_180002441
0x18000243c  mov     ebx, 80070057h
0x180002441  mov     eax, ebx
0x180002443  add     rsp, 0D8h
0x18000244a  pop     r15
0x18000244c  pop     r14
0x18000244e  pop     rdi
0x18000244f  pop     rsi
0x180002450  pop     rbp
0x180002451  pop     rbx
0x180002452  retn
```
