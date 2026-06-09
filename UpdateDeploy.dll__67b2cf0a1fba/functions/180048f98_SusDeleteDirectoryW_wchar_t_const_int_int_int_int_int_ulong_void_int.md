# SusDeleteDirectoryW(wchar_t const *,int,int,int,int,int,ulong,void *,int)

- ea: `0x180048f98`
- end: `0x18004912a`
- name: `?SusDeleteDirectoryW@@YAJPEB_WHHHHHKPEAXH@Z`
- size: `402`
- prototype: `__int64 __fastcall(const wchar_t *, int, int, int, int, int, unsigned int, void *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180040a3c`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x18004890c`
- `0x180048980`
- `0x180048c80`
- `0x180048f98`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049052`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049066`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049066`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180048fee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180048fee`

## string_xrefs

- `0x1800490a8`: `SusDeleteDirectoryW deleted directory=%ls`

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
  __int64 v8; // r8
  __int64 v9; // r9
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
        v5 = SusDeleteDirectoryWorker((PCNZWCH *)&lpMem, &v13, v8, v9, v11, lpFindFileData);
        if ( v5 >= 0 )
        {
          WUTrace(0, 0, 32, 4);
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
0x180048f98  mov     [rsp-18h+arg_8], rbx
0x180048f9d  mov     [rsp-18h+arg_10], rsi
0x180048fa2  push    rbp
0x180048fa3  push    rdi
0x180048fa4  push    r14
0x180048fa6  mov     rbp, rsp
0x180048fa9  sub     rsp, 80h
0x180048fb0  mov     rax, cs:__security_cookie
0x180048fb7  xor     rax, rsp
0x180048fba  mov     [rbp+var_8], rax
0x180048fbe  mov     rsi, rcx
0x180048fc1  xor     r14d, r14d
0x180048fc4  mov     ebx, r14d
0x180048fc7  mov     [rbp+lpMem], r14
0x180048fcb  mov     [rbp+var_10], r14
0x180048fcf  lea     rax, [rbp+lpMem]
0x180048fd3  mov     [rbp+var_28], rax
0x180048fd7  mov     [rbp+var_20], 1
0x180048fdb  test    rcx, rcx
0x180048fde  jz      loc_1800490CF
0x180048fe4  cmp     [rcx], r14w
0x180048fe8  jz      loc_1800490CF
0x180048fee  call    cs:__imp_PathIsRootW
0x180048ff4  test    eax, eax
0x180048ff6  jz      short loc_180049002
0x180048ff8  mov     edx, 2A9h
0x180048ffd  jmp     loc_1800490D4
0x180049002  mov     rcx, rsi; wchar_t *
0x180049005  call    ?HasLocalShortPathPrefix@@YAHPEB_W@Z; HasLocalShortPathPrefix(wchar_t const *)
0x18004900a  test    eax, eax
0x18004900c  jz      short loc_180049032
0x18004900e  lea     r8, asc_18007E748; "\\\\?\\"
0x180049015  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180049019  lea     rcx, [rbp+lpMem]; wchar_t **
0x18004901d  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180049022  mov     edi, eax
0x180049024  test    eax, eax
0x180049026  jns     short loc_180049032
0x180049028  mov     edx, 2ADh
0x18004902d  jmp     loc_1800490D9
0x180049032  mov     r8, rsi; wchar_t *
0x180049035  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180049039  lea     rcx, [rbp+lpMem]; wchar_t **
0x18004903d  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180049042  mov     edi, eax
0x180049044  test    eax, eax
0x180049046  jns     short loc_180049052
0x180049048  mov     edx, 2B0h
0x18004904d  jmp     loc_1800490D9
0x180049052  call    cs:__imp_GetProcessHeap
0x180049058  mov     edx, 8; dwFlags
0x18004905d  mov     r8d, 250h; dwBytes
0x180049063  mov     rcx, rax; hHeap
0x180049066  call    cs:__imp_HeapAlloc
0x18004906c  mov     rbx, rax
0x18004906f  mov     [rbp+var_30], rax
0x180049073  test    rax, rax
0x180049076  jnz     short loc_180049084
0x180049078  mov     edi, 8007000Eh
0x18004907d  mov     edx, 2B2h
0x180049082  jmp     short loc_1800490D9
0x180049084  mov     [rsp+80h+lpFindFileData], rax; lpFindFileData
0x180049089  lea     rdx, [rbp+var_10]; int
0x18004908d  lea     rcx, [rbp+lpMem]; int
0x180049091  call    SusDeleteDirectoryWorker
0x180049096  mov     edi, eax
0x180049098  test    eax, eax
0x18004909a  jns     short loc_1800490A3
0x18004909c  mov     edx, 2BDh
0x1800490a1  jmp     short loc_1800490D9
0x1800490a3  mov     [rsp+80h+var_50], rsi
0x1800490a8  lea     rax, aSusdeletedirec; "SusDeleteDirectoryW deleted directory=%"...
0x1800490af  mov     [rsp+80h+lpFindFileData], rax
0x1800490b4  mov     [rsp+80h+var_60], r14
0x1800490b9  xor     edx, edx
0x1800490bb  xor     ecx, ecx
0x1800490bd  lea     r9d, [rdx+4]
0x1800490c1  lea     r8d, [rdx+20h]
0x1800490c5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800490ca  mov     edi, r14d
0x1800490cd  jmp     short loc_1800490ED
0x1800490cf  mov     edx, 2A8h; void *
0x1800490d4  mov     edi, 80070057h
0x1800490d9  mov     rcx, [rbp+18h]; this
0x1800490dd  mov     r9d, edi; char *
0x1800490e0  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800490e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800490ec  nop
0x1800490ed  mov     rcx, [rbp+lpMem]; lpMem
0x1800490f1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800490f6  nop
0x1800490f7  test    rbx, rbx
0x1800490fa  jz      short loc_180049104
0x1800490fc  mov     rcx, rbx; lpMem
0x1800490ff  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180049104  mov     eax, edi
0x180049106  mov     rcx, [rbp+var_8]
0x18004910a  xor     rcx, rsp; StackCookie
0x18004910d  call    __security_check_cookie
0x180049112  lea     r11, [rsp+80h+var_s0]
0x18004911a  mov     rbx, [r11+28h]
0x18004911e  mov     rsi, [r11+30h]
0x180049122  mov     rsp, r11
0x180049125  pop     r14
0x180049127  pop     rdi
0x180049128  pop     rbp
0x180049129  retn
```
