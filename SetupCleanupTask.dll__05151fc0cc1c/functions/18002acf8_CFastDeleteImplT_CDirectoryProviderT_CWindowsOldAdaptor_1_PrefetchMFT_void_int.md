# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::PrefetchMFT(void *,int *)

- ea: `0x18002acf8`
- end: `0x18002aece`
- name: `?PrefetchMFT@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEAH@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18002bae0`

## callees

- `0x180026070`
- `0x180027008`
- `0x180027a90`
- `0x180028a08`
- `0x180028d7c`
- `0x1800293a4`
- `0x18002a3c4`
- `0x18002acf8`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ae52`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ae52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad78`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002ad6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002ad6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ae89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ae70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ae98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ae70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ae98`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::PrefetchMFT(__int64 a1, _DWORD *a2)
{
  int v3; // r8d
  signed int LastError; // eax
  unsigned int v5; // edi
  int v6; // ecx
  int inited; // eax
  const unsigned __int16 *v8; // rdx
  void *v9; // r14
  __int64 v10; // rbx
  __int64 i; // rsi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22[6]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)v19 = 0;
  v21 = 0;
  v20 = 0;
  memset_0(v22, 0, 0x40u);
  v18 = 0;
  v17 = 13;
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v6 = v5;
    goto LABEL_7;
  }
  Buffer[260] = 0;
  inited = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(&v18, (__int64)&v17, v3);
  v5 = inited;
  if ( inited < 0
    || (inited = CNTPrefetcherVolume::Init((CNTPrefetcherVolume *)v19, Buffer), v5 = inited, inited < 0)
    || (inited = CNTPrefetcherFile::InitPath((CNTPrefetcherFile *)v22, v8), v5 = inited, inited < 0)
    || (inited = CNTPrefetcherT<CEmptyType>::Prefetch((int)v19, (int)v22, 1, 5, 0, 0), v5 = inited, inited < 0) )
  {
    v6 = inited;
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_14;
  }
  *a2 = 0;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v18 )
  {
    v9 = (void *)(v18 - 8);
    v10 = *(_QWORD *)(v18 - 8);
    for ( i = v18 + 8 * v10; v10; --v10 )
    {
      i -= 8;
      CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(i);
    }
    operator delete[](v9);
  }
  v12 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    lpMem = 0;
  }
  v14 = v20;
  if ( v20 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)(v14 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v5;
}

```

## disassembly

```asm
0x18002acf8  mov     [rsp-8+arg_0], rbx
0x18002acfd  mov     [rsp-8+arg_10], rsi
0x18002ad02  push    rbp
0x18002ad03  push    rdi
0x18002ad04  push    r14
0x18002ad06  lea     rbp, [rsp-1C0h]
0x18002ad0e  sub     rsp, 2C0h
0x18002ad15  mov     rax, cs:__security_cookie
0x18002ad1c  xor     rax, rsp
0x18002ad1f  mov     [rbp+1D0h+var_20], rax
0x18002ad26  mov     rbx, rdx
0x18002ad29  mov     qword ptr [rsp+2D0h+var_290], 0
0x18002ad32  xor     edx, edx; Val
0x18002ad34  mov     [rsp+2D0h+var_280], 0
0x18002ad3d  lea     rcx, [rsp+2D0h+var_270]; void *
0x18002ad42  mov     [rsp+2D0h+var_288], 0
0x18002ad4b  lea     r8d, [rdx+40h]; Size
0x18002ad4f  call    memset_0
0x18002ad54  mov     edx, 105h; uSize
0x18002ad59  mov     [rsp+2D0h+var_298], 0
0x18002ad62  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x18002ad66  mov     [rsp+2D0h+var_2A0], 0Dh
0x18002ad6e  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002ad74  test    eax, eax
0x18002ad76  jnz     short loc_18002AD9F
0x18002ad78  call    cs:__imp_GetLastError
0x18002ad7e  mov     edi, eax
0x18002ad80  test    eax, eax
0x18002ad82  jnz     short loc_18002AD8B
0x18002ad84  mov     edi, 80004005h
0x18002ad89  jmp     short loc_18002AD96
0x18002ad8b  jle     short loc_18002AD96
0x18002ad8d  movzx   edi, ax
0x18002ad90  or      edi, 80070000h
0x18002ad96  mov     ecx, edi
0x18002ad98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ad9d  jmp     short loc_18002AE1C
0x18002ad9f  xor     eax, eax
0x18002ada1  lea     rdx, [rsp+2D0h+var_2A0]
0x18002ada6  lea     rcx, [rsp+2D0h+var_298]
0x18002adab  mov     [rbp+1D0h+var_28], ax
0x18002adb2  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x18002adb7  mov     edi, eax
0x18002adb9  test    eax, eax
0x18002adbb  jns     short loc_18002ADC1
0x18002adbd  mov     ecx, eax
0x18002adbf  jmp     short loc_18002AD98
0x18002adc1  lea     rdx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x18002adc5  lea     rcx, [rsp+2D0h+var_290]; this
0x18002adca  call    ?Init@CNTPrefetcherVolume@@QEAAJPEBG@Z; CNTPrefetcherVolume::Init(ushort const *)
0x18002adcf  mov     edi, eax
0x18002add1  test    eax, eax
0x18002add3  js      short loc_18002ADBD
0x18002add5  lea     rcx, [rsp+2D0h+var_270]; this
0x18002adda  call    ?InitPath@CNTPrefetcherFile@@QEAAJPEBGHHK@Z; CNTPrefetcherFile::InitPath(ushort const *,int,int,ulong)
0x18002addf  mov     edi, eax
0x18002ade1  test    eax, eax
0x18002ade3  js      short loc_18002ADBD
0x18002ade5  mov     r9d, 5; int
0x18002adeb  mov     qword ptr [rsp+2D0h+var_2A8], 0; int
0x18002adf4  lea     rdx, [rsp+2D0h+var_270]; int
0x18002adf9  mov     [rsp+2D0h+Size], 0; Size
0x18002ae02  lea     rcx, [rsp+2D0h+var_290]; int
0x18002ae07  lea     r8d, [r9-4]; int
0x18002ae0b  call    ?Prefetch@?$CNTPrefetcherT@VCEmptyType@@@@SAJPEBUCNTPrefetcherVolume@@PEBUCNTPrefetcherFile@@KK_JPEAU?$CNTPrefetcherStatsT@VCEmptyType@@@@@Z; CNTPrefetcherT<CEmptyType>::Prefetch(CNTPrefetcherVolume const *,CNTPrefetcherFile const *,ulong,ulong,__int64,CNTPrefetcherStatsT<CEmptyType> *)
0x18002ae10  mov     edi, eax
0x18002ae12  test    eax, eax
0x18002ae14  js      short loc_18002ADBD
0x18002ae16  mov     dword ptr [rbx], 0
0x18002ae1c  mov     ecx, edi
0x18002ae1e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ae23  mov     rax, [rsp+2D0h+var_298]
0x18002ae28  test    rax, rax
0x18002ae2b  jz      short loc_18002AE58
0x18002ae2d  lea     r14, [rax-8]
0x18002ae31  mov     rbx, [r14]
0x18002ae34  lea     rsi, [rax+rbx*8]
0x18002ae38  test    rbx, rbx
0x18002ae3b  jz      short loc_18002AE4F
0x18002ae3d  sub     rsi, 8
0x18002ae41  mov     rcx, rsi
0x18002ae44  call    ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x18002ae49  sub     rbx, 1
0x18002ae4d  jnz     short loc_18002AE3D
0x18002ae4f  mov     rcx, r14
0x18002ae52  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ae58  mov     rbx, [rsp+2D0h+lpMem]
0x18002ae5d  test    rbx, rbx
0x18002ae60  jz      short loc_18002AE7F
0x18002ae62  call    cs:__imp_GetProcessHeap
0x18002ae68  mov     r8, rbx; lpMem
0x18002ae6b  xor     edx, edx; dwFlags
0x18002ae6d  mov     rcx, rax; hHeap
0x18002ae70  call    cs:__imp_HeapFree
0x18002ae76  mov     [rsp+2D0h+lpMem], 0
0x18002ae7f  mov     rbx, [rsp+2D0h+var_288]
0x18002ae84  test    rbx, rbx
0x18002ae87  jz      short loc_18002AEA5
0x18002ae89  call    cs:__imp_GetProcessHeap
0x18002ae8f  lea     r8, [rbx-4]; lpMem
0x18002ae93  xor     edx, edx; dwFlags
0x18002ae95  mov     rcx, rax; hHeap
0x18002ae98  call    cs:__imp_HeapFree
0x18002ae9e  xor     ecx, ecx
0x18002aea0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002aea5  mov     eax, edi
0x18002aea7  mov     rcx, [rbp+1D0h+var_20]
0x18002aeae  xor     rcx, rsp; StackCookie
0x18002aeb1  call    __security_check_cookie
0x18002aeb6  lea     r11, [rsp+2D0h+var_10]
0x18002aebe  mov     rbx, [r11+20h]
0x18002aec2  mov     rsi, [r11+30h]
0x18002aec6  mov     rsp, r11
0x18002aec9  pop     r14
0x18002aecb  pop     rdi
0x18002aecc  pop     rbp
0x18002aecd  retn
```
