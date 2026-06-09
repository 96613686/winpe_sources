# TryCustomKEKPathFromRegistry(uchar * *,uint *,ushort *)

- ea: `0x18003a308`
- end: `0x18003a530`
- name: `?TryCustomKEKPathFromRegistry@@YAJPEAPEAEPEAIPEAG@Z`
- size: `552`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180037338`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bddc`
- `0x18001be20`
- `0x180036230`
- `0x18003a308`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a4cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a484`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a484`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a38e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a38e`

## string_xrefs

- `0x18003a360`: `CustomKekDirectory`
- `0x18003a3bb`: `Attempting KEK install from custom directory: %s`
- `0x18003a3d6`: `CustomKekUpdate.bin`
- `0x18003a407`: `Custom KEK path construction failed (hr=0x%08X)`
- `0x18003a4b3`: `Custom KEK load from custom directory failed (hr=0x%08X)`
- `0x18003a4fa`: `Custom KEK content loaded from custom directory: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall TryCustomKEKPathFromRegistry(unsigned __int8 **a1, unsigned int *a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  int v7; // eax
  unsigned int v8; // ebx
  int FileContent; // eax
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  HANDLE v17; // rax
  unsigned int v18; // eax
  unsigned int dwBytes; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwBytes_4; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v21[264]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD pvData[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(pvData, 0, 0x208u);
  dwBytes_4 = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
             L"CustomKekDirectory",
             2u,
             0,
             pvData,
             &dwBytes_4);
  *a1 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( ValueW || !pvData[0] )
    return 1;
  SBServicingLogMessage((wchar_t *)L"Attempting KEK install from custom directory: %s", pvData);
  memset_0(v21, 0, 0x208u);
  v7 = StringCchPrintfW(v21, 0x104u, L"%s\\%s", pvData, L"CustomKekUpdate.bin");
  v8 = v7;
  if ( v7 < 0 )
  {
    SBServicingLogMessage((wchar_t *)L"Custom KEK path construction failed (hr=0x%08X)", (unsigned int)v7);
    return v8;
  }
  dwBytes = 0;
  FileContent = GetFileContent(v21, 0, &dwBytes);
  v8 = FileContent;
  if ( FileContent < 0 )
  {
    SBServicingLogMessage((wchar_t *)L"Custom KEK file not found: %s (hr=0x%08X)", v21, (unsigned int)FileContent);
    return v8;
  }
  v11 = dwBytes;
  if ( dwBytes > 0x14 )
  {
    ProcessHeap = GetProcessHeap();
    v13 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, v11);
    v14 = v13;
    if ( v13 )
    {
      v15 = GetFileContent(v21, v13, &dwBytes);
      v16 = v15;
      if ( v15 >= 0 )
      {
        v18 = dwBytes;
        *a1 = v14;
        *a2 = v18;
        StringCchCopyW(a3, 0x104u, v21);
        SBServicingLogMessage((wchar_t *)L"Custom KEK content loaded from custom directory: %s", pvData);
        return 0;
      }
      else
      {
        SBServicingLogMessage((wchar_t *)L"Custom KEK load from custom directory failed (hr=0x%08X)", (unsigned int)v15);
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v14);
        return v16;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"Custom KEK file too small: %s (size=%u)", v21, dwBytes);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x18003a308  push    rbp
0x18003a30a  push    rbx
0x18003a30b  push    rsi
0x18003a30c  push    rdi
0x18003a30d  push    r12
0x18003a30f  push    r14
0x18003a311  push    r15
0x18003a313  lea     rbp, [rsp-380h]
0x18003a31b  sub     rsp, 480h
0x18003a322  mov     rax, cs:__security_cookie
0x18003a329  xor     rax, rsp
0x18003a32c  mov     [rbp+3B0h+var_40], rax
0x18003a333  mov     r15, r8
0x18003a336  mov     r14, rdx
0x18003a339  mov     rsi, rcx
0x18003a33c  mov     ebx, 208h
0x18003a341  mov     r8d, ebx; Size
0x18003a344  lea     rcx, [rbp+3B0h+var_250]; void *
0x18003a34b  xor     edx, edx; Val
0x18003a34d  call    memset_0
0x18003a352  lea     rax, [rsp+4B0h+dwBytes+4]
0x18003a357  mov     [rsp+4B0h+dwBytes+4], ebx
0x18003a35b  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18003a360  lea     r8, aCustomkekdirec; "CustomKekDirectory"
0x18003a367  xor     r12d, r12d
0x18003a36a  lea     rax, [rbp+3B0h+var_250]
0x18003a371  mov     [rsp+4B0h+pvData], rax; pvData
0x18003a376  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003a37d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003a384  mov     [rsp+4B0h+pdwType], r12; pdwType
0x18003a389  lea     r9d, [r12+2]; dwFlags
0x18003a38e  call    cs:__imp_RegGetValueW
0x18003a394  mov     [rsi], r12
0x18003a397  mov     [r14], r12d
0x18003a39a  mov     [r15], r12w
0x18003a39e  test    eax, eax
0x18003a3a0  jnz     loc_18003A50A
0x18003a3a6  cmp     [rbp+3B0h+var_250], r12w
0x18003a3ae  jz      loc_18003A50A
0x18003a3b4  lea     rdx, [rbp+3B0h+var_250]
0x18003a3bb  lea     rcx, aAttemptingKekI; "Attempting KEK install from custom dire"...
0x18003a3c2  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a3c7  mov     r8d, ebx; Size
0x18003a3ca  lea     rcx, [rsp+4B0h+var_460]; void *
0x18003a3cf  xor     edx, edx; Val
0x18003a3d1  call    memset_0
0x18003a3d6  lea     rax, aCustomkekupdat; "CustomKekUpdate.bin"
0x18003a3dd  mov     edx, 104h; unsigned __int64
0x18003a3e2  lea     r9, [rbp+3B0h+var_250]
0x18003a3e9  mov     [rsp+4B0h+pdwType], rax
0x18003a3ee  lea     r8, aSS; "%s\\%s"
0x18003a3f5  lea     rcx, [rsp+4B0h+var_460]; unsigned __int16 *
0x18003a3fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a3ff  mov     ebx, eax
0x18003a401  test    eax, eax
0x18003a403  jns     short loc_18003A41A
0x18003a405  mov     edx, eax
0x18003a407  lea     rcx, aCustomKekPathC; "Custom KEK path construction failed (hr"...
0x18003a40e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a413  mov     eax, ebx
0x18003a415  jmp     loc_18003A50F
0x18003a41a  lea     r8, [rsp+4B0h+dwBytes]; unsigned int *
0x18003a41f  mov     [rsp+4B0h+dwBytes], r12d
0x18003a424  xor     edx, edx; unsigned __int8 *
0x18003a426  lea     rcx, [rsp+4B0h+var_460]; unsigned __int16 *
0x18003a42b  call    ?GetFileContent@@YAJPEBGQEAEPEAK@Z; GetFileContent(ushort const *,uchar * const,ulong *)
0x18003a430  mov     ebx, eax
0x18003a432  test    eax, eax
0x18003a434  jns     short loc_18003A44C
0x18003a436  mov     r8d, eax
0x18003a439  lea     rdx, [rsp+4B0h+var_460]
0x18003a43e  lea     rcx, aCustomKekFileN; "Custom KEK file not found: %s (hr=0x%08"...
0x18003a445  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a44a  jmp     short loc_18003A413
0x18003a44c  mov     ebx, [rsp+4B0h+dwBytes]
0x18003a450  cmp     ebx, 14h
0x18003a453  ja      short loc_18003A473
0x18003a455  mov     r8d, ebx
0x18003a458  lea     rdx, [rsp+4B0h+var_460]
0x18003a45d  lea     rcx, aCustomKekFileT; "Custom KEK file too small: %s (size=%u)"
0x18003a464  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a469  mov     eax, 80070002h
0x18003a46e  jmp     loc_18003A50F
0x18003a473  call    cs:__imp_GetProcessHeap
0x18003a479  mov     r8, rbx; dwBytes
0x18003a47c  mov     edx, 8; dwFlags
0x18003a481  mov     rcx, rax; hHeap
0x18003a484  call    cs:__imp_HeapAlloc
0x18003a48a  mov     rbx, rax
0x18003a48d  test    rax, rax
0x18003a490  jnz     short loc_18003A499
0x18003a492  mov     eax, 8007000Eh
0x18003a497  jmp     short loc_18003A50F
0x18003a499  lea     r8, [rsp+4B0h+dwBytes]; unsigned int *
0x18003a49e  mov     rdx, rbx; unsigned __int8 *
0x18003a4a1  lea     rcx, [rsp+4B0h+var_460]; unsigned __int16 *
0x18003a4a6  call    ?GetFileContent@@YAJPEBGQEAEPEAK@Z; GetFileContent(ushort const *,uchar * const,ulong *)
0x18003a4ab  mov     edi, eax
0x18003a4ad  test    eax, eax
0x18003a4af  jns     short loc_18003A4D7
0x18003a4b1  mov     edx, eax
0x18003a4b3  lea     rcx, aCustomKekLoadF; "Custom KEK load from custom directory f"...
0x18003a4ba  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a4bf  call    cs:__imp_GetProcessHeap
0x18003a4c5  mov     r8, rbx; lpMem
0x18003a4c8  xor     edx, edx; dwFlags
0x18003a4ca  mov     rcx, rax; hHeap
0x18003a4cd  call    cs:__imp_HeapFree
0x18003a4d3  mov     eax, edi
0x18003a4d5  jmp     short loc_18003A50F
0x18003a4d7  mov     eax, [rsp+4B0h+dwBytes]
0x18003a4db  lea     r8, [rsp+4B0h+var_460]; unsigned __int16 *
0x18003a4e0  mov     [rsi], rbx
0x18003a4e3  mov     edx, 104h; unsigned __int64
0x18003a4e8  mov     rcx, r15; unsigned __int16 *
0x18003a4eb  mov     [r14], eax
0x18003a4ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a4f3  lea     rdx, [rbp+3B0h+var_250]
0x18003a4fa  lea     rcx, aCustomKekConte; "Custom KEK content loaded from custom d"...
0x18003a501  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a506  xor     eax, eax
0x18003a508  jmp     short loc_18003A50F
0x18003a50a  mov     eax, 1
0x18003a50f  mov     rcx, [rbp+3B0h+var_40]
0x18003a516  xor     rcx, rsp; StackCookie
0x18003a519  call    __security_check_cookie
0x18003a51e  add     rsp, 480h
0x18003a525  pop     r15
0x18003a527  pop     r14
0x18003a529  pop     r12
0x18003a52b  pop     rdi
0x18003a52c  pop     rsi
0x18003a52d  pop     rbx
0x18003a52e  pop     rbp
0x18003a52f  retn
```
