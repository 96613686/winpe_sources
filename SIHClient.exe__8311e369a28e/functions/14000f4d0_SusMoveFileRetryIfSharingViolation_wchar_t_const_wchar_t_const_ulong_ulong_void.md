# SusMoveFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,ulong,ulong,void *)

- ea: `0x14000f4d0`
- end: `0x14000f5a3`
- name: `?SusMoveFileRetryIfSharingViolation@@YAJPEB_W0KKPEAX@Z`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400210f0`
- `0x140022f7c`

## callees

- `0x140008de4`
- `0x14000f4d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f4f3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000f52b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000f52b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000f53d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000f53d`

## pseudocode

```c
__int64 __fastcall SusMoveFileRetryIfSharingViolation(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName)
{
  const WCHAR *v2; // rbp
  const WCHAR *v3; // r14
  int v4; // esi
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // edi
  int v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = lpNewFileName;
  v3 = lpExistingFileName;
  v4 = 0;
  while ( 1 )
  {
    if ( MoveFileExW(lpExistingFileName, lpNewFileName, 1u) )
      return 0;
    LastError = GetLastError();
    v6 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v6 = LastError;
    if ( (v6 & 0x80000000) == 0 )
      break;
    v7 = v6;
    if ( v6 != -2147024891 && v6 != -2147024864 )
      goto LABEL_13;
    v8 = v4++;
    if ( v8 == 3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F1,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v6,
        v10);
      return v6;
    }
    Sleep(0x1F4u);
    lpNewFileName = v2;
    lpExistingFileName = v3;
  }
  v7 = -2147418113;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E1,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v7,
    v10);
  return v7;
}

```

## disassembly

```asm
0x14000f4d0  mov     rax, rsp
0x14000f4d3  mov     [rax+8], rbx
0x14000f4d7  mov     [rax+10h], rbp
0x14000f4db  mov     [rax+18h], rsi
0x14000f4df  mov     [rax+20h], rdi
0x14000f4e3  push    r14
0x14000f4e5  sub     rsp, 20h
0x14000f4e9  mov     rbp, rdx
0x14000f4ec  mov     r14, rcx
0x14000f4ef  xor     esi, esi
0x14000f4f1  jmp     short loc_14000F537
0x14000f4f3  call    cs:__imp_GetLastError
0x14000f4f9  movzx   ebx, ax
0x14000f4fc  or      ebx, 80070000h
0x14000f502  test    eax, eax
0x14000f504  cmovle  ebx, eax
0x14000f507  test    ebx, ebx
0x14000f509  jns     short loc_14000F581
0x14000f50b  mov     edi, ebx
0x14000f50d  cmp     ebx, 80070005h
0x14000f513  jz      short loc_14000F51D
0x14000f515  cmp     ebx, 80070020h
0x14000f51b  jnz     short loc_14000F586
0x14000f51d  mov     eax, esi
0x14000f51f  inc     esi
0x14000f521  cmp     eax, 3
0x14000f524  jz      short loc_14000F564
0x14000f526  mov     ecx, 1F4h; dwMilliseconds
0x14000f52b  call    cs:__imp_Sleep
0x14000f531  mov     rdx, rbp; lpNewFileName
0x14000f534  mov     rcx, r14; lpExistingFileName
0x14000f537  mov     r8d, 1; dwFlags
0x14000f53d  call    cs:__imp_MoveFileExW
0x14000f543  test    eax, eax
0x14000f545  jz      short loc_14000F4F3
0x14000f547  xor     eax, eax
0x14000f549  mov     rbx, [rsp+28h+arg_0]
0x14000f54e  mov     rbp, [rsp+28h+arg_8]
0x14000f553  mov     rsi, [rsp+28h+arg_10]
0x14000f558  mov     rdi, [rsp+28h+arg_18]
0x14000f55d  add     rsp, 20h
0x14000f561  pop     r14
0x14000f563  retn
0x14000f564  mov     rcx, [rsp+28h]; this
0x14000f569  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f570  mov     r9d, ebx; char *
0x14000f573  mov     edx, 5F1h; void *
0x14000f578  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f57d  mov     eax, ebx
0x14000f57f  jmp     short loc_14000F549
0x14000f581  mov     edi, 8000FFFFh
0x14000f586  mov     rcx, [rsp+28h]; this
0x14000f58b  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f592  mov     r9d, edi; char *
0x14000f595  mov     edx, 5E1h; void *
0x14000f59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f59f  mov     eax, edi
0x14000f5a1  jmp     short loc_14000F549
```
