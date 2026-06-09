# HashFileData

- ea: `0x18005ae90`
- end: `0x18005aff4`
- name: `HashFileData`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005affc`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x18000dd60`
- `0x180049e88`
- `0x18005ae90`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005afd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005afd4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005af4b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005af4b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005af63`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005af80`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005af63`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18005af80`

## pseudocode

```c
__int64 __fastcall HashFileData(const WCHAR *a1, HCRYPTHASH a2, HCRYPTHASH a3, struct _SECURITY_ATTRIBUTES *a4)
{
  BYTE *v4; // rbx
  void *FileRetryIfSharingViolation; // rsi
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // edi
  int lpOverlapped; // [rsp+20h] [rbp-78h]
  void *v13; // [rsp+30h] [rbp-68h]
  unsigned int v14; // [rsp+38h] [rbp-60h]
  void *v15; // [rsp+40h] [rbp-58h]
  DWORD NumberOfBytesRead; // [rsp+64h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = 0;
  NumberOfBytesRead = 0;
  FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(
                                  a1,
                                  1u,
                                  1u,
                                  a4,
                                  3u,
                                  0x8000000u,
                                  v13,
                                  v14,
                                  v15,
                                  0,
                                  0);
  if ( FileRetryIfSharingViolation == (void *)-1LL )
  {
    v9 = 249;
  }
  else
  {
    v4 = (BYTE *)SafeSusAllocArray(0x100000u, 1u);
    LastError = v4 == 0 ? 0x8007000E : 0;
    if ( !v4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)LastError,
        lpOverlapped);
      goto LABEL_15;
    }
    while ( ReadFile(FileRetryIfSharingViolation, v4, 0x100000u, &NumberOfBytesRead, 0) )
    {
      if ( !CryptHashData(a2, v4, NumberOfBytesRead, 0) )
      {
        v9 = 270;
        goto LABEL_14;
      }
      if ( a3 && !CryptHashData(a3, v4, NumberOfBytesRead, 0) )
      {
        v9 = 277;
        goto LABEL_14;
      }
      if ( !NumberOfBytesRead )
      {
        LastError = 0;
        goto LABEL_16;
      }
    }
    v9 = 263;
  }
LABEL_14:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v9,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
                v8);
LABEL_15:
  if ( v4 )
LABEL_16:
    SusFree(v4);
  if ( FileRetryIfSharingViolation != (void *)-1LL )
    CloseHandle(FileRetryIfSharingViolation);
  return LastError;
}

```

## disassembly

```asm
0x18005ae90  push    rbx
0x18005ae92  push    rbp
0x18005ae93  push    rsi
0x18005ae94  push    rdi
0x18005ae95  push    r14
0x18005ae97  sub     rsp, 70h
0x18005ae9b  mov     rax, cs:__security_cookie
0x18005aea2  xor     rax, rsp
0x18005aea5  mov     [rsp+98h+var_30], rax
0x18005aeaa  xor     ebx, ebx
0x18005aeac  mov     rbp, r8
0x18005aeaf  mov     [rsp+98h+var_48], ebx; unsigned int
0x18005aeb3  mov     r14, rdx
0x18005aeb6  mov     [rsp+98h+var_50], ebx; int
0x18005aeba  mov     [rsp+98h+var_70], 8000000h; DWORD
0x18005aec2  lea     edi, [rbx+1]
0x18005aec5  mov     [rsp+98h+NumberOfBytesRead], ebx
0x18005aec9  mov     r8d, edi; dwShareMode
0x18005aecc  mov     dword ptr [rsp+98h+lpOverlapped], 3; int
0x18005aed4  mov     edx, edi; dwDesiredAccess
0x18005aed6  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x18005aedb  mov     rsi, rax
0x18005aede  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005aee2  jnz     short loc_18005AEEE
0x18005aee4  mov     edx, 0F9h
0x18005aee9  jmp     loc_18005AFA8
0x18005aeee  mov     rdx, rdi; unsigned __int64
0x18005aef1  mov     ecx, 100000h; unsigned __int64
0x18005aef6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18005aefb  mov     rbx, rax
0x18005aefe  neg     rax
0x18005af01  sbb     edi, edi
0x18005af03  not     edi
0x18005af05  and     edi, 8007000Eh
0x18005af0b  test    rbx, rbx
0x18005af0e  jnz     short loc_18005AF31
0x18005af10  mov     rcx, [rsp+98h]; this
0x18005af18  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005af1f  mov     r9d, edi; char *
0x18005af22  mov     edx, 0FCh; void *
0x18005af27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005af2c  jmp     loc_18005AFBE
0x18005af31  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005af36  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x18005af3f  mov     r8d, 100000h; nNumberOfBytesToRead
0x18005af45  mov     rdx, rbx; lpBuffer
0x18005af48  mov     rcx, rsi; hFile
0x18005af4b  call    cs:__imp_ReadFile
0x18005af51  test    eax, eax
0x18005af53  jz      short loc_18005AFA3
0x18005af55  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x18005af5a  xor     r9d, r9d; dwFlags
0x18005af5d  mov     rdx, rbx; pbData
0x18005af60  mov     rcx, r14; hHash
0x18005af63  call    cs:__imp_CryptHashData
0x18005af69  test    eax, eax
0x18005af6b  jz      short loc_18005AF9C
0x18005af6d  test    rbp, rbp
0x18005af70  jz      short loc_18005AF8A
0x18005af72  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x18005af77  xor     r9d, r9d; dwFlags
0x18005af7a  mov     rdx, rbx; pbData
0x18005af7d  mov     rcx, rbp; hHash
0x18005af80  call    cs:__imp_CryptHashData
0x18005af86  test    eax, eax
0x18005af88  jz      short loc_18005AF95
0x18005af8a  cmp     [rsp+98h+NumberOfBytesRead], 0
0x18005af8f  jnz     short loc_18005AF31
0x18005af91  xor     edi, edi
0x18005af93  jmp     short loc_18005AFC3
0x18005af95  mov     edx, 115h
0x18005af9a  jmp     short loc_18005AFA8
0x18005af9c  mov     edx, 10Eh
0x18005afa1  jmp     short loc_18005AFA8
0x18005afa3  mov     edx, 107h; void *
0x18005afa8  mov     rcx, [rsp+98h]; this
0x18005afb0  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005afb7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005afbc  mov     edi, eax
0x18005afbe  test    rbx, rbx
0x18005afc1  jz      short loc_18005AFCB
0x18005afc3  mov     rcx, rbx; lpMem
0x18005afc6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005afcb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005afcf  jz      short loc_18005AFDA
0x18005afd1  mov     rcx, rsi; hObject
0x18005afd4  call    cs:__imp_CloseHandle
0x18005afda  mov     eax, edi
0x18005afdc  mov     rcx, [rsp+98h+var_30]
0x18005afe1  xor     rcx, rsp; StackCookie
0x18005afe4  call    __security_check_cookie
0x18005afe9  add     rsp, 70h
0x18005afed  pop     r14
0x18005afef  pop     rdi
0x18005aff0  pop     rsi
0x18005aff1  pop     rbp
0x18005aff2  pop     rbx
0x18005aff3  retn
```
