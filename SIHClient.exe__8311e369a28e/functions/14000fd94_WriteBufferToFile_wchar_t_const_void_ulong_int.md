# WriteBufferToFile(wchar_t const *,void *,ulong,int)

- ea: `0x14000fd94`
- end: `0x14000fe94`
- name: `?WriteBufferToFile@@YAJPEB_WPEAXKH@Z`
- size: `256`
- prototype: `int(const wchar_t *, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002c6e0`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000fd94`
- `0x1400122f0`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fe77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fe77`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000fe18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000fe18`

## pseudocode

```c
__int64 __fastcall WriteBufferToFile(const wchar_t *a1, void *a2, DWORD a3)
{
  int v5; // eax
  unsigned int LastError; // edi
  __int64 v7; // r9
  __int64 v8; // rdx
  const char *v9; // r9
  int lpOverlapped; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+28h] [rbp-60h]
  HANDLE hFile; // [rsp+50h] [rbp-38h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  hFile = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  v5 = SafeCreateFile(&hFile, 0, a1, 0x40000000u, 7u, v12, 3u, 0);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 2122;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)v7,
      lpOverlapped);
    goto LABEL_9;
  }
  if ( !WriteFile(hFile, a2, a3, &NumberOfBytesWritten, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x84C,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                  v9);
    goto LABEL_9;
  }
  if ( NumberOfBytesWritten != a3 )
  {
    LastError = -2147467259;
    v8 = 2126;
    v7 = 2147500037LL;
    goto LABEL_7;
  }
  LastError = 0;
LABEL_9:
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return LastError;
}

```

## disassembly

```asm
0x14000fd94  push    rbp
0x14000fd96  push    rsi
0x14000fd97  push    rdi
0x14000fd98  sub     rsp, 70h
0x14000fd9c  mov     rax, cs:__security_cookie
0x14000fda3  xor     rax, rsp
0x14000fda6  mov     [rsp+88h+var_28], rax
0x14000fdab  mov     esi, r8d
0x14000fdae  mov     [rsp+88h+var_50], 0; unsigned int
0x14000fdb6  mov     r8, rcx; wchar_t *
0x14000fdb9  mov     [rsp+88h+var_58], 3; unsigned int
0x14000fdc1  mov     rbp, rdx
0x14000fdc4  mov     [rsp+88h+hFile], 0FFFFFFFFFFFFFFFFh
0x14000fdcd  lea     rcx, [rsp+88h+hFile]; void **
0x14000fdd2  mov     [rsp+88h+NumberOfBytesWritten], 0
0x14000fdda  mov     r9d, 40000000h; unsigned int
0x14000fde0  mov     dword ptr [rsp+88h+lpOverlapped], 7; unsigned int
0x14000fde8  xor     edx, edx; unsigned int
0x14000fdea  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x14000fdef  mov     edi, eax
0x14000fdf1  test    eax, eax
0x14000fdf3  jns     short loc_14000FDFF
0x14000fdf5  mov     r9d, eax
0x14000fdf8  mov     edx, 84Ah
0x14000fdfd  jmp     short loc_14000FE52
0x14000fdff  mov     rcx, [rsp+88h+hFile]; hFile
0x14000fe04  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000fe09  mov     r8d, esi; nNumberOfBytesToWrite
0x14000fe0c  mov     [rsp+88h+lpOverlapped], 0; int
0x14000fe15  mov     rdx, rbp; lpBuffer
0x14000fe18  call    cs:__imp_WriteFile
0x14000fe1e  test    eax, eax
0x14000fe20  jnz     short loc_14000FE3F
0x14000fe22  mov     rcx, [rsp+88h]; this
0x14000fe2a  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000fe31  mov     edx, 84Ch; void *
0x14000fe36  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000fe3b  mov     edi, eax
0x14000fe3d  jmp     short loc_14000FE6A
0x14000fe3f  cmp     [rsp+88h+NumberOfBytesWritten], esi
0x14000fe43  jz      short loc_14000FE68
0x14000fe45  mov     edi, 80004005h
0x14000fe4a  mov     edx, 84Eh; void *
0x14000fe4f  mov     r9d, edi; char *
0x14000fe52  mov     rcx, [rsp+88h]; this
0x14000fe5a  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000fe61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe66  jmp     short loc_14000FE6A
0x14000fe68  xor     edi, edi
0x14000fe6a  cmp     [rsp+88h+hFile], 0FFFFFFFFFFFFFFFFh
0x14000fe70  jz      short loc_14000FE7D
0x14000fe72  mov     rcx, [rsp+88h+hFile]; hObject
0x14000fe77  call    cs:__imp_CloseHandle
0x14000fe7d  mov     eax, edi
0x14000fe7f  mov     rcx, [rsp+88h+var_28]
0x14000fe84  xor     rcx, rsp; StackCookie
0x14000fe87  call    __security_check_cookie
0x14000fe8c  add     rsp, 70h
0x14000fe90  pop     rdi
0x14000fe91  pop     rsi
0x14000fe92  pop     rbp
0x14000fe93  retn
```
