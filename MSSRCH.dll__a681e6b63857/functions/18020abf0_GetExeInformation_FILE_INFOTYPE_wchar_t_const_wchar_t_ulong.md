# GetExeInformation(FILE_INFOTYPE,wchar_t const *,wchar_t *,ulong)

- ea: `0x18020abf0`
- end: `0x18020ae43`
- name: `?GetExeInformation@@YAHW4FILE_INFOTYPE@@PEB_WPEA_WK@Z`
- size: `595`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800534dc`

## callees

- `0x18000c4cc`
- `0x18009491c`
- `0x1801244c0`
- `0x18020abf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020ae15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020ae15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18020ac99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18020ac99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18020ac8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18020ae07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18020ac8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18020ae07`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18020add1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18020add1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18020ac45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18020ac45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18020addb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18020addb`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18020acc1`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18020acc1`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18020ac7a`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18020ac7a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ace3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ad3f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ad7a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020adb5`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ace3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ad3f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020ad7a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18020adb5`

## pseudocode

```c
_BOOL8 __fastcall GetExeInformation(__int64 a1, const WCHAR *a2, wchar_t *a3, unsigned int a4)
{
  unsigned __int64 v4; // r14
  void *v7; // rbx
  DWORD FileVersionInfoSize; // edi
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  size_t *FileNameW; // r8
  int v12; // edi
  HANDLE v13; // rax
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID v18; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubBlock[64]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR wstrFilename[264]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = a4;
  puLen = 0;
  v18 = 0;
  dwHandle = 0;
  lpBuffer = 0;
  if ( !PathFileExistsW(a2) )
    return 0;
  v7 = 0;
  if ( (int)StringCchCopyW(wstrFilename, 0x104u, a2) >= 0 )
  {
    FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, wstrFilename, &dwHandle);
    if ( FileVersionInfoSize )
    {
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSize);
      v7 = v10;
      if ( v10 )
      {
        if ( GetFileVersionInfoExW(3u, wstrFilename, dwHandle, FileVersionInfoSize, v10) )
        {
          if ( !VerQueryValueW(v7, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen)
            || !puLen
            || (LODWORD(lpData) = *((unsigned __int16 *)lpBuffer + 1),
                (int)StringCchPrintfW(
                       SubBlock,
                       0x3Cu,
                       L"\\StringFileInfo\\%04X%04X\\%s",
                       *(unsigned __int16 *)lpBuffer,
                       lpData,
                       L"FileDescription") < 0)
            || !VerQueryValueW(v7, SubBlock, &v18, &puLen) )
          {
            if ( ((int)StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\040904E4\\%s", L"FileDescription") < 0
               || !VerQueryValueW(v7, SubBlock, &v18, &puLen))
              && (int)StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\04090000\\%s", L"FileDescription") >= 0 )
            {
              VerQueryValueW(v7, SubBlock, &v18, &puLen);
            }
          }
        }
      }
    }
  }
  FileNameW = (size_t *)v18;
  if ( !v18 || !*(_WORD *)v18 )
  {
    PathRemoveExtensionW(wstrFilename);
    FileNameW = (size_t *)PathFindFileNameW(wstrFilename);
    v18 = FileNameW;
  }
  if ( !FileNameW )
    FileNameW = (size_t *)&cchOriginalDestLength;
  v12 = StringCchCopyW(a3, v4, (const wchar_t *)FileNameW);
  if ( v7 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v7);
  }
  return v12 >= 0;
}

```

## disassembly

```asm
0x18020abf0  push    rbp
0x18020abf2  push    rbx
0x18020abf3  push    rsi
0x18020abf4  push    rdi
0x18020abf5  push    r14
0x18020abf7  lea     rbp, [rsp-1F0h]
0x18020abff  sub     rsp, 2F0h
0x18020ac06  mov     rax, cs:__security_cookie
0x18020ac0d  xor     rax, rsp
0x18020ac10  mov     [rbp+210h+var_30], rax
0x18020ac17  mov     rcx, rdx; pszPath
0x18020ac1a  mov     r14d, r9d
0x18020ac1d  mov     rsi, r8
0x18020ac20  mov     [rsp+310h+puLen], 0
0x18020ac28  mov     rdi, rdx
0x18020ac2b  mov     [rsp+310h+var_2D8], 0
0x18020ac34  mov     [rsp+310h+dwHandle], 0
0x18020ac3c  mov     [rsp+310h+lpBuffer], 0
0x18020ac45  call    cs:__imp_PathFileExistsW
0x18020ac4b  test    eax, eax
0x18020ac4d  jz      loc_18020AE24
0x18020ac53  mov     r8, rdi; wchar_t *
0x18020ac56  lea     rcx, [rbp+210h+wstrFilename]; wchar_t *
0x18020ac5a  mov     edx, 104h; unsigned __int64
0x18020ac5f  xor     ebx, ebx
0x18020ac61  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18020ac66  test    eax, eax
0x18020ac68  js      loc_18020ADBB
0x18020ac6e  lea     r8, [rsp+310h+dwHandle]; lpdwHandle
0x18020ac73  lea     rdx, [rbp+210h+wstrFilename]; lpwstrFilename
0x18020ac77  lea     ecx, [rbx+1]; dwFlags
0x18020ac7a  call    cs:__imp_GetFileVersionInfoSizeExW
0x18020ac80  mov     edi, eax
0x18020ac82  test    eax, eax
0x18020ac84  jz      loc_18020ADBB
0x18020ac8a  call    cs:__imp_GetProcessHeap
0x18020ac90  mov     r8d, edi; dwBytes
0x18020ac93  lea     edx, [rbx+8]; dwFlags
0x18020ac96  mov     rcx, rax; hHeap
0x18020ac99  call    cs:__imp_HeapAlloc
0x18020ac9f  mov     rbx, rax
0x18020aca2  test    rax, rax
0x18020aca5  jz      loc_18020ADBB
0x18020acab  mov     r8d, [rsp+310h+dwHandle]; dwHandle
0x18020acb0  lea     rdx, [rbp+210h+wstrFilename]; lpwstrFilename
0x18020acb4  mov     r9d, edi; dwLen
0x18020acb7  mov     [rsp+310h+lpData], rax; lpData
0x18020acbc  mov     ecx, 3; dwFlags
0x18020acc1  call    cs:__imp_GetFileVersionInfoExW
0x18020acc7  test    eax, eax
0x18020acc9  jz      loc_18020ADBB
0x18020accf  lea     r9, [rsp+310h+puLen]; puLen
0x18020acd4  mov     rcx, rbx; pBlock
0x18020acd7  lea     r8, [rsp+310h+lpBuffer]; lplpBuffer
0x18020acdc  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18020ace3  call    cs:__imp_VerQueryValueW
0x18020ace9  mov     edi, 3Ch ; '<'
0x18020acee  test    eax, eax
0x18020acf0  jz      short loc_18020AD49
0x18020acf2  cmp     [rsp+310h+puLen], 0
0x18020acf7  jbe     short loc_18020AD49
0x18020acf9  mov     rax, [rsp+310h+lpBuffer]
0x18020acfe  lea     r8, aStringfileinfo_0; "\\StringFileInfo\\%04X%04X\\%s"
0x18020ad05  mov     edx, edi; unsigned __int64
0x18020ad07  movzx   ecx, word ptr [rax+2]
0x18020ad0b  movzx   r9d, word ptr [rax]
0x18020ad0f  mov     rax, cs:off_180254970; "FileDescription"
0x18020ad16  mov     [rsp+310h+var_2E8], rax
0x18020ad1b  mov     dword ptr [rsp+310h+lpData], ecx
0x18020ad1f  lea     rcx, [rsp+310h+SubBlock]; wchar_t *
0x18020ad24  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18020ad29  test    eax, eax
0x18020ad2b  js      short loc_18020AD49
0x18020ad2d  lea     r9, [rsp+310h+puLen]; puLen
0x18020ad32  mov     rcx, rbx; pBlock
0x18020ad35  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x18020ad3a  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x18020ad3f  call    cs:__imp_VerQueryValueW
0x18020ad45  test    eax, eax
0x18020ad47  jnz     short loc_18020ADBB
0x18020ad49  mov     r9, cs:off_180254970; "FileDescription"
0x18020ad50  lea     r8, aStringfileinfo_1; "\\StringFileInfo\\040904E4\\%s"
0x18020ad57  mov     rdx, rdi; unsigned __int64
0x18020ad5a  lea     rcx, [rsp+310h+SubBlock]; wchar_t *
0x18020ad5f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18020ad64  test    eax, eax
0x18020ad66  js      short loc_18020AD84
0x18020ad68  lea     r9, [rsp+310h+puLen]; puLen
0x18020ad6d  mov     rcx, rbx; pBlock
0x18020ad70  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x18020ad75  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x18020ad7a  call    cs:__imp_VerQueryValueW
0x18020ad80  test    eax, eax
0x18020ad82  jnz     short loc_18020ADBB
0x18020ad84  mov     r9, cs:off_180254970; "FileDescription"
0x18020ad8b  lea     r8, aStringfileinfo; "\\StringFileInfo\\04090000\\%s"
0x18020ad92  mov     rdx, rdi; unsigned __int64
0x18020ad95  lea     rcx, [rsp+310h+SubBlock]; wchar_t *
0x18020ad9a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18020ad9f  test    eax, eax
0x18020ada1  js      short loc_18020ADBB
0x18020ada3  lea     r9, [rsp+310h+puLen]; puLen
0x18020ada8  mov     rcx, rbx; pBlock
0x18020adab  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x18020adb0  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x18020adb5  call    cs:__imp_VerQueryValueW
0x18020adbb  mov     r8, [rsp+310h+var_2D8]
0x18020adc0  test    r8, r8
0x18020adc3  jz      short loc_18020ADCD
0x18020adc5  xor     eax, eax
0x18020adc7  cmp     ax, [r8]
0x18020adcb  jnz     short loc_18020ADE9
0x18020adcd  lea     rcx, [rbp+210h+wstrFilename]; pszPath
0x18020add1  call    cs:__imp_PathRemoveExtensionW
0x18020add7  lea     rcx, [rbp+210h+wstrFilename]; pszPath
0x18020addb  call    cs:__imp_PathFindFileNameW
0x18020ade1  mov     r8, rax
0x18020ade4  mov     [rsp+310h+var_2D8], rax
0x18020ade9  mov     rdx, r14; unsigned __int64
0x18020adec  mov     rcx, rsi; wchar_t *
0x18020adef  test    r8, r8
0x18020adf2  jnz     short loc_18020ADFB
0x18020adf4  lea     r8, cchOriginalDestLength; wchar_t *
0x18020adfb  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18020ae00  mov     edi, eax
0x18020ae02  test    rbx, rbx
0x18020ae05  jz      short loc_18020AE1B
0x18020ae07  call    cs:__imp_GetProcessHeap
0x18020ae0d  mov     r8, rbx; lpMem
0x18020ae10  xor     edx, edx; dwFlags
0x18020ae12  mov     rcx, rax; hHeap
0x18020ae15  call    cs:__imp_HeapFree
0x18020ae1b  xor     eax, eax
0x18020ae1d  test    edi, edi
0x18020ae1f  setns   al
0x18020ae22  jmp     short loc_18020AE26
0x18020ae24  xor     eax, eax
0x18020ae26  mov     rcx, [rbp+210h+var_30]
0x18020ae2d  xor     rcx, rsp; StackCookie
0x18020ae30  call    __security_check_cookie
0x18020ae35  add     rsp, 2F0h
0x18020ae3c  pop     r14
0x18020ae3e  pop     rdi
0x18020ae3f  pop     rsi
0x18020ae40  pop     rbx
0x18020ae41  pop     rbp
0x18020ae42  retn
```
