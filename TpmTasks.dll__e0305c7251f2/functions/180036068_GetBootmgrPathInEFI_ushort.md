# GetBootmgrPathInEFI(ushort * *)

- ea: `0x180036068`
- end: `0x180036227`
- name: `?GetBootmgrPathInEFI@@YAJPEAPEAG@Z`
- size: `447`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037a04`
- `0x180037b10`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x180036068`
- `0x180036f28`
- `0x1800394b0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800361db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800361cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036138`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036138`

## string_xrefs

- `0x1800360bf`: `GetSystemPartition`
- `0x1800361f9`: `GetBootmgrPathInEFI`
- `0x1800361a8`: `SystemPartitionFailure`
- `0x18003619a`: `BootMgrRootPathFailure`
- `0x18003614b`: `lBootmgrPathNULL`
- `0x180036191`: `BootMgrPathFailure`
- `0x1800361e8`: `GetBootmgrPathInEFI failed with error %x actionString %ls`

## pseudocode

```c
__int64 __fastcall GetBootmgrPathInEFI(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rsi
  int SystemPartition; // eax
  unsigned __int16 *v4; // rbp
  int v5; // ebx
  const unsigned __int16 *v6; // rdi
  __int64 v7; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-268h] BYREF
  unsigned __int16 v14[264]; // [rsp+30h] [rbp-258h] BYREF

  lpMem = 0;
  v2 = 0;
  memset_0(v14, 0, 0x208u);
  SystemPartition = GetSystemPartition((unsigned __int16 **)&lpMem);
  v4 = (unsigned __int16 *)lpMem;
  v5 = SystemPartition;
  if ( SystemPartition >= 0 )
  {
    if ( !lpMem )
      goto LABEL_16;
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)lpMem + v7) );
    if ( v7 )
    {
      v5 = StringCchCopyW(v14, 0x104u, L"\\\\.\\");
      if ( v5 < 0 || (v5 = StringCchCatW(v14, 0x104u, v4 + 8), v5 < 0) )
      {
        v6 = L"BootMgrRootPathFailure";
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
        v2 = v9;
        if ( v9 )
        {
          v5 = StringCchCopyW(v9, 0x104u, v14);
          if ( v5 < 0 || (v5 = StringCchCatW(v2, 0x104u, L"\\EFI\\Microsoft\\Boot\\Bootmgfw.efi"), v5 < 0) )
          {
            v6 = L"BootMgrPathFailure";
          }
          else
          {
            *a1 = v2;
            v6 = L"Passed";
            v2 = 0;
          }
        }
        else
        {
          v5 = -2147024882;
          v6 = L"lBootmgrPathNULL";
        }
      }
    }
    else
    {
LABEL_16:
      v5 = -2147467261;
      v6 = L"SystemPartitionFailure";
    }
  }
  else
  {
    v6 = L"GetSystemPartition";
  }
  if ( v4 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
  }
  if ( v2 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v2);
  }
  if ( v5 < 0 )
  {
    SBServicingLogMessage((wchar_t *)L"GetBootmgrPathInEFI failed with error %x actionString %ls", (unsigned int)v5, v6);
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"GetBootmgrPathInEFI", v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180036068  push    rbx
0x18003606a  push    rbp
0x18003606b  push    rsi
0x18003606c  push    rdi
0x18003606d  push    r14
0x18003606f  push    r15
0x180036071  sub     rsp, 258h
0x180036078  mov     rax, cs:__security_cookie
0x18003607f  xor     rax, rsp
0x180036082  mov     [rsp+288h+var_48], rax
0x18003608a  mov     r14, rcx
0x18003608d  xor     r15d, r15d
0x180036090  lea     rcx, [rsp+288h+var_258]; void *
0x180036095  mov     [rsp+288h+lpMem], r15
0x18003609a  xor     edx, edx; Val
0x18003609c  mov     r8d, 208h; Size
0x1800360a2  mov     esi, r15d
0x1800360a5  call    memset_0
0x1800360aa  lea     rcx, [rsp+288h+lpMem]; unsigned __int16 **
0x1800360af  call    ?GetSystemPartition@@YAJPEAPEAG@Z; GetSystemPartition(ushort * *)
0x1800360b4  mov     rbp, [rsp+288h+lpMem]
0x1800360b9  mov     ebx, eax
0x1800360bb  test    eax, eax
0x1800360bd  jns     short loc_1800360CB
0x1800360bf  lea     rdi, aGetsystemparti; "GetSystemPartition"
0x1800360c6  jmp     loc_1800361AF
0x1800360cb  test    rbp, rbp
0x1800360ce  jz      loc_1800361A3
0x1800360d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800360d8  inc     rax
0x1800360db  cmp     [rbp+rax*2+0], r15w
0x1800360e1  jnz     short loc_1800360D8
0x1800360e3  test    rax, rax
0x1800360e6  jz      loc_1800361A3
0x1800360ec  mov     edi, 104h
0x1800360f1  lea     r8, asc_18006FFE8; "\\\\.\\"
0x1800360f8  mov     edx, edi; unsigned __int64
0x1800360fa  lea     rcx, [rsp+288h+var_258]; unsigned __int16 *
0x1800360ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036104  mov     ebx, eax
0x180036106  test    eax, eax
0x180036108  js      loc_18003619A
0x18003610e  lea     r8, [rbp+10h]; unsigned __int16 *
0x180036112  mov     edx, edi; unsigned __int64
0x180036114  lea     rcx, [rsp+288h+var_258]; unsigned __int16 *
0x180036119  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003611e  mov     ebx, eax
0x180036120  test    eax, eax
0x180036122  js      short loc_18003619A
0x180036124  call    cs:__imp_GetProcessHeap
0x18003612a  mov     edx, 8; dwFlags
0x18003612f  mov     r8d, 208h; dwBytes
0x180036135  mov     rcx, rax; hHeap
0x180036138  call    cs:__imp_HeapAlloc
0x18003613e  mov     rsi, rax
0x180036141  test    rax, rax
0x180036144  jnz     short loc_180036154
0x180036146  mov     ebx, 8007000Eh
0x18003614b  lea     rdi, aLbootmgrpathnu; "lBootmgrPathNULL"
0x180036152  jmp     short loc_1800361AF
0x180036154  lea     r8, [rsp+288h+var_258]; unsigned __int16 *
0x180036159  mov     rdx, rdi; unsigned __int64
0x18003615c  mov     rcx, rsi; unsigned __int16 *
0x18003615f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036164  mov     ebx, eax
0x180036166  test    eax, eax
0x180036168  js      short loc_180036191
0x18003616a  lea     r8, aEfiMicrosoftBo_3; "\\EFI\\Microsoft\\Boot\\Bootmgfw.efi"
0x180036171  mov     rdx, rdi; unsigned __int64
0x180036174  mov     rcx, rsi; unsigned __int16 *
0x180036177  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003617c  mov     ebx, eax
0x18003617e  test    eax, eax
0x180036180  js      short loc_180036191
0x180036182  mov     [r14], rsi
0x180036185  lea     rdi, aPassed; "Passed"
0x18003618c  mov     rsi, r15
0x18003618f  jmp     short loc_1800361AF
0x180036191  lea     rdi, aBootmgrpathfai; "BootMgrPathFailure"
0x180036198  jmp     short loc_1800361AF
0x18003619a  lea     rdi, aBootmgrrootpat; "BootMgrRootPathFailure"
0x1800361a1  jmp     short loc_1800361AF
0x1800361a3  mov     ebx, 80004003h
0x1800361a8  lea     rdi, aSystempartitio; "SystemPartitionFailure"
0x1800361af  test    rbp, rbp
0x1800361b2  jz      short loc_1800361C8
0x1800361b4  call    cs:__imp_GetProcessHeap
0x1800361ba  mov     r8, rbp; lpMem
0x1800361bd  xor     edx, edx; dwFlags
0x1800361bf  mov     rcx, rax; hHeap
0x1800361c2  call    cs:__imp_HeapFree
0x1800361c8  test    rsi, rsi
0x1800361cb  jz      short loc_1800361E1
0x1800361cd  call    cs:__imp_GetProcessHeap
0x1800361d3  mov     r8, rsi; lpMem
0x1800361d6  xor     edx, edx; dwFlags
0x1800361d8  mov     rcx, rax; hHeap
0x1800361db  call    cs:__imp_HeapFree
0x1800361e1  test    ebx, ebx
0x1800361e3  jns     short loc_180036205
0x1800361e5  mov     r8, rdi
0x1800361e8  lea     rcx, aGetbootmgrpath; "GetBootmgrPathInEFI failed with error %"...
0x1800361ef  mov     edx, ebx
0x1800361f1  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800361f6  mov     rdx, rdi; unsigned __int16 *
0x1800361f9  lea     rcx, aGetbootmgrpath_0; "GetBootmgrPathInEFI"
0x180036200  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x180036205  mov     eax, ebx
0x180036207  mov     rcx, [rsp+288h+var_48]
0x18003620f  xor     rcx, rsp; StackCookie
0x180036212  call    __security_check_cookie
0x180036217  add     rsp, 258h
0x18003621e  pop     r15
0x180036220  pop     r14
0x180036222  pop     rdi
0x180036223  pop     rsi
0x180036224  pop     rbp
0x180036225  pop     rbx
0x180036226  retn
```
