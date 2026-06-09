# CopyFileToBuffer(ushort const *,CBuffer &)

- ea: `0x18002484c`
- end: `0x1800249a8`
- name: `?CopyFileToBuffer@@YAJPEBGAEAVCBuffer@@@Z`
- size: `348`
- prototype: `int(const unsigned __int16 *, struct CBuffer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002a30`

## callees

- `0x180003ee0`
- `0x180014b00`
- `0x18002484c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002495a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002495a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002498f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002498f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180024950`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180024950`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800248c7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800248c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024881`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024881`

## pseudocode

```c
__int64 __fastcall CopyFileToBuffer(const unsigned __int16 *a1, DWORD *a2)
{
  DWORD v3; // esi
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD LowPart; // ebx
  unsigned __int8 *v7; // rax
  LPOVERLAPPED lpOverlapped; // rdx
  __int64 result; // rax
  ulong pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  ulong LastError; // [rsp+44h] [rbp-34h] BYREF
  ulong v12; // [rsp+48h] [rbp-30h] BYREF
  ulong v13; // [rsp+4Ch] [rbp-2Ch] BYREF
  ulong v14; // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h]
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v15 = -1;
  try
  {
    FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0, 0);
    v5 = FileW;
    v15 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( FileSize.HighPart )
    {
      v12 = -2146435068;
      throw &v12;
    }
    LowPart = FileSize.LowPart;
    NumberOfBytesRead = FileSize.LowPart;
    CBuffer::Presize((CBuffer *)a2, FileSize.LowPart, 0);
    a2[4] = LowPart;
    v7 = CBuffer::Access((CBuffer *)a2, 0);
    if ( !ReadFile(v5, v7, a2[5], &NumberOfBytesRead, lpOverlapped) )
    {
      v13 = GetLastError();
      throw &v13;
    }
  }
  catch ( ulong v14 )
  {
    NumberOfBytesRead = v14;
    goto LABEL_10;
  }
  catch ( ... )
  {
    NumberOfBytesRead = -2146435068;
LABEL_10:
    v5 = (void *)v15;
    v3 = NumberOfBytesRead;
    if ( v15 != -1 )
      goto LABEL_11;
LABEL_12:
    result = v3;
  }
LABEL_11:
  CloseHandle(v5);
  goto LABEL_12;
}

```

## disassembly

```asm
0x18002484c  mov     rax, rsp
0x18002484f  mov     [rax+8], rbx
0x180024853  push    rsi
0x180024854  push    rdi
0x180024855  push    r14
0x180024857  sub     rsp, 60h
0x18002485b  mov     r14, rdx
0x18002485e  xor     esi, esi
0x180024860  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFFh
0x180024868  mov     [rax-48h], rsi
0x18002486c  mov     [rax-50h], esi
0x18002486f  mov     dword ptr [rax-58h], 3
0x180024876  xor     r9d, r9d; lpSecurityAttributes
0x180024879  xor     r8d, r8d; dwShareMode
0x18002487c  mov     edx, 80000000h; dwDesiredAccess
0x180024881  call    cs:__imp_CreateFileW
0x180024887  mov     rdi, rax
0x18002488a  mov     [rsp+78h+var_20], rax
0x18002488f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024893  jnz     short loc_1800248B0
0x180024895  call    cs:__imp_GetLastError
0x18002489b  mov     [rsp+78h+pExceptionObject], eax
0x18002489f  lea     rdx, _TI1K; pThrowInfo
0x1800248a6  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800248ab  call    _CxxThrowException_0
0x1800248b0  mov     qword ptr [rsp+78h+FileSize], 0
0x1800248bc  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x1800248c4  mov     rcx, rdi; hFile
0x1800248c7  call    cs:__imp_GetFileSizeEx
0x1800248cd  test    eax, eax
0x1800248cf  jnz     short loc_1800248EC
0x1800248d1  call    cs:__imp_GetLastError
0x1800248d7  mov     [rsp+78h+var_34], eax
0x1800248db  lea     rdx, _TI1K; pThrowInfo
0x1800248e2  lea     rcx, [rsp+78h+var_34]; pExceptionObject
0x1800248e7  call    _CxxThrowException_0
0x1800248ec  cmp     dword ptr [rsp+78h+FileSize+4], 0
0x1800248f4  jz      short loc_18002490F
0x1800248f6  mov     [rsp+78h+var_30], 80100004h
0x1800248fe  lea     rdx, _TI1K; pThrowInfo
0x180024905  lea     rcx, [rsp+78h+var_30]; pExceptionObject
0x18002490a  call    _CxxThrowException_0
0x18002490f  mov     rbx, qword ptr [rsp+78h+FileSize]
0x180024917  mov     [rsp+78h+NumberOfBytesRead], ebx
0x18002491e  xor     r8d, r8d; int
0x180024921  mov     edx, ebx; unsigned int
0x180024923  mov     rcx, r14; this
0x180024926  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18002492b  mov     [r14+10h], ebx
0x18002492f  xor     edx, edx; unsigned int
0x180024931  mov     rcx, r14; this
0x180024934  call    ?Access@CBuffer@@QEBAPEAEK@Z; CBuffer::Access(ulong)
0x180024939  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x18002493e  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180024946  mov     r8d, [r14+14h]; nNumberOfBytesToRead
0x18002494a  mov     rdx, rax; lpBuffer
0x18002494d  mov     rcx, rdi; hFile
0x180024950  call    cs:__imp_ReadFile
0x180024956  test    eax, eax
0x180024958  jnz     short loc_180024976
0x18002495a  call    cs:__imp_GetLastError
0x180024960  mov     [rsp+78h+var_2C], eax
0x180024964  lea     rdx, _TI1K; pThrowInfo
0x18002496b  lea     rcx, [rsp+78h+var_2C]; pExceptionObject
0x180024970  call    _CxxThrowException_0
0x180024976  jmp     short loc_18002498C
0x180024978  jmp     short $+2
0x18002497a  mov     rdi, [rsp+78h+var_20]
0x18002497f  mov     esi, [rsp+78h+NumberOfBytesRead]
0x180024986  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002498a  jz      short loc_180024995
0x18002498c  mov     rcx, rdi; hObject
0x18002498f  call    cs:__imp_CloseHandle
0x180024995  mov     eax, esi
0x180024997  mov     rbx, [rsp+78h+arg_0]
0x18002499f  add     rsp, 60h
0x1800249a3  pop     r14
0x1800249a5  pop     rdi
0x1800249a6  pop     rsi
0x1800249a7  retn
```
