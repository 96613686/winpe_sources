# NgcUtils::ReadFile(ushort const *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x180072c40`
- end: `0x180072df5`
- name: `?ReadFile@NgcUtils@@YAJPEBGPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `437`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003c5a8`
- `0x18003cc20`
- `0x180049284`
- `0x180049478`

## callees

- `0x18000d60c`
- `0x18000d62c`
- `0x18000fa2c`
- `0x180011c1c`
- `0x1800183c4`
- `0x18001ddec`
- `0x180072af0`
- `0x180072c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072c7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072c7b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180072ce9`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180072ce9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180072d63`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180072d63`

## string_xrefs

- `0x180072ca6`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072d0b`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072d71`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`
- `0x180072dab`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::ReadFile(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rbx
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  __int64 v7; // rax
  LPVOID *p_lpBuffer; // rcx
  __int64 v9; // rdx
  const char *v10; // r9
  int lpOverlapped; // [rsp+20h] [rbp-60h]
  int lpOverlappeda; // [rsp+20h] [rbp-60h]
  HANDLE v14; // [rsp+40h] [rbp-40h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h]
  _BYTE v17[32]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+20h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+28h] BYREF

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v14 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v5 = 108;
      goto LABEL_4;
    }
    if ( FileSize.QuadPart )
    {
      if ( FileSize.QuadPart <= 0x1E84800uLL )
      {
        ((void (__fastcall *)(_QWORD, _QWORD))std::vector<unsigned char>::vector<unsigned char>)(
          &lpBuffer,
          (union _LARGE_INTEGER)FileSize.QuadPart);
        NumberOfBytesRead = 0;
        if ( ReadFile(FileW, lpBuffer, v16 - (_DWORD)lpBuffer, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead == v16 - (_QWORD)lpBuffer )
          {
            std::vector<unsigned char>::operator=(a2, &lpBuffer);
            p_lpBuffer = &lpBuffer;
            goto LABEL_19;
          }
          LastError = -2147024866;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x84,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
            (const char *)0x8007001ELL,
            lpOverlappeda);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x80,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
                        v10);
        }
        std::vector<unsigned char>::_Tidy(&lpBuffer);
        goto LABEL_20;
      }
      LastError = -2147024673;
      v9 = 117;
    }
    else
    {
      LastError = -2147020590;
      v9 = 112;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
      (const char *)LastError,
      lpOverlapped);
    goto LABEL_20;
  }
  if ( GetLastError() - 2 <= 1 )
  {
    v7 = std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v17);
    std::vector<unsigned char>::operator=(a2, v7);
    p_lpBuffer = (LPVOID *)v17;
LABEL_19:
    std::vector<unsigned char>::_Tidy(p_lpBuffer);
    LastError = 0;
    goto LABEL_20;
  }
  v5 = 102;
LABEL_4:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
                v4);
LABEL_20:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x180072c40  mov     rax, rsp
0x180072c43  mov     [rax+8], rbx
0x180072c47  mov     [rax+10h], rdi
0x180072c4b  push    rbp
0x180072c4c  mov     rbp, rsp
0x180072c4f  sub     rsp, 80h
0x180072c56  mov     rdi, rdx
0x180072c59  mov     qword ptr [rax-58h], 0
0x180072c61  mov     dword ptr [rax-60h], 80h
0x180072c68  mov     dword ptr [rax-68h], 3
0x180072c6f  xor     r9d, r9d; lpSecurityAttributes
0x180072c72  mov     edx, 80000000h; dwDesiredAccess
0x180072c77  lea     r8d, [r9+1]; dwShareMode
0x180072c7b  call    cs:__imp_CreateFileW
0x180072c81  mov     rbx, rax
0x180072c84  mov     [rbp+var_40], rax
0x180072c88  inc     rax
0x180072c8b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180072c91  jnz     short loc_180072CDA
0x180072c93  call    cs:__imp_GetLastError
0x180072c99  add     eax, 0FFFFFFFEh
0x180072c9c  cmp     eax, 1
0x180072c9f  jbe     short loc_180072CBD
0x180072ca1  mov     edx, 66h ; 'f'; void *
0x180072ca6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072cad  mov     rcx, [rbp+8]; this
0x180072cb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072cb6  mov     ebx, eax
0x180072cb8  jmp     loc_180072DD5
0x180072cbd  lea     rcx, [rbp+var_20]
0x180072cc1  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180072cc6  mov     rdx, rax
0x180072cc9  mov     rcx, rdi
0x180072ccc  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180072cd1  lea     rcx, [rbp+var_20]
0x180072cd5  jmp     loc_180072DCE
0x180072cda  mov     qword ptr [rbp+FileSize], 0
0x180072ce2  lea     rdx, [rbp+FileSize]; lpFileSize
0x180072ce6  mov     rcx, rbx; hFile
0x180072ce9  call    cs:__imp_GetFileSizeEx
0x180072cef  test    eax, eax
0x180072cf1  jnz     short loc_180072CF8
0x180072cf3  lea     edx, [rax+6Ch]
0x180072cf6  jmp     short loc_180072CA6
0x180072cf8  mov     rdx, qword ptr [rbp+FileSize]
0x180072cfc  test    rdx, rdx
0x180072cff  jnz     short loc_180072D23
0x180072d01  mov     ebx, 800710D2h
0x180072d06  mov     edx, 70h ; 'p'; void *
0x180072d0b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072d12  mov     r9d, ebx; char *
0x180072d15  mov     rcx, [rbp+8]; this
0x180072d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072d1e  jmp     loc_180072DD5
0x180072d23  cmp     rdx, 1E84800h
0x180072d2a  jbe     short loc_180072D38
0x180072d2c  mov     ebx, 800700DFh
0x180072d31  mov     edx, 75h ; 'u'
0x180072d36  jmp     short loc_180072D0B
0x180072d38  lea     rcx, [rbp+lpBuffer]
0x180072d3c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180072d41  mov     [rbp+NumberOfBytesRead], 0
0x180072d48  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180072d4c  mov     r8d, dword ptr [rbp+var_30]
0x180072d50  sub     r8d, edx; nNumberOfBytesToRead
0x180072d53  mov     qword ptr [rsp+80h+lpOverlapped], 0; int
0x180072d5c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180072d60  mov     rcx, rbx; hFile
0x180072d63  call    cs:__imp_ReadFile
0x180072d69  test    eax, eax
0x180072d6b  jnz     short loc_180072D8F
0x180072d6d  mov     rcx, [rbp+8]; this
0x180072d71  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072d78  mov     edx, 80h; void *
0x180072d7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072d82  mov     ebx, eax
0x180072d84  lea     rcx, [rbp+lpBuffer]
0x180072d88  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180072d8d  jmp     short loc_180072DD5
0x180072d8f  mov     rcx, [rbp+var_30]
0x180072d93  sub     rcx, [rbp+lpBuffer]
0x180072d97  mov     eax, [rbp+NumberOfBytesRead]
0x180072d9a  cmp     rax, rcx
0x180072d9d  jz      short loc_180072DBE
0x180072d9f  mov     rcx, [rbp+8]; this
0x180072da3  mov     ebx, 8007001Eh
0x180072da8  mov     r9d, ebx; char *
0x180072dab  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180072db2  mov     edx, 84h; void *
0x180072db7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072dbc  jmp     short loc_180072D84
0x180072dbe  lea     rdx, [rbp+lpBuffer]
0x180072dc2  mov     rcx, rdi
0x180072dc5  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180072dca  lea     rcx, [rbp+lpBuffer]
0x180072dce  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180072dd3  xor     ebx, ebx
0x180072dd5  lea     rcx, [rbp+var_40]
0x180072dd9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180072dde  mov     eax, ebx
0x180072de0  lea     r11, [rsp+80h+var_s0]
0x180072de8  mov     rbx, [r11+10h]
0x180072dec  mov     rdi, [r11+18h]
0x180072df0  mov     rsp, r11
0x180072df3  pop     rbp
0x180072df4  retn
```
