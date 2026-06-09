# VolumeUtil::GetVolumeIdForPath(wchar_t const *,unsigned __int64,wchar_t *)

- ea: `0x18004bcd4`
- end: `0x18004bd87`
- name: `?GetVolumeIdForPath@VolumeUtil@@YAJPEB_W_KPEA_W@Z`
- size: `179`
- prototype: `int(VolumeUtil *__hidden this, const wchar_t *, unsigned __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180020b5c`

## callees

- `0x180003180`
- `0x18004bc3c`
- `0x18004bcd4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd52`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004bcfd`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004bcfd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004bd48`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004bd48`

## pseudocode

```c
__int64 __fastcall VolumeUtil::GetVolumeIdForPath(const WCHAR *this, const wchar_t *a2, WCHAR *a3, wchar_t *a4)
{
  DWORD LastError; // eax
  unsigned int v6; // edx
  int LastVolumeApiErrorHr; // ebx
  __int64 v8; // rdx
  DWORD v10; // eax
  unsigned int v11; // edx
  int szVolumePathName[132]; // [rsp+20h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( !GetVolumePathNameW(this, (LPWSTR)szVolumePathName, 0x104u) )
  {
    LastError = GetLastError();
    LastVolumeApiErrorHr = VolumeUtil::GetLastVolumeApiErrorHr((VolumeUtil *)LastError, v6);
    if ( LastVolumeApiErrorHr >= 0 )
      return (unsigned int)LastVolumeApiErrorHr;
    v8 = 113;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\volumeutil.cpp",
      (const char *)(unsigned int)LastVolumeApiErrorHr,
      szVolumePathName[0]);
    return (unsigned int)LastVolumeApiErrorHr;
  }
  if ( !GetVolumeNameForVolumeMountPointW((LPCWSTR)szVolumePathName, a3, 0x33u) )
  {
    v10 = GetLastError();
    LastVolumeApiErrorHr = VolumeUtil::GetLastVolumeApiErrorHr((VolumeUtil *)v10, v11);
    if ( LastVolumeApiErrorHr >= 0 )
      return (unsigned int)LastVolumeApiErrorHr;
    v8 = 117;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18004bcd4  push    rbx
0x18004bcd6  sub     rsp, 240h
0x18004bcdd  mov     rax, cs:__security_cookie
0x18004bce4  xor     rax, rsp
0x18004bce7  mov     [rsp+248h+var_18], rax
0x18004bcef  mov     rbx, r8
0x18004bcf2  lea     rdx, [rsp+248h+szVolumePathName]; lpszVolumePathName
0x18004bcf7  mov     r8d, 104h; cchBufferLength
0x18004bcfd  call    cs:__imp_GetVolumePathNameW
0x18004bd03  test    eax, eax
0x18004bd05  jnz     short loc_18004BD3A
0x18004bd07  call    cs:__imp_GetLastError
0x18004bd0d  mov     ecx, eax; this
0x18004bd0f  call    ?GetLastVolumeApiErrorHr@VolumeUtil@@YAJK@Z; VolumeUtil::GetLastVolumeApiErrorHr(ulong)
0x18004bd14  mov     ebx, eax
0x18004bd16  test    eax, eax
0x18004bd18  jns     short loc_18004BD36
0x18004bd1a  mov     edx, 71h ; 'q'; void *
0x18004bd1f  mov     rcx, [rsp+248h]; this
0x18004bd27  lea     r8, aCW1SSrcClientL_7; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004bd2e  mov     r9d, ebx; char *
0x18004bd31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd36  mov     eax, ebx
0x18004bd38  jmp     short loc_18004BD6E
0x18004bd3a  mov     r8d, 33h ; '3'; cchBufferLength
0x18004bd40  lea     rcx, [rsp+248h+szVolumePathName]; lpszVolumeMountPoint
0x18004bd45  mov     rdx, rbx; lpszVolumeName
0x18004bd48  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004bd4e  test    eax, eax
0x18004bd50  jnz     short loc_18004BD6C
0x18004bd52  call    cs:__imp_GetLastError
0x18004bd58  mov     ecx, eax; this
0x18004bd5a  call    ?GetLastVolumeApiErrorHr@VolumeUtil@@YAJK@Z; VolumeUtil::GetLastVolumeApiErrorHr(ulong)
0x18004bd5f  mov     ebx, eax
0x18004bd61  test    eax, eax
0x18004bd63  jns     short loc_18004BD36
0x18004bd65  mov     edx, 75h ; 'u'
0x18004bd6a  jmp     short loc_18004BD1F
0x18004bd6c  xor     eax, eax
0x18004bd6e  mov     rcx, [rsp+248h+var_18]
0x18004bd76  xor     rcx, rsp; StackCookie
0x18004bd79  call    __security_check_cookie
0x18004bd7e  add     rsp, 240h
0x18004bd85  pop     rbx
0x18004bd86  retn
```
