# HashFileData

- ea: `0x14003b2a0`
- end: `0x14003b404`
- name: `HashFileData`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003b40c`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14000fab0`
- `0x14003b2a0`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b3e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b3e4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003b35b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003b35b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14003b373`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14003b390`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14003b373`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14003b390`

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
0x14003b2a0  push    rbx
0x14003b2a2  push    rbp
0x14003b2a3  push    rsi
0x14003b2a4  push    rdi
0x14003b2a5  push    r14
0x14003b2a7  sub     rsp, 70h
0x14003b2ab  mov     rax, cs:__security_cookie
0x14003b2b2  xor     rax, rsp
0x14003b2b5  mov     [rsp+98h+var_30], rax
0x14003b2ba  xor     ebx, ebx
0x14003b2bc  mov     rbp, r8
0x14003b2bf  mov     [rsp+98h+var_48], ebx; unsigned int
0x14003b2c3  mov     r14, rdx
0x14003b2c6  mov     [rsp+98h+var_50], ebx; int
0x14003b2ca  mov     [rsp+98h+var_70], 8000000h; DWORD
0x14003b2d2  lea     edi, [rbx+1]
0x14003b2d5  mov     [rsp+98h+NumberOfBytesRead], ebx
0x14003b2d9  mov     r8d, edi; dwShareMode
0x14003b2dc  mov     dword ptr [rsp+98h+lpOverlapped], 3; int
0x14003b2e4  mov     edx, edi; dwDesiredAccess
0x14003b2e6  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x14003b2eb  mov     rsi, rax
0x14003b2ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003b2f2  jnz     short loc_14003B2FE
0x14003b2f4  mov     edx, 0F9h
0x14003b2f9  jmp     loc_14003B3B8
0x14003b2fe  mov     rdx, rdi; unsigned __int64
0x14003b301  mov     ecx, 100000h; unsigned __int64
0x14003b306  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003b30b  mov     rbx, rax
0x14003b30e  neg     rax
0x14003b311  sbb     edi, edi
0x14003b313  not     edi
0x14003b315  and     edi, 8007000Eh
0x14003b31b  test    rbx, rbx
0x14003b31e  jnz     short loc_14003B341
0x14003b320  mov     rcx, [rsp+98h]; this
0x14003b328  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b32f  mov     r9d, edi; char *
0x14003b332  mov     edx, 0FCh; void *
0x14003b337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b33c  jmp     loc_14003B3CE
0x14003b341  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003b346  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x14003b34f  mov     r8d, 100000h; nNumberOfBytesToRead
0x14003b355  mov     rdx, rbx; lpBuffer
0x14003b358  mov     rcx, rsi; hFile
0x14003b35b  call    cs:__imp_ReadFile
0x14003b361  test    eax, eax
0x14003b363  jz      short loc_14003B3B3
0x14003b365  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x14003b36a  xor     r9d, r9d; dwFlags
0x14003b36d  mov     rdx, rbx; pbData
0x14003b370  mov     rcx, r14; hHash
0x14003b373  call    cs:__imp_CryptHashData
0x14003b379  test    eax, eax
0x14003b37b  jz      short loc_14003B3AC
0x14003b37d  test    rbp, rbp
0x14003b380  jz      short loc_14003B39A
0x14003b382  mov     r8d, [rsp+98h+NumberOfBytesRead]; dwDataLen
0x14003b387  xor     r9d, r9d; dwFlags
0x14003b38a  mov     rdx, rbx; pbData
0x14003b38d  mov     rcx, rbp; hHash
0x14003b390  call    cs:__imp_CryptHashData
0x14003b396  test    eax, eax
0x14003b398  jz      short loc_14003B3A5
0x14003b39a  cmp     [rsp+98h+NumberOfBytesRead], 0
0x14003b39f  jnz     short loc_14003B341
0x14003b3a1  xor     edi, edi
0x14003b3a3  jmp     short loc_14003B3D3
0x14003b3a5  mov     edx, 115h
0x14003b3aa  jmp     short loc_14003B3B8
0x14003b3ac  mov     edx, 10Eh
0x14003b3b1  jmp     short loc_14003B3B8
0x14003b3b3  mov     edx, 107h; void *
0x14003b3b8  mov     rcx, [rsp+98h]; this
0x14003b3c0  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b3c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003b3cc  mov     edi, eax
0x14003b3ce  test    rbx, rbx
0x14003b3d1  jz      short loc_14003B3DB
0x14003b3d3  mov     rcx, rbx; lpMem
0x14003b3d6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003b3db  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14003b3df  jz      short loc_14003B3EA
0x14003b3e1  mov     rcx, rsi; hObject
0x14003b3e4  call    cs:__imp_CloseHandle
0x14003b3ea  mov     eax, edi
0x14003b3ec  mov     rcx, [rsp+98h+var_30]
0x14003b3f1  xor     rcx, rsp; StackCookie
0x14003b3f4  call    __security_check_cookie
0x14003b3f9  add     rsp, 70h
0x14003b3fd  pop     r14
0x14003b3ff  pop     rdi
0x14003b400  pop     rsi
0x14003b401  pop     rbp
0x14003b402  pop     rbx
0x14003b403  retn
```
