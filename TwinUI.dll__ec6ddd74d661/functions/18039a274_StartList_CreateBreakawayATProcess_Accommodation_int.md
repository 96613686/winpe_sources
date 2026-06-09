# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x18039a274`
- end: `0x18039a652`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `990`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18039bec4`

## callees

- `0x18002fb8c`
- `0x180136c44`
- `0x180143a7c`
- `0x180398a40`
- `0x1803992d4`
- `0x180399bec`
- `0x18039a274`
- `0x18039a88c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a388`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a45a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a46f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a61e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a388`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a45a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a46f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039a61e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18039a501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18039a501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18039a60e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18039a60e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18039a4ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18039a5fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18039a4ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18039a5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039a31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039a31e`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18039a5e9`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18039a5e9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18039a557`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18039a557`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18039a4dd`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18039a522`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18039a4dd`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18039a522`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18039a5a7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18039a5a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039a5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039a5ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039a5be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039a5ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18039a30e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18039a30e`

## string_xrefs

- `0x18039a3c9`: `/launchnarratorupdates`
- `0x18039a2c0`: `%SystemRoot%\System32\ATBroker.exe`
- `0x18039a307`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(WCHAR *this, struct Accommodation *a2, int a3)
{
  LPWSTR v6; // rbx
  DWORD v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  LPWSTR v11; // rbx
  char IsEnabled; // al
  char v13; // dl
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  const WCHAR *v16; // rdx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // eax
  const WCHAR *v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned int v22; // ecx
  int v23; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v24; // r14
  SIZE_T v25; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v29; // rcx
  HANDLE v30; // rax
  const WCHAR *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const WCHAR *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  void *Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v37; // [rsp+F0h] [rbp+2Fh]
  LPWSTR lpDst; // [rsp+128h] [rbp+67h] BYREF
  void *Block; // [rsp+140h] [rbp+7Fh] BYREF

  lpDst = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  lpDst = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, 0x7FFFFFFFu, (unsigned __int64 *)&lpDst) >= 0 )
  {
    v6 = lpDst + 130;
    if ( lpDst + 130 >= lpDst )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, v6) )
      {
        v7 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, lpDst, (DWORD)v6);
        if ( !v7 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
        if ( v7 > (unsigned __int64)v6 )
        {
          v9 = -2147024774;
LABEL_32:
          free(lpDst);
          return v9;
        }
        v10 = (unsigned __int64)(v6 + 11);
        if ( v6 + 11 >= v6 )
        {
          v11 = v6 + 141;
          if ( v10 + 260 >= v10 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v10 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v13 = *((_BYTE *)a2 + 85);
            v14 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v13 )
                v14 = &pszDefault;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = &pszDefault;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = &pszDefault;
              lpPreviousValue = v16;
              v17 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v17,
                      L"%s /start %s %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValue,
                      v15,
                      v14);
            }
            else
            {
              if ( !v13 )
                v14 = &pszDefault;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = &pszDefault;
              lpPreviousValuea = v20;
              v21 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v21,
                      L"%s /start %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValuea,
                      v14);
            }
            if ( v19 >= 0 )
            {
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
              StartupInfo.cb = 112;
              Value = 0;
              v23 = 0;
              v24 = 0;
              Size = 0;
              if ( a3 )
              {
                if ( (int)GetShellProcessHandle(v22, &Value) >= 0 )
                {
                  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                  v25 = Size;
                  ProcessHeap = GetProcessHeap();
                  v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v25);
                  v24 = v27;
                  if ( v27 )
                  {
                    if ( InitializeProcThreadAttributeList(v27, 1u, 0, &Size) )
                    {
                      v23 = 1;
                      updated = UpdateProcThreadAttribute(v24, 0, 0x20000u, &Value, 8u, 0, 0);
                      v29 = v37;
                      if ( updated )
                        v29 = v24;
                      v37 = v29;
                    }
                  }
                }
              }
              if ( CreateProcessW(lpDst, v18, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                v9 = 0;
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
              else
              {
                v9 = -2147467259;
              }
              if ( v23 )
                DeleteProcThreadAttributeList(v24);
              if ( v24 )
              {
                v30 = GetProcessHeap();
                HeapFree(v30, 0, v24);
              }
              free(v18);
              goto LABEL_32;
            }
            free(v18);
          }
        }
        v9 = -2147467259;
        goto LABEL_32;
      }
LABEL_15:
      v9 = -2147024882;
      goto LABEL_32;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18039a274  mov     rax, rsp
0x18039a277  mov     [rax+10h], rbx
0x18039a27b  mov     [rax+18h], rsi
0x18039a27f  mov     [rax+8], rcx
0x18039a283  push    rbp
0x18039a284  push    r12
0x18039a286  push    r13
0x18039a288  push    r14
0x18039a28a  push    r15
0x18039a28c  lea     rbp, [rax-5Fh]
0x18039a290  sub     rsp, 0F0h
0x18039a297  mov     r12d, r8d
0x18039a29a  mov     rsi, rdx
0x18039a29d  mov     rcx, rdx; this
0x18039a2a0  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x18039a2a5  xor     r13d, r13d
0x18039a2a8  test    eax, eax
0x18039a2aa  jz      short loc_18039A2B3
0x18039a2ac  xor     eax, eax
0x18039a2ae  jmp     loc_18039A634
0x18039a2b3  mov     [rbp+57h+lpDst], r13
0x18039a2b7  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x18039a2bb  mov     edx, 7FFFFFFFh; unsigned __int64
0x18039a2c0  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x18039a2c7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18039a2cc  test    eax, eax
0x18039a2ce  js      loc_18039A62F
0x18039a2d4  mov     rax, [rbp+57h+lpDst]
0x18039a2d8  lea     rbx, [rax+104h]
0x18039a2df  cmp     rbx, rax
0x18039a2e2  jb      loc_18039A62F
0x18039a2e8  mov     [rbp+57h+lpDst], r13
0x18039a2ec  mov     rdx, rbx
0x18039a2ef  lea     rcx, [rbp+57h+lpDst]
0x18039a2f3  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18039a2f8  test    al, al
0x18039a2fa  jz      loc_18039A394
0x18039a300  mov     r8d, ebx; nSize
0x18039a303  mov     rdx, [rbp+57h+lpDst]; lpDst
0x18039a307  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x18039a30e  call    cs:__imp_ExpandEnvironmentStringsW
0x18039a315  nop     dword ptr [rax+rax+00h]
0x18039a31a  test    eax, eax
0x18039a31c  jnz     short loc_18039A342
0x18039a31e  call    cs:__imp_GetLastError
0x18039a325  nop     dword ptr [rax+rax+00h]
0x18039a32a  mov     esi, eax
0x18039a32c  test    eax, eax
0x18039a32e  jle     loc_18039A46B
0x18039a334  movzx   esi, ax
0x18039a337  or      esi, 80070000h
0x18039a33d  jmp     loc_18039A46B
0x18039a342  mov     eax, eax
0x18039a344  cmp     rax, rbx
0x18039a347  jbe     short loc_18039A353
0x18039a349  mov     esi, 8007007Ah
0x18039a34e  jmp     loc_18039A46B
0x18039a353  lea     rax, [rbx+16h]
0x18039a357  cmp     rax, rbx
0x18039a35a  jb      loc_18039A466
0x18039a360  lea     rbx, [rax+104h]
0x18039a367  cmp     rbx, rax
0x18039a36a  jb      loc_18039A466
0x18039a370  mov     [rbp+57h+Block], r13
0x18039a374  mov     rdx, rbx
0x18039a377  lea     rcx, [rbp+57h+Block]
0x18039a37b  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x18039a380  test    al, al
0x18039a382  jnz     short loc_18039A39E
0x18039a384  mov     rcx, [rbp+57h+Block]; Block
0x18039a388  call    cs:__imp_free
0x18039a38f  nop     dword ptr [rax+rax+00h]
0x18039a394  mov     esi, 8007000Eh
0x18039a399  jmp     loc_18039A46B
0x18039a39e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x18039a3a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x18039a3aa  mov     dl, [rsi+55h]
0x18039a3ad  lea     r8, pszDefault
0x18039a3b4  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x18039a3bb  mov     r9, [rbp+57h+lpDst]
0x18039a3bf  test    al, al
0x18039a3c1  jz      short loc_18039A416
0x18039a3c3  test    dl, dl
0x18039a3c5  cmovz   rcx, r8
0x18039a3c9  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x18039a3d0  cmp     [rsi+56h], r13b
0x18039a3d4  cmovz   rax, r8
0x18039a3d8  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x18039a3df  cmp     [rsi+54h], r13b
0x18039a3e3  cmovz   rdx, r8
0x18039a3e7  mov     [rsp+110h+lpCurrentDirectory], rcx
0x18039a3ec  mov     [rsp+110h+lpReturnSize], rax
0x18039a3f1  mov     [rsp+110h+lpPreviousValue], rdx
0x18039a3f6  mov     rax, [rsi]
0x18039a3f9  mov     [rsp+110h+cbSize], rax
0x18039a3fe  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x18039a405  mov     rdx, rbx; unsigned __int64
0x18039a408  mov     rbx, [rbp+57h+Block]
0x18039a40c  mov     rcx, rbx; unsigned __int16 *
0x18039a40f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18039a414  jmp     short loc_18039A453
0x18039a416  test    dl, dl
0x18039a418  cmovz   rcx, r8
0x18039a41c  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x18039a423  cmp     [rsi+54h], r13b
0x18039a427  cmovz   rdx, r8
0x18039a42b  mov     [rsp+110h+lpReturnSize], rcx
0x18039a430  mov     [rsp+110h+lpPreviousValue], rdx
0x18039a435  mov     rax, [rsi]
0x18039a438  mov     [rsp+110h+cbSize], rax
0x18039a43d  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x18039a444  mov     rdx, rbx; unsigned __int64
0x18039a447  mov     rbx, [rbp+57h+Block]
0x18039a44b  mov     rcx, rbx; unsigned __int16 *
0x18039a44e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18039a453  test    eax, eax
0x18039a455  jns     short loc_18039A482
0x18039a457  mov     rcx, rbx; Block
0x18039a45a  call    cs:__imp_free
0x18039a461  nop     dword ptr [rax+rax+00h]
0x18039a466  mov     esi, 80004005h
0x18039a46b  mov     rcx, [rbp+57h+lpDst]; Block
0x18039a46f  call    cs:__imp_free
0x18039a476  nop     dword ptr [rax+rax+00h]
0x18039a47b  mov     eax, esi
0x18039a47d  jmp     loc_18039A634
0x18039a482  xorps   xmm0, xmm0
0x18039a485  xor     eax, eax
0x18039a487  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18039a48b  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18039a48f  xor     edx, edx; Val
0x18039a491  lea     r8d, [rax+6Ch]; Size
0x18039a495  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18039a499  call    memset_0
0x18039a49e  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x18039a4a5  mov     [rbp+57h+Value], r13
0x18039a4a9  mov     r15d, r13d
0x18039a4ac  mov     r14, r13
0x18039a4af  mov     [rbp+57h+Size], r13
0x18039a4b3  test    r12d, r12d
0x18039a4b6  jz      loc_18039A571
0x18039a4bc  lea     rdx, [rbp+57h+Value]; void **
0x18039a4c0  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x18039a4c5  test    eax, eax
0x18039a4c7  js      loc_18039A571
0x18039a4cd  lea     r9, [rbp+57h+Size]; lpSize
0x18039a4d1  xor     r8d, r8d; dwFlags
0x18039a4d4  lea     r12d, [r8+1]
0x18039a4d8  mov     edx, r12d; dwAttributeCount
0x18039a4db  xor     ecx, ecx; lpAttributeList
0x18039a4dd  call    cs:__imp_InitializeProcThreadAttributeList
0x18039a4e4  nop     dword ptr [rax+rax+00h]
0x18039a4e9  mov     rsi, [rbp+57h+Size]
0x18039a4ed  call    cs:__imp_GetProcessHeap
0x18039a4f4  nop     dword ptr [rax+rax+00h]
0x18039a4f9  mov     r8, rsi; dwBytes
0x18039a4fc  xor     edx, edx; dwFlags
0x18039a4fe  mov     rcx, rax; hHeap
0x18039a501  call    cs:__imp_HeapAlloc
0x18039a508  nop     dword ptr [rax+rax+00h]
0x18039a50d  mov     r14, rax
0x18039a510  test    rax, rax
0x18039a513  jz      short loc_18039A571
0x18039a515  lea     r9, [rbp+57h+Size]; lpSize
0x18039a519  xor     r8d, r8d; dwFlags
0x18039a51c  mov     edx, r12d; dwAttributeCount
0x18039a51f  mov     rcx, rax; lpAttributeList
0x18039a522  call    cs:__imp_InitializeProcThreadAttributeList
0x18039a529  nop     dword ptr [rax+rax+00h]
0x18039a52e  test    eax, eax
0x18039a530  jz      short loc_18039A571
0x18039a532  mov     r15d, r12d
0x18039a535  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x18039a53a  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x18039a53f  mov     [rsp+110h+cbSize], 8; cbSize
0x18039a548  lea     r9, [rbp+57h+Value]; lpValue
0x18039a54c  xor     edx, edx; dwFlags
0x18039a54e  mov     r8d, 20000h; Attribute
0x18039a554  mov     rcx, r14; lpAttributeList
0x18039a557  call    cs:__imp_UpdateProcThreadAttribute
0x18039a55e  nop     dword ptr [rax+rax+00h]
0x18039a563  mov     rcx, [rbp+57h+var_28]
0x18039a567  test    eax, eax
0x18039a569  cmovnz  rcx, r14
0x18039a56d  mov     [rbp+57h+var_28], rcx
0x18039a571  lea     rax, [rbp+57h+ProcessInformation]
0x18039a575  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18039a57a  lea     rax, [rbp+57h+StartupInfo]
0x18039a57e  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x18039a583  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18039a588  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x18039a58d  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x18039a595  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x18039a59a  xor     r9d, r9d; lpThreadAttributes
0x18039a59d  xor     r8d, r8d; lpProcessAttributes
0x18039a5a0  mov     rdx, rbx; lpCommandLine
0x18039a5a3  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x18039a5a7  call    cs:__imp_CreateProcessW
0x18039a5ae  nop     dword ptr [rax+rax+00h]
0x18039a5b3  test    eax, eax
0x18039a5b5  jz      short loc_18039A5DC
0x18039a5b7  mov     esi, r13d
0x18039a5ba  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18039a5be  call    cs:__imp_CloseHandle
0x18039a5c5  nop     dword ptr [rax+rax+00h]
0x18039a5ca  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18039a5ce  call    cs:__imp_CloseHandle
0x18039a5d5  nop     dword ptr [rax+rax+00h]
0x18039a5da  jmp     short loc_18039A5E1
0x18039a5dc  mov     esi, 80004005h
0x18039a5e1  test    r15d, r15d
0x18039a5e4  jz      short loc_18039A5F5
0x18039a5e6  mov     rcx, r14; lpAttributeList
0x18039a5e9  call    cs:__imp_DeleteProcThreadAttributeList
0x18039a5f0  nop     dword ptr [rax+rax+00h]
0x18039a5f5  test    r14, r14
0x18039a5f8  jz      short loc_18039A61B
0x18039a5fa  call    cs:__imp_GetProcessHeap
0x18039a601  nop     dword ptr [rax+rax+00h]
0x18039a606  mov     rcx, rax; hHeap
0x18039a609  mov     r8, r14; lpMem
0x18039a60c  xor     edx, edx; dwFlags
0x18039a60e  call    cs:__imp_HeapFree
0x18039a615  nop     dword ptr [rax+rax+00h]
0x18039a61a  nop
0x18039a61b  mov     rcx, rbx; Block
0x18039a61e  call    cs:__imp_free
0x18039a625  nop     dword ptr [rax+rax+00h]
0x18039a62a  jmp     loc_18039A46B
0x18039a62f  mov     eax, 80004005h
0x18039a634  lea     r11, [rsp+110h+var_20]
0x18039a63c  mov     rbx, [r11+38h]
0x18039a640  mov     rsi, [r11+40h]
0x18039a644  mov     rsp, r11
0x18039a647  pop     r15
0x18039a649  pop     r14
0x18039a64b  pop     r13
0x18039a64d  pop     r12
0x18039a64f  pop     rbp
0x18039a650  retn
```
