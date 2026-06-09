# SusDeleteDirectoryW(wchar_t const *,int,int,int,int,int,ulong,void *,int)

- ea: `0x14000eaa8`
- end: `0x14000ec3a`
- name: `?SusDeleteDirectoryW@@YAJPEB_WHHHHHKPEAXH@Z`
- size: `402`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140025e78`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x14000e4f4`
- `0x14000e568`
- `0x14000e788`
- `0x14000eaa8`
- `0x1400154b4`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eb62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eb62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000eb76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000eb76`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x14000eafe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x14000eafe`

## string_xrefs

- `0x14000ebb8`: `SusDeleteDirectoryW deleted directory=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SusDeleteDirectoryW(const wchar_t *a1)
{
  struct _WIN32_FIND_DATAW *v2; // rbx
  __int64 v3; // rdx
  unsigned __int64 v4; // r9
  int v5; // edi
  HANDLE ProcessHeap; // rax
  struct _WIN32_FIND_DATAW *lpFindFileData; // rax
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-60h]
  void *lpMem; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = 0;
  lpMem = 0;
  v13 = 0;
  if ( !a1 || !*a1 )
  {
    v3 = 680;
    goto LABEL_16;
  }
  if ( PathIsRootW(a1) )
  {
    v3 = 681;
LABEL_16:
    v5 = -2147024809;
    goto LABEL_17;
  }
  if ( (unsigned int)HasLocalShortPathPrefix(a1)
    && (v5 = WUAppendPathReAlloc((wchar_t **)&lpMem, &v13, L"\\\\?\\", v4), v5 < 0) )
  {
    v3 = 685;
  }
  else
  {
    v5 = WUAppendPathReAlloc((wchar_t **)&lpMem, &v13, a1, v4);
    if ( v5 >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      lpFindFileData = (struct _WIN32_FIND_DATAW *)HeapAlloc(ProcessHeap, 8u, 0x250u);
      v2 = lpFindFileData;
      if ( lpFindFileData )
      {
        v5 = SusDeleteDirectoryWorker((int)&lpMem, (int)&v13, v8, v9, v11, lpFindFileData);
        if ( v5 >= 0 )
        {
          WUTrace(0, 0, 32, 4, 0, L"SusDeleteDirectoryW deleted directory=%ls");
          v5 = 0;
          goto LABEL_18;
        }
        v3 = 701;
      }
      else
      {
        v5 = -2147024882;
        v3 = 690;
      }
    }
    else
    {
      v3 = 688;
    }
  }
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)(unsigned int)v5,
    v11);
LABEL_18:
  SusFree(lpMem);
  if ( v2 )
    SusFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000eaa8  mov     [rsp-18h+arg_8], rbx
0x14000eaad  mov     [rsp-18h+arg_10], rsi
0x14000eab2  push    rbp
0x14000eab3  push    rdi
0x14000eab4  push    r14
0x14000eab6  mov     rbp, rsp
0x14000eab9  sub     rsp, 80h
0x14000eac0  mov     rax, cs:__security_cookie
0x14000eac7  xor     rax, rsp
0x14000eaca  mov     [rbp+var_8], rax
0x14000eace  mov     rsi, rcx
0x14000ead1  xor     r14d, r14d
0x14000ead4  mov     ebx, r14d
0x14000ead7  mov     [rbp+lpMem], r14
0x14000eadb  mov     [rbp+var_10], r14
0x14000eadf  lea     rax, [rbp+lpMem]
0x14000eae3  mov     [rbp+var_28], rax
0x14000eae7  mov     [rbp+var_20], 1
0x14000eaeb  test    rcx, rcx
0x14000eaee  jz      loc_14000EBDF
0x14000eaf4  cmp     [rcx], r14w
0x14000eaf8  jz      loc_14000EBDF
0x14000eafe  call    cs:__imp_PathIsRootW
0x14000eb04  test    eax, eax
0x14000eb06  jz      short loc_14000EB12
0x14000eb08  mov     edx, 2A9h
0x14000eb0d  jmp     loc_14000EBE4
0x14000eb12  mov     rcx, rsi; wchar_t *
0x14000eb15  call    ?HasLocalShortPathPrefix@@YAHPEB_W@Z; HasLocalShortPathPrefix(wchar_t const *)
0x14000eb1a  test    eax, eax
0x14000eb1c  jz      short loc_14000EB42
0x14000eb1e  lea     r8, asc_140054590; "\\\\?\\"
0x14000eb25  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x14000eb29  lea     rcx, [rbp+lpMem]; wchar_t **
0x14000eb2d  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x14000eb32  mov     edi, eax
0x14000eb34  test    eax, eax
0x14000eb36  jns     short loc_14000EB42
0x14000eb38  mov     edx, 2ADh
0x14000eb3d  jmp     loc_14000EBE9
0x14000eb42  mov     r8, rsi; wchar_t *
0x14000eb45  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x14000eb49  lea     rcx, [rbp+lpMem]; wchar_t **
0x14000eb4d  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x14000eb52  mov     edi, eax
0x14000eb54  test    eax, eax
0x14000eb56  jns     short loc_14000EB62
0x14000eb58  mov     edx, 2B0h
0x14000eb5d  jmp     loc_14000EBE9
0x14000eb62  call    cs:__imp_GetProcessHeap
0x14000eb68  mov     edx, 8; dwFlags
0x14000eb6d  mov     r8d, 250h; dwBytes
0x14000eb73  mov     rcx, rax; hHeap
0x14000eb76  call    cs:__imp_HeapAlloc
0x14000eb7c  mov     rbx, rax
0x14000eb7f  mov     [rbp+var_30], rax
0x14000eb83  test    rax, rax
0x14000eb86  jnz     short loc_14000EB94
0x14000eb88  mov     edi, 8007000Eh
0x14000eb8d  mov     edx, 2B2h
0x14000eb92  jmp     short loc_14000EBE9
0x14000eb94  mov     [rsp+80h+lpFindFileData], rax; lpFindFileData
0x14000eb99  lea     rdx, [rbp+var_10]; int
0x14000eb9d  lea     rcx, [rbp+lpMem]; int
0x14000eba1  call    SusDeleteDirectoryWorker
0x14000eba6  mov     edi, eax
0x14000eba8  test    eax, eax
0x14000ebaa  jns     short loc_14000EBB3
0x14000ebac  mov     edx, 2BDh
0x14000ebb1  jmp     short loc_14000EBE9
0x14000ebb3  mov     [rsp+80h+var_50], rsi
0x14000ebb8  lea     rax, aSusdeletedirec; "SusDeleteDirectoryW deleted directory=%"...
0x14000ebbf  mov     [rsp+80h+lpFindFileData], rax
0x14000ebc4  mov     [rsp+80h+var_60], r14
0x14000ebc9  xor     edx, edx
0x14000ebcb  xor     ecx, ecx
0x14000ebcd  lea     r9d, [rdx+4]
0x14000ebd1  lea     r8d, [rdx+20h]
0x14000ebd5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000ebda  mov     edi, r14d
0x14000ebdd  jmp     short loc_14000EBFD
0x14000ebdf  mov     edx, 2A8h; void *
0x14000ebe4  mov     edi, 80070057h
0x14000ebe9  mov     rcx, [rbp+18h]; this
0x14000ebed  mov     r9d, edi; char *
0x14000ebf0  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000ebf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ebfc  nop
0x14000ebfd  mov     rcx, [rbp+lpMem]; lpMem
0x14000ec01  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14000ec06  nop
0x14000ec07  test    rbx, rbx
0x14000ec0a  jz      short loc_14000EC14
0x14000ec0c  mov     rcx, rbx; lpMem
0x14000ec0f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14000ec14  mov     eax, edi
0x14000ec16  mov     rcx, [rbp+var_8]
0x14000ec1a  xor     rcx, rsp; StackCookie
0x14000ec1d  call    __security_check_cookie
0x14000ec22  lea     r11, [rsp+80h+var_s0]
0x14000ec2a  mov     rbx, [r11+28h]
0x14000ec2e  mov     rsi, [r11+30h]
0x14000ec32  mov     rsp, r11
0x14000ec35  pop     r14
0x14000ec37  pop     rdi
0x14000ec38  pop     rbp
0x14000ec39  retn
```
