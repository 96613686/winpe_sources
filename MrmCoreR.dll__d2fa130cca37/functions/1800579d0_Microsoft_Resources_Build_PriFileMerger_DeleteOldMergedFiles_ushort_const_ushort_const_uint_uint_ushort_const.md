# Microsoft::Resources::Build::PriFileMerger::DeleteOldMergedFiles(ushort const *,ushort const *,uint,uint,ushort const *)

- ea: `0x1800579d0`
- end: `0x180057ca1`
- name: `?DeleteOldMergedFiles@PriFileMerger@Build@Resources@Microsoft@@KAJPEBG0II0@Z`
- size: `721`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005742c`

## callees

- `0x180017960`
- `0x180027270`
- `0x180028510`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x18003c030`
- `0x180042f70`
- `0x1800579d0`
- `0x180078b3c`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180057afe`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180057afe`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180057c28`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180057c28`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180057bed`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180057bed`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180057c0d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180057c0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180057a3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180057a3f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180057a4f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180057a4f`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::PriFileMerger::DeleteOldMergedFiles(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 *a5)
{
  struct _FILETIME v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  const WCHAR *v11; // rdx
  int v12; // eax
  const WCHAR *v13; // rcx
  char *v14; // rdi
  unsigned int v15; // r14d
  int v16; // esi
  const unsigned __int16 *Ref; // rax
  const WCHAR *v18; // rax
  __int64 v20; // rdx
  DWORD dwLowDateTime; // [rsp+20h] [rbp-E0h]
  struct _FILETIME FileTime; // [rsp+28h] [rbp-D8h] BYREF
  char *FirstFileW; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v24[4]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v25; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[24]; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileTime = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  v7 = FileTime;
  DefStringResult_InitBuf(v26);
  v25 = v26;
  v8 = DefStringResult_SetCopy(v26, a1);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 186;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)(unsigned int)v8,
      0);
    goto LABEL_29;
  }
  v8 = DefStringResult_ConcatPathElement(v25, a2, 92);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 187;
    goto LABEL_5;
  }
  if ( v25 && (*(_QWORD *)v25 || !*((_DWORD *)v25 + 2)) && (*((_DWORD *)v25 + 2) || !*(_QWORD *)v25) )
  {
    v11 = (const WCHAR *)*((_QWORD *)v25 + 2);
    v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = -2147024809;
  }
  v13 = 0;
  if ( v12 >= 0 )
    v13 = v11;
  FirstFileW = (char *)FindFirstFileW(v13, &FindFileData);
  v14 = FirstFileW;
  if ( FirstFileW == (char *)-1LL )
  {
LABEL_26:
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FindClose(v14);
    v9 = 0;
    goto LABEL_29;
  }
  v15 = 0;
  while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
LABEL_25:
    if ( !FindNextFileW(v14, &FindFileData) )
      goto LABEL_26;
  }
  dwLowDateTime = FindFileData.ftLastAccessTime.dwLowDateTime;
  if ( !(int)((double)(int)((*(_QWORD *)&v7 - *(_QWORD *)&FindFileData.ftLastAccessTime) / 0x989680uLL) - 2764800.0) )
  {
LABEL_24:
    if ( v15 >= 0xA )
      goto LABEL_26;
    goto LABEL_25;
  }
  Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)v24);
  v16 = DefStringResult_SetCopy(v24[0], a1);
  if ( v16 >= 0 )
  {
    v16 = DefStringResult_ConcatPathElement(v24[0], FindFileData.cFileName, 92);
    if ( v16 < 0 )
    {
      v20 = 216;
      goto LABEL_32;
    }
    Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v24);
    if ( (unsigned int)DefString_CompareWithOptions(Ref, a5, 1) )
    {
      v18 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v24);
      DeleteFileW(v18);
      ++v15;
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v24);
    goto LABEL_24;
  }
  v20 = 215;
LABEL_32:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
    (const char *)(unsigned int)v16,
    dwLowDateTime);
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFileW);
  v9 = v16;
LABEL_29:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v25);
  return v9;
}

```

## disassembly

```asm
0x1800579d0  mov     [rsp-8+arg_10], rbx
0x1800579d5  mov     [rsp-8+arg_18], rsi
0x1800579da  push    rbp
0x1800579db  push    rdi
0x1800579dc  push    r12
0x1800579de  push    r14
0x1800579e0  push    r15
0x1800579e2  lea     rbp, [rsp-1F0h]
0x1800579ea  sub     rsp, 2F0h
0x1800579f1  mov     rax, cs:__security_cookie
0x1800579f8  xor     rax, rsp
0x1800579fb  mov     [rbp+210h+var_30], rax
0x180057a02  mov     r12, [rbp+210h+arg_20]
0x180057a09  mov     rsi, rdx
0x180057a0c  mov     r15, rcx
0x180057a0f  xor     edx, edx; Val
0x180057a11  lea     rcx, [rbp+210h+FindFileData]; void *
0x180057a15  mov     r8d, 250h; Size
0x180057a1b  call    memset_0
0x180057a20  xorps   xmm0, xmm0
0x180057a23  mov     qword ptr [rsp+310h+FileTime.dwLowDateTime], 0
0x180057a2c  lea     rcx, [rsp+310h+SystemTime]; lpSystemTime
0x180057a31  mov     qword ptr [rsp+310h+var_2F0], 0; int
0x180057a3a  movups  xmmword ptr [rsp+310h+SystemTime.wYear], xmm0
0x180057a3f  call    cs:__imp_GetSystemTime
0x180057a45  lea     rdx, [rsp+310h+FileTime]; lpFileTime
0x180057a4a  lea     rcx, [rsp+310h+SystemTime]; lpSystemTime
0x180057a4f  call    cs:__imp_SystemTimeToFileTime
0x180057a55  mov     rbx, qword ptr [rsp+310h+FileTime.dwLowDateTime]
0x180057a5a  lea     rcx, [rsp+310h+var_2B0]
0x180057a5f  call    DefStringResult_InitBuf
0x180057a64  lea     rcx, [rsp+310h+var_2B0]
0x180057a69  mov     rdx, r15
0x180057a6c  mov     [rsp+310h+var_2B8], rcx
0x180057a71  lea     rcx, [rsp+310h+var_2B0]
0x180057a76  call    DefStringResult_SetCopy
0x180057a7b  mov     edi, eax
0x180057a7d  test    eax, eax
0x180057a7f  jns     short loc_180057A88
0x180057a81  mov     edx, 0BAh
0x180057a86  jmp     short loc_180057AA6
0x180057a88  mov     rcx, [rsp+310h+var_2B8]
0x180057a8d  mov     r8d, 5Ch ; '\'
0x180057a93  mov     rdx, rsi
0x180057a96  call    DefStringResult_ConcatPathElement
0x180057a9b  mov     edi, eax
0x180057a9d  test    eax, eax
0x180057a9f  jns     short loc_180057AC1
0x180057aa1  mov     edx, 0BBh; void *
0x180057aa6  mov     rcx, [rbp+218h]; this
0x180057aad  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x180057ab4  mov     r9d, eax; char *
0x180057ab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057abc  jmp     loc_180057C30
0x180057ac1  mov     rax, [rsp+310h+var_2B8]
0x180057ac6  test    rax, rax
0x180057ac9  jz      short loc_180057AEB
0x180057acb  cmp     qword ptr [rax], 0
0x180057acf  jnz     short loc_180057AD7
0x180057ad1  cmp     dword ptr [rax+8], 0
0x180057ad5  ja      short loc_180057AEB
0x180057ad7  cmp     dword ptr [rax+8], 0
0x180057adb  jnz     short loc_180057AE3
0x180057add  cmp     qword ptr [rax], 0
0x180057ae1  jnz     short loc_180057AEB
0x180057ae3  mov     rdx, [rax+10h]
0x180057ae7  xor     eax, eax
0x180057ae9  jmp     short loc_180057AF2
0x180057aeb  xor     edx, edx
0x180057aed  mov     eax, 80070057h
0x180057af2  xor     ecx, ecx
0x180057af4  test    eax, eax
0x180057af6  cmovns  rcx, rdx; lpFileName
0x180057afa  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180057afe  call    cs:__imp_FindFirstFileW
0x180057b04  mov     [rsp+310h+var_2E0], rax
0x180057b09  mov     rdi, rax
0x180057b0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180057b10  jz      loc_180057C1B
0x180057b16  xor     r14d, r14d
0x180057b19  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180057b1d  jnz     loc_180057C06
0x180057b23  mov     rax, qword ptr [rbp+210h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x180057b27  mov     rcx, rbx
0x180057b2a  mov     [rsp+310h+var_2F0], eax; int
0x180057b2e  xorps   xmm0, xmm0
0x180057b31  shr     rax, 20h
0x180057b35  mov     [rsp+310h+var_2F0+4], eax
0x180057b39  mov     rax, 0D6BF94D5E57A42BDh
0x180057b43  sub     rcx, qword ptr [rsp+310h+var_2F0]
0x180057b48  mul     rcx
0x180057b4b  shr     rdx, 17h
0x180057b4f  test    rdx, rdx
0x180057b52  js      short loc_180057B5B
0x180057b54  cvtsi2sd xmm0, rdx
0x180057b59  jmp     short loc_180057B70
0x180057b5b  mov     rax, rdx
0x180057b5e  and     edx, 1
0x180057b61  shr     rax, 1
0x180057b64  or      rax, rdx
0x180057b67  cvtsi2sd xmm0, rax
0x180057b6c  addsd   xmm0, xmm0
0x180057b70  subsd   xmm0, cs:__real@4145180000000000
0x180057b78  cvttsd2si rax, xmm0
0x180057b7d  test    rax, rax
0x180057b80  jle     short loc_180057C00
0x180057b82  lea     rcx, [rsp+310h+var_2D8]; this
0x180057b87  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x180057b8c  mov     rcx, [rsp+310h+var_2D8]
0x180057b91  mov     rdx, r15
0x180057b94  call    DefStringResult_SetCopy
0x180057b99  mov     esi, eax
0x180057b9b  test    eax, eax
0x180057b9d  js      loc_180057C6E
0x180057ba3  mov     rcx, [rsp+310h+var_2D8]
0x180057ba8  lea     rdx, [rbp+210h+FindFileData.cFileName]
0x180057bac  mov     r8d, 5Ch ; '\'
0x180057bb2  call    DefStringResult_ConcatPathElement
0x180057bb7  mov     esi, eax
0x180057bb9  test    eax, eax
0x180057bbb  js      loc_180057C67
0x180057bc1  lea     rcx, [rsp+310h+var_2D8]; this
0x180057bc6  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180057bcb  mov     rcx, rax
0x180057bce  mov     rdx, r12
0x180057bd1  mov     r8d, 1
0x180057bd7  call    DefString_CompareWithOptions
0x180057bdc  test    eax, eax
0x180057bde  jz      short loc_180057BF6
0x180057be0  lea     rcx, [rsp+310h+var_2D8]; this
0x180057be5  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180057bea  mov     rcx, rax; lpFileName
0x180057bed  call    cs:__imp_DeleteFileW
0x180057bf3  inc     r14d
0x180057bf6  lea     rcx, [rsp+310h+var_2D8]; this
0x180057bfb  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180057c00  cmp     r14d, 0Ah
0x180057c04  jnb     short loc_180057C1B
0x180057c06  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180057c0a  mov     rcx, rdi; hFindFile
0x180057c0d  call    cs:__imp_FindNextFileW
0x180057c13  test    eax, eax
0x180057c15  jnz     loc_180057B19
0x180057c1b  lea     rax, [rdi-1]
0x180057c1f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180057c23  ja      short loc_180057C2E
0x180057c25  mov     rcx, rdi; hFindFile
0x180057c28  call    cs:__imp_FindClose
0x180057c2e  xor     edi, edi
0x180057c30  lea     rcx, [rsp+310h+var_2B8]; this
0x180057c35  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180057c3a  mov     eax, edi
0x180057c3c  mov     rcx, [rbp+210h+var_30]
0x180057c43  xor     rcx, rsp; StackCookie
0x180057c46  call    __security_check_cookie
0x180057c4b  lea     r11, [rsp+310h+var_20]
0x180057c53  mov     rbx, [r11+40h]
0x180057c57  mov     rsi, [r11+48h]
0x180057c5b  mov     rsp, r11
0x180057c5e  pop     r15
0x180057c60  pop     r14
0x180057c62  pop     r12
0x180057c64  pop     rdi
0x180057c65  pop     rbp
0x180057c66  retn
0x180057c67  mov     edx, 0D8h
0x180057c6c  jmp     short loc_180057C73
0x180057c6e  mov     edx, 0D7h; void *
0x180057c73  mov     rcx, [rbp+218h]; this
0x180057c7a  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x180057c81  mov     r9d, esi; char *
0x180057c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057c89  lea     rcx, [rsp+310h+var_2D8]; this
0x180057c8e  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180057c93  lea     rcx, [rsp+310h+var_2E0]
0x180057c98  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180057c9d  mov     edi, esi
0x180057c9f  jmp     short loc_180057C30
```
