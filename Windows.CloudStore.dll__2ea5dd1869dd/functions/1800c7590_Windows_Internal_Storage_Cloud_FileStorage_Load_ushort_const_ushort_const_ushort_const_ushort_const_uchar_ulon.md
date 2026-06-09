# Windows::Internal::Storage::Cloud::FileStorage::Load(ushort const *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x1800c7590`
- end: `0x1800c77cb`
- name: `?Load@FileStorage@Cloud@Storage@Internal@Windows@@UEAAJPEBG000PEAPEAEPEAK@Z`
- size: `571`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::FileStorage *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800320d4`
- `0x18007e0c8`
- `0x18007e75c`
- `0x180091b04`
- `0x1800c7590`
- `0x1800c8458`
- `0x1800fc644`
- `0x1801201a0`
- `0x1801a8e60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c7627`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c7627`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c764d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c764d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7724`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c76fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c76fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7755`

## string_xrefs

- `0x1800c75f0`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800c765a`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800c76da`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800c7735`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1800c777a`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Storage::Cloud::FileStorage::Load(
        Windows::Internal::Storage::Cloud::FileStorage *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int v7; // eax
  unsigned int LastError; // ebx
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rbx
  __int64 v12; // rdx
  void *v13; // rcx
  int v14; // edi
  void *v15; // rcx
  const char *v16; // r9
  void *v17; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v26; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID *p_pv; // [rsp+68h] [rbp-98h] BYREF
  void *v28; // [rsp+70h] [rbp-90h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *a7 = 0;
  *a6 = 0;
  v7 = Windows::Internal::Storage::Cloud::FileStorage::GetFileName(this, a5, FileName, (unsigned __int64)a4);
  LastError = v7;
  if ( v7 >= 0 )
  {
    FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0, 0);
    v11 = FileW;
    v26 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v12 = 69;
    }
    else
    {
      FileSize.QuadPart = 0;
      if ( GetFileSizeEx(FileW, &FileSize) )
      {
        pv = 0;
        p_pv = &pv;
        v29 = 1;
        v28 = 0;
        v25 = 0;
        v14 = ULongLongMult(FileSize.QuadPart, 1u, &v25);
        if ( v14 >= 0 )
          v14 = CTCoAllocPolicy::Alloc(v13, 1u, v25, &v28);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
            (const char *)(unsigned int)v14,
            dwCreationDispositiona);
          v15 = pv;
          pv = 0;
          if ( v15 )
            CoTaskMemFree(v15);
          LastError = v14;
          goto LABEL_21;
        }
        NumberOfBytesRead = 0;
        if ( ReadFile(v11, pv, FileSize.LowPart, &NumberOfBytesRead, 0) )
        {
          if ( FileSize.QuadPart == NumberOfBytesRead )
          {
            *a7 = FileSize.LowPart;
            *a6 = (unsigned __int8 *)pv;
            pv = 0;
            LastError = 0;
            goto LABEL_21;
          }
          LastError = -2147467259;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
            (const char *)0x80004005LL,
            dwCreationDispositionb);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x4E,
                        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
                        v16);
        }
        v17 = pv;
        pv = 0;
        if ( v17 )
          CoTaskMemFree(v17);
        goto LABEL_21;
      }
      v12 = 72;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
                  v10);
LABEL_21:
    std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&v26);
    return LastError;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
    (const char *)(unsigned int)v7,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x1800c7590  push    rbp
0x1800c7592  push    rbx
0x1800c7593  push    rsi
0x1800c7594  push    rdi
0x1800c7595  push    r14
0x1800c7597  push    r15
0x1800c7599  lea     rbp, [rsp-1A8h]
0x1800c75a1  sub     rsp, 2A8h
0x1800c75a8  mov     rax, cs:__security_cookie
0x1800c75af  xor     rax, rsp
0x1800c75b2  mov     [rbp+1D0h+var_40], rax
0x1800c75b9  mov     rdx, [rbp+1D0h+arg_20]; unsigned __int16 *
0x1800c75c0  mov     rsi, [rbp+1D0h+arg_28]
0x1800c75c7  mov     r14, [rbp+1D0h+arg_30]
0x1800c75ce  xor     r15d, r15d
0x1800c75d1  mov     [r14], r15d
0x1800c75d4  mov     [rsi], r15
0x1800c75d7  lea     r8, [rbp+1D0h+FileName]; unsigned __int16 *
0x1800c75db  call    ?GetFileName@FileStorage@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::FileStorage::GetFileName(ushort const *,ushort *,unsigned __int64)
0x1800c75e0  mov     ebx, eax
0x1800c75e2  test    eax, eax
0x1800c75e4  jns     short loc_1800C7605
0x1800c75e6  mov     rcx, [rbp+1D8h]; this
0x1800c75ed  mov     r9d, eax; char *
0x1800c75f0  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c75f7  lea     edx, [r15+3Bh]; void *
0x1800c75fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7600  jmp     loc_1800C77AA
0x1800c7605  mov     [rsp+2D0h+hTemplateFile], r15; hTemplateFile
0x1800c760a  mov     [rsp+2D0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800c760f  mov     [rsp+2D0h+dwCreationDisposition], 3; int
0x1800c7617  xor     r9d, r9d; lpSecurityAttributes
0x1800c761a  mov     edx, 80000000h; dwDesiredAccess
0x1800c761f  lea     r8d, [r9+1]; dwShareMode
0x1800c7623  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x1800c7627  call    cs:__imp_CreateFileW
0x1800c762d  mov     rbx, rax
0x1800c7630  mov     [rsp+2D0h+var_270], rax
0x1800c7635  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c7639  jnz     short loc_1800C7640
0x1800c763b  lea     edx, [rax+46h]
0x1800c763e  jmp     short loc_1800C765A
0x1800c7640  mov     qword ptr [rsp+2D0h+FileSize], r15
0x1800c7645  lea     rdx, [rsp+2D0h+FileSize]; lpFileSize
0x1800c764a  mov     rcx, rbx; hFile
0x1800c764d  call    cs:__imp_GetFileSizeEx
0x1800c7653  test    eax, eax
0x1800c7655  jnz     short loc_1800C7674
0x1800c7657  lea     edx, [rax+48h]; void *
0x1800c765a  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c7661  mov     rcx, [rbp+1D8h]; this
0x1800c7668  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c766d  mov     ebx, eax
0x1800c766f  jmp     loc_1800C77A0
0x1800c7674  mov     [rsp+2D0h+pv], r15
0x1800c7679  lea     rax, [rsp+2D0h+pv]
0x1800c767e  mov     [rsp+2D0h+var_268], rax
0x1800c7683  mov     [rsp+2D0h+var_258], 1
0x1800c7688  mov     [rsp+2D0h+var_260], r15
0x1800c768d  mov     [rsp+2D0h+var_278], r15
0x1800c7692  lea     r8, [rsp+2D0h+var_278]; unsigned __int64 *
0x1800c7697  mov     edx, 1; unsigned __int64
0x1800c769c  mov     rcx, qword ptr [rsp+2D0h+FileSize]; unsigned __int64
0x1800c76a1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800c76a6  mov     edi, eax
0x1800c76a8  test    eax, eax
0x1800c76aa  js      short loc_1800C76C2
0x1800c76ac  lea     r9, [rsp+2D0h+var_260]; void **
0x1800c76b1  mov     r8, [rsp+2D0h+var_278]; unsigned __int64
0x1800c76b6  mov     edx, 1; unsigned int
0x1800c76bb  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800c76c0  mov     edi, eax
0x1800c76c2  lea     rcx, [rsp+2D0h+var_268]
0x1800c76c7  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c76cc  test    edi, edi
0x1800c76ce  jns     short loc_1800C7708
0x1800c76d0  mov     rcx, [rbp+1D8h]; this
0x1800c76d7  mov     r9d, edi; char *
0x1800c76da  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c76e1  mov     edx, 4Bh ; 'K'; void *
0x1800c76e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c76eb  nop
0x1800c76ec  mov     rcx, [rsp+2D0h+pv]; pv
0x1800c76f1  mov     [rsp+2D0h+pv], r15
0x1800c76f6  test    rcx, rcx
0x1800c76f9  jz      short loc_1800C7701
0x1800c76fb  call    cs:__imp_CoTaskMemFree
0x1800c7701  mov     ebx, edi
0x1800c7703  jmp     loc_1800C77A0
0x1800c7708  mov     [rsp+2D0h+NumberOfBytesRead], r15d
0x1800c770d  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r15; int
0x1800c7712  lea     r9, [rsp+2D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c7717  mov     r8d, dword ptr [rsp+2D0h+FileSize]; nNumberOfBytesToRead
0x1800c771c  mov     rdx, [rsp+2D0h+pv]; lpBuffer
0x1800c7721  mov     rcx, rbx; hFile
0x1800c7724  call    cs:__imp_ReadFile
0x1800c772a  test    eax, eax
0x1800c772c  jnz     short loc_1800C775D
0x1800c772e  mov     rcx, [rbp+1D8h]; this
0x1800c7735  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c773c  lea     edx, [rax+4Eh]; void *
0x1800c773f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c7744  mov     ebx, eax
0x1800c7746  mov     rcx, [rsp+2D0h+pv]; pv
0x1800c774b  mov     [rsp+2D0h+pv], r15
0x1800c7750  test    rcx, rcx
0x1800c7753  jz      short loc_1800C77A0
0x1800c7755  call    cs:__imp_CoTaskMemFree
0x1800c775b  jmp     short loc_1800C77A0
0x1800c775d  mov     ecx, [rsp+2D0h+NumberOfBytesRead]
0x1800c7761  mov     rax, qword ptr [rsp+2D0h+FileSize]
0x1800c7766  cmp     rax, rcx
0x1800c7769  jz      short loc_1800C778D
0x1800c776b  mov     rcx, [rbp+1D8h]; this
0x1800c7772  mov     ebx, 80004005h
0x1800c7777  mov     r9d, ebx; char *
0x1800c777a  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c7781  mov     edx, 4Fh ; 'O'; void *
0x1800c7786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c778b  jmp     short loc_1800C7746
0x1800c778d  mov     [r14], eax
0x1800c7790  mov     rax, [rsp+2D0h+pv]
0x1800c7795  mov     [rsi], rax
0x1800c7798  mov     [rsp+2D0h+pv], r15
0x1800c779d  mov     ebx, r15d
0x1800c77a0  lea     rcx, [rsp+2D0h+var_270]
0x1800c77a5  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1800c77aa  mov     eax, ebx
0x1800c77ac  mov     rcx, [rbp+1D0h+var_40]
0x1800c77b3  xor     rcx, rsp; StackCookie
0x1800c77b6  call    __security_check_cookie
0x1800c77bb  add     rsp, 2A8h
0x1800c77c2  pop     r15
0x1800c77c4  pop     r14
0x1800c77c6  pop     rdi
0x1800c77c7  pop     rsi
0x1800c77c8  pop     rbx
0x1800c77c9  pop     rbp
0x1800c77ca  retn
```
