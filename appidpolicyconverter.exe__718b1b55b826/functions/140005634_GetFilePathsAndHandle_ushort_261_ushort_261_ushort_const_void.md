# GetFilePathsAndHandle(ushort (&)[261],ushort (&)[261],ushort const *,void * *)

- ea: `0x140005634`
- end: `0x14000578a`
- name: `?GetFilePathsAndHandle@@YAKAEAY0BAF@G0PEBGPEAPEAX@Z`
- size: `342`
- prototype: `DWORD __fastcall(WCHAR *, unsigned __int16 (*)[261], const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006154`
- `0x1400064f8`

## callees

- `0x140005634`
- `0x1400059dc`
- `0x140005a50`
- `0x1400073a8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005713`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005713`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400056e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400056e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000565c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000571f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000565c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000571f`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140005652`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140005652`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005731`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140005731`

## string_xrefs

- `0x140005674`: `\System32\AppLocker\`

## pseudocode

```c
DWORD __fastcall GetFilePathsAndHandle(WCHAR *a1, unsigned __int16 (*a2)[261], const unsigned __int16 *a3, void **a4)
{
  UINT WindowsDirectoryW; // eax
  unsigned int i; // edi
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  int v13; // r8d

  WindowsDirectoryW = GetWindowsDirectoryW(a1, 0x104u);
  if ( !WindowsDirectoryW )
    return GetLastError();
  if ( WindowsDirectoryW >= 0x104 )
    return 122;
  if ( StringCbCatW(a1, 0x20Au, L"\\System32\\AppLocker\\") < 0 )
    return 122;
  if ( StringCbCatW(a1, 0x20Au, a3) < 0 )
    return 122;
  StringCbCopyW((unsigned __int16 *)a2, 0x20Au, a1);
  if ( StringCbCatW((unsigned __int16 *)a2, 0x20Au, L".New") < 0 || StringCbCatW(a1, 0x20Au, L".AppLocker") < 0 )
    return 122;
  DeleteFileW((LPCWSTR)a2);
  for ( i = 0; i < 0xA; ++i )
  {
    FileW = CreateFileW((LPCWSTR)a2, 0x10000000u, 0, 0, 2u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      *a4 = FileW;
      return 0;
    }
    LastError = GetLastError();
    if ( LastError != 32 )
      break;
    Sleep(0x3E8u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v13, (_DWORD)a2, LastError);
  return LastError;
}

```

## disassembly

```asm
0x140005634  push    rbx
0x140005636  push    rbp
0x140005637  push    rsi
0x140005638  push    rdi
0x140005639  push    r14
0x14000563b  sub     rsp, 40h
0x14000563f  mov     rsi, rdx
0x140005642  mov     ebp, 104h
0x140005647  mov     edx, ebp; uSize
0x140005649  mov     r14, r9
0x14000564c  mov     rdi, r8
0x14000564f  mov     rbx, rcx
0x140005652  call    cs:__imp_GetWindowsDirectoryW
0x140005658  test    eax, eax
0x14000565a  jnz     short loc_140005667
0x14000565c  call    cs:__imp_GetLastError
0x140005662  jmp     loc_14000577F
0x140005667  cmp     eax, ebp
0x140005669  jnb     loc_14000577A
0x14000566f  mov     ebp, 20Ah
0x140005674  lea     r8, aSystem32Apploc_1; "\\System32\\AppLocker\\"
0x14000567b  mov     edx, ebp; unsigned __int64
0x14000567d  mov     rcx, rbx; unsigned __int16 *
0x140005680  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140005685  test    eax, eax
0x140005687  js      loc_14000577A
0x14000568d  mov     r8, rdi; unsigned __int16 *
0x140005690  mov     edx, ebp; unsigned __int64
0x140005692  mov     rcx, rbx; unsigned __int16 *
0x140005695  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14000569a  test    eax, eax
0x14000569c  js      loc_14000577A
0x1400056a2  mov     r8, rbx; unsigned __int16 *
0x1400056a5  mov     edx, ebp; unsigned __int64
0x1400056a7  mov     rcx, rsi; unsigned __int16 *
0x1400056aa  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400056af  lea     r8, aNew; ".New"
0x1400056b6  mov     edx, ebp; unsigned __int64
0x1400056b8  mov     rcx, rsi; unsigned __int16 *
0x1400056bb  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400056c0  test    eax, eax
0x1400056c2  js      loc_14000577A
0x1400056c8  lea     r8, aApplocker; ".AppLocker"
0x1400056cf  mov     edx, ebp; unsigned __int64
0x1400056d1  mov     rcx, rbx; unsigned __int16 *
0x1400056d4  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400056d9  test    eax, eax
0x1400056db  js      loc_14000577A
0x1400056e1  mov     rcx, rsi; lpFileName
0x1400056e4  call    cs:__imp_DeleteFileW
0x1400056ea  xor     edi, edi
0x1400056ec  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1400056f5  xor     r9d, r9d; lpSecurityAttributes
0x1400056f8  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140005700  xor     r8d, r8d; dwShareMode
0x140005703  mov     edx, 10000000h; dwDesiredAccess
0x140005708  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x140005710  mov     rcx, rsi; lpFileName
0x140005713  call    cs:__imp_CreateFileW
0x140005719  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000571d  jnz     short loc_140005773
0x14000571f  call    cs:__imp_GetLastError
0x140005725  mov     ebx, eax
0x140005727  cmp     eax, 20h ; ' '
0x14000572a  jnz     short loc_14000573E
0x14000572c  mov     ecx, 3E8h; dwMilliseconds
0x140005731  call    cs:__imp_Sleep
0x140005737  inc     edi
0x140005739  cmp     edi, 0Ah
0x14000573c  jb      short loc_1400056EC
0x14000573e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005745  lea     rax, WPP_GLOBAL_Control
0x14000574c  cmp     rcx, rax
0x14000574f  jz      short loc_14000576F
0x140005751  test    dword ptr [rcx+1Ch], 800h
0x140005758  jz      short loc_14000576F
0x14000575a  mov     rcx, [rcx+10h]
0x14000575e  mov     edx, 36h ; '6'
0x140005763  mov     r9, rsi
0x140005766  mov     [rsp+68h+dwCreationDisposition], ebx
0x14000576a  call    WPP_SF_Sd
0x14000576f  mov     eax, ebx
0x140005771  jmp     short loc_14000577F
0x140005773  mov     [r14], rax
0x140005776  xor     eax, eax
0x140005778  jmp     short loc_14000577F
0x14000577a  mov     eax, 7Ah ; 'z'
0x14000577f  add     rsp, 40h
0x140005783  pop     r14
0x140005785  pop     rdi
0x140005786  pop     rsi
0x140005787  pop     rbp
0x140005788  pop     rbx
0x140005789  retn
```
