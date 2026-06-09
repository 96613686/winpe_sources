# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x180021d44`
- end: `0x1800220bb`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `887`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800241b0`

## callees

- `0x18001a6c0`
- `0x18001e984`
- `0x180020dfc`
- `0x180021704`
- `0x180021d44`
- `0x1800226b4`
- `0x1800249d4`
- `0x18002d1ee`

## import_xrefs

- `msvcrt!free` at `0x180021e4c`
- `msvcrt!free` at `0x180021f18`
- `msvcrt!free` at `0x180021f27`
- `msvcrt!free` at `0x18002208e`
- `msvcrt!free` at `0x180021e4c`
- `msvcrt!free` at `0x180021f18`
- `msvcrt!free` at `0x180021f27`
- `msvcrt!free` at `0x18002208e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021fa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021fa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022084`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022084`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021f99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021f99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021de8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002204c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002204c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022056`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021dde`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021dde`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021f8f`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021fc2`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021f8f`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021fc2`
- `KERNEL32!UpdateProcThreadAttribute` at `0x180021ff1`
- `KERNEL32!UpdateProcThreadAttribute` at `0x180021ff1`
- `KERNEL32!CreateProcessW` at `0x18002203b`
- `KERNEL32!CreateProcessW` at `0x18002203b`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002206b`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002206b`

## string_xrefs

- `0x180021e87`: `/launchnarratorupdates`
- `0x180021d90`: `%SystemRoot%\System32\ATBroker.exe`
- `0x180021dd7`: `%SystemRoot%\System32\ATBroker.exe`

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
  const wchar_t *v16; // rdx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // eax
  const wchar_t *v20; // rdx
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
  const wchar_t *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const wchar_t *lpPreviousValuea; // [rsp+30h] [rbp-91h]
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
                v14 = &Data;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = &Data;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = &Data;
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
                v14 = &Data;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = &Data;
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
0x180021d44  mov     rax, rsp
0x180021d47  mov     [rax+10h], rbx
0x180021d4b  mov     [rax+18h], rsi
0x180021d4f  mov     [rax+8], rcx
0x180021d53  push    rbp
0x180021d54  push    r12
0x180021d56  push    r13
0x180021d58  push    r14
0x180021d5a  push    r15
0x180021d5c  lea     rbp, [rax-5Fh]
0x180021d60  sub     rsp, 0F0h
0x180021d67  mov     r12d, r8d
0x180021d6a  mov     rsi, rdx
0x180021d6d  mov     rcx, rdx; this
0x180021d70  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x180021d75  xor     r13d, r13d
0x180021d78  test    eax, eax
0x180021d7a  jz      short loc_180021D83
0x180021d7c  xor     eax, eax
0x180021d7e  jmp     loc_18002209E
0x180021d83  mov     [rbp+57h+lpDst], r13
0x180021d87  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x180021d8b  mov     edx, 7FFFFFFFh; unsigned __int64
0x180021d90  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x180021d97  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180021d9c  test    eax, eax
0x180021d9e  js      loc_180022099
0x180021da4  mov     rax, [rbp+57h+lpDst]
0x180021da8  lea     rbx, [rax+104h]
0x180021daf  cmp     rbx, rax
0x180021db2  jb      loc_180022099
0x180021db8  mov     [rbp+57h+lpDst], r13
0x180021dbc  mov     rdx, rbx
0x180021dbf  lea     rcx, [rbp+57h+lpDst]
0x180021dc3  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180021dc8  test    al, al
0x180021dca  jz      loc_180021E52
0x180021dd0  mov     r8d, ebx; nSize
0x180021dd3  mov     rdx, [rbp+57h+lpDst]; lpDst
0x180021dd7  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x180021dde  call    cs:__imp_ExpandEnvironmentStringsW
0x180021de4  test    eax, eax
0x180021de6  jnz     short loc_180021E06
0x180021de8  call    cs:__imp_GetLastError
0x180021dee  mov     esi, eax
0x180021df0  test    eax, eax
0x180021df2  jle     loc_180021F23
0x180021df8  movzx   esi, ax
0x180021dfb  or      esi, 80070000h
0x180021e01  jmp     loc_180021F23
0x180021e06  mov     eax, eax
0x180021e08  cmp     rax, rbx
0x180021e0b  jbe     short loc_180021E17
0x180021e0d  mov     esi, 8007007Ah
0x180021e12  jmp     loc_180021F23
0x180021e17  lea     rax, [rbx+16h]
0x180021e1b  cmp     rax, rbx
0x180021e1e  jb      loc_180021F1E
0x180021e24  lea     rbx, [rax+104h]
0x180021e2b  cmp     rbx, rax
0x180021e2e  jb      loc_180021F1E
0x180021e34  mov     [rbp+57h+Block], r13
0x180021e38  mov     rdx, rbx
0x180021e3b  lea     rcx, [rbp+57h+Block]
0x180021e3f  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180021e44  test    al, al
0x180021e46  jnz     short loc_180021E5C
0x180021e48  mov     rcx, [rbp+57h+Block]; Block
0x180021e4c  call    cs:__imp_free
0x180021e52  mov     esi, 8007000Eh
0x180021e57  jmp     loc_180021F23
0x180021e5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x180021e63  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x180021e68  mov     dl, [rsi+55h]
0x180021e6b  lea     r8, Data
0x180021e72  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x180021e79  mov     r9, [rbp+57h+lpDst]
0x180021e7d  test    al, al
0x180021e7f  jz      short loc_180021ED4
0x180021e81  test    dl, dl
0x180021e83  cmovz   rcx, r8
0x180021e87  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x180021e8e  cmp     [rsi+56h], r13b
0x180021e92  cmovz   rax, r8
0x180021e96  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x180021e9d  cmp     [rsi+54h], r13b
0x180021ea1  cmovz   rdx, r8
0x180021ea5  mov     [rsp+110h+lpCurrentDirectory], rcx
0x180021eaa  mov     [rsp+110h+lpReturnSize], rax
0x180021eaf  mov     [rsp+110h+lpPreviousValue], rdx
0x180021eb4  mov     rax, [rsi]
0x180021eb7  mov     [rsp+110h+cbSize], rax
0x180021ebc  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x180021ec3  mov     rdx, rbx; unsigned __int64
0x180021ec6  mov     rbx, [rbp+57h+Block]
0x180021eca  mov     rcx, rbx; unsigned __int16 *
0x180021ecd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021ed2  jmp     short loc_180021F11
0x180021ed4  test    dl, dl
0x180021ed6  cmovz   rcx, r8
0x180021eda  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x180021ee1  cmp     [rsi+54h], r13b
0x180021ee5  cmovz   rdx, r8
0x180021ee9  mov     [rsp+110h+lpReturnSize], rcx
0x180021eee  mov     [rsp+110h+lpPreviousValue], rdx
0x180021ef3  mov     rax, [rsi]
0x180021ef6  mov     [rsp+110h+cbSize], rax
0x180021efb  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x180021f02  mov     rdx, rbx; unsigned __int64
0x180021f05  mov     rbx, [rbp+57h+Block]
0x180021f09  mov     rcx, rbx; unsigned __int16 *
0x180021f0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021f11  test    eax, eax
0x180021f13  jns     short loc_180021F34
0x180021f15  mov     rcx, rbx; Block
0x180021f18  call    cs:__imp_free
0x180021f1e  mov     esi, 80004005h
0x180021f23  mov     rcx, [rbp+57h+lpDst]; Block
0x180021f27  call    cs:__imp_free
0x180021f2d  mov     eax, esi
0x180021f2f  jmp     loc_18002209E
0x180021f34  xorps   xmm0, xmm0
0x180021f37  xor     eax, eax
0x180021f39  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180021f3d  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180021f41  xor     edx, edx; Val
0x180021f43  lea     r8d, [rax+6Ch]; Size
0x180021f47  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x180021f4b  call    memset_0
0x180021f50  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x180021f57  mov     [rbp+57h+Value], r13
0x180021f5b  mov     r15d, r13d
0x180021f5e  mov     r14, r13
0x180021f61  mov     [rbp+57h+Size], r13
0x180021f65  test    r12d, r12d
0x180021f68  jz      loc_180022005
0x180021f6e  lea     rdx, [rbp+57h+Value]; void **
0x180021f72  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x180021f77  test    eax, eax
0x180021f79  js      loc_180022005
0x180021f7f  lea     r9, [rbp+57h+Size]; lpSize
0x180021f83  xor     r8d, r8d; dwFlags
0x180021f86  lea     r12d, [r8+1]
0x180021f8a  mov     edx, r12d; dwAttributeCount
0x180021f8d  xor     ecx, ecx; lpAttributeList
0x180021f8f  call    cs:__imp_InitializeProcThreadAttributeList
0x180021f95  mov     rsi, [rbp+57h+Size]
0x180021f99  call    cs:__imp_GetProcessHeap
0x180021f9f  mov     r8, rsi; dwBytes
0x180021fa2  xor     edx, edx; dwFlags
0x180021fa4  mov     rcx, rax; hHeap
0x180021fa7  call    cs:__imp_HeapAlloc
0x180021fad  mov     r14, rax
0x180021fb0  test    rax, rax
0x180021fb3  jz      short loc_180022005
0x180021fb5  lea     r9, [rbp+57h+Size]; lpSize
0x180021fb9  xor     r8d, r8d; dwFlags
0x180021fbc  mov     edx, r12d; dwAttributeCount
0x180021fbf  mov     rcx, rax; lpAttributeList
0x180021fc2  call    cs:__imp_InitializeProcThreadAttributeList
0x180021fc8  test    eax, eax
0x180021fca  jz      short loc_180022005
0x180021fcc  mov     r15d, r12d
0x180021fcf  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x180021fd4  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x180021fd9  mov     [rsp+110h+cbSize], 8; cbSize
0x180021fe2  lea     r9, [rbp+57h+Value]; lpValue
0x180021fe6  xor     edx, edx; dwFlags
0x180021fe8  mov     r8d, 20000h; Attribute
0x180021fee  mov     rcx, r14; lpAttributeList
0x180021ff1  call    cs:__imp_UpdateProcThreadAttribute
0x180021ff7  mov     rcx, [rbp+57h+var_28]
0x180021ffb  test    eax, eax
0x180021ffd  cmovnz  rcx, r14
0x180022001  mov     [rbp+57h+var_28], rcx
0x180022005  lea     rax, [rbp+57h+ProcessInformation]
0x180022009  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18002200e  lea     rax, [rbp+57h+StartupInfo]
0x180022012  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x180022017  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x18002201c  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x180022021  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x180022029  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x18002202e  xor     r9d, r9d; lpThreadAttributes
0x180022031  xor     r8d, r8d; lpProcessAttributes
0x180022034  mov     rdx, rbx; lpCommandLine
0x180022037  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x18002203b  call    cs:__imp_CreateProcessW
0x180022041  test    eax, eax
0x180022043  jz      short loc_18002205E
0x180022045  mov     esi, r13d
0x180022048  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18002204c  call    cs:__imp_CloseHandle
0x180022052  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180022056  call    cs:__imp_CloseHandle
0x18002205c  jmp     short loc_180022063
0x18002205e  mov     esi, 80004005h
0x180022063  test    r15d, r15d
0x180022066  jz      short loc_180022071
0x180022068  mov     rcx, r14; lpAttributeList
0x18002206b  call    cs:__imp_DeleteProcThreadAttributeList
0x180022071  test    r14, r14
0x180022074  jz      short loc_18002208B
0x180022076  call    cs:__imp_GetProcessHeap
0x18002207c  mov     rcx, rax; hHeap
0x18002207f  mov     r8, r14; lpMem
0x180022082  xor     edx, edx; dwFlags
0x180022084  call    cs:__imp_HeapFree
0x18002208a  nop
0x18002208b  mov     rcx, rbx; Block
0x18002208e  call    cs:__imp_free
0x180022094  jmp     loc_180021F23
0x180022099  mov     eax, 80004005h
0x18002209e  lea     r11, [rsp+110h+var_20]
0x1800220a6  mov     rbx, [r11+38h]
0x1800220aa  mov     rsi, [r11+40h]
0x1800220ae  mov     rsp, r11
0x1800220b1  pop     r15
0x1800220b3  pop     r14
0x1800220b5  pop     r13
0x1800220b7  pop     r12
0x1800220b9  pop     rbp
0x1800220ba  retn
```
