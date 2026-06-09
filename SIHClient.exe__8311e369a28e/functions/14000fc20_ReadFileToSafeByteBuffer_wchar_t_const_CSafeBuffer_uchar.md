# ReadFileToSafeByteBuffer(wchar_t const *,CSafeBuffer<uchar> *)

- ea: `0x14000fc20`
- end: `0x14000fd8d`
- name: `?ReadFileToSafeByteBuffer@@YAJPEB_WPEAV?$CSafeBuffer@E@@@Z`
- size: `365`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400254e8`
- `0x14002c6e0`
- `0x1400333b4`
- `0x14003dcf8`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000fc20`
- `0x14000feec`
- `0x1400122f0`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fd68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fd68`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000fd0a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000fd0a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000fcc4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000fcc4`

## pseudocode

```c
__int64 __fastcall ReadFileToSafeByteBuffer(wchar_t *a1, __int64 a2)
{
  __int64 v2; // rbx
  unsigned int LastError; // edi
  __int64 v6; // rdx
  int v7; // eax
  DWORD FileSize; // eax
  const char *v9; // r9
  DWORD v10; // esi
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // r9
  int lpOverlapped; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+28h] [rbp-60h]
  HANDLE hFile; // [rsp+50h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = -1;
  NumberOfBytesRead = 0;
  hFile = (HANDLE)-1LL;
  if ( !a2 )
  {
    LastError = -2147024809;
    v6 = 2078;
LABEL_14:
    v13 = LastError;
    goto LABEL_15;
  }
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  SusFree(0);
  v7 = SafeCreateFile(&hFile, 0, a1, 0x80000000, 1u, v16, 3u, 0x8000000u);
  v2 = (__int64)hFile;
  LastError = v7;
  if ( v7 < 0 )
  {
    v6 = 2090;
    goto LABEL_14;
  }
  FileSize = GetFileSize(hFile, 0);
  v10 = FileSize;
  if ( FileSize == -1 )
  {
    v11 = 2093;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                  v9);
    goto LABEL_17;
  }
  v12 = CSafeBuffer<unsigned char>::resize(a2, FileSize);
  LastError = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v6 = 2095;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)v13,
      lpOverlapped);
    goto LABEL_17;
  }
  if ( !ReadFile((HANDLE)v2, *(LPVOID *)(a2 + 8), v10, &NumberOfBytesRead, 0) )
  {
    v11 = 2097;
    goto LABEL_11;
  }
  if ( NumberOfBytesRead != v10 )
  {
    LastError = -2145103617;
    v6 = 2099;
    goto LABEL_14;
  }
  *(_DWORD *)(a2 + 20) = v10;
  LastError = 0;
LABEL_17:
  if ( v2 != -1 )
    CloseHandle((HANDLE)v2);
  return LastError;
}

```

## disassembly

```asm
0x14000fc20  mov     [rsp+arg_10], rbx
0x14000fc25  push    rbp
0x14000fc26  push    rsi
0x14000fc27  push    rdi
0x14000fc28  sub     rsp, 70h
0x14000fc2c  mov     rax, cs:__security_cookie
0x14000fc33  xor     rax, rsp
0x14000fc36  mov     [rsp+88h+var_28], rax
0x14000fc3b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000fc3f  mov     [rsp+88h+NumberOfBytesRead], 0
0x14000fc47  mov     [rsp+88h+hFile], rbx
0x14000fc4c  mov     rbp, rdx
0x14000fc4f  mov     rdi, rcx
0x14000fc52  test    rdx, rdx
0x14000fc55  jnz     short loc_14000FC66
0x14000fc57  mov     edi, 80070057h
0x14000fc5c  mov     edx, 81Eh
0x14000fc61  jmp     loc_14000FD41
0x14000fc66  xor     ecx, ecx; lpMem
0x14000fc68  mov     qword ptr [rdx+8], 0
0x14000fc70  mov     qword ptr [rdx+10h], 0
0x14000fc78  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14000fc7d  mov     [rsp+88h+var_50], 8000000h; unsigned int
0x14000fc85  lea     rcx, [rsp+88h+hFile]; void **
0x14000fc8a  mov     [rsp+88h+var_58], 3; unsigned int
0x14000fc92  mov     r9d, 80000000h; unsigned int
0x14000fc98  mov     r8, rdi; wchar_t *
0x14000fc9b  mov     dword ptr [rsp+88h+lpOverlapped], 1; unsigned int
0x14000fca3  xor     edx, edx; unsigned int
0x14000fca5  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x14000fcaa  mov     rbx, [rsp+88h+hFile]
0x14000fcaf  mov     edi, eax
0x14000fcb1  test    eax, eax
0x14000fcb3  jns     short loc_14000FCBF
0x14000fcb5  mov     edx, 82Ah
0x14000fcba  jmp     loc_14000FD41
0x14000fcbf  xor     edx, edx; lpFileSizeHigh
0x14000fcc1  mov     rcx, rbx; hFile
0x14000fcc4  call    cs:__imp_GetFileSize
0x14000fcca  mov     esi, eax
0x14000fccc  cmp     eax, 0FFFFFFFFh
0x14000fccf  jnz     short loc_14000FCD8
0x14000fcd1  mov     edx, 82Dh
0x14000fcd6  jmp     short loc_14000FD19
0x14000fcd8  mov     edx, esi
0x14000fcda  mov     rcx, rbp
0x14000fcdd  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x14000fce2  mov     edi, eax
0x14000fce4  test    eax, eax
0x14000fce6  jns     short loc_14000FCF2
0x14000fce8  mov     r9d, eax
0x14000fceb  mov     edx, 82Fh
0x14000fcf0  jmp     short loc_14000FD44
0x14000fcf2  mov     rdx, [rbp+8]; lpBuffer
0x14000fcf6  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000fcfb  mov     r8d, esi; nNumberOfBytesToRead
0x14000fcfe  mov     [rsp+88h+lpOverlapped], 0; int
0x14000fd07  mov     rcx, rbx; hFile
0x14000fd0a  call    cs:__imp_ReadFile
0x14000fd10  test    eax, eax
0x14000fd12  jnz     short loc_14000FD31
0x14000fd14  mov     edx, 831h; void *
0x14000fd19  mov     rcx, [rsp+88h]; this
0x14000fd21  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000fd28  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000fd2d  mov     edi, eax
0x14000fd2f  jmp     short loc_14000FD5F
0x14000fd31  cmp     [rsp+88h+NumberOfBytesRead], esi
0x14000fd35  jz      short loc_14000FD5A
0x14000fd37  mov     edi, 802450FFh
0x14000fd3c  mov     edx, 833h; void *
0x14000fd41  mov     r9d, edi; char *
0x14000fd44  mov     rcx, [rsp+88h]; this
0x14000fd4c  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000fd53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd58  jmp     short loc_14000FD5F
0x14000fd5a  mov     [rbp+14h], esi
0x14000fd5d  xor     edi, edi
0x14000fd5f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000fd63  jz      short loc_14000FD6E
0x14000fd65  mov     rcx, rbx; hObject
0x14000fd68  call    cs:__imp_CloseHandle
0x14000fd6e  mov     eax, edi
0x14000fd70  mov     rcx, [rsp+88h+var_28]
0x14000fd75  xor     rcx, rsp; StackCookie
0x14000fd78  call    __security_check_cookie
0x14000fd7d  mov     rbx, [rsp+88h+arg_10]
0x14000fd85  add     rsp, 70h
0x14000fd89  pop     rdi
0x14000fd8a  pop     rsi
0x14000fd8b  pop     rbp
0x14000fd8c  retn
```
